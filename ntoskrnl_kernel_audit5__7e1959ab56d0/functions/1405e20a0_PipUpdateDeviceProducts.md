# PipUpdateDeviceProducts

- ea: `0x1405e20a0`
- end: `0x1405e273f`
- name: `PipUpdateDeviceProducts`
- size: `1695`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1404a46a8`
- `0x140544600`
- `0x1405e20a0`
- `0x1406dc8c0`
- `0x14086daf0`
- `0x14086fe2c`
- `0x140870974`
- `0x140870f78`
- `0x140873488`
- `0x140879b80`
- `0x1408eeed8`
- `0x1408efd10`
- `0x140907074`
- `0x14090f73c`
- `0x140a420e8`
- `0x140a8ba44`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1405e2165`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x1405e21bf`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x1405e2170`: `DynamicInstalledProducts`
- `0x1405e21ca`: `DynamicInstalledProducts`

## pseudocode

```c
void __fastcall PipUpdateDeviceProducts(PVOID P)
{
  unsigned int v1; // esi
  PVOID v2; // rbx
  void *v3; // rdi
  void *v4; // r15
  void *v5; // r12
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // r14d
  int v10; // r13d
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // esi
  int v15; // r14d
  void *v16; // r13
  unsigned int v17; // ebx
  __int64 v18; // rcx
  int v19; // [rsp+28h] [rbp-91h]
  __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  int v21; // [rsp+48h] [rbp-71h] BYREF
  void *v22; // [rsp+50h] [rbp-69h]
  PVOID v23; // [rsp+58h] [rbp-61h]
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  int v25; // [rsp+68h] [rbp-51h] BYREF
  int v26; // [rsp+6Ch] [rbp-4Dh] BYREF
  __int64 v27; // [rsp+70h] [rbp-49h] BYREF
  __int64 v28; // [rsp+78h] [rbp-41h] BYREF
  __int64 v29; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v30; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v31; // [rsp+8Ch] [rbp-2Dh] BYREF
  int v32; // [rsp+90h] [rbp-29h] BYREF
  __int64 v33; // [rsp+98h] [rbp-21h] BYREF
  void *Pool2; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-11h] BYREF
  wchar_t Str1[8]; // [rsp+B0h] [rbp-9h] BYREF

  v1 = 0;
  v23 = P;
  v2 = P;
  v28 = 0;
  v35 = 0;
  v3 = 0;
  v29 = 0;
  v4 = 0;
  v24 = 0;
  Pool2 = 0;
  v5 = 0;
  v27 = 0;
  v33 = 0;
  LODWORD(v20) = 0;
  v25 = 0;
  v26 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v21 = 0;
  v22 = 0;
  if ( (int)PnpCtxGetCachedContextBaseKey(*(_QWORD *)&PiPnpRtlCtx, 15, &Pool2) < 0
    || (unsigned int)PnpCtxRegOpenKey(0, (_DWORD)Pool2, (unsigned int)L"Current\\ProductIds", 0, 131097, (__int64)&v33) == -1073741772
    || (unsigned int)RtlGetPersistedStateLocation(L"DynamicInstalledProducts", 0, 0, (__int64)&v20) != -2147483643 )
  {
    v16 = 0;
    goto LABEL_54;
  }
  v7 = v20;
  Pool2 = (void *)ExAllocatePool2(256, (unsigned int)v20, 1852403792);
  v4 = Pool2;
  if ( Pool2 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"DynamicInstalledProducts", Pool2, v7, (__int64)&v20) >= 0
      && !(unsigned int)PnpCtxRegCreateTree(0, 0, v4, 0, 131103, 0, &v29, 0) )
    {
      KeQueryBootTimeValues(&v20, &v28, &v35);
      v28 -= v35;
      if ( !(unsigned int)PnpCtxRegQueryInfoKey(v8, v29, &v30, &v25, 0, 0, 0) )
      {
        v9 = v30;
        if ( !v30 )
        {
LABEL_35:
          if ( (unsigned int)PnpCtxRegQueryInfoKey(v6, v33, 0, 0, &v31, &v26, 0) || (v14 = v31) == 0 )
          {
            v16 = v22;
          }
          else
          {
            v15 = v26 + 1;
            v16 = (void *)ExAllocatePool2(256, 2LL * (unsigned int)(v26 + 1), 1852403792);
            if ( v16 )
            {
              v17 = 0;
              if ( v14 )
              {
                do
                {
                  v26 = v15;
                  if ( v27 )
                  {
                    PnpCtxRegCloseKey(v6, v27);
                    v27 = 0;
                  }
                  if ( (int)PnpCtxRegEnumValue(v6, v33, v17, v16, &v26, 0, 0, 0) >= 0
                    && (int)PnpCtxRegCreateKey(0, v29, (_DWORD)v16, 0, 131078, 0, (__int64)&v27, (__int64)&v32) >= 0 )
                  {
                    if ( v32 == 1 )
                      PnpCtxRegSetValue(v6, v27, L"CreationTime");
                    LODWORD(v20) = 0;
                    if ( (unsigned int)PnpCtxRegQueryValue(v6, v27, L"Version", 0, 0, &v20) == -1073741772
                      && (int)PnpCtxRegSetValue(v6, v27, L"Version") >= 0 )
                    {
                      PnpCtxRegSetValue(v6, v27, L"ActivationTime");
                      PnpCtxRegSetValue(v18, v27, L"Source");
                    }
                  }
                  ++v17;
                }
                while ( v17 < v14 );
                v4 = Pool2;
              }
            }
          }
          goto LABEL_53;
        }
        v10 = v25 + 1;
        v5 = (void *)ExAllocatePool2(256, 2LL * (unsigned int)(v25 + 1), 1852403792);
        if ( v5 )
        {
          if ( v9 )
          {
            while ( 1 )
            {
              v25 = v10;
              if ( v24 )
              {
                PnpCtxRegCloseKey(v6, v24);
                v24 = 0;
              }
              if ( (int)PnpCtxRegEnumKey(v6, v29, v1, v5, &v25, v19) < 0 )
                goto LABEL_34;
              if ( (int)PnpCtxRegOpenKey(0, v29, (_DWORD)v5, 0, 131103, (__int64)&v24) < 0 )
                goto LABEL_34;
              LODWORD(v20) = 14;
              if ( (int)PnpCtxRegQueryValue(v6, v24, L"Source", &v21, Str1, &v20) < 0 )
                goto LABEL_34;
              if ( v21 != 1 )
                goto LABEL_34;
              if ( (_DWORD)v20 != 14 )
                goto LABEL_34;
              if ( wcsicmp(Str1, L"SMBIOS") )
                goto LABEL_34;
              LODWORD(v20) = 0;
              if ( (unsigned int)PnpCtxRegQueryValue(v6, v33, v5, 0, 0, &v20) != -1073741772 )
                goto LABEL_34;
              if ( v3 )
              {
                ExFreePoolWithTag(v3, 0);
                v3 = 0;
              }
              LODWORD(v20) = 0;
              v11 = PnpCtxRegQueryValue(v6, v24, L"Version", &v21, v3, &v20);
              if ( v11 == -1073741789 )
              {
                v12 = v20;
                v3 = (void *)ExAllocatePool2(256, (unsigned int)v20, 1852403792);
                if ( !v3 )
                  goto LABEL_31;
                v11 = PnpCtxRegQueryValue(v6, v24, L"Version", &v21, v3, &v20);
              }
              if ( v11 != -1073741772 )
              {
                v12 = v20;
                if ( (v11 < 0 || v21 != 1 || (unsigned int)v20 < 2) && v3 )
                {
                  ExFreePoolWithTag(v3, 0);
                  v3 = 0;
                }
LABEL_31:
                v19 = 8;
                PnpCtxRegSetValue(v6, v24, L"DeactivationTime");
                if ( v3 )
                {
                  v19 = v12;
                  PnpCtxRegSetValue(v13, v24, L"DeactivationVersion");
                }
                PnpCtxRegDeleteValue(v13, v24, L"Version");
              }
LABEL_34:
              if ( ++v1 >= v9 )
                goto LABEL_35;
            }
          }
          goto LABEL_35;
        }
      }
    }
  }
  v16 = 0;
LABEL_53:
  v2 = v23;
LABEL_54:
  if ( v27 )
    PnpCtxRegCloseKey(v6, v27);
  if ( v33 )
    PnpCtxRegCloseKey(v6, v33);
  if ( v24 )
    PnpCtxRegCloseKey(v6, v24);
  if ( v29 )
    PnpCtxRegCloseKey(v6, v29);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
}

```

