# DhcpWriterInit

- ea: `0x18008ddac`
- end: `0x18008e1bd`
- name: `DhcpWriterInit`
- size: `1041`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d644`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18008ddac`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x18008df05`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008dff7`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008df05`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008dff7`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008deac`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008deac`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18008e0b9`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18008e0b9`
- `KERNEL32!LocalAlloc` at `0x18008df2b`
- `KERNEL32!LocalAlloc` at `0x18008df3f`
- `KERNEL32!LocalAlloc` at `0x18008df53`
- `KERNEL32!LocalAlloc` at `0x18008df67`
- `KERNEL32!LocalAlloc` at `0x18008df7b`
- `KERNEL32!LocalAlloc` at `0x18008df2b`
- `KERNEL32!LocalAlloc` at `0x18008df3f`
- `KERNEL32!LocalAlloc` at `0x18008df53`
- `KERNEL32!LocalAlloc` at `0x18008df67`
- `KERNEL32!LocalAlloc` at `0x18008df7b`
- `KERNEL32!GetLastError` at `0x18008df11`
- `KERNEL32!GetLastError` at `0x18008e101`
- `KERNEL32!GetLastError` at `0x18008e190`
- `KERNEL32!GetLastError` at `0x18008df11`
- `KERNEL32!GetLastError` at `0x18008e101`
- `KERNEL32!GetLastError` at `0x18008e190`
- `KERNEL32!LocalFree` at `0x18008e11e`
- `KERNEL32!LocalFree` at `0x18008e132`
- `KERNEL32!LocalFree` at `0x18008e146`
- `KERNEL32!LocalFree` at `0x18008e15a`
- `KERNEL32!LocalFree` at `0x18008e16e`
- `KERNEL32!LocalFree` at `0x18008e182`
- `KERNEL32!LocalFree` at `0x18008e11e`
- `KERNEL32!LocalFree` at `0x18008e132`
- `KERNEL32!LocalFree` at `0x18008e146`
- `KERNEL32!LocalFree` at `0x18008e15a`
- `KERNEL32!LocalFree` at `0x18008e16e`
- `KERNEL32!LocalFree` at `0x18008e182`
- `ole32!CoInitializeSecurity` at `0x18008e030`
- `ole32!CoInitializeSecurity` at `0x18008e030`
- `ole32!CoInitializeEx` at `0x18008de1c`
- `ole32!CoInitializeEx` at `0x18008de1c`

## string_xrefs

- `0x18008e095`: `Dhcp Jet Writer`

## pseudocode

