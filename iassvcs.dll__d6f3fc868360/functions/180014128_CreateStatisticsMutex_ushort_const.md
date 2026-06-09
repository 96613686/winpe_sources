# CreateStatisticsMutex(ushort const *)

- ea: `0x180014128`
- end: `0x180014700`
- name: `?CreateStatisticsMutex@@YAPEAXPEBG@Z`
- size: `1496`
- prototype: `HANDLE __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800157b8`

## callees

- `0x18000d1c8`
- `0x1800138d0`
- `0x180014128`
- `0x180017754`
- `0x180017a84`
- `0x1800181e0`
- `0x1800182a0`
- `0x180019010`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180014515`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180014515`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180014477`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180014477`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014411`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001442b`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014445`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014460`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014411`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001442b`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014445`
- `ADVAPI32!AddAccessAllowedAce` at `0x180014460`
- `ADVAPI32!InitializeAcl` at `0x180014370`
- `ADVAPI32!InitializeAcl` at `0x180014370`
- `ADVAPI32!GetLengthSid` at `0x180014283`
- `ADVAPI32!GetLengthSid` at `0x180014293`
- `ADVAPI32!GetLengthSid` at `0x1800142a3`
- `ADVAPI32!GetLengthSid` at `0x1800142b3`
- `ADVAPI32!GetLengthSid` at `0x180014283`
- `ADVAPI32!GetLengthSid` at `0x180014293`
- `ADVAPI32!GetLengthSid` at `0x1800142a3`
- `ADVAPI32!GetLengthSid` at `0x1800142b3`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18001420f`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18001420f`
- `KERNEL32!GlobalFree` at `0x1800141ca`
- `KERNEL32!GlobalFree` at `0x1800141fc`
- `KERNEL32!GlobalFree` at `0x180014603`
- `KERNEL32!GlobalFree` at `0x180014611`
- `KERNEL32!GlobalFree` at `0x18001461f`
- `KERNEL32!GlobalFree` at `0x1800146c1`
- `KERNEL32!GlobalFree` at `0x1800146cf`
- `KERNEL32!GlobalFree` at `0x1800146dd`
- `KERNEL32!GlobalFree` at `0x1800141ca`
- `KERNEL32!GlobalFree` at `0x1800141fc`
- `KERNEL32!GlobalFree` at `0x180014603`
- `KERNEL32!GlobalFree` at `0x180014611`
- `KERNEL32!GlobalFree` at `0x18001461f`
- `KERNEL32!GlobalFree` at `0x1800146c1`
- `KERNEL32!GlobalFree` at `0x1800146cf`
- `KERNEL32!GlobalFree` at `0x1800146dd`
- `KERNEL32!CreateMutexW` at `0x1800145ca`
- `KERNEL32!CreateMutexW` at `0x1800145ca`
- `KERNEL32!GetLastError` at `0x180014219`
- `KERNEL32!GetLastError` at `0x18001437e`
- `KERNEL32!GetLastError` at `0x180014485`
- `KERNEL32!GetLastError` at `0x180014523`
- `KERNEL32!GetLastError` at `0x18001462d`
- `KERNEL32!GetLastError` at `0x180014219`
- `KERNEL32!GetLastError` at `0x18001437e`
- `KERNEL32!GetLastError` at `0x180014485`
- `KERNEL32!GetLastError` at `0x180014523`
- `KERNEL32!GetLastError` at `0x18001462d`
- `KERNEL32!LocalFree` at `0x180014188`
- `KERNEL32!LocalFree` at `0x1800141bb`
- `KERNEL32!LocalFree` at `0x1800141ed`
- `KERNEL32!LocalFree` at `0x1800145f5`
- `KERNEL32!LocalFree` at `0x1800146b3`
- `KERNEL32!LocalFree` at `0x180014188`
- `KERNEL32!LocalFree` at `0x1800141bb`
- `KERNEL32!LocalFree` at `0x1800141ed`
- `KERNEL32!LocalFree` at `0x1800145f5`
- `KERNEL32!LocalFree` at `0x1800146b3`

## string_xrefs

- `0x180014248`: `ConvertStringSidToSid failed. Error %!winerr!`
- `0x1800143a8`: `AddAccessAllowedAce failed. Error %x`
- `0x180014657`: `AddAccessAllowedAce failed. Error %x`
- `0x1800144af`: `InitializeSecurityDescriptor failed. Error %x`
- `0x18001454d`: `SetSecurityDescriptorDacl failed. Error %x`

## pseudocode

```c
HANDLE __fastcall CreateStatisticsMutex(const unsigned __int16 *a1)
{
  PSID v1; // rcx
  char LastError; // bl
  DWORD LengthSid; // r12d
  HGLOBAL v4; // r14
  DWORD v5; // r12d
  HGLOBAL v6; // rsi
  DWORD v7; // r12d
  PSID v8; // rdi
  HLOCAL *p_hMem; // rbx
  __int64 v10; // r12
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  _DWORD *v15; // rax
  char v16; // r12
  char v17; // r12
  char v18; // r12
  HANDLE v19; // r15
  char v21; // r12
  __int64 v22; // [rsp+0h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp+0h] BYREF
  PSID v24; // [rsp+38h] [rbp+8h] BYREF
  HGLOBAL v25; // [rsp+40h] [rbp+10h] BYREF
  HGLOBAL pSid; // [rsp+48h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+50h] [rbp+20h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+68h] [rbp+38h] BYREF

  v24 = 0;
  v25 = 0;
  pSid = 0;
  hMem = 0;
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v24) )
  {
LABEL_4:
    v1 = v24;
    if ( !v24 )
      return 0;
LABEL_90:
    GlobalFree(v1);
    return 0;
  }
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v25) )
  {
LABEL_9:
    if ( v25 )
      GlobalFree(v25);
    goto LABEL_4;
  }
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &pSid) )
  {
LABEL_12:
    if ( hMem )
      LocalFree(hMem);
    if ( pSid )
      GlobalFree(pSid);
    goto LABEL_9;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-611605672-2879557022-2206624263-4029342278-3129212340", &hMem) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("ConvertStringSidToSid failed. Error %!winerr!");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        LastError);
    }
    goto LABEL_12;
  }
  LengthSid = GetLengthSid(hMem);
  v4 = pSid;
  v5 = GetLengthSid(pSid) + LengthSid;
  v6 = v25;
  v7 = GetLengthSid(v25) + v5;
  v8 = v24;
  p_hMem = 0;
  v10 = GetLengthSid(v24) + v7 + 40;
  if ( !(_DWORD)v10
    || (unsigned int)v10 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v10 + g_ulAdditionalProbeSize + 8 < (unsigned int)v10
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_29;
  }
  v11 = v10 + 23;
  if ( v10 + 23 <= (unsigned __int64)(v10 + 8) )
    v11 = 0xFFFFFFFFFFFFFF0LL;
  v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
  v13 = alloca(v12);
  v14 = alloca(v12);
  p_hMem = &hMem;
  if ( &v22 == (__int64 *)-48LL || (LODWORD(hMem) = 1801679955, (p_hMem = &v24) == 0) )
  {
LABEL_29:
    if ( v10 + 8 >= (unsigned __int64)(unsigned int)v10 )
    {
      v15 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v15 )
        goto LABEL_82;
      *v15 = 1885431112;
      p_hMem = (HLOCAL *)(v15 + 2);
    }
    if ( p_hMem )
      goto LABEL_33;
