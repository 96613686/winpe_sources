# SetHandleAccessWithInheritance

- ea: `0x180065938`
- end: `0x180065a52`
- name: `SetHandleAccessWithInheritance`
- size: `282`
- prototype: `__int64 __fastcall(HANDLE handle, SE_OBJECT_TYPE ObjectType, void *, unsigned int, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180065880`
- `0x180065bd0`
- `0x180065c80`

## callees

- `0x180030b64`
- `0x1800321a0`
- `0x180065938`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180065a3b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18006598f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18006598f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180065a21`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180065a21`

## pseudocode

```c
__int64 __fastcall SetHandleAccessWithInheritance(
        HANDLE handle,
        SE_OBJECT_TYPE ObjectType,
        void *a3,
        DWORD a4,
        bool a5)
{
  unsigned int SecurityInfo; // edi
  PACL v10; // rbx
  struct _ACL *pDacl; // rax
  PACL v12; // rsi
  PACL pAcl; // [rsp+40h] [rbp-20h] BYREF
  PACL v15; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF

  hMem = 0;
  pAcl = 0;
  SecurityInfo = GetSecurityInfo(handle, ObjectType, 4u, 0, 0, &pAcl, 0, &hMem);
  if ( !SecurityInfo )
  {
    v10 = 0;
    a5 = 0;
    v15 = 0;
    if ( AclHasSIDCheckAndSetAccess(pAcl, a3, a4, 3u, 0, &a5) )
    {
      pDacl = pAcl;
      v12 = 0;
    }
    else
    {
      SecurityInfo = CreateSIDAcl(pAcl, &v15, a3, a4, 3u);
      if ( SecurityInfo )
      {
LABEL_8:
        LocalFree(hMem);
        return SecurityInfo;
      }
      v10 = v15;
      pDacl = v15;
      v12 = v15;
    }
    SecurityInfo = SetSecurityInfo(handle, ObjectType, 4u, 0, 0, pDacl, 0);
    if ( v12 )
      LocalFree(v10);
    goto LABEL_8;
  }
  return SecurityInfo;
}

```

## disassembly

```asm
0x180065938  mov     r11, rsp
0x18006593b  push    rbp
0x18006593c  push    rbx
0x18006593d  push    rsi
0x18006593e  push    rdi
0x18006593f  push    r12
0x180065941  push    r14
0x180065943  push    r15
0x180065945  mov     rbp, rsp
0x180065948  sub     rsp, 60h
0x18006594c  mov     esi, r9d
0x18006594f  mov     [rbp+hMem], 0
0x180065957  xor     r9d, r9d; ppsidOwner
0x18006595a  mov     [rbp+pAcl], 0
0x180065962  lea     rax, [rbp+hMem]
0x180065966  mov     r14, r8
0x180065969  mov     [r11-60h], rax
0x18006596d  mov     r15d, edx
0x180065970  mov     qword ptr [r11-68h], 0
0x180065978  lea     rax, [rbp+pAcl]
0x18006597c  mov     [r11-70h], rax
0x180065980  lea     r8d, [r9+4]; SecurityInfo
0x180065984  mov     r12, rcx
0x180065987  mov     qword ptr [r11-78h], 0
0x18006598f  call    cs:__imp_GetSecurityInfo
0x180065995  mov     edi, eax
0x180065997  test    eax, eax
0x180065999  jnz     loc_180065A41
0x18006599f  mov     rcx, [rbp+pAcl]; pAcl
0x1800659a3  xor     ebx, ebx
0x1800659a5  mov     [rbp+arg_20], al
0x1800659a8  mov     r8d, esi; unsigned int
0x1800659ab  lea     rax, [rbp+arg_20]
0x1800659af  mov     [rbp+var_18], rbx
0x1800659b3  mov     [rsp+60h+pDacl], rax; bool *
0x1800659b8  mov     rdx, r14; pSid2
0x1800659bb  lea     edi, [rbx+3]
0x1800659be  mov     dword ptr [rsp+60h+psidGroup], ebx; unsigned int
0x1800659c2  mov     r9d, edi; unsigned int
0x1800659c5  call    ?AclHasSIDCheckAndSetAccess@@YA_NPEAU_ACL@@PEAXKKKPEA_N@Z; AclHasSIDCheckAndSetAccess(_ACL *,void *,ulong,ulong,ulong,bool *)
0x1800659ca  test    al, al
0x1800659cc  jnz     short loc_1800659F7
0x1800659ce  mov     rcx, [rbp+pAcl]; pAcl
0x1800659d2  lea     rdx, [rbp+var_18]; struct _ACL **
0x1800659d6  mov     r9d, esi; unsigned int
0x1800659d9  mov     dword ptr [rsp+60h+psidGroup], edi; unsigned int
0x1800659dd  mov     r8, r14; void *
0x1800659e0  call    ?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z; CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)
0x1800659e5  mov     edi, eax
0x1800659e7  test    eax, eax
0x1800659e9  jnz     short loc_180065A37
0x1800659eb  mov     rbx, [rbp+var_18]
0x1800659ef  mov     rax, rbx
0x1800659f2  mov     rsi, rbx
0x1800659f5  jmp     short loc_1800659FD
0x1800659f7  mov     rax, [rbp+pAcl]
0x1800659fb  xor     esi, esi
0x1800659fd  xor     r9d, r9d; psidOwner
0x180065a00  mov     [rsp+60h+pSacl], 0; pSacl
0x180065a09  mov     [rsp+60h+pDacl], rax; pDacl
0x180065a0e  mov     edx, r15d; ObjectType
0x180065a11  mov     rcx, r12; handle
0x180065a14  mov     [rsp+60h+psidGroup], 0; psidGroup
0x180065a1d  lea     r8d, [r9+4]; SecurityInfo
0x180065a21  call    cs:__imp_SetSecurityInfo
0x180065a27  mov     edi, eax
0x180065a29  test    rsi, rsi
0x180065a2c  jz      short loc_180065A37
0x180065a2e  mov     rcx, rbx; hMem
0x180065a31  call    cs:__imp_LocalFree
0x180065a37  mov     rcx, [rbp+hMem]; hMem
0x180065a3b  call    cs:__imp_LocalFree
0x180065a41  mov     eax, edi
0x180065a43  add     rsp, 60h
0x180065a47  pop     r15
0x180065a49  pop     r14
0x180065a4b  pop     r12
0x180065a4d  pop     rdi
0x180065a4e  pop     rsi
0x180065a4f  pop     rbx
0x180065a50  pop     rbp
0x180065a51  retn
```
