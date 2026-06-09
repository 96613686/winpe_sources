# DllGetClassObject

- ea: `0x180005b40`
- end: `0x180005c38`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003378`
- `0x180005b40`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005bee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005bee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005bc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005bc3`

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
  v7 = qword_18000B808;
  if ( qword_18000B808 )
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
0x180005b40  push    rbx
0x180005b42  push    rbp
0x180005b43  push    rsi
0x180005b44  push    rdi
0x180005b45  push    r14
0x180005b47  push    r15
0x180005b49  sub     rsp, 28h
0x180005b4d  mov     rsi, r8
0x180005b50  mov     r15, rdx
0x180005b53  mov     rbp, rcx
0x180005b56  test    r8, r8
0x180005b59  jnz     short loc_180005B65
0x180005b5b  mov     edi, 80004003h
0x180005b60  jmp     loc_180005C29
0x180005b65  mov     qword ptr [r8], 0
0x180005b6c  xor     edi, edi
0x180005b6e  mov     rbx, cs:qword_18000B808
0x180005b75  test    rbx, rbx
0x180005b78  jz      loc_180005C0F
0x180005b7e  jmp     short loc_180005BAC
0x180005b80  cmp     [rbx+10h], rdi
0x180005b84  jz      short loc_180005BA8
0x180005b86  mov     rcx, [rbx]
0x180005b89  mov     eax, [rcx]
0x180005b8b  cmp     [rbp+0], eax
0x180005b8e  jnz     short loc_180005BA8
0x180005b90  mov     eax, [rcx+4]
0x180005b93  cmp     [rbp+4], eax
0x180005b96  jnz     short loc_180005BA8
0x180005b98  mov     eax, [rcx+8]
0x180005b9b  cmp     [rbp+8], eax
0x180005b9e  jnz     short loc_180005BA8
0x180005ba0  mov     eax, [rcx+0Ch]
0x180005ba3  cmp     [rbp+0Ch], eax
0x180005ba6  jz      short loc_180005BB3
0x180005ba8  add     rbx, 48h ; 'H'
0x180005bac  cmp     [rbx], rdi
0x180005baf  jnz     short loc_180005B80
0x180005bb1  jmp     short loc_180005C0F
0x180005bb3  lea     r14, [rbx+20h]
0x180005bb7  cmp     [r14], rdi
0x180005bba  jnz     short loc_180005BF4
0x180005bbc  lea     rcx, CriticalSection; lpCriticalSection
0x180005bc3  call    cs:__imp_EnterCriticalSection
0x180005bc9  cmp     [r14], rdi
0x180005bcc  jnz     short loc_180005BE7
0x180005bce  mov     rcx, [rbx+18h]
0x180005bd2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180005bd9  mov     rax, [rbx+10h]
0x180005bdd  mov     r8, r14
0x180005be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be5  mov     edi, eax
0x180005be7  lea     rcx, CriticalSection; lpCriticalSection
0x180005bee  call    cs:__imp_LeaveCriticalSection
0x180005bf4  mov     rcx, [r14]
0x180005bf7  test    rcx, rcx
0x180005bfa  jz      short loc_180005C0F
0x180005bfc  mov     rax, [rcx]
0x180005bff  mov     r8, rsi
0x180005c02  mov     rdx, r15
0x180005c05  mov     rax, [rax]
0x180005c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c0d  mov     edi, eax
0x180005c0f  cmp     qword ptr [rsi], 0
0x180005c13  jnz     short loc_180005C29
0x180005c15  test    edi, edi
0x180005c17  jnz     short loc_180005C29
0x180005c19  mov     r9, rsi; void **
0x180005c1c  mov     r8, r15; struct _GUID *
0x180005c1f  mov     rdx, rbp; struct _GUID *
0x180005c22  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180005c27  mov     edi, eax
0x180005c29  mov     eax, edi
0x180005c2b  add     rsp, 28h
0x180005c2f  pop     r15
0x180005c31  pop     r14
0x180005c33  pop     rdi
0x180005c34  pop     rsi
0x180005c35  pop     rbp
0x180005c36  pop     rbx
0x180005c37  retn
```
