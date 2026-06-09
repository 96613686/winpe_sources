# PcapCheckEnablePca(ushort const *,ushort const *,ulong)

- ea: `0x180002210`
- end: `0x180002bbe`
- name: `?PcapCheckEnablePca@@YAHPEBG0K@Z`
- size: `2478`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001bd0`
- `0x180008480`

## callees

- `0x180002210`
- `0x180002bd0`
- `0x180002ee8`
- `0x180007738`
- `0x180008764`
- `0x1800088a8`
- `0x18000bff2`
- `0x18000bffe`
- `0x18000c030`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000244f`
- `msvcrt!_wcsicmp` at `0x180002666`
- `msvcrt!_wcsicmp` at `0x1800027b7`
- `msvcrt!_wcsicmp` at `0x1800028da`
- `msvcrt!_wcsicmp` at `0x18000244f`
- `msvcrt!_wcsicmp` at `0x180002666`
- `msvcrt!_wcsicmp` at `0x1800027b7`
- `msvcrt!_wcsicmp` at `0x1800028da`
- `msvcrt!wcscat_s` at `0x180002483`
- `msvcrt!wcscat_s` at `0x180002483`
- `msvcrt!wcscpy_s` at `0x18000246e`
- `msvcrt!wcscpy_s` at `0x18000246e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000248e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000248e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800024d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800024d8`
- `ntdll!RtlGetNtSystemRoot` at `0x180002368`
- `ntdll!RtlGetNtSystemRoot` at `0x18000245d`
- `ntdll!RtlGetNtSystemRoot` at `0x1800024ff`
- `ntdll!RtlGetNtSystemRoot` at `0x180002677`
- `ntdll!RtlGetNtSystemRoot` at `0x1800028eb`
- `ntdll!RtlGetNtSystemRoot` at `0x180002368`
- `ntdll!RtlGetNtSystemRoot` at `0x18000245d`
- `ntdll!RtlGetNtSystemRoot` at `0x1800024ff`
- `ntdll!RtlGetNtSystemRoot` at `0x180002677`
- `ntdll!RtlGetNtSystemRoot` at `0x1800028eb`

## string_xrefs

