# AdvertisingIdHelpers::CreateOrOpenHkcuRootKey(ushort const *,HKEY__ * *)

- ea: `0x1800061c4`
- end: `0x18000626e`
- name: `?CreateOrOpenHkcuRootKey@AdvertisingIdHelpers@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(HKEY lpString2, const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800060c0`
- `0x180006274`

## callees

- `0x180002b70`
- `0x180004f00`
- `0x180005e44`
- `0x1800061c4`
- `0x180006324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006256`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006256`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CreateOrOpenHkcuRootKey(
        unsigned __int16 *lpString2,
        unsigned __int16 *a2,
        HKEY *a3)
{
  int v5; // eax
  const unsigned __int16 *v6; // r8
  int v7; // ebx
  HKEY v8; // rcx
  HKEY v9; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD v13; // [rsp+40h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+20h] BYREF

  hKey = 0;
  v13 = 2;
  v5 = AdvertisingIdHelpers::CreateAdvertisingRegKeyForUser(lpString2, (__int64)a2, &hKey, &v13);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v5,
      v11);
LABEL_6:
    v8 = hKey;
    goto LABEL_8;
  }
  if ( v13 == 1 )
  {
    v7 = AdvertisingIdHelpers::SetDaclForRootKey(hKey, lpString2, v6);
    if ( v7 < 0 )
    {
      AdvertisingIdHelpers::DeleteAdvertisingRegKeyForUser(lpString2);
      goto LABEL_6;
    }
  }
  v9 = hKey;
  v8 = 0;
  hKey = 0;
  v7 = 0;
  *(_QWORD *)a2 = v9;
LABEL_8:
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800061c4  mov     rax, rsp
0x1800061c7  mov     [rax+8], rbx
0x1800061cb  mov     [rax+10h], rsi
0x1800061cf  push    rdi; int
0x1800061d0  sub     rsp, 20h
0x1800061d4  lea     r9, [rax+18h]
0x1800061d8  mov     qword ptr [rax+20h], 0
0x1800061e0  lea     r8, [rax+20h]
0x1800061e4  mov     dword ptr [rax+18h], 2
0x1800061eb  mov     rsi, rdx
0x1800061ee  mov     rdi, rcx
0x1800061f1  call    AdvertisingIdHelpers__CreateAdvertisingRegKeyForUser
0x1800061f6  mov     ebx, eax
0x1800061f8  test    eax, eax
0x1800061fa  jns     short loc_180006217
0x1800061fc  mov     rcx, [rsp+28h]; this
0x180006201  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180006208  mov     r9d, eax; char *
0x18000620b  mov     edx, 171h; void *
0x180006210  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006215  jmp     short loc_180006239
0x180006217  cmp     [rsp+28h+arg_10], 1
0x18000621c  jnz     short loc_180006240
0x18000621e  mov     rcx, [rsp+28h+hKey]; hKey
0x180006223  mov     rdx, rdi; lpString2
0x180006226  call    ?SetDaclForRootKey@AdvertisingIdHelpers@@YAJPEAUHKEY__@@PEBG@Z; AdvertisingIdHelpers::SetDaclForRootKey(HKEY__ *,ushort const *)
0x18000622b  mov     ebx, eax
0x18000622d  test    eax, eax
0x18000622f  jns     short loc_180006240
0x180006231  mov     rcx, rdi
0x180006234  call    AdvertisingIdHelpers__DeleteAdvertisingRegKeyForUser
0x180006239  mov     rcx, [rsp+28h+hKey]
0x18000623e  jmp     short loc_180006251
0x180006240  mov     rax, [rsp+28h+hKey]
0x180006245  xor     ecx, ecx; hKey
0x180006247  mov     [rsp+28h+hKey], rcx
0x18000624c  xor     ebx, ebx
0x18000624e  mov     [rsi], rax
0x180006251  test    rcx, rcx
0x180006254  jz      short loc_18000625C
0x180006256  call    cs:__imp_RegCloseKey
0x18000625c  mov     rsi, [rsp+28h+arg_8]
0x180006261  mov     eax, ebx
0x180006263  mov     rbx, [rsp+28h+arg_0]
0x180006268  add     rsp, 20h
0x18000626c  pop     rdi
0x18000626d  retn
```
