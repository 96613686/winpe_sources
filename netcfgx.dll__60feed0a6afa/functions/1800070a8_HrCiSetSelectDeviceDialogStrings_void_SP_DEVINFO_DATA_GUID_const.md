# HrCiSetSelectDeviceDialogStrings(void *,_SP_DEVINFO_DATA *,_GUID const &)

- ea: `0x1800070a8`
- end: `0x180007830`
- name: `?HrCiSetSelectDeviceDialogStrings@@YAJPEAXPEAU_SP_DEVINFO_DATA@@AEBU_GUID@@@Z`
- size: `1928`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, const struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x180006ecc`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x1800068e4`
- `0x180006a2c`
- `0x1800070a8`
- `0x180007988`
- `0x180007f3c`
- `0x1800082c4`
- `0x1800083e8`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800077b8`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800077b8`

## pseudocode

```c
__int64 __fastcall HrCiSetSelectDeviceDialogStrings(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        const struct _GUID *a3)
{
  int FixedSizeClassInstallParams; // eax
  unsigned int Win32Error; // ebx
  _QWORD *v8; // rcx
  int v9; // esi
  __int64 v10; // rbx
  __int64 v11; // rdi
  const unsigned __int16 *String; // rax
  __int64 v13; // rdx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  __int64 v16; // rdi
  const unsigned __int16 *v17; // rax
  __int64 v18; // rdx
  _WORD *v19; // r8
  _WORD *v20; // rcx
  const unsigned __int16 *v21; // rax
  __int64 v22; // r8
  unsigned __int16 *v23; // rdx
  __int64 v24; // rbx
  __int64 v25; // rdi
  const unsigned __int16 *v26; // rax
  __int64 v27; // rdx
  _WORD *v28; // r8
  _WORD *v29; // rcx
  __int64 v30; // rdi
  const unsigned __int16 *v31; // rax
  __int64 v32; // rdx
  _WORD *v33; // r8
  _WORD *v34; // rcx
  const unsigned __int16 *v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rdi
  const unsigned __int16 *v38; // rax
  __int64 v39; // rdx
  _WORD *v40; // r8
  _WORD *v41; // rcx
  __int64 v42; // rdi
  const unsigned __int16 *v43; // rax
  __int64 v44; // rdx
  _WORD *v45; // r8
  _WORD *v46; // rcx
  const unsigned __int16 *v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rdi
  const unsigned __int16 *v50; // rax
  __int64 v51; // rdx
  _WORD *v52; // r8
  _WORD *v53; // rcx
  __int64 v54; // rdi
  const unsigned __int16 *v55; // rax
  __int64 v56; // r8
  _WORD *v57; // rdx
  _WORD *v58; // rcx
  __int64 v59; // rdi
  const unsigned __int16 *v60; // rax
  __int64 v61; // rdx
  _WORD *v62; // r8
  _WORD *v63; // rcx
  const unsigned __int16 *v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rdi
  const unsigned __int16 *v67; // rax
  __int64 v68; // rdx
  _WORD *v69; // r8
  _WORD *v70; // rcx
  __int64 v71; // rdi
  const unsigned __int16 *v72; // rax
  __int64 v73; // r8
  _WORD *v74; // rdx
  _WORD *v75; // rcx
  __int64 v76; // rdi
  const unsigned __int16 *v77; // rax
  __int64 v78; // rdx
  _WORD *v79; // r8
  _WORD *v80; // rcx
  const unsigned __int16 *v81; // rax
  unsigned __int16 *v82; // rcx
  const unsigned __int16 *v83; // rax
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v86[120]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v87[256]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v88[60]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v89[516]; // [rsp+2DCh] [rbp+1DCh] BYREF
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(&ClassInstallParams, 0, 0x4BCu);
  FixedSizeClassInstallParams = HrSetupDiGetFixedSizeClassInstallParams(
                                  DeviceInfoSet,
                                  DeviceInfoData,
                                  &ClassInstallParams,
                                  1212);
  if ( FixedSizeClassInstallParams < 0 )
  {
    Win32Error = 0;
    if ( FixedSizeClassInstallParams != -2146500075 )
      Win32Error = FixedSizeClassInstallParams;
    goto LABEL_10;
  }
  Win32Error = FixedSizeClassInstallParams;
  if ( ClassInstallParams.InstallFunction == 1 )
  {
LABEL_10:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_555e6cdaff2135333903973068bb5302_Traceguids,
      ClassInstallParams.InstallFunction);
    goto LABEL_10;
  }
LABEL_11:
  if ( Win32Error )
  {
LABEL_127:
    if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 2u && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
      WPP_SF_d(v8[2], 15, WPP_555e6cdaff2135333903973068bb5302_Traceguids, Win32Error);
    return Win32Error;
  }
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  HrSetupDiGetDeviceInstallParams(DeviceInfoSet, DeviceInfoData, &DeviceInstallParams);
  v9 = DeviceInstallParams.Flags & 1;
  if ( *(_QWORD *)&GUID_DEVCLASS_NETCLIENT.Data1 == *(_QWORD *)&a3->Data1
    && *(_QWORD *)GUID_DEVCLASS_NETCLIENT.Data4 == *(_QWORD *)a3->Data4 )
  {
    v10 = 2147483646;
    v11 = 2147483646;
    String = SzLoadString(hModule, 0x36B9u);
    v13 = 60;
    v14 = v86;
    do
    {
      if ( !v11 )
        break;
      if ( !*String )
        break;
      *v14++ = *String++;
      --v11;
      --v13;
    }
    while ( v13 );
    v15 = v14 - 1;
    v16 = 2147483646;
    if ( v13 )
      v15 = v14;
    *v15 = 0;
    v17 = SzLoadString(hModule, 0x36B8u);
    v18 = 30;
    v19 = v88;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    v21 = SzLoadString(hModule, 0x36B7u);
    v22 = 256;
    v23 = v87;
    do
    {
      if ( !v10 )
        break;
      if ( !*v21 )
        break;
      *v23++ = *v21++;
      --v10;
      --v22;
    }
    while ( v22 );
  }
  else if ( *(_QWORD *)&GUID_DEVCLASS_NETSERVICE.Data1 == *(_QWORD *)&a3->Data1
         && *(_QWORD *)GUID_DEVCLASS_NETSERVICE.Data4 == *(_QWORD *)a3->Data4 )
  {
    v24 = 2147483646;
    v25 = 2147483646;
    v26 = SzLoadString(hModule, 0x36C3u);
    v27 = 60;
    v28 = v86;
    do
    {
      if ( !v25 )
        break;
      if ( !*v26 )
        break;
      *v28++ = *v26++;
      --v25;
      --v27;
    }
    while ( v27 );
    v29 = v28 - 1;
    v30 = 2147483646;
    if ( v27 )
      v29 = v28;
    *v29 = 0;
    v31 = SzLoadString(hModule, 0x36C2u);
    v32 = 30;
    v33 = v88;
    do
    {
      if ( !v30 )
        break;
      if ( !*v31 )
        break;
      *v33++ = *v31++;
      --v30;
      --v32;
    }
    while ( v32 );
    v34 = v33 - 1;
    if ( v32 )
      v34 = v33;
    *v34 = 0;
    v35 = SzLoadString(hModule, 0x36C1u);
    v22 = 256;
    v23 = v87;
    do
    {
      if ( !v24 )
        break;
      if ( !*v35 )
        break;
      *v23++ = *v35++;
      --v24;
      --v22;
    }
    while ( v22 );
  }
  else if ( *(_QWORD *)&GUID_DEVCLASS_NETTRANS.Data1 == *(_QWORD *)&a3->Data1
         && *(_QWORD *)GUID_DEVCLASS_NETTRANS.Data4 == *(_QWORD *)a3->Data4 )
  {
    v36 = 2147483646;
    v37 = 2147483646;
    v38 = SzLoadString(hModule, 0x36C0u);
    v39 = 60;
    v40 = v86;
    do
    {
      if ( !v37 )
        break;
      if ( !*v38 )
        break;
      *v40++ = *v38++;
      --v37;
      --v39;
    }
    while ( v39 );
    v41 = v40 - 1;
    v42 = 2147483646;
    if ( v39 )
      v41 = v40;
    *v41 = 0;
    v43 = SzLoadString(hModule, 0x36BFu);
    v44 = 30;
    v45 = v88;
    do
    {
      if ( !v42 )
        break;
      if ( !*v43 )
        break;
      *v45++ = *v43++;
      --v42;
      --v44;
    }
    while ( v44 );
    v46 = v45 - 1;
    if ( v44 )
      v46 = v45;
    *v46 = 0;
    v47 = SzLoadString(hModule, 0x36BEu);
    v22 = 256;
    v23 = v87;
    do
    {
      if ( !v36 )
        break;
      if ( !*v47 )
        break;
      *v23++ = *v47++;
      --v36;
      --v22;
    }
    while ( v22 );
  }
  else if ( *(_QWORD *)&GUID_DEVCLASS_NET.Data1 == *(_QWORD *)&a3->Data1
         && *(_QWORD *)GUID_DEVCLASS_NET.Data4 == *(_QWORD *)a3->Data4 )
  {
    v48 = 2147483646;
    v49 = 2147483646;
    v50 = SzLoadString(hModule, 0x36B6u);
    v51 = 60;
    v52 = v86;
    do
    {
      if ( !v49 )
        break;
      if ( !*v50 )
        break;
      *v52++ = *v50++;
      --v49;
      --v51;
    }
    while ( v51 );
    v53 = v52 - 1;
    v54 = 2147483646;
    if ( v51 )
      v53 = v52;
    *v53 = 0;
    v55 = SzLoadString(hModule, 0x36B5u);
    v56 = 256;
    v57 = v89;
    do
    {
      if ( !v54 )
        break;
      if ( !*v55 )
        break;
      *v57++ = *v55++;
      --v54;
      --v56;
    }
    while ( v56 );
    v58 = v57 - 1;
    v59 = 2147483646;
    if ( v56 )
      v58 = v57;
    *v58 = 0;
    v60 = SzLoadString(hModule, 0x36B4u);
    v61 = 30;
    v62 = v88;
    do
    {
      if ( !v59 )
        break;
      if ( !*v60 )
        break;
      *v62++ = *v60++;
      --v59;
      --v61;
    }
    while ( v61 );
    v63 = v62 - 1;
    if ( v61 )
      v63 = v62;
    *v63 = 0;
    v64 = SzLoadString(hModule, 0x36B3u);
    v22 = 256;
    v23 = v87;
    do
    {
      if ( !v48 )
        break;
      if ( !*v64 )
        break;
      *v23++ = *v64++;
      --v48;
      --v22;
    }
    while ( v22 );
  }
  else
  {
    if ( *(_QWORD *)&GUID_DEVCLASS_INFRARED.Data1 != *(_QWORD *)&a3->Data1
      || *(_QWORD *)GUID_DEVCLASS_INFRARED.Data4 != *(_QWORD *)a3->Data4 )
    {
      goto LABEL_121;
    }
    v65 = 2147483646;
    v66 = 2147483646;
    v67 = SzLoadString(hModule, 0x36BDu);
    v68 = 60;
    v69 = v86;
    do
    {
      if ( !v66 )
        break;
      if ( !*v67 )
        break;
      *v69++ = *v67++;
      --v66;
      --v68;
    }
    while ( v68 );
    v70 = v69 - 1;
    v71 = 2147483646;
    if ( v68 )
      v70 = v69;
    *v70 = 0;
    v72 = SzLoadString(hModule, 0x36BCu);
    v73 = 256;
    v74 = v89;
    do
    {
      if ( !v71 )
        break;
      if ( !*v72 )
        break;
      *v74++ = *v72++;
      --v71;
      --v73;
    }
    while ( v73 );
    v75 = v74 - 1;
    v76 = 2147483646;
    if ( v73 )
      v75 = v74;
    *v75 = 0;
    v77 = SzLoadString(hModule, 0x36BBu);
    v78 = 30;
    v79 = v88;
    do
    {
      if ( !v76 )
        break;
      if ( !*v77 )
        break;
      *v79++ = *v77++;
      --v76;
      --v78;
    }
    while ( v78 );
    v80 = v79 - 1;
    if ( v78 )
      v80 = v79;
    *v80 = 0;
    v81 = SzLoadString(hModule, 0x36BAu);
    v22 = 256;
    v23 = v87;
    do
    {
      if ( !v65 )
        break;
      if ( !*v81 )
        break;
      *v23++ = *v81++;
      --v65;
      --v22;
    }
    while ( v22 );
  }
  v82 = v23 - 1;
  if ( v22 )
    v82 = v23;
  *v82 = 0;
LABEL_121:
  if ( v9 )
  {
    v83 = SzLoadString(hModule, 0x36C4u);
    StringCchCatW(v87, 0x100u, v83);
  }
  ClassInstallParams.InstallFunction = 1;
  Win32Error = 0;
  if ( !SetupDiSetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0x4BCu) )
    Win32Error = HrFromLastWin32Error();
  if ( Win32Error )
  {
    v8 = WPP_GLOBAL_Control;
    goto LABEL_127;
  }
  return Win32Error;
}

```