## disassembly

```asm
0x1405e20a0  push    rbp
0x1405e20a2  push    rbx
0x1405e20a3  push    rsi
0x1405e20a4  push    rdi
0x1405e20a5  push    r12
0x1405e20a7  push    r13
0x1405e20a9  push    r14
0x1405e20ab  push    r15
0x1405e20ad  lea     rbp, [rsp-1Fh]
0x1405e20b2  sub     rsp, 0D8h
0x1405e20b9  mov     rax, cs:__security_cookie
0x1405e20c0  xor     rax, rsp
0x1405e20c3  mov     [rbp+57h+var_50], rax
0x1405e20c7  xor     esi, esi
0x1405e20c9  mov     [rbp+57h+var_B8], rcx
0x1405e20cd  mov     rbx, rcx
0x1405e20d0  mov     [rbp+57h+var_98], rsi
0x1405e20d4  mov     rcx, cs:PiPnpRtlCtx
0x1405e20db  lea     r8, [rbp+57h+var_70]
0x1405e20df  mov     [rbp+57h+var_68], rsi
0x1405e20e3  mov     edi, esi
0x1405e20e5  lea     edx, [rsi+0Fh]
0x1405e20e8  mov     [rbp+57h+var_90], rsi
0x1405e20ec  mov     r15d, esi
0x1405e20ef  mov     [rbp+57h+var_B0], rsi
0x1405e20f3  mov     [rbp+57h+var_70], rsi
0x1405e20f7  mov     r12d, esi
0x1405e20fa  mov     [rbp+57h+var_A0], rsi
0x1405e20fe  mov     [rbp+57h+var_78], rsi
0x1405e2102  mov     dword ptr [rbp+57h+var_D0], esi
0x1405e2105  mov     [rbp+57h+var_A8], esi
0x1405e2108  mov     [rbp+57h+var_A4], esi
0x1405e210b  mov     [rbp+57h+var_88], esi
0x1405e210e  mov     [rbp+57h+var_84], esi
0x1405e2111  mov     [rbp+57h+var_80], esi
0x1405e2114  mov     [rbp+57h+var_C8], esi
0x1405e2117  mov     [rbp+57h+var_C0], rsi
0x1405e211b  call    _PnpCtxGetCachedContextBaseKey
0x1405e2120  test    eax, eax
0x1405e2122  js      loc_1405E2689
0x1405e2128  mov     rdx, [rbp+57h+var_70]
0x1405e212c  lea     rax, [rbp+57h+var_78]
0x1405e2130  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e2135  lea     r8, aCurrentProduct; "Current\\ProductIds"
0x1405e213c  xor     r9d, r9d
0x1405e213f  mov     dword ptr [rsp+110h+var_F0], 20019h
0x1405e2147  xor     ecx, ecx
0x1405e2149  call    _PnpCtxRegOpenKey
0x1405e214e  cmp     eax, 0C0000034h
0x1405e2153  jz      loc_1405E2689
0x1405e2159  lea     rax, [rbp+57h+var_D0]
0x1405e215d  xor     r9d, r9d
0x1405e2160  mov     [rsp+110h+var_E0], rax; __int64
0x1405e2165  lea     r8, aRegistryMachin_65; "\\Registry\\Machine\\Software\\Microsof"...
0x1405e216c  mov     [rsp+110h+var_E8], esi; int
0x1405e2170  lea     rcx, aDynamicinstall; "DynamicInstalledProducts"
0x1405e2177  xor     edx, edx
0x1405e2179  mov     [rsp+110h+var_F0], rsi; void *
0x1405e217e  call    RtlGetPersistedStateLocation
0x1405e2183  cmp     eax, 80000005h
0x1405e2188  jnz     loc_1405E2689
0x1405e218e  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405e2191  mov     ecx, 100h
0x1405e2196  mov     edx, ebx
0x1405e2198  mov     r8d, 6E697050h
0x1405e219e  call    ExAllocatePool2
0x1405e21a3  mov     [rbp+57h+var_70], rax
0x1405e21a7  mov     r15, rax
0x1405e21aa  test    rax, rax
0x1405e21ad  jz      loc_1405E268E
0x1405e21b3  lea     rax, [rbp+57h+var_D0]
0x1405e21b7  xor     r9d, r9d
0x1405e21ba  mov     [rsp+110h+var_E0], rax; __int64
0x1405e21bf  lea     r8, aRegistryMachin_65; "\\Registry\\Machine\\Software\\Microsof"...
0x1405e21c6  mov     [rsp+110h+var_E8], ebx; int
0x1405e21ca  lea     rcx, aDynamicinstall; "DynamicInstalledProducts"
0x1405e21d1  xor     edx, edx
0x1405e21d3  mov     [rsp+110h+var_F0], r15; void *
0x1405e21d8  call    RtlGetPersistedStateLocation
0x1405e21dd  test    eax, eax
0x1405e21df  js      loc_1405E268E
0x1405e21e5  mov     [rsp+110h+var_D8], rsi
0x1405e21ea  lea     rax, [rbp+57h+var_90]
0x1405e21ee  mov     [rsp+110h+var_E0], rax
0x1405e21f3  xor     r9d, r9d
0x1405e21f6  mov     qword ptr [rsp+110h+var_E8], rsi
0x1405e21fb  mov     r8, r15
0x1405e21fe  xor     edx, edx
0x1405e2200  mov     dword ptr [rsp+110h+var_F0], 2001Fh
0x1405e2208  xor     ecx, ecx
0x1405e220a  call    _PnpCtxRegCreateTree
0x1405e220f  test    eax, eax
0x1405e2211  jnz     loc_1405E268E
0x1405e2217  lea     r8, [rbp+57h+var_68]
0x1405e221b  lea     rdx, [rbp+57h+var_98]
0x1405e221f  lea     rcx, [rbp+57h+var_D0]
0x1405e2223  call    KeQueryBootTimeValues
0x1405e2228  mov     rax, [rbp+57h+var_68]
0x1405e222c  lea     r9, [rbp+57h+var_A8]
0x1405e2230  mov     rdx, [rbp+57h+var_90]
0x1405e2234  lea     r8, [rbp+57h+var_88]
0x1405e2238  sub     [rbp+57h+var_98], rax
0x1405e223c  mov     [rsp+110h+var_E0], rsi
0x1405e2241  mov     qword ptr [rsp+110h+var_E8], rsi
0x1405e2246  mov     [rsp+110h+var_F0], rsi
0x1405e224b  call    _PnpCtxRegQueryInfoKey
0x1405e2250  test    eax, eax
0x1405e2252  jnz     loc_1405E268E
0x1405e2258  mov     r14d, [rbp+57h+var_88]
0x1405e225c  test    r14d, r14d
0x1405e225f  jz      loc_1405E249D
0x1405e2265  mov     r13d, [rbp+57h+var_A8]
0x1405e2269  mov     ecx, 100h
0x1405e226e  inc     r13d
0x1405e2271  mov     r8d, 6E697050h
0x1405e2277  mov     edx, r13d
0x1405e227a  add     rdx, rdx
0x1405e227d  call    ExAllocatePool2
0x1405e2282  mov     r12, rax
0x1405e2285  test    rax, rax
0x1405e2288  jz      loc_1405E268E
0x1405e228e  test    r14d, r14d
0x1405e2291  jz      loc_1405E249D
0x1405e2297  mov     rdx, [rbp+57h+var_B0]
0x1405e229b  mov     [rbp+57h+var_A8], r13d
0x1405e229f  test    rdx, rdx
0x1405e22a2  jz      short loc_1405E22B1
0x1405e22a4  call    _PnpCtxRegCloseKey
0x1405e22a9  mov     [rbp+57h+var_B0], 0
0x1405e22b1  mov     rdx, [rbp+57h+var_90]
0x1405e22b5  lea     rax, [rbp+57h+var_A8]
0x1405e22b9  mov     r9, r12
0x1405e22bc  mov     [rsp+110h+var_F0], rax
0x1405e22c1  mov     r8d, esi
0x1405e22c4  call    _PnpCtxRegEnumKey
0x1405e22c9  test    eax, eax
0x1405e22cb  js      loc_1405E2490
0x1405e22d1  mov     rdx, [rbp+57h+var_90]
0x1405e22d5  lea     rax, [rbp+57h+var_B0]
0x1405e22d9  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e22de  xor     r9d, r9d
0x1405e22e1  mov     r8, r12
0x1405e22e4  mov     dword ptr [rsp+110h+var_F0], 2001Fh
0x1405e22ec  xor     ecx, ecx
0x1405e22ee  call    _PnpCtxRegOpenKey
0x1405e22f3  test    eax, eax
0x1405e22f5  js      loc_1405E2490
0x1405e22fb  mov     rdx, [rbp+57h+var_B0]
0x1405e22ff  lea     rax, [rbp+57h+var_D0]
0x1405e2303  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e2308  lea     r9, [rbp+57h+var_C8]
0x1405e230c  lea     rax, [rbp+57h+Str1]
0x1405e2310  mov     dword ptr [rbp+57h+var_D0], 0Eh
0x1405e2317  lea     r8, aSource; "Source"
0x1405e231e  mov     [rsp+110h+var_F0], rax
0x1405e2323  call    _PnpCtxRegQueryValue
0x1405e2328  test    eax, eax
0x1405e232a  js      loc_1405E2490
0x1405e2330  cmp     [rbp+57h+var_C8], 1
0x1405e2334  jnz     loc_1405E2490
0x1405e233a  cmp     dword ptr [rbp+57h+var_D0], 0Eh
0x1405e233e  jnz     loc_1405E2490
0x1405e2344  lea     rdx, aSmbios_0; "SMBIOS"
0x1405e234b  lea     rcx, [rbp+57h+Str1]; Str1
0x1405e234f  call    _wcsicmp
0x1405e2354  test    eax, eax
0x1405e2356  jnz     loc_1405E2490
0x1405e235c  mov     rdx, [rbp+57h+var_78]
0x1405e2360  xor     r9d, r9d
0x1405e2363  mov     dword ptr [rbp+57h+var_D0], eax
0x1405e2366  mov     r8, r12
0x1405e2369  lea     rax, [rbp+57h+var_D0]
0x1405e236d  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e2372  mov     [rsp+110h+var_F0], 0
0x1405e237b  call    _PnpCtxRegQueryValue
0x1405e2380  cmp     eax, 0C0000034h
0x1405e2385  jnz     loc_1405E2490
0x1405e238b  test    rdi, rdi
0x1405e238e  jz      short loc_1405E239C
0x1405e2390  xor     edx, edx; Tag
0x1405e2392  mov     rcx, rdi; P
0x1405e2395  call    ExFreePoolWithTag
0x1405e239a  xor     edi, edi
0x1405e239c  mov     rdx, [rbp+57h+var_B0]
0x1405e23a0  lea     rax, [rbp+57h+var_D0]
0x1405e23a4  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e23a9  lea     r9, [rbp+57h+var_C8]
0x1405e23ad  lea     r8, aVersion_2; "Version"
0x1405e23b4  mov     [rsp+110h+var_F0], rdi
0x1405e23b9  mov     dword ptr [rbp+57h+var_D0], 0
0x1405e23c0  call    _PnpCtxRegQueryValue
0x1405e23c5  cmp     eax, 0C0000023h
0x1405e23ca  jnz     short loc_1405E240B
0x1405e23cc  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405e23cf  mov     ecx, 100h
0x1405e23d4  mov     edx, ebx
0x1405e23d6  mov     r8d, 6E697050h
0x1405e23dc  call    ExAllocatePool2
0x1405e23e1  mov     rdi, rax
0x1405e23e4  test    rax, rax
0x1405e23e7  jz      short loc_1405E2435
0x1405e23e9  mov     rdx, [rbp+57h+var_B0]
0x1405e23ed  lea     rax, [rbp+57h+var_D0]
0x1405e23f1  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e23f6  lea     r9, [rbp+57h+var_C8]
0x1405e23fa  lea     r8, aVersion_2; "Version"
0x1405e2401  mov     [rsp+110h+var_F0], rdi
0x1405e2406  call    _PnpCtxRegQueryValue
0x1405e240b  cmp     eax, 0C0000034h
0x1405e2410  jz      short loc_1405E2490
0x1405e2412  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405e2415  test    eax, eax
0x1405e2417  js      short loc_1405E2424
0x1405e2419  cmp     [rbp+57h+var_C8], 1
0x1405e241d  jnz     short loc_1405E2424
0x1405e241f  cmp     ebx, 2
0x1405e2422  jnb     short loc_1405E2435
0x1405e2424  test    rdi, rdi
0x1405e2427  jz      short loc_1405E2435
0x1405e2429  xor     edx, edx; Tag
0x1405e242b  mov     rcx, rdi; P
0x1405e242e  call    ExFreePoolWithTag
0x1405e2433  xor     edi, edi
0x1405e2435  mov     rdx, [rbp+57h+var_B0]
0x1405e2439  lea     rax, [rbp+57h+var_98]
0x1405e243d  mov     [rsp+110h+var_E8], 8
0x1405e2445  lea     r8, aDeactivationti; "DeactivationTime"
0x1405e244c  mov     r9d, 3
0x1405e2452  mov     [rsp+110h+var_F0], rax
0x1405e2457  call    _PnpCtxRegSetValue
0x1405e245c  test    rdi, rdi
0x1405e245f  jz      short loc_1405E2480
0x1405e2461  mov     rdx, [rbp+57h+var_B0]
0x1405e2465  lea     r8, aDeactivationve; "DeactivationVersion"
0x1405e246c  mov     [rsp+110h+var_E8], ebx
0x1405e2470  mov     r9d, 1
0x1405e2476  mov     [rsp+110h+var_F0], rdi
0x1405e247b  call    _PnpCtxRegSetValue
0x1405e2480  mov     rdx, [rbp+57h+var_B0]
0x1405e2484  lea     r8, aVersion_2; "Version"
0x1405e248b  call    _PnpCtxRegDeleteValue
0x1405e2490  inc     esi
0x1405e2492  cmp     esi, r14d
0x1405e2495  jb      loc_1405E2297
0x1405e249b  xor     esi, esi
0x1405e249d  mov     rdx, [rbp+57h+var_78]
0x1405e24a1  lea     rax, [rbp+57h+var_A4]
0x1405e24a5  mov     [rsp+110h+var_E0], rsi
0x1405e24aa  xor     r9d, r9d
0x1405e24ad  mov     qword ptr [rsp+110h+var_E8], rax
0x1405e24b2  xor     r8d, r8d
0x1405e24b5  lea     rax, [rbp+57h+var_84]
0x1405e24b9  mov     [rsp+110h+var_F0], rax
0x1405e24be  call    _PnpCtxRegQueryInfoKey
0x1405e24c3  test    eax, eax
0x1405e24c5  jnz     loc_1405E2693
0x1405e24cb  mov     esi, [rbp+57h+var_84]
0x1405e24ce  test    esi, esi
0x1405e24d0  jz      loc_1405E2693
0x1405e24d6  mov     r14d, [rbp+57h+var_A4]
0x1405e24da  mov     ecx, 100h
0x1405e24df  inc     r14d
0x1405e24e2  mov     r8d, 6E697050h
0x1405e24e8  mov     edx, r14d
0x1405e24eb  add     rdx, rdx
0x1405e24ee  call    ExAllocatePool2
0x1405e24f3  mov     r13, rax
0x1405e24f6  test    rax, rax
0x1405e24f9  jz      loc_1405E2697
0x1405e24ff  xor     ebx, ebx
0x1405e2501  test    esi, esi
0x1405e2503  jz      loc_1405E2697
0x1405e2509  lea     r15, aSmbios_0; "SMBIOS"
0x1405e2510  mov     rdx, [rbp+57h+var_A0]
0x1405e2514  mov     [rbp+57h+var_A4], r14d
0x1405e2518  test    rdx, rdx
0x1405e251b  jz      short loc_1405E252A
0x1405e251d  call    _PnpCtxRegCloseKey
0x1405e2522  mov     [rbp+57h+var_A0], 0
0x1405e252a  mov     rdx, [rbp+57h+var_78]
0x1405e252e  lea     rax, [rbp+57h+var_A4]
0x1405e2532  mov     [rsp+110h+var_D8], 0
0x1405e253b  mov     r9, r13
0x1405e253e  mov     [rsp+110h+var_E0], 0
0x1405e2547  mov     r8d, ebx
0x1405e254a  mov     qword ptr [rsp+110h+var_E8], 0
0x1405e2553  mov     [rsp+110h+var_F0], rax
0x1405e2558  call    _PnpCtxRegEnumValue
0x1405e255d  test    eax, eax
0x1405e255f  js      loc_1405E2679
0x1405e2565  mov     rdx, [rbp+57h+var_90]
0x1405e2569  lea     rax, [rbp+57h+var_80]
0x1405e256d  mov     [rsp+110h+var_D8], rax
0x1405e2572  xor     r9d, r9d
0x1405e2575  lea     rax, [rbp+57h+var_A0]
0x1405e2579  mov     r8, r13
0x1405e257c  mov     [rsp+110h+var_E0], rax
0x1405e2581  xor     ecx, ecx
0x1405e2583  mov     qword ptr [rsp+110h+var_E8], 0
0x1405e258c  mov     dword ptr [rsp+110h+var_F0], 20006h
  ... truncated ...
```
