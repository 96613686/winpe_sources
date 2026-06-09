# GetImagePathInReg

- ea: `0x18006149c`
- end: `0x180061619`
- name: `GetImagePathInReg`
- size: `381`
- prototype: `__int64 __fastcall(__int64, __int64, BYTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800613cc`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18006149c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800614e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800614e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800615e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800615e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006153a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800615bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006153a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800615bd`

## string_xrefs

- `0x1800614fb`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x18006156f`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetImagePathInReg(__int64 a1, __int64 a2, BYTE **a3)
{
  BYTE *lpData; // rdi
  unsigned int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int v12; // [rsp+54h] [rbp+24h]
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+5Ch] [rbp+2Ch]
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v14 = HIDWORD(a2);
  v12 = HIDWORD(a1);
  hKey = 0;
  lpData = 0;
  cbData = 0;
  Type = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Software Key Storage Provider\\Properties",
         0,
         0x20019u,
         &hKey);
  if ( v5 )
  {
    v6 = 96;
LABEL_3:
    DebugTraceError(v5, "lResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", v6);
    v7 = -2146893794;
    goto LABEL_14;
  }
  v5 = RegQueryValueExW(hKey, L"BioProtectionBioImage", 0, &Type, 0, &cbData);
  if ( v5 )
  {
    v6 = 109;
    goto LABEL_3;
  }
  if ( Type != 2 )
  {
    v7 = -2146893794;
    v8 = 117;
    v9 = 2148073502LL;
LABEL_8:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", v8);
    goto LABEL_14;
  }
  lpData = (BYTE *)SafeAllocaAllocateFromHeap(cbData);
  if ( !lpData )
  {
    v7 = -2146893810;
    v8 = 125;
    v9 = 2148073486LL;
    goto LABEL_8;
  }
  v5 = RegQueryValueExW(hKey, L"BioProtectionBioImage", 0, &Type, lpData, &cbData);
  if ( v5 )
  {
    v6 = 137;
    goto LABEL_3;
  }
  v7 = 0;
  *a3 = lpData;
  lpData = 0;
LABEL_14:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( lpData )
    MSCryptFree(lpData);
  return v7;
}

```

## disassembly

```asm
0x18006149c  mov     r11, rsp
0x18006149f  mov     [r11+18h], rbx
0x1800614a3  mov     [r11+10h], rdx
0x1800614a7  mov     [r11+8], rcx
0x1800614ab  push    rbp
0x1800614ac  push    rsi
0x1800614ad  push    rdi
0x1800614ae  mov     rbp, rsp
0x1800614b1  sub     rsp, 30h
0x1800614b5  mov     rsi, r8
0x1800614b8  mov     [rbp+hKey], 0
0x1800614c0  xor     edi, edi
0x1800614c2  lea     rax, [rbp+hKey]
0x1800614c6  xor     r8d, r8d; ulOptions
0x1800614c9  mov     [rbp+cbData], edi
0x1800614cc  mov     r9d, 20019h; samDesired
0x1800614d2  mov     [rbp+Type], edi
0x1800614d5  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Cry"...
0x1800614dc  mov     [r11-28h], rax
0x1800614e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800614e7  call    cs:__imp_RegOpenKeyExW
0x1800614ee  nop     dword ptr [rax+rax+00h]
0x1800614f3  test    eax, eax
0x1800614f5  jz      short loc_18006151A
0x1800614f7  lea     r9d, [rdi+60h]
0x1800614fb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061502  mov     ecx, eax
0x180061504  lea     rdx, aLresult; "lResult"
0x18006150b  call    DebugTraceError
0x180061510  mov     ebx, 8009001Eh
0x180061515  jmp     loc_1800615DF
0x18006151a  mov     rcx, [rbp+hKey]; hKey
0x18006151e  lea     rax, [rbp+cbData]
0x180061522  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180061527  lea     r9, [rbp+Type]; lpType
0x18006152b  xor     r8d, r8d; lpReserved
0x18006152e  mov     [rsp+30h+lpData], rdi; lpData
0x180061533  lea     rdx, aBioprotectionb; "BioProtectionBioImage"
0x18006153a  call    cs:__imp_RegQueryValueExW
0x180061541  nop     dword ptr [rax+rax+00h]
0x180061546  test    eax, eax
0x180061548  jz      short loc_180061552
0x18006154a  mov     r9d, 6Dh ; 'm'
0x180061550  jmp     short loc_1800614FB
0x180061552  cmp     [rbp+Type], 2
0x180061556  jz      short loc_18006157D
0x180061558  mov     ebx, 8009001Eh
0x18006155d  mov     r9d, 75h ; 'u'
0x180061563  mov     ecx, 8009001Eh
0x180061568  lea     rdx, aStatus; "Status"
0x18006156f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180061576  call    DebugTraceError
0x18006157b  jmp     short loc_1800615DF
0x18006157d  mov     ecx, [rbp+cbData]
0x180061580  call    SafeAllocaAllocateFromHeap
0x180061585  mov     rdi, rax
0x180061588  test    rax, rax
0x18006158b  jnz     short loc_18006159D
0x18006158d  mov     ebx, 8009000Eh
0x180061592  lea     r9d, [rax+7Dh]
0x180061596  mov     ecx, 8009000Eh
0x18006159b  jmp     short loc_180061568
0x18006159d  mov     rcx, [rbp+hKey]; hKey
0x1800615a1  lea     rax, [rbp+cbData]
0x1800615a5  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800615aa  lea     r9, [rbp+Type]; lpType
0x1800615ae  xor     r8d, r8d; lpReserved
0x1800615b1  mov     [rsp+30h+lpData], rdi; lpData
0x1800615b6  lea     rdx, aBioprotectionb; "BioProtectionBioImage"
0x1800615bd  call    cs:__imp_RegQueryValueExW
0x1800615c4  nop     dword ptr [rax+rax+00h]
0x1800615c9  test    eax, eax
0x1800615cb  jz      short loc_1800615D8
0x1800615cd  mov     r9d, 89h
0x1800615d3  jmp     loc_1800614FB
0x1800615d8  xor     ebx, ebx
0x1800615da  mov     [rsi], rdi
0x1800615dd  xor     edi, edi
0x1800615df  mov     rcx, [rbp+hKey]; hKey
0x1800615e3  test    rcx, rcx
0x1800615e6  jz      short loc_1800615FC
0x1800615e8  call    cs:__imp_RegCloseKey
0x1800615ef  nop     dword ptr [rax+rax+00h]
0x1800615f4  mov     [rbp+hKey], 0
0x1800615fc  test    rdi, rdi
0x1800615ff  jz      short loc_180061609
0x180061601  mov     rcx, rdi
0x180061604  call    MSCryptFree
0x180061609  mov     eax, ebx
0x18006160b  mov     rbx, [rsp+30h+arg_10]
0x180061610  add     rsp, 30h
0x180061614  pop     rdi
0x180061615  pop     rsi
0x180061616  pop     rbp
0x180061617  retn
```
