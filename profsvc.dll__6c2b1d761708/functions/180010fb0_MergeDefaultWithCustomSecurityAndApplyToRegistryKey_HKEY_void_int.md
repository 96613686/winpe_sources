# MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)

- ea: `0x180010fb0`
- end: `0x1800114c2`
- name: `?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z`
- size: `1298`
- prototype: `__int64 __fastcall(HKEY hKey, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010da8`

## callees

- `0x180010fb0`
- `0x1800114d0`
- `0x180011c00`
- `0x18001214c`
- `0x1800250b0`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001100d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001100d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ff3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011140`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ff3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011140`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001134d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001134d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011395`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180011034`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001132c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180011034`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001132c`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180011115`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180011115`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001148b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001148b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800110c5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800112e1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800110c5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800112e1`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011280`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011452`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011280`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180011452`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001107c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001107c`

## pseudocode

```c
__int64 __fastcall MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY hKey, void *a2, int a3)
{
  PACL v4; // r14
  PSECURITY_DESCRIPTOR v6; // r15
  HANDLE ProcessHeap; // rax
  struct _ACL *v8; // rax
  PACL v9; // rsi
  int KeySecurity; // eax
  bool v11; // sf
  struct _ACL *v12; // rcx
  DWORD v13; // ebx
  unsigned __int16 v14; // r12
  DWORD AceCount; // edi
  void *v16; // rbx
  LSTATUS v17; // eax
  unsigned int v18; // ebx
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  DWORD i; // ebx
  BOOL Ace; // eax
  LSTATUS v25; // eax
  signed int LastError; // eax
  bool v27; // sf
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  bool v31; // sf
  int v32; // eax
  DWORD dwDaclSize; // [rsp+68h] [rbp-19h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp-15h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-11h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-9h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-1h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+84h] [rbp+3h] BYREF
  DWORD dwOwnerSize; // [rsp+88h] [rbp+7h] BYREF
  DWORD dwSaclSize; // [rsp+8Ch] [rbp+Bh] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+90h] [rbp+Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+98h] [rbp+17h] BYREF
  PACL pAcl; // [rsp+A0h] [rbp+1Fh] BYREF
  DWORD cbSecurityDescriptor; // [rsp+100h] [rbp+7Fh] BYREF

  v4 = 0;
  v6 = 0;
  pAbsoluteSecurityDescriptor = 0;
  pAcl = 0;
  cbSecurityDescriptor = 512;
  ProcessHeap = GetProcessHeap();
  v8 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, 0x200u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_33;
  KeySecurity = RegGetKeySecurity(hKey, 4u, v8, &cbSecurityDescriptor);
  if ( KeySecurity > 0 )
    KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
  if ( KeySecurity != -2147024774 )
    goto LABEL_5;
  pDacl = 0;
  if ( (int)ResultFromHeapReAlloc(v9, cbSecurityDescriptor, (void **)&pDacl) < 0 )
  {
LABEL_33:
    v16 = a2;
    goto LABEL_17;
  }
  v9 = pDacl;
  v25 = RegGetKeySecurity(hKey, 4u, pDacl, &cbSecurityDescriptor);
  v11 = v25 < 0;
  if ( v25 > 0 )
  {
    KeySecurity = (unsigned __int16)v25 | 0x80070000;
LABEL_5:
    v11 = KeySecurity < 0;
  }
  if ( v11 )
    goto LABEL_33;
  if ( !a3 )
    goto LABEL_33;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) && (int)ResultFromKnownLastError() < 0 )
    goto LABEL_33;
  if ( !bDaclPresent )
    goto LABEL_33;
  v12 = pDacl;
  if ( !pDacl )
    goto LABEL_33;
  v13 = 0;
  v14 = 0;
  pAce = 0;
  AceCount = pDacl->AceCount;
  if ( pDacl->AceCount )
  {
    while ( GetAce(v12, v13, &pAce) || (int)ResultFromKnownLastError() >= 0 )
    {
      if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
        v14 += *((_WORD *)pAce + 1);
      if ( ++v13 >= AceCount )
        goto LABEL_16;
      v12 = pDacl;
    }
    goto LABEL_56;
  }
LABEL_16:
  v16 = a2;
  if ( v14 )
  {
    dwAbsoluteSecurityDescriptorSize = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( MakeAbsoluteSD(
           a2,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize)
      || GetLastError() == 122 )
    {
      goto LABEL_36;
    }
    LastError = GetLastError();
    v27 = LastError < 0;
    if ( LastError > 0 )
      v27 = 1;
    if ( !v27 )
    {
LABEL_36:
      if ( (int)ResultFromHeapAlloc(dwAbsoluteSecurityDescriptorSize, &pAbsoluteSecurityDescriptor) < 0 )
      {
        v6 = pAbsoluteSecurityDescriptor;
        goto LABEL_17;
      }
      v32 = ResultFromHeapAlloc(dwDaclSize + v14, (void **)&pAcl);
      v6 = pAbsoluteSecurityDescriptor;
      if ( v32 >= 0 )
      {
        v4 = pAcl;
        if ( MakeAbsoluteSD(
               a2,
               pAbsoluteSecurityDescriptor,
               &dwAbsoluteSecurityDescriptorSize,
               pAcl,
               &dwDaclSize,
               0,
               &dwSaclSize,
               0,
               &dwOwnerSize,
               0,
               &dwPrimaryGroupSize) )
        {
          goto LABEL_39;
        }
        v28 = GetLastError();
        v29 = v28 < 0;
        if ( v28 > 0 )
          v29 = 1;
        if ( !v29 )
        {
LABEL_39:
          v4->AclRevision = 2;
          v4->AclSize += v14;
          for ( i = 0; ; ++i )
          {
            if ( i >= AceCount )
              goto LABEL_44;
            Ace = GetAce(pDacl, i, &pAce);
            if ( (int)ResultFromWin32Bool(Ace) < 0 )
              goto LABEL_56;
            if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
            {
              *((_BYTE *)pAce + 1) &= ~0x10u;
              if ( !AddAce(v4, 2u, 0, pAce, *((unsigned __int16 *)pAce + 1)) )
                break;
            }
          }
          v30 = GetLastError();
          v31 = v30 < 0;
          if ( v30 > 0 )
            v31 = 1;
          if ( !v31 )
          {
LABEL_44:
            v16 = v6;
            goto LABEL_17;
          }
        }
LABEL_56:
        v16 = a2;
        goto LABEL_17;
      }
      v4 = pAcl;
    }
  }
LABEL_17:
  v17 = RegSetKeySecurity(hKey, 4u, v16);
  v18 = v17;
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  if ( v6 )
  {
    v19 = GetProcessHeap();
    if ( !HeapFree(v19, 0, v6) )
      ResultFromKnownLastError();
  }
  if ( v9 )
  {
    v20 = GetProcessHeap();
    if ( !HeapFree(v20, 0, v9) )
      ResultFromKnownLastError();
  }
  if ( v4 )
  {
    v21 = GetProcessHeap();
    if ( !HeapFree(v21, 0, v4) )
      ResultFromKnownLastError();
  }
  return v18;
}

```

