# EEDBManager::SetRenewStateAndErrorCode(_GUID,ulong,long)

- ea: `0x1800214ec`
- end: `0x1800215d4`
- name: `?SetRenewStateAndErrorCode@EEDBManager@@QEAAJU_GUID@@KJ@Z`
- size: `232`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct _GUID *__struct_ptr, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e5dc`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x1800214ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021565`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800215a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021565`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800215a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800215c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800215c1`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetRenewStateAndErrorCode(EEDBManager *this, struct _GUID *a2, int a3, int a4)
{
  LSTATUS v5; // eax
  HKEY v6; // rcx
  signed int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  struct _GUID v11; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  int lpData; // [rsp+68h] [rbp+28h] BYREF

  lpData = a4;
  Data = a3;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v11 = *a2;
  v5 = EEDBManager::OpenEnrollmentKey(&v11, 131103, 0, &hKey);
  v6 = hKey;
  v7 = v5;
  if ( v5 >= 0 )
  {
    v8 = RegSetValueExW(hKey, L"RenewStatus", 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    v6 = hKey;
    if ( v7 >= 0 )
    {
      v9 = RegSetValueExW(hKey, L"RenewErrorCode", 0, 4u, (const BYTE *)&lpData, 4u);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      v6 = hKey;
    }
  }
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800214ec  mov     rax, rsp
0x1800214ef  mov     [rax+10h], rbx
0x1800214f3  mov     [rax+20h], r9d
0x1800214f7  mov     [rax+18h], r8d
0x1800214fb  mov     [rax+8], rcx
0x1800214ff  push    rbp
0x180021500  mov     rbp, rsp
0x180021503  sub     rsp, 40h
0x180021507  mov     rbx, rdx
0x18002150a  mov     [rbp+hKey], 0
0x180021512  xor     edx, edx
0x180021514  lea     rcx, [rbp+hKey]
0x180021518  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002151d  movaps  xmm0, xmmword ptr [rbx]
0x180021520  lea     r9, [rbp+hKey]; HKEY *
0x180021524  xor     r8d, r8d; unsigned __int16 *
0x180021527  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18002152c  mov     edx, 2001Fh; unsigned int
0x180021531  lea     rcx, [rbp+var_10]; struct _GUID
0x180021535  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18002153a  mov     rcx, [rbp+hKey]; hKey
0x18002153e  mov     ebx, eax
0x180021540  test    eax, eax
0x180021542  js      short loc_1800215BC
0x180021544  lea     rax, [rbp+Data]
0x180021548  mov     [rsp+40h+cbData], 4; cbData
0x180021550  mov     r9d, 4; dwType
0x180021556  mov     [rsp+40h+lpData], rax; lpData
0x18002155b  xor     r8d, r8d; Reserved
0x18002155e  lea     rdx, aRenewstatus; "RenewStatus"
0x180021565  call    cs:__imp_RegSetValueExW
0x18002156b  mov     ebx, eax
0x18002156d  test    eax, eax
0x18002156f  jle     short loc_18002157A
0x180021571  movzx   ebx, ax
0x180021574  or      ebx, 80070000h
0x18002157a  mov     rcx, [rbp+hKey]; hKey
0x18002157e  test    ebx, ebx
0x180021580  js      short loc_1800215BC
0x180021582  lea     rax, [rbp+arg_18]
0x180021586  mov     [rsp+40h+cbData], 4; cbData
0x18002158e  mov     r9d, 4; dwType
0x180021594  mov     [rsp+40h+lpData], rax; lpData
0x180021599  xor     r8d, r8d; Reserved
0x18002159c  lea     rdx, aRenewerrorcode; "RenewErrorCode"
0x1800215a3  call    cs:__imp_RegSetValueExW
0x1800215a9  mov     ebx, eax
0x1800215ab  test    eax, eax
0x1800215ad  jle     short loc_1800215B8
0x1800215af  movzx   ebx, ax
0x1800215b2  or      ebx, 80070000h
0x1800215b8  mov     rcx, [rbp+hKey]; hKey
0x1800215bc  test    rcx, rcx
0x1800215bf  jz      short loc_1800215C7
0x1800215c1  call    cs:__imp_RegCloseKey
0x1800215c7  mov     eax, ebx
0x1800215c9  mov     rbx, [rsp+40h+arg_8]
0x1800215ce  add     rsp, 40h
0x1800215d2  pop     rbp
0x1800215d3  retn
```
