# DllGetClassObject

- ea: `0x180008fc0`
- end: `0x1800090b8`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006160`
- `0x180008fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000906e`
- `KERNEL32!LeaveCriticalSection` at `0x18000906e`
- `KERNEL32!EnterCriticalSection` at `0x180009043`
- `KERNEL32!EnterCriticalSection` at `0x180009043`

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
  v7 = qword_18001AC68;
  if ( qword_18001AC68 )
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
            EnterCriticalSection(&stru_18001A210);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&stru_18001A210);
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
0x180008fc0  push    rbx
0x180008fc2  push    rbp
0x180008fc3  push    rsi
0x180008fc4  push    rdi
0x180008fc5  push    r14
0x180008fc7  push    r15
0x180008fc9  sub     rsp, 28h
0x180008fcd  mov     rsi, r8
0x180008fd0  mov     r15, rdx
0x180008fd3  mov     rbp, rcx
0x180008fd6  test    r8, r8
0x180008fd9  jnz     short loc_180008FE5
0x180008fdb  mov     edi, 80004003h
0x180008fe0  jmp     loc_1800090A9
0x180008fe5  mov     qword ptr [r8], 0
0x180008fec  xor     edi, edi
0x180008fee  mov     rbx, cs:qword_18001AC68
0x180008ff5  test    rbx, rbx
0x180008ff8  jz      loc_18000908F
0x180008ffe  jmp     short loc_18000902C
0x180009000  cmp     [rbx+10h], rdi
0x180009004  jz      short loc_180009028
0x180009006  mov     rcx, [rbx]
0x180009009  mov     eax, [rcx]
0x18000900b  cmp     [rbp+0], eax
0x18000900e  jnz     short loc_180009028
0x180009010  mov     eax, [rcx+4]
0x180009013  cmp     [rbp+4], eax
0x180009016  jnz     short loc_180009028
0x180009018  mov     eax, [rcx+8]
0x18000901b  cmp     [rbp+8], eax
0x18000901e  jnz     short loc_180009028
0x180009020  mov     eax, [rcx+0Ch]
0x180009023  cmp     [rbp+0Ch], eax
0x180009026  jz      short loc_180009033
0x180009028  add     rbx, 48h ; 'H'
0x18000902c  cmp     [rbx], rdi
0x18000902f  jnz     short loc_180009000
0x180009031  jmp     short loc_18000908F
0x180009033  lea     r14, [rbx+20h]
0x180009037  cmp     [r14], rdi
0x18000903a  jnz     short loc_180009074
0x18000903c  lea     rcx, stru_18001A210; lpCriticalSection
0x180009043  call    cs:__imp_EnterCriticalSection
0x180009049  cmp     [r14], rdi
0x18000904c  jnz     short loc_180009067
0x18000904e  mov     rcx, [rbx+18h]
0x180009052  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009059  mov     rax, [rbx+10h]
0x18000905d  mov     r8, r14
0x180009060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009065  mov     edi, eax
0x180009067  lea     rcx, stru_18001A210; lpCriticalSection
0x18000906e  call    cs:__imp_LeaveCriticalSection
0x180009074  mov     rcx, [r14]
0x180009077  test    rcx, rcx
0x18000907a  jz      short loc_18000908F
0x18000907c  mov     rax, [rcx]
0x18000907f  mov     r8, rsi
0x180009082  mov     rdx, r15
0x180009085  mov     rax, [rax]
0x180009088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000908d  mov     edi, eax
0x18000908f  cmp     qword ptr [rsi], 0
0x180009093  jnz     short loc_1800090A9
0x180009095  test    edi, edi
0x180009097  jnz     short loc_1800090A9
0x180009099  mov     r9, rsi; void **
0x18000909c  mov     r8, r15; struct _GUID *
0x18000909f  mov     rdx, rbp; struct _GUID *
0x1800090a2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800090a7  mov     edi, eax
0x1800090a9  mov     eax, edi
0x1800090ab  add     rsp, 28h
0x1800090af  pop     r15
0x1800090b1  pop     r14
0x1800090b3  pop     rdi
0x1800090b4  pop     rsi
0x1800090b5  pop     rbp
0x1800090b6  pop     rbx
0x1800090b7  retn
```