## disassembly

```asm
0x180010fb0  mov     rax, rsp
0x180010fb3  mov     [rax+10h], rdx
0x180010fb7  push    rbp
0x180010fb8  push    rbx
0x180010fb9  push    r14
0x180010fbb  lea     rbp, [rax-5Fh]
0x180010fbf  sub     rsp, 0C0h
0x180010fc6  mov     [rax+8], rsi
0x180010fca  mov     ebx, r8d
0x180010fcd  mov     [rax-20h], rdi
0x180010fd1  xor     edi, edi
0x180010fd3  mov     [rax-30h], r13
0x180010fd7  mov     r14d, edi
0x180010fda  mov     [rax-38h], r15
0x180010fde  mov     r13, rcx
0x180010fe1  mov     r15d, edi
0x180010fe4  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x180010fe8  mov     [rbp+57h+pAcl], rdi
0x180010fec  mov     [rbp+57h+cbSecurityDescriptor], 200h
0x180010ff3  call    cs:__imp_GetProcessHeap
0x180010ffa  nop     dword ptr [rax+rax+00h]
0x180010fff  mov     edx, 8; dwFlags
0x180011004  mov     r8d, 200h; dwBytes
0x18001100a  mov     rcx, rax; hHeap
0x18001100d  call    cs:__imp_HeapAlloc
0x180011014  nop     dword ptr [rax+rax+00h]
0x180011019  mov     rsi, rax
0x18001101c  test    rax, rax
0x18001101f  jz      loc_180011224
0x180011025  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180011029  mov     r8, rax; pSecurityDescriptor
0x18001102c  mov     edx, 4; SecurityInformation
0x180011031  mov     rcx, r13; hKey
0x180011034  call    cs:__imp_RegGetKeySecurity
0x18001103b  nop     dword ptr [rax+rax+00h]
0x180011040  test    eax, eax
0x180011042  jg      loc_1800111F8
0x180011048  cmp     eax, 8007007Ah
0x18001104d  jz      loc_1800113DF
0x180011053  test    eax, eax
0x180011055  js      loc_180011224
0x18001105b  test    ebx, ebx
0x18001105d  jz      loc_180011224
0x180011063  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180011067  mov     [rbp+57h+pDacl], rdi
0x18001106b  lea     r8, [rbp+57h+pDacl]; pDacl
0x18001106f  mov     [rbp+57h+bDaclPresent], edi
0x180011072  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180011076  mov     [rbp+57h+bDaclDefaulted], edi
0x180011079  mov     rcx, rsi; pSecurityDescriptor
0x18001107c  call    cs:__imp_GetSecurityDescriptorDacl
0x180011083  nop     dword ptr [rax+rax+00h]
0x180011088  test    eax, eax
0x18001108a  jz      loc_180011217
0x180011090  cmp     [rbp+57h+bDaclPresent], edi
0x180011093  jz      loc_180011224
0x180011099  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18001109d  test    rcx, rcx
0x1800110a0  jz      loc_180011224
0x1800110a6  mov     [rsp+0D0h+var_20], r12
0x1800110ae  mov     ebx, edi
0x1800110b0  mov     r12d, edi
0x1800110b3  mov     [rbp+57h+pAce], rdi
0x1800110b7  movzx   edi, word ptr [rcx+4]
0x1800110bb  test    edi, edi
0x1800110bd  jz      short loc_1800110F4
0x1800110bf  lea     r8, [rbp+57h+pAce]; pAce
0x1800110c3  mov     edx, ebx; dwAceIndex
0x1800110c5  call    cs:__imp_GetAce
0x1800110cc  nop     dword ptr [rax+rax+00h]
0x1800110d1  test    eax, eax
0x1800110d3  jz      loc_180011205
0x1800110d9  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x1800110dd  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x1800110e2  test    eax, eax
0x1800110e4  jnz     loc_1800113FF
0x1800110ea  inc     ebx
0x1800110ec  cmp     ebx, edi
0x1800110ee  jb      loc_1800111EF
0x1800110f4  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x1800110f8  test    r12w, r12w
0x1800110fc  jnz     loc_18001122D
0x180011102  mov     r12, [rsp+0D0h+var_20]
0x18001110a  mov     r8, rbx; pSecurityDescriptor
0x18001110d  mov     edx, 4; SecurityInformation
0x180011112  mov     rcx, r13; hKey
0x180011115  call    cs:__imp_RegSetKeySecurity
0x18001111c  nop     dword ptr [rax+rax+00h]
0x180011121  mov     r13, [rsp+0D0h+var_28]
0x180011129  mov     ebx, eax
0x18001112b  mov     rdi, [rsp+0B8h]
0x180011133  test    eax, eax
0x180011135  jg      loc_1800111E1
0x18001113b  test    r15, r15
0x18001113e  jz      short loc_180011168
0x180011140  call    cs:__imp_GetProcessHeap
0x180011147  nop     dword ptr [rax+rax+00h]
0x18001114c  mov     r8, r15; lpMem
0x18001114f  xor     edx, edx; dwFlags
0x180011151  mov     rcx, rax; hHeap
0x180011154  call    cs:__imp_HeapFree
0x18001115b  nop     dword ptr [rax+rax+00h]
0x180011160  test    eax, eax
0x180011162  jz      loc_1800114A4
0x180011168  mov     r15, [rsp+0D0h+var_30]
0x180011170  test    rsi, rsi
0x180011173  jz      short loc_18001119D
0x180011175  call    cs:__imp_GetProcessHeap
0x18001117c  nop     dword ptr [rax+rax+00h]
0x180011181  mov     r8, rsi; lpMem
0x180011184  xor     edx, edx; dwFlags
0x180011186  mov     rcx, rax; hHeap
0x180011189  call    cs:__imp_HeapFree
0x180011190  nop     dword ptr [rax+rax+00h]
0x180011195  test    eax, eax
0x180011197  jz      loc_1800114AE
0x18001119d  mov     rsi, [rsp+0D0h+arg_0]
0x1800111a5  test    r14, r14
0x1800111a8  jz      short loc_1800111D2
0x1800111aa  call    cs:__imp_GetProcessHeap
0x1800111b1  nop     dword ptr [rax+rax+00h]
0x1800111b6  mov     r8, r14; lpMem
0x1800111b9  xor     edx, edx; dwFlags
0x1800111bb  mov     rcx, rax; hHeap
0x1800111be  call    cs:__imp_HeapFree
0x1800111c5  nop     dword ptr [rax+rax+00h]
0x1800111ca  test    eax, eax
0x1800111cc  jz      loc_1800114B8
0x1800111d2  mov     eax, ebx
0x1800111d4  add     rsp, 0C0h
0x1800111db  pop     r14
0x1800111dd  pop     rbx
0x1800111de  pop     rbp
0x1800111df  retn
0x1800111e1  movzx   ebx, ax
0x1800111e4  or      ebx, 80070000h
0x1800111ea  jmp     loc_18001113B
0x1800111ef  mov     rcx, [rbp+57h+pDacl]
0x1800111f3  jmp     loc_1800110BF
0x1800111f8  movzx   eax, ax
0x1800111fb  or      eax, 80070000h
0x180011200  jmp     loc_180011048
0x180011205  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001120a  test    eax, eax
0x18001120c  jns     loc_1800110D9
0x180011212  jmp     loc_1800113B5
0x180011217  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001121c  test    eax, eax
0x18001121e  jns     loc_180011090
0x180011224  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180011228  jmp     loc_18001110A
0x18001122d  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180011231  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x180011235  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18001123a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001123e  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x180011243  lea     rax, [rbp+57h+dwOwnerSize]
0x180011247  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001124c  xor     r9d, r9d; pDacl
0x18001124f  mov     [rsp+0D0h+pOwner], r14; pOwner
0x180011254  lea     rax, [rbp+57h+dwSaclSize]
0x180011258  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001125d  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18001125f  lea     rax, [rbp+57h+dwDaclSize]
0x180011263  mov     [rsp+0D0h+pSacl], r14; pSacl
0x180011268  mov     rcx, rbx; pSelfRelativeSecurityDescriptor
0x18001126b  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x180011270  mov     [rbp+57h+dwDaclSize], r14d
0x180011274  mov     [rbp+57h+dwSaclSize], r14d
0x180011278  mov     [rbp+57h+dwOwnerSize], r14d
0x18001127c  mov     [rbp+57h+dwPrimaryGroupSize], r14d
0x180011280  call    cs:__imp_MakeAbsoluteSD
0x180011287  nop     dword ptr [rax+rax+00h]
0x18001128c  test    eax, eax
0x18001128e  jnz     short loc_1800112A5
0x180011290  call    cs:__imp_GetLastError
0x180011297  nop     dword ptr [rax+rax+00h]
0x18001129c  cmp     eax, 7Ah ; 'z'
0x18001129f  jnz     loc_18001134D
0x1800112a5  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; dwBytes
0x1800112a8  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; void **
0x1800112ac  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800112b1  test    eax, eax
0x1800112b3  jns     loc_1800113BE
0x1800112b9  mov     r15, [rbp+57h+pAbsoluteSecurityDescriptor]
0x1800112bd  jmp     loc_180011102
0x1800112c2  js      loc_1800113B5
0x1800112c8  mov     byte ptr [r14], 2
0x1800112cc  add     [r14+2], r12w
0x1800112d1  xor     ebx, ebx
0x1800112d3  cmp     ebx, edi
0x1800112d5  jnb     short loc_180011311
0x1800112d7  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1800112db  lea     r8, [rbp+57h+pAce]; pAce
0x1800112df  mov     edx, ebx; dwAceIndex
0x1800112e1  call    cs:__imp_GetAce
0x1800112e8  nop     dword ptr [rax+rax+00h]
0x1800112ed  mov     ecx, eax; int
0x1800112ef  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800112f4  test    eax, eax
0x1800112f6  js      loc_1800113B5
0x1800112fc  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x180011300  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x180011305  test    eax, eax
0x180011307  jnz     loc_18001146B
0x18001130d  inc     ebx
0x18001130f  jmp     short loc_1800112D3
0x180011311  mov     rbx, r15
0x180011314  jmp     loc_180011102
0x180011319  mov     rsi, [rbp+57h+pDacl]
0x18001131d  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180011321  mov     r8, rsi; pSecurityDescriptor
0x180011324  mov     edx, 4; SecurityInformation
0x180011329  mov     rcx, r13; hKey
0x18001132c  call    cs:__imp_RegGetKeySecurity
0x180011333  nop     dword ptr [rax+rax+00h]
0x180011338  test    eax, eax
0x18001133a  jle     loc_180011055
0x180011340  movzx   eax, ax
0x180011343  or      eax, 80070000h
0x180011348  jmp     loc_180011053
0x18001134d  call    cs:__imp_GetLastError
0x180011354  nop     dword ptr [rax+rax+00h]
0x180011359  test    eax, eax
0x18001135b  jle     short loc_180011367
0x18001135d  movzx   eax, ax
0x180011360  or      eax, 80070000h
0x180011365  test    eax, eax
0x180011367  js      loc_180011102
0x18001136d  jmp     loc_1800112A5
0x180011372  call    cs:__imp_GetLastError
0x180011379  nop     dword ptr [rax+rax+00h]
0x18001137e  test    eax, eax
0x180011380  jle     loc_1800112C2
0x180011386  movzx   eax, ax
0x180011389  or      eax, 80070000h
0x18001138e  test    eax, eax
0x180011390  jmp     loc_1800112C2
0x180011395  call    cs:__imp_GetLastError
0x18001139c  nop     dword ptr [rax+rax+00h]
0x1800113a1  test    eax, eax
0x1800113a3  jle     short loc_1800113AF
0x1800113a5  movzx   eax, ax
0x1800113a8  or      eax, 80070000h
0x1800113ad  test    eax, eax
0x1800113af  jns     loc_180011311
0x1800113b5  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x1800113b9  jmp     loc_180011102
0x1800113be  movzx   ecx, r12w
0x1800113c2  lea     rdx, [rbp+57h+pAcl]; void **
0x1800113c6  add     ecx, [rbp+57h+dwDaclSize]; dwBytes
0x1800113c9  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800113ce  mov     r15, [rbp+57h+pAbsoluteSecurityDescriptor]
0x1800113d2  test    eax, eax
0x1800113d4  jns     short loc_18001140D
0x1800113d6  mov     r14, [rbp+57h+pAcl]
0x1800113da  jmp     loc_180011102
0x1800113df  mov     edx, [rbp+57h+cbSecurityDescriptor]; dwBytes
0x1800113e2  lea     r8, [rbp+57h+pDacl]; void **
0x1800113e6  mov     rcx, rsi; lpMem
0x1800113e9  mov     [rbp+57h+pDacl], rdi
0x1800113ed  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800113f2  test    eax, eax
0x1800113f4  js      loc_180011224
0x1800113fa  jmp     loc_180011319
0x1800113ff  mov     rax, [rbp+57h+pAce]
0x180011403  add     r12w, [rax+2]
0x180011408  jmp     loc_1800110EA
0x18001140d  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180011411  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180011415  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18001141a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18001141e  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x180011423  lea     rax, [rbp+57h+dwOwnerSize]
0x180011427  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18001142c  mov     rdx, r15; pAbsoluteSecurityDescriptor
0x18001142f  mov     [rsp+0D0h+pOwner], r14; pOwner
0x180011434  lea     rax, [rbp+57h+dwSaclSize]
0x180011438  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x18001143d  lea     rax, [rbp+57h+dwDaclSize]
0x180011441  mov     [rsp+0D0h+pSacl], r14; pSacl
0x180011446  mov     r14, [rbp+57h+pAcl]
0x18001144a  mov     r9, r14; pDacl
0x18001144d  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x180011452  call    cs:__imp_MakeAbsoluteSD
0x180011459  nop     dword ptr [rax+rax+00h]
0x18001145e  test    eax, eax
0x180011460  jnz     loc_1800112C8
0x180011466  jmp     loc_180011372
0x18001146b  mov     rax, [rbp+57h+pAce]
0x18001146f  xor     r8d, r8d; dwStartingAceIndex
0x180011472  mov     edx, 2; dwAceRevision
0x180011477  mov     rcx, r14; pAcl
0x18001147a  and     byte ptr [rax+1], 0EFh
0x18001147e  mov     r9, [rbp+57h+pAce]; pAceList
0x180011482  movzx   eax, word ptr [r9+2]
0x180011487  mov     dword ptr [rsp+0D0h+lpdwDaclSize], eax; nAceListLength
0x18001148b  call    cs:__imp_AddAce
0x180011492  nop     dword ptr [rax+rax+00h]
0x180011497  test    eax, eax
  ... truncated ...
```
