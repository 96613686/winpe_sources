# PipUpdateDeviceProducts

- ea: `0x1405db4c0`
- end: `0x1405dbb5f`
- name: `PipUpdateDeviceProducts`
- size: `1695`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140496b88`
- `0x14053cf40`
- `0x1405db4c0`
- `0x1406d9d70`
- `0x1408b9fc8`
- `0x1408bae00`
- `0x1408d2294`
- `0x1408da95c`
- `0x14095e740`
- `0x140960a7c`
- `0x1409615c4`
- `0x140961bc8`
- `0x1409640d8`
- `0x140973560`
- `0x140a3b768`
- `0x140a85084`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x1405db585`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x1405db5df`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x1405db590`: `DynamicInstalledProducts`
- `0x1405db5ea`: `DynamicInstalledProducts`

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
0x1405db4c0  push    rbp
0x1405db4c2  push    rbx
0x1405db4c3  push    rsi
0x1405db4c4  push    rdi
0x1405db4c5  push    r12
0x1405db4c7  push    r13
0x1405db4c9  push    r14
0x1405db4cb  push    r15
0x1405db4cd  lea     rbp, [rsp-1Fh]
0x1405db4d2  sub     rsp, 0D8h
0x1405db4d9  mov     rax, cs:__security_cookie
0x1405db4e0  xor     rax, rsp
0x1405db4e3  mov     [rbp+57h+var_50], rax
0x1405db4e7  xor     esi, esi
0x1405db4e9  mov     [rbp+57h+var_B8], rcx
0x1405db4ed  mov     rbx, rcx
0x1405db4f0  mov     [rbp+57h+var_98], rsi
0x1405db4f4  mov     rcx, cs:PiPnpRtlCtx
0x1405db4fb  lea     r8, [rbp+57h+var_70]
0x1405db4ff  mov     [rbp+57h+var_68], rsi
0x1405db503  mov     edi, esi
0x1405db505  lea     edx, [rsi+0Fh]
0x1405db508  mov     [rbp+57h+var_90], rsi
0x1405db50c  mov     r15d, esi
0x1405db50f  mov     [rbp+57h+var_B0], rsi
0x1405db513  mov     [rbp+57h+var_70], rsi
0x1405db517  mov     r12d, esi
0x1405db51a  mov     [rbp+57h+var_A0], rsi
0x1405db51e  mov     [rbp+57h+var_78], rsi
0x1405db522  mov     dword ptr [rbp+57h+var_D0], esi
0x1405db525  mov     [rbp+57h+var_A8], esi
0x1405db528  mov     [rbp+57h+var_A4], esi
0x1405db52b  mov     [rbp+57h+var_88], esi
0x1405db52e  mov     [rbp+57h+var_84], esi
0x1405db531  mov     [rbp+57h+var_80], esi
0x1405db534  mov     [rbp+57h+var_C8], esi
0x1405db537  mov     [rbp+57h+var_C0], rsi
0x1405db53b  call    _PnpCtxGetCachedContextBaseKey
0x1405db540  test    eax, eax
0x1405db542  js      loc_1405DBAA9
0x1405db548  mov     rdx, [rbp+57h+var_70]
0x1405db54c  lea     rax, [rbp+57h+var_78]
0x1405db550  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db555  lea     r8, aCurrentProduct; "Current\\ProductIds"
0x1405db55c  xor     r9d, r9d
0x1405db55f  mov     dword ptr [rsp+110h+var_F0], 20019h
0x1405db567  xor     ecx, ecx
0x1405db569  call    _PnpCtxRegOpenKey
0x1405db56e  cmp     eax, 0C0000034h
0x1405db573  jz      loc_1405DBAA9
0x1405db579  lea     rax, [rbp+57h+var_D0]
0x1405db57d  xor     r9d, r9d
0x1405db580  mov     [rsp+110h+var_E0], rax; __int64
0x1405db585  lea     r8, aRegistryMachin_65; "\\Registry\\Machine\\Software\\Microsof"...
0x1405db58c  mov     [rsp+110h+var_E8], esi; int
0x1405db590  lea     rcx, aDynamicinstall; "DynamicInstalledProducts"
0x1405db597  xor     edx, edx
0x1405db599  mov     [rsp+110h+var_F0], rsi; void *
0x1405db59e  call    RtlGetPersistedStateLocation
0x1405db5a3  cmp     eax, 80000005h
0x1405db5a8  jnz     loc_1405DBAA9
0x1405db5ae  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405db5b1  mov     ecx, 100h
0x1405db5b6  mov     edx, ebx
0x1405db5b8  mov     r8d, 6E697050h
0x1405db5be  call    ExAllocatePool2
0x1405db5c3  mov     [rbp+57h+var_70], rax
0x1405db5c7  mov     r15, rax
0x1405db5ca  test    rax, rax
0x1405db5cd  jz      loc_1405DBAAE
0x1405db5d3  lea     rax, [rbp+57h+var_D0]
0x1405db5d7  xor     r9d, r9d
0x1405db5da  mov     [rsp+110h+var_E0], rax; __int64
0x1405db5df  lea     r8, aRegistryMachin_65; "\\Registry\\Machine\\Software\\Microsof"...
0x1405db5e6  mov     [rsp+110h+var_E8], ebx; int
0x1405db5ea  lea     rcx, aDynamicinstall; "DynamicInstalledProducts"
0x1405db5f1  xor     edx, edx
0x1405db5f3  mov     [rsp+110h+var_F0], r15; void *
0x1405db5f8  call    RtlGetPersistedStateLocation
0x1405db5fd  test    eax, eax
0x1405db5ff  js      loc_1405DBAAE
0x1405db605  mov     [rsp+110h+var_D8], rsi
0x1405db60a  lea     rax, [rbp+57h+var_90]
0x1405db60e  mov     [rsp+110h+var_E0], rax
0x1405db613  xor     r9d, r9d
0x1405db616  mov     qword ptr [rsp+110h+var_E8], rsi
0x1405db61b  mov     r8, r15
0x1405db61e  xor     edx, edx
0x1405db620  mov     dword ptr [rsp+110h+var_F0], 2001Fh
0x1405db628  xor     ecx, ecx
0x1405db62a  call    _PnpCtxRegCreateTree
0x1405db62f  test    eax, eax
0x1405db631  jnz     loc_1405DBAAE
0x1405db637  lea     r8, [rbp+57h+var_68]
0x1405db63b  lea     rdx, [rbp+57h+var_98]
0x1405db63f  lea     rcx, [rbp+57h+var_D0]
0x1405db643  call    KeQueryBootTimeValues
0x1405db648  mov     rax, [rbp+57h+var_68]
0x1405db64c  lea     r9, [rbp+57h+var_A8]
0x1405db650  mov     rdx, [rbp+57h+var_90]
0x1405db654  lea     r8, [rbp+57h+var_88]
0x1405db658  sub     [rbp+57h+var_98], rax
0x1405db65c  mov     [rsp+110h+var_E0], rsi
0x1405db661  mov     qword ptr [rsp+110h+var_E8], rsi
0x1405db666  mov     [rsp+110h+var_F0], rsi
0x1405db66b  call    _PnpCtxRegQueryInfoKey
0x1405db670  test    eax, eax
0x1405db672  jnz     loc_1405DBAAE
0x1405db678  mov     r14d, [rbp+57h+var_88]
0x1405db67c  test    r14d, r14d
0x1405db67f  jz      loc_1405DB8BD
0x1405db685  mov     r13d, [rbp+57h+var_A8]
0x1405db689  mov     ecx, 100h
0x1405db68e  inc     r13d
0x1405db691  mov     r8d, 6E697050h
0x1405db697  mov     edx, r13d
0x1405db69a  add     rdx, rdx
0x1405db69d  call    ExAllocatePool2
0x1405db6a2  mov     r12, rax
0x1405db6a5  test    rax, rax
0x1405db6a8  jz      loc_1405DBAAE
0x1405db6ae  test    r14d, r14d
0x1405db6b1  jz      loc_1405DB8BD
0x1405db6b7  mov     rdx, [rbp+57h+var_B0]
0x1405db6bb  mov     [rbp+57h+var_A8], r13d
0x1405db6bf  test    rdx, rdx
0x1405db6c2  jz      short loc_1405DB6D1
0x1405db6c4  call    _PnpCtxRegCloseKey
0x1405db6c9  mov     [rbp+57h+var_B0], 0
0x1405db6d1  mov     rdx, [rbp+57h+var_90]
0x1405db6d5  lea     rax, [rbp+57h+var_A8]
0x1405db6d9  mov     r9, r12
0x1405db6dc  mov     [rsp+110h+var_F0], rax
0x1405db6e1  mov     r8d, esi
0x1405db6e4  call    _PnpCtxRegEnumKey
0x1405db6e9  test    eax, eax
0x1405db6eb  js      loc_1405DB8B0
0x1405db6f1  mov     rdx, [rbp+57h+var_90]
0x1405db6f5  lea     rax, [rbp+57h+var_B0]
0x1405db6f9  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db6fe  xor     r9d, r9d
0x1405db701  mov     r8, r12
0x1405db704  mov     dword ptr [rsp+110h+var_F0], 2001Fh
0x1405db70c  xor     ecx, ecx
0x1405db70e  call    _PnpCtxRegOpenKey
0x1405db713  test    eax, eax
0x1405db715  js      loc_1405DB8B0
0x1405db71b  mov     rdx, [rbp+57h+var_B0]
0x1405db71f  lea     rax, [rbp+57h+var_D0]
0x1405db723  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db728  lea     r9, [rbp+57h+var_C8]
0x1405db72c  lea     rax, [rbp+57h+Str1]
0x1405db730  mov     dword ptr [rbp+57h+var_D0], 0Eh
0x1405db737  lea     r8, aSource; "Source"
0x1405db73e  mov     [rsp+110h+var_F0], rax
0x1405db743  call    _PnpCtxRegQueryValue
0x1405db748  test    eax, eax
0x1405db74a  js      loc_1405DB8B0
0x1405db750  cmp     [rbp+57h+var_C8], 1
0x1405db754  jnz     loc_1405DB8B0
0x1405db75a  cmp     dword ptr [rbp+57h+var_D0], 0Eh
0x1405db75e  jnz     loc_1405DB8B0
0x1405db764  lea     rdx, aSmbios_0; "SMBIOS"
0x1405db76b  lea     rcx, [rbp+57h+Str1]; Str1
0x1405db76f  call    _wcsicmp
0x1405db774  test    eax, eax
0x1405db776  jnz     loc_1405DB8B0
0x1405db77c  mov     rdx, [rbp+57h+var_78]
0x1405db780  xor     r9d, r9d
0x1405db783  mov     dword ptr [rbp+57h+var_D0], eax
0x1405db786  mov     r8, r12
0x1405db789  lea     rax, [rbp+57h+var_D0]
0x1405db78d  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db792  mov     [rsp+110h+var_F0], 0
0x1405db79b  call    _PnpCtxRegQueryValue
0x1405db7a0  cmp     eax, 0C0000034h
0x1405db7a5  jnz     loc_1405DB8B0
0x1405db7ab  test    rdi, rdi
0x1405db7ae  jz      short loc_1405DB7BC
0x1405db7b0  xor     edx, edx; Tag
0x1405db7b2  mov     rcx, rdi; P
0x1405db7b5  call    ExFreePoolWithTag
0x1405db7ba  xor     edi, edi
0x1405db7bc  mov     rdx, [rbp+57h+var_B0]
0x1405db7c0  lea     rax, [rbp+57h+var_D0]
0x1405db7c4  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db7c9  lea     r9, [rbp+57h+var_C8]
0x1405db7cd  lea     r8, aVersion_2; "Version"
0x1405db7d4  mov     [rsp+110h+var_F0], rdi
0x1405db7d9  mov     dword ptr [rbp+57h+var_D0], 0
0x1405db7e0  call    _PnpCtxRegQueryValue
0x1405db7e5  cmp     eax, 0C0000023h
0x1405db7ea  jnz     short loc_1405DB82B
0x1405db7ec  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405db7ef  mov     ecx, 100h
0x1405db7f4  mov     edx, ebx
0x1405db7f6  mov     r8d, 6E697050h
0x1405db7fc  call    ExAllocatePool2
0x1405db801  mov     rdi, rax
0x1405db804  test    rax, rax
0x1405db807  jz      short loc_1405DB855
0x1405db809  mov     rdx, [rbp+57h+var_B0]
0x1405db80d  lea     rax, [rbp+57h+var_D0]
0x1405db811  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db816  lea     r9, [rbp+57h+var_C8]
0x1405db81a  lea     r8, aVersion_2; "Version"
0x1405db821  mov     [rsp+110h+var_F0], rdi
0x1405db826  call    _PnpCtxRegQueryValue
0x1405db82b  cmp     eax, 0C0000034h
0x1405db830  jz      short loc_1405DB8B0
0x1405db832  mov     ebx, dword ptr [rbp+57h+var_D0]
0x1405db835  test    eax, eax
0x1405db837  js      short loc_1405DB844
0x1405db839  cmp     [rbp+57h+var_C8], 1
0x1405db83d  jnz     short loc_1405DB844
0x1405db83f  cmp     ebx, 2
0x1405db842  jnb     short loc_1405DB855
0x1405db844  test    rdi, rdi
0x1405db847  jz      short loc_1405DB855
0x1405db849  xor     edx, edx; Tag
0x1405db84b  mov     rcx, rdi; P
0x1405db84e  call    ExFreePoolWithTag
0x1405db853  xor     edi, edi
0x1405db855  mov     rdx, [rbp+57h+var_B0]
0x1405db859  lea     rax, [rbp+57h+var_98]
0x1405db85d  mov     [rsp+110h+var_E8], 8
0x1405db865  lea     r8, aDeactivationti; "DeactivationTime"
0x1405db86c  mov     r9d, 3
0x1405db872  mov     [rsp+110h+var_F0], rax
0x1405db877  call    _PnpCtxRegSetValue
0x1405db87c  test    rdi, rdi
0x1405db87f  jz      short loc_1405DB8A0
0x1405db881  mov     rdx, [rbp+57h+var_B0]
0x1405db885  lea     r8, aDeactivationve; "DeactivationVersion"
0x1405db88c  mov     [rsp+110h+var_E8], ebx
0x1405db890  mov     r9d, 1
0x1405db896  mov     [rsp+110h+var_F0], rdi
0x1405db89b  call    _PnpCtxRegSetValue
0x1405db8a0  mov     rdx, [rbp+57h+var_B0]
0x1405db8a4  lea     r8, aVersion_2; "Version"
0x1405db8ab  call    _PnpCtxRegDeleteValue
0x1405db8b0  inc     esi
0x1405db8b2  cmp     esi, r14d
0x1405db8b5  jb      loc_1405DB6B7
0x1405db8bb  xor     esi, esi
0x1405db8bd  mov     rdx, [rbp+57h+var_78]
0x1405db8c1  lea     rax, [rbp+57h+var_A4]
0x1405db8c5  mov     [rsp+110h+var_E0], rsi
0x1405db8ca  xor     r9d, r9d
0x1405db8cd  mov     qword ptr [rsp+110h+var_E8], rax
0x1405db8d2  xor     r8d, r8d
0x1405db8d5  lea     rax, [rbp+57h+var_84]
0x1405db8d9  mov     [rsp+110h+var_F0], rax
0x1405db8de  call    _PnpCtxRegQueryInfoKey
0x1405db8e3  test    eax, eax
0x1405db8e5  jnz     loc_1405DBAB3
0x1405db8eb  mov     esi, [rbp+57h+var_84]
0x1405db8ee  test    esi, esi
0x1405db8f0  jz      loc_1405DBAB3
0x1405db8f6  mov     r14d, [rbp+57h+var_A4]
0x1405db8fa  mov     ecx, 100h
0x1405db8ff  inc     r14d
0x1405db902  mov     r8d, 6E697050h
0x1405db908  mov     edx, r14d
0x1405db90b  add     rdx, rdx
0x1405db90e  call    ExAllocatePool2
0x1405db913  mov     r13, rax
0x1405db916  test    rax, rax
0x1405db919  jz      loc_1405DBAB7
0x1405db91f  xor     ebx, ebx
0x1405db921  test    esi, esi
0x1405db923  jz      loc_1405DBAB7
0x1405db929  lea     r15, aSmbios_0; "SMBIOS"
0x1405db930  mov     rdx, [rbp+57h+var_A0]
0x1405db934  mov     [rbp+57h+var_A4], r14d
0x1405db938  test    rdx, rdx
0x1405db93b  jz      short loc_1405DB94A
0x1405db93d  call    _PnpCtxRegCloseKey
0x1405db942  mov     [rbp+57h+var_A0], 0
0x1405db94a  mov     rdx, [rbp+57h+var_78]
0x1405db94e  lea     rax, [rbp+57h+var_A4]
0x1405db952  mov     [rsp+110h+var_D8], 0
0x1405db95b  mov     r9, r13
0x1405db95e  mov     [rsp+110h+var_E0], 0
0x1405db967  mov     r8d, ebx
0x1405db96a  mov     qword ptr [rsp+110h+var_E8], 0
0x1405db973  mov     [rsp+110h+var_F0], rax
0x1405db978  call    _PnpCtxRegEnumValue
0x1405db97d  test    eax, eax
0x1405db97f  js      loc_1405DBA99
0x1405db985  mov     rdx, [rbp+57h+var_90]
0x1405db989  lea     rax, [rbp+57h+var_80]
0x1405db98d  mov     [rsp+110h+var_D8], rax
0x1405db992  xor     r9d, r9d
0x1405db995  lea     rax, [rbp+57h+var_A0]
0x1405db999  mov     r8, r13
0x1405db99c  mov     [rsp+110h+var_E0], rax
0x1405db9a1  xor     ecx, ecx
0x1405db9a3  mov     qword ptr [rsp+110h+var_E8], 0
0x1405db9ac  mov     dword ptr [rsp+110h+var_F0], 20006h
  ... truncated ...
```
