# GetInfoEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,bool,ushort const *,ushort *,ulong *)

- ea: `0x18000e5b0`
- end: `0x18000ed3a`
- name: `?GetInfoEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@_N0PEAGPEAK@Z`
- size: `1930`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, bool, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000ded0`
- `0x18017f504`
- `0x1801a5b90`

## callees

- `0x18000c4bc`
- `0x18000e5b0`
- `0x18000f930`
- `0x180013b7c`
- `0x180014e38`
- `0x18003c030`
- `0x18003e40c`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000e8d7`
- `ADVAPI32!RegCloseKey` at `0x18000ea00`
- `ADVAPI32!RegCloseKey` at `0x18000e8d7`
- `ADVAPI32!RegCloseKey` at `0x18000ea00`
- `KERNEL32!InitializeCriticalSection` at `0x18000e7ef`
- `KERNEL32!InitializeCriticalSection` at `0x18000e7ef`
- `KERNEL32!DeleteCriticalSection` at `0x18000e909`
- `KERNEL32!DeleteCriticalSection` at `0x18000ea32`
- `KERNEL32!DeleteCriticalSection` at `0x18000e909`
- `KERNEL32!DeleteCriticalSection` at `0x18000ea32`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea22`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea22`
- `KERNEL32!EnterCriticalSection` at `0x18000e8c1`
- `KERNEL32!EnterCriticalSection` at `0x18000e9ea`
- `KERNEL32!EnterCriticalSection` at `0x18000e8c1`
- `KERNEL32!EnterCriticalSection` at `0x18000e9ea`
- `KERNEL32!lstrlenW` at `0x18000e660`
- `KERNEL32!lstrlenW` at `0x18000e660`
- `KERNEL32!GlobalFree` at `0x18000e73f`
- `KERNEL32!GlobalFree` at `0x18000e91f`
- `KERNEL32!GlobalFree` at `0x18000e935`
- `KERNEL32!GlobalFree` at `0x18000e9ce`
- `KERNEL32!GlobalFree` at `0x18000eab4`
- `KERNEL32!GlobalFree` at `0x18000ec2f`
- `KERNEL32!GlobalFree` at `0x18000ecb2`
- `KERNEL32!GlobalFree` at `0x18000ed0e`
- `KERNEL32!GlobalFree` at `0x18000e73f`
- `KERNEL32!GlobalFree` at `0x18000e91f`
- `KERNEL32!GlobalFree` at `0x18000e935`
- `KERNEL32!GlobalFree` at `0x18000e9ce`
- `KERNEL32!GlobalFree` at `0x18000eab4`
- `KERNEL32!GlobalFree` at `0x18000ec2f`
- `KERNEL32!GlobalFree` at `0x18000ecb2`
- `KERNEL32!GlobalFree` at `0x18000ed0e`
- `KERNEL32!lstrcmpiW` at `0x18000ea51`
- `KERNEL32!lstrcmpiW` at `0x18000ebc0`
- `KERNEL32!lstrcmpiW` at `0x18000ebde`
- `KERNEL32!lstrcmpiW` at `0x18000ea51`
- `KERNEL32!lstrcmpiW` at `0x18000ebc0`
- `KERNEL32!lstrcmpiW` at `0x18000ebde`
- `USER32!CharUpperW` at `0x18000e650`
- `USER32!CharUpperW` at `0x18000e650`

## string_xrefs

