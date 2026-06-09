# SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x180039ce0`
- end: `0x18003a196`
- name: `?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z`
- size: `1206`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003fa4`
- `0x180041560`

## callees

- `0x180029804`
- `0x180036080`
- `0x180039ce0`
- `0x180041618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039f61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039f61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a076`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a15c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a076`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a15c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a00f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a110`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a00f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a110`

## string_xrefs

- `0x180039d63`: `Software\Microsoft\Command Processor`
- `0x180039db0`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetDefaultHiveAppContainerSecurity_(
        const unsigned __int16 *a1,
        HKEY hKey,
        int (*a3)(HKEY, void *, void *, int, int))
{
  unsigned __int64 v6; // r14
  LSTATUS v7; // eax
  signed int v8; // edi
  int v9; // r8d
  signed int v10; // ebx
  LSTATUS v11; // eax
  __int64 v12; // r9
  unsigned __int64 v13; // rdi
  LSTATUS v14; // eax
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h]
  int v17[2]; // [rsp+58h] [rbp-A8h]
  const wchar_t *v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  const WCHAR *v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  int v26; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v30; // [rsp+A0h] [rbp-60h]
  int v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+ACh] [rbp-54h]
  const wchar_t *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  const wchar_t *v35; // [rsp+C0h] [rbp-40h]
  int v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+CCh] [rbp-34h]
  const wchar_t *v38; // [rsp+D0h] [rbp-30h]
  int v39; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+DCh] [rbp-24h]
  const wchar_t *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  const wchar_t *v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+FCh] [rbp-4h]
  const wchar_t *v46; // [rsp+100h] [rbp+0h]
  int v47; // [rsp+108h] [rbp+8h]
  int v48; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v49; // [rsp+110h] [rbp+10h]
  int v50; // [rsp+118h] [rbp+18h]
  int v51; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v52; // [rsp+120h] [rbp+20h]
  int v53; // [rsp+128h] [rbp+28h]
  int v54; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v55; // [rsp+130h] [rbp+30h]
  int v56; // [rsp+138h] [rbp+38h]
  int v57; // [rsp+13Ch] [rbp+3Ch]
  const wchar_t *v58; // [rsp+140h] [rbp+40h]
  int v59; // [rsp+148h] [rbp+48h]
  int v60; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v61; // [rsp+150h] [rbp+50h]
  int v62; // [rsp+158h] [rbp+58h]
  int v63; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v64; // [rsp+160h] [rbp+60h]
  __int64 v65; // [rsp+168h] [rbp+68h]
  const wchar_t *v66; // [rsp+170h] [rbp+70h]
  int v67; // [rsp+178h] [rbp+78h]
  int v68; // [rsp+17Ch] [rbp+7Ch]
  const wchar_t *v69; // [rsp+180h] [rbp+80h]
  int v70; // [rsp+188h] [rbp+88h]
  int v71; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v72; // [rsp+190h] [rbp+90h]
  __int64 v73; // [rsp+198h] [rbp+98h]
  const wchar_t *v74; // [rsp+1A0h] [rbp+A0h]
  int v75; // [rsp+1A8h] [rbp+A8h]
  int v76; // [rsp+1ACh] [rbp+ACh]
  __int64 v77; // [rsp+1B0h] [rbp+B0h]
  int v78; // [rsp+1B8h] [rbp+B8h]
  int v79; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v80; // [rsp+1C0h] [rbp+C0h]
  int v81; // [rsp+1C8h] [rbp+C8h]
  int v82; // [rsp+1CCh] [rbp+CCh]
  const wchar_t *v83; // [rsp+1D0h] [rbp+D0h]
  int v84; // [rsp+1D8h] [rbp+D8h]
  int v85; // [rsp+1DCh] [rbp+DCh]
  const wchar_t *v86; // [rsp+1E0h] [rbp+E0h]
  int v87; // [rsp+1E8h] [rbp+E8h]
  int v88; // [rsp+1ECh] [rbp+ECh]
  const wchar_t *v89; // [rsp+1F0h] [rbp+F0h]
  int v90; // [rsp+1F8h] [rbp+F8h]
  int v91; // [rsp+1FCh] [rbp+FCh]
  const wchar_t *v92; // [rsp+200h] [rbp+100h]
  int v93; // [rsp+208h] [rbp+108h]
  int v94; // [rsp+20Ch] [rbp+10Ch]
  LPCWSTR v95; // [rsp+210h] [rbp+110h]
  int v96; // [rsp+218h] [rbp+118h]
  const wchar_t *v97; // [rsp+220h] [rbp+120h]
  int v98; // [rsp+228h] [rbp+128h]
  const wchar_t *v99; // [rsp+230h] [rbp+130h]
  int v100; // [rsp+238h] [rbp+138h]
  HKEY hKeya; // [rsp+2A8h] [rbp+1A8h] BYREF

  lpSubKey = L"AppEvents";
  *(_QWORD *)v17 = 1;
  v18 = L"Control Panel";
  v19 = 1;
  v21 = L"Environment";
  v20 = 1;
  v24 = L"EUDC";
  v22 = 1;
  v27 = L"Keyboard Layout";
  v30 = L"Keyboard Layout\\Toggle";
  v33 = L"Software\\Microsoft\\Command Processor";
  v35 = L"Software\\Microsoft\\CTF";
  v38 = L"Software\\Microsoft\\Internet Explorer";
  v41 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AppHost";
  v43 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer";
  v46 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings";
  v49 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies";
  v52 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions";
  v55 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes";
  v58 = L"Software\\Microsoft\\Windows\\CurrentVersion\\WinTrust";
  v61 = L"Software\\Microsoft\\Windows\\Windows Error Reporting";
  v64 = L"Software\\Microsoft\\Windows NT";
  v66 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ICM";
  v69 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows";
  v23 = 1;
  v25 = 1;
  v26 = 1;
  v28 = 1;
  v29 = 1;
  v31 = 1;
  v32 = 1;
  v34 = 1;
  v36 = 1;
  v37 = 1;
  v39 = 1;
  v40 = 1;
  v42 = 1;
  v44 = 1;
  v45 = 1;
  v47 = 1;
  v48 = 1;
  v50 = 1;
  v51 = 1;
  v53 = 1;
  v54 = 1;
  v56 = 1;
  v57 = 1;
  v59 = 1;
  v60 = 1;
  v62 = 1;
  v63 = 1;
  v65 = 1;
  v67 = 1;
  v68 = 1;
  v70 = 1;
  v71 = 1;
  v73 = 1;
  v72 = L"Software\\Microsoft\\Wisp";
  v6 = 0;
  v75 = 1;
  v74 = L"Software\\Policies";
  v80 = L"Software";
  v83 = L"Software\\Microsoft";
  v86 = L"Software\\Microsoft\\Windows";
  v89 = L"Software\\Microsoft\\Windows\\CurrentVersion";
  v92 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Holographic";
  v76 = 1;
  v77 = 0;
  v78 = 0;
  v79 = 1;
  v81 = 0;
  v82 = 1;
  v84 = 0;
  v85 = 1;
  v87 = 0;
  v88 = 1;
  v90 = 0;
  v91 = 1;
  v93 = 0;
  v94 = 1;
  hKeya = 0;
  do
  {
    v7 = RegOpenKeyExW(hKey, *(LPCWSTR *)&v17[4 * v6 - 2], 0, 0x60019u, &hKeya);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 >= 0 )
    {
      v9 = v17[4 * v6];
      if ( v17[4 * v6 + 1] )
        SetHiveLpacSecurity_(a1, hKeya, v9, a3);
      else
        SetHiveAppContainerSecurity_(a1, hKeya, v9, a3);
      RegCloseKey(hKeya);
    }
    ++v6;
  }
  while ( v6 < 0x1C );
  v10 = 0;
  if ( v8 != -2147024894 )
    v10 = v8;
  if ( v10 >= 0 )
  {
    v11 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\SystemCertificates", 0, 0, 0, 0x60019u, 0, &hKeya, 0);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v10 < 0 )
    {
      if ( v10 == -2147024894 )
      {
LABEL_21:
        v96 = 1;
        v95 = L"Software\\Microsoft\\Speech_OneCore";
        v13 = 0;
        v98 = 0;
        v97 = L"Software\\Microsoft\\Speech";
        v99 = L"Software\\Microsoft\\Speech Virtual";
        v100 = 0;
        do
        {
          v14 = RegCreateKeyExW(hKey, (&v95)[2 * v13], 0, 0, 0, 0x60019u, 0, &hKeya, 0);
          v10 = v14;
          if ( v14 > 0 )
            v10 = (unsigned __int16)v14 | 0x80070000;
          if ( v10 >= 0 )
          {
            if ( v17[4 * v13 + 1] )
              SetHiveLpacSecurity_(a1, hKeya, 1, a3);
            else
              SetHiveAppContainerSecurity_(a1, hKeya, 1, a3);
            RegCloseKey(hKeya);
          }
          ++v13;
        }
        while ( v13 < 3 );
        if ( v10 == -2147024894 )
          return 0;
        return (unsigned int)v10;
      }
    }
    else
    {
      v12 = -1;
      do
        ++v12;
      while ( a1[v12] );
      SetHiveSecurity_(
        a1,
        L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;S-1-15-3-9)",
        L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;OICIID;KR;;;S-1-15-3-9)",
        v12 + 104,
        hKeya,
        1,
        a3);
      RegCloseKey(hKeya);
    }
    if ( v10 < 0 )
      return (unsigned int)v10;
    goto LABEL_21;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180039ce0  push    rbp
