# AeWERQueryFileInfo

- ea: `0x180040590`
- end: `0x180040934`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800402f0`

## callees

- `0x1800212e4`
- `0x18003c2f4`
- `0x18003f6fc`
- `0x180040590`
- `0x180052880`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180040709`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180040709`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040819`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004087f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040819`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004087f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800407bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800407bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800408e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800408f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800408e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800408f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040905`

## string_xrefs

- `0x180040629`: `Failed to hash File path [%#x]`
- `0x18004064b`: `AppCompat\Programs`
- `0x180040678`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x1800406ac`: `Amcache.hve`
- `0x180040791`: `Failed to open file key [%d]`
- `0x1800407d0`: `Failed to open file key [%d]`

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
0x180040590  mov     [rsp-8+arg_8], rbx
0x180040595  mov     [rsp-8+arg_10], rsi
0x18004059a  push    rbp
0x18004059b  push    rdi
0x18004059c  push    r14
0x18004059e  lea     rbp, [rsp-600h]
0x1800405a6  sub     rsp, 700h
0x1800405ad  mov     rax, cs:__security_cookie
0x1800405b4  xor     rax, rsp
0x1800405b7  mov     [rbp+610h+var_20], rax
0x1800405be  mov     rsi, rcx
0x1800405c1  mov     ebx, 20Ah
0x1800405c6  mov     r8d, ebx; Size
0x1800405c9  lea     rcx, [rbp+610h+Destination]; void *
0x1800405d0  xor     edx, edx; Val
0x1800405d2  call    memset_0
0x1800405d7  mov     r8d, ebx; Size
0x1800405da  lea     rcx, [rbp+610h+var_650]; void *
0x1800405de  xor     edx, edx; Val
0x1800405e0  call    memset_0
0x1800405e5  xor     r14d, r14d
0x1800405e8  cmp     dword ptr [rsi+4], 210h
0x1800405ef  mov     [rsp+710h+var_6D0], r14d
0x1800405f4  mov     [rsp+710h+phkResult], r14
0x1800405f9  mov     [rsp+710h+hkey], r14
0x1800405fe  mov     [rsp+710h+hKey], r14
0x180040603  jnz     loc_1800408D6
0x180040609  lea     edi, [r14+1]
0x18004060d  cmp     [rsi], edi
0x18004060f  jnz     loc_1800408D6
0x180040615  mov     r8, [rsi+8]; unsigned __int16 *
0x180040619  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x18004061e  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x180040623  mov     ebx, eax
0x180040625  test    eax, eax
0x180040627  jns     short loc_18004064B
0x180040629  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x180040630  lea     r8d, [r14+7Dh]
0x180040634  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18004063b  mov     [rsp+710h+Reserved], eax
0x18004063f  mov     ecx, edi
0x180040641  call    AslLogCallPrintf
0x180040646  jmp     loc_1800408DB
0x18004064b  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x180040652  mov     r9d, 7FFE0030h
0x180040658  lea     r8, aSS; "%s\\%s"
0x18004065f  mov     qword ptr [rsp+710h+Reserved], rax
0x180040664  mov     edx, 105h; unsigned __int64
0x180040669  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x18004066d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040672  mov     ebx, eax
0x180040674  test    eax, eax
0x180040676  jns     short loc_180040687
0x180040678  lea     r9, aStringcchprint; "StringCchPrintf for StoreDirectory [%#x"...
0x18004067f  mov     r8d, 88h
0x180040685  jmp     short loc_180040634
0x180040687  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x18004068b  lea     rcx, [rbp+610h+Destination]; Destination
0x180040692  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x180040697  mov     ebx, eax
0x180040699  test    eax, eax
0x18004069b  jns     short loc_1800406AC
0x18004069d  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1800406a4  mov     r8d, 93h
0x1800406aa  jmp     short loc_180040634
0x1800406ac  lea     rax, aAmcacheHve; "Amcache.hve"
0x1800406b3  mov     edx, 104h; unsigned __int64
0x1800406b8  lea     r9, [rbp+610h+Destination]
0x1800406bf  mov     qword ptr [rsp+710h+Reserved], rax
0x1800406c4  lea     r8, aSS; "%s\\%s"
0x1800406cb  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1800406d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800406d7  mov     ebx, eax
0x1800406d9  test    eax, eax
0x1800406db  jns     short loc_1800406EF
0x1800406dd  lea     r9, aStringcchprint_0; "StringCchPrintf [%#x]"
0x1800406e4  mov     r8d, 9Dh
0x1800406ea  jmp     loc_180040634
0x1800406ef  xor     r9d, r9d; dwOptions
0x1800406f2  mov     [rsp+710h+Reserved], r14d; Reserved
0x1800406f7  mov     r8d, 20019h; samDesired
0x1800406fd  lea     rdx, [rsp+710h+phkResult]; phkResult
0x180040702  lea     rcx, [rbp+610h+File]; lpFile
0x180040709  call    cs:__imp_RegLoadAppKeyW
0x18004070f  mov     ebx, eax
0x180040711  test    eax, eax
0x180040713  jz      short loc_180040761
0x180040715  cmp     eax, 5
0x180040718  jz      short loc_180040727
0x18004071a  cmp     eax, 2
0x18004071d  jz      short loc_180040727
0x18004071f  mov     r8d, 0AFh
0x180040725  jmp     short loc_180040732
0x180040727  mov     edi, 3
0x18004072c  mov     r8d, 0ABh
0x180040732  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x180040739  mov     ecx, edi
0x18004073b  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180040742  mov     [rsp+710h+Reserved], ebx
0x180040746  call    AslLogCallPrintf
0x18004074b  test    ebx, ebx
0x18004074d  jle     loc_1800408DB
0x180040753  movzx   ebx, bx
0x180040756  or      ebx, 80070000h
0x18004075c  jmp     loc_1800408DB
0x180040761  mov     rcx, [rsp+710h+phkResult]; hKey
0x180040766  lea     rax, [rsp+710h+hKey]
0x18004076b  mov     r9d, 20019h; samDesired
0x180040771  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180040776  xor     r8d, r8d; ulOptions
0x180040779  lea     rdx, aRoot; "Root"
0x180040780  call    cs:__imp_RegOpenKeyExW
0x180040786  mov     ebx, eax
0x180040788  test    eax, eax
0x18004078a  jz      short loc_1800407A0
0x18004078c  cmp     eax, 2
0x18004078f  jz      short loc_180040753
0x180040791  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x180040798  mov     r8d, 0BDh
0x18004079e  jmp     short loc_180040739
0x1800407a0  mov     rcx, [rsp+710h+hKey]; hKey
0x1800407a5  lea     rax, [rsp+710h+hkey]
0x1800407aa  mov     r9d, 20019h; samDesired
0x1800407b0  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800407b5  xor     r8d, r8d; ulOptions
0x1800407b8  lea     rdx, aInventoryappli; "InventoryApplicationFile"
0x1800407bf  call    cs:__imp_RegOpenKeyExW
0x1800407c5  mov     ebx, eax
0x1800407c7  test    eax, eax
0x1800407c9  jz      short loc_1800407E2
0x1800407cb  cmp     eax, 2
0x1800407ce  jz      short loc_180040753
0x1800407d0  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x1800407d7  mov     r8d, 0C7h
0x1800407dd  jmp     loc_180040739
0x1800407e2  mov     rcx, [rsp+710h+hkey]; hkey
0x1800407e7  lea     rax, [rsp+710h+var_6D0]
0x1800407ec  mov     [rsp+710h+pcbData], rax; pcbData
0x1800407f1  lea     rdi, [rsi+10h]
0x1800407f5  mov     [rsp+710h+pvData], rdi; pvData
0x1800407fa  lea     r8, aProgramid; "ProgramId"
0x180040801  mov     r9d, 2; dwFlags
0x180040807  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18004080c  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180040811  mov     [rsp+710h+var_6D0], 100h
0x180040819  call    cs:__imp_RegGetValueW
0x18004081f  mov     ebx, eax
0x180040821  test    eax, eax
0x180040823  jz      short loc_180040845
0x180040825  cmp     eax, 2
0x180040828  jz      loc_180040753
0x18004082e  lea     r9, aFailedToGetPro_0; "Failed to get program id [%d]"
0x180040835  mov     r8d, 0DCh
0x18004083b  mov     ecx, 3
0x180040840  jmp     loc_18004073B
0x180040845  mov     rcx, [rsp+710h+hkey]; hkey
0x18004084a  lea     rax, [rsp+710h+var_6D0]
0x18004084f  mov     [rsp+710h+pcbData], rax; pcbData
0x180040854  lea     r8, aFileid; "FileId"
0x18004085b  add     rsi, 110h
0x180040862  mov     [rsp+710h+var_6D0], 100h
0x18004086a  mov     [rsp+710h+pvData], rsi; pvData
0x18004086f  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180040874  mov     r9d, 2; dwFlags
0x18004087a  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18004087f  call    cs:__imp_RegGetValueW
0x180040885  mov     ebx, eax
0x180040887  test    eax, eax
0x180040889  jz      short loc_1800408A3
0x18004088b  cmp     eax, 2
0x18004088e  jz      loc_180040753
0x180040894  lea     r9, aFailedToGetFil; "Failed to get file id [%d]"
0x18004089b  mov     r8d, 0F2h
0x1800408a1  jmp     short loc_18004083B
0x1800408a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800408a7  mov     rcx, rax
0x1800408aa  inc     rcx
0x1800408ad  cmp     [rsi+rcx*2], r14w
0x1800408b2  jnz     short loc_1800408AA
0x1800408b4  cmp     rcx, 2Ch ; ','
0x1800408b8  jnz     short loc_1800408CF
0x1800408ba  inc     rax
0x1800408bd  cmp     [rdi+rax*2], r14w
0x1800408c2  jnz     short loc_1800408BA
0x1800408c4  cmp     rax, 2Ch ; ','
0x1800408c8  jnz     short loc_1800408CF
0x1800408ca  mov     ebx, r14d
0x1800408cd  jmp     short loc_1800408DB
0x1800408cf  mov     ebx, 80070002h
0x1800408d4  jmp     short loc_1800408DB
0x1800408d6  mov     ebx, 80070057h
0x1800408db  mov     rcx, [rsp+710h+hkey]; hKey
0x1800408e0  test    rcx, rcx
0x1800408e3  jz      short loc_1800408EB
0x1800408e5  call    cs:__imp_RegCloseKey
0x1800408eb  mov     rcx, [rsp+710h+hKey]; hKey
0x1800408f0  test    rcx, rcx
0x1800408f3  jz      short loc_1800408FB
0x1800408f5  call    cs:__imp_RegCloseKey
0x1800408fb  mov     rcx, [rsp+710h+phkResult]; hKey
0x180040900  test    rcx, rcx
0x180040903  jz      short loc_18004090B
0x180040905  call    cs:__imp_RegCloseKey
0x18004090b  mov     eax, ebx
0x18004090d  mov     rcx, [rbp+610h+var_20]
0x180040914  xor     rcx, rsp; StackCookie
0x180040917  call    __security_check_cookie
0x18004091c  lea     r11, [rsp+710h+var_10]
0x180040924  mov     rbx, [r11+28h]
0x180040928  mov     rsi, [r11+30h]
0x18004092c  mov     rsp, r11
0x18004092f  pop     r14
0x180040931  pop     rdi
0x180040932  pop     rbp
0x180040933  retn
```