- `0x18000e98e`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c
__int64 __fastcall GetInfoEx(
        WCHAR *a1,
        WCHAR *a2,
        enum tagMSIINSTALLCONTEXT a3,
        char a4,
        const unsigned __int16 *lpString1,
        unsigned __int16 *a6,
        unsigned int *a7)
{
  __int64 v10; // rax
  WCHAR *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  int v14; // eax
  char v16; // al
  _BYTE *v17; // r10
  int v18; // eax
  __int64 v19; // rcx
  _WORD *v20; // r9
  unsigned int v21; // r8d
  __int64 *v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // esi
  unsigned int v25; // edi
  char v26; // bl
  unsigned int CurrentUserStringSID; // eax
  unsigned int v28; // ebx
  int v29; // edi
  unsigned int Info; // ebx
  unsigned int *v31; // rcx
  int v32; // r14d
  int v33; // [rsp+38h] [rbp-C8h]
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v35; // [rsp+68h] [rbp-98h]
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  HGLOBAL v37; // [rsp+80h] [rbp-80h]
  int v38; // [rsp+88h] [rbp-78h]
  __int16 v39; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+98h] [rbp-68h] BYREF
  HGLOBAL v41; // [rsp+C0h] [rbp-40h] BYREF
  int v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+CCh] [rbp-34h]
  _BYTE hMem[128]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR sz[37]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v46; // [rsp+19Ah] [rbp+9Ah]
  _BYTE v47[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v35 = a7;
  if ( !a1 )
    return 87;
  v10 = 2147483646;
  v11 = sz;
  v12 = 39;
  do
  {
    if ( !v10 )
      break;
    if ( !*a1 )
      break;
    *v11++ = *a1++;
    --v10;
    --v12;
  }
  while ( v12 );
  v13 = v11 - 1;
  if ( v12 )
    v13 = v11;
  *v13 = 0;
  if ( !v12 )
    return 87;
  CharUpperW(sz);
  v14 = lstrlenW(sz);
  if ( v46 != 125
    || sz[9] != 45
    || sz[0] != 123
    || sz[24] != 45
    || v14 != 38
    || sz[14] != 45
    || sz[19] != 45
    || a2 && (a3 == MSIINSTALLCONTEXT_MACHINE || !*a2 || !lstrcmpiW(a2, L"S-1-5-18") || !lstrcmpiW(a2, L"S-1-1-0")) )
  {
    return 87;
  }
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0
    || a3 == (MSIINSTALLCONTEXT_USERUNMANAGED|MSIINSTALLCONTEXT_USERMANAGED)
    || !lpString1
    || !*lpString1
    || a6 && !a7 )
  {
    return 87;
  }
  v16 = 0;
  v42 = 64;
  v17 = hMem;
  v41 = hMem;
  if ( !a2 && (a3 & 3) != 0 )
  {
    v43 = 64;
    CurrentUserStringSID = GetCurrentUserStringSID(&v41);
    v28 = CurrentUserStringSID;
    if ( CurrentUserStringSID )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Failed to get the current user SID with error code=%d",
          (const unsigned __int16 *)CurrentUserStringSID,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( v42 > 64 )
        GlobalFree(v41);
      return v28;
    }
    v17 = v41;
    v16 = 1;
    a2 = (WCHAR *)v41;
  }
  if ( a3 != MSIINSTALLCONTEXT_MACHINE && !v16 )
  {
    if ( !IsCurrentUser(a2) && !IsAdmin() && !a4 )
    {
      if ( v42 > 64 )
        GlobalFree(v41);
      return 5;
    }
    v17 = v41;
  }
  v18 = 0;
  while ( v18 < 38 )
  {
    v19 = v18++;
    if ( !sz[v19] )
      goto LABEL_28;
  }
  if ( v46 != 125 || sz[0] != 123 )
    goto LABEL_28;
  v20 = v47;
  v21 = 0;
  v22 = qword_1802796B8;
  while ( v22 < &qword_1802796D8 )
  {
    if ( v21 >= 0x21 )
      goto LABEL_28;
    v23 = *(unsigned __int8 *)v22;
    v22 = (__int64 *)((char *)v22 + 1);
    *v20++ = sz[v23];
    ++v21;
  }
  if ( v21 >= 0x21 )
  {
LABEL_28:
    if ( v42 > 64 )
      GlobalFree(v17);
    return 87;
  }
  *v20 = 0;
  v24 = 3;
  switch ( a3 )
  {
    case MSIINSTALLCONTEXT_MACHINE:
      v25 = 2;
      break;
    case MSIINSTALLCONTEXT_USERMANAGED:
      v25 = 0;
      break;
    case MSIINSTALLCONTEXT_USERUNMANAGED:
      v25 = 1;
      if ( !IsCurrentUser(a2) )
      {
        v26 = 1;
        goto LABEL_40;
      }
      break;
    default:
      v25 = 3;
      break;
  }
  v26 = 0;
