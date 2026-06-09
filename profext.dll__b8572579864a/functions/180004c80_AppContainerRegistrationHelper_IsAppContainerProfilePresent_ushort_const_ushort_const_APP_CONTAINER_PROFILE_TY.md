# AppContainerRegistrationHelper::IsAppContainerProfilePresent(ushort const *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *,int *)

- ea: `0x180004c80`
- end: `0x180005082`
- name: `?IsAppContainerProfilePresent@AppContainerRegistrationHelper@@SAJPEBG0W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@PEAH@Z`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013de4`

## callees

- `0x180004250`
- `0x1800044e0`
- `0x180004594`
- `0x1800045bc`
- `0x180004c80`
- `0x18000a18c`
- `0x180022830`

## string_xrefs

- `0x180004ccf`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004d1f`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004d97`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004e83`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000503a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004e61`: `Path %ls dir %ls`
- `0x180004efd`: `Path %ls dir %ls`
- `0x180004f4b`: `Path %ls dir %ls`
- `0x180004f99`: `Path %ls dir %ls`
- `0x180004fe7`: `Path %ls dir %ls`
- `0x180004d14`: `Name %ls Sid %ls type %d`
- `0x180004d75`: `Path %ls`
- `0x180004eaf`: `Path %ls`
- `0x180004ed8`: `INetCache`
- `0x18000502e`: `Path %ls Sid %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::IsAppContainerProfilePresent(
        const char *a1,
        const unsigned __int16 *a2,
        int a3,
        const struct _GUID *a4,
        int *a5)
{
  int v10; // r14d
  unsigned int IsFolderPresent; // edi
  unsigned __int16 *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  int IsRegistryStoragePresent; // ebx
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v23[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x892,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
  *a5 = 0;
  v10 = AppContainerRegistrationHelper::DeriveTopLevelFolderPath(0, a1, v23, (__int64)a4, a3);
  if ( v10 < 0 )
  {
    LODWORD(v22) = a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x89D,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)v10,
      (int)"Name %ls Sid %ls type %d",
      a1,
      a2,
      v22);
    return (unsigned int)v10;
  }
  if ( a3 != 2 )
  {
    if ( ((a3 - 1) & 0xFFFFFFFD) != 0 )
    {
      IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, 0, a4, a5);
      if ( (IsFolderPresent & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x8A4,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)IsFolderPresent,
          (int)"Path %ls",
          (const char *)v23);
        return IsFolderPresent;
      }
      if ( !*a5 )
        return 0;
    }
    v12 = v23;
    v13 = 260;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v13;
    }
    while ( v13 );
    IsFolderPresent = v13 == 0 ? 0x80070057 : 0;
    v14 = (260 - v13) & -(__int64)(v13 != 0);
    if ( !v13 )
      goto LABEL_22;
    v15 = 2147483646;
    v16 = &v23[v14];
    v17 = L"\\AC";
    v18 = 260 - v14;
    if ( 260 != v14 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v17 )
          break;
        *v16++ = *v17++;
        --v15;
        --v18;
      }
      while ( v18 );
    }
    v19 = v16 - 1;
    IsFolderPresent = v18 == 0 ? 0x8007007A : 0;
    if ( v18 )
      v19 = v16;
    *v19 = 0;
    if ( !v18 )
    {
LABEL_22:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x8B4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)IsFolderPresent,
        (int)"Path %ls dir %ls",
        (const char *)v23,
        L"\\AC");
      return IsFolderPresent;
    }
  }
  IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, 0, a4, a5);
  if ( (IsFolderPresent & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8B8,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)IsFolderPresent,
      (int)"Path %ls",
      (const char *)v23);
    return IsFolderPresent;
  }
  if ( *a5 )
  {
    IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, L"INetCache", a4, a5);
    if ( (IsFolderPresent & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x8BD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)IsFolderPresent,
        (int)"Path %ls dir %ls",
        (const char *)v23,
        L"INetCache");
      return IsFolderPresent;
    }
    if ( *a5 )
    {
      IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, L"INetHistory", a4, a5);
      if ( (IsFolderPresent & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x8C2,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)IsFolderPresent,
          (int)"Path %ls dir %ls",
          (const char *)v23,
          L"INetHistory");
        return IsFolderPresent;
      }
      if ( *a5 )
      {
        IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, L"INetCookies", a4, a5);
        if ( (IsFolderPresent & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x8C7,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
            (const char *)IsFolderPresent,
            (int)"Path %ls dir %ls",
            (const char *)v23,
            L"INetCookies");
          return IsFolderPresent;
        }
        if ( *a5 )
        {
          IsFolderPresent = AppContainerRegistrationHelper::IsFolderPresent((char *)v23, L"Temp", a4, a5);
          if ( (IsFolderPresent & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x8CC,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)IsFolderPresent,
              (int)"Path %ls dir %ls",
              (const char *)v23,
              L"Temp");
            return IsFolderPresent;
          }
          if ( *a5 )
          {
            IsRegistryStoragePresent = AppContainerRegistrationHelper::IsRegistryStoragePresent(
                                         0,
                                         (const unsigned __int16 *)a1,
                                         a2,
                                         a4,
                                         a5);
            if ( IsRegistryStoragePresent < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x8D5,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
                (const char *)(unsigned int)IsRegistryStoragePresent,
                (int)"Path %ls Sid %ls",
                a1,
                a2);
              return (unsigned int)IsRegistryStoragePresent;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004c80  push    rbp
0x180004c82  push    rbx
0x180004c83  push    rsi
0x180004c84  push    rdi
0x180004c85  push    r12
0x180004c87  push    r13
0x180004c89  push    r14
0x180004c8b  push    r15
0x180004c8d  lea     rbp, [rsp-168h]
0x180004c95  sub     rsp, 268h
0x180004c9c  mov     rax, cs:__security_cookie
0x180004ca3  xor     rax, rsp
0x180004ca6  mov     [rbp+1A0h+var_50], rax
0x180004cad  mov     rbx, [rbp+1A0h+arg_20]
0x180004cb4  xor     r13d, r13d
0x180004cb7  mov     rsi, r9
0x180004cba  mov     edi, r8d
0x180004cbd  mov     r12, rdx
0x180004cc0  mov     r15, rcx
0x180004cc3  test    rbx, rbx
0x180004cc6  jnz     short loc_180004CF0
0x180004cc8  mov     rcx, [rbp+1A8h]; this
0x180004ccf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004cd6  mov     r9d, 80070057h; char *
0x180004cdc  mov     edx, 892h; void *
0x180004ce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ce6  mov     eax, 80070057h
0x180004ceb  jmp     loc_18000505E
0x180004cf0  lea     r8, [rsp+2A0h+var_260]
0x180004cf5  mov     [rbx], r13d
0x180004cf8  mov     rdx, r15
0x180004cfb  mov     dword ptr [rsp+2A0h+var_280], edi
0x180004cff  xor     ecx, ecx
0x180004d01  call    ?DeriveTopLevelFolderPath@AppContainerRegistrationHelper@@CAJPEAXPEBGPEAG_KW4APP_CONTAINER_PROFILE_TYPE@@@Z; AppContainerRegistrationHelper::DeriveTopLevelFolderPath(void *,ushort const *,ushort *,unsigned __int64,APP_CONTAINER_PROFILE_TYPE)
0x180004d06  mov     r14d, eax
0x180004d09  test    eax, eax
0x180004d0b  jns     short loc_180004D4A
0x180004d0d  mov     rcx, [rbp+1A8h]; this
0x180004d14  lea     rax, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x180004d1b  mov     dword ptr [rsp+2A0h+var_268], edi
0x180004d1f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004d26  mov     [rsp+2A0h+var_270], r12
0x180004d2b  mov     r9d, r14d; char *
0x180004d2e  mov     [rsp+2A0h+var_278], r15; char *
0x180004d33  mov     edx, 89Dh; void *
0x180004d38  mov     [rsp+2A0h+var_280], rax; int
0x180004d3d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004d42  mov     eax, r14d
0x180004d45  jmp     loc_18000505E
0x180004d4a  cmp     edi, 2
0x180004d4d  jz      loc_180004E97
0x180004d53  lea     eax, [rdi-1]
0x180004d56  test    eax, 0FFFFFFFDh
0x180004d5b  jz      short loc_180004DB6
0x180004d5d  mov     r9, rbx; int *
0x180004d60  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004d65  mov     r8, rsi; struct _GUID *
0x180004d68  xor     edx, edx; unsigned __int16 *
0x180004d6a  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004d6f  mov     edi, eax
0x180004d71  test    eax, eax
0x180004d73  jns     short loc_180004DAD
0x180004d75  lea     rdx, aPathLs_0; "Path %ls"
0x180004d7c  lea     rax, [rsp+2A0h+var_260]
0x180004d81  mov     [rsp+2A0h+var_278], rax; char *
0x180004d86  mov     [rsp+2A0h+var_280], rdx; int
0x180004d8b  mov     edx, 8A4h; void *
0x180004d90  mov     rcx, [rbp+1A8h]; this
0x180004d97  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004d9e  mov     r9d, edi; char *
0x180004da1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004da6  mov     eax, edi
0x180004da8  jmp     loc_18000505E
0x180004dad  cmp     [rbx], r13d
0x180004db0  jz      loc_18000505C
0x180004db6  mov     edx, 104h
0x180004dbb  lea     rax, [rsp+2A0h+var_260]
0x180004dc0  mov     r8d, edx
0x180004dc3  cmp     [rax], r13w
0x180004dc7  jz      short loc_180004DD3
0x180004dc9  add     rax, 2
0x180004dcd  sub     r8, 1
0x180004dd1  jnz     short loc_180004DC3
0x180004dd3  mov     rax, r8
0x180004dd6  lea     r10, aAc; "\\AC"
0x180004ddd  neg     rax
0x180004de0  mov     rcx, rdx
0x180004de3  mov     rax, r8
0x180004de6  sbb     edi, edi
0x180004de8  sub     rcx, r8
0x180004deb  not     edi
0x180004ded  and     edi, 80070057h
0x180004df3  neg     rax
0x180004df6  sbb     r9, r9
0x180004df9  and     r9, rcx
0x180004dfc  test    r8, r8
0x180004dff  jz      short loc_180004E5C
0x180004e01  lea     r8, [rsp+2A0h+var_260]
0x180004e06  mov     eax, 7FFFFFFEh
0x180004e0b  lea     r8, [r8+r9*2]
0x180004e0f  mov     rcx, r10
0x180004e12  sub     rdx, r9
0x180004e15  jz      short loc_180004E3B
0x180004e17  test    rax, rax
0x180004e1a  jz      short loc_180004E3B
0x180004e1c  movzx   r9d, word ptr [rcx]
0x180004e20  test    r9w, r9w
0x180004e24  jz      short loc_180004E3B
0x180004e26  mov     [r8], r9w
0x180004e2a  add     rcx, 2
0x180004e2e  add     r8, 2
0x180004e32  dec     rax
0x180004e35  sub     rdx, 1
0x180004e39  jnz     short loc_180004E17
0x180004e3b  mov     rax, rdx
0x180004e3e  lea     rcx, [r8-2]
0x180004e42  neg     rax
0x180004e45  sbb     edi, edi
0x180004e47  not     edi
0x180004e49  and     edi, 8007007Ah
0x180004e4f  test    rdx, rdx
0x180004e52  cmovnz  rcx, r8
0x180004e56  mov     [rcx], r13w
0x180004e5a  jnz     short loc_180004E97
0x180004e5c  mov     [rsp+2A0h+var_270], r10
0x180004e61  lea     rdx, aPathLsDirLs; "Path %ls dir %ls"
0x180004e68  lea     rax, [rsp+2A0h+var_260]
0x180004e6d  mov     [rsp+2A0h+var_278], rax; char *
0x180004e72  mov     [rsp+2A0h+var_280], rdx; int
0x180004e77  mov     edx, 8B4h; void *
0x180004e7c  mov     rcx, [rbp+1A8h]; this
0x180004e83  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004e8a  mov     r9d, edi; char *
0x180004e8d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004e92  jmp     loc_180004DA6
0x180004e97  mov     r9, rbx; int *
0x180004e9a  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004e9f  mov     r8, rsi; struct _GUID *
0x180004ea2  xor     edx, edx; unsigned __int16 *
0x180004ea4  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004ea9  mov     edi, eax
0x180004eab  test    eax, eax
0x180004ead  jns     short loc_180004ECF
0x180004eaf  lea     rdx, aPathLs_0; "Path %ls"
0x180004eb6  lea     rax, [rsp+2A0h+var_260]
0x180004ebb  mov     [rsp+2A0h+var_278], rax
0x180004ec0  mov     [rsp+2A0h+var_280], rdx
0x180004ec5  mov     edx, 8B8h
0x180004eca  jmp     loc_180004D90
0x180004ecf  cmp     [rbx], r13d
0x180004ed2  jz      loc_18000505C
0x180004ed8  lea     r14, aInetcache; "INetCache"
0x180004edf  mov     r9, rbx; int *
0x180004ee2  mov     rdx, r14; unsigned __int16 *
0x180004ee5  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004eea  mov     r8, rsi; struct _GUID *
0x180004eed  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004ef2  mov     edi, eax
0x180004ef4  test    eax, eax
0x180004ef6  jns     short loc_180004F1D
0x180004ef8  mov     [rsp+2A0h+var_270], r14
0x180004efd  lea     rdx, aPathLsDirLs; "Path %ls dir %ls"
0x180004f04  lea     rax, [rsp+2A0h+var_260]
0x180004f09  mov     [rsp+2A0h+var_278], rax
0x180004f0e  mov     [rsp+2A0h+var_280], rdx
0x180004f13  mov     edx, 8BDh
0x180004f18  jmp     loc_180004E7C
0x180004f1d  cmp     [rbx], r13d
0x180004f20  jz      loc_18000505C
0x180004f26  lea     r14, aInethistory; "INetHistory"
0x180004f2d  mov     r9, rbx; int *
0x180004f30  mov     rdx, r14; unsigned __int16 *
0x180004f33  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004f38  mov     r8, rsi; struct _GUID *
0x180004f3b  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004f40  mov     edi, eax
0x180004f42  test    eax, eax
0x180004f44  jns     short loc_180004F6B
0x180004f46  mov     [rsp+2A0h+var_270], r14
0x180004f4b  lea     rdx, aPathLsDirLs; "Path %ls dir %ls"
0x180004f52  lea     rax, [rsp+2A0h+var_260]
0x180004f57  mov     [rsp+2A0h+var_278], rax
0x180004f5c  mov     [rsp+2A0h+var_280], rdx
0x180004f61  mov     edx, 8C2h
0x180004f66  jmp     loc_180004E7C
0x180004f6b  cmp     [rbx], r13d
0x180004f6e  jz      loc_18000505C
0x180004f74  lea     r14, aInetcookies; "INetCookies"
0x180004f7b  mov     r9, rbx; int *
0x180004f7e  mov     rdx, r14; unsigned __int16 *
0x180004f81  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004f86  mov     r8, rsi; struct _GUID *
0x180004f89  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004f8e  mov     edi, eax
0x180004f90  test    eax, eax
0x180004f92  jns     short loc_180004FB9
0x180004f94  mov     [rsp+2A0h+var_270], r14
0x180004f99  lea     rdx, aPathLsDirLs; "Path %ls dir %ls"
0x180004fa0  lea     rax, [rsp+2A0h+var_260]
0x180004fa5  mov     [rsp+2A0h+var_278], rax
0x180004faa  mov     [rsp+2A0h+var_280], rdx
0x180004faf  mov     edx, 8C7h
0x180004fb4  jmp     loc_180004E7C
0x180004fb9  cmp     [rbx], r13d
0x180004fbc  jz      loc_18000505C
0x180004fc2  lea     r14, aTemp; "Temp"
0x180004fc9  mov     r9, rbx; int *
0x180004fcc  mov     rdx, r14; unsigned __int16 *
0x180004fcf  lea     rcx, [rsp+2A0h+var_260]; char *
0x180004fd4  mov     r8, rsi; struct _GUID *
0x180004fd7  call    ?IsFolderPresent@AppContainerRegistrationHelper@@CAJPEBG0PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsFolderPresent(ushort const *,ushort const *,_GUID const *,int *)
0x180004fdc  mov     edi, eax
0x180004fde  test    eax, eax
0x180004fe0  jns     short loc_180005007
0x180004fe2  mov     [rsp+2A0h+var_270], r14
0x180004fe7  lea     rdx, aPathLsDirLs; "Path %ls dir %ls"
0x180004fee  lea     rax, [rsp+2A0h+var_260]
0x180004ff3  mov     [rsp+2A0h+var_278], rax
0x180004ff8  mov     [rsp+2A0h+var_280], rdx
0x180004ffd  mov     edx, 8CCh
0x180005002  jmp     loc_180004E7C
0x180005007  cmp     [rbx], r13d
0x18000500a  jz      short loc_18000505C
0x18000500c  mov     r9, rsi; struct _GUID *
0x18000500f  mov     [rsp+2A0h+var_280], rbx; int *
0x180005014  mov     r8, r12; unsigned __int16 *
0x180005017  mov     rdx, r15; unsigned __int16 *
0x18000501a  xor     ecx, ecx; void *
0x18000501c  call    ?IsRegistryStoragePresent@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@PEAH@Z; AppContainerRegistrationHelper::IsRegistryStoragePresent(void *,ushort const *,ushort const *,_GUID const *,int *)
0x180005021  mov     ebx, eax
0x180005023  test    eax, eax
0x180005025  jns     short loc_18000505C
0x180005027  mov     rcx, [rbp+1A8h]; this
0x18000502e  lea     rax, aPathLsSidLs; "Path %ls Sid %ls"
0x180005035  mov     [rsp+2A0h+var_270], r12
0x18000503a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005041  mov     [rsp+2A0h+var_278], r15; char *
0x180005046  mov     r9d, ebx; char *
0x180005049  mov     edx, 8D5h; void *
0x18000504e  mov     [rsp+2A0h+var_280], rax; int
0x180005053  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005058  mov     eax, ebx
0x18000505a  jmp     short loc_18000505E
0x18000505c  xor     eax, eax
0x18000505e  mov     rcx, [rbp+1A0h+var_50]
0x180005065  xor     rcx, rsp; StackCookie
0x180005068  call    __security_check_cookie
0x18000506d  add     rsp, 268h
0x180005074  pop     r15
0x180005076  pop     r14
0x180005078  pop     r13
0x18000507a  pop     r12
0x18000507c  pop     rdi
0x18000507d  pop     rsi
0x18000507e  pop     rbx
0x18000507f  pop     rbp
0x180005080  retn
```
