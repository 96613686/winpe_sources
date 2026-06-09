# DllGetClassObject

- ea: `0x180009ad0`
- end: `0x180009bc8`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800081a0`
- `0x180009ad0`
- `0x180019010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009b7e`
- `KERNEL32!LeaveCriticalSection` at `0x180009b7e`
- `KERNEL32!EnterCriticalSection` at `0x180009b53`
- `KERNEL32!EnterCriticalSection` at `0x180009b53`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT v6; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = qword_180022B48;
  if ( qword_180022B48 )
  {
    while ( *(_QWORD *)v7 )
    {
      if ( *(_QWORD *)(v7 + 16) )
      {
        rclsid = *(const IID *const *)v7;
        if ( v5->Data1 == **(_DWORD **)v7
          && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
          && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
          && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
        {
          v8 = (const IID *const *)(v7 + 32);
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          rclsid = *v8;
          if ( *v8 )
            v6 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                   rclsid,
                   riid,
                   ppv);
          break;
        }
      }
      v7 += 72;
    }
  }
  if ( !*ppv && !v6 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v6;
}

```

## disassembly

```asm
0x180009ad0  push    rbx
0x180009ad2  push    rbp
0x180009ad3  push    rsi
0x180009ad4  push    rdi
0x180009ad5  push    r14
0x180009ad7  push    r15
0x180009ad9  sub     rsp, 28h
0x180009add  mov     rsi, r8
0x180009ae0  mov     r15, rdx
0x180009ae3  mov     rbp, rcx
0x180009ae6  test    r8, r8
0x180009ae9  jnz     short loc_180009AF5
0x180009aeb  mov     edi, 80004003h
0x180009af0  jmp     loc_180009BB9
0x180009af5  mov     qword ptr [r8], 0
0x180009afc  xor     edi, edi
0x180009afe  mov     rbx, cs:qword_180022B48
0x180009b05  test    rbx, rbx
0x180009b08  jz      loc_180009B9F
0x180009b0e  jmp     short loc_180009B3C
0x180009b10  cmp     [rbx+10h], rdi
0x180009b14  jz      short loc_180009B38
0x180009b16  mov     rcx, [rbx]
0x180009b19  mov     eax, [rcx]
0x180009b1b  cmp     [rbp+0], eax
0x180009b1e  jnz     short loc_180009B38
0x180009b20  mov     eax, [rcx+4]
0x180009b23  cmp     [rbp+4], eax
0x180009b26  jnz     short loc_180009B38
0x180009b28  mov     eax, [rcx+8]
0x180009b2b  cmp     [rbp+8], eax
0x180009b2e  jnz     short loc_180009B38
0x180009b30  mov     eax, [rcx+0Ch]
0x180009b33  cmp     [rbp+0Ch], eax
0x180009b36  jz      short loc_180009B43
0x180009b38  add     rbx, 48h ; 'H'
0x180009b3c  cmp     [rbx], rdi
0x180009b3f  jnz     short loc_180009B10
0x180009b41  jmp     short loc_180009B9F
0x180009b43  lea     r14, [rbx+20h]
0x180009b47  cmp     [r14], rdi
0x180009b4a  jnz     short loc_180009B84
0x180009b4c  lea     rcx, CriticalSection; lpCriticalSection
0x180009b53  call    cs:__imp_EnterCriticalSection
0x180009b59  cmp     [r14], rdi
0x180009b5c  jnz     short loc_180009B77
0x180009b5e  mov     rcx, [rbx+18h]
0x180009b62  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009b69  mov     rax, [rbx+10h]
0x180009b6d  mov     r8, r14
0x180009b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b75  mov     edi, eax
0x180009b77  lea     rcx, CriticalSection; lpCriticalSection
0x180009b7e  call    cs:__imp_LeaveCriticalSection
0x180009b84  mov     rcx, [r14]
0x180009b87  test    rcx, rcx
0x180009b8a  jz      short loc_180009B9F
0x180009b8c  mov     rax, [rcx]
0x180009b8f  mov     r8, rsi
0x180009b92  mov     rdx, r15
0x180009b95  mov     rax, [rax]
0x180009b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b9d  mov     edi, eax
0x180009b9f  cmp     qword ptr [rsi], 0
0x180009ba3  jnz     short loc_180009BB9
0x180009ba5  test    edi, edi
0x180009ba7  jnz     short loc_180009BB9
0x180009ba9  mov     r9, rsi; void **
0x180009bac  mov     r8, r15; struct _GUID *
0x180009baf  mov     rdx, rbp; struct _GUID *
0x180009bb2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180009bb7  mov     edi, eax
0x180009bb9  mov     eax, edi
0x180009bbb  add     rsp, 28h
0x180009bbf  pop     r15
0x180009bc1  pop     r14
0x180009bc3  pop     rdi
0x180009bc4  pop     rsi
0x180009bc5  pop     rbp
0x180009bc6  pop     rbx
0x180009bc7  retn
```
