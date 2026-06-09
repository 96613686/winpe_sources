# UpdateSecurityDescriptor(void *,_ACL *,void * *)

- ea: `0x180010f30`
- end: `0x18001121f`
- name: `?UpdateSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX@Z`
- size: `751`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, struct _ACL *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800106c0`

## callees

- `0x1800081a4`
- `0x1800081c4`
- `0x180010f30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fe2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ff0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ffe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001100c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001112a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fe2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ff0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ffe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001100c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001112a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001107f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001108d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001109b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011183`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001119f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001107f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001108d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001109b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011183`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001119f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111fc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800110f8`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001113d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800110f8`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18001113d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800110d4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800110d4`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180010f9f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011055`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180010f9f`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011055`

## string_xrefs

- `0x180010fad`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x180011068`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x180011106`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`
- `0x18001114b`: `onecoreuap\admin\dm\configmanager2\service\cmlockservice\cmlockserviceapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall UpdateSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor,
        struct _ACL *a2,
        void **a3)
{
  unsigned int LastError; // r12d
  HLOCAL v7; // rbx
  struct _ACL *v8; // rdi
  struct _ACL *pSacl; // rsi
  HLOCAL pOwner; // r14
  HLOCAL pPrimaryGroup; // r15
  const char *v12; // r9
  __int64 v13; // rdx
  HLOCAL v14; // r12
  const char *v15; // r9
  unsigned int v16; // r13d
  SIZE_T uBytes; // [rsp+60h] [rbp-20h] BYREF
  DWORD dwDaclSize; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp-14h] BYREF
  DWORD dwBufferLength[4]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  SIZE_T lpdwPrimaryGroupSize; // [rsp+D8h] [rbp+58h] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  uBytes = 0;
  LODWORD(lpdwPrimaryGroupSize) = 0;
  if ( MakeAbsoluteSD(
         pSelfRelativeSecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         (LPDWORD)&uBytes + 1,
         0,
         (LPDWORD)&uBytes,
         0,
         (LPDWORD)&lpdwPrimaryGroupSize) )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33E,
      (int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
      (const char *)0x8000FFFFLL);
    return LastError;
  }
  v7 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
  v8 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
  pSacl = (struct _ACL *)LocalAlloc(0, HIDWORD(uBytes));
  pOwner = LocalAlloc(0, (unsigned int)uBytes);
  pPrimaryGroup = LocalAlloc(0, (unsigned int)lpdwPrimaryGroupSize);
  if ( !MakeAbsoluteSD(
          pSelfRelativeSecurityDescriptor,
          v7,
          &dwAbsoluteSecurityDescriptorSize,
          v8,
          &dwDaclSize,
          pSacl,
          (LPDWORD)&uBytes + 1,
          pOwner,
          (LPDWORD)&uBytes,
          pPrimaryGroup,
          (LPDWORD)&lpdwPrimaryGroupSize) )
  {
    v13 = 850;
LABEL_6:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
                  v12);
LABEL_7:
    if ( pPrimaryGroup )
      LocalFree(pPrimaryGroup);
    if ( pOwner )
      LocalFree(pOwner);
    if ( pSacl )
      LocalFree(pSacl);
    if ( v8 )
      LocalFree(v8);
    if ( v7 )
      LocalFree(v7);
    return LastError;
  }
  if ( !SetSecurityDescriptorDacl(v7, 1, a2, 0) )
  {
    v13 = 857;
    goto LABEL_6;
  }
  dwBufferLength[0] = 0;
  if ( MakeSelfRelativeSD(v7, 0, dwBufferLength) )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x364,
      (int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
      (const char *)0x8000FFFFLL);
    goto LABEL_7;
  }
  v14 = LocalAlloc(0, dwBufferLength[0]);
  if ( MakeSelfRelativeSD(v7, v14, dwBufferLength) )
  {
    *a3 = v14;
    if ( pPrimaryGroup )
      LocalFree(pPrimaryGroup);
    if ( pOwner )
      LocalFree(pOwner);
    if ( pSacl )
      LocalFree(pSacl);
    if ( v8 )
      LocalFree(v8);
    if ( v7 )
      LocalFree(v7);
    return 0;
  }
  else
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x36C,
            (int)"onecoreuap\\admin\\dm\\configmanager2\\service\\cmlockservice\\cmlockserviceapiimpl.cpp",
            v15);
    if ( v14 )
      LocalFree(v14);
    if ( pPrimaryGroup )
      LocalFree(pPrimaryGroup);
    if ( pOwner )
      LocalFree(pOwner);
    if ( pSacl )
      LocalFree(pSacl);
    if ( v8 )
      LocalFree(v8);
    if ( v7 )
      LocalFree(v7);
    return v16;
  }
}

