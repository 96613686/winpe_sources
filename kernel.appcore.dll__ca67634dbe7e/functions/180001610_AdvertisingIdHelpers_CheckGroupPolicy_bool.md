# AdvertisingIdHelpers::CheckGroupPolicy(bool *)

- ea: `0x180001610`
- end: `0x180001782`
- name: `?CheckGroupPolicy@AdvertisingIdHelpers@@YAJPEA_N@Z`
- size: `370`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800011a0`
- `0x180001380`

## callees

- `0x180001610`
- `0x1800020d0`
- `0x180002ad0`
- `0x1800058d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000166a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000166a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800016b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800016b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800016e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000175e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800016e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000175e`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CheckGroupPolicy(AdvertisingIdHelpers *this, bool *a2)
{
  int PersistedRegKeyPath; // eax
  unsigned int v4; // ebx
  WCHAR *v5; // rbx
  LSTATUS v6; // eax
  signed int v7; // edi
  LSTATUS ValueW; // eax
  char v10; // al
  int phkResult; // [rsp+20h] [rbp-48h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int pvData; // [rsp+78h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+20h] BYREF

  hkey = 0;
  pvData = 0;
  pcbData = 0;
  lpSubKey = 0;
  PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(this, (unsigned __int16 **)&lpSubKey);
  v4 = PersistedRegKeyPath;
  if ( PersistedRegKeyPath >= 0 )
  {
    v5 = (WCHAR *)lpSubKey;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hkey);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 != 2 )
        goto LABEL_5;
    }
    else
    {
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"DisabledByGroupPolicy", 0x10u, 0, &pvData, &pcbData);
      v7 = ValueW;
      if ( ValueW == 2 )
      {
        pvData = 0;
        goto LABEL_12;
      }
      if ( ValueW )
      {
LABEL_5:
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        Common::GlobalHeap::Free(v5);
        if ( hkey )
          RegCloseKey(hkey);
        return (unsigned int)v7;
      }
    }
    if ( pvData == 1 )
    {
      v10 = 1;
      goto LABEL_13;
    }
LABEL_12:
    v10 = 0;
LABEL_13:
    *(_BYTE *)this = v10;
    Common::GlobalHeap::Free(v5);
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E5,
    (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
    (const char *)(unsigned int)PersistedRegKeyPath,
    phkResult);
  Common::GlobalHeap::Free((void *)lpSubKey);
  if ( hkey )
    RegCloseKey(hkey);
  return v4;
}

```

## disassembly

```asm
0x180001610  mov     rax, rsp
0x180001613  push    rbx
0x180001614  push    rbp
0x180001615  push    rsi
0x180001616  sub     rsp, 50h
0x18000161a  xor     ebp, ebp
0x18000161c  lea     rdx, [rax-28h]; unsigned __int16 **
0x180001620  mov     [rax+20h], rbp
0x180001624  mov     rsi, rcx
0x180001627  mov     [rax+10h], ebp
0x18000162a  mov     [rax+18h], ebp
0x18000162d  mov     [rax-28h], rbp
0x180001631  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort * *)
0x180001636  mov     ebx, eax
0x180001638  test    eax, eax
0x18000163a  js      loc_18000172E
0x180001640  mov     rbx, [rsp+68h+lpSubKey]
0x180001645  lea     rax, [rsp+68h+hkey]
0x18000164d  mov     rdx, rbx; lpSubKey
0x180001650  mov     [rsp+68h+arg_0], rdi
0x180001655  mov     r9d, 20119h; samDesired
0x18000165b  mov     [rsp+68h+phkResult], rax; phkResult
0x180001660  xor     r8d, r8d; ulOptions
0x180001663  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000166a  call    cs:__imp_RegOpenKeyExW
0x180001670  mov     edi, eax
0x180001672  test    eax, eax
0x180001674  jnz     short loc_1800016F0
0x180001676  mov     rcx, [rsp+68h+hkey]; hkey
0x18000167e  lea     rax, [rsp+68h+arg_10]
0x180001686  mov     [rsp+68h+pcbData], rax; pcbData
0x18000168b  lea     r8, Value; "DisabledByGroupPolicy"
0x180001692  lea     rax, [rsp+68h+arg_8]
0x180001697  mov     [rsp+68h+arg_10], 4
0x1800016a2  mov     [rsp+68h+pvData], rax; pvData
0x1800016a7  mov     r9d, 10h; dwFlags
0x1800016ad  xor     edx, edx; lpSubKey
0x1800016af  mov     [rsp+68h+phkResult], rbp; pdwType
0x1800016b4  call    cs:__imp_RegGetValueW
0x1800016ba  mov     edi, eax
0x1800016bc  cmp     eax, 2
0x1800016bf  jz      loc_18000176E
0x1800016c5  test    eax, eax
0x1800016c7  jz      short loc_1800016F5
0x1800016c9  test    edi, edi
0x1800016cb  jg      loc_180001774
0x1800016d1  mov     rcx, rbx; void *
0x1800016d4  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800016d9  mov     rcx, [rsp+68h+hkey]; hKey
0x1800016e1  test    rcx, rcx
0x1800016e4  jz      short loc_1800016EC
0x1800016e6  call    cs:__imp_RegCloseKey
0x1800016ec  mov     eax, edi
0x1800016ee  jmp     short loc_18000171D
0x1800016f0  cmp     eax, 2
0x1800016f3  jnz     short loc_1800016C9
0x1800016f5  cmp     [rsp+68h+arg_8], 1
0x1800016fa  jz      short loc_18000172A
0x1800016fc  xor     al, al
0x1800016fe  mov     rcx, rbx; void *
0x180001701  mov     [rsi], al
0x180001703  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180001708  mov     rcx, [rsp+68h+hkey]; hKey
0x180001710  test    rcx, rcx
0x180001713  jz      short loc_18000171B
0x180001715  call    cs:__imp_RegCloseKey
0x18000171b  xor     eax, eax
0x18000171d  mov     rdi, [rsp+68h+arg_0]
0x180001722  add     rsp, 50h
0x180001726  pop     rsi
0x180001727  pop     rbp
0x180001728  pop     rbx
0x180001729  retn
0x18000172a  mov     al, 1
0x18000172c  jmp     short loc_1800016FE
0x18000172e  mov     rcx, [rsp+68h]; this
0x180001733  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000173a  mov     r9d, ebx; char *
0x18000173d  mov     edx, 1E5h; void *
0x180001742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001747  mov     rcx, [rsp+68h+lpSubKey]; void *
0x18000174c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180001751  mov     rcx, [rsp+68h+hkey]; hKey
0x180001759  test    rcx, rcx
0x18000175c  jz      short loc_180001764
0x18000175e  call    cs:__imp_RegCloseKey
0x180001764  mov     eax, ebx
0x180001766  add     rsp, 50h
0x18000176a  pop     rsi
0x18000176b  pop     rbp
0x18000176c  pop     rbx
0x18000176d  retn
0x18000176e  mov     [rsp+68h+arg_8], ebp
0x180001772  jmp     short loc_1800016FC
0x180001774  movzx   edi, di
0x180001777  or      edi, 80070000h
0x18000177d  jmp     loc_1800016D1
```
