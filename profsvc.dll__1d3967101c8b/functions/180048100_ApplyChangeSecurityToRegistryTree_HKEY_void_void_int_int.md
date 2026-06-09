# ApplyChangeSecurityToRegistryTree_(HKEY__ *,void *,void *,int,int)

- ea: `0x180048100`
- end: `0x1800486b6`
- name: `?ApplyChangeSecurityToRegistryTree_@@YAJPEAUHKEY__@@PEAX1HH@Z`
- size: `1462`
- prototype: `__int64 __fastcall(HKEY, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180048100`

## callees

- `0x180004170`
- `0x180006580`
- `0x1800220f0`
- `0x180024898`
- `0x18003e8fc`
- `0x180048100`
- `0x1800510e0`
- `0x1800510ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048573`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048573`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800484b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800484b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800485a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800485a9`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004817e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800481cb`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004817e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800481cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004853e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004853e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180048698`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180048698`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180048621`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180048621`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180048675`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180048675`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004864c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004864c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800485fc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800485fc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004827f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004828e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004836e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004827f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004828e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004836e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180048228`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004826a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004833d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180048435`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180048228`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004826a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004833d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180048435`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180048303`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180048303`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180048203`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180048249`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800482a6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180048203`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180048249`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800482a6`

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
0x180048100  mov     rax, rsp
0x180048103  mov     [rax+20h], rbx
0x180048107  mov     [rax+18h], r8
0x18004810b  mov     [rax+10h], rdx
0x18004810f  mov     [rax+8], rcx
0x180048113  push    rbp
0x180048114  push    rsi
0x180048115  push    rdi
0x180048116  push    r12
0x180048118  push    r13
0x18004811a  push    r14
0x18004811c  push    r15
0x18004811e  lea     rbp, [rax-57h]
0x180048122  sub     rsp, 0E0h
0x180048129  xor     r13d, r13d
0x18004812c  xorps   xmm0, xmm0
0x18004812f  mov     rsi, rcx
0x180048132  mov     [rbp+4Fh+hKey], r13
0x180048136  mov     ecx, 200h; dwBytes
0x18004813b  mov     [rbp+4Fh+pAcl], r13
0x18004813f  mov     r14, rdx
0x180048142  mov     [rbp+4Fh+cbSecurityDescriptor], ecx
0x180048145  xor     eax, eax
0x180048147  lea     rdx, [rbp+4Fh+hKey]; void **
0x18004814b  mov     r15, r8
0x18004814e  mov     [rbp+4Fh+var_40], rax
0x180048152  movups  [rbp+4Fh+var_60], xmm0
0x180048156  mov     edi, r13d
0x180048159  movups  [rbp+4Fh+var_50], xmm0
0x18004815d  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180048162  mov     r12, [rbp+4Fh+hKey]
0x180048166  mov     ebx, eax
0x180048168  test    eax, eax
0x18004816a  js      loc_180048458
0x180048170  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180048174  mov     r8, r12; pSecurityDescriptor
0x180048177  lea     edx, [r13+4]; SecurityInformation
0x18004817b  mov     rcx, rsi; hKey
0x18004817e  call    cs:__imp_RegGetKeySecurity
0x180048184  mov     ebx, eax
0x180048186  test    eax, eax
0x180048188  jle     short loc_180048193
0x18004818a  movzx   ebx, ax
0x18004818d  or      ebx, 80070000h
0x180048193  cmp     ebx, 8007007Ah
0x180048199  jnz     short loc_1800481E0
0x18004819b  mov     edx, [rbp+4Fh+cbSecurityDescriptor]; dwBytes
0x18004819e  lea     r8, [rbp+4Fh+hKey]; void **
0x1800481a2  mov     rcx, r12; lpMem
0x1800481a5  mov     [rbp+4Fh+hKey], r13
0x1800481a9  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800481ae  mov     ebx, eax
0x1800481b0  test    eax, eax
0x1800481b2  js      loc_180048458
0x1800481b8  mov     r12, [rbp+4Fh+hKey]
0x1800481bc  lea     r9, [rbp+4Fh+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800481c0  mov     r8, r12; pSecurityDescriptor
0x1800481c3  mov     edx, 4; SecurityInformation
0x1800481c8  mov     rcx, rsi; hKey
0x1800481cb  call    cs:__imp_RegGetKeySecurity
0x1800481d1  mov     ebx, eax
0x1800481d3  test    eax, eax
0x1800481d5  jle     short loc_1800481E0
0x1800481d7  movzx   ebx, ax
0x1800481da  or      ebx, 80070000h
0x1800481e0  test    ebx, ebx
0x1800481e2  js      loc_180048458
0x1800481e8  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x1800481ec  mov     [rbp+4Fh+hKey], r13
0x1800481f0  lea     r8, [rbp+4Fh+hKey]; pDacl
0x1800481f4  mov     [rbp+4Fh+bDaclPresent], r13d
0x1800481f8  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x1800481fc  mov     [rbp+4Fh+bDaclDefaulted], r13d
0x180048200  mov     rcx, r14; pSecurityDescriptor
0x180048203  call    cs:__imp_GetSecurityDescriptorDacl
0x180048209  mov     ecx, eax; int
0x18004820b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180048210  mov     ebx, eax
0x180048212  test    eax, eax
0x180048214  js      loc_180048458
0x18004821a  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004821e  lea     r8, [rbp+4Fh+pAce]; pAce
0x180048222  xor     edx, edx; dwAceIndex
0x180048224  mov     [rbp+4Fh+pAce], r13
0x180048228  call    cs:__imp_GetAce
0x18004822e  mov     r14, [rbp+4Fh+pAce]
0x180048232  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x180048236  add     r14, 8
0x18004823a  lea     r8, [rbp+4Fh+hKey]; pDacl
0x18004823e  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x180048242  mov     [rbp+4Fh+Buf1], r14
0x180048246  mov     rcx, r15; pSecurityDescriptor
0x180048249  call    cs:__imp_GetSecurityDescriptorDacl
0x18004824f  mov     ecx, eax; int
0x180048251  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180048256  mov     ebx, eax
0x180048258  test    eax, eax
0x18004825a  js      loc_180048458
0x180048260  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x180048264  lea     r8, [rbp+4Fh+pAce]; pAce
0x180048268  xor     edx, edx; dwAceIndex
0x18004826a  call    cs:__imp_GetAce
0x180048270  mov     rbx, [rbp+4Fh+pAce]
0x180048274  mov     rcx, r14; pSid
0x180048277  add     rbx, 8
0x18004827b  mov     [rbp+4Fh+var_68], rbx
0x18004827f  call    cs:__imp_GetLengthSid
0x180048285  mov     rcx, rbx; pSid
0x180048288  mov     [rbp+4Fh+cchName], eax
0x18004828b  mov     r14d, eax
0x18004828e  call    cs:__imp_GetLengthSid
0x180048294  lea     r9, [rbp+4Fh+bDaclDefaulted]; lpbDaclDefaulted
0x180048298  mov     rcx, r12; pSecurityDescriptor
0x18004829b  lea     r8, [rbp+4Fh+hKey]; pDacl
0x18004829f  mov     [rbp+4Fh+var_7C], eax
0x1800482a2  lea     rdx, [rbp+4Fh+bDaclPresent]; lpbDaclPresent
0x1800482a6  call    cs:__imp_GetSecurityDescriptorDacl
0x1800482ac  mov     ecx, eax; int
0x1800482ae  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800482b3  mov     ebx, eax
0x1800482b5  test    eax, eax
0x1800482b7  js      loc_180048458
0x1800482bd  cmp     [rbp+4Fh+bDaclPresent], r13d
0x1800482c1  jz      loc_1800485EA
0x1800482c7  mov     rax, [rbp+4Fh+hKey]
0x1800482cb  test    rax, rax
0x1800482ce  jz      loc_1800485EA
0x1800482d4  mov     esi, 100h
0x1800482d9  lea     rdx, [rbp+4Fh+pAcl]; void **
0x1800482dd  add     si, [rax+2]
0x1800482e1  movzx   ecx, si; dwBytes
0x1800482e4  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800482e9  mov     rdi, [rbp+4Fh+pAcl]
0x1800482ed  mov     ebx, eax
0x1800482ef  test    eax, eax
0x1800482f1  js      loc_180048458
0x1800482f7  movzx   edx, si; nAclLength
0x1800482fa  mov     r8d, 2; dwAclRevision
0x180048300  mov     rcx, rdi; pAcl
0x180048303  call    cs:__imp_InitializeAcl
0x180048309  mov     ecx, eax; int
0x18004830b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180048310  mov     ebx, eax
0x180048312  test    eax, eax
0x180048314  js      loc_180048458
0x18004831a  mov     rax, [rbp+4Fh+hKey]
0x18004831e  lea     r8, [rbp+4Fh+pAce]; pAce
0x180048322  xor     edx, edx; dwAceIndex
0x180048324  mov     dword ptr [rbp+4Fh+pAcl], 0
0x18004832b  mov     r13d, 8
0x180048331  movzx   ecx, word ptr [rax+4]
0x180048335  mov     [rdi+4], cx
0x180048339  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004833d  call    cs:__imp_GetAce
0x180048343  test    eax, eax
0x180048345  jz      loc_1800485DF
0x18004834b  mov     rdx, [rbp+4Fh+pAce]
0x18004834f  mov     [rbp+4Fh+var_80], 0
0x180048356  movzx   ecx, byte ptr [rdx]
0x180048359  movzx   r15d, word ptr [rdx+2]
0x18004835e  test    ecx, ecx
0x180048360  jz      short loc_180048367
0x180048362  cmp     ecx, 1
0x180048365  jnz     short loc_1800483AF
0x180048367  lea     rbx, [rdx+8]
0x18004836b  mov     rcx, rbx; pSid
0x18004836e  call    cs:__imp_GetLengthSid
0x180048374  movzx   ecx, r14w
0x180048378  cmp     ecx, eax
0x18004837a  jnz     short loc_1800483AB
0x18004837c  mov     rcx, [rbp+4Fh+Buf1]; Buf1
0x180048380  mov     rdx, rbx; Buf2
0x180048383  movzx   r8d, r14w; Size
0x180048387  call    memcmp_0
0x18004838c  test    eax, eax
0x18004838e  jnz     short loc_1800483AB
0x180048390  mov     rdx, [rbp+4Fh+pAce]
0x180048394  mov     [rbp+4Fh+var_80], 1
0x18004839b  movzx   r15d, word ptr [rdx+2]
0x1800483a0  sub     r15w, r14w
0x1800483a4  add     r15w, word ptr [rbp+4Fh+var_7C]
0x1800483a9  jmp     short loc_1800483AF
0x1800483ab  mov     rdx, [rbp+4Fh+pAce]
0x1800483af  lea     r14d, [r15+r13]
0x1800483b3  cmp     r14w, r13w
0x1800483b7  jb      loc_180048450
0x1800483bd  xor     ebx, ebx
0x1800483bf  cmp     r14w, si
0x1800483c3  jbe     short loc_1800483F5
0x1800483c5  movzx   eax, r14w
0x1800483c9  add     eax, eax
0x1800483cb  cmp     eax, 0FFFFh
0x1800483d0  ja      short loc_180048450
0x1800483d2  movzx   esi, ax
0x1800483d5  lea     r8, [rbp+4Fh+lpName]; void **
0x1800483d9  mov     edx, esi; dwBytes
0x1800483db  mov     [rbp+4Fh+lpName], rbx
0x1800483df  mov     rcx, rdi; lpMem
0x1800483e2  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800483e7  mov     ebx, eax
0x1800483e9  test    eax, eax
0x1800483eb  js      short loc_180048455
0x1800483ed  mov     rdi, [rbp+4Fh+lpName]
0x1800483f1  mov     rdx, [rbp+4Fh+pAce]; Src
0x1800483f5  movzx   ecx, r13w
0x1800483f9  xor     r13d, r13d
0x1800483fc  add     rcx, rdi; void *
0x1800483ff  cmp     [rbp+4Fh+var_80], r13d
0x180048403  jz      short loc_18004841A
0x180048405  mov     rax, [rdx]
0x180048408  movzx   r8d, word ptr [rbp+4Fh+var_7C]
0x18004840d  mov     rdx, [rbp+4Fh+var_68]
0x180048411  mov     [rcx], rax
0x180048414  add     rcx, 8
0x180048418  jmp     short loc_18004841E
0x18004841a  movzx   r8d, r15w; Size
0x18004841e  call    memcpy_0
0x180048423  mov     eax, dword ptr [rbp+4Fh+pAcl]
0x180048426  lea     r8, [rbp+4Fh+pAce]; pAce
0x18004842a  mov     rcx, [rbp+4Fh+hKey]; pAcl
0x18004842e  inc     eax
0x180048430  mov     edx, eax; dwAceIndex
0x180048432  mov     dword ptr [rbp+4Fh+pAcl], eax
0x180048435  call    cs:__imp_GetAce
0x18004843b  test    eax, eax
0x18004843d  jz      loc_1800485E2
0x180048443  movzx   r13d, r14w
0x180048447  mov     r14d, [rbp+4Fh+cchName]
0x18004844b  jmp     loc_18004834B
0x180048450  mov     ebx, 80070216h
0x180048455  xor     r13d, r13d
0x180048458  mov     rcx, r12; lpMem
0x18004845b  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180048460  mov     rcx, rdi; lpMem
0x180048463  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180048468  test    ebx, ebx
0x18004846a  js      loc_1800485C2
0x180048470  mov     r14, [rbp+4Fh+arg_0]
0x180048474  lea     rax, [rbp+4Fh+bDaclPresent]
0x180048478  mov     [rsp+58h], r13; lpftLastWriteTime
0x18004847d  xor     r9d, r9d; lpReserved
0x180048480  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180048485  xor     r8d, r8d; lpcchClass
0x180048488  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004848d  xor     edx, edx; lpClass
0x18004848f  mov     [rsp+110h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180048494  mov     rcx, r14; hKey
0x180048497  mov     [rsp+110h+lpcValues], r13; lpcValues
0x18004849c  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800484a1  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800484a6  lea     rax, [rbp+4Fh+bDaclDefaulted]
0x1800484aa  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x1800484af  mov     [rbp+4Fh+bDaclDefaulted], r13d
0x1800484b3  mov     [rbp+4Fh+bDaclPresent], r13d
0x1800484b7  call    cs:__imp_RegQueryInfoKeyW
0x1800484bd  mov     ebx, eax
0x1800484bf  test    eax, eax
0x1800484c1  jle     short loc_1800484CC
0x1800484c3  movzx   ebx, ax
0x1800484c6  or      ebx, 80070000h
0x1800484cc  test    ebx, ebx
0x1800484ce  js      loc_1800485C2
0x1800484d4  cmp     [rbp+4Fh+bDaclDefaulted], r13d
0x1800484d8  jbe     loc_1800485C2
0x1800484de  mov     eax, [rbp+4Fh+bDaclPresent]
0x1800484e1  lea     rdx, [rbp+4Fh+lpName]
0x1800484e5  inc     eax
0x1800484e7  mov     [rbp+4Fh+lpName], r13
0x1800484eb  mov     ecx, eax
0x1800484ed  mov     [rbp+4Fh+bDaclPresent], eax
0x1800484f0  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x1800484f5  mov     ebx, eax
0x1800484f7  test    eax, eax
0x1800484f9  js      loc_1800485C2
0x1800484ff  mov     edi, r13d
0x180048502  mov     rsi, [rbp+4Fh+lpName]
0x180048506  cmp     [rbp+4Fh+bDaclDefaulted], r13d
0x18004850a  jbe     loc_1800485BA
0x180048510  mov     r15, [rbp+4Fh+pSecurityDescriptor]
0x180048514  mov     r12, [rbp+4Fh+arg_10]
0x180048518  mov     eax, [rbp+4Fh+bDaclPresent]
0x18004851b  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x18004851f  mov     [rsp+110h+lpcValues], r13; lpftLastWriteTime
0x180048524  mov     r8, rsi; lpName
0x180048527  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcchClass
0x18004852c  mov     edx, edi; dwIndex
0x18004852e  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpClass
0x180048533  mov     rcx, r14; hKey
0x180048536  mov     [rsp+110h+lpcSubKeys], r13; lpReserved
0x18004853b  mov     [rbp+4Fh+cchName], eax
0x18004853e  call    cs:__imp_RegEnumKeyExW
0x180048544  mov     ebx, eax
0x180048546  test    eax, eax
0x180048548  jle     short loc_180048553
0x18004854a  movzx   ebx, ax
0x18004854d  or      ebx, 80070000h
0x180048553  test    ebx, ebx
0x180048555  js      short loc_1800485AF
0x180048557  lea     rax, [rbp+4Fh+hKey]
0x18004855b  mov     [rbp+4Fh+hKey], r13
  ... truncated ...
```