```c
__int64 DhcpWriterInit()
{
  HLOCAL v0; // r12
  struct _ACL *v1; // r15
  struct _ACL *pSacl; // r14
  HLOCAL pOwner; // rsi
  void *v4; // rdi
  unsigned int v5; // ebx
  PSECURITY_DESCRIPTOR v6; // r13
  HLOCAL pPrimaryGroup; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // eax
  signed int v11; // eax
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-1h] BYREF
  __int128 v15; // [rsp+70h] [rbp+7h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+D0h] [rbp+67h] BYREF
  DWORD dwOwnerSize; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD dwSaclSize; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwDaclSize; // [rsp+E8h] [rbp+7Fh] BYREF

  v0 = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v1 = 0;
  dwDaclSize = 0;
  pSacl = 0;
  dwSaclSize = 0;
  pOwner = 0;
  dwOwnerSize = 0;
  v4 = 0;
  dwPrimaryGroupSize = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids);
  dword_1800FD084 = CoInitializeEx(0, 0);
  LOWORD(v5) = dword_1800FD084;
  if ( (int)(dword_1800FD084 + 0x80000000) >= 0 && dword_1800FD084 != -2147417850 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids,
        (unsigned int)dword_1800FD084);
      LOWORD(v5) = dword_1800FD084;
    }
    return (unsigned __int16)v5;
  }
  SecurityDescriptor = 0;
  dword_1800FD268 = dword_1800FD084 != -2147417850;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAG:BAD:(A;;0x3;;;IU)(A;;0x3;;;SY)(A;;0x3;;;BA)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v6 = SecurityDescriptor;
    MakeAbsoluteSD(
      SecurityDescriptor,
      0,
      &dwAbsoluteSecurityDescriptorSize,
      0,
      &dwDaclSize,
      0,
      &dwSaclSize,
      0,
      &dwOwnerSize,
      0,
      &dwPrimaryGroupSize);
    if ( GetLastError() == 122 )
    {
      v0 = LocalAlloc(0, dwAbsoluteSecurityDescriptorSize);
      v1 = (struct _ACL *)LocalAlloc(0, dwDaclSize);
      pSacl = (struct _ACL *)LocalAlloc(0, dwSaclSize);
      pOwner = LocalAlloc(0, dwOwnerSize);
      pPrimaryGroup = LocalAlloc(0, dwPrimaryGroupSize);
      v4 = pPrimaryGroup;
      if ( !v0 || !v1 || !pSacl || !pOwner || !pPrimaryGroup )
      {
        LOWORD(v5) = 14;
        goto LABEL_29;
      }
      if ( MakeAbsoluteSD(
             v6,
             v0,
             &dwAbsoluteSecurityDescriptorSize,
             v1,
             &dwDaclSize,
             pSacl,
             &dwSaclSize,
             pOwner,
             &dwOwnerSize,
             pPrimaryGroup,
             &dwPrimaryGroupSize) )
      {
        v5 = CoInitializeSecurity(v0, -1, 0, 0, 2u, 2u, 0, 0, 0);
        if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147417831 )
        {
          v15 = xmmword_1800E7078;
          v5 = CVssJetWriter::Initialize(
                 (CVssJetWriter *)&off_1800F9870,
                 (struct _GUID *)&v15,
                 L"Dhcp Jet Writer",
                 1,
                 0,
                 (const unsigned __int16 *)&Annotation,
                 (const unsigned __int16 *)&Annotation,
                 0);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          {
            goto LABEL_29;
          }
          v9 = 13;
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_29;
          }
          v9 = 12;
        }
        WPP_SF_D(v8[2], v9, &WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids, v5);
LABEL_29:
        if ( v6 )
          LocalFree(v6);
        if ( v0 )
          LocalFree(v0);
        if ( v1 )
          LocalFree(v1);
        if ( pSacl )
          LocalFree(pSacl);
        if ( pOwner )
          LocalFree(pOwner);
        if ( v4 )
          LocalFree(v4);
        return (unsigned __int16)v5;
      }
    }
    LastError = GetLastError();
    LOWORD(v5) = LastError;
    if ( LastError > 0 )
      LOWORD(v5) = LastError;
    goto LABEL_29;
  }
  v11 = GetLastError();
  LOWORD(v5) = v11;
  if ( v11 > 0 )
    LOWORD(v5) = v11;
  return (unsigned __int16)v5;
}

```

## disassembly

