# ApplyChangeSecurityToRegistryTree_(HKEY__ *,void *,void *,int,int)

- ea: `0x18004a270`
- end: `0x18004a8af`
- name: `?ApplyChangeSecurityToRegistryTree_@@YAJPEAUHKEY__@@PEAX1HH@Z`
- size: `1599`
- prototype: `__int64 __fastcall(HKEY, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004a270`

## callees

- `0x180005370`
- `0x180011c00`
- `0x1800250b0`
- `0x180027220`
- `0x18003fff4`
- `0x18004a270`
- `0x180054110`
- `0x18005411c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a741`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004a679`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004a679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a77d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a77d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004a2ee`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004a341`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004a2ee`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004a341`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004a706`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004a706`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18004a88b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18004a88b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004a802`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004a802`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18004a862`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18004a862`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004a833`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004a833`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004a7d7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004a7d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a413`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a428`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a520`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a413`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a428`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a520`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a3aa`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a3f8`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a4e9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a5f1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a3aa`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a3f8`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a4e9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004a5f1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004a4a9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004a4a9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a37f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a3d1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a446`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a37f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a3d1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004a446`

## pseudocode

```c
__int64 __fastcall ApplyChangeSecurityToRegistryTree_(HKEY a1, void *a2, void *a3)
{
  HKEY v3; // rsi
  struct _ACL *v6; // rdi
  int v7; // eax
  HKEY v8; // r12
  signed int v9; // ebx
  LSTATUS KeySecurity; // eax
  LSTATUS v11; // eax
  BOOL SecurityDescriptorDacl; // eax
  char *v13; // r14
  BOOL v14; // eax
  char *v15; // rbx
  unsigned __int16 v16; // r14
  BOOL v17; // eax
  WORD v18; // si
  int v19; // eax
  BOOL v20; // eax
  unsigned __int16 v21; // r13
  __int64 *v22; // rdx
  unsigned __int16 v23; // r15
  char *v24; // rbx
  WORD v25; // r14
  _QWORD *v26; // rcx
  __int64 v27; // rax
  size_t v28; // r8
  LSTATUS InfoKeyW; // eax
  DWORD v30; // edi
  WCHAR *i; // rsi
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  BOOL v35; // eax
  BOOL v36; // eax
  BOOL SecurityDescriptorControl; // eax
  BOOL v38; // eax
  LSTATUS v39; // eax
  WINBOOL bDaclPresent; // [rsp+68h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-59h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+78h] [rbp-51h] BYREF
  DWORD cchName; // [rsp+7Ch] [rbp-4Dh] BYREF
  LPVOID pAce; // [rsp+80h] [rbp-49h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+88h] [rbp-41h] BYREF
  PACL pAcl; // [rsp+90h] [rbp-39h] BYREF
  int v47; // [rsp+98h] [rbp-31h]
  DWORD LengthSid; // [rsp+9Ch] [rbp-2Dh]
  LPWSTR lpName; // [rsp+A0h] [rbp-29h] BYREF
  void *Buf1; // [rsp+A8h] [rbp-21h]
  char *v51; // [rsp+B0h] [rbp-19h]
  _OWORD v52[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v53; // [rsp+D8h] [rbp+Fh]

  v3 = a1;
  hKey = 0;
  pAcl = 0;
  cbSecurityDescriptor = 512;
  v53 = 0;
  memset(v52, 0, sizeof(v52));
  v6 = 0;
  v7 = ResultFromHeapAlloc(0x200u, (void **)&hKey);
  v8 = hKey;
  v9 = v7;
  if ( v7 >= 0 )
  {
    KeySecurity = RegGetKeySecurity(v3, 4u, hKey, &cbSecurityDescriptor);
    v9 = KeySecurity;
    if ( KeySecurity > 0 )
      v9 = (unsigned __int16)KeySecurity | 0x80070000;
    if ( v9 == -2147024774 )
    {
      hKey = 0;
      v9 = ResultFromHeapReAlloc(v8, cbSecurityDescriptor, (void **)&hKey);
      if ( v9 < 0 )
        goto LABEL_34;
      v8 = hKey;
      v11 = RegGetKeySecurity(v3, 4u, hKey, &cbSecurityDescriptor);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
    }
    if ( v9 >= 0 )
    {
      hKey = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      SecurityDescriptorDacl = GetSecurityDescriptorDacl(a2, &bDaclPresent, (PACL *)&hKey, &bDaclDefaulted);
      v9 = ResultFromWin32Bool(SecurityDescriptorDacl);
      if ( v9 >= 0 )
      {
        pAce = 0;
        GetAce((PACL)hKey, 0, &pAce);
        v13 = (char *)pAce + 8;
        Buf1 = (char *)pAce + 8;
        v14 = GetSecurityDescriptorDacl(a3, &bDaclPresent, (PACL *)&hKey, &bDaclDefaulted);
        v9 = ResultFromWin32Bool(v14);
        if ( v9 >= 0 )
        {
          GetAce((PACL)hKey, 0, &pAce);
          v15 = (char *)pAce + 8;
          v51 = (char *)pAce + 8;
          cchName = GetLengthSid(v13);
          v16 = cchName;
          LengthSid = GetLengthSid(v15);
          v17 = GetSecurityDescriptorDacl(v8, &bDaclPresent, (PACL *)&hKey, &bDaclDefaulted);
          v9 = ResultFromWin32Bool(v17);
          if ( v9 >= 0 )
          {
            if ( bDaclPresent && hKey )
            {
              v18 = *((_WORD *)hKey + 1) + 256;
              v19 = ResultFromHeapAlloc(v18, (void **)&pAcl);
              v6 = pAcl;
              v9 = v19;
              if ( v19 < 0 )
                goto LABEL_34;
              v20 = InitializeAcl(pAcl, v18, 2u);
              v9 = ResultFromWin32Bool(v20);
              if ( v9 < 0 )
                goto LABEL_34;
              LODWORD(pAcl) = 0;
              v21 = 8;
              v6->AceCount = *((_WORD *)hKey + 2);
              if ( GetAce((PACL)hKey, 0, &pAce) )
              {
                while ( 1 )
                {
                  v22 = (__int64 *)pAce;
                  v47 = 0;
                  v23 = *((_WORD *)pAce + 1);
                  if ( !*(_BYTE *)pAce || *(_BYTE *)pAce == 1 )
                  {
                    v24 = (char *)pAce + 8;
                    if ( v16 == GetLengthSid((char *)pAce + 8) && !memcmp_0(Buf1, v24, v16) )
                    {
                      v22 = (__int64 *)pAce;
                      v47 = 1;
                      v23 = LengthSid + *((_WORD *)pAce + 1) - v16;
                    }
                    else
                    {
                      v22 = (__int64 *)pAce;
                    }
                  }
                  v25 = v23 + v21;
                  if ( (unsigned __int16)(v23 + v21) < v21 )
                    break;
                  v9 = 0;
                  if ( v25 > v18 )
                  {
                    if ( 2 * (unsigned int)v25 > 0xFFFF )
                      break;
                    v18 = 2 * v25;
                    lpName = 0;
                    v9 = ResultFromHeapReAlloc(v6, (unsigned __int16)(2 * v25), (void **)&lpName);
                    if ( v9 < 0 )
                      goto LABEL_34;
                    v6 = (struct _ACL *)lpName;
                    v22 = (__int64 *)pAce;
                  }
                  v26 = (_QWORD *)((char *)v6 + v21);
                  if ( v47 )
                  {
                    v27 = *v22;
                    v28 = (unsigned __int16)LengthSid;
                    v22 = (__int64 *)v51;
                    *v26++ = v27;
                  }
                  else
                  {
                    v28 = v23;
                  }
                  memcpy_0(v26, v22, v28);
                  LODWORD(pAcl) = (_DWORD)pAcl + 1;
                  if ( !GetAce((PACL)hKey, (DWORD)pAcl, &pAce) )
                    goto LABEL_51;
                  v21 += v23;
                  v16 = cchName;
                }
                v9 = -2147024362;
                goto LABEL_34;
              }
LABEL_51:
              v6->AclSize = v18;
              v3 = a1;
            }
            if ( v6 )
            {
              v35 = InitializeSecurityDescriptor(v52, 1u);
              v9 = ResultFromWin32Bool(v35);
              if ( v9 >= 0 )
              {
                v36 = SetSecurityDescriptorDacl(v52, 1, v6, 0);
                v9 = ResultFromWin32Bool(v36);
                if ( v9 >= 0 )
                {
                  LOWORD(bDaclPresent) = 0;
                  cchName = 0;
                  SecurityDescriptorControl = GetSecurityDescriptorControl(
                                                v8,
                                                (PSECURITY_DESCRIPTOR_CONTROL)&bDaclPresent,
                                                &cchName);
                  v9 = ResultFromWin32Bool(SecurityDescriptorControl);
                  if ( v9 >= 0 )
                  {
                    v38 = SetSecurityDescriptorControl(v52, 0x1500u, bDaclPresent & 0x1500);
                    v9 = ResultFromWin32Bool(v38);
                    if ( v9 >= 0 )
                    {
                      v39 = RegSetKeySecurity(v3, 4u, v52);
                      v9 = v39;
                      if ( v39 > 0 )
                        v9 = (unsigned __int16)v39 | 0x80070000;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_34:
  ResultFromHeapFree(v8);
  ResultFromHeapFree(v6);
  if ( v9 >= 0 )
  {
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    InfoKeyW = RegQueryInfoKeyW(a1, 0, 0, 0, (LPDWORD)&bDaclDefaulted, (LPDWORD)&bDaclPresent, 0, 0, 0, 0, 0, 0);
    v9 = InfoKeyW;
    if ( InfoKeyW > 0 )
      v9 = (unsigned __int16)InfoKeyW | 0x80070000;
    if ( v9 >= 0 )
    {
      if ( bDaclDefaulted )
      {
        lpName = 0;
        v9 = ResultFromHeapAllocArray<unsigned short>((unsigned int)++bDaclPresent, &lpName);
        if ( v9 >= 0 )
        {
          v30 = 0;
          for ( i = lpName; v30 < bDaclDefaulted; ++v30 )
          {
            cchName = bDaclPresent;
            v32 = RegEnumKeyExW(a1, v30, i, &cchName, 0, 0, 0, 0);
            v9 = v32;
            if ( v32 > 0 )
              v9 = (unsigned __int16)v32 | 0x80070000;
            if ( v9 >= 0 )
            {
              hKey = 0;
              v33 = RegOpenKeyExW(a1, i, 0, 0x60019u, &hKey);
              v9 = v33;
              if ( v33 > 0 )
                v9 = (unsigned __int16)v33 | 0x80070000;
              if ( v9 >= 0 )
              {
                v9 = ApplyChangeSecurityToRegistryTree_(hKey, a2, a3, 0, 0);
                RegCloseKey(hKey);
              }
            }
          }
          ResultFromHeapFree(i);
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a270  mov     rax, rsp
0x18004a273  mov     [rax+20h], rbx
0x18004a277  mov     [rax+18h], r8
0x18004a27b  mov     [rax+10h], rdx
0x18004a27f  mov     [rax+8], rcx
0x18004a283  push    rbp
0x18004a284  push    rsi
0x18004a285  push    rdi
0x18004a286  push    r12
0x18004a288  push    r13
0x18004a28a  push    r14
0x18004a28c  push    r15
0x18004a28e  lea     rbp, [rax-57h]
0x18004a292  sub     rsp, 0E0h
0x18004a299  xor     r13d, r13d
0x18004a29c  xorps   xmm0, xmm0
0x18004a29f  mov     rsi, rcx
0x18004a2a2  mov     [rbp+4Fh+hKey], r13
0x18004a2a6  mov     ecx, 200h; dwBytes
0x18004a2ab  mov     [rbp+4Fh+pAcl], r13
0x18004a2af  mov     r14, rdx
0x18004a2b2  mov     [rbp+4Fh+cbSecurityDescriptor], ecx
0x18004a2b5  xor     eax, eax
0x18004a2b7  lea     rdx, [rbp+4Fh+hKey]; void **
0x18004a2bb  mov     r15, r8
0x18004a2be  mov     [rbp+4Fh+var_40], rax
0x18004a2c2  movups  [rbp+4Fh+var_60], xmm0
0x18004a2c6  mov     edi, r13d
0x18004a2c9  movups  [rbp+4Fh+var_50], xmm0
0x18004a2cd  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18004a2d2  mov     r12, [rbp+4Fh+hKey]
0x18004a2d6  mov     ebx, eax
0x18004a2d8  test    eax, eax
0x18004a2da  js      loc_18004A61A
0x18004a2e0  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18004a2e4  mov     r8, r12; pSecurityDescriptor
0x18004a2e7  lea     edx, [r13+4]; SecurityInformation
0x18004a2eb  mov     rcx, rsi; hKey
0x18004a2ee  call    cs:__imp_RegGetKeySecurity
0x18004a2f5  nop     dword ptr [rax+rax+00h]
0x18004a2fa  mov     ebx, eax
0x18004a2fc  test    eax, eax
0x18004a2fe  jle     short loc_18004A309
0x18004a300  movzx   ebx, ax
0x18004a303  or      ebx, 80070000h
0x18004a309  cmp     ebx, 8007007Ah
0x18004a30f  jnz     short loc_18004A35C
0x18004a311  mov     edx, [rbp+4Fh+cbSecurityDescriptor]; dwBytes
0x18004a314  lea     r8, [rbp+4Fh+hKey]; void **
0x18004a318  mov     rcx, r12; lpMem
0x18004a31b  mov     [rbp+4Fh+hKey], r13
0x18004a31f  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18004a324  mov     ebx, eax
0x18004a326  test    eax, eax
0x18004a328  js      loc_18004A61A
0x18004a32e  mov     r12, [rbp+4Fh+hKey]
0x18004a332  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18004a336  mov     r8, r12; pSecurityDescriptor
0x18004a339  mov     edx, 4; SecurityInformation
0x18004a33e  mov     rcx, rsi; hKey
0x18004a341  call    cs:__imp_RegGetKeySecurity
0x18004a348  nop     dword ptr [rax+rax+00h]
0x18004a34d  mov     ebx, eax
0x18004a34f  test    eax, eax
0x18004a351  jle     short loc_18004A35C
0x18004a353  movzx   ebx, ax
0x18004a356  or      ebx, 80070000h
0x18004a35c  test    ebx, ebx
0x18004a35e  js      loc_18004A61A
0x18004a364  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x18004a368  mov     [rbp+4Fh+hKey], r13
0x18004a36c  lea     r8, [rbp+4Fh+hKey]; pDacl
0x18004a370  mov     [rbp+4Fh+bDaclPresent], r13d
0x18004a374  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x18004a378  mov     [rbp+4Fh+bDaclDefaulted], r13d
0x18004a37c  mov     rcx, r14; pSecurityDescriptor
0x18004a37f  call    cs:__imp_GetSecurityDescriptorDacl
0x18004a386  nop     dword ptr [rax+rax+00h]
0x18004a38b  mov     ecx, eax; int
0x18004a38d  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004a392  mov     ebx, eax
0x18004a394  test    eax, eax
0x18004a396  js      loc_18004A61A
0x18004a39c  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004a3a0  lea     r8, [rbp+4Fh+pAce]; pAce
0x18004a3a4  xor     edx, edx; dwAceIndex
0x18004a3a6  mov     [rbp+4Fh+pAce], r13
0x18004a3aa  call    cs:__imp_GetAce
0x18004a3b1  nop     dword ptr [rax+rax+00h]
0x18004a3b6  mov     r14, [rbp+4Fh+pAce]
0x18004a3ba  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x18004a3be  add     r14, 8
0x18004a3c2  lea     r8, [rbp+4Fh+hKey]; pDacl
0x18004a3c6  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x18004a3ca  mov     [rbp+4Fh+Buf1], r14
0x18004a3ce  mov     rcx, r15; pSecurityDescriptor
0x18004a3d1  call    cs:__imp_GetSecurityDescriptorDacl
0x18004a3d8  nop     dword ptr [rax+rax+00h]
0x18004a3dd  mov     ecx, eax; int
0x18004a3df  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004a3e4  mov     ebx, eax
0x18004a3e6  test    eax, eax
0x18004a3e8  js      loc_18004A61A
0x18004a3ee  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004a3f2  lea     r8, [rbp+4Fh+pAce]; pAce
0x18004a3f6  xor     edx, edx; dwAceIndex
0x18004a3f8  call    cs:__imp_GetAce
0x18004a3ff  nop     dword ptr [rax+rax+00h]
0x18004a404  mov     rbx, [rbp+4Fh+pAce]
0x18004a408  mov     rcx, r14; pSid
0x18004a40b  add     rbx, 8
0x18004a40f  mov     [rbp+4Fh+var_68], rbx
0x18004a413  call    cs:__imp_GetLengthSid
0x18004a41a  nop     dword ptr [rax+rax+00h]
0x18004a41f  mov     rcx, rbx; pSid
0x18004a422  mov     [rbp+4Fh+cchName], eax
0x18004a425  mov     r14d, eax
0x18004a428  call    cs:__imp_GetLengthSid
0x18004a42f  nop     dword ptr [rax+rax+00h]
0x18004a434  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x18004a438  mov     rcx, r12; pSecurityDescriptor
0x18004a43b  lea     r8, [rbp+4Fh+hKey]; pDacl
0x18004a43f  mov     [rbp+4Fh+var_7C], eax
0x18004a442  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x18004a446  call    cs:__imp_GetSecurityDescriptorDacl
0x18004a44d  nop     dword ptr [rax+rax+00h]
0x18004a452  mov     ecx, eax; int
0x18004a454  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004a459  mov     ebx, eax
0x18004a45b  test    eax, eax
0x18004a45d  js      loc_18004A61A
0x18004a463  cmp     [rbp+4Fh+bDaclPresent], r13d
0x18004a467  jz      loc_18004A7C5
0x18004a46d  mov     rax, [rbp+4Fh+hKey]
0x18004a471  test    rax, rax
0x18004a474  jz      loc_18004A7C5
0x18004a47a  mov     esi, 100h
0x18004a47f  lea     rdx, [rbp+4Fh+pAcl]; void **
0x18004a483  add     si, [rax+2]
0x18004a487  movzx   ecx, si; dwBytes
0x18004a48a  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18004a48f  mov     rdi, [rbp+4Fh+pAcl]
0x18004a493  mov     ebx, eax
0x18004a495  test    eax, eax
0x18004a497  js      loc_18004A61A
0x18004a49d  movzx   edx, si; nAclLength
0x18004a4a0  mov     r8d, 2; dwAclRevision
0x18004a4a6  mov     rcx, rdi; pAcl
0x18004a4a9  call    cs:__imp_InitializeAcl
0x18004a4b0  nop     dword ptr [rax+rax+00h]
0x18004a4b5  mov     ecx, eax; int
0x18004a4b7  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004a4bc  mov     ebx, eax
0x18004a4be  test    eax, eax
0x18004a4c0  js      loc_18004A61A
0x18004a4c6  mov     rax, [rbp+4Fh+hKey]
0x18004a4ca  lea     r8, [rbp+4Fh+pAce]; pAce
0x18004a4ce  xor     edx, edx; dwAceIndex
0x18004a4d0  mov     dword ptr [rbp+4Fh+pAcl], 0
0x18004a4d7  mov     r13d, 8
0x18004a4dd  movzx   ecx, word ptr [rax+4]
0x18004a4e1  mov     [rdi+4], cx
0x18004a4e5  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004a4e9  call    cs:__imp_GetAce
0x18004a4f0  nop     dword ptr [rax+rax+00h]
0x18004a4f5  test    eax, eax
0x18004a4f7  jz      loc_18004A7BA
0x18004a4fd  mov     rdx, [rbp+4Fh+pAce]
0x18004a501  mov     [rbp+4Fh+var_80], 0
0x18004a508  movzx   ecx, byte ptr [rdx]
0x18004a50b  movzx   r15d, word ptr [rdx+2]
0x18004a510  test    ecx, ecx
0x18004a512  jz      short loc_18004A519
0x18004a514  cmp     ecx, 1
0x18004a517  jnz     short loc_18004A567
0x18004a519  lea     rbx, [rdx+8]
0x18004a51d  mov     rcx, rbx; pSid
0x18004a520  call    cs:__imp_GetLengthSid
0x18004a527  nop     dword ptr [rax+rax+00h]
0x18004a52c  movzx   ecx, r14w
0x18004a530  cmp     ecx, eax
0x18004a532  jnz     short loc_18004A563
0x18004a534  mov     rcx, [rbp+4Fh+Buf1]; Buf1
0x18004a538  mov     rdx, rbx; Buf2
0x18004a53b  movzx   r8d, r14w; Size
0x18004a53f  call    memcmp_0
0x18004a544  test    eax, eax
0x18004a546  jnz     short loc_18004A563
0x18004a548  mov     rdx, [rbp+4Fh+pAce]
0x18004a54c  mov     [rbp+4Fh+var_80], 1
0x18004a553  movzx   r15d, word ptr [rdx+2]
0x18004a558  sub     r15w, r14w
0x18004a55c  add     r15w, word ptr [rbp+4Fh+var_7C]
0x18004a561  jmp     short loc_18004A567
0x18004a563  mov     rdx, [rbp+4Fh+pAce]
0x18004a567  lea     r14d, [r15+r13]
0x18004a56b  cmp     r14w, r13w
0x18004a56f  jb      loc_18004A612
0x18004a575  xor     ebx, ebx
0x18004a577  cmp     r14w, si
0x18004a57b  jbe     short loc_18004A5B1
0x18004a57d  movzx   eax, r14w
0x18004a581  add     eax, eax
0x18004a583  cmp     eax, 0FFFFh
0x18004a588  ja      loc_18004A612
0x18004a58e  movzx   esi, ax
0x18004a591  lea     r8, [rbp+4Fh+lpName]; void **
0x18004a595  mov     edx, esi; dwBytes
0x18004a597  mov     [rbp+4Fh+lpName], rbx
0x18004a59b  mov     rcx, rdi; lpMem
0x18004a59e  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18004a5a3  mov     ebx, eax
0x18004a5a5  test    eax, eax
0x18004a5a7  js      short loc_18004A617
0x18004a5a9  mov     rdi, [rbp+4Fh+lpName]
0x18004a5ad  mov     rdx, [rbp+4Fh+pAce]; Src
0x18004a5b1  movzx   ecx, r13w
0x18004a5b5  xor     r13d, r13d
0x18004a5b8  add     rcx, rdi; void *
0x18004a5bb  cmp     [rbp+4Fh+var_80], r13d
0x18004a5bf  jz      short loc_18004A5D6
0x18004a5c1  mov     rax, [rdx]
0x18004a5c4  movzx   r8d, word ptr [rbp+4Fh+var_7C]
0x18004a5c9  mov     rdx, [rbp+4Fh+var_68]
0x18004a5cd  mov     [rcx], rax
0x18004a5d0  add     rcx, 8
0x18004a5d4  jmp     short loc_18004A5DA
0x18004a5d6  movzx   r8d, r15w; Size
0x18004a5da  call    memcpy_0
0x18004a5df  mov     eax, dword ptr [rbp+4Fh+pAcl]
0x18004a5e2  lea     r8, [rbp+4Fh+pAce]; pAce
0x18004a5e6  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004a5ea  inc     eax
0x18004a5ec  mov     edx, eax; dwAceIndex
0x18004a5ee  mov     dword ptr [rbp+4Fh+pAcl], eax
0x18004a5f1  call    cs:__imp_GetAce
0x18004a5f8  nop     dword ptr [rax+rax+00h]
0x18004a5fd  test    eax, eax
0x18004a5ff  jz      loc_18004A7BD
0x18004a605  movzx   r13d, r14w
0x18004a609  mov     r14d, [rbp+4Fh+cchName]
0x18004a60d  jmp     loc_18004A4FD
0x18004a612  mov     ebx, 80070216h
0x18004a617  xor     r13d, r13d
0x18004a61a  mov     rcx, r12; lpMem
0x18004a61d  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18004a622  mov     rcx, rdi; lpMem
0x18004a625  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18004a62a  test    ebx, ebx
0x18004a62c  js      loc_18004A79C
0x18004a632  mov     r14, [rbp+4Fh+arg_0]
0x18004a636  lea     rax, [rbp+4Fh+bDaclPresent]
0x18004a63a  mov     [rsp+58h], r13; lpftLastWriteTime
0x18004a63f  xor     r9d, r9d; lpReserved
0x18004a642  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004a647  xor     r8d, r8d; lpcchClass
0x18004a64a  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004a64f  xor     edx, edx; lpClass
0x18004a651  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18004a656  mov     rcx, r14; hKey
0x18004a659  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18004a65e  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004a663  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18004a668  lea     rax, [rbp+4Fh+bDaclDefaulted]
0x18004a66c  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x18004a671  mov     [rbp+4Fh+bDaclDefaulted], r13d
0x18004a675  mov     [rbp+4Fh+bDaclPresent], r13d
0x18004a679  call    cs:__imp_RegQueryInfoKeyW
0x18004a680  nop     dword ptr [rax+rax+00h]
0x18004a685  mov     ebx, eax
0x18004a687  test    eax, eax
0x18004a689  jle     short loc_18004A694
0x18004a68b  movzx   ebx, ax
0x18004a68e  or      ebx, 80070000h
0x18004a694  test    ebx, ebx
0x18004a696  js      loc_18004A79C
0x18004a69c  cmp     [rbp+4Fh+bDaclDefaulted], r13d
0x18004a6a0  jbe     loc_18004A79C
0x18004a6a6  mov     eax, [rbp+4Fh+bDaclPresent]
0x18004a6a9  lea     rdx, [rbp+4Fh+lpName]
0x18004a6ad  inc     eax
0x18004a6af  mov     [rbp+4Fh+lpName], r13
0x18004a6b3  mov     ecx, eax
0x18004a6b5  mov     [rbp+4Fh+bDaclPresent], eax
0x18004a6b8  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18004a6bd  mov     ebx, eax
0x18004a6bf  test    eax, eax
0x18004a6c1  js      loc_18004A79C
0x18004a6c7  mov     edi, r13d
0x18004a6ca  mov     rsi, [rbp+4Fh+lpName]
0x18004a6ce  cmp     [rbp+4Fh+bDaclDefaulted], r13d
0x18004a6d2  jbe     loc_18004A794
0x18004a6d8  mov     r15, [rbp+4Fh+pSecurityDescriptor]
0x18004a6dc  mov     r12, [rbp+4Fh+arg_10]
0x18004a6e0  mov     eax, [rbp+4Fh+bDaclPresent]
0x18004a6e3  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x18004a6e7  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x18004a6ec  mov     r8, rsi; lpName
0x18004a6ef  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18004a6f4  mov     edx, edi; dwIndex
  ... truncated ...
```
