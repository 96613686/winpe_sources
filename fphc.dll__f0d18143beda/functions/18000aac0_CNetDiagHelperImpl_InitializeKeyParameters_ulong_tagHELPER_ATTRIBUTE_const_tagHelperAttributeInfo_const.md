# CNetDiagHelperImpl::InitializeKeyParameters(ulong,tagHELPER_ATTRIBUTE * const,tagHelperAttributeInfo const *)

- ea: `0x18000aac0`
- end: `0x18000abe0`
- name: `?InitializeKeyParameters@CNetDiagHelperImpl@@IEAAJKQEAUtagHELPER_ATTRIBUTE@@PEBUtagHelperAttributeInfo@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, unsigned int, struct tagHELPER_ATTRIBUTE *const, const struct tagHelperAttributeInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008350`
- `0x180008370`

## callees

- `0x180006628`
- `0x18000a38c`
- `0x18000aac0`
- `0x18000edb8`
- `0x18001131a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab9f`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::InitializeKeyParameters(
        CNetDiagHelperImpl *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3,
        const struct tagHelperAttributeInfo *a4)
{
  __int64 result; // rax
  int v9; // esi
  ATTRIBUTE_TYPE type; // r12d
  __int64 v11; // r15
  __int64 i; // r14
  __int64 v13; // rax
  bool v14; // zf

  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 && !*((_DWORD *)this + 6) && !*((_QWORD *)this + 4) )
    return 0;
  result = _attributes_array_t::Copy((CNetDiagHelperImpl *)((char *)this + 24), a2, a3);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    if ( !a2 )
      return 0;
LABEL_10:
    if ( a4 && (type = a4->type) != AT_INVALID )
    {
      v11 = *((_QWORD *)this + 4);
      if ( v11 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(v11 + 144 * i + 8) == type )
          {
            v13 = *(_QWORD *)(v11 + 144 * i);
            if ( a4->pwszName )
            {
              if ( !v13 )
                continue;
              v14 = wcsncmp_0(*(const wchar_t **)(v11 + 144 * i), a4->pwszName, 0xFFu) == 0;
            }
            else
            {
              v14 = v13 == 0;
            }
            if ( v14 )
            {
              if ( ++v9 < a2 )
              {
                ++a4;
                goto LABEL_10;
              }
              return 0;
            }
          }
        }
      }
      _attributes_array_t::FreeElements((CNetDiagHelperImpl *)((char *)this + 24));
      CoTaskMemFree(*((LPVOID *)this + 4));
      *((_QWORD *)this + 4) = 0;
      *((_DWORD *)this + 6) = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return 2147942487LL;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000aac0  push    rbx
0x18000aac2  push    rbp
0x18000aac3  push    rsi
0x18000aac4  push    rdi
0x18000aac5  push    r12
0x18000aac7  push    r14
0x18000aac9  push    r15
0x18000aacb  sub     rsp, 20h
0x18000aacf  mov     rbx, rcx
0x18000aad2  mov     rdi, r9
0x18000aad5  mov     ecx, 1
0x18000aada  mov     rsi, r8
0x18000aadd  mov     ebp, edx
0x18000aadf  xor     eax, eax
0x18000aae1  lock cmpxchg [rbx+10h], ecx
0x18000aae6  jz      short loc_18000AAED
0x18000aae8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aaed  test    rdi, rdi
0x18000aaf0  jnz     short loc_18000AAF7
0x18000aaf2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000aaf7  test    ebp, ebp
0x18000aaf9  jnz     short loc_18000AB0B
0x18000aafb  cmp     [rbx+18h], ebp
0x18000aafe  jnz     short loc_18000AB0B
0x18000ab00  cmp     qword ptr [rbx+20h], 0
0x18000ab05  jz      loc_18000ABCF
0x18000ab0b  mov     r8, rsi; struct tagHELPER_ATTRIBUTE *
0x18000ab0e  lea     rcx, [rbx+18h]; this
0x18000ab12  mov     edx, ebp; unsigned int
0x18000ab14  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x18000ab19  test    eax, eax
0x18000ab1b  js      loc_18000ABD1
0x18000ab21  xor     esi, esi
0x18000ab23  test    ebp, ebp
0x18000ab25  jz      loc_18000ABCF
0x18000ab2b  test    rdi, rdi
0x18000ab2e  jz      loc_18000ABCF
0x18000ab34  mov     r12d, [rdi+8]
0x18000ab38  test    r12d, r12d
0x18000ab3b  jz      loc_18000ABCF
0x18000ab41  mov     r15, [rbx+20h]
0x18000ab45  test    r15, r15
0x18000ab48  jz      short loc_18000AB92
0x18000ab4a  xor     r14d, r14d
0x18000ab4d  cmp     [rbx+18h], r14d
0x18000ab51  jbe     short loc_18000AB92
0x18000ab53  lea     rcx, [r14+r14*8]
0x18000ab57  add     rcx, rcx
0x18000ab5a  cmp     [r15+rcx*8+8], r12d
0x18000ab5f  jnz     short loc_18000AB89
0x18000ab61  mov     rdx, [rdi]; String2
0x18000ab64  mov     rax, [r15+rcx*8]
0x18000ab68  test    rdx, rdx
0x18000ab6b  jz      short loc_18000AB84
0x18000ab6d  test    rax, rax
0x18000ab70  jz      short loc_18000AB89
0x18000ab72  mov     r8d, 0FFh; MaxCount
0x18000ab78  mov     rcx, rax; String1
0x18000ab7b  call    wcsncmp_0
0x18000ab80  test    eax, eax
0x18000ab82  jmp     short loc_18000AB87
0x18000ab84  test    rax, rax
0x18000ab87  jz      short loc_18000ABC0
0x18000ab89  inc     r14d
0x18000ab8c  cmp     r14d, [rbx+18h]
0x18000ab90  jb      short loc_18000AB53
0x18000ab92  lea     rcx, [rbx+18h]; this
0x18000ab96  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000ab9b  mov     rcx, [rbx+20h]; pv
0x18000ab9f  call    cs:__imp_CoTaskMemFree
0x18000aba5  mov     qword ptr [rbx+20h], 0
0x18000abad  mov     dword ptr [rbx+18h], 0
0x18000abb4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000abb9  mov     eax, 80070057h
0x18000abbe  jmp     short loc_18000ABD1
0x18000abc0  inc     esi
0x18000abc2  cmp     esi, ebp
0x18000abc4  jnb     short loc_18000ABCF
0x18000abc6  add     rdi, 10h
0x18000abca  jmp     loc_18000AB2B
0x18000abcf  xor     eax, eax
0x18000abd1  add     rsp, 20h
0x18000abd5  pop     r15
0x18000abd7  pop     r14
0x18000abd9  pop     r12
0x18000abdb  pop     rdi
0x18000abdc  pop     rsi
0x18000abdd  pop     rbp
0x18000abde  pop     rbx
0x18000abdf  retn
```
