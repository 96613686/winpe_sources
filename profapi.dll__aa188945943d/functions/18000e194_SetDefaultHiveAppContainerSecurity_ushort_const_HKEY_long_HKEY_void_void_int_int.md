# SetDefaultHiveAppContainerSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x18000e194`
- end: `0x18000e637`
- name: `?SetDefaultHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z`
- size: `1187`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000df6c`

## callees

- `0x18000df14`
- `0x18000e194`
- `0x1800121a8`
- `0x1800121fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e4da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e5c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e4da`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e5c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e481`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e43f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e43f`

## string_xrefs

- `0x18000e217`: `Software\Microsoft\Command Processor`
- `0x18000e264`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions`

## pseudocode

```c
__int64 __fastcall SetDefaultHiveAppContainerSecurity_(
        const unsigned __int16 *a1,
        HKEY hKey,
        int (*a3)(HKEY, void *, void *, int, int))
{
  unsigned __int64 v5; // r14
  LSTATUS v6; // eax
  int (*v7)(HKEY, void *, void *, int, int); // r9
  signed int v8; // edi
  int v9; // r8d
  signed int v10; // ebx
  LSTATUS v11; // eax
  __int64 v12; // r9
  unsigned __int64 v13; // rdi
  LSTATUS v14; // eax
  int (*v15)(HKEY, void *, void *, int, int); // r9
  int (*lpSecurityAttributes)(HKEY, void *, void *, int, int); // [rsp+30h] [rbp-D0h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h]
  int v19[2]; // [rsp+58h] [rbp-A8h]
  const wchar_t *v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+6Ch] [rbp-94h]
  const WCHAR *v23; // [rsp+70h] [rbp-90h]
  int v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+7Ch] [rbp-84h]
  const wchar_t *v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  int v28; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+ACh] [rbp-54h]
  const wchar_t *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  const wchar_t *v37; // [rsp+C0h] [rbp-40h]
  int v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+CCh] [rbp-34h]
  const wchar_t *v40; // [rsp+D0h] [rbp-30h]
  int v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+DCh] [rbp-24h]
  const wchar_t *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  const wchar_t *v45; // [rsp+F0h] [rbp-10h]
  int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+FCh] [rbp-4h]
  const wchar_t *v48; // [rsp+100h] [rbp+0h]
  int v49; // [rsp+108h] [rbp+8h]
  int v50; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v51; // [rsp+110h] [rbp+10h]
  int v52; // [rsp+118h] [rbp+18h]
  int v53; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+128h] [rbp+28h]
  int v56; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+138h] [rbp+38h]
  int v59; // [rsp+13Ch] [rbp+3Ch]
  const wchar_t *v60; // [rsp+140h] [rbp+40h]
  int v61; // [rsp+148h] [rbp+48h]
  int v62; // [rsp+14Ch] [rbp+4Ch]
  const wchar_t *v63; // [rsp+150h] [rbp+50h]
  int v64; // [rsp+158h] [rbp+58h]
  int v65; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v66; // [rsp+160h] [rbp+60h]
  __int64 v67; // [rsp+168h] [rbp+68h]
  const wchar_t *v68; // [rsp+170h] [rbp+70h]
  int v69; // [rsp+178h] [rbp+78h]
  int v70; // [rsp+17Ch] [rbp+7Ch]
  const wchar_t *v71; // [rsp+180h] [rbp+80h]
  int v72; // [rsp+188h] [rbp+88h]
  int v73; // [rsp+18Ch] [rbp+8Ch]
  const wchar_t *v74; // [rsp+190h] [rbp+90h]
  __int64 v75; // [rsp+198h] [rbp+98h]
  const wchar_t *v76; // [rsp+1A0h] [rbp+A0h]
  int v77; // [rsp+1A8h] [rbp+A8h]
  int v78; // [rsp+1ACh] [rbp+ACh]
  __int64 v79; // [rsp+1B0h] [rbp+B0h]
  int v80; // [rsp+1B8h] [rbp+B8h]
  int v81; // [rsp+1BCh] [rbp+BCh]
  const wchar_t *v82; // [rsp+1C0h] [rbp+C0h]
  int v83; // [rsp+1C8h] [rbp+C8h]
  int v84; // [rsp+1CCh] [rbp+CCh]
  const wchar_t *v85; // [rsp+1D0h] [rbp+D0h]
  int v86; // [rsp+1D8h] [rbp+D8h]
  int v87; // [rsp+1DCh] [rbp+DCh]
  const wchar_t *v88; // [rsp+1E0h] [rbp+E0h]
  int v89; // [rsp+1E8h] [rbp+E8h]
  int v90; // [rsp+1ECh] [rbp+ECh]
  const WCHAR *v91; // [rsp+1F0h] [rbp+F0h]
  int v92; // [rsp+1F8h] [rbp+F8h]
  int v93; // [rsp+1FCh] [rbp+FCh]
  const wchar_t *v94; // [rsp+200h] [rbp+100h]
  int v95; // [rsp+208h] [rbp+108h]
  int v96; // [rsp+20Ch] [rbp+10Ch]
  LPCWSTR v97; // [rsp+210h] [rbp+110h]
  int v98; // [rsp+218h] [rbp+118h]
  const wchar_t *v99; // [rsp+220h] [rbp+120h]
  int v100; // [rsp+228h] [rbp+128h]
  const wchar_t *v101; // [rsp+230h] [rbp+130h]
  int v102; // [rsp+238h] [rbp+138h]
  HKEY hKeya; // [rsp+2A0h] [rbp+1A0h] BYREF

  lpSubKey = L"AppEvents";
  *(_QWORD *)v19 = 1;
  v20 = L"Control Panel";
  v21 = 1;
  v23 = L"Environment";
  v22 = 1;
  v26 = L"EUDC";
  v29 = L"Keyboard Layout";
  v32 = L"Keyboard Layout\\Toggle";
  v35 = L"Software\\Microsoft\\Command Processor";
  v37 = L"Software\\Microsoft\\CTF";
  v40 = L"Software\\Microsoft\\Internet Explorer";
  v43 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AppHost";
  v45 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer";
  v48 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings";
  v51 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies";
  v54 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions";
  v57 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes";
  v60 = L"Software\\Microsoft\\Windows\\CurrentVersion\\WinTrust";
  v63 = L"Software\\Microsoft\\Windows\\Windows Error Reporting";
  v66 = L"Software\\Microsoft\\Windows NT";
  v68 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ICM";
  v71 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows";
  v24 = 1;
  v25 = 1;
  v27 = 1;
  v28 = 1;
  v30 = 1;
  v31 = 1;
  v33 = 1;
  v34 = 1;
  v36 = 1;
  v38 = 1;
  v39 = 1;
  v41 = 1;
  v42 = 1;
  v44 = 1;
  v46 = 1;
  v47 = 1;
  v49 = 1;
  v50 = 1;
  v52 = 1;
  v53 = 1;
  v55 = 1;
  v56 = 1;
  v58 = 1;
  v59 = 1;
  v61 = 1;
  v62 = 1;
  v64 = 1;
  v65 = 1;
  v67 = 1;
  v69 = 1;
  v70 = 1;
  v72 = 1;
  v73 = 1;
  v74 = L"Software\\Microsoft\\Wisp";
  v5 = 0;
  v75 = 1;
  v76 = L"Software\\Policies";
  v82 = L"Software";
  v85 = L"Software\\Microsoft";
  v88 = L"Software\\Microsoft\\Windows";
  v91 = L"Software\\Microsoft\\Windows\\CurrentVersion";
  v94 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Holographic";
  v77 = 1;
  v78 = 1;
  v79 = 0;
  v80 = 0;
  v81 = 1;
  v83 = 0;
  v84 = 1;
  v86 = 0;
  v87 = 1;
  v89 = 0;
  v90 = 1;
  v92 = 0;
  v93 = 1;
  v95 = 0;
  v96 = 1;
  hKeya = 0;
  do
  {
    v6 = RegOpenKeyExW(hKey, *(LPCWSTR *)&v19[4 * v5 - 2], 0, 0x60019u, &hKeya);
    v8 = v6;
    if ( v6 > 0 )
      v8 = (unsigned __int16)v6 | 0x80070000;
    if ( v8 >= 0 )
    {
      v9 = v19[4 * v5];
      if ( v19[4 * v5 + 1] )
        SetHiveLpacSecurity_(a1, hKeya, v9, v7);
      else
        SetHiveAppContainerSecurity_(a1, hKeya, v9, v7);
      RegCloseKey(hKeya);
    }
    ++v5;
  }
  while ( v5 < 0x1C );
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
        v98 = 1;
        v97 = L"Software\\Microsoft\\Speech_OneCore";
        v13 = 0;
        v100 = 0;
        v99 = L"Software\\Microsoft\\Speech";
        v101 = L"Software\\Microsoft\\Speech Virtual";
        v102 = 0;
        do
        {
          v14 = RegCreateKeyExW(hKey, (&v97)[2 * v13], 0, 0, 0, 0x60019u, 0, &hKeya, 0);
          v10 = v14;
          if ( v14 > 0 )
            v10 = (unsigned __int16)v14 | 0x80070000;
          if ( v10 >= 0 )
          {
            if ( v19[4 * v13 + 1] )
              SetHiveLpacSecurity_(a1, hKeya, 1, v15);
            else
              SetHiveAppContainerSecurity_(a1, hKeya, 1, v15);
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
        lpSecurityAttributes);
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
0x18000e194  mov     [rsp-8+hKey], r8
0x18000e199  push    rbp
0x18000e19a  push    rbx
0x18000e19b  push    rsi
0x18000e19c  push    rdi
0x18000e19d  push    r12
0x18000e19f  push    r13
0x18000e1a1  push    r14
0x18000e1a3  push    r15
0x18000e1a5  lea     rbp, [rsp-148h]
0x18000e1ad  sub     rsp, 248h
0x18000e1b4  mov     r13d, 1
0x18000e1ba  lea     rax, aAppevents; "AppEvents"
0x18000e1c1  mov     [rsp+280h+lpSubKey], rax
0x18000e1c6  mov     r15, rdx
0x18000e1c9  lea     rax, aControlPanel; "Control Panel"
0x18000e1d0  mov     qword ptr [rsp+280h+var_228], r13
0x18000e1d5  mov     [rsp+280h+var_220], rax
0x18000e1da  mov     rsi, rcx
0x18000e1dd  lea     rax, aEnvironment; "Environment"
0x18000e1e4  mov     [rsp+280h+var_218], r13d
0x18000e1e9  mov     [rsp+280h+var_210], rax
0x18000e1ee  xor     r12d, r12d
0x18000e1f1  lea     rax, aEudc; "EUDC"
0x18000e1f8  mov     [rsp+280h+var_214], r13d
0x18000e1fd  mov     [rbp+180h+var_200], rax
0x18000e201  lea     rax, aKeyboardLayout; "Keyboard Layout"
0x18000e208  mov     [rbp+180h+var_1F0], rax
0x18000e20c  lea     rax, aKeyboardLayout_0; "Keyboard Layout\\Toggle"
0x18000e213  mov     [rbp+180h+var_1E0], rax
0x18000e217  lea     rax, aSoftwareMicros_18; "Software\\Microsoft\\Command Processor"
0x18000e21e  mov     [rbp+180h+var_1D0], rax
0x18000e222  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\CTF"
0x18000e229  mov     [rbp+180h+var_1C0], rax
0x18000e22d  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Internet Explorer"
0x18000e234  mov     [rbp+180h+var_1B0], rax
0x18000e238  lea     rax, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e23f  mov     [rbp+180h+var_1A0], rax
0x18000e243  lea     rax, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e24a  mov     [rbp+180h+var_190], rax
0x18000e24e  lea     rax, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e255  mov     [rbp+180h+var_180], rax
0x18000e259  lea     rax, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e260  mov     [rbp+180h+var_170], rax
0x18000e264  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e26b  mov     [rbp+180h+var_160], rax
0x18000e26f  lea     rax, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e276  mov     [rbp+180h+var_150], rax
0x18000e27a  lea     rax, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e281  mov     [rbp+180h+var_140], rax
0x18000e285  lea     rax, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\Windows E"...
0x18000e28c  mov     [rbp+180h+var_130], rax
0x18000e290  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows NT"
0x18000e297  mov     [rbp+180h+var_120], rax
0x18000e29b  lea     rax, aSoftwareMicros_19; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000e2a2  mov     [rbp+180h+var_110], rax
0x18000e2a6  lea     rax, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000e2ad  mov     [rbp+180h+var_100], rax
0x18000e2b4  lea     rax, aSoftwareMicros_7; "Software\\Microsoft\\Wisp"
0x18000e2bb  mov     [rsp+280h+var_208], r13d
0x18000e2c0  mov     [rsp+280h+var_204], r13d
0x18000e2c5  mov     [rbp+180h+var_1F8], r13d
0x18000e2c9  mov     [rbp+180h+var_1F4], r13d
0x18000e2cd  mov     [rbp+180h+var_1E8], r13d
0x18000e2d1  mov     [rbp+180h+var_1E4], r13d
0x18000e2d5  mov     [rbp+180h+var_1D8], r13d
0x18000e2d9  mov     [rbp+180h+var_1D4], r13d
0x18000e2dd  mov     [rbp+180h+var_1C8], r13
0x18000e2e1  mov     [rbp+180h+var_1B8], r13d
0x18000e2e5  mov     [rbp+180h+var_1B4], r13d
0x18000e2e9  mov     [rbp+180h+var_1A8], r13d
0x18000e2ed  mov     [rbp+180h+var_1A4], r13d
0x18000e2f1  mov     [rbp+180h+var_198], r13
0x18000e2f5  mov     [rbp+180h+var_188], r13d
0x18000e2f9  mov     [rbp+180h+var_184], r13d
0x18000e2fd  mov     [rbp+180h+var_178], r13d
0x18000e301  mov     [rbp+180h+var_174], r13d
0x18000e305  mov     [rbp+180h+var_168], r13d
0x18000e309  mov     [rbp+180h+var_164], r13d
0x18000e30d  mov     [rbp+180h+var_158], r13d
0x18000e311  mov     [rbp+180h+var_154], r13d
0x18000e315  mov     [rbp+180h+var_148], r13d
0x18000e319  mov     [rbp+180h+var_144], r13d
0x18000e31d  mov     [rbp+180h+var_138], r13d
0x18000e321  mov     [rbp+180h+var_134], r13d
0x18000e325  mov     [rbp+180h+var_128], r13d
0x18000e329  mov     [rbp+180h+var_124], r13d
0x18000e32d  mov     [rbp+180h+var_118], r13
0x18000e331  mov     [rbp+180h+var_108], r13d
0x18000e335  mov     [rbp+180h+var_104], r13d
0x18000e339  mov     [rbp+180h+var_F8], r13d
0x18000e340  mov     [rbp+180h+var_F4], r13d
0x18000e347  mov     [rbp+180h+var_F0], rax
0x18000e34e  mov     r14d, r12d
0x18000e351  lea     rax, aSoftwarePolici; "Software\\Policies"
0x18000e358  mov     [rbp+180h+var_E8], r13
0x18000e35f  mov     [rbp+180h+var_E0], rax
0x18000e366  lea     rax, aSoftware_0; "Software"
0x18000e36d  mov     [rbp+180h+var_C0], rax
0x18000e374  lea     rax, aSoftwareMicros_2; "Software\\Microsoft"
0x18000e37b  mov     [rbp+180h+var_B0], rax
0x18000e382  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\Windows"
0x18000e389  mov     [rbp+180h+var_A0], rax
0x18000e390  lea     rax, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e397  mov     [rbp+180h+var_90], rax
0x18000e39e  lea     rax, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000e3a5  mov     [rbp+180h+var_80], rax
0x18000e3ac  mov     [rbp+180h+var_D8], r13d
0x18000e3b3  mov     [rbp+180h+var_D4], r13d
0x18000e3ba  mov     [rbp+180h+var_D0], r12
0x18000e3c1  mov     [rbp+180h+var_C8], r12d
0x18000e3c8  mov     [rbp+180h+var_C4], r13d
0x18000e3cf  mov     [rbp+180h+var_B8], r12d
0x18000e3d6  mov     [rbp+180h+var_B4], r13d
0x18000e3dd  mov     [rbp+180h+var_A8], r12d
0x18000e3e4  mov     [rbp+180h+var_A4], r13d
0x18000e3eb  mov     [rbp+180h+var_98], r12d
0x18000e3f2  mov     [rbp+180h+var_94], r13d
0x18000e3f9  mov     [rbp+180h+var_88], r12d
0x18000e400  mov     [rbp+180h+var_84], r13d
0x18000e407  mov     [rbp+180h+var_78], r12d
0x18000e40e  mov     [rbp+180h+var_74], r13d
0x18000e415  mov     [rbp+180h+hKey], r12
0x18000e41c  lea     rax, [rbp+180h+hKey]
0x18000e423  mov     rbx, r14
0x18000e426  add     rbx, rbx
0x18000e429  mov     [rsp+280h+phkResult], rax; phkResult
0x18000e42e  mov     r9d, 60019h; samDesired
0x18000e434  xor     r8d, r8d; ulOptions
0x18000e437  mov     rcx, r15; hKey
0x18000e43a  mov     rdx, [rsp+rbx*8+280h+lpSubKey]; lpSubKey
0x18000e43f  call    cs:__imp_RegOpenKeyExW
0x18000e445  mov     edi, eax
0x18000e447  test    eax, eax
0x18000e449  jle     short loc_18000E454
0x18000e44b  movzx   edi, ax
0x18000e44e  or      edi, 80070000h
0x18000e454  test    edi, edi
0x18000e456  js      short loc_18000E487
0x18000e458  mov     rcx, rsi; unsigned __int16 *
0x18000e45b  mov     r8d, [rsp+rbx*8+280h+var_228]; int
0x18000e460  mov     rdx, [rbp+180h+hKey]; HKEY
0x18000e467  cmp     [rsp+rbx*8+280h+var_228+4], r12d
0x18000e46c  jz      short loc_18000E475
0x18000e46e  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e473  jmp     short loc_18000E47A
0x18000e475  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e47a  mov     rcx, [rbp+180h+hKey]; hKey
0x18000e481  call    cs:__imp_RegCloseKey
0x18000e487  add     r14, r13
0x18000e48a  cmp     r14, 1Ch
0x18000e48e  jb      short loc_18000E41C
0x18000e490  mov     r14d, 80070002h
0x18000e496  mov     ebx, r12d
0x18000e499  cmp     edi, r14d
0x18000e49c  cmovnz  ebx, edi
0x18000e49f  test    ebx, ebx
0x18000e4a1  js      loc_18000E621
0x18000e4a7  mov     [rsp+280h+lpdwDisposition], r12; lpdwDisposition
0x18000e4ac  lea     rax, [rbp+180h+hKey]
0x18000e4b3  mov     [rsp+280h+var_248], rax; phkResult
0x18000e4b8  lea     rdx, aSoftwareMicros_28; "Software\\Microsoft\\SystemCertificates"
0x18000e4bf  mov     [rsp+280h+lpSecurityAttributes], r12; int (*)(HKEY, void *, void *, int, int)
0x18000e4c4  xor     r9d, r9d; lpClass
0x18000e4c7  mov     [rsp+280h+samDesired], 60019h; samDesired
0x18000e4cf  xor     r8d, r8d; Reserved
0x18000e4d2  mov     rcx, r15; hKey
0x18000e4d5  mov     dword ptr [rsp+280h+phkResult], r12d; dwOptions
0x18000e4da  call    cs:__imp_RegCreateKeyExW
0x18000e4e0  mov     ebx, eax
0x18000e4e2  test    eax, eax
0x18000e4e4  jle     short loc_18000E4EF
0x18000e4e6  movzx   ebx, ax
0x18000e4e9  or      ebx, 80070000h
0x18000e4ef  test    ebx, ebx
0x18000e4f1  js      short loc_18000E53B
0x18000e4f3  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e4f7  inc     r9
0x18000e4fa  cmp     [rsi+r9*2], r12w
0x18000e4ff  jnz     short loc_18000E4F7
0x18000e501  mov     rax, [rbp+180h+hKey]
0x18000e508  lea     r8, ?c_szInherited@?1??SetHiveSharedUserCertSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x18000e50f  add     r9, 68h ; 'h'; unsigned __int64
0x18000e513  mov     [rsp+280h+samDesired], r13d; int
0x18000e518  lea     rdx, ?c_szNonInherited@?1??SetHiveSharedUserCertSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z@4QBGB; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x18000e51f  mov     [rsp+280h+phkResult], rax; HKEY
0x18000e524  mov     rcx, rsi; unsigned __int16 *
0x18000e527  call    ?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z; SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e52c  mov     rcx, [rbp+180h+hKey]; hKey
0x18000e533  call    cs:__imp_RegCloseKey
0x18000e539  jmp     short loc_18000E540
0x18000e53b  cmp     ebx, r14d
0x18000e53e  jz      short loc_18000E548
0x18000e540  test    ebx, ebx
0x18000e542  js      loc_18000E621
0x18000e548  lea     rax, aSoftwareMicros_5; "Software\\Microsoft\\Speech_OneCore"
0x18000e54f  mov     [rbp+180h+var_68], r13d
0x18000e556  mov     [rbp+180h+var_70], rax
0x18000e55d  mov     rdi, r12
0x18000e560  lea     rax, aSoftwareMicros_15; "Software\\Microsoft\\Speech"
0x18000e567  mov     [rbp+180h+var_58], r12d
0x18000e56e  mov     [rbp+180h+var_60], rax
0x18000e575  lea     rax, aSoftwareMicros_10; "Software\\Microsoft\\Speech Virtual"
0x18000e57c  mov     [rbp+180h+var_50], rax
0x18000e583  mov     [rbp+180h+var_48], r12d
0x18000e58a  mov     [rsp+280h+lpdwDisposition], r12; lpdwDisposition
0x18000e58f  lea     rax, [rbp+180h+hKey]
0x18000e596  mov     [rsp+280h+var_248], rax; phkResult
0x18000e59b  mov     r14, rdi
0x18000e59e  mov     [rsp+280h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000e5a3  add     r14, r14
0x18000e5a6  mov     [rsp+280h+samDesired], 60019h; samDesired
0x18000e5ae  xor     r9d, r9d; lpClass
0x18000e5b1  xor     r8d, r8d; Reserved
0x18000e5b4  mov     dword ptr [rsp+280h+phkResult], r12d; dwOptions
0x18000e5b9  mov     rcx, r15; hKey
0x18000e5bc  mov     rdx, [rbp+r14*8+180h+var_70]; lpSubKey
0x18000e5c4  call    cs:__imp_RegCreateKeyExW
0x18000e5ca  mov     ebx, eax
0x18000e5cc  test    eax, eax
0x18000e5ce  jle     short loc_18000E5D9
0x18000e5d0  movzx   ebx, ax
0x18000e5d3  or      ebx, 80070000h
0x18000e5d9  test    ebx, ebx
0x18000e5db  js      short loc_18000E60A
0x18000e5dd  mov     r8d, r13d; int
0x18000e5e0  mov     rdx, [rbp+180h+hKey]; HKEY
0x18000e5e7  mov     rcx, rsi; unsigned __int16 *
0x18000e5ea  cmp     [rsp+r14*8+280h+var_228+4], r12d
0x18000e5ef  jz      short loc_18000E5F8
0x18000e5f1  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e5f6  jmp     short loc_18000E5FD
0x18000e5f8  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18000e5fd  mov     rcx, [rbp+180h+hKey]; hKey
0x18000e604  call    cs:__imp_RegCloseKey
0x18000e60a  add     rdi, r13
0x18000e60d  cmp     rdi, 3
0x18000e611  jb      loc_18000E58A
0x18000e617  cmp     ebx, 80070002h
0x18000e61d  cmovz   ebx, r12d
0x18000e621  mov     eax, ebx
0x18000e623  add     rsp, 248h
0x18000e62a  pop     r15
0x18000e62c  pop     r14
0x18000e62e  pop     r13
0x18000e630  pop     r12
0x18000e632  pop     rdi
0x18000e633  pop     rsi
0x18000e634  pop     rbx
0x18000e635  pop     rbp
0x18000e636  retn
```
