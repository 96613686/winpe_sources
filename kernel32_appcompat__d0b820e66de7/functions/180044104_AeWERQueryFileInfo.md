# AeWERQueryFileInfo

- ea: `0x180044104`
- end: `0x1800444dd`
- name: `AeWERQueryFileInfo`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043e44`

## callees

- `0x18001f138`
- `0x18003fcbc`
- `0x1800431a0`
- `0x180044104`
- `0x180057c18`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18004427d`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x18004427d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800443a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004440f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800443a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004440f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800442fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004433f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800442fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004433f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004447b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800444a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004447b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800444a7`

## string_xrefs

- `0x18004419d`: `Failed to hash File path [%#x]`
- `0x1800441bf`: `AppCompat\Programs`
- `0x1800441ec`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x180044220`: `Amcache.hve`
- `0x180044311`: `Failed to open file key [%d]`
- `0x18004435a`: `Failed to open file key [%d]`

## pseudocode

```c
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  int v4; // edi
  signed int PersistedLocation; // ebx
  const char *v6; // r9
  int v7; // r8d
  unsigned int v8; // edx
  LSTATUS v9; // eax
  int v10; // r8d
  const char *v11; // r9
  int v12; // ecx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rsi
  LSTATUS v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v27[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR File[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(Destination, 0, 0x20Au);
  memset_0(v27, 0, 0x20Au);
  v3 = *(_DWORD *)(a1 + 4) == 528;
  pcbData = 0;
  phkResult = 0;
  hkey = 0;
  hKey = 0;
  if ( v3 && (v4 = 1, *(_DWORD *)a1 == 1) )
  {
    PersistedLocation = ComputeFileCacheKey(SubKey, v2, *(const unsigned __int16 **)(a1 + 8));
    if ( PersistedLocation < 0 )
    {
      v6 = "Failed to hash File path [%#x]";
      v7 = 125;
LABEL_5:
      AslLogCallPrintf(1, (unsigned int)"AeWERQueryFileInfo", v7, (_DWORD)v6);
      goto LABEL_42;
    }
    PersistedLocation = StringCchPrintfW(v27, 0x105u, L"%s\\%s", 2147352624, L"AppCompat\\Programs");
    if ( PersistedLocation < 0 )
    {
      v6 = "StringCchPrintf for StoreDirectory [%#x]";
      v7 = 136;
      goto LABEL_5;
    }
    PersistedLocation = AeGetPersistedLocation(Destination, v8, v27);
    if ( PersistedLocation < 0 )
    {
      v6 = "AeGetPersistedLocation failed [%#x]";
      v7 = 147;
      goto LABEL_5;
    }
    PersistedLocation = StringCchPrintfW(File, 0x104u, L"%s\\%s", Destination, L"Amcache.hve");
    if ( PersistedLocation < 0 )
    {
      v6 = "StringCchPrintf [%#x]";
      v7 = 157;
      goto LABEL_5;
    }
    v9 = RegLoadAppKeyW(File, &phkResult, 0x20019u, 0, 0);
    PersistedLocation = v9;
    if ( v9 )
    {
      if ( v9 == 5 || v9 == 2 )
      {
        v4 = 3;
        v10 = 171;
      }
      else
      {
        v10 = 175;
      }
      v11 = "RegLoadAppKey failed [%d]";
      goto LABEL_18;
    }
    v13 = RegOpenKeyExW(phkResult, L"Root", 0, 0x20019u, &hKey);
    PersistedLocation = v13;
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        v11 = "Failed to open file key [%d]";
        v10 = 189;
LABEL_18:
        v12 = v4;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    v14 = RegOpenKeyExW(hKey, L"InventoryApplicationFile", 0, 0x20019u, &hkey);
    PersistedLocation = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        v11 = "Failed to open file key [%d]";
        v10 = 199;
        goto LABEL_18;
      }
LABEL_20:
      PersistedLocation = (unsigned __int16)PersistedLocation | 0x80070000;
      goto LABEL_42;
    }
    v15 = a1 + 16;
    pcbData = 256;
    ValueW = RegGetValueW(hkey, SubKey, L"ProgramId", 2u, 0, (PVOID)(a1 + 16), &pcbData);
    PersistedLocation = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_20;
      v11 = "Failed to get program id [%d]";
      v10 = 220;
LABEL_30:
      v12 = 3;
LABEL_19:
      AslLogCallPrintf(v12, (unsigned int)"AeWERQueryFileInfo", v10, (_DWORD)v11);
      if ( PersistedLocation <= 0 )
        goto LABEL_42;
      goto LABEL_20;
    }
    pvData = (void *)(a1 + 272);
    pcbData = 256;
    v18 = RegGetValueW(hkey, SubKey, L"FileId", 2u, 0, pvData, &pcbData);
    PersistedLocation = v18;
    if ( v18 )
    {
      if ( v18 == 2 )
        goto LABEL_20;
      v11 = "Failed to get file id [%d]";
      v10 = 242;
      goto LABEL_30;
    }
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)pvData + v20) );
    if ( v20 != 44 )
      goto LABEL_40;
    do
      ++v19;
    while ( *(_WORD *)(v15 + 2 * v19) );
    if ( v19 == 44 )
      PersistedLocation = 0;
    else