- `0x180002474`: `\System32\sfc_os.dll`
- `0x1800027df`: `PcaClient`
- `0x180002b2b`: `PcaClient`
- `0x180002b64`: `PcaClient`
- `0x180002613`: `msiexec.exe`
- `0x180002341`: `\system32\`
- `0x1800023e1`: `PcaUtilityCompareToSystemExe`
- `0x180002570`: `PcaUtilityCompareToSystemExe`
- `0x1800023d4`: `Failed to cat system32 path`
- `0x180002563`: `Failed to cat system32 path`
- `0x180002a79`: `Failed to copy NtSystemRoot`
- `0x180002a8b`: `Failed to copy NtSystemRoot`
- `0x1800023fd`: `Bad ApplicationName or CommandLine [%d]`
- `0x180002a9f`: `Bad ApplicationName or CommandLine [%d]`
- `0x180002ab4`: `PcaUtilityGetExecutablePath`
- `0x180002b8c`: `Bad cpl command line [%d]`
- `0x1800026d8`: `Failed to cat syswow64 path`
- `0x180002953`: `Failed to cat syswow64 path`

## pseudocode

```c
__int64 __fastcall PcapCheckEnablePca(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v6; // r13
  wchar_t *p_String1; // r8
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  wchar_t *v12; // rcx
  BOOL v13; // edx
  wchar_t v14; // ax
  unsigned __int64 v15; // rax
  const wchar_t *v16; // rsi
  const wchar_t *v17; // r15
  __int64 v18; // rbx
  wchar_t *NtSystemRoot; // rax
  __int64 v20; // rdx
  wchar_t *v21; // r8
  wchar_t *v22; // rcx
  __int64 v23; // rdx
  wchar_t *v24; // rax
  _WORD *v26; // rcx
  const unsigned __int16 *v27; // rdx
  const wchar_t *v28; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int64 v31; // rbx
  wchar_t *v32; // rax
  __int64 v33; // r9
  wchar_t *v34; // r10
  wchar_t *v35; // rcx
  __int64 v36; // rdx
  wchar_t *v37; // rax
  __int64 v38; // rcx
  _WORD *v39; // r9
  _WORD *v40; // rcx
  __int64 v41; // rdx
  wchar_t *v42; // rax
  __int64 v43; // rcx
  _WORD *v44; // r9
  const wchar_t *v45; // rdi
  const wchar_t *v46; // r8
  _WORD *v47; // rcx
  __int64 v48; // rbx
  wchar_t *v49; // rax
  __int64 v50; // rdx
  wchar_t *v51; // r9
  wchar_t *v52; // rcx
  __int64 v53; // rdx
  wchar_t *v54; // rax
  __int64 v55; // rcx
  _WORD *v56; // r9
  _WORD *v57; // rcx
  wchar_t *v58; // rax
  _WORD *v59; // rdx
  _WORD *v60; // rcx
  __int64 v61; // rcx
  const wchar_t *v62; // r8
  _WORD *v63; // r9
  _WORD *v64; // rcx
  __int64 v65; // rdx
  wchar_t *v66; // rax
  __int64 v67; // rcx
  _WORD *v68; // r9
  const wchar_t *v69; // rdi
  const wchar_t *v70; // r8
  _WORD *v71; // rcx
  __int64 v72; // rbx
  wchar_t *v73; // rax
  __int64 v74; // rdx
  wchar_t *v75; // r8
  wchar_t *v76; // rcx
  __int64 v77; // rdx
  wchar_t *v78; // rax
  __int64 v79; // rcx
  const wchar_t *v80; // r8
  _WORD *v81; // r9
  _WORD *v82; // rcx
  __int64 v83; // rdx
  wchar_t *v84; // rax
  __int64 v85; // rcx
  _WORD *v86; // r8
  __int64 v87; // r8
  __int64 v88; // r8
  const unsigned __int16 *v89; // r8
  unsigned int FileNameInCommandLine; // eax
  wchar_t String2[260]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v93[8]; // [rsp+248h] [rbp+148h] BYREF
  wchar_t String1; // [rsp+250h] [rbp+150h] BYREF
  _BYTE Src[526]; // [rsp+252h] [rbp+152h] BYREF

  memset_0(Src, 0, 0x206u);
  String1 = 0;
  if ( !a1 )
  {
    if ( !a2 )
    {
LABEL_33:
      AslLogCallPrintf(1, "PcapCheckEnablePca", 534, "Bad ApplicationName or CommandLine [%d]", 87);
      return 0;
    }
    a1 = a2;
  }
  v6 = 2147483646;
  p_String1 = &String1;
  v8 = 260;
  v9 = 2147483646;
  v10 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*a1 )
      break;
    *p_String1++ = *a1++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = p_String1 - 1;
  if ( v10 )
    v11 = p_String1;
  *v11 = 0;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "PcaUtilityGetExecutablePath", 541, "Bad ApplicationName or CommandLine [%d]", 87);
    goto LABEL_33;
  }
  v12 = &String1;
  v13 = 0;
  while ( 1 )
  {
    v14 = *v12;
    if ( !*v12 )
      break;
    if ( v14 == 34 )
    {
      v13 = !v13;
    }
    else if ( !v13 && v14 == 32 )
    {
      if ( *++v12 )
      {
        *(v12 - 1) = 0;
        goto LABEL_16;
      }
      break;
    }
    ++v12;
  }
  if ( &String1 < v12 && *(v12 - 1) == 32 )
    *(v12 - 1) = 0;
