# SecurityDescriptor::SetDacl(Dacl const &,int)

- ea: `0x1401c84cc`
- end: `0x1401c8688`
- name: `?SetDacl@SecurityDescriptor@@QEAAPEAVFrsStatus@@AEBVDacl@@H@Z`
- size: `444`
- prototype: `struct FrsStatus *__fastcall(SecurityDescriptor *__hidden this, const struct Dacl *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14004b83c`
- `0x14004ef40`
- `0x1401c636c`

## callees

- `0x14000bbc5`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c71cc`
- `0x1401c74c0`
- `0x1401c77a8`
- `0x1401c84cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c854e`
- `KERNEL32!GetLastError` at `0x1401c8615`
- `KERNEL32!GetLastError` at `0x1401c854e`
- `KERNEL32!GetLastError` at `0x1401c8615`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8540`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8607`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8540`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8607`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1401c85f7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1401c85f7`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1401c8530`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1401c8530`

## string_xrefs

- `0x1401c8583`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c864a`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c8560`: `SecurityDescriptor::SetDacl`
- `0x1401c8627`: `SecurityDescriptor::SetDacl`

## pseudocode

```c
struct FrsStatus *__fastcall SecurityDescriptor::SetDacl(SecurityDescriptor *this, const void **a2, WINBOOL a3)
{
  struct FrsStatus *result; // rax
  void *v6; // rcx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  struct _ACL *v9; // rsi
  unsigned int Length; // ebx
  BOOL v11; // edx
  DWORD v12; // ebx
  DWORD v13; // eax
  __int64 v14; // rbx
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+80h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+88h] [rbp+20h] BYREF

  bDaclDefaulted = a3;
  if ( !*((_QWORD *)this + 1) || (result = SecurityDescriptor::MakeAbsolute(this)) == 0 )
  {
    pDacl = 0;
    v6 = (void *)*((_QWORD *)this + 1);
    if ( v6 )
    {
      bDaclDefaulted = 0;
      bDaclPresent = 0;
      if ( !GetSecurityDescriptorDacl(v6, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        return (struct FrsStatus *)FrsStatusList::PushNewError(
                                     "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                     LastError,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                     "SecurityDescriptor::SetDacl",
                                     2354,
                                     CurrentThreadId,
                                     0);
      }
    }
    else
    {
      result = SecurityDescriptor::Initialize(this);
      if ( result )
        return result;
    }
    if ( a2[3] )
    {
      Length = Acl::GetLength((Acl *)a2);
      v9 = (struct _ACL *)operator_new(Length);
      memcpy_0(v9, a2[3], Length);
    }
    else
    {
      v9 = 0;
    }
    v11 = !a2[3] || v9;
    if ( SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), v11, v9, 0) )
    {
      operator delete[](pDacl);
      return 0;
    }
    else
    {
      v12 = GetCurrentThreadId();
      v13 = GetLastError();
      v14 = FrsStatusList::PushNewError(
              "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
              v13,
              0,
              1,
              "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
              "SecurityDescriptor::SetDacl",
              2374,
              v12,
              0);
      operator delete[](v9);
      return (struct FrsStatus *)v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1401c84cc  mov     [rsp+arg_8], rbx
0x1401c84d1  mov     [rsp+bDaclDefaulted], r8d
0x1401c84d6  push    rbp
0x1401c84d7  push    rsi
0x1401c84d8  push    rdi
0x1401c84d9  sub     rsp, 50h
0x1401c84dd  cmp     qword ptr [rcx+8], 0
0x1401c84e2  mov     rbp, rdx
0x1401c84e5  mov     rdi, rcx
0x1401c84e8  jz      short loc_1401C84F8
0x1401c84ea  call    ?MakeAbsolute@SecurityDescriptor@@QEAAPEAVFrsStatus@@XZ; SecurityDescriptor::MakeAbsolute(void)
0x1401c84ef  test    rax, rax
0x1401c84f2  jnz     loc_1401C867A
0x1401c84f8  and     [rsp+68h+pDacl], 0
0x1401c8501  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1401c8505  test    rcx, rcx
0x1401c8508  jz      loc_1401C8599
0x1401c850e  and     [rsp+68h+bDaclDefaulted], 0
0x1401c8516  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1401c851e  and     [rsp+68h+bDaclPresent], 0
0x1401c8523  lea     r8, [rsp+68h+pDacl]; pDacl
0x1401c852b  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x1401c8530  call    cs:__imp_GetSecurityDescriptorDacl
0x1401c8537  nop     dword ptr [rax+rax+00h]
0x1401c853c  test    eax, eax
0x1401c853e  jnz     short loc_1401C85AA
0x1401c8540  call    cs:__imp_GetCurrentThreadId
0x1401c8547  nop     dword ptr [rax+rax+00h]
0x1401c854c  mov     ebx, eax
0x1401c854e  call    cs:__imp_GetLastError
0x1401c8555  nop     dword ptr [rax+rax+00h]
0x1401c855a  and     [rsp+68h+var_28], 0
0x1401c8560  lea     rcx, aSecuritydescri_0; "SecurityDescriptor::SetDacl"
0x1401c8567  mov     [rsp+68h+var_30], ebx
0x1401c856b  mov     r9d, 1
0x1401c8571  mov     [rsp+68h+var_38], 932h
0x1401c8579  xor     r8d, r8d
0x1401c857c  mov     [rsp+68h+var_40], rcx
0x1401c8581  mov     edx, eax
0x1401c8583  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c858a  mov     [rsp+68h+var_48], rcx
0x1401c858f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c8594  jmp     loc_1401C867A
0x1401c8599  mov     rcx, rdi; this
0x1401c859c  call    ?Initialize@SecurityDescriptor@@QEAAPEAVFrsStatus@@XZ; SecurityDescriptor::Initialize(void)
0x1401c85a1  test    rax, rax
0x1401c85a4  jnz     loc_1401C867A
0x1401c85aa  cmp     qword ptr [rbp+18h], 0
0x1401c85af  jnz     short loc_1401C85B5
0x1401c85b1  xor     esi, esi
0x1401c85b3  jmp     short loc_1401C85D8
0x1401c85b5  mov     rcx, rbp; this
0x1401c85b8  call    ?GetLength@Acl@@QEBAKXZ; Acl::GetLength(void)
0x1401c85bd  mov     ecx, eax; unsigned __int64
0x1401c85bf  mov     ebx, eax
0x1401c85c1  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c85c6  mov     rdx, [rbp+18h]; Src
0x1401c85ca  mov     r8d, ebx; Size
0x1401c85cd  mov     rcx, rax; void *
0x1401c85d0  mov     rsi, rax
0x1401c85d3  call    memcpy_0
0x1401c85d8  cmp     qword ptr [rbp+18h], 0
0x1401c85dd  jz      short loc_1401C85E8
0x1401c85df  test    rsi, rsi
0x1401c85e2  jnz     short loc_1401C85E8
0x1401c85e4  xor     edx, edx
0x1401c85e6  jmp     short loc_1401C85ED
0x1401c85e8  mov     edx, 1; bDaclPresent
0x1401c85ed  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1401c85f1  xor     r9d, r9d; bDaclDefaulted
0x1401c85f4  mov     r8, rsi; pDacl
0x1401c85f7  call    cs:__imp_SetSecurityDescriptorDacl
0x1401c85fe  nop     dword ptr [rax+rax+00h]
0x1401c8603  test    eax, eax
0x1401c8605  jnz     short loc_1401C866B
0x1401c8607  call    cs:__imp_GetCurrentThreadId
0x1401c860e  nop     dword ptr [rax+rax+00h]
0x1401c8613  mov     ebx, eax
0x1401c8615  call    cs:__imp_GetLastError
0x1401c861c  nop     dword ptr [rax+rax+00h]
0x1401c8621  and     [rsp+68h+var_28], 0
0x1401c8627  lea     rcx, aSecuritydescri_0; "SecurityDescriptor::SetDacl"
0x1401c862e  mov     [rsp+68h+var_30], ebx
0x1401c8632  mov     r9d, 1
0x1401c8638  mov     [rsp+68h+var_38], 946h
0x1401c8640  xor     r8d, r8d
0x1401c8643  mov     [rsp+68h+var_40], rcx
0x1401c8648  mov     edx, eax
0x1401c864a  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c8651  mov     [rsp+68h+var_48], rcx
0x1401c8656  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c865b  mov     rcx, rsi; Block
0x1401c865e  mov     rbx, rax
0x1401c8661  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c8666  mov     rax, rbx
0x1401c8669  jmp     short loc_1401C867A
0x1401c866b  mov     rcx, [rsp+68h+pDacl]; Block
0x1401c8673  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c8678  xor     eax, eax
0x1401c867a  mov     rbx, [rsp+68h+arg_8]
0x1401c867f  add     rsp, 50h
0x1401c8683  pop     rdi
0x1401c8684  pop     rsi
0x1401c8685  pop     rbp
0x1401c8686  retn
```
