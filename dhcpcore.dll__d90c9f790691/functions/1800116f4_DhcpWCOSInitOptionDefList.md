# DhcpWCOSInitOptionDefList

- ea: `0x1800116f4`
- end: `0x180011ef6`
- name: `DhcpWCOSInitOptionDefList`
- size: `2050`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180011454`

## callees

- `0x180005670`
- `0x180006440`
- `0x1800069d0`
- `0x180010e00`
- `0x1800116f4`
- `0x180011efc`
- `0x180018fbc`
- `0x180047e3c`
- `0x18004d1a0`

## string_xrefs

- `0x1800119b8`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpDomain`
- `0x1800119a7`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpDomain`
- `0x180011953`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpNameServer`
- `0x180011942`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\DhcpNameServer`
- `0x180011b19`: `SYSTEM\CurrentControlSet\Services\NetBT\Parameters\DhcpNodeType`
- `0x180011c2b`: `SYSTEM\CurrentControlSet\Services\NetBT\Parameters\DhcpScopeID`
- `0x180011a07`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?\DhcpNameServerList`
- `0x180011d3d`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpRequestOptions`

## pseudocode

```c
__int64 DhcpWCOSInitOptionDefList()
{
  int v0; // esi
  const wchar_t *v1; // rdi
  unsigned int v2; // eax
  int v3; // eax
  int v4; // ebx
  HRESULT v5; // eax
  unsigned int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  int v10; // esi
  const wchar_t *v11; // rdi
  unsigned int v12; // eax
  int v13; // eax
  int v14; // ebx
  HRESULT v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // rax
  BOOL IsWCOSSystem; // eax
  const wchar_t *psz; // rcx
  unsigned int v21; // eax
  BOOL v22; // eax
  const wchar_t *v23; // rcx
  unsigned int v24; // eax
  int v25; // esi
  const wchar_t *v26; // rdi
  unsigned int v27; // eax
  int v28; // eax
  int v29; // ebx
  HRESULT v30; // eax
  _QWORD *v31; // rax
  _QWORD *v32; // rbx
  _QWORD *v33; // rax
  int v34; // esi
  const wchar_t *v35; // rdi
  unsigned int v36; // eax
  int v37; // eax
  int v38; // ebx
  HRESULT v39; // eax
  _QWORD *v40; // rax
  _QWORD *v41; // rbx
  _QWORD *v42; // rax
  int v43; // esi
  const wchar_t *v44; // rdi
  unsigned int v45; // eax
  int v46; // eax
  int v47; // ebx
  HRESULT v48; // eax
  _QWORD *v49; // rax
  _QWORD *v50; // rbx
  _QWORD *v51; // rax
  int v52; // edi
  const wchar_t *v53; // rbx
  const wchar_t *v54; // rcx
  unsigned int v55; // eax
  int v56; // eax
  unsigned int v57; // edi
  _QWORD *v58; // rax
  _QWORD *v59; // rbx
  _QWORD *v60; // rax
  int v61; // edi
  const wchar_t *v62; // rbx
  const wchar_t *v63; // rcx
  unsigned int v64; // eax
  int v65; // eax
  unsigned int v66; // edi
  _QWORD *v67; // rax
  _QWORD *v68; // rbx
  _QWORD *v69; // rax
  int v71; // [rsp+70h] [rbp+30h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp+38h] BYREF

  v71 = 0;
  v0 = 0;
  v1 = L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpSubnetMaskOpt";
  v2 = WxStringCchLengthDWordW(L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpSubnetMaskOpt", 512, &v71);
  v3 = WX_WIN32_FROM_HR(v2);
  v4 = v71;
  while ( v4 && v3 >= 0 )
  {
    pcchLength = 0;
    v1 += (unsigned int)(v4 + 1);
    v71 = 0;
    v0 += 2 * v4 + 2;
    if ( !v1 )
    {
      v5 = -2147024809;
      HIDWORD(pcchLength) = 77;
LABEL_5:
      v4 = v71;
      goto LABEL_9;
    }
    v5 = StringCchLengthW(v1, 0x200u, &pcchLength);
    if ( v5 < 0 )
    {
      HIDWORD(pcchLength) = 81;
      goto LABEL_5;
    }
    v4 = pcchLength;
LABEL_9:
    v3 = WX_WIN32_FROM_HR((unsigned int)v5);
  }
  v6 = v0 + 2;
  v7 = DhcpAlloc(v6 + 64);
  v8 = v7;
  if ( v7 )
  {
    v7[6] = v7 + 8;
    v7[2] = 1;
    v7[3] = 0;
    *((_DWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 14) = 7;
    v7[5] = 0;
    memcpy_0(v7 + 8, L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpSubnetMaskOpt", v6);
    v9 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v8 = &DhcpGlobalOptionDefList;
      v8[1] = v9;
      *v9 = v8;
      off_1800610C0[0] = (_UNKNOWN **)v8;
      goto LABEL_16;
    }
LABEL_105:
    __fastfail(3u);
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 19, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_16:
  v71 = 0;
  v10 = 0;
  v11 = L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpDefaultGateway";
  v12 = WxStringCchLengthDWordW(L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpDefaultGateway", 512, &v71);
  v13 = WX_WIN32_FROM_HR(v12);
  v14 = v71;
  while ( 2 )
  {
    if ( v14 && v13 >= 0 )
    {
      pcchLength = 0;
      v11 += (unsigned int)(v14 + 1);
      v71 = 0;
      v10 += 2 * v14 + 2;
      if ( !v11 )
      {
        v15 = -2147024809;
        HIDWORD(pcchLength) = 77;
        goto LABEL_20;
      }
      v15 = StringCchLengthW(v11, 0x200u, &pcchLength);
      if ( v15 >= 0 )
      {
        v14 = pcchLength;
      }
      else
      {
        HIDWORD(pcchLength) = 81;
LABEL_20:
        v14 = v71;
      }
      v13 = WX_WIN32_FROM_HR((unsigned int)v15);
      continue;
    }
    break;
  }
  v16 = DhcpAlloc((unsigned int)(v10 + 66));
  v17 = v16;
  if ( v16 )
  {
    v16[6] = v16 + 8;
    v16[2] = 3;
    v16[3] = 0;
    *((_DWORD *)v16 + 8) = 0;
    *((_DWORD *)v16 + 14) = 7;
    v16[5] = 0;
    memcpy_0(v16 + 8, L"OSDATA\\Networking\\Dhcp\\Client4\\?\\DhcpDefaultGateway", (unsigned int)(v10 + 2));
    v18 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v17 = &DhcpGlobalOptionDefList;
      v17[1] = v18;
      *v18 = v17;
      off_1800610C0[0] = (_UNKNOWN **)v17;
      goto LABEL_31;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 20, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_31:
  IsWCOSSystem = DhcpIsWCOSSystem();
  psz = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpNameServer";
  if ( !IsWCOSSystem )
    psz = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpNameServer";
  v21 = DhcpAddOptionDef((__int64)psz, 6, 0, 0, 0, 0, psz, 3);
  if ( v21 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 21, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v21);
  v22 = DhcpIsWCOSSystem();
  v23 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpDomain";
  if ( !v22 )
    v23 = L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters\\DhcpDomain";
  v24 = DhcpAddOptionDef((__int64)v23, 15, 0, 0, 0, 0, v23, 1);
  if ( v24 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 22, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v24);
  v71 = 0;
  v25 = 0;
  v26 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList";
  v27 = WxStringCchLengthDWordW(
          L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList",
          512,
          &v71);
  v28 = WX_WIN32_FROM_HR(v27);
  v29 = v71;
  while ( 2 )
  {
    if ( v29 && v28 >= 0 )
    {
      pcchLength = 0;
      v26 += (unsigned int)(v29 + 1);
      v71 = 0;
      v25 += 2 * v29 + 2;
      if ( !v26 )
      {
        v30 = -2147024809;
        HIDWORD(pcchLength) = 77;
        goto LABEL_45;
      }
      v30 = StringCchLengthW(v26, 0x200u, &pcchLength);
      if ( v30 >= 0 )
      {
        v29 = pcchLength;
      }
      else
      {
        HIDWORD(pcchLength) = 81;
LABEL_45:
        v29 = v71;
      }
      v28 = WX_WIN32_FROM_HR((unsigned int)v30);
      continue;
    }
    break;
  }
  v31 = DhcpAlloc((unsigned int)(v25 + 66));
  v32 = v31;
  if ( v31 )
  {
    v31[6] = v31 + 8;
    v31[2] = 44;
    v31[3] = 0;
    *((_DWORD *)v31 + 8) = 0;
    *((_DWORD *)v31 + 14) = 3;
    v31[5] = 0;
    memcpy_0(
      v31 + 8,
      L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?\\DhcpNameServerList",
      (unsigned int)(v25 + 2));
    v33 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v32 = &DhcpGlobalOptionDefList;
      v32[1] = v33;
      *v33 = v32;
      off_1800610C0[0] = (_UNKNOWN **)v32;
      goto LABEL_56;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 23, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_56:
  v71 = 0;
  v34 = 0;
  v35 = L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpNodeType";
  v36 = WxStringCchLengthDWordW(L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpNodeType", 512, &v71);
  v37 = WX_WIN32_FROM_HR(v36);
  v38 = v71;
  while ( 2 )
  {
    if ( v38 && v37 >= 0 )
    {
      pcchLength = 0;
      v35 += (unsigned int)(v38 + 1);
      v71 = 0;
      v34 += 2 * v38 + 2;
      if ( !v35 )
      {
        v39 = -2147024809;
        HIDWORD(pcchLength) = 77;
        goto LABEL_60;
      }
      v39 = StringCchLengthW(v35, 0x200u, &pcchLength);
      if ( v39 >= 0 )
      {
        v38 = pcchLength;
      }
      else
      {
        HIDWORD(pcchLength) = 81;
LABEL_60:
        v38 = v71;
      }
      v37 = WX_WIN32_FROM_HR((unsigned int)v39);
      continue;
    }
    break;
  }
  v40 = DhcpAlloc((unsigned int)(v34 + 66));
  v41 = v40;
  if ( v40 )
  {
    v40[6] = v40 + 8;
    v40[2] = 46;
    v40[3] = 0;
    *((_DWORD *)v40 + 8) = 0;
    *((_DWORD *)v40 + 14) = 4;
    v40[5] = 0;
    memcpy_0(v40 + 8, L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpNodeType", (unsigned int)(v34 + 2));
    v42 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v41 = &DhcpGlobalOptionDefList;
      v41[1] = v42;
      *v42 = v41;
      off_1800610C0[0] = (_UNKNOWN **)v41;
      goto LABEL_71;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 24, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_71:
  v71 = 0;
  v43 = 0;
  v44 = L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpScopeID";
  v45 = WxStringCchLengthDWordW(L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpScopeID", 512, &v71);
  v46 = WX_WIN32_FROM_HR(v45);
  v47 = v71;
  while ( 2 )
  {
    if ( v47 && v46 >= 0 )
    {
      pcchLength = 0;
      v44 += (unsigned int)(v47 + 1);
      v71 = 0;
      v43 += 2 * v47 + 2;
      if ( !v44 )
      {
        v48 = -2147024809;
        HIDWORD(pcchLength) = 77;
        goto LABEL_75;
      }
      v48 = StringCchLengthW(v44, 0x200u, &pcchLength);
      if ( v48 >= 0 )
      {
        v47 = pcchLength;
      }
      else
      {
        HIDWORD(pcchLength) = 81;
LABEL_75:
        v47 = v71;
      }
      v46 = WX_WIN32_FROM_HR((unsigned int)v48);
      continue;
    }
    break;
  }
  v49 = DhcpAlloc((unsigned int)(v43 + 66));
  v50 = v49;
  if ( v49 )
  {
    v49[6] = v49 + 8;
    v49[2] = 47;
    v49[3] = 0;
    *((_DWORD *)v49 + 8) = 0;
    *((_DWORD *)v49 + 14) = 3;
    v49[5] = 0;
    memcpy_0(v49 + 8, L"SYSTEM\\CurrentControlSet\\Services\\NetBT\\Parameters\\DhcpScopeID", (unsigned int)(v43 + 2));
    v51 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v50 = &DhcpGlobalOptionDefList;
      v50[1] = v51;
      *v51 = v50;
      off_1800610C0[0] = (_UNKNOWN **)v50;
      goto LABEL_86;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 25, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_86:
  v52 = 0;
  v53 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  v54 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  while ( 1 )
  {
    v71 = 0;
    v55 = WxStringCchLengthDWordW(v54, 512, &v71);
    v56 = WX_WIN32_FROM_HR(v55);
    if ( !v71 || v56 < 0 )
      break;
    v53 += (unsigned int)(v71 + 1);
    v54 = v53;
    v52 += 2 * v71 + 2;
  }
  v57 = v52 + 2;
  v58 = DhcpAlloc(v57 + 64);
  v59 = v58;
  if ( v58 )
  {
    v58[5] = v58 + 8;
    v58[2] = 55;
    v58[3] = 0;
    *((_DWORD *)v58 + 8) = 0;
    *((_DWORD *)v58 + 14) = 0;
    memcpy_0(v58 + 8, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions", v57);
    v59[6] = 0;
    v60 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v59 = &DhcpGlobalOptionDefList;
      v59[1] = v60;
      *v60 = v59;
      off_1800610C0[0] = (_UNKNOWN **)v59;
      goto LABEL_95;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 26, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
LABEL_95:
  v61 = 0;
  v62 = L"OSDATA\\Networking\\Dhcp\\Client4\\?\\SoHRequest";
  v63 = L"OSDATA\\Networking\\Dhcp\\Client4\\?\\SoHRequest";
  while ( 1 )
  {
    v71 = 0;
    v64 = WxStringCchLengthDWordW(v63, 512, &v71);
    v65 = WX_WIN32_FROM_HR(v64);
    if ( !v71 || v65 < 0 )
      break;
    v62 += (unsigned int)(v71 + 1);
    v63 = v62;
    v61 += 2 * v71 + 2;
  }
  v66 = v61 + 2;
  v67 = DhcpAlloc(v66 + 64);
  v68 = v67;
  if ( v67 )
  {
    v67[5] = v67 + 8;
    *((_DWORD *)v67 + 4) = 220;
    *((_DWORD *)v67 + 5) = 1;
    v67[3] = 0;
    *((_DWORD *)v67 + 8) = 0;
    *((_DWORD *)v67 + 14) = 3;
    memcpy_0(v67 + 8, L"OSDATA\\Networking\\Dhcp\\Client4\\?\\SoHRequest", v66);
    v68[6] = 0;
    v69 = off_1800610C0[0];
    if ( *(_UNKNOWN ***)off_1800610C0[0] == &DhcpGlobalOptionDefList )
    {
      *v68 = &DhcpGlobalOptionDefList;
      v68[1] = v69;
      *v69 = v68;
      off_1800610C0[0] = (_UNKNOWN **)v68;
      return 0;
    }
    goto LABEL_105;
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 27, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, 8);
  return 0;
}

```

## disassembly

```asm
0x1800116f4  mov     [rsp-28h+arg_10], rbx
0x1800116f9  mov     [rsp-28h+arg_18], rsi
0x1800116fe  push    rbp
0x1800116ff  push    rdi
0x180011700  push    r12
0x180011702  push    r14
0x180011704  push    r15
0x180011706  mov     rbp, rsp
0x180011709  sub     rsp, 40h
0x18001170d  lea     r12, aOsdataNetworki_5; "OSDATA\\Networking\\Dhcp\\Client4\\?\\D"...
0x180011714  xor     r14d, r14d
0x180011717  mov     r15d, 200h
0x18001171d  mov     [rbp+arg_0], r14d
0x180011721  mov     edx, r15d
0x180011724  lea     r8, [rbp+arg_0]
0x180011728  mov     rcx, r12
0x18001172b  mov     esi, r14d
0x18001172e  mov     rdi, r12
0x180011731  call    WxStringCchLengthDWordW
0x180011736  mov     ecx, eax
0x180011738  call    WX_WIN32_FROM_HR
0x18001173d  mov     ebx, [rbp+arg_0]
0x180011740  jmp     short loc_18001179B
0x180011742  test    eax, eax
0x180011744  js      short loc_18001179F
0x180011746  mov     dword ptr [rbp+pcchLength+4], r14d
0x18001174a  lea     eax, [rbx+1]
0x18001174d  lea     esi, [rsi+rbx*2]
0x180011750  mov     [rbp+pcchLength], r14
0x180011754  lea     rdi, [rdi+rax*2]
0x180011758  mov     [rbp+arg_0], r14d
0x18001175c  add     esi, 2
0x18001175f  test    rdi, rdi
0x180011762  jnz     short loc_180011775
0x180011764  mov     eax, 80070057h
0x180011769  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x180011770  mov     ebx, [rbp+arg_0]
0x180011773  jmp     short loc_180011794
0x180011775  lea     r8, [rbp+pcchLength]; pcchLength
0x180011779  mov     rdx, r15; cchMax
0x18001177c  mov     rcx, rdi; psz
0x18001177f  call    StringCchLengthW
0x180011784  test    eax, eax
0x180011786  jns     short loc_180011791
0x180011788  mov     dword ptr [rbp+pcchLength+4], 51h ; 'Q'
0x18001178f  jmp     short loc_180011770
0x180011791  mov     ebx, dword ptr [rbp+pcchLength]
0x180011794  mov     ecx, eax
0x180011796  call    WX_WIN32_FROM_HR
0x18001179b  test    ebx, ebx
0x18001179d  jnz     short loc_180011742
0x18001179f  add     esi, 2
0x1800117a2  lea     ecx, [rsi+40h]
0x1800117a5  call    DhcpAlloc
0x1800117aa  lea     r15, DhcpGlobalOptionDefList
0x1800117b1  mov     rbx, rax
0x1800117b4  test    rax, rax
0x1800117b7  jnz     short loc_1800117DC
0x1800117b9  test    byte ptr cs:xmmword_1800616A0, 2
0x1800117c0  jz      short loc_18001182B
0x1800117c2  lea     edx, [rax+13h]
0x1800117c5  mov     ecx, 401h
0x1800117ca  lea     r9d, [rax+8]
0x1800117ce  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800117d5  call    WPP_SF_D
0x1800117da  jmp     short loc_18001182B
0x1800117dc  lea     rcx, [rax+40h]; void *
0x1800117e0  mov     r8d, esi; Size
0x1800117e3  mov     rdx, r12; Src
0x1800117e6  mov     [rax+30h], rcx
0x1800117ea  mov     qword ptr [rax+10h], 1
0x1800117f2  mov     [rax+18h], r14
0x1800117f6  mov     [rax+20h], r14d
0x1800117fa  mov     dword ptr [rax+38h], 7
0x180011801  mov     [rax+28h], r14
0x180011805  call    memcpy_0
0x18001180a  mov     rax, cs:off_1800610C0
0x180011811  cmp     [rax], r15
0x180011814  jnz     loc_180011EEF
0x18001181a  mov     [rbx], r15
0x18001181d  mov     [rbx+8], rax
0x180011821  mov     [rax], rbx
0x180011824  mov     cs:off_1800610C0, rbx
0x18001182b  lea     r12, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client4\\?\\D"...
0x180011832  mov     [rbp+arg_0], r14d
0x180011836  mov     rcx, r12
0x180011839  lea     r8, [rbp+arg_0]
0x18001183d  mov     edx, 200h
0x180011842  mov     esi, r14d
0x180011845  mov     rdi, r12
0x180011848  call    WxStringCchLengthDWordW
0x18001184d  mov     ecx, eax
0x18001184f  call    WX_WIN32_FROM_HR
0x180011854  mov     ebx, [rbp+arg_0]
0x180011857  jmp     short loc_1800118B4
0x180011859  test    eax, eax
0x18001185b  js      short loc_1800118B8
0x18001185d  mov     dword ptr [rbp+pcchLength+4], r14d
0x180011861  lea     eax, [rbx+1]
0x180011864  lea     esi, [rsi+rbx*2]
0x180011867  mov     [rbp+pcchLength], r14
0x18001186b  lea     rdi, [rdi+rax*2]
0x18001186f  mov     [rbp+arg_0], r14d
0x180011873  add     esi, 2
0x180011876  test    rdi, rdi
0x180011879  jnz     short loc_18001188C
0x18001187b  mov     eax, 80070057h
0x180011880  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x180011887  mov     ebx, [rbp+arg_0]
0x18001188a  jmp     short loc_1800118AD
0x18001188c  lea     r8, [rbp+pcchLength]; pcchLength
0x180011890  mov     edx, 200h; cchMax
0x180011895  mov     rcx, rdi; psz
0x180011898  call    StringCchLengthW
0x18001189d  test    eax, eax
0x18001189f  jns     short loc_1800118AA
0x1800118a1  mov     dword ptr [rbp+pcchLength+4], 51h ; 'Q'
0x1800118a8  jmp     short loc_180011887
0x1800118aa  mov     ebx, dword ptr [rbp+pcchLength]
0x1800118ad  mov     ecx, eax
0x1800118af  call    WX_WIN32_FROM_HR
0x1800118b4  test    ebx, ebx
0x1800118b6  jnz     short loc_180011859
0x1800118b8  lea     edi, [rsi+2]
0x1800118bb  lea     ecx, [rdi+40h]
0x1800118be  call    DhcpAlloc
0x1800118c3  mov     rbx, rax
0x1800118c6  test    rax, rax
0x1800118c9  jnz     short loc_1800118EE
0x1800118cb  test    byte ptr cs:xmmword_1800616A0, 2
0x1800118d2  jz      short loc_18001193D
0x1800118d4  lea     edx, [rax+14h]
0x1800118d7  mov     ecx, 401h
0x1800118dc  lea     r9d, [rax+8]
0x1800118e0  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800118e7  call    WPP_SF_D
0x1800118ec  jmp     short loc_18001193D
0x1800118ee  lea     rcx, [rax+40h]; void *
0x1800118f2  mov     r8d, edi; Size
0x1800118f5  mov     rdx, r12; Src
0x1800118f8  mov     [rax+30h], rcx
0x1800118fc  mov     qword ptr [rax+10h], 3
0x180011904  mov     [rax+18h], r14
0x180011908  mov     [rax+20h], r14d
0x18001190c  mov     dword ptr [rax+38h], 7
0x180011913  mov     [rax+28h], r14
0x180011917  call    memcpy_0
0x18001191c  mov     rax, cs:off_1800610C0
0x180011923  cmp     [rax], r15
0x180011926  jnz     loc_180011EEF
0x18001192c  mov     [rbx], r15
0x18001192f  mov     [rbx+8], rax
0x180011933  mov     [rax], rbx
0x180011936  mov     cs:off_1800610C0, rbx
0x18001193d  call    DhcpIsWCOSSystem
0x180011942  lea     rdx, aSystemCurrentc_13; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180011949  mov     [rsp+40h+var_8], 3; int
0x180011951  test    eax, eax
0x180011953  lea     rcx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x18001195a  cmovz   rcx, rdx; int
0x18001195e  xor     r9d, r9d; int
0x180011961  mov     [rsp+40h+psz], rcx; psz
0x180011966  xor     r8d, r8d; int
0x180011969  mov     [rsp+40h+Src], r14; Src
0x18001196e  mov     [rsp+40h+var_20], r14d; int
0x180011973  lea     edx, [r9+6]; int
0x180011977  call    DhcpAddOptionDef
0x18001197c  test    eax, eax
0x18001197e  jz      short loc_1800119A2
0x180011980  test    byte ptr cs:xmmword_1800616A0, 2
0x180011987  jz      short loc_1800119A2
0x180011989  mov     edx, 15h
0x18001198e  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180011995  mov     ecx, 401h
0x18001199a  mov     r9d, eax
0x18001199d  call    WPP_SF_D
0x1800119a2  call    DhcpIsWCOSSystem
0x1800119a7  lea     rdx, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1800119ae  mov     [rsp+40h+var_8], 1; int
0x1800119b6  test    eax, eax
0x1800119b8  lea     rcx, aSystemCurrentc_16; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1800119bf  cmovz   rcx, rdx; int
0x1800119c3  xor     r9d, r9d; int
0x1800119c6  mov     [rsp+40h+psz], rcx; psz
0x1800119cb  xor     r8d, r8d; int
0x1800119ce  mov     [rsp+40h+Src], r14; Src
0x1800119d3  mov     [rsp+40h+var_20], r14d; int
0x1800119d8  lea     edx, [r9+0Fh]; int
0x1800119dc  call    DhcpAddOptionDef
0x1800119e1  test    eax, eax
0x1800119e3  jz      short loc_180011A07
0x1800119e5  test    byte ptr cs:xmmword_1800616A0, 2
0x1800119ec  jz      short loc_180011A07
0x1800119ee  mov     edx, 16h
0x1800119f3  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800119fa  mov     ecx, 401h
0x1800119ff  mov     r9d, eax
0x180011a02  call    WPP_SF_D
0x180011a07  lea     r12, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Ne"...
0x180011a0e  mov     [rbp+arg_0], r14d
0x180011a12  mov     rcx, r12
0x180011a15  lea     r8, [rbp+arg_0]
0x180011a19  mov     edx, 200h
0x180011a1e  mov     esi, r14d
0x180011a21  mov     rdi, r12
0x180011a24  call    WxStringCchLengthDWordW
0x180011a29  mov     ecx, eax
0x180011a2b  call    WX_WIN32_FROM_HR
0x180011a30  mov     ebx, [rbp+arg_0]
0x180011a33  jmp     short loc_180011A90
0x180011a35  test    eax, eax
0x180011a37  js      short loc_180011A94
0x180011a39  mov     dword ptr [rbp+pcchLength+4], r14d
0x180011a3d  lea     eax, [rbx+1]
0x180011a40  lea     esi, [rsi+rbx*2]
0x180011a43  mov     [rbp+pcchLength], r14
0x180011a47  lea     rdi, [rdi+rax*2]
0x180011a4b  mov     [rbp+arg_0], r14d
0x180011a4f  add     esi, 2
0x180011a52  test    rdi, rdi
0x180011a55  jnz     short loc_180011A68
0x180011a57  mov     eax, 80070057h
0x180011a5c  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x180011a63  mov     ebx, [rbp+arg_0]
0x180011a66  jmp     short loc_180011A89
0x180011a68  lea     r8, [rbp+pcchLength]; pcchLength
0x180011a6c  mov     edx, 200h; cchMax
0x180011a71  mov     rcx, rdi; psz
0x180011a74  call    StringCchLengthW
0x180011a79  test    eax, eax
0x180011a7b  jns     short loc_180011A86
0x180011a7d  mov     dword ptr [rbp+pcchLength+4], 51h ; 'Q'
0x180011a84  jmp     short loc_180011A63
0x180011a86  mov     ebx, dword ptr [rbp+pcchLength]
0x180011a89  mov     ecx, eax
0x180011a8b  call    WX_WIN32_FROM_HR
0x180011a90  test    ebx, ebx
0x180011a92  jnz     short loc_180011A35
0x180011a94  lea     edi, [rsi+2]
0x180011a97  lea     ecx, [rdi+40h]
0x180011a9a  call    DhcpAlloc
0x180011a9f  mov     rbx, rax
0x180011aa2  test    rax, rax
0x180011aa5  jnz     short loc_180011ACA
0x180011aa7  test    byte ptr cs:xmmword_1800616A0, 2
0x180011aae  jz      short loc_180011B19
0x180011ab0  lea     edx, [rax+17h]
0x180011ab3  mov     ecx, 401h
0x180011ab8  lea     r9d, [rax+8]
0x180011abc  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180011ac3  call    WPP_SF_D
0x180011ac8  jmp     short loc_180011B19
0x180011aca  lea     rcx, [rax+40h]; void *
0x180011ace  mov     r8d, edi; Size
0x180011ad1  mov     rdx, r12; Src
0x180011ad4  mov     [rax+30h], rcx
0x180011ad8  mov     qword ptr [rax+10h], 2Ch ; ','
0x180011ae0  mov     [rax+18h], r14
0x180011ae4  mov     [rax+20h], r14d
0x180011ae8  mov     dword ptr [rax+38h], 3
0x180011aef  mov     [rax+28h], r14
0x180011af3  call    memcpy_0
0x180011af8  mov     rax, cs:off_1800610C0
0x180011aff  cmp     [rax], r15
0x180011b02  jnz     loc_180011EEF
0x180011b08  mov     [rbx], r15
0x180011b0b  mov     [rbx+8], rax
0x180011b0f  mov     [rax], rbx
0x180011b12  mov     cs:off_1800610C0, rbx
0x180011b19  lea     r12, aSystemCurrentc_14; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180011b20  mov     [rbp+arg_0], r14d
0x180011b24  mov     rcx, r12
0x180011b27  lea     r8, [rbp+arg_0]
0x180011b2b  mov     edx, 200h
0x180011b30  mov     esi, r14d
0x180011b33  mov     rdi, r12
0x180011b36  call    WxStringCchLengthDWordW
0x180011b3b  mov     ecx, eax
0x180011b3d  call    WX_WIN32_FROM_HR
0x180011b42  mov     ebx, [rbp+arg_0]
0x180011b45  jmp     short loc_180011BA2
0x180011b47  test    eax, eax
0x180011b49  js      short loc_180011BA6
0x180011b4b  mov     dword ptr [rbp+pcchLength+4], r14d
0x180011b4f  lea     eax, [rbx+1]
0x180011b52  lea     esi, [rsi+rbx*2]
0x180011b55  mov     [rbp+pcchLength], r14
0x180011b59  lea     rdi, [rdi+rax*2]
0x180011b5d  mov     [rbp+arg_0], r14d
0x180011b61  add     esi, 2
0x180011b64  test    rdi, rdi
0x180011b67  jnz     short loc_180011B7A
0x180011b69  mov     eax, 80070057h
0x180011b6e  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x180011b75  mov     ebx, [rbp+arg_0]
0x180011b78  jmp     short loc_180011B9B
0x180011b7a  lea     r8, [rbp+pcchLength]; pcchLength
0x180011b7e  mov     edx, 200h; cchMax
0x180011b83  mov     rcx, rdi; psz
0x180011b86  call    StringCchLengthW
  ... truncated ...
```