LABEL_40:
      PersistedLocation = -2147024894;
  }
  else
  {
    PersistedLocation = -2147024809;
  }
LABEL_42:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)PersistedLocation;
}

```

## disassembly

```asm
0x180044104  mov     [rsp-8+arg_8], rbx
0x180044109  mov     [rsp-8+arg_10], rsi
0x18004410e  push    rbp
0x18004410f  push    rdi
0x180044110  push    r14
0x180044112  lea     rbp, [rsp-600h]
0x18004411a  sub     rsp, 700h
0x180044121  mov     rax, cs:__security_cookie
0x180044128  xor     rax, rsp
0x18004412b  mov     [rbp+610h+var_20], rax
0x180044132  mov     rsi, rcx
0x180044135  mov     ebx, 20Ah
0x18004413a  mov     r8d, ebx; Size
0x18004413d  lea     rcx, [rbp+610h+Destination]; void *
0x180044144  xor     edx, edx; Val
0x180044146  call    memset_0
0x18004414b  mov     r8d, ebx; Size
0x18004414e  lea     rcx, [rbp+610h+var_650]; void *
0x180044152  xor     edx, edx; Val
0x180044154  call    memset_0
0x180044159  xor     r14d, r14d
0x18004415c  cmp     dword ptr [rsi+4], 210h
0x180044163  mov     [rsp+710h+var_6D0], r14d
0x180044168  mov     [rsp+710h+phkResult], r14
0x18004416d  mov     [rsp+710h+hkey], r14
0x180044172  mov     [rsp+710h+hKey], r14
0x180044177  jnz     loc_18004446C
0x18004417d  lea     edi, [r14+1]
0x180044181  cmp     [rsi], edi
0x180044183  jnz     loc_18004446C
0x180044189  mov     r8, [rsi+8]; unsigned __int16 *
0x18004418d  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x180044192  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x180044197  mov     ebx, eax
0x180044199  test    eax, eax
0x18004419b  jns     short loc_1800441BF
0x18004419d  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x1800441a4  lea     r8d, [r14+7Dh]
0x1800441a8  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800441af  mov     [rsp+710h+Reserved], eax
0x1800441b3  mov     ecx, edi
0x1800441b5  call    AslLogCallPrintf
0x1800441ba  jmp     loc_180044471
0x1800441bf  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x1800441c6  mov     r9d, 7FFE0030h
0x1800441cc  lea     r8, aSS; "%s\\%s"
0x1800441d3  mov     qword ptr [rsp+710h+Reserved], rax
0x1800441d8  mov     edx, 105h; unsigned __int64
0x1800441dd  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x1800441e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800441e6  mov     ebx, eax
0x1800441e8  test    eax, eax
0x1800441ea  jns     short loc_1800441FB
0x1800441ec  lea     r9, aStringcchprint; "StringCchPrintf for StoreDirectory [%#x"...
0x1800441f3  mov     r8d, 88h
0x1800441f9  jmp     short loc_1800441A8
0x1800441fb  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x1800441ff  lea     rcx, [rbp+610h+Destination]; Destination
0x180044206  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x18004420b  mov     ebx, eax
0x18004420d  test    eax, eax
0x18004420f  jns     short loc_180044220
0x180044211  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x180044218  mov     r8d, 93h
0x18004421e  jmp     short loc_1800441A8
0x180044220  lea     rax, aAmcacheHve; "Amcache.hve"
0x180044227  mov     edx, 104h; unsigned __int64
0x18004422c  lea     r9, [rbp+610h+Destination]
0x180044233  mov     qword ptr [rsp+710h+Reserved], rax
0x180044238  lea     r8, aSS; "%s\\%s"
0x18004423f  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x180044246  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004424b  mov     ebx, eax
0x18004424d  test    eax, eax
0x18004424f  jns     short loc_180044263
0x180044251  lea     r9, aStringcchprint_0; "StringCchPrintf [%#x]"
0x180044258  mov     r8d, 9Dh
0x18004425e  jmp     loc_1800441A8
0x180044263  xor     r9d, r9d; dwOptions
0x180044266  mov     [rsp+710h+Reserved], r14d; Reserved
0x18004426b  mov     r8d, 20019h; samDesired
0x180044271  lea     rdx, [rsp+710h+phkResult]; phkResult
0x180044276  lea     rcx, [rbp+610h+File]; lpFile
0x18004427d  call    cs:__imp_RegLoadAppKeyW
0x180044284  nop     dword ptr [rax+rax+00h]
0x180044289  mov     ebx, eax
0x18004428b  test    eax, eax
0x18004428d  jz      short loc_1800442DB
0x18004428f  cmp     eax, 5
0x180044292  jz      short loc_1800442A1
0x180044294  cmp     eax, 2
0x180044297  jz      short loc_1800442A1
0x180044299  mov     r8d, 0AFh
0x18004429f  jmp     short loc_1800442AC
0x1800442a1  mov     edi, 3
0x1800442a6  mov     r8d, 0ABh
0x1800442ac  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x1800442b3  mov     ecx, edi
0x1800442b5  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800442bc  mov     [rsp+710h+Reserved], ebx
0x1800442c0  call    AslLogCallPrintf
0x1800442c5  test    ebx, ebx
0x1800442c7  jle     loc_180044471
0x1800442cd  movzx   ebx, bx
0x1800442d0  or      ebx, 80070000h
0x1800442d6  jmp     loc_180044471
0x1800442db  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800442e0  lea     rax, [rsp+710h+hKey]
0x1800442e5  mov     r9d, 20019h; samDesired
0x1800442eb  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800442f0  xor     r8d, r8d; ulOptions
0x1800442f3  lea     rdx, aRoot; "Root"
0x1800442fa  call    cs:__imp_RegOpenKeyExW
0x180044301  nop     dword ptr [rax+rax+00h]
0x180044306  mov     ebx, eax
0x180044308  test    eax, eax
0x18004430a  jz      short loc_180044320
0x18004430c  cmp     eax, 2
0x18004430f  jz      short loc_1800442CD
0x180044311  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x180044318  mov     r8d, 0BDh
0x18004431e  jmp     short loc_1800442B3
0x180044320  mov     rcx, [rsp+710h+hKey]; hKey
0x180044325  lea     rax, [rsp+710h+hkey]
0x18004432a  mov     r9d, 20019h; samDesired
0x180044330  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180044335  xor     r8d, r8d; ulOptions
0x180044338  lea     rdx, aInventoryappli; "InventoryApplicationFile"
0x18004433f  call    cs:__imp_RegOpenKeyExW
0x180044346  nop     dword ptr [rax+rax+00h]
0x18004434b  mov     ebx, eax
0x18004434d  test    eax, eax
0x18004434f  jz      short loc_18004436C
0x180044351  cmp     eax, 2
0x180044354  jz      loc_1800442CD
0x18004435a  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x180044361  mov     r8d, 0C7h
0x180044367  jmp     loc_1800442B3
0x18004436c  mov     rcx, [rsp+710h+hkey]; hkey
0x180044371  lea     rax, [rsp+710h+var_6D0]
0x180044376  mov     [rsp+710h+pcbData], rax; pcbData
0x18004437b  lea     rdi, [rsi+10h]
0x18004437f  mov     [rsp+710h+pvData], rdi; pvData
0x180044384  lea     r8, aProgramid; "ProgramId"
0x18004438b  mov     r9d, 2; dwFlags
0x180044391  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x180044396  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x18004439b  mov     [rsp+710h+var_6D0], 100h
0x1800443a3  call    cs:__imp_RegGetValueW
0x1800443aa  nop     dword ptr [rax+rax+00h]
0x1800443af  mov     ebx, eax
0x1800443b1  test    eax, eax
0x1800443b3  jz      short loc_1800443D5
0x1800443b5  cmp     eax, 2
0x1800443b8  jz      loc_1800442CD
0x1800443be  lea     r9, aFailedToGetPro_0; "Failed to get program id [%d]"
0x1800443c5  mov     r8d, 0DCh
0x1800443cb  mov     ecx, 3
0x1800443d0  jmp     loc_1800442B5
0x1800443d5  mov     rcx, [rsp+710h+hkey]; hkey
0x1800443da  lea     rax, [rsp+710h+var_6D0]
0x1800443df  mov     [rsp+710h+pcbData], rax; pcbData
0x1800443e4  lea     r8, aFileid; "FileId"
0x1800443eb  add     rsi, 110h
0x1800443f2  mov     [rsp+710h+var_6D0], 100h
0x1800443fa  mov     [rsp+710h+pvData], rsi; pvData
0x1800443ff  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180044404  mov     r9d, 2; dwFlags
0x18004440a  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18004440f  call    cs:__imp_RegGetValueW
0x180044416  nop     dword ptr [rax+rax+00h]
0x18004441b  mov     ebx, eax
0x18004441d  test    eax, eax
0x18004441f  jz      short loc_180044439
0x180044421  cmp     eax, 2
0x180044424  jz      loc_1800442CD
0x18004442a  lea     r9, aFailedToGetFil; "Failed to get file id [%d]"
0x180044431  mov     r8d, 0F2h
0x180044437  jmp     short loc_1800443CB
0x180044439  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004443d  mov     rcx, rax
0x180044440  inc     rcx
0x180044443  cmp     [rsi+rcx*2], r14w
0x180044448  jnz     short loc_180044440
0x18004444a  cmp     rcx, 2Ch ; ','
0x18004444e  jnz     short loc_180044465
0x180044450  inc     rax
0x180044453  cmp     [rdi+rax*2], r14w
0x180044458  jnz     short loc_180044450
0x18004445a  cmp     rax, 2Ch ; ','
0x18004445e  jnz     short loc_180044465
0x180044460  mov     ebx, r14d
0x180044463  jmp     short loc_180044471
0x180044465  mov     ebx, 80070002h
0x18004446a  jmp     short loc_180044471
0x18004446c  mov     ebx, 80070057h
0x180044471  mov     rcx, [rsp+710h+hkey]; hKey
0x180044476  test    rcx, rcx
0x180044479  jz      short loc_180044487
0x18004447b  call    cs:__imp_RegCloseKey
0x180044482  nop     dword ptr [rax+rax+00h]
0x180044487  mov     rcx, [rsp+710h+hKey]; hKey
0x18004448c  test    rcx, rcx
0x18004448f  jz      short loc_18004449D
0x180044491  call    cs:__imp_RegCloseKey
0x180044498  nop     dword ptr [rax+rax+00h]
0x18004449d  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800444a2  test    rcx, rcx
0x1800444a5  jz      short loc_1800444B3
0x1800444a7  call    cs:__imp_RegCloseKey
0x1800444ae  nop     dword ptr [rax+rax+00h]
0x1800444b3  mov     eax, ebx
0x1800444b5  mov     rcx, [rbp+610h+var_20]
0x1800444bc  xor     rcx, rsp; StackCookie
0x1800444bf  call    __security_check_cookie
0x1800444c4  lea     r11, [rsp+710h+var_10]
0x1800444cc  mov     rbx, [r11+28h]
0x1800444d0  mov     rsi, [r11+30h]
0x1800444d4  mov     rsp, r11
0x1800444d7  pop     r14
0x1800444d9  pop     rdi
0x1800444da  pop     rbp
0x1800444db  retn
```