## disassembly

```asm
0x1800070a8  mov     [rsp-8+arg_10], rbx
0x1800070ad  push    rbp
0x1800070ae  push    rsi
0x1800070af  push    rdi
0x1800070b0  push    r12
0x1800070b2  push    r13
0x1800070b4  push    r14
0x1800070b6  push    r15
0x1800070b8  lea     rbp, [rsp-640h]
0x1800070c0  sub     rsp, 740h
0x1800070c7  mov     rax, cs:__security_cookie
0x1800070ce  xor     rax, rsp
0x1800070d1  mov     [rbp+670h+var_40], rax
0x1800070d8  mov     rdi, r8
0x1800070db  mov     r15, rdx
0x1800070de  mov     r14, rcx
0x1800070e1  mov     ebx, 4BCh
0x1800070e6  mov     r8d, ebx; Size
0x1800070e9  lea     rcx, [rsp+770h+ClassInstallParams]; void *
0x1800070ee  xor     edx, edx; Val
0x1800070f0  call    memset_0
0x1800070f5  mov     r9d, ebx; int
0x1800070f8  lea     r8, [rsp+770h+ClassInstallParams]; ClassInstallParams
0x1800070fd  mov     rdx, r15; DeviceInfoData
0x180007100  mov     rcx, r14; DeviceInfoSet
0x180007103  call    ?HrSetupDiGetFixedSizeClassInstallParams@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_CLASSINSTALL_HEADER@@H@Z; HrSetupDiGetFixedSizeClassInstallParams(void *,_SP_DEVINFO_DATA *,_SP_CLASSINSTALL_HEADER *,int)
0x180007108  xor     r12d, r12d
0x18000710b  lea     rdx, WPP_GLOBAL_Control
0x180007112  mov     r13d, 1
0x180007118  test    eax, eax
0x18000711a  jns     short loc_180007129
0x18000711c  cmp     eax, 800F0215h
0x180007121  mov     ebx, r12d
0x180007124  cmovnz  ebx, eax
0x180007127  jmp     short loc_180007162
0x180007129  mov     r9d, [rsp+770h+ClassInstallParams.InstallFunction]
0x18000712e  mov     ebx, eax
0x180007130  cmp     r9d, r13d
0x180007133  jz      short loc_180007162
0x180007135  mov     rcx, cs:WPP_GLOBAL_Control
0x18000713c  cmp     rcx, rdx
0x18000713f  jz      short loc_180007169
0x180007141  cmp     byte ptr [rcx+19h], 5
0x180007145  jb      short loc_180007169
0x180007147  test    byte ptr [rcx+1Ch], 10h
0x18000714b  jz      short loc_180007169
0x18000714d  mov     rcx, [rcx+10h]
0x180007151  lea     r8, WPP_555e6cdaff2135333903973068bb5302_Traceguids
0x180007158  mov     edx, 0Eh
0x18000715d  call    WPP_SF_d
0x180007162  mov     rcx, cs:WPP_GLOBAL_Control
0x180007169  test    ebx, ebx
0x18000716b  jnz     loc_1800077D4
0x180007171  xor     edx, edx; Val
0x180007173  lea     rcx, [rbp+670h+DeviceInstallParams]; void *
0x18000717a  mov     r8d, 248h; Size
0x180007180  call    memset_0
0x180007185  lea     r8, [rbp+670h+DeviceInstallParams]; DeviceInstallParams
0x18000718c  mov     rdx, r15; DeviceInfoData
0x18000718f  mov     rcx, r14; DeviceInfoSet
0x180007192  call    ?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)
0x180007197  mov     esi, [rbp+670h+DeviceInstallParams.Flags]
0x18000719d  mov     rax, qword ptr cs:GUID_DEVCLASS_NETCLIENT.Data1
0x1800071a4  and     esi, r13d
0x1800071a7  cmp     rax, [rdi]
0x1800071aa  jnz     loc_1800072AB
0x1800071b0  mov     rax, qword ptr cs:GUID_DEVCLASS_NETCLIENT.Data4
0x1800071b7  cmp     rax, [rdi+8]
0x1800071bb  jnz     loc_1800072AB
0x1800071c1  mov     rcx, cs:hModule; hModule
0x1800071c8  mov     ebx, 7FFFFFFEh
0x1800071cd  mov     edx, 36B9h; unsigned int
0x1800071d2  mov     edi, ebx
0x1800071d4  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x1800071d9  mov     edx, 3Ch ; '<'
0x1800071de  lea     r8, [rsp+770h+var_748]
0x1800071e3  test    rdi, rdi
0x1800071e6  jz      short loc_180007204
0x1800071e8  movzx   ecx, word ptr [rax]
0x1800071eb  test    cx, cx
0x1800071ee  jz      short loc_180007204
0x1800071f0  mov     [r8], cx
0x1800071f4  add     rax, 2
0x1800071f8  add     r8, 2
0x1800071fc  sub     rdi, r13
0x1800071ff  sub     rdx, r13
0x180007202  jnz     short loc_1800071E3
0x180007204  test    rdx, rdx
0x180007207  lea     rcx, [r8-2]
0x18000720b  mov     edx, 36B8h; unsigned int
0x180007210  mov     rdi, rbx
0x180007213  cmovnz  rcx, r8
0x180007217  mov     [rcx], r12w
0x18000721b  mov     rcx, cs:hModule; hModule
0x180007222  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x180007227  mov     edx, 1Eh
0x18000722c  lea     r8, [rbp+670h+var_4D0]
0x180007233  test    rdi, rdi
0x180007236  jz      short loc_180007254
0x180007238  movzx   ecx, word ptr [rax]
0x18000723b  test    cx, cx
0x18000723e  jz      short loc_180007254
0x180007240  mov     [r8], cx
0x180007244  add     rax, 2
0x180007248  add     r8, 2
0x18000724c  sub     rdi, r13
0x18000724f  sub     rdx, r13
0x180007252  jnz     short loc_180007233
0x180007254  test    rdx, rdx
0x180007257  lea     rcx, [r8-2]
0x18000725b  mov     edx, 36B7h; unsigned int
0x180007260  cmovnz  rcx, r8
0x180007264  mov     [rcx], r12w
0x180007268  mov     rcx, cs:hModule; hModule
0x18000726f  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x180007274  mov     r8d, 100h
0x18000727a  lea     rdx, [rbp+670h+var_6D0]
0x18000727e  test    rbx, rbx
0x180007281  jz      loc_18000776A
0x180007287  movzx   ecx, word ptr [rax]
0x18000728a  test    cx, cx
0x18000728d  jz      loc_18000776A
0x180007293  mov     [rdx], cx
0x180007296  add     rax, 2
0x18000729a  add     rdx, 2
0x18000729e  sub     rbx, r13
0x1800072a1  sub     r8, r13
0x1800072a4  jnz     short loc_18000727E
0x1800072a6  jmp     loc_18000776A
0x1800072ab  mov     rax, qword ptr cs:GUID_DEVCLASS_NETSERVICE.Data1
0x1800072b2  cmp     rax, [rdi]
0x1800072b5  jnz     loc_1800073B6
0x1800072bb  mov     rax, qword ptr cs:GUID_DEVCLASS_NETSERVICE.Data4
0x1800072c2  cmp     rax, [rdi+8]
0x1800072c6  jnz     loc_1800073B6
0x1800072cc  mov     rcx, cs:hModule; hModule
0x1800072d3  mov     ebx, 7FFFFFFEh
0x1800072d8  mov     edx, 36C3h; unsigned int
0x1800072dd  mov     edi, ebx
0x1800072df  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x1800072e4  mov     edx, 3Ch ; '<'
0x1800072e9  lea     r8, [rsp+770h+var_748]
0x1800072ee  test    rdi, rdi
0x1800072f1  jz      short loc_18000730F
0x1800072f3  movzx   ecx, word ptr [rax]
0x1800072f6  test    cx, cx
0x1800072f9  jz      short loc_18000730F
0x1800072fb  mov     [r8], cx
0x1800072ff  add     rax, 2
0x180007303  add     r8, 2
0x180007307  sub     rdi, r13
0x18000730a  sub     rdx, r13
0x18000730d  jnz     short loc_1800072EE
0x18000730f  test    rdx, rdx
0x180007312  lea     rcx, [r8-2]
0x180007316  mov     edx, 36C2h; unsigned int
0x18000731b  mov     rdi, rbx
0x18000731e  cmovnz  rcx, r8
0x180007322  mov     [rcx], r12w
0x180007326  mov     rcx, cs:hModule; hModule
0x18000732d  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x180007332  mov     edx, 1Eh
0x180007337  lea     r8, [rbp+670h+var_4D0]
0x18000733e  test    rdi, rdi
0x180007341  jz      short loc_18000735F
0x180007343  movzx   ecx, word ptr [rax]
0x180007346  test    cx, cx
0x180007349  jz      short loc_18000735F
0x18000734b  mov     [r8], cx
0x18000734f  add     rax, 2
0x180007353  add     r8, 2
0x180007357  sub     rdi, r13
0x18000735a  sub     rdx, r13
0x18000735d  jnz     short loc_18000733E
0x18000735f  test    rdx, rdx
0x180007362  lea     rcx, [r8-2]
0x180007366  mov     edx, 36C1h; unsigned int
0x18000736b  cmovnz  rcx, r8
0x18000736f  mov     [rcx], r12w
0x180007373  mov     rcx, cs:hModule; hModule
0x18000737a  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000737f  mov     r8d, 100h
0x180007385  lea     rdx, [rbp+670h+var_6D0]
0x180007389  test    rbx, rbx
0x18000738c  jz      loc_18000776A
0x180007392  movzx   ecx, word ptr [rax]
0x180007395  test    cx, cx
0x180007398  jz      loc_18000776A
0x18000739e  mov     [rdx], cx
0x1800073a1  add     rax, 2
0x1800073a5  add     rdx, 2
0x1800073a9  sub     rbx, r13
0x1800073ac  sub     r8, r13
0x1800073af  jnz     short loc_180007389
0x1800073b1  jmp     loc_18000776A
0x1800073b6  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data1
0x1800073bd  cmp     rax, [rdi]
0x1800073c0  jnz     loc_1800074C1
0x1800073c6  mov     rax, qword ptr cs:GUID_DEVCLASS_NETTRANS.Data4
0x1800073cd  cmp     rax, [rdi+8]
0x1800073d1  jnz     loc_1800074C1
0x1800073d7  mov     rcx, cs:hModule; hModule
0x1800073de  mov     ebx, 7FFFFFFEh
0x1800073e3  mov     edx, 36C0h; unsigned int
0x1800073e8  mov     edi, ebx
0x1800073ea  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x1800073ef  mov     edx, 3Ch ; '<'
0x1800073f4  lea     r8, [rsp+770h+var_748]
0x1800073f9  test    rdi, rdi
0x1800073fc  jz      short loc_18000741A
0x1800073fe  movzx   ecx, word ptr [rax]
0x180007401  test    cx, cx
0x180007404  jz      short loc_18000741A
0x180007406  mov     [r8], cx
0x18000740a  add     rax, 2
0x18000740e  add     r8, 2
0x180007412  sub     rdi, r13
0x180007415  sub     rdx, r13
0x180007418  jnz     short loc_1800073F9
0x18000741a  test    rdx, rdx
0x18000741d  lea     rcx, [r8-2]
0x180007421  mov     edx, 36BFh; unsigned int
0x180007426  mov     rdi, rbx
0x180007429  cmovnz  rcx, r8
0x18000742d  mov     [rcx], r12w
0x180007431  mov     rcx, cs:hModule; hModule
0x180007438  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000743d  mov     edx, 1Eh
0x180007442  lea     r8, [rbp+670h+var_4D0]
0x180007449  test    rdi, rdi
0x18000744c  jz      short loc_18000746A
0x18000744e  movzx   ecx, word ptr [rax]
0x180007451  test    cx, cx
0x180007454  jz      short loc_18000746A
0x180007456  mov     [r8], cx
0x18000745a  add     rax, 2
0x18000745e  add     r8, 2
0x180007462  sub     rdi, r13
0x180007465  sub     rdx, r13
0x180007468  jnz     short loc_180007449
0x18000746a  test    rdx, rdx
0x18000746d  lea     rcx, [r8-2]
0x180007471  mov     edx, 36BEh; unsigned int
0x180007476  cmovnz  rcx, r8
0x18000747a  mov     [rcx], r12w
0x18000747e  mov     rcx, cs:hModule; hModule
0x180007485  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x18000748a  mov     r8d, 100h
0x180007490  lea     rdx, [rbp+670h+var_6D0]
0x180007494  test    rbx, rbx
0x180007497  jz      loc_18000776A
0x18000749d  movzx   ecx, word ptr [rax]
0x1800074a0  test    cx, cx
0x1800074a3  jz      loc_18000776A
0x1800074a9  mov     [rdx], cx
0x1800074ac  add     rax, 2
0x1800074b0  add     rdx, 2
0x1800074b4  sub     rbx, r13
0x1800074b7  sub     r8, r13
0x1800074ba  jnz     short loc_180007494
0x1800074bc  jmp     loc_18000776A
0x1800074c1  mov     rax, qword ptr cs:GUID_DEVCLASS_NET.Data1
0x1800074c8  cmp     rax, [rdi]
0x1800074cb  jnz     loc_18000761C
0x1800074d1  mov     rax, qword ptr cs:GUID_DEVCLASS_NET.Data4
0x1800074d8  cmp     rax, [rdi+8]
0x1800074dc  jnz     loc_18000761C
0x1800074e2  mov     rcx, cs:hModule; hModule
0x1800074e9  mov     ebx, 7FFFFFFEh
0x1800074ee  mov     edx, 36B6h; unsigned int
0x1800074f3  mov     edi, ebx
0x1800074f5  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x1800074fa  mov     edx, 3Ch ; '<'
0x1800074ff  lea     r8, [rsp+770h+var_748]
0x180007504  test    rdi, rdi
0x180007507  jz      short loc_180007525
0x180007509  movzx   ecx, word ptr [rax]
0x18000750c  test    cx, cx
0x18000750f  jz      short loc_180007525
0x180007511  mov     [r8], cx
0x180007515  add     rax, 2
0x180007519  add     r8, 2
0x18000751d  sub     rdi, r13
0x180007520  sub     rdx, r13
0x180007523  jnz     short loc_180007504
0x180007525  test    rdx, rdx
0x180007528  lea     rcx, [r8-2]
0x18000752c  mov     edx, 36B5h; unsigned int
0x180007531  mov     rdi, rbx
0x180007534  cmovnz  rcx, r8
0x180007538  mov     [rcx], r12w
0x18000753c  mov     rcx, cs:hModule; hModule
0x180007543  call    ?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z; SzLoadString(HINSTANCE__ *,uint)
0x180007548  mov     r8d, 100h
0x18000754e  lea     rdx, [rbp+670h+var_494]
0x180007555  test    rdi, rdi
0x180007558  jz      short loc_180007575
0x18000755a  movzx   ecx, word ptr [rax]
0x18000755d  test    cx, cx
0x180007560  jz      short loc_180007575
  ... truncated ...
```