LABEL_40:
  v38 = 1;
  v37 = &v39;
  v39 = 0;
  *(_OWORD *)hKey = 0;
  InitializeCriticalSection(&CriticalSection);
  v34 = 0;
  if ( (unsigned int)GetInfo(v47, a2, v25, 1, L"LocalPackage", 0, &v34, 1, -1) || !v34 )
  {
    if ( !v26 )
    {
      if ( (a3 & 4) != 0 )
      {
        LOBYTE(v33) = 0;
        if ( !(unsigned int)GetInfo(v47, a2, 2, 1, L"AdvertiseFlags", 0, 0, v33, 1) )
        {
          v29 = 1;
          EnterCriticalSection(&CriticalSection);
          if ( hKey[0] )
          {
            RegCloseKey(hKey[0]);
            hKey[0] = 0;
            *(_WORD *)v37 = 0;
          }
          LeaveCriticalSection(&CriticalSection);
          DeleteCriticalSection(&CriticalSection);
          if ( v38 > 1 )
            GlobalFree(v37);
          goto LABEL_63;
        }
      }
      if ( (a3 & 0xFFFFFFFB) == 0 )
      {
        EnterCriticalSection(&CriticalSection);
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
          *(_WORD *)v37 = 0;
        }
        LeaveCriticalSection(&CriticalSection);
        DeleteCriticalSection(&CriticalSection);
        if ( v38 > 1 )
          GlobalFree(v37);
        goto LABEL_49;
      }
      LOBYTE(v33) = 0;
      if ( (unsigned int)GetInfo(v47, a2, 0, 1, L"AdvertiseFlags", 0, 0, v33, 1) )
      {
        LOBYTE(v33) = 0;
        if ( (unsigned int)GetInfo(v47, a2, 1, 1, L"AdvertiseFlags", 0, 0, v33, 1) || (a3 & 2) == 0 )
          goto LABEL_73;
LABEL_111:
        v29 = 1;
        goto LABEL_76;
      }
      if ( (a3 & 1) != 0 )
        goto LABEL_111;
    }
LABEL_73:
    CRegHandle::~CRegHandle((CRegHandle *)hKey);
LABEL_49:
    if ( v42 > 64 )
      GlobalFree(v41);
    return 1605;
  }
  v29 = 5;
LABEL_76:
  CRegHandle::~CRegHandle((CRegHandle *)hKey);
LABEL_63:
  if ( lstrcmpiW(lpString1, L"State") )
  {
    if ( a3 == MSIINSTALLCONTEXT_MACHINE )
    {
      v24 = 2;
    }
    else
    {
      v32 = a3 - 1;
      if ( v32 )
      {
        if ( v32 == 1 )
          v24 = 1;
      }
      else
      {
        v24 = 0;
      }
    }
    LOBYTE(v33) = v26;
    Info = GetInfo(v47, a2, v24, 1, lpString1, a6, v35, v33, v29);
    goto LABEL_67;
  }
  v31 = v35;
  if ( v35 )
  {
    if ( *v35 < 2 )
    {
      Info = 234;
    }
    else
    {
      *a6 = v29 + 48;
      Info = 0;
      a6[1] = 0;
    }
    *v31 = 1;
LABEL_67:
    if ( v42 > 64 )
      GlobalFree(v41);
    return Info;
  }
  if ( v42 > 64 )
    GlobalFree(v41);
  return 0;
}

