# DhcpWriterInit

- ea: `0x18008dc8c`
- end: `0x18008e091`
- name: `DhcpWriterInit`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000df98`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18008dc8c`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x18008dddc`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008dece`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008dddc`
- `ADVAPI32!MakeAbsoluteSD` at `0x18008dece`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008dd83`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008dd83`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18008df8d`
- `VSSAPI!?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z` at `0x18008df8d`
- `KERNEL32!LocalAlloc` at `0x18008de02`
- `KERNEL32!LocalAlloc` at `0x18008de16`
- `KERNEL32!LocalAlloc` at `0x18008de2a`
- `KERNEL32!LocalAlloc` at `0x18008de3e`
- `KERNEL32!LocalAlloc` at `0x18008de52`
- `KERNEL32!LocalAlloc` at `0x18008de02`
- `KERNEL32!LocalAlloc` at `0x18008de16`
- `KERNEL32!LocalAlloc` at `0x18008de2a`
- `KERNEL32!LocalAlloc` at `0x18008de3e`
- `KERNEL32!LocalAlloc` at `0x18008de52`
- `KERNEL32!GetLastError` at `0x18008dde8`
- `KERNEL32!GetLastError` at `0x18008dfd5`
- `KERNEL32!GetLastError` at `0x18008e064`
- `KERNEL32!GetLastError` at `0x18008dde8`
- `KERNEL32!GetLastError` at `0x18008dfd5`
- `KERNEL32!GetLastError` at `0x18008e064`
- `KERNEL32!LocalFree` at `0x18008dff2`
- `KERNEL32!LocalFree` at `0x18008e006`
- `KERNEL32!LocalFree` at `0x18008e01a`
- `KERNEL32!LocalFree` at `0x18008e02e`
- `KERNEL32!LocalFree` at `0x18008e042`
- `KERNEL32!LocalFree` at `0x18008e056`
- `KERNEL32!LocalFree` at `0x18008dff2`
- `KERNEL32!LocalFree` at `0x18008e006`
- `KERNEL32!LocalFree` at `0x18008e01a`
- `KERNEL32!LocalFree` at `0x18008e02e`
- `KERNEL32!LocalFree` at `0x18008e042`
- `KERNEL32!LocalFree` at `0x18008e056`
- `ole32!CoInitializeSecurity` at `0x18008df07`
- `ole32!CoInitializeSecurity` at `0x18008df07`
- `ole32!CoInitializeEx` at `0x18008dcf4`
- `ole32!CoInitializeEx` at `0x18008dcf4`

## string_xrefs

- `0x18008df69`: `Dhcp Jet Writer`

## pseudocode