LABEL_16:
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)&Src[2 * v15 - 2] );
  if ( String1 == 34 && v15 < 0x104 && *(_WORD *)&v93[2 * v15 + 6] == 34 )
  {
    *(_WORD *)&v93[2 * v15 + 6] = 0;
    memmove_0(&String1, Src, 2 * v15 - 2);
  }
  if ( !(unsigned int)PcaIsPcaDisabled() )
  {
    v16 = L"\\system32\\";
    v17 = L"\\syswow64\\";
    if ( !a2 )
      goto LABEL_38;
    String2[0] = 0;
    v18 = 2147483646;
    NtSystemRoot = (wchar_t *)RtlGetNtSystemRoot();
    v20 = 260;
    v21 = String2;
    do
    {
      if ( !v18 )
        break;
      if ( !*NtSystemRoot )
        break;
      *v21++ = *NtSystemRoot++;
      --v18;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    if ( v20 )
    {
      v23 = 260;
      v24 = String2;
      while ( *v24 )
      {
        ++v24;
        if ( !--v23 )
          goto LABEL_31;
      }
      v61 = 2147483646;
      v62 = L"\\system32\\";
      v63 = &v93[-2 * v23];
      do
      {
        if ( !v61 )
          break;
        if ( !*v62 )
          break;
        *v63++ = *v62++;
        --v61;
        --v23;
      }
      while ( v23 );
      v64 = v63 - 1;
      if ( v23 )
        v64 = v63;
      *v64 = 0;
      if ( !v23 )
      {
LABEL_31:
        AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 613, "Failed to cat system32 path");
        goto LABEL_38;
      }
      v65 = 260;
      v66 = String2;
      while ( *v66 )
      {
        ++v66;
        if ( !--v65 )
          goto LABEL_114;
      }
      v67 = 2147483646;
      v68 = &v93[-2 * v65];
      v69 = L"control.exe";
      v70 = L"control.exe";
      do
      {
        if ( !v67 )
          break;
        if ( !*v70 )
          break;
        *v68++ = *v70++;
        --v67;
        --v65;
      }
      while ( v65 );
      v71 = v68 - 1;
      if ( v65 )
        v71 = v68;
      *v71 = 0;
      if ( !v65 )
      {
LABEL_114:
        AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 620, "Failed to cat SystemExeName");
        goto LABEL_38;
      }
      if ( !_wcsicmp(&String1, String2) )
      {
LABEL_166:
        if ( PcaUtilityWcsIStr(a2, v27) )
        {
          PcaTracePrintf("PcaClient", 0, a3, "Excluded,System CPL");
          return 0;
        }
        FileNameInCommandLine = PcaUtilityFindFileNameInCommandLine(&String1, a2, v89);
        if ( FileNameInCommandLine )
        {
          AslLogCallPrintf(3, "PcapCheckEnablePca", 579, "Bad cpl command line [%d]", FileNameInCommandLine);
          return 0;
        }
LABEL_38:
        v28 = (const wchar_t *)RtlGetNtSystemRoot();
        wcscpy_s(String2, 0x104u, v28);
        wcscat_s(String2, 0x104u, L"\\System32\\sfc_os.dll");
        LibraryW = LoadLibraryW(String2);
        if ( !LibraryW )
          return 1;
        ProcAddress = GetProcAddress(LibraryW, "SfcIsFileProtected");
        if ( !ProcAddress || !((unsigned int (__fastcall *)(_QWORD, wchar_t *))ProcAddress)(0, &String1) )
          return 1;
        v31 = 2147483646;
        String2[0] = 0;
        v32 = (wchar_t *)RtlGetNtSystemRoot();
        v33 = 260;
        v34 = String2;
        do
        {
          if ( !v31 )
            break;
          if ( !*v32 )
            break;
          *v34++ = *v32++;
          --v31;
          --v33;
        }
        while ( v33 );
        v35 = v34 - 1;
        if ( v33 )
          v35 = v34;
        *v35 = 0;
        if ( v33 )
        {
          v36 = 260;
          v37 = String2;
          while ( *v37 )
          {
            ++v37;
            if ( !--v36 )
              goto LABEL_52;
          }
          v38 = 2147483646;
          v39 = &v93[-2 * v36];
          do
          {
            if ( !v38 )
              break;
            if ( !*v16 )
              break;
            *v39++ = *v16++;
            --v38;
            --v36;
          }
          while ( v36 );
          v40 = v39 - 1;
          if ( v36 )
            v40 = v39;
          *v40 = 0;
          if ( !v36 )
          {
LABEL_52:
            AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 613, "Failed to cat system32 path");
            goto LABEL_102;
          }
          v41 = 260;
          v42 = String2;
          while ( *v42 )
          {
            ++v42;
            if ( !--v41 )
              goto LABEL_63;
          }
          v43 = 2147483646;
          v44 = &v93[-2 * v41];
          v45 = L"msiexec.exe";
          v46 = L"msiexec.exe";
          do
          {
            if ( !v43 )
              break;
            if ( !*v46 )
              break;
            *v44++ = *v46++;
            --v43;
            --v41;
          }
          while ( v41 );
          v47 = v44 - 1;
          if ( v41 )
            v47 = v44;
          *v47 = 0;
          if ( !v41 )
          {
LABEL_63:
            AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 620, "Failed to cat SystemExeName");
            goto LABEL_102;
          }
          if ( !_wcsicmp(&String1, String2) )
            return 1;
          v48 = 2147483646;
          v49 = (wchar_t *)RtlGetNtSystemRoot();
          v50 = 260;
          v51 = String2;
          do
          {
            if ( !v48 )
              break;
            if ( !*v49 )
              break;
            *v51++ = *v49++;
            --v48;
            --v50;
          }
          while ( v50 );
          v52 = v51 - 1;
          if ( v50 )
            v52 = v51;
          *v52 = 0;
          if ( v50 )
          {
            v53 = 260;
            v54 = String2;
            while ( *v54 )
            {
              ++v54;
              if ( !--v53 )
                goto LABEL_82;
            }
            v55 = 2147483646;
            v56 = &v93[-2 * v53];
            do
            {
              if ( !v55 )
                break;
              if ( !*v17 )
                break;
              *v56++ = *v17++;
              --v55;
              --v53;
            }
            while ( v53 );
            v57 = v56 - 1;
            if ( v53 )
              v57 = v56;
            *v57 = 0;
            if ( !v53 )
            {
LABEL_82:
              AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 643, "Failed to cat syswow64 path");
              goto LABEL_102;
            }
            v58 = String2;
            while ( *v58 )
            {
              ++v58;
              if ( !--v8 )
                goto LABEL_93;
            }
            v59 = &v93[-2 * v8];
            do
            {
              if ( !v6 )
                break;
              if ( !*v45 )
                break;
              *v59++ = *v45++;
              --v6;
              --v8;
            }
            while ( v8 );
            v60 = v59 - 1;
            if ( v8 )
              v60 = v59;
            *v60 = 0;
            if ( !v8 )
            {
LABEL_93:
              AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 650, "Failed to cat SystemExeName");
              goto LABEL_102;
            }
            if ( _wcsicmp(&String1, String2) )
              goto LABEL_102;
            return 1;
          }
          v88 = 636;
        }
        else
        {
          v88 = 606;
        }
        AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", v88, "Failed to copy NtSystemRoot");