```

## disassembly

```asm
0x180010f30  mov     r11, rsp
0x180010f33  mov     [r11+8], rbx
0x180010f37  mov     [r11+10h], rdx
0x180010f3b  push    rbp
0x180010f3c  push    rsi
0x180010f3d  push    rdi
0x180010f3e  push    r12
0x180010f40  push    r13
0x180010f42  push    r14
0x180010f44  push    r15
0x180010f46  mov     rbp, rsp
0x180010f49  sub     rsp, 80h
0x180010f50  xor     ebx, ebx
0x180010f52  lea     rax, [rbp+arg_18]
0x180010f56  mov     [r11-68h], rax
0x180010f5a  mov     r13, r8
0x180010f5d  mov     [r11-70h], rbx
0x180010f61  lea     rax, [rbp+uBytes]
0x180010f65  mov     [r11-78h], rax
0x180010f69  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180010f6d  mov     [r11-80h], rbx
0x180010f71  lea     rax, [rbp+uBytes+4]
0x180010f75  mov     [rsp+80h+lpdwSaclSize], rax; lpdwSaclSize
0x180010f7a  xor     r9d, r9d; pDacl
0x180010f7d  lea     rax, [rbp+dwDaclSize]
0x180010f81  mov     [rsp+80h+pSacl], rbx; pSacl
0x180010f86  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180010f88  mov     [rsp+80h+lpdwDaclSize], rax; int
0x180010f8d  mov     r12, rcx
0x180010f90  mov     [rbp+dwAbsoluteSecurityDescriptorSize], ebx
0x180010f93  mov     [rbp+dwDaclSize], ebx
0x180010f96  mov     dword ptr [rbp+uBytes+4], ebx
0x180010f99  mov     dword ptr [rbp+uBytes], ebx
0x180010f9c  mov     dword ptr [rbp+arg_18], ebx
0x180010f9f  call    cs:__imp_MakeAbsoluteSD
0x180010fa5  test    eax, eax
0x180010fa7  jz      short loc_180010FCF
0x180010fa9  mov     rcx, [rbp+38h]; this
0x180010fad  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x180010fb4  mov     r12d, 8000FFFFh
0x180010fba  mov     edx, 33Eh; void *
0x180010fbf  mov     r9d, r12d; char *
0x180010fc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fc7  mov     eax, r12d
0x180010fca  jmp     loc_180011204
0x180010fcf  mov     edx, [rbp+dwAbsoluteSecurityDescriptorSize]; uBytes
0x180010fd2  xor     ecx, ecx; uFlags
0x180010fd4  call    cs:__imp_LocalAlloc
0x180010fda  mov     edx, [rbp+dwDaclSize]; uBytes
0x180010fdd  xor     ecx, ecx; uFlags
0x180010fdf  mov     rbx, rax
0x180010fe2  call    cs:__imp_LocalAlloc
0x180010fe8  mov     edx, dword ptr [rbp+uBytes+4]; uBytes
0x180010feb  xor     ecx, ecx; uFlags
0x180010fed  mov     rdi, rax
0x180010ff0  call    cs:__imp_LocalAlloc
0x180010ff6  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180010ff9  xor     ecx, ecx; uFlags
0x180010ffb  mov     rsi, rax
0x180010ffe  call    cs:__imp_LocalAlloc
0x180011004  mov     edx, dword ptr [rbp+arg_18]; uBytes
0x180011007  xor     ecx, ecx; uFlags
0x180011009  mov     r14, rax
0x18001100c  call    cs:__imp_LocalAlloc
0x180011012  mov     r9, rdi; pDacl
0x180011015  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180011019  mov     r15, rax
0x18001101c  mov     rdx, rbx; pAbsoluteSecurityDescriptor
0x18001101f  lea     rax, [rbp+arg_18]
0x180011023  mov     rcx, r12; pSelfRelativeSecurityDescriptor
0x180011026  mov     [rsp+80h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18001102b  lea     rax, [rbp+uBytes]
0x18001102f  mov     [rsp+80h+pPrimaryGroup], r15; pPrimaryGroup
0x180011034  mov     [rsp+80h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180011039  lea     rax, [rbp+uBytes+4]
0x18001103d  mov     [rsp+80h+pOwner], r14; pOwner
0x180011042  mov     [rsp+80h+lpdwSaclSize], rax; lpdwSaclSize
0x180011047  lea     rax, [rbp+dwDaclSize]
0x18001104b  mov     [rsp+80h+pSacl], rsi; pSacl
0x180011050  mov     [rsp+80h+lpdwDaclSize], rax; int
0x180011055  call    cs:__imp_MakeAbsoluteSD
0x18001105b  test    eax, eax
0x18001105d  jnz     short loc_1800110C6
0x18001105f  mov     edx, 352h; void *
0x180011064  mov     rcx, [rbp+38h]; this
0x180011068  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x18001106f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011074  mov     r12d, eax
0x180011077  test    r15, r15
0x18001107a  jz      short loc_180011085
0x18001107c  mov     rcx, r15; hMem
0x18001107f  call    cs:__imp_LocalFree
0x180011085  test    r14, r14
0x180011088  jz      short loc_180011093
0x18001108a  mov     rcx, r14; hMem
0x18001108d  call    cs:__imp_LocalFree
0x180011093  test    rsi, rsi
0x180011096  jz      short loc_1800110A1
0x180011098  mov     rcx, rsi; hMem
0x18001109b  call    cs:__imp_LocalFree
0x1800110a1  test    rdi, rdi
0x1800110a4  jz      short loc_1800110AF
0x1800110a6  mov     rcx, rdi; hMem
0x1800110a9  call    cs:__imp_LocalFree
0x1800110af  test    rbx, rbx
0x1800110b2  jz      loc_180010FC7
0x1800110b8  mov     rcx, rbx; hMem
0x1800110bb  call    cs:__imp_LocalFree
0x1800110c1  jmp     loc_180010FC7
0x1800110c6  mov     r8, [rbp+pDacl]; pDacl
0x1800110ca  xor     r9d, r9d; bDaclDefaulted
0x1800110cd  mov     rcx, rbx; pSecurityDescriptor
0x1800110d0  lea     edx, [r9+1]; bDaclPresent
0x1800110d4  call    cs:__imp_SetSecurityDescriptorDacl
0x1800110da  test    eax, eax
0x1800110dc  jnz     short loc_1800110E8
0x1800110de  mov     edx, 359h
0x1800110e3  jmp     loc_180011064
0x1800110e8  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x1800110ec  mov     [rbp+dwBufferLength], 0
0x1800110f3  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1800110f5  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1800110f8  call    cs:__imp_MakeSelfRelativeSD
0x1800110fe  test    eax, eax
0x180011100  jz      short loc_180011125
0x180011102  mov     rcx, [rbp+38h]; this
0x180011106  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x18001110d  mov     r12d, 8000FFFFh
0x180011113  mov     edx, 364h; void *
0x180011118  mov     r9d, r12d; char *
0x18001111b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011120  jmp     loc_180011077
0x180011125  mov     edx, [rbp+dwBufferLength]; uBytes
0x180011128  xor     ecx, ecx; uFlags
0x18001112a  call    cs:__imp_LocalAlloc
0x180011130  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180011134  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180011137  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18001113a  mov     r12, rax
0x18001113d  call    cs:__imp_MakeSelfRelativeSD
0x180011143  test    eax, eax
0x180011145  jnz     short loc_1800111B8
0x180011147  mov     rcx, [rbp+38h]; this
0x18001114b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\configmanager2\\"...
0x180011152  mov     edx, 36Ch; void *
0x180011157  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001115c  mov     r13d, eax
0x18001115f  test    r12, r12
0x180011162  jz      short loc_18001116D
0x180011164  mov     rcx, r12; hMem
0x180011167  call    cs:__imp_LocalFree
0x18001116d  test    r15, r15
0x180011170  jz      short loc_18001117B
0x180011172  mov     rcx, r15; hMem
0x180011175  call    cs:__imp_LocalFree
0x18001117b  test    r14, r14
0x18001117e  jz      short loc_180011189
0x180011180  mov     rcx, r14; hMem
0x180011183  call    cs:__imp_LocalFree
0x180011189  test    rsi, rsi
0x18001118c  jz      short loc_180011197
0x18001118e  mov     rcx, rsi; hMem
0x180011191  call    cs:__imp_LocalFree
0x180011197  test    rdi, rdi
0x18001119a  jz      short loc_1800111A5
0x18001119c  mov     rcx, rdi; hMem
0x18001119f  call    cs:__imp_LocalFree
0x1800111a5  test    rbx, rbx
0x1800111a8  jz      short loc_1800111B3
0x1800111aa  mov     rcx, rbx; hMem
0x1800111ad  call    cs:__imp_LocalFree
0x1800111b3  mov     eax, r13d
0x1800111b6  jmp     short loc_180011204
0x1800111b8  mov     [r13+0], r12
0x1800111bc  test    r15, r15
0x1800111bf  jz      short loc_1800111CA
0x1800111c1  mov     rcx, r15; hMem
0x1800111c4  call    cs:__imp_LocalFree
0x1800111ca  test    r14, r14
0x1800111cd  jz      short loc_1800111D8
0x1800111cf  mov     rcx, r14; hMem
0x1800111d2  call    cs:__imp_LocalFree
0x1800111d8  test    rsi, rsi
0x1800111db  jz      short loc_1800111E6
0x1800111dd  mov     rcx, rsi; hMem
0x1800111e0  call    cs:__imp_LocalFree
0x1800111e6  test    rdi, rdi
0x1800111e9  jz      short loc_1800111F4
0x1800111eb  mov     rcx, rdi; hMem
0x1800111ee  call    cs:__imp_LocalFree
0x1800111f4  test    rbx, rbx
0x1800111f7  jz      short loc_180011202
0x1800111f9  mov     rcx, rbx; hMem
0x1800111fc  call    cs:__imp_LocalFree
0x180011202  xor     eax, eax
0x180011204  mov     rbx, [rsp+80h+arg_0]
0x18001120c  add     rsp, 80h
0x180011213  pop     r15
0x180011215  pop     r14
0x180011217  pop     r13
0x180011219  pop     r12
0x18001121b  pop     rdi
0x18001121c  pop     rsi
0x18001121d  pop     rbp
0x18001121e  retn
```