0x180039ce2  push    rbx
0x180039ce3  push    rsi
0x180039ce4  push    rdi
0x180039ce5  push    r12
0x180039ce7  push    r13
0x180039ce9  push    r14
0x180039ceb  push    r15
0x180039ced  lea     rbp, [rsp-148h]
0x180039cf5  sub     rsp, 248h
0x180039cfc  lea     rax, aAppevents; "AppEvents"
0x180039d03  mov     rsi, rcx
0x180039d06  mov     ecx, 1
0x180039d0b  mov     [rsp+280h+lpSubKey], rax
0x180039d10  lea     rax, aControlPanel; "Control Panel"
0x180039d17  mov     qword ptr [rsp+280h+var_228], rcx
0x180039d1c  mov     [rsp+280h+var_220], rax
0x180039d21  mov     r15, r8
0x180039d24  lea     rax, aEnvironment; "Environment"
0x180039d2b  mov     [rsp+280h+var_218], ecx
0x180039d2f  mov     [rsp+280h+var_210], rax
0x180039d34  mov     r12, rdx
0x180039d37  lea     rax, aEudc; "EUDC"
0x180039d3e  mov     [rsp+280h+var_214], ecx
0x180039d42  mov     [rbp+180h+var_200], rax
0x180039d46  xor     r13d, r13d
0x180039d49  lea     rax, aKeyboardLayout; "Keyboard Layout"
0x180039d50  mov     [rsp+280h+var_208], ecx
0x180039d54  mov     [rbp+180h+var_1F0], rax
0x180039d58  lea     rax, aKeyboardLayout_0; "Keyboard Layout\\Toggle"
0x180039d5f  mov     [rbp+180h+var_1E0], rax
0x180039d63  lea     rax, aSoftwareMicros_24; "Software\\Microsoft\\Command Processor"
0x180039d6a  mov     [rbp+180h+var_1D0], rax
0x180039d6e  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\CTF"
0x180039d75  mov     [rbp+180h+var_1C0], rax
0x180039d79  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Internet Explorer"
0x180039d80  mov     [rbp+180h+var_1B0], rax
0x180039d84  lea     rax, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039d8b  mov     [rbp+180h+var_1A0], rax
0x180039d8f  lea     rax, aSoftwareMicros_29; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039d96  mov     [rbp+180h+var_190], rax
0x180039d9a  lea     rax, aSoftwareMicros_30; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039da1  mov     [rbp+180h+var_180], rax
0x180039da5  lea     rax, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039dac  mov     [rbp+180h+var_170], rax
0x180039db0  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039db7  mov     [rbp+180h+var_160], rax
0x180039dbb  lea     rax, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039dc2  mov     [rbp+180h+var_150], rax
0x180039dc6  lea     rax, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039dcd  mov     [rbp+180h+var_140], rax
0x180039dd1  lea     rax, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\Windows E"...
0x180039dd8  mov     [rbp+180h+var_130], rax
0x180039ddc  lea     rax, aSoftwareMicros_36; "Software\\Microsoft\\Windows NT"
0x180039de3  mov     [rbp+180h+var_120], rax
0x180039de7  lea     rax, aSoftwareMicros_26; "Software\\Microsoft\\Windows NT\\Curren"...
0x180039dee  mov     [rbp+180h+var_110], rax
0x180039df2  lea     rax, aSoftwareMicros_7; "Software\\Microsoft\\Windows NT\\Curren"...
0x180039df9  mov     [rbp+180h+var_100], rax
0x180039e00  mov     [rsp+280h+var_204], ecx
0x180039e04  mov     [rbp+180h+var_1F8], ecx
0x180039e07  mov     [rbp+180h+var_1F4], ecx
0x180039e0a  mov     [rbp+180h+var_1E8], ecx
0x180039e0d  mov     [rbp+180h+var_1E4], ecx
0x180039e10  mov     [rbp+180h+var_1D8], ecx
0x180039e13  mov     [rbp+180h+var_1D4], ecx
0x180039e16  mov     [rbp+180h+var_1C8], rcx
0x180039e1a  mov     [rbp+180h+var_1B8], ecx
0x180039e1d  mov     [rbp+180h+var_1B4], ecx
0x180039e20  mov     [rbp+180h+var_1A8], ecx
0x180039e23  mov     [rbp+180h+var_1A4], ecx
0x180039e26  mov     [rbp+180h+var_198], rcx
0x180039e2a  mov     [rbp+180h+var_188], ecx
0x180039e2d  mov     [rbp+180h+var_184], ecx
0x180039e30  mov     [rbp+180h+var_178], ecx
0x180039e33  mov     [rbp+180h+var_174], ecx
0x180039e36  mov     [rbp+180h+var_168], ecx
0x180039e39  mov     [rbp+180h+var_164], ecx
0x180039e3c  mov     [rbp+180h+var_158], ecx
0x180039e3f  mov     [rbp+180h+var_154], ecx
0x180039e42  mov     [rbp+180h+var_148], ecx
0x180039e45  mov     [rbp+180h+var_144], ecx
0x180039e48  mov     [rbp+180h+var_138], ecx
0x180039e4b  mov     [rbp+180h+var_134], ecx
0x180039e4e  mov     [rbp+180h+var_128], ecx
0x180039e51  mov     [rbp+180h+var_124], ecx
0x180039e54  mov     [rbp+180h+var_118], rcx
0x180039e58  mov     [rbp+180h+var_108], ecx
0x180039e5b  mov     [rbp+180h+var_104], ecx
0x180039e5e  mov     [rbp+180h+var_F8], ecx
0x180039e64  mov     [rbp+180h+var_F4], ecx
0x180039e6a  lea     rax, aSoftwareMicros_10; "Software\\Microsoft\\Wisp"
0x180039e71  mov     [rbp+180h+var_E8], rcx
0x180039e78  mov     [rbp+180h+var_F0], rax
0x180039e7f  mov     r14d, r13d
0x180039e82  lea     rax, aSoftwarePolici_0; "Software\\Policies"
0x180039e89  mov     [rbp+180h+var_D8], ecx
0x180039e8f  mov     [rbp+180h+var_E0], rax
0x180039e96  lea     rax, aSoftware; "Software"
0x180039e9d  mov     [rbp+180h+var_C0], rax
0x180039ea4  lea     rax, aSoftwareMicros_4; "Software\\Microsoft"
0x180039eab  mov     [rbp+180h+var_B0], rax
0x180039eb2  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows"
0x180039eb9  mov     [rbp+180h+var_A0], rax
0x180039ec0  lea     rax, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039ec7  mov     [rbp+180h+var_90], rax
0x180039ece  lea     rax, aSoftwareMicros_28; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039ed5  mov     [rbp+180h+var_80], rax
0x180039edc  mov     [rbp+180h+var_D4], ecx
0x180039ee2  mov     [rbp+180h+var_D0], r13
0x180039ee9  mov     [rbp+180h+var_C8], r13d
0x180039ef0  mov     [rbp+180h+var_C4], ecx
0x180039ef6  mov     [rbp+180h+var_B8], r13d
0x180039efd  mov     [rbp+180h+var_B4], ecx
0x180039f03  mov     [rbp+180h+var_A8], r13d
0x180039f0a  mov     [rbp+180h+var_A4], ecx
0x180039f10  mov     [rbp+180h+var_98], r13d
0x180039f17  mov     [rbp+180h+var_94], ecx
0x180039f1d  mov     [rbp+180h+var_88], r13d
0x180039f24  mov     [rbp+180h+var_84], ecx
0x180039f2a  mov     [rbp+180h+var_78], r13d
0x180039f31  mov     [rbp+180h+var_74], ecx
0x180039f37  mov     [rbp+180h+hKey], r13
0x180039f3e  lea     rax, [rbp+180h+hKey]
0x180039f45  mov     rbx, r14
0x180039f48  add     rbx, rbx
0x180039f4b  mov     [rsp+280h+phkResult], rax; phkResult
0x180039f50  mov     r9d, 60019h; samDesired
0x180039f56  xor     r8d, r8d; ulOptions
0x180039f59  mov     rcx, r12; hKey
0x180039f5c  mov     rdx, [rsp+rbx*8+280h+lpSubKey]; lpSubKey
0x180039f61  call    cs:__imp_RegOpenKeyExW
0x180039f68  nop     dword ptr [rax+rax+00h]
0x180039f6d  mov     edi, eax
0x180039f6f  test    eax, eax
0x180039f71  jle     short loc_180039F7C
0x180039f73  movzx   edi, ax
0x180039f76  or      edi, 80070000h
0x180039f7c  test    edi, edi
0x180039f7e  js      short loc_180039FB8
0x180039f80  mov     r9, r15; int (*)(HKEY, void *, void *, int, int)
0x180039f83  mov     r8d, [rsp+rbx*8+280h+var_228]; int
0x180039f88  mov     rcx, rsi; unsigned __int16 *
0x180039f8b  mov     rdx, [rbp+180h+hKey]; HKEY
0x180039f92  cmp     [rsp+rbx*8+280h+var_228+4], r13d
0x180039f97  jz      short loc_180039FA0
0x180039f99  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x180039f9e  jmp     short loc_180039FA5
0x180039fa0  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x180039fa5  mov     rcx, [rbp+180h+hKey]; hKey
0x180039fac  call    cs:__imp_RegCloseKey
0x180039fb3  nop     dword ptr [rax+rax+00h]
0x180039fb8  inc     r14
0x180039fbb  cmp     r14, 1Ch
0x180039fbf  jb      loc_180039F3E
0x180039fc5  mov     r14d, 80070002h
0x180039fcb  mov     ebx, r13d
0x180039fce  cmp     edi, r14d
0x180039fd1  cmovnz  ebx, edi
0x180039fd4  test    ebx, ebx
0x180039fd6  js      loc_18003A17F
0x180039fdc  mov     [rsp+280h+lpdwDisposition], r13; lpdwDisposition
0x180039fe1  lea     rax, [rbp+180h+hKey]
0x180039fe8  mov     [rsp+280h+var_248], rax; phkResult
0x180039fed  lea     rdx, aSoftwareMicros_38; "Software\\Microsoft\\SystemCertificates"
0x180039ff4  mov     [rsp+280h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180039ff9  xor     r9d, r9d; lpClass
0x180039ffc  mov     [rsp+280h+samDesired], 60019h; samDesired
0x18003a004  xor     r8d, r8d; Reserved
0x18003a007  mov     rcx, r12; hKey
0x18003a00a  mov     dword ptr [rsp+280h+phkResult], r13d; dwOptions
0x18003a00f  call    cs:__imp_RegCreateKeyExW
0x18003a016  nop     dword ptr [rax+rax+00h]
0x18003a01b  mov     ebx, eax
0x18003a01d  test    eax, eax
0x18003a01f  jle     short loc_18003A02A
0x18003a021  movzx   ebx, ax
0x18003a024  or      ebx, 80070000h
0x18003a02a  test    ebx, ebx
0x18003a02c  js      short loc_18003A084
0x18003a02e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003a032  inc     r9
0x18003a035  cmp     [rsi+r9*2], r13w
0x18003a03a  jnz     short loc_18003A032
0x18003a03c  mov     rax, [rbp+180h+hKey]
0x18003a043  lea     r8, ?c_szInherited@?1??SetHiveSharedUserCertSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x18003a04a  mov     [rsp+280h+lpSecurityAttributes], r15; int (*)(HKEY, void *, void *, int, int)
0x18003a04f  lea     rdx, ?c_szNonInherited@?1??SetHiveSharedUserCertSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x18003a056  mov     [rsp+280h+samDesired], 1; int
0x18003a05e  add     r9, 68h ; 'h'; unsigned __int64
0x18003a062  mov     rcx, rsi; unsigned __int16 *
0x18003a065  mov     [rsp+280h+phkResult], rax; HKEY
0x18003a06a  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18003a06f  mov     rcx, [rbp+180h+hKey]; hKey
0x18003a076  call    cs:__imp_RegCloseKey
0x18003a07d  nop     dword ptr [rax+rax+00h]
0x18003a082  jmp     short loc_18003A089
0x18003a084  cmp     ebx, r14d
0x18003a087  jz      short loc_18003A091
0x18003a089  test    ebx, ebx
0x18003a08b  js      loc_18003A17F
0x18003a091  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Speech_OneCore"
0x18003a098  mov     [rbp+180h+var_68], 1
0x18003a0a2  mov     [rbp+180h+var_70], rax
0x18003a0a9  mov     rdi, r13
0x18003a0ac  lea     rax, aSoftwareMicros_20; "Software\\Microsoft\\Speech"
0x18003a0b3  mov     [rbp+180h+var_58], r13d
0x18003a0ba  mov     [rbp+180h+var_60], rax
0x18003a0c1  lea     rax, aSoftwareMicros_15; "Software\\Microsoft\\Speech Virtual"
0x18003a0c8  mov     [rbp+180h+var_50], rax
0x18003a0cf  mov     [rbp+180h+var_48], r13d
0x18003a0d6  mov     [rsp+280h+lpdwDisposition], r13; lpdwDisposition
0x18003a0db  lea     rax, [rbp+180h+hKey]
0x18003a0e2  mov     [rsp+280h+var_248], rax; phkResult
0x18003a0e7  mov     r14, rdi
0x18003a0ea  mov     [rsp+280h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003a0ef  add     r14, r14
0x18003a0f2  mov     [rsp+280h+samDesired], 60019h; samDesired
0x18003a0fa  xor     r9d, r9d; lpClass
0x18003a0fd  xor     r8d, r8d; Reserved
0x18003a100  mov     dword ptr [rsp+280h+phkResult], r13d; dwOptions
0x18003a105  mov     rcx, r12; hKey
0x18003a108  mov     rdx, [rbp+r14*8+180h+var_70]; lpSubKey
0x18003a110  call    cs:__imp_RegCreateKeyExW
0x18003a117  nop     dword ptr [rax+rax+00h]
0x18003a11c  mov     ebx, eax
0x18003a11e  test    eax, eax
0x18003a120  jle     short loc_18003A12B
0x18003a122  movzx   ebx, ax
0x18003a125  or      ebx, 80070000h
0x18003a12b  test    ebx, ebx
0x18003a12d  js      short loc_18003A168
0x18003a12f  mov     r9, r15; int (*)(HKEY, void *, void *, int, int)
0x18003a132  mov     rdx, [rbp+180h+hKey]; HKEY
0x18003a139  mov     r8d, 1; int
0x18003a13f  mov     rcx, rsi; unsigned __int16 *
0x18003a142  cmp     [rsp+r14*8+280h+var_228+4], r13d
0x18003a147  jz      short loc_18003A150
0x18003a149  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18003a14e  jmp     short loc_18003A155
0x18003a150  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18003a155  mov     rcx, [rbp+180h+hKey]; hKey
0x18003a15c  call    cs:__imp_RegCloseKey
0x18003a163  nop     dword ptr [rax+rax+00h]
0x18003a168  inc     rdi
0x18003a16b  cmp     rdi, 3
0x18003a16f  jb      loc_18003A0D6
0x18003a175  cmp     ebx, 80070002h
0x18003a17b  cmovz   ebx, r13d
0x18003a17f  mov     eax, ebx
0x18003a181  add     rsp, 248h
0x18003a188  pop     r15
0x18003a18a  pop     r14
0x18003a18c  pop     r13
0x18003a18e  pop     r12
0x18003a190  pop     rdi
0x18003a191  pop     rsi
0x18003a192  pop     rbx
0x18003a193  pop     rbp
0x18003a194  retn
```