LABEL_102:
        PcaTracePrintf("PcaClient", 0, a3, "Excluded,%S,SFC protected", &String1);
        return 0;
      }
      v72 = 2147483646;
      v73 = (wchar_t *)RtlGetNtSystemRoot();
      v74 = 260;
      v75 = String2;
      do
      {
        if ( !v72 )
          break;
        if ( !*v73 )
          break;
        *v75++ = *v73++;
        --v72;
        --v74;
      }
      while ( v74 );
      v76 = v75 - 1;
      if ( v74 )
        v76 = v75;
      *v76 = 0;
      if ( v74 )
      {
        v77 = 260;
        v78 = String2;
        while ( *v78 )
        {
          ++v78;
          if ( !--v77 )
            goto LABEL_133;
        }
        v79 = 2147483646;
        v80 = L"\\syswow64\\";
        v81 = &v93[-2 * v77];
        do
        {
          if ( !v79 )
            break;
          if ( !*v80 )
            break;
          *v81++ = *v80++;
          --v79;
          --v77;
        }
        while ( v77 );
        v82 = v81 - 1;
        if ( v77 )
          v82 = v81;
        *v82 = 0;
        if ( !v77 )
        {
LABEL_133:
          AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 643, "Failed to cat syswow64 path");
          goto LABEL_38;
        }
        v83 = 260;
        v84 = String2;
        while ( *v84 )
        {
          ++v84;
          if ( !--v83 )
            goto LABEL_144;
        }
        v85 = 2147483646;
        v86 = &v93[-2 * v83];
        do
        {
          if ( !v85 )
            break;
          if ( !*v69 )
            break;
          *v86++ = *v69++;
          --v85;
          --v83;
        }
        while ( v83 );
        v26 = v86 - 1;
        if ( v83 )
          v26 = v86;
        *v26 = 0;
        if ( !v83 )
        {
LABEL_144:
          AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", 650, "Failed to cat SystemExeName");
          goto LABEL_38;
        }
        if ( !_wcsicmp(&String1, String2) )
          goto LABEL_166;
        goto LABEL_38;
      }
      v87 = 636;
    }
    else
    {
      v87 = 606;
    }
    AslLogCallPrintf(1, "PcaUtilityCompareToSystemExe", v87, "Failed to copy NtSystemRoot");
    goto LABEL_38;
  }
  PcaTracePrintf("PcaClient", 0, a3, "Excluded,%S,PCA disabled", &String1);
  return 0;
}