```asm
0x18008ddac  push    rbp
0x18008ddae  push    rbx
0x18008ddaf  push    rsi
0x18008ddb0  push    rdi
0x18008ddb1  push    r12
0x18008ddb3  push    r13
0x18008ddb5  push    r14
0x18008ddb7  push    r15
0x18008ddb9  lea     rbp, [rsp-1Fh]
0x18008ddbe  sub     rsp, 88h
0x18008ddc5  xor     r13d, r13d
0x18008ddc8  mov     r12d, r13d
0x18008ddcb  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x18008ddcf  mov     r15d, r13d
0x18008ddd2  mov     [rbp+57h+dwDaclSize], r13d
0x18008ddd6  mov     r14d, r13d
0x18008ddd9  mov     [rbp+57h+dwSaclSize], r13d
0x18008dddd  mov     esi, r13d
0x18008dde0  mov     [rbp+57h+dwOwnerSize], r13d
0x18008dde4  mov     edi, r13d
0x18008dde7  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x18008ddeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ddf2  lea     rax, WPP_GLOBAL_Control
0x18008ddf9  cmp     rcx, rax
0x18008ddfc  jz      short loc_18008DE18
0x18008ddfe  test    byte ptr [rcx+1Ch], 40h
0x18008de02  jz      short loc_18008DE18
0x18008de04  mov     rcx, [rcx+10h]
0x18008de08  lea     edx, [r13+0Ah]
0x18008de0c  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008de13  call    WPP_SF_
0x18008de18  xor     edx, edx; dwCoInit
0x18008de1a  xor     ecx, ecx; pvReserved
0x18008de1c  call    cs:__imp_CoInitializeEx
0x18008de23  nop     dword ptr [rax+rax+00h]
0x18008de28  mov     edx, 80000000h
0x18008de2d  mov     cs:dword_1800FD084, eax
0x18008de33  mov     ebx, eax
0x18008de35  mov     ecx, 80010106h
0x18008de3a  add     eax, edx
0x18008de3c  test    edx, eax
0x18008de3e  jnz     short loc_18008DE88
0x18008de40  cmp     ebx, ecx
0x18008de42  jz      short loc_18008DE88
0x18008de44  mov     rcx, cs:WPP_GLOBAL_Control
0x18008de4b  lea     rax, WPP_GLOBAL_Control
0x18008de52  cmp     rcx, rax
0x18008de55  jz      loc_18008E1A5
0x18008de5b  test    byte ptr [rcx+1Ch], 10h
0x18008de5f  jz      loc_18008E1A5
0x18008de65  mov     rcx, [rcx+10h]
0x18008de69  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008de70  mov     edx, 0Bh
0x18008de75  mov     r9d, ebx
0x18008de78  call    WPP_SF_D
0x18008de7d  mov     ebx, cs:dword_1800FD084
0x18008de83  jmp     loc_18008E1A5
0x18008de88  cmp     ebx, ecx
0x18008de8a  mov     [rbp+57h+SecurityDescriptor], r13
0x18008de8e  mov     eax, r13d
0x18008de91  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18008de95  setnz   al
0x18008de98  lea     rcx, aOBagBadA0x3IuA; "O:BAG:BAD:(A;;0x3;;;IU)(A;;0x3;;;SY)(A;"...
0x18008de9f  xor     r9d, r9d; SecurityDescriptorSize
0x18008dea2  mov     cs:dword_1800FD268, eax
0x18008dea8  lea     edx, [r9+1]; StringSDRevision
0x18008deac  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008deb3  nop     dword ptr [rax+rax+00h]
0x18008deb8  test    eax, eax
0x18008deba  jz      loc_18008E190
0x18008dec0  mov     r13, [rbp+57h+SecurityDescriptor]
0x18008dec4  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18008dec8  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18008decd  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18008ded1  xor     ebx, ebx
0x18008ded3  lea     rax, [rbp+57h+dwOwnerSize]
0x18008ded7  mov     [rsp+0C0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18008dedc  xor     r9d, r9d; pDacl
0x18008dedf  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18008dee4  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18008dee6  mov     [rsp+0C0h+pOwner], rbx; pOwner
0x18008deeb  lea     rax, [rbp+57h+dwSaclSize]
0x18008deef  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18008def4  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18008def7  lea     rax, [rbp+57h+dwDaclSize]
0x18008defb  mov     [rsp+0C0h+pSacl], rbx; pSacl
0x18008df00  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18008df05  call    cs:__imp_MakeAbsoluteSD
0x18008df0c  nop     dword ptr [rax+rax+00h]
0x18008df11  call    cs:__imp_GetLastError
0x18008df18  nop     dword ptr [rax+rax+00h]
0x18008df1d  cmp     eax, 7Ah ; 'z'
0x18008df20  jnz     loc_18008E101
0x18008df26  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18008df29  xor     ecx, ecx; uFlags
0x18008df2b  call    cs:__imp_LocalAlloc
0x18008df32  nop     dword ptr [rax+rax+00h]
0x18008df37  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x18008df3a  xor     ecx, ecx; uFlags
0x18008df3c  mov     r12, rax
0x18008df3f  call    cs:__imp_LocalAlloc
0x18008df46  nop     dword ptr [rax+rax+00h]
0x18008df4b  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x18008df4e  xor     ecx, ecx; uFlags
0x18008df50  mov     r15, rax
0x18008df53  call    cs:__imp_LocalAlloc
0x18008df5a  nop     dword ptr [rax+rax+00h]
0x18008df5f  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x18008df62  xor     ecx, ecx; uFlags
0x18008df64  mov     r14, rax
0x18008df67  call    cs:__imp_LocalAlloc
0x18008df6e  nop     dword ptr [rax+rax+00h]
0x18008df73  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x18008df76  xor     ecx, ecx; uFlags
0x18008df78  mov     rsi, rax
0x18008df7b  call    cs:__imp_LocalAlloc
0x18008df82  nop     dword ptr [rax+rax+00h]
0x18008df87  mov     rdi, rax
0x18008df8a  test    r12, r12
0x18008df8d  jz      loc_18008E0FA
0x18008df93  test    r15, r15
0x18008df96  jz      loc_18008E0FA
0x18008df9c  test    r14, r14
0x18008df9f  jz      loc_18008E0FA
0x18008dfa5  test    rsi, rsi
0x18008dfa8  jz      loc_18008E0FA
0x18008dfae  test    rax, rax
0x18008dfb1  jz      loc_18008E0FA
0x18008dfb7  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18008dfbb  mov     r9, r15; pDacl
0x18008dfbe  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18008dfc3  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18008dfc7  mov     [rsp+0C0h+pPrimaryGroup], rdi; pPrimaryGroup
0x18008dfcc  lea     rax, [rbp+57h+dwOwnerSize]
0x18008dfd0  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18008dfd5  mov     rdx, r12; pAbsoluteSecurityDescriptor
0x18008dfd8  mov     [rsp+0C0h+pOwner], rsi; pOwner
0x18008dfdd  lea     rax, [rbp+57h+dwSaclSize]
0x18008dfe1  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18008dfe6  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18008dfe9  lea     rax, [rbp+57h+dwDaclSize]
0x18008dfed  mov     [rsp+0C0h+pSacl], r14; pSacl
0x18008dff2  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18008dff7  call    cs:__imp_MakeAbsoluteSD
0x18008dffe  nop     dword ptr [rax+rax+00h]
0x18008e003  test    eax, eax
0x18008e005  jz      loc_18008E101
0x18008e00b  mov     [rsp+0C0h+lpdwOwnerSize], rbx; pReserved3
0x18008e010  lea     eax, [rbx+2]
0x18008e013  mov     dword ptr [rsp+0C0h+pOwner], ebx; dwCapabilities
0x18008e017  xor     r9d, r9d; pReserved1
0x18008e01a  mov     [rsp+0C0h+lpdwSaclSize], rbx; pAuthList
0x18008e01f  xor     r8d, r8d; asAuthSvc
0x18008e022  mov     dword ptr [rsp+0C0h+pSacl], eax; dwImpLevel
0x18008e026  or      edx, 0FFFFFFFFh; cAuthSvc
0x18008e029  mov     rcx, r12; pSecDesc
0x18008e02c  mov     dword ptr [rsp+0C0h+lpdwDaclSize], eax; dwAuthnLevel
0x18008e030  call    cs:__imp_CoInitializeSecurity
0x18008e037  nop     dword ptr [rax+rax+00h]
0x18008e03c  mov     ebx, eax
0x18008e03e  mov     eax, 80000000h
0x18008e043  lea     ecx, [rbx+rax]
0x18008e046  test    eax, ecx
0x18008e048  jnz     short loc_18008E07A
0x18008e04a  cmp     ebx, 80010119h
0x18008e050  jz      short loc_18008E07A
0x18008e052  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e059  lea     rax, WPP_GLOBAL_Control
0x18008e060  cmp     rcx, rax
0x18008e063  jz      loc_18008E116
0x18008e069  test    byte ptr [rcx+1Ch], 10h
0x18008e06d  jz      loc_18008E116
0x18008e073  mov     edx, 0Ch
0x18008e078  jmp     short loc_18008E0E5
0x18008e07a  movups  xmm0, cs:xmmword_1800E7078
0x18008e081  lea     rax, Annotation
0x18008e088  mov     dword ptr [rsp+0C0h+pOwner], 0
0x18008e090  mov     [rsp+0C0h+lpdwSaclSize], rax
0x18008e095  lea     r8, aDhcpJetWriter; "Dhcp Jet Writer"
0x18008e09c  mov     [rsp+0C0h+pSacl], rax
0x18008e0a1  lea     rdx, [rbp+57h+var_50]
0x18008e0a5  mov     r9b, 1
0x18008e0a8  mov     byte ptr [rsp+0C0h+lpdwDaclSize], 0
0x18008e0ad  lea     rcx, off_1800F9870
0x18008e0b4  movdqu  [rbp+57h+var_50], xmm0
0x18008e0b9  call    cs:__imp_?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z; CVssJetWriter::Initialize(_GUID,ushort const *,bool,bool,ushort const *,ushort const *,ulong)
0x18008e0c0  nop     dword ptr [rax+rax+00h]
0x18008e0c5  mov     ebx, eax
0x18008e0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e0ce  lea     rax, WPP_GLOBAL_Control
0x18008e0d5  cmp     rcx, rax
0x18008e0d8  jz      short loc_18008E116
0x18008e0da  test    byte ptr [rcx+1Ch], 40h
0x18008e0de  jz      short loc_18008E116
0x18008e0e0  mov     edx, 0Dh
0x18008e0e5  mov     rcx, [rcx+10h]
0x18008e0e9  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008e0f0  mov     r9d, ebx
0x18008e0f3  call    WPP_SF_D
0x18008e0f8  jmp     short loc_18008E116
0x18008e0fa  mov     ebx, 8007000Eh
0x18008e0ff  jmp     short loc_18008E116
0x18008e101  call    cs:__imp_GetLastError
0x18008e108  nop     dword ptr [rax+rax+00h]
0x18008e10d  mov     ebx, eax
0x18008e10f  test    eax, eax
0x18008e111  jle     short loc_18008E116
0x18008e113  movzx   ebx, ax
0x18008e116  test    r13, r13
0x18008e119  jz      short loc_18008E12A
0x18008e11b  mov     rcx, r13; hMem
0x18008e11e  call    cs:__imp_LocalFree
0x18008e125  nop     dword ptr [rax+rax+00h]
0x18008e12a  test    r12, r12
0x18008e12d  jz      short loc_18008E13E
0x18008e12f  mov     rcx, r12; hMem
0x18008e132  call    cs:__imp_LocalFree
0x18008e139  nop     dword ptr [rax+rax+00h]
0x18008e13e  test    r15, r15
0x18008e141  jz      short loc_18008E152
0x18008e143  mov     rcx, r15; hMem
0x18008e146  call    cs:__imp_LocalFree
0x18008e14d  nop     dword ptr [rax+rax+00h]
0x18008e152  test    r14, r14
0x18008e155  jz      short loc_18008E166
0x18008e157  mov     rcx, r14; hMem
0x18008e15a  call    cs:__imp_LocalFree
0x18008e161  nop     dword ptr [rax+rax+00h]
0x18008e166  test    rsi, rsi
0x18008e169  jz      short loc_18008E17A
0x18008e16b  mov     rcx, rsi; hMem
0x18008e16e  call    cs:__imp_LocalFree
0x18008e175  nop     dword ptr [rax+rax+00h]
0x18008e17a  test    rdi, rdi
0x18008e17d  jz      short loc_18008E1A5
0x18008e17f  mov     rcx, rdi; hMem
0x18008e182  call    cs:__imp_LocalFree
0x18008e189  nop     dword ptr [rax+rax+00h]
0x18008e18e  jmp     short loc_18008E1A5
0x18008e190  call    cs:__imp_GetLastError
0x18008e197  nop     dword ptr [rax+rax+00h]
0x18008e19c  mov     ebx, eax
0x18008e19e  test    eax, eax
0x18008e1a0  jle     short loc_18008E1A5
0x18008e1a2  movzx   ebx, ax
0x18008e1a5  movzx   eax, bx
0x18008e1a8  add     rsp, 88h
0x18008e1af  pop     r15
0x18008e1b1  pop     r14
0x18008e1b3  pop     r13
0x18008e1b5  pop     r12
0x18008e1b7  pop     rdi
0x18008e1b8  pop     rsi
0x18008e1b9  pop     rbx
0x18008e1ba  pop     rbp
0x18008e1bb  retn
```
