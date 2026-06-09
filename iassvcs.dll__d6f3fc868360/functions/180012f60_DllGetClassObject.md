# DllGetClassObject

- ea: `0x180012f60`
- end: `0x180013058`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e7c8`
- `0x180012f60`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012fe3`
- `KERNEL32!EnterCriticalSection` at `0x180012fe3`
- `KERNEL32!LeaveCriticalSection` at `0x18001300e`
- `KERNEL32!LeaveCriticalSection` at `0x18001300e`

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
  v7 = qword_180024F98;
  if ( qword_180024F98 )
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
0x180012f60  push    rbx
0x180012f62  push    rbp
0x180012f63  push    rsi
0x180012f64  push    rdi
0x180012f65  push    r14
0x180012f67  push    r15
0x180012f69  sub     rsp, 28h
0x180012f6d  mov     rsi, r8
0x180012f70  mov     r15, rdx
0x180012f73  mov     rbp, rcx
0x180012f76  test    r8, r8
0x180012f79  jnz     short loc_180012F85
0x180012f7b  mov     edi, 80004003h
0x180012f80  jmp     loc_180013049
0x180012f85  mov     qword ptr [r8], 0
0x180012f8c  xor     edi, edi
0x180012f8e  mov     rbx, cs:qword_180024F98
0x180012f95  test    rbx, rbx
0x180012f98  jz      loc_18001302F
0x180012f9e  jmp     short loc_180012FCC
0x180012fa0  cmp     [rbx+10h], rdi
0x180012fa4  jz      short loc_180012FC8
0x180012fa6  mov     rcx, [rbx]
0x180012fa9  mov     eax, [rcx]
0x180012fab  cmp     [rbp+0], eax
0x180012fae  jnz     short loc_180012FC8
0x180012fb0  mov     eax, [rcx+4]
0x180012fb3  cmp     [rbp+4], eax
0x180012fb6  jnz     short loc_180012FC8
0x180012fb8  mov     eax, [rcx+8]
0x180012fbb  cmp     [rbp+8], eax
0x180012fbe  jnz     short loc_180012FC8
0x180012fc0  mov     eax, [rcx+0Ch]
0x180012fc3  cmp     [rbp+0Ch], eax
0x180012fc6  jz      short loc_180012FD3
0x180012fc8  add     rbx, 48h ; 'H'
0x180012fcc  cmp     [rbx], rdi
0x180012fcf  jnz     short loc_180012FA0
0x180012fd1  jmp     short loc_18001302F
0x180012fd3  lea     r14, [rbx+20h]
0x180012fd7  cmp     [r14], rdi
0x180012fda  jnz     short loc_180013014
0x180012fdc  lea     rcx, CriticalSection; lpCriticalSection
0x180012fe3  call    cs:__imp_EnterCriticalSection
0x180012fe9  cmp     [r14], rdi
0x180012fec  jnz     short loc_180013007
0x180012fee  mov     r8, r14
0x180012ff1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180012ff8  mov     rcx, [rbx+18h]
0x180012ffc  mov     rax, [rbx+10h]
0x180013000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013005  mov     edi, eax
0x180013007  lea     rcx, CriticalSection; lpCriticalSection
0x18001300e  call    cs:__imp_LeaveCriticalSection
0x180013014  mov     rcx, [r14]
0x180013017  test    rcx, rcx
0x18001301a  jz      short loc_18001302F
0x18001301c  mov     rax, [rcx]
0x18001301f  mov     r8, rsi
0x180013022  mov     rdx, r15
0x180013025  mov     rax, [rax]
0x180013028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302d  mov     edi, eax
0x18001302f  cmp     qword ptr [rsi], 0
0x180013033  jnz     short loc_180013049
0x180013035  test    edi, edi
0x180013037  jnz     short loc_180013049
0x180013039  mov     r9, rsi; void **
0x18001303c  mov     r8, r15; struct _GUID *
0x18001303f  mov     rdx, rbp; struct _GUID *
0x180013042  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180013047  mov     edi, eax
0x180013049  mov     eax, edi
0x18001304b  add     rsp, 28h
0x18001304f  pop     r15
0x180013051  pop     r14
0x180013053  pop     rdi
0x180013054  pop     rsi
0x180013055  pop     rbp
0x180013056  pop     rbx
0x180013057  retn
```