```

## disassembly

```asm
0x180002210  push    rbp
0x180002212  push    rbx
0x180002213  push    rdi
0x180002214  push    r12
0x180002216  push    r13
0x180002218  push    r14
0x18000221a  lea     rbp, [rsp-378h]
0x180002222  sub     rsp, 478h
0x180002229  mov     rax, cs:__security_cookie
0x180002230  xor     rax, rsp
0x180002233  mov     [rbp+3A0h+var_40], rax
0x18000223a  mov     edi, r8d
0x18000223d  mov     [rsp+4A0h+var_470], r8d
0x180002242  mov     r12, rdx
0x180002245  mov     rbx, rcx
0x180002248  xor     edx, edx; Val
0x18000224a  lea     rcx, [rbp+3A0h+Src]; void *
0x180002251  mov     r8d, 206h; Size
0x180002257  call    memset_0
0x18000225c  xor     eax, eax
0x18000225e  mov     [rbp+3A0h+String1], ax
0x180002265  test    rbx, rbx
0x180002268  jz      loc_1800023F4
0x18000226e  mov     r13d, 7FFFFFFEh
0x180002274  lea     r8, [rbp+3A0h+String1]
0x18000227b  mov     r14d, 104h
0x180002281  mov     ecx, r13d
0x180002284  mov     edx, r14d
0x180002287  test    rcx, rcx
0x18000228a  jz      short loc_1800022A9
0x18000228c  movzx   eax, word ptr [rbx]
0x18000228f  test    ax, ax
0x180002292  jz      short loc_1800022A9
0x180002294  mov     [r8], ax
0x180002298  add     rbx, 2
0x18000229c  add     r8, 2
0x1800022a0  dec     rcx
0x1800022a3  sub     rdx, 1
0x1800022a7  jnz     short loc_180002287
0x1800022a9  test    rdx, rdx
0x1800022ac  lea     rcx, [r8-2]
0x1800022b0  cmovnz  rcx, r8
0x1800022b4  xor     eax, eax
0x1800022b6  mov     [rcx], ax
0x1800022b9  test    rdx, rdx
0x1800022bc  jz      loc_180002A9F
0x1800022c2  lea     rcx, [rbp+3A0h+String1]
0x1800022c9  xor     edx, edx
0x1800022cb  movzx   eax, word ptr [rcx]
0x1800022ce  test    ax, ax
0x1800022d1  jz      loc_180002ADC
0x1800022d7  cmp     ax, 22h ; '"'
0x1800022db  jz      loc_180002ACA
0x1800022e1  test    edx, edx
0x1800022e3  jnz     loc_180002AD3
0x1800022e9  cmp     ax, 20h ; ' '
0x1800022ed  jnz     loc_180002AD3
0x1800022f3  add     rcx, 2
0x1800022f7  cmp     [rcx], dx
0x1800022fa  jz      loc_180002ADC
0x180002300  xor     eax, eax
0x180002302  mov     [rcx-2], ax
0x180002306  lea     rcx, [rbp+3A0h+String1]
0x18000230d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002314  inc     rax
0x180002317  cmp     word ptr [rcx+rax*2], 0
0x18000231c  jnz     short loc_180002314
0x18000231e  cmp     [rbp+3A0h+String1], 22h ; '"'
0x180002326  jz      loc_180002A2F
0x18000232c  call    ?PcaIsPcaDisabled@@YAHXZ; PcaIsPcaDisabled(void)
0x180002331  test    eax, eax
0x180002333  jnz     loc_180002B13
0x180002339  mov     [rsp+4A0h+arg_0], rsi
0x180002341  lea     rsi, aSystem32_0; "\\system32\\"
0x180002348  mov     [rsp+4A0h+var_30], r15
0x180002350  lea     r15, aSyswow64_0; "\\syswow64\\"
0x180002357  test    r12, r12
0x18000235a  jz      loc_18000245D
0x180002360  mov     [rsp+4A0h+String2], ax
0x180002365  mov     rbx, r13
0x180002368  call    cs:__imp_RtlGetNtSystemRoot
0x18000236e  mov     rdx, r14
0x180002371  lea     r8, [rsp+4A0h+String2]
0x180002376  test    rbx, rbx
0x180002379  jz      short loc_180002398
0x18000237b  movzx   ecx, word ptr [rax]
0x18000237e  test    cx, cx
0x180002381  jz      short loc_180002398
0x180002383  mov     [r8], cx
0x180002387  add     rax, 2
0x18000238b  add     r8, 2
0x18000238f  dec     rbx
0x180002392  sub     rdx, 1
0x180002396  jnz     short loc_180002376
0x180002398  test    rdx, rdx
0x18000239b  lea     rcx, [r8-2]
0x18000239f  cmovnz  rcx, r8
0x1800023a3  xor     eax, eax
0x1800023a5  mov     [rcx], ax
0x1800023a8  test    rdx, rdx
0x1800023ab  jz      loc_180002B3E
0x1800023b1  mov     rdx, r14
0x1800023b4  lea     rax, [rsp+4A0h+String2]
0x1800023b9  nop     dword ptr [rax+00000000h]
0x1800023c0  cmp     word ptr [rax], 0
0x1800023c4  jz      loc_1800027F2
0x1800023ca  add     rax, 2
0x1800023ce  sub     rdx, 1
0x1800023d2  jnz     short loc_1800023C0
0x1800023d4  lea     r9, aFailedToCatSys; "Failed to cat system32 path"
0x1800023db  mov     r8d, 265h
0x1800023e1  lea     rdx, aPcautilitycomp; "PcaUtilityCompareToSystemExe"
0x1800023e8  mov     ecx, 1
0x1800023ed  call    AslLogCallPrintf
0x1800023f2  jmp     short loc_18000245D
0x1800023f4  test    r12, r12
0x1800023f7  jnz     loc_180002A97
0x1800023fd  lea     r9, aBadApplication; "Bad ApplicationName or CommandLine [%d]"
0x180002404  mov     dword ptr [rsp+4A0h+var_480], 57h ; 'W'
0x18000240c  mov     r8d, 216h
0x180002412  lea     rdx, aPcapcheckenabl; "PcapCheckEnablePca"
0x180002419  mov     ecx, 1
0x18000241e  call    AslLogCallPrintf
0x180002423  xor     eax, eax
0x180002425  jmp     loc_1800024AE
0x18000242a  test    rdx, rdx
0x18000242d  lea     rcx, [r8-2]
0x180002431  cmovnz  rcx, r8
0x180002435  xor     eax, eax
0x180002437  mov     [rcx], ax
0x18000243a  test    rdx, rdx
0x18000243d  jz      loc_1800029D0
0x180002443  lea     rdx, [rsp+4A0h+String2]; String2
0x180002448  lea     rcx, [rbp+3A0h+String1]; String1
0x18000244f  call    cs:__imp__wcsicmp
0x180002455  test    eax, eax
0x180002457  jz      loc_180002B49
0x18000245d  call    cs:__imp_RtlGetNtSystemRoot
0x180002463  mov     rdx, r14; SizeInWords
0x180002466  lea     rcx, [rsp+4A0h+String2]; Destination
0x18000246b  mov     r8, rax; Source
0x18000246e  call    cs:__imp_wcscpy_s
0x180002474  lea     r8, aSystem32SfcOsD; "\\System32\\sfc_os.dll"
0x18000247b  mov     rdx, r14; SizeInWords
0x18000247e  lea     rcx, [rsp+4A0h+String2]; Destination
0x180002483  call    cs:__imp_wcscat_s
0x180002489  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x18000248e  call    cs:__imp_LoadLibraryW
0x180002494  test    rax, rax
0x180002497  jnz     short loc_1800024CE
0x180002499  mov     eax, 1
0x18000249e  mov     rsi, [rsp+4A0h+arg_0]
0x1800024a6  mov     r15, [rsp+4A0h+var_30]
0x1800024ae  mov     rcx, [rbp+3A0h+var_40]
0x1800024b5  xor     rcx, rsp; StackCookie
0x1800024b8  call    __security_check_cookie
0x1800024bd  add     rsp, 478h
0x1800024c4  pop     r14
0x1800024c6  pop     r13
0x1800024c8  pop     r12
0x1800024ca  pop     rdi
0x1800024cb  pop     rbx
0x1800024cc  pop     rbp
0x1800024cd  retn
0x1800024ce  lea     rdx, ProcName; "SfcIsFileProtected"
0x1800024d5  mov     rcx, rax; hModule
0x1800024d8  call    cs:__imp_GetProcAddress
0x1800024de  test    rax, rax
0x1800024e1  jz      short loc_180002499
0x1800024e3  lea     rdx, [rbp+3A0h+String1]
0x1800024ea  xor     ecx, ecx
0x1800024ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f1  test    eax, eax
0x1800024f3  jz      short loc_180002499
0x1800024f5  xor     eax, eax
0x1800024f7  mov     rbx, r13
0x1800024fa  mov     [rsp+4A0h+String2], ax
0x1800024ff  call    cs:__imp_RtlGetNtSystemRoot
0x180002505  mov     r9, r14
0x180002508  lea     r10, [rsp+4A0h+String2]
0x18000250d  nop     dword ptr [rax]
0x180002510  test    rbx, rbx
0x180002513  jz      short loc_180002532
0x180002515  movzx   ecx, word ptr [rax]
0x180002518  test    cx, cx
0x18000251b  jz      short loc_180002532
0x18000251d  mov     [r10], cx
0x180002521  add     rax, 2
0x180002525  add     r10, 2
0x180002529  dec     rbx
0x18000252c  sub     r9, 1
0x180002530  jnz     short loc_180002510
0x180002532  test    r9, r9
0x180002535  lea     rcx, [r10-2]
0x180002539  cmovnz  rcx, r10
0x18000253d  xor     eax, eax
0x18000253f  mov     [rcx], ax
0x180002542  test    r9, r9
0x180002545  jz      loc_180002BB3
0x18000254b  mov     rdx, r14
0x18000254e  lea     rax, [rsp+4A0h+String2]
0x180002553  cmp     word ptr [rax], 0
0x180002557  jz      short loc_180002586
0x180002559  add     rax, 2
0x18000255d  sub     rdx, 1
0x180002561  jnz     short loc_180002553
0x180002563  lea     r9, aFailedToCatSys; "Failed to cat system32 path"
0x18000256a  mov     r8d, 265h
0x180002570  lea     rdx, aPcautilitycomp; "PcaUtilityCompareToSystemExe"
0x180002577  mov     ecx, 1
0x18000257c  call    AslLogCallPrintf
0x180002581  jmp     loc_1800027C5
0x180002586  lea     rax, [rdx+rdx]
0x18000258a  mov     rcx, r13
0x18000258d  lea     r9, [rbp+3A0h+var_258]
0x180002594  sub     r9, rax
0x180002597  test    rdx, rdx
0x18000259a  jz      short loc_1800025C2
0x18000259c  nop     dword ptr [rax+00h]
0x1800025a0  test    rcx, rcx
0x1800025a3  jz      short loc_1800025C2
0x1800025a5  movzx   eax, word ptr [rsi]
0x1800025a8  test    ax, ax
0x1800025ab  jz      short loc_1800025C2
0x1800025ad  mov     [r9], ax
0x1800025b1  add     rsi, 2
0x1800025b5  add     r9, 2
0x1800025b9  dec     rcx
0x1800025bc  sub     rdx, 1
0x1800025c0  jnz     short loc_1800025A0
0x1800025c2  test    rdx, rdx
0x1800025c5  lea     rcx, [r9-2]
0x1800025c9  cmovnz  rcx, r9
0x1800025cd  xor     eax, eax
0x1800025cf  mov     [rcx], ax
0x1800025d2  test    rdx, rdx
0x1800025d5  jz      short loc_180002563
0x1800025d7  mov     rdx, r14
0x1800025da  lea     rax, [rsp+4A0h+String2]
0x1800025df  nop
0x1800025e0  cmp     word ptr [rax], 0
0x1800025e4  jz      short loc_180002602
0x1800025e6  add     rax, 2
0x1800025ea  sub     rdx, 1
0x1800025ee  jnz     short loc_1800025E0
0x1800025f0  lea     r9, aFailedToCatSys_1; "Failed to cat SystemExeName"
0x1800025f7  mov     r8d, 26Ch
0x1800025fd  jmp     loc_180002570
0x180002602  lea     rax, [rdx+rdx]
0x180002606  mov     rcx, r13
0x180002609  lea     r9, [rbp+3A0h+var_258]
0x180002610  sub     r9, rax
0x180002613  lea     rdi, aMsiexecExe; "msiexec.exe"
0x18000261a  mov     r8, rdi
0x18000261d  test    rdx, rdx
0x180002620  jz      short loc_180002645
0x180002622  test    rcx, rcx
0x180002625  jz      short loc_180002645
0x180002627  movzx   eax, word ptr [r8]
0x18000262b  test    ax, ax
0x18000262e  jz      short loc_180002645
0x180002630  mov     [r9], ax
0x180002634  add     r8, 2
0x180002638  add     r9, 2
0x18000263c  dec     rcx
0x18000263f  sub     rdx, 1
0x180002643  jnz     short loc_180002622
0x180002645  test    rdx, rdx
0x180002648  lea     rcx, [r9-2]
0x18000264c  cmovnz  rcx, r9
0x180002650  xor     eax, eax
0x180002652  mov     [rcx], ax
0x180002655  test    rdx, rdx
0x180002658  jz      short loc_1800025F0
0x18000265a  lea     rdx, [rsp+4A0h+String2]; String2
0x18000265f  lea     rcx, [rbp+3A0h+String1]; String1
0x180002666  call    cs:__imp__wcsicmp
0x18000266c  test    eax, eax
0x18000266e  jz      loc_180002499
0x180002674  mov     rbx, r13
0x180002677  call    cs:__imp_RtlGetNtSystemRoot
0x18000267d  mov     rdx, r14
0x180002680  lea     r9, [rsp+4A0h+String2]
0x180002685  test    rbx, rbx
0x180002688  jz      short loc_1800026A7
0x18000268a  movzx   ecx, word ptr [rax]
0x18000268d  test    cx, cx
0x180002690  jz      short loc_1800026A7
0x180002692  mov     [r9], cx
0x180002696  add     rax, 2
0x18000269a  add     r9, 2
0x18000269e  dec     rbx
0x1800026a1  sub     rdx, 1
0x1800026a5  jnz     short loc_180002685
0x1800026a7  test    rdx, rdx
0x1800026aa  lea     rcx, [r9-2]
0x1800026ae  cmovnz  rcx, r9
0x1800026b2  xor     eax, eax
0x1800026b4  mov     [rcx], ax
0x1800026b7  test    rdx, rdx
  ... truncated ...
```
