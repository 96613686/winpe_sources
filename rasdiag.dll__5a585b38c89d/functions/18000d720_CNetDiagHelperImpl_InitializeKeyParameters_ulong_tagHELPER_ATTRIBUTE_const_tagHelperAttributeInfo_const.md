# CNetDiagHelperImpl::InitializeKeyParameters(ulong,tagHELPER_ATTRIBUTE * const,tagHelperAttributeInfo const *)

- ea: `0x18000d720`
- end: `0x18000d85d`
- name: `?InitializeKeyParameters@CNetDiagHelperImpl@@IEAAJKQEAUtagHELPER_ATTRIBUTE@@PEBUtagHelperAttributeInfo@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, __int64, struct tagHELPER_ATTRIBUTE *const, const struct tagHelperAttributeInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800075c0`
- `0x1800075e0`
- `0x180009440`
- `0x18000a710`
- `0x18000b610`

## callees

- `0x18000678c`
- `0x18000d100`
- `0x18000d720`
- `0x18000dd64`
- `0x18000dede`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d815`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d815`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::InitializeKeyParameters(
        CNetDiagHelperImpl *this,
        __int64 a2,
        struct tagHELPER_ATTRIBUTE *const a3,
        const struct tagHelperAttributeInfo *a4)
{
  const struct tagHelperAttributeInfo *v5; // rdi
  __int64 v6; // rcx
  unsigned int v8; // ebp
  __int64 result; // rax
  int v10; // esi
  ATTRIBUTE_TYPE type; // r12d
  __int64 v12; // r15
  __int64 i; // r14
  __int64 v14; // rax
  bool v15; // zf
  __int64 j; // rdi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9

  v5 = a4;
  v6 = 1;
  v8 = a2;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(1, a2, a3, a4);
  if ( !v5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, a2, a3, a4);
  if ( !v8 && !*((_DWORD *)this + 6) && !*((_QWORD *)this + 4) )
    return 0;
  result = _attributes_array_t::Copy((LPVOID *)this + 3, v8, a3);
  if ( (int)result >= 0 )
  {
    v10 = 0;
    if ( !v8 )
      return 0;
LABEL_10:
    if ( v5 && (type = v5->type) != AT_INVALID )
    {
      v12 = *((_QWORD *)this + 4);
      if ( v12 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(v12 + 144 * i + 8) == type )
          {
            v14 = *(_QWORD *)(v12 + 144 * i);
            if ( v5->pwszName )
            {
              if ( !v14 )
                continue;
              v15 = wcsncmp_0(*(const wchar_t **)(v12 + 144 * i), v5->pwszName, 0xFFu) == 0;
            }
            else
            {
              v15 = v14 == 0;
            }
            if ( v15 )
            {
              if ( ++v10 < v8 )
              {
                ++v5;
                goto LABEL_10;
              }
              return 0;
            }
          }
        }
        for ( j = 0; (unsigned int)j < *((_DWORD *)this + 6); j = (unsigned int)(j + 1) )
          _attribute_t::FreeAll((LPVOID *)(*((_QWORD *)this + 4) + 144 * j));
      }
      CoTaskMemFree(*((LPVOID *)this + 4));
      *((_QWORD *)this + 4) = 0;
      *((_DWORD *)this + 6) = 0;
      MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
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
0x18000d720  push    rbx
0x18000d722  push    rbp
0x18000d723  push    rsi
0x18000d724  push    rdi
0x18000d725  push    r12
0x18000d727  push    r14
0x18000d729  push    r15
0x18000d72b  sub     rsp, 20h
0x18000d72f  mov     rbx, rcx
0x18000d732  mov     rdi, r9
0x18000d735  mov     ecx, 1
0x18000d73a  mov     rsi, r8
0x18000d73d  mov     ebp, edx
0x18000d73f  xor     eax, eax
0x18000d741  lock cmpxchg [rbx+10h], ecx
0x18000d746  jz      short loc_18000D74D
0x18000d748  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d74d  test    rdi, rdi
0x18000d750  jnz     short loc_18000D757
0x18000d752  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d757  test    ebp, ebp
0x18000d759  jnz     short loc_18000D76B
0x18000d75b  cmp     [rbx+18h], ebp
0x18000d75e  jnz     short loc_18000D76B
0x18000d760  cmp     qword ptr [rbx+20h], 0
0x18000d765  jz      loc_18000D84B
0x18000d76b  mov     r8, rsi; struct tagHELPER_ATTRIBUTE *
0x18000d76e  lea     rcx, [rbx+18h]; this
0x18000d772  mov     edx, ebp; unsigned int
0x18000d774  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x18000d779  test    eax, eax
0x18000d77b  js      loc_18000D84D
0x18000d781  xor     esi, esi
0x18000d783  test    ebp, ebp
0x18000d785  jz      loc_18000D84B
0x18000d78b  test    rdi, rdi
0x18000d78e  jz      loc_18000D84B
0x18000d794  mov     r12d, [rdi+8]
0x18000d798  test    r12d, r12d
0x18000d79b  jz      loc_18000D84B
0x18000d7a1  mov     r15, [rbx+20h]
0x18000d7a5  test    r15, r15
0x18000d7a8  jz      short loc_18000D811
0x18000d7aa  xor     r14d, r14d
0x18000d7ad  cmp     [rbx+18h], r14d
0x18000d7b1  jbe     short loc_18000D7F2
0x18000d7b3  lea     rcx, [r14+r14*8]
0x18000d7b7  add     rcx, rcx
0x18000d7ba  cmp     [r15+rcx*8+8], r12d
0x18000d7bf  jnz     short loc_18000D7E9
0x18000d7c1  mov     rdx, [rdi]; String2
0x18000d7c4  mov     rax, [r15+rcx*8]
0x18000d7c8  test    rdx, rdx
0x18000d7cb  jz      short loc_18000D7E4
0x18000d7cd  test    rax, rax
0x18000d7d0  jz      short loc_18000D7E9
0x18000d7d2  mov     r8d, 0FFh; MaxCount
0x18000d7d8  mov     rcx, rax; String1
0x18000d7db  call    wcsncmp_0
0x18000d7e0  test    eax, eax
0x18000d7e2  jmp     short loc_18000D7E7
0x18000d7e4  test    rax, rax
0x18000d7e7  jz      short loc_18000D83C
0x18000d7e9  inc     r14d
0x18000d7ec  cmp     r14d, [rbx+18h]
0x18000d7f0  jb      short loc_18000D7B3
0x18000d7f2  xor     edi, edi
0x18000d7f4  cmp     [rbx+18h], edi
0x18000d7f7  jbe     short loc_18000D811
0x18000d7f9  lea     rcx, [rdi+rdi*8]
0x18000d7fd  shl     rcx, 4
0x18000d801  add     rcx, [rbx+20h]; this
0x18000d805  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d80a  inc     edi
0x18000d80c  cmp     edi, [rbx+18h]
0x18000d80f  jb      short loc_18000D7F9
0x18000d811  mov     rcx, [rbx+20h]; pv
0x18000d815  call    cs:__imp_CoTaskMemFree
0x18000d81c  nop     dword ptr [rax+rax+00h]
0x18000d821  mov     qword ptr [rbx+20h], 0
0x18000d829  mov     dword ptr [rbx+18h], 0
0x18000d830  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d835  mov     eax, 80070057h
0x18000d83a  jmp     short loc_18000D84D
0x18000d83c  inc     esi
0x18000d83e  cmp     esi, ebp
0x18000d840  jnb     short loc_18000D84B
0x18000d842  add     rdi, 10h
0x18000d846  jmp     loc_18000D78B
0x18000d84b  xor     eax, eax
0x18000d84d  add     rsp, 20h
0x18000d851  pop     r15
0x18000d853  pop     r14
0x18000d855  pop     r12
0x18000d857  pop     rdi
0x18000d858  pop     rsi
0x18000d859  pop     rbp
0x18000d85a  pop     rbx
0x18000d85b  retn
```
