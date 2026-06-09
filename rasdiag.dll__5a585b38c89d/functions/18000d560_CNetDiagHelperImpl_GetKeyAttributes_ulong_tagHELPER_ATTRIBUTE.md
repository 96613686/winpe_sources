# CNetDiagHelperImpl::GetKeyAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x18000d560`
- end: `0x18000d65d`
- name: `?GetKeyAttributes@CNetDiagHelperImpl@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *this, unsigned int *, struct tagHELPER_ATTRIBUTE **, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006274`
- `0x18000678c`
- `0x18000d560`
- `0x18000d9e0`
- `0x18000dd64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d63a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d63a`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetKeyAttributes(
        CNetDiagHelperImpl *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3,
        __int64 a4)
{
  unsigned int v7; // edx
  int v8; // ebx
  LPVOID *v9; // rdi
  unsigned int v10; // ebp
  __int64 j; // rsi
  struct tagHELPER_ATTRIBUTE *v12; // rbp
  __int64 i; // rbx
  unsigned int v15; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-30h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3, a4);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  if ( a2 && a3 )
  {
    v7 = *((_DWORD *)this + 6);
    v15 = 0;
    pv = 0;
    v8 = _attributes_array_t::SetCount((_attributes_array_t *)&v15, v7);
    if ( v8 >= 0 )
    {
      v12 = (struct tagHELPER_ATTRIBUTE *)pv;
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
        _attribute_t::Copy(&v12[i], (const struct tagHELPER_ATTRIBUTE *)(144 * i + *((_QWORD *)this + 4)));
      *a2 = v15;
      *a3 = v12;
      CoTaskMemFree(0);
      return 0;
    }
    else
    {
      v9 = (LPVOID *)pv;
      if ( pv )
      {
        v10 = v15;
        for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
          _attribute_t::FreeAll(&v9[18 * j]);
      }
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d560  push    rbx
0x18000d562  push    rbp
0x18000d563  push    rsi
0x18000d564  push    rdi
0x18000d565  push    r14
0x18000d567  sub     rsp, 30h
0x18000d56b  mov     rsi, r8
0x18000d56e  mov     r14, rdx
0x18000d571  mov     rdi, rcx
0x18000d574  test    rdx, rdx
0x18000d577  jnz     short loc_18000D57E
0x18000d579  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d57e  test    rsi, rsi
0x18000d581  jnz     short loc_18000D588
0x18000d583  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d588  cmp     dword ptr [rdi+10h], 1
0x18000d58c  jz      short loc_18000D593
0x18000d58e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d593  test    r14, r14
0x18000d596  jz      loc_18000D64A
0x18000d59c  test    rsi, rsi
0x18000d59f  jz      loc_18000D64A
0x18000d5a5  mov     edx, [rdi+18h]; unsigned int
0x18000d5a8  lea     rcx, [rsp+58h+var_38]; this
0x18000d5ad  mov     [rsp+58h+var_38], 0
0x18000d5b5  mov     [rsp+58h+pv], 0
0x18000d5be  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x18000d5c3  mov     ebx, eax
0x18000d5c5  test    eax, eax
0x18000d5c7  jns     short loc_18000D604
0x18000d5c9  mov     rdi, [rsp+58h+pv]
0x18000d5ce  test    rdi, rdi
0x18000d5d1  jz      short loc_18000D5F3
0x18000d5d3  mov     ebp, [rsp+58h+var_38]
0x18000d5d7  xor     esi, esi
0x18000d5d9  test    ebp, ebp
0x18000d5db  jz      short loc_18000D5F3
0x18000d5dd  lea     rcx, [rsi+rsi*8]
0x18000d5e1  shl     rcx, 4
0x18000d5e5  add     rcx, rdi; this
0x18000d5e8  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000d5ed  inc     esi
0x18000d5ef  cmp     esi, ebp
0x18000d5f1  jb      short loc_18000D5DD
0x18000d5f3  mov     rcx, rdi; pv
0x18000d5f6  call    cs:__imp_CoTaskMemFree
0x18000d5fd  nop     dword ptr [rax+rax+00h]
0x18000d602  jmp     short loc_18000D64F
0x18000d604  mov     rbp, [rsp+58h+pv]
0x18000d609  xor     ebx, ebx
0x18000d60b  cmp     [rdi+18h], ebx
0x18000d60e  jbe     short loc_18000D62E
0x18000d610  mov     rdx, [rdi+20h]
0x18000d614  lea     rcx, [rbx+rbx*8]
0x18000d618  shl     rcx, 4
0x18000d61c  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x18000d61f  add     rcx, rbp; this
0x18000d622  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000d627  inc     ebx
0x18000d629  cmp     ebx, [rdi+18h]
0x18000d62c  jb      short loc_18000D610
0x18000d62e  mov     eax, [rsp+58h+var_38]
0x18000d632  xor     ecx, ecx; pv
0x18000d634  mov     [r14], eax
0x18000d637  mov     [rsi], rbp
0x18000d63a  call    cs:__imp_CoTaskMemFree
0x18000d641  nop     dword ptr [rax+rax+00h]
0x18000d646  xor     ebx, ebx
0x18000d648  jmp     short loc_18000D64F
0x18000d64a  mov     ebx, 80070057h
0x18000d64f  mov     eax, ebx
0x18000d651  add     rsp, 30h
0x18000d655  pop     r14
0x18000d657  pop     rdi
0x18000d658  pop     rsi
0x18000d659  pop     rbp
0x18000d65a  pop     rbx
0x18000d65b  retn
```