```

## disassembly

```asm
0x18000e5b0  push    rbp
0x18000e5b2  push    rbx
0x18000e5b3  push    rdi
0x18000e5b4  push    r12
0x18000e5b6  push    r13
0x18000e5b8  push    r14
0x18000e5ba  push    r15
0x18000e5bc  lea     rbp, [rsp-100h]
0x18000e5c4  sub     rsp, 200h
0x18000e5cb  mov     rax, cs:__security_cookie
0x18000e5d2  xor     rax, rsp
0x18000e5d5  mov     [rbp+130h+var_40], rax
0x18000e5dc  mov     rbx, [rbp+130h+arg_30]
0x18000e5e3  movzx   edi, r9b
0x18000e5e7  mov     r15, [rbp+130h+lpString1]
0x18000e5ee  mov     r14d, r8d
0x18000e5f1  mov     r13, [rbp+130h+arg_28]
0x18000e5f8  mov     r12, rdx
0x18000e5fb  mov     [rsp+230h+var_1C8], rbx
0x18000e600  test    rcx, rcx
0x18000e603  jz      short loc_18000E676
0x18000e605  mov     eax, 7FFFFFFEh
0x18000e60a  lea     r8, [rbp+130h+sz]
0x18000e60e  mov     edx, 27h ; '''
0x18000e613  test    rax, rax
0x18000e616  jz      short loc_18000E637
0x18000e618  movzx   r9d, word ptr [rcx]
0x18000e61c  test    r9w, r9w
0x18000e620  jz      short loc_18000E637
0x18000e622  mov     [r8], r9w
0x18000e626  add     rcx, 2
0x18000e62a  add     r8, 2
0x18000e62e  dec     rax
0x18000e631  sub     rdx, 1
0x18000e635  jnz     short loc_18000E613
0x18000e637  test    rdx, rdx
0x18000e63a  lea     rcx, [r8-2]
0x18000e63e  cmovnz  rcx, r8
0x18000e642  xor     eax, eax
0x18000e644  mov     [rcx], ax
0x18000e647  test    rdx, rdx
0x18000e64a  jz      short loc_18000E676
0x18000e64c  lea     rcx, [rbp+130h+sz]; lpsz
0x18000e650  call    cs:__imp_CharUpperW
0x18000e657  nop     dword ptr [rax+rax+00h]
0x18000e65c  lea     rcx, [rbp+130h+sz]; lpString
0x18000e660  call    cs:__imp_lstrlenW
0x18000e667  nop     dword ptr [rax+rax+00h]
0x18000e66c  cmp     [rbp+130h+var_96], 7Dh ; '}'
0x18000e674  jz      short loc_18000E69E
0x18000e676  mov     eax, 57h ; 'W'
0x18000e67b  mov     rcx, [rbp+130h+var_40]
0x18000e682  xor     rcx, rsp; StackCookie
0x18000e685  call    __security_check_cookie
0x18000e68a  add     rsp, 200h
0x18000e691  pop     r15
0x18000e693  pop     r14
0x18000e695  pop     r13
0x18000e697  pop     r12
0x18000e699  pop     rdi
0x18000e69a  pop     rbx
0x18000e69b  pop     rbp
0x18000e69c  retn
0x18000e69e  cmp     [rbp+130h+var_CE], 2Dh ; '-'
0x18000e6a3  jnz     short loc_18000E676
0x18000e6a5  cmp     [rbp+130h+sz], 7Bh ; '{'
0x18000e6aa  jnz     short loc_18000E676
0x18000e6ac  cmp     [rbp+130h+var_B0], 2Dh ; '-'
0x18000e6b4  jnz     short loc_18000E676
0x18000e6b6  cmp     eax, 26h ; '&'
0x18000e6b9  jnz     short loc_18000E676
0x18000e6bb  cmp     [rbp+130h+var_C4], 2Dh ; '-'
0x18000e6c0  jnz     short loc_18000E676
0x18000e6c2  cmp     [rbp+130h+var_BA], 2Dh ; '-'
0x18000e6c7  jnz     short loc_18000E676
0x18000e6c9  test    r12, r12
0x18000e6cc  jnz     loc_18000EBA0
0x18000e6d2  lea     eax, [r14-1]
0x18000e6d6  test    eax, 0FFFFFFFCh
0x18000e6db  jnz     short loc_18000E676
0x18000e6dd  cmp     r14d, 3
0x18000e6e1  jz      short loc_18000E676
0x18000e6e3  test    r15, r15
0x18000e6e6  jz      short loc_18000E676
0x18000e6e8  cmp     word ptr [r15], 0
0x18000e6ed  jz      short loc_18000E676
0x18000e6ef  test    r13, r13
0x18000e6f2  jnz     loc_18000EB92
0x18000e6f8  xor     al, al
0x18000e6fa  mov     [rbp+130h+var_168], 40h ; '@'
0x18000e701  lea     r10, [rbp+130h+hMem]
0x18000e705  mov     [rbp+130h+var_170], r10
0x18000e709  test    r12, r12
0x18000e70c  jz      loc_18000E953
0x18000e712  cmp     r14d, 4
0x18000e716  jnz     loc_18000EBF7
0x18000e71c  xor     eax, eax
0x18000e71e  xchg    ax, ax
0x18000e720  cmp     eax, 26h ; '&'
0x18000e723  jge     short loc_18000E750
0x18000e725  movsxd  rcx, eax
0x18000e728  inc     eax
0x18000e72a  cmp     [rbp+rcx*2+130h+sz], 0
0x18000e730  jnz     short loc_18000E720
0x18000e732  cmp     [rbp+130h+var_168], 40h ; '@'
0x18000e736  jle     loc_18000E676
0x18000e73c  mov     rcx, r10; hMem
0x18000e73f  call    cs:__imp_GlobalFree
0x18000e746  nop     dword ptr [rax+rax+00h]
0x18000e74b  jmp     loc_18000E676
0x18000e750  cmp     [rbp+130h+var_96], 7Dh ; '}'
0x18000e758  jnz     short loc_18000E732
0x18000e75a  cmp     [rbp+130h+sz], 7Bh ; '{'
0x18000e75f  jnz     short loc_18000E732
0x18000e761  lea     r9, [rbp+130h+var_90]
0x18000e768  xor     r8d, r8d
0x18000e76b  lea     rdx, qword_1802796B8
0x18000e772  lea     r11, qword_1802796D8
0x18000e779  nop     dword ptr [rax+00000000h]
0x18000e780  cmp     rdx, r11
0x18000e783  jnb     short loc_18000E7A3
0x18000e785  cmp     r8d, 21h ; '!'
0x18000e789  jnb     short loc_18000E732
0x18000e78b  movzx   eax, byte ptr [rdx]
0x18000e78e  inc     rdx
0x18000e791  movzx   ecx, [rbp+rax*2+130h+sz]
0x18000e796  mov     [r9], cx
0x18000e79a  add     r9, 2
0x18000e79e  inc     r8d
0x18000e7a1  jmp     short loc_18000E780
0x18000e7a3  cmp     r8d, 21h ; '!'
0x18000e7a7  jnb     short loc_18000E732
0x18000e7a9  xor     eax, eax
0x18000e7ab  mov     [rsp+230h+arg_10], rsi
0x18000e7b3  mov     [r9], ax
0x18000e7b7  mov     esi, 3
0x18000e7bc  cmp     r14d, 4
0x18000e7c0  jnz     loc_18000EC45
0x18000e7c6  mov     edi, 2
0x18000e7cb  xor     bl, bl
0x18000e7cd  lea     rax, [rbp+130h+var_1A0]
0x18000e7d1  mov     [rbp+130h+var_1A8], 1
0x18000e7d8  mov     [rbp+130h+var_1B0], rax
0x18000e7dc  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000e7e0  xor     eax, eax
0x18000e7e2  xorps   xmm0, xmm0
0x18000e7e5  mov     [rbp+130h+var_1A0], ax
0x18000e7e9  movdqa  xmmword ptr [rsp+230h+hKey], xmm0
0x18000e7ef  call    cs:__imp_InitializeCriticalSection
0x18000e7f6  nop     dword ptr [rax+rax+00h]
0x18000e7fb  mov     dword ptr [rsp+230h+var_1F0], 0FFFFFFFFh
0x18000e803  lea     rax, [rsp+230h+var_1D0]
0x18000e808  mov     byte ptr [rsp+230h+var_1F8], 1
0x18000e80d  lea     rcx, [rbp+130h+var_90]
0x18000e814  mov     [rsp+230h+var_200], rax
0x18000e819  mov     r9d, 1
0x18000e81f  lea     rax, aLocalpackage_0; "LocalPackage"
0x18000e826  mov     [rsp+230h+var_208], 0
0x18000e82f  mov     r8d, edi
0x18000e832  mov     [rsp+230h+var_210], rax
0x18000e837  mov     rdx, r12
0x18000e83a  mov     [rsp+230h+var_1D0], 0
0x18000e842  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000e847  test    eax, eax
0x18000e849  jz      loc_18000EB73
0x18000e84f  test    bl, bl
0x18000e851  jnz     loc_18000EB64
0x18000e857  lea     rax, aAdvertiseflags; "AdvertiseFlags"
0x18000e85e  test    r14b, 4
0x18000e862  jz      short loc_18000E8B1
0x18000e864  mov     dword ptr [rsp+230h+var_1F0], 1
0x18000e86c  lea     rcx, [rbp+130h+var_90]
0x18000e873  mov     byte ptr [rsp+230h+var_1F8], bl
0x18000e877  mov     r9d, 1
0x18000e87d  mov     [rsp+230h+var_200], 0
0x18000e886  mov     r8d, 2
0x18000e88c  mov     [rsp+230h+var_208], 0
0x18000e895  mov     rdx, r12
0x18000e898  mov     [rsp+230h+var_210], rax
0x18000e89d  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000e8a2  test    eax, eax
0x18000e8a4  jz      loc_18000E9E1
0x18000e8aa  lea     rax, aAdvertiseflags; "AdvertiseFlags"
0x18000e8b1  mov     edi, r14d
0x18000e8b4  and     edi, 0FFFFFFFBh
0x18000e8b7  jnz     loc_18000EACF
0x18000e8bd  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000e8c1  call    cs:__imp_EnterCriticalSection
0x18000e8c8  nop     dword ptr [rax+rax+00h]
0x18000e8cd  mov     rcx, [rsp+230h+hKey]; hKey
0x18000e8d2  test    rcx, rcx
0x18000e8d5  jz      short loc_18000E8F5
0x18000e8d7  call    cs:__imp_RegCloseKey
0x18000e8de  nop     dword ptr [rax+rax+00h]
0x18000e8e3  mov     rax, [rbp+130h+var_1B0]
0x18000e8e7  xor     ecx, ecx
0x18000e8e9  mov     [rsp+230h+hKey], 0
0x18000e8f2  mov     [rax], cx
0x18000e8f5  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000e8f9  call    cs:__imp_LeaveCriticalSection
0x18000e900  nop     dword ptr [rax+rax+00h]
0x18000e905  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000e909  call    cs:__imp_DeleteCriticalSection
0x18000e910  nop     dword ptr [rax+rax+00h]
0x18000e915  cmp     [rbp+130h+var_1A8], 1
0x18000e919  jle     short loc_18000E92B
0x18000e91b  mov     rcx, [rbp+130h+var_1B0]; hMem
0x18000e91f  call    cs:__imp_GlobalFree
0x18000e926  nop     dword ptr [rax+rax+00h]
0x18000e92b  cmp     [rbp+130h+var_168], 40h ; '@'
0x18000e92f  jle     short loc_18000E941
0x18000e931  mov     rcx, [rbp+130h+var_170]; hMem
0x18000e935  call    cs:__imp_GlobalFree
0x18000e93c  nop     dword ptr [rax+rax+00h]
0x18000e941  mov     rsi, [rsp+230h+arg_10]
0x18000e949  mov     eax, 645h
0x18000e94e  jmp     loc_18000E67B
0x18000e953  test    r14b, 3
0x18000e957  jz      loc_18000E712
0x18000e95d  lea     rcx, [rbp+130h+var_170]
0x18000e961  mov     [rbp+130h+var_164], 40h ; '@'
0x18000e968  call    ?GetCurrentUserStringSID@@YAKAEAV?$CAPITempBufferRef@G@@@Z; GetCurrentUserStringSID(CAPITempBufferRef<ushort> &)
0x18000e96d  mov     ebx, eax
0x18000e96f  test    eax, eax
0x18000e971  jz      loc_18000ECEE
0x18000e977  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18000e97e  jz      short loc_18000E9C4
0x18000e980  lea     rax, aNull; "(NULL)"
0x18000e987  xor     edx, edx; unsigned __int16
0x18000e989  mov     [rsp+230h+var_1D8], rdx; void *
0x18000e98e  lea     r9, aFailedToGetThe; "Failed to get the current user SID with"...
0x18000e995  mov     [rsp+230h+var_1E0], edx; unsigned int
0x18000e999  xor     r8d, r8d; int
0x18000e99c  mov     [rsp+230h+var_1E8], rax; unsigned __int16 *
0x18000e9a1  mov     ecx, 9; int
0x18000e9a6  mov     [rsp+230h+var_1F0], rax; unsigned __int16 *
0x18000e9ab  mov     [rsp+230h+var_1F8], rax; unsigned __int16 *
0x18000e9b0  mov     [rsp+230h+var_200], rax; unsigned __int16 *
0x18000e9b5  mov     [rsp+230h+var_208], rax; unsigned __int16 *
0x18000e9ba  mov     [rsp+230h+var_210], rbx; unsigned __int16 *
0x18000e9bf  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000e9c4  cmp     [rbp+130h+var_168], 40h ; '@'
0x18000e9c8  jle     short loc_18000E9DA
0x18000e9ca  mov     rcx, [rbp+130h+var_170]; hMem
0x18000e9ce  call    cs:__imp_GlobalFree
0x18000e9d5  nop     dword ptr [rax+rax+00h]
0x18000e9da  mov     eax, ebx
0x18000e9dc  jmp     loc_18000E67B
0x18000e9e1  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000e9e5  mov     edi, 1
0x18000e9ea  call    cs:__imp_EnterCriticalSection
0x18000e9f1  nop     dword ptr [rax+rax+00h]
0x18000e9f6  mov     rcx, [rsp+230h+hKey]; hKey
0x18000e9fb  test    rcx, rcx
0x18000e9fe  jz      short loc_18000EA1E
0x18000ea00  call    cs:__imp_RegCloseKey
0x18000ea07  nop     dword ptr [rax+rax+00h]
0x18000ea0c  mov     rax, [rbp+130h+var_1B0]
0x18000ea10  xor     ecx, ecx
0x18000ea12  mov     [rsp+230h+hKey], 0
0x18000ea1b  mov     [rax], cx
0x18000ea1e  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000ea22  call    cs:__imp_LeaveCriticalSection
0x18000ea29  nop     dword ptr [rax+rax+00h]
0x18000ea2e  lea     rcx, [rbp+130h+CriticalSection]; lpCriticalSection
0x18000ea32  call    cs:__imp_DeleteCriticalSection
0x18000ea39  nop     dword ptr [rax+rax+00h]
0x18000ea3e  cmp     [rbp+130h+var_1A8], edi
0x18000ea41  jg      loc_18000ED0A
0x18000ea47  lea     rdx, aState; "State"
0x18000ea4e  mov     rcx, r15; lpString1
0x18000ea51  call    cs:__imp_lstrcmpiW
0x18000ea58  nop     dword ptr [rax+rax+00h]
0x18000ea5d  test    eax, eax
0x18000ea5f  jz      loc_18000EC75
0x18000ea65  cmp     r14d, 4
0x18000ea69  jnz     loc_18000ECD6
0x18000ea6f  mov     esi, 2
0x18000ea74  mov     rcx, [rsp+230h+var_1C8]
0x18000ea79  mov     r9d, 1
0x18000ea7f  mov     dword ptr [rsp+230h+var_1F0], edi
0x18000ea83  mov     r8d, esi
0x18000ea86  mov     byte ptr [rsp+230h+var_1F8], bl
0x18000ea8a  mov     rdx, r12
0x18000ea8d  mov     [rsp+230h+var_200], rcx
0x18000ea92  lea     rcx, [rbp+130h+var_90]
0x18000ea99  mov     [rsp+230h+var_208], r13
0x18000ea9e  mov     [rsp+230h+var_210], r15
0x18000eaa3  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x18000eaa8  mov     ebx, eax
0x18000eaaa  cmp     [rbp+130h+var_168], 40h ; '@'
0x18000eaae  jle     short loc_18000EAC0
0x18000eab0  mov     rcx, [rbp+130h+var_170]; hMem
0x18000eab4  call    cs:__imp_GlobalFree
0x18000eabb  nop     dword ptr [rax+rax+00h]
0x18000eac0  mov     rsi, [rsp+230h+arg_10]
0x18000eac8  mov     eax, ebx
0x18000eaca  jmp     loc_18000E67B
0x18000eacf  mov     dword ptr [rsp+230h+var_1F0], 1
0x18000ead7  lea     rcx, [rbp+130h+var_90]
  ... truncated ...
```