```c
__int64 DhcpWriterInit()
{
  HLOCAL v0; // r13
  struct _ACL *v1; // r12
  struct _ACL *pSacl; // r15
  HLOCAL pOwner; // r14
  void *v4; // rsi
  unsigned int v5; // ebx
  PSECURITY_DESCRIPTOR v6; // rdi
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
  dword_1800FB094 = CoInitializeEx(0, 0);
  LOWORD(v5) = dword_1800FB094;
  if ( (int)(dword_1800FB094 + 0x80000000) >= 0 && dword_1800FB094 != -2147417850 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids,
        (unsigned int)dword_1800FB094);
      LOWORD(v5) = dword_1800FB094;
    }
    return (unsigned __int16)v5;
  }
  SecurityDescriptor = 0;
  dword_1800FB2B0 = dword_1800FB094 != -2147417850;
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
          v15 = xmmword_1800E50C8;
          v5 = CVssJetWriter::Initialize(
                 (CVssJetWriter *)&off_1800F7870,
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
0x18008dc8c  push    rbp
0x18008dc8e  push    rbx
0x18008dc8f  push    rsi
0x18008dc90  push    rdi
0x18008dc91  push    r12
0x18008dc93  push    r13
0x18008dc95  push    r14
0x18008dc97  push    r15
0x18008dc99  lea     rbp, [rsp-1Fh]
0x18008dc9e  sub     rsp, 88h
0x18008dca5  xor     edi, edi
0x18008dca7  mov     r13d, edi
0x18008dcaa  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], edi
0x18008dcad  mov     r12d, edi
0x18008dcb0  mov     [rbp+57h+dwDaclSize], edi
0x18008dcb3  mov     r15d, edi
0x18008dcb6  mov     [rbp+57h+dwSaclSize], edi
0x18008dcb9  mov     r14d, edi
0x18008dcbc  mov     [rbp+57h+dwOwnerSize], edi
0x18008dcbf  mov     esi, edi
0x18008dcc1  mov     [rbp+57h+dwPrimaryGroupSize], edi
0x18008dcc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dccb  lea     rax, WPP_GLOBAL_Control
0x18008dcd2  cmp     rcx, rax
0x18008dcd5  jz      short loc_18008DCF0
0x18008dcd7  test    byte ptr [rcx+1Ch], 40h
0x18008dcdb  jz      short loc_18008DCF0
0x18008dcdd  mov     rcx, [rcx+10h]
0x18008dce1  lea     edx, [rdi+0Ah]
0x18008dce4  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008dceb  call    WPP_SF_
0x18008dcf0  xor     edx, edx; dwCoInit
0x18008dcf2  xor     ecx, ecx; pvReserved
0x18008dcf4  call    cs:__imp_CoInitializeEx
0x18008dcfb  nop     dword ptr [rax+rax+00h]
0x18008dd00  mov     edx, 80000000h
0x18008dd05  mov     cs:dword_1800FB094, eax
0x18008dd0b  mov     ebx, eax
0x18008dd0d  mov     ecx, 80010106h
0x18008dd12  add     eax, edx
0x18008dd14  test    edx, eax
0x18008dd16  jnz     short loc_18008DD60
0x18008dd18  cmp     ebx, ecx
0x18008dd1a  jz      short loc_18008DD60
0x18008dd1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dd23  lea     rax, WPP_GLOBAL_Control
0x18008dd2a  cmp     rcx, rax
0x18008dd2d  jz      loc_18008E079
0x18008dd33  test    byte ptr [rcx+1Ch], 10h
0x18008dd37  jz      loc_18008E079
0x18008dd3d  mov     rcx, [rcx+10h]
0x18008dd41  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008dd48  mov     edx, 0Bh
0x18008dd4d  mov     r9d, ebx
0x18008dd50  call    WPP_SF_D
0x18008dd55  mov     ebx, cs:dword_1800FB094
0x18008dd5b  jmp     loc_18008E079
0x18008dd60  cmp     ebx, ecx
0x18008dd62  mov     [rbp+57h+SecurityDescriptor], rdi
0x18008dd66  mov     eax, edi
0x18008dd68  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18008dd6c  setnz   al
0x18008dd6f  lea     rcx, aOBagBadA0x3IuA; "O:BAG:BAD:(A;;0x3;;;IU)(A;;0x3;;;SY)(A;"...
0x18008dd76  xor     r9d, r9d; SecurityDescriptorSize
0x18008dd79  mov     cs:dword_1800FB2B0, eax
0x18008dd7f  lea     edx, [r9+1]; StringSDRevision
0x18008dd83  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008dd8a  nop     dword ptr [rax+rax+00h]
0x18008dd8f  test    eax, eax
0x18008dd91  jz      loc_18008E064
0x18008dd97  mov     rdi, [rbp+57h+SecurityDescriptor]
0x18008dd9b  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18008dd9f  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18008dda4  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18008dda8  xor     ebx, ebx
0x18008ddaa  lea     rax, [rbp+57h+dwOwnerSize]
0x18008ddae  mov     [rsp+0C0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18008ddb3  xor     r9d, r9d; pDacl
0x18008ddb6  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18008ddbb  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18008ddbd  mov     [rsp+0C0h+pOwner], rbx; pOwner
0x18008ddc2  lea     rax, [rbp+57h+dwSaclSize]
0x18008ddc6  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18008ddcb  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x18008ddce  lea     rax, [rbp+57h+dwDaclSize]
0x18008ddd2  mov     [rsp+0C0h+pSacl], rbx; pSacl
0x18008ddd7  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18008dddc  call    cs:__imp_MakeAbsoluteSD
0x18008dde3  nop     dword ptr [rax+rax+00h]
0x18008dde8  call    cs:__imp_GetLastError
0x18008ddef  nop     dword ptr [rax+rax+00h]
0x18008ddf4  cmp     eax, 7Ah ; 'z'
0x18008ddf7  jnz     loc_18008DFD5
0x18008ddfd  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x18008de00  xor     ecx, ecx; uFlags
0x18008de02  call    cs:__imp_LocalAlloc
0x18008de09  nop     dword ptr [rax+rax+00h]
0x18008de0e  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x18008de11  xor     ecx, ecx; uFlags
0x18008de13  mov     r13, rax
0x18008de16  call    cs:__imp_LocalAlloc
0x18008de1d  nop     dword ptr [rax+rax+00h]
0x18008de22  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x18008de25  xor     ecx, ecx; uFlags
0x18008de27  mov     r12, rax
0x18008de2a  call    cs:__imp_LocalAlloc
0x18008de31  nop     dword ptr [rax+rax+00h]
0x18008de36  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x18008de39  xor     ecx, ecx; uFlags
0x18008de3b  mov     r15, rax
0x18008de3e  call    cs:__imp_LocalAlloc
0x18008de45  nop     dword ptr [rax+rax+00h]
0x18008de4a  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x18008de4d  xor     ecx, ecx; uFlags
0x18008de4f  mov     r14, rax
0x18008de52  call    cs:__imp_LocalAlloc
0x18008de59  nop     dword ptr [rax+rax+00h]
0x18008de5e  mov     rsi, rax
0x18008de61  test    r13, r13
0x18008de64  jz      loc_18008DFCE
0x18008de6a  test    r12, r12
0x18008de6d  jz      loc_18008DFCE
0x18008de73  test    r15, r15
0x18008de76  jz      loc_18008DFCE
0x18008de7c  test    r14, r14
0x18008de7f  jz      loc_18008DFCE
0x18008de85  test    rax, rax
0x18008de88  jz      loc_18008DFCE
0x18008de8e  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18008de92  mov     r9, r12; pDacl
0x18008de95  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18008de9a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18008de9e  mov     [rsp+0C0h+pPrimaryGroup], rsi; pPrimaryGroup
0x18008dea3  lea     rax, [rbp+57h+dwOwnerSize]
0x18008dea7  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18008deac  mov     rdx, r13; pAbsoluteSecurityDescriptor
0x18008deaf  mov     [rsp+0C0h+pOwner], r14; pOwner
0x18008deb4  lea     rax, [rbp+57h+dwSaclSize]
0x18008deb8  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18008debd  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x18008dec0  lea     rax, [rbp+57h+dwDaclSize]
0x18008dec4  mov     [rsp+0C0h+pSacl], r15; pSacl
0x18008dec9  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18008dece  call    cs:__imp_MakeAbsoluteSD
0x18008ded5  nop     dword ptr [rax+rax+00h]
0x18008deda  test    eax, eax
0x18008dedc  jz      loc_18008DFD5
0x18008dee2  mov     [rsp+0C0h+lpdwOwnerSize], rbx; pReserved3
0x18008dee7  lea     eax, [rbx+2]
0x18008deea  mov     dword ptr [rsp+0C0h+pOwner], ebx; dwCapabilities
0x18008deee  xor     r9d, r9d; pReserved1
0x18008def1  mov     [rsp+0C0h+lpdwSaclSize], rbx; pAuthList
0x18008def6  xor     r8d, r8d; asAuthSvc
0x18008def9  mov     dword ptr [rsp+0C0h+pSacl], eax; dwImpLevel
0x18008defd  or      edx, 0FFFFFFFFh; cAuthSvc
0x18008df00  mov     rcx, r13; pSecDesc
0x18008df03  mov     dword ptr [rsp+0C0h+lpdwDaclSize], eax; dwAuthnLevel
0x18008df07  call    cs:__imp_CoInitializeSecurity
0x18008df0e  nop     dword ptr [rax+rax+00h]
0x18008df13  mov     ebx, eax
0x18008df15  mov     eax, 80000000h
0x18008df1a  lea     ecx, [rbx+rax]
0x18008df1d  test    eax, ecx
0x18008df1f  jnz     short loc_18008DF51
0x18008df21  cmp     ebx, 80010119h
0x18008df27  jz      short loc_18008DF51
0x18008df29  mov     rcx, cs:WPP_GLOBAL_Control
0x18008df30  lea     rax, WPP_GLOBAL_Control
0x18008df37  cmp     rcx, rax
0x18008df3a  jz      loc_18008DFEA
0x18008df40  test    byte ptr [rcx+1Ch], 10h
0x18008df44  jz      loc_18008DFEA
0x18008df4a  mov     edx, 0Ch
0x18008df4f  jmp     short loc_18008DFB9
0x18008df51  and     dword ptr [rsp+0C0h+pOwner], 0
0x18008df56  lea     rax, Annotation
0x18008df5d  movups  xmm0, cs:xmmword_1800E50C8
0x18008df64  mov     [rsp+0C0h+lpdwSaclSize], rax
0x18008df69  lea     r8, aDhcpJetWriter; "Dhcp Jet Writer"
0x18008df70  mov     [rsp+0C0h+pSacl], rax
0x18008df75  lea     rdx, [rbp+57h+var_50]
0x18008df79  mov     r9b, 1
0x18008df7c  mov     byte ptr [rsp+0C0h+lpdwDaclSize], 0
0x18008df81  lea     rcx, off_1800F7870
0x18008df88  movdqu  [rbp+57h+var_50], xmm0
0x18008df8d  call    cs:__imp_?Initialize@CVssJetWriter@@QEAAJU_GUID@@PEBG_N211K@Z; CVssJetWriter::Initialize(_GUID,ushort const *,bool,bool,ushort const *,ushort const *,ulong)
0x18008df94  nop     dword ptr [rax+rax+00h]
0x18008df99  mov     ebx, eax
0x18008df9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dfa2  lea     rax, WPP_GLOBAL_Control
0x18008dfa9  cmp     rcx, rax
0x18008dfac  jz      short loc_18008DFEA
0x18008dfae  test    byte ptr [rcx+1Ch], 40h
0x18008dfb2  jz      short loc_18008DFEA
0x18008dfb4  mov     edx, 0Dh
0x18008dfb9  mov     rcx, [rcx+10h]
0x18008dfbd  lea     r8, WPP_4eb29c9c30dd37b82311529fc786cb8c_Traceguids
0x18008dfc4  mov     r9d, ebx
0x18008dfc7  call    WPP_SF_D
0x18008dfcc  jmp     short loc_18008DFEA
0x18008dfce  mov     ebx, 8007000Eh
0x18008dfd3  jmp     short loc_18008DFEA
0x18008dfd5  call    cs:__imp_GetLastError
0x18008dfdc  nop     dword ptr [rax+rax+00h]
0x18008dfe1  mov     ebx, eax
0x18008dfe3  test    eax, eax
0x18008dfe5  jle     short loc_18008DFEA
0x18008dfe7  movzx   ebx, ax
0x18008dfea  test    rdi, rdi
0x18008dfed  jz      short loc_18008DFFE
0x18008dfef  mov     rcx, rdi; hMem
0x18008dff2  call    cs:__imp_LocalFree
0x18008dff9  nop     dword ptr [rax+rax+00h]
0x18008dffe  test    r13, r13
0x18008e001  jz      short loc_18008E012
0x18008e003  mov     rcx, r13; hMem
0x18008e006  call    cs:__imp_LocalFree
0x18008e00d  nop     dword ptr [rax+rax+00h]
0x18008e012  test    r12, r12
0x18008e015  jz      short loc_18008E026
0x18008e017  mov     rcx, r12; hMem
0x18008e01a  call    cs:__imp_LocalFree
0x18008e021  nop     dword ptr [rax+rax+00h]
0x18008e026  test    r15, r15
0x18008e029  jz      short loc_18008E03A
0x18008e02b  mov     rcx, r15; hMem
0x18008e02e  call    cs:__imp_LocalFree
0x18008e035  nop     dword ptr [rax+rax+00h]
0x18008e03a  test    r14, r14
0x18008e03d  jz      short loc_18008E04E
0x18008e03f  mov     rcx, r14; hMem
0x18008e042  call    cs:__imp_LocalFree
0x18008e049  nop     dword ptr [rax+rax+00h]
0x18008e04e  test    rsi, rsi
0x18008e051  jz      short loc_18008E079
0x18008e053  mov     rcx, rsi; hMem
0x18008e056  call    cs:__imp_LocalFree
0x18008e05d  nop     dword ptr [rax+rax+00h]
0x18008e062  jmp     short loc_18008E079
0x18008e064  call    cs:__imp_GetLastError
0x18008e06b  nop     dword ptr [rax+rax+00h]
0x18008e070  mov     ebx, eax
0x18008e072  test    eax, eax
0x18008e074  jle     short loc_18008E079
0x18008e076  movzx   ebx, ax
0x18008e079  movzx   eax, bx
0x18008e07c  add     rsp, 88h
0x18008e083  pop     r15
0x18008e085  pop     r14
0x18008e087  pop     r13
0x18008e089  pop     r12
0x18008e08b  pop     rdi
0x18008e08c  pop     rsi
0x18008e08d  pop     rbx
0x18008e08e  pop     rbp
0x18008e08f  retn
```