LABEL_82:
    if ( hMem )
      LocalFree(hMem);
    if ( v4 )
      GlobalFree(v4);
    if ( v6 )
      GlobalFree(v6);
    if ( !v8 )
      return 0;
    v1 = v8;
    goto LABEL_90;
  }
LABEL_33:
  if ( !InitializeAcl((PACL)p_hMem, v10, 2u) )
  {
    v16 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("AddAccessAllowedAce failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v16);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !AddAccessAllowedAce((PACL)p_hMem, 2u, 0x1F0001u, v8)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0x1F0001u, v6)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0x1F0001u, v4)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0x1F0001u, hMem) )
  {
    v21 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("AddAccessAllowedAce failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v21);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v17 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("InitializeSecurityDescriptor failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v17);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)p_hMem, 0) )
  {
    v18 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("SetSecurityDescriptorDacl failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v18);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 1;
  MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  v19 = CreateMutexW(&MutexAttributes, 0, L"{A5B99A4D-2959-11D1-BAC8-00C04FC2E20D}");
  if ( *((_DWORD *)p_hMem - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hMem )
    LocalFree(hMem);
  if ( v4 )
    GlobalFree(v4);
  if ( v6 )
    GlobalFree(v6);
  if ( v8 )
    GlobalFree(v8);
  return v19;
}

```

## disassembly

```asm
0x180014128  push    rbp
0x18001412a  push    rbx
0x18001412b  push    rsi
0x18001412c  push    rdi
0x18001412d  push    r12
0x18001412f  push    r14
0x180014131  push    r15
0x180014133  sub     rsp, 0A0h
0x18001413a  lea     rbp, [rsp+30h]
0x18001413f  mov     rax, cs:__security_cookie
0x180014146  xor     rax, rbp
0x180014149  mov     [rbp+0A0h+var_40], rax
0x18001414d  mov     [rbp+0A0h+var_98], 0
0x180014155  mov     [rbp+0A0h+var_90], 0
0x18001415d  mov     [rbp+0A0h+pSid], 0
0x180014165  mov     [rbp+0A0h+hMem], 0
0x18001416d  lea     rdx, [rbp+0A0h+var_98]; void **
0x180014171  mov     ecx, 1Ah; WellKnownSidType
0x180014176  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18001417b  test    eax, eax
0x18001417d  jz      short loc_1800141A0
0x18001417f  mov     rcx, [rbp+0A0h+hMem]; hMem
0x180014183  test    rcx, rcx
0x180014186  jz      short loc_18001418E
0x180014188  call    cs:__imp_LocalFree
0x18001418e  mov     rcx, [rbp+0A0h+var_98]
0x180014192  test    rcx, rcx
0x180014195  jz      loc_1800146E3
0x18001419b  jmp     loc_1800146DD
0x1800141a0  lea     rdx, [rbp+0A0h+var_90]; void **
0x1800141a4  mov     ecx, 39h ; '9'; WellKnownSidType
0x1800141a9  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800141ae  test    eax, eax
0x1800141b0  jz      short loc_1800141D2
0x1800141b2  mov     rcx, [rbp+0A0h+hMem]; hMem
0x1800141b6  test    rcx, rcx
0x1800141b9  jz      short loc_1800141C1
0x1800141bb  call    cs:__imp_LocalFree
0x1800141c1  mov     rcx, [rbp+0A0h+var_90]; hMem
0x1800141c5  test    rcx, rcx
0x1800141c8  jz      short loc_18001418E
0x1800141ca  call    cs:__imp_GlobalFree
0x1800141d0  jmp     short loc_18001418E
0x1800141d2  lea     rdx, [rbp+0A0h+pSid]; void **
0x1800141d6  mov     ecx, 3Ah ; ':'; WellKnownSidType
0x1800141db  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800141e0  test    eax, eax
0x1800141e2  jz      short loc_180014204
0x1800141e4  mov     rcx, [rbp+0A0h+hMem]; hMem
0x1800141e8  test    rcx, rcx
0x1800141eb  jz      short loc_1800141F3
0x1800141ed  call    cs:__imp_LocalFree
0x1800141f3  mov     rcx, [rbp+0A0h+pSid]; hMem
0x1800141f7  test    rcx, rcx
0x1800141fa  jz      short loc_1800141C1
0x1800141fc  call    cs:__imp_GlobalFree
0x180014202  jmp     short loc_1800141C1
0x180014204  lea     rdx, [rbp+0A0h+hMem]; Sid
0x180014208  lea     rcx, StringSid; "S-1-5-80-611605672-2879557022-220662426"...
0x18001420f  call    cs:__imp_ConvertStringSidToSidW
0x180014215  test    eax, eax
0x180014217  jnz     short loc_18001427F
0x180014219  call    cs:__imp_GetLastError
0x18001421f  mov     ebx, eax
0x180014221  lea     rcx, WPP_GLOBAL_Control
0x180014228  mov     rdx, cs:WPP_GLOBAL_Control
0x18001422f  cmp     rdx, rcx
0x180014232  jz      short loc_1800141E4
0x180014234  mov     r15d, 2
0x18001423a  cmp     [rdx+19h], r15b
0x18001423e  jb      short loc_1800141E4
0x180014240  test    byte ptr [rdx+1Ch], 1
0x180014244  jz      short loc_1800141E4
0x180014246  mov     edx, eax
0x180014248  lea     rcx, aConvertstrings; "ConvertStringSidToSid failed. Error %!w"...
0x18001424f  call    WppDbgPrint
0x180014254  lea     edx, [r15+13h]
0x180014258  mov     [rsp+0D0h+var_B0], ebx
0x18001425c  lea     r9, aNapbase; "NAPBASE"
0x180014263  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18001426a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014271  mov     rcx, [rcx+10h]
0x180014275  call    WPP_SF_sD
0x18001427a  jmp     loc_1800141E4
0x18001427f  mov     rcx, [rbp+0A0h+hMem]; pSid
0x180014283  call    cs:__imp_GetLengthSid
0x180014289  mov     r12d, eax
0x18001428c  mov     r14, [rbp+0A0h+pSid]
0x180014290  mov     rcx, r14; pSid
0x180014293  call    cs:__imp_GetLengthSid
0x180014299  add     r12d, eax
0x18001429c  mov     rsi, [rbp+0A0h+var_90]
0x1800142a0  mov     rcx, rsi; pSid
0x1800142a3  call    cs:__imp_GetLengthSid
0x1800142a9  add     r12d, eax
0x1800142ac  mov     rdi, [rbp+0A0h+var_98]
0x1800142b0  mov     rcx, rdi; pSid
0x1800142b3  call    cs:__imp_GetLengthSid
0x1800142b9  add     r12d, 28h ; '('
0x1800142bd  xor     ebx, ebx
0x1800142bf  add     r12d, eax
0x1800142c2  jz      short loc_180014329
0x1800142c4  mov     r15d, r12d
0x1800142c7  cmp     r15, cs:g_ulMaxStackAllocSize
0x1800142ce  ja      short loc_180014329
0x1800142d0  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800142d7  add     rcx, 8
0x1800142db  add     rcx, r15
0x1800142de  cmp     rcx, r15
0x1800142e1  jb      short loc_180014329
0x1800142e3  call    VerifyStackAvailable
0x1800142e8  test    eax, eax
0x1800142ea  jz      short loc_180014329
0x1800142ec  lea     rax, [r12+8]
0x1800142f1  lea     rcx, [rax+0Fh]
0x1800142f5  cmp     rcx, rax
0x1800142f8  ja      short loc_180014304
0x1800142fa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180014304  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180014308  mov     rax, rcx
0x18001430b  call    _alloca_probe
0x180014310  sub     rsp, rcx
0x180014313  lea     rbx, [rsp+0D0h+hMem]
0x180014318  test    rbx, rbx
0x18001431b  jz      short loc_180014329
0x18001431d  mov     dword ptr [rbx], 6B637453h
0x180014323  add     rbx, 8
0x180014327  jnz     short loc_180014361
0x180014329  mov     eax, r12d
0x18001432c  lea     rcx, [r12+8]
0x180014331  cmp     rcx, rax
0x180014334  jb      short loc_180014358
0x180014336  mov     rax, cs:g_pfnAllocate
0x18001433d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014342  mov     rbx, rax
0x180014345  test    rax, rax
0x180014348  jz      loc_1800146AA
0x18001434e  mov     dword ptr [rax], 70616548h
0x180014354  add     rbx, 8
0x180014358  test    rbx, rbx
0x18001435b  jz      loc_1800146AA
0x180014361  mov     r15d, 2
0x180014367  mov     r8d, r15d; dwAclRevision
0x18001436a  mov     edx, r12d; nAclLength
0x18001436d  mov     rcx, rbx; pAcl
0x180014370  call    cs:__imp_InitializeAcl
0x180014376  test    eax, eax
0x180014378  jnz     loc_1800143FF
0x18001437e  call    cs:__imp_GetLastError
0x180014384  mov     r12d, eax
0x180014387  lea     rcx, WPP_GLOBAL_Control
0x18001438e  mov     rdx, cs:WPP_GLOBAL_Control
0x180014395  cmp     rdx, rcx
0x180014398  jz      short loc_1800143DC
0x18001439a  cmp     [rdx+19h], r15b
0x18001439e  jb      short loc_1800143DC
0x1800143a0  test    byte ptr [rdx+1Ch], 1
0x1800143a4  jz      short loc_1800143DC
0x1800143a6  mov     edx, eax
0x1800143a8  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x1800143af  call    WppDbgPrint
0x1800143b4  lea     edx, [r15+14h]
0x1800143b8  mov     [rsp+0D0h+var_B0], r12d
0x1800143bd  lea     r9, aNapbase; "NAPBASE"
0x1800143c4  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x1800143cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d2  mov     rcx, [rcx+10h]
0x1800143d6  call    WPP_SF_sD
0x1800143db  nop
0x1800143dc  test    rbx, rbx
0x1800143df  jz      short loc_1800143FA
0x1800143e1  lea     rcx, [rbx-8]
0x1800143e5  cmp     dword ptr [rcx], 70616548h
0x1800143eb  jnz     short loc_1800143FA
0x1800143ed  mov     rax, cs:g_pfnFree
0x1800143f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f9  nop
0x1800143fa  jmp     loc_1800146AA
0x1800143ff  mov     r9, rdi; pSid
0x180014402  mov     r12d, 1F0001h
0x180014408  mov     r8d, r12d; AccessMask
0x18001440b  mov     edx, r15d; dwAceRevision
0x18001440e  mov     rcx, rbx; pAcl
0x180014411  call    cs:__imp_AddAccessAllowedAce
0x180014417  test    eax, eax
0x180014419  jz      loc_18001462D
0x18001441f  mov     r9, rsi; pSid
0x180014422  mov     r8d, r12d; AccessMask
0x180014425  mov     edx, r15d; dwAceRevision
0x180014428  mov     rcx, rbx; pAcl
0x18001442b  call    cs:__imp_AddAccessAllowedAce
0x180014431  test    eax, eax
0x180014433  jz      loc_18001462D
0x180014439  mov     r9, r14; pSid
0x18001443c  mov     r8d, r12d; AccessMask
0x18001443f  mov     edx, r15d; dwAceRevision
0x180014442  mov     rcx, rbx; pAcl
0x180014445  call    cs:__imp_AddAccessAllowedAce
0x18001444b  test    eax, eax
0x18001444d  jz      loc_18001462D
0x180014453  mov     r9, [rbp+0A0h+hMem]; pSid
0x180014457  mov     r8d, r12d; AccessMask
0x18001445a  mov     edx, r15d; dwAceRevision
0x18001445d  mov     rcx, rbx; pAcl
0x180014460  call    cs:__imp_AddAccessAllowedAce
0x180014466  test    eax, eax
0x180014468  jz      loc_18001462D
0x18001446e  mov     edx, 1; dwRevision
0x180014473  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180014477  call    cs:__imp_InitializeSecurityDescriptor
0x18001447d  test    eax, eax
0x18001447f  jnz     loc_180014507
0x180014485  call    cs:__imp_GetLastError
0x18001448b  mov     r12d, eax
0x18001448e  lea     rcx, WPP_GLOBAL_Control
0x180014495  mov     rdx, cs:WPP_GLOBAL_Control
0x18001449c  cmp     rdx, rcx
0x18001449f  jz      short loc_1800144E4
0x1800144a1  cmp     [rdx+19h], r15b
0x1800144a5  jb      short loc_1800144E4
0x1800144a7  test    byte ptr [rdx+1Ch], 1
0x1800144ab  jz      short loc_1800144E4
0x1800144ad  mov     edx, eax
0x1800144af  lea     rcx, aInitializesecu; "InitializeSecurityDescriptor failed. Er"...
0x1800144b6  call    WppDbgPrint
0x1800144bb  mov     edx, 18h
0x1800144c0  mov     [rsp+0D0h+var_B0], r12d
0x1800144c5  lea     r9, aNapbase; "NAPBASE"
0x1800144cc  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x1800144d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144da  mov     rcx, [rcx+10h]
0x1800144de  call    WPP_SF_sD
0x1800144e3  nop
0x1800144e4  test    rbx, rbx
0x1800144e7  jz      short loc_180014502
0x1800144e9  lea     rcx, [rbx-8]
0x1800144ed  cmp     dword ptr [rcx], 70616548h
0x1800144f3  jnz     short loc_180014502
0x1800144f5  mov     rax, cs:g_pfnFree
0x1800144fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014501  nop
0x180014502  jmp     loc_1800146AA
0x180014507  xor     r9d, r9d; bDaclDefaulted
0x18001450a  mov     r8, rbx; pDacl
0x18001450d  lea     edx, [r9+1]; bDaclPresent
0x180014511  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180014515  call    cs:__imp_SetSecurityDescriptorDacl
0x18001451b  test    eax, eax
0x18001451d  jnz     loc_1800145A5
0x180014523  call    cs:__imp_GetLastError
0x180014529  mov     r12d, eax
0x18001452c  lea     rcx, WPP_GLOBAL_Control
0x180014533  mov     rdx, cs:WPP_GLOBAL_Control
0x18001453a  cmp     rdx, rcx
0x18001453d  jz      short loc_180014582
0x18001453f  cmp     [rdx+19h], r15b
0x180014543  jb      short loc_180014582
0x180014545  test    byte ptr [rdx+1Ch], 1
0x180014549  jz      short loc_180014582
0x18001454b  mov     edx, eax
0x18001454d  lea     rcx, aSetsecuritydes; "SetSecurityDescriptorDacl failed. Error"...
0x180014554  call    WppDbgPrint
0x180014559  mov     edx, 19h
0x18001455e  mov     [rsp+0D0h+var_B0], r12d
0x180014563  lea     r9, aNapbase; "NAPBASE"
0x18001456a  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180014571  mov     rcx, cs:WPP_GLOBAL_Control
0x180014578  mov     rcx, [rcx+10h]
0x18001457c  call    WPP_SF_sD
0x180014581  nop
0x180014582  test    rbx, rbx
0x180014585  jz      short loc_1800145A0
0x180014587  lea     rcx, [rbx-8]
0x18001458b  cmp     dword ptr [rcx], 70616548h
0x180014591  jnz     short loc_1800145A0
0x180014593  mov     rax, cs:g_pfnFree
0x18001459a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001459f  nop
0x1800145a0  jmp     loc_1800146AA
0x1800145a5  mov     qword ptr [rbp+0A0h+MutexAttributes.nLength], 18h
0x1800145ad  mov     qword ptr [rbp+0A0h+MutexAttributes.bInheritHandle], 1
0x1800145b5  lea     rax, [rbp+0A0h+pSecurityDescriptor]
0x1800145b9  mov     [rbp+0A0h+MutexAttributes.lpSecurityDescriptor], rax
0x1800145bd  lea     r8, aA5b99a4d295911; "{A5B99A4D-2959-11D1-BAC8-00C04FC2E20D}"
0x1800145c4  xor     edx, edx; bInitialOwner
0x1800145c6  lea     rcx, [rbp+0A0h+MutexAttributes]; lpMutexAttributes
0x1800145ca  call    cs:__imp_CreateMutexW
0x1800145d0  mov     r15, rax
0x1800145d3  lea     rcx, [rbx-8]
0x1800145d7  cmp     dword ptr [rcx], 70616548h
0x1800145dd  jnz     short loc_1800145EC
0x1800145df  mov     rax, cs:g_pfnFree
0x1800145e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145eb  nop
0x1800145ec  mov     rcx, [rbp+0A0h+hMem]; hMem
0x1800145f0  test    rcx, rcx
0x1800145f3  jz      short loc_1800145FB
0x1800145f5  call    cs:__imp_LocalFree
0x1800145fb  test    r14, r14
0x1800145fe  jz      short loc_180014609
  ... truncated ...
```
