# OmaDmDeleteUserInfo

- ea: `0x180016a80`
- end: `0x180016be6`
- name: `OmaDmDeleteUserInfo`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b750`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x180009bf4`
- `0x18000c814`
- `0x18000dfc0`
- `0x18000f47c`
- `0x180016a80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ba9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016bc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016bc7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016b53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016b53`
- `DMCmnUtils!CopyString` at `0x180016ada`
- `DMCmnUtils!CopyString` at `0x180016ada`

## pseudocode

```c
__int64 __fastcall OmaDmDeleteUserInfo(const unsigned __int16 *a1, __int64 a2)
{
  int v2; // ebx
  signed int AccountIDFromLookupID; // ebx
  __int64 v5; // rax
  LSTATUS v6; // eax
  bool v7; // cc
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+28h] BYREF

  v2 = a2;
  hMem = 0;
  hObject = 0;
  hKey = 0;
  if ( !(unsigned int)IsValidAccountID(a1, a2) || !a1 )
    goto LABEL_2;
  if ( !v2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, &hMem);
LABEL_9:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_17;
    goto LABEL_10;
  }
  if ( v2 != 1 )
  {
LABEL_2:
    AccountIDFromLookupID = -2147024809;
    goto LABEL_17;
  }
  AccountIDFromLookupID = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( AccountIDFromLookupID < 0 )
    goto LABEL_9;
LABEL_10:
  AccountIDFromLookupID = AcquireOmaDmMutex(&hObject);
  if ( AccountIDFromLookupID >= 0 )
  {
    v5 = ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    AccountIDFromLookupID = GetAccountKey(hMem, 1, 131334, v5, 0);
    if ( AccountIDFromLookupID >= 0 )
    {
      v6 = RegDeleteTreeW(hKey, L"UserInfo");
      v7 = v6 <= 0;
      if ( v6
        || (Data = 0, v6 = RegSetValueExW(hKey, L"CountOfUserInfo", 0, 4u, (const BYTE *)&Data, 4u), v7 = v6 <= 0, v6) )
      {
        if ( v7 )
          AccountIDFromLookupID = v6;
        else
          AccountIDFromLookupID = (unsigned __int16)v6 | 0x80070000;
      }
    }
  }
LABEL_17:
  LocalFree(hMem);
  ReleaseOmaDmMutex(hObject);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x180016a80  mov     [rsp-8+arg_0], rbx
0x180016a85  mov     [rsp-8+arg_8], rdi
0x180016a8a  push    rbp
0x180016a8b  mov     rbp, rsp
0x180016a8e  sub     rsp, 40h
0x180016a92  mov     ebx, edx
0x180016a94  mov     [rbp+hMem], 0
0x180016a9c  mov     rdi, rcx
0x180016a9f  mov     [rbp+hObject], 0
0x180016aa7  mov     [rbp+hKey], 0
0x180016aaf  call    IsValidAccountID
0x180016ab4  test    eax, eax
0x180016ab6  jnz     short loc_180016AC2
0x180016ab8  mov     ebx, 80070057h
0x180016abd  jmp     loc_180016BA5
0x180016ac2  test    rdi, rdi
0x180016ac5  jz      short loc_180016AB8
0x180016ac7  test    ebx, ebx
0x180016ac9  jz      short loc_180016AEE
0x180016acb  cmp     ebx, 1
0x180016ace  jnz     short loc_180016AB8
0x180016ad0  lea     r8, [rbp+hMem]
0x180016ad4  or      edx, 0FFFFFFFFh
0x180016ad7  mov     rcx, rdi
0x180016ada  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180016ae1  nop     dword ptr [rax+rax+00h]
0x180016ae6  mov     ebx, eax
0x180016ae8  test    eax, eax
0x180016aea  js      short loc_180016AFE
0x180016aec  jmp     short loc_180016B06
0x180016aee  lea     r8, [rbp+hMem]
0x180016af2  xor     edx, edx
0x180016af4  mov     rcx, rdi
0x180016af7  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x180016afc  mov     ebx, eax
0x180016afe  test    ebx, ebx
0x180016b00  js      loc_180016BA5
0x180016b06  lea     rcx, [rbp+hObject]; void **
0x180016b0a  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180016b0f  mov     ebx, eax
0x180016b11  test    eax, eax
0x180016b13  js      loc_180016BA5
0x180016b19  lea     rcx, [rbp+hKey]
0x180016b1d  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180016b22  mov     rcx, [rbp+hMem]
0x180016b26  mov     r9, rax
0x180016b29  mov     edx, 1
0x180016b2e  mov     [rsp+40h+lpData], 0
0x180016b37  mov     r8d, 20106h
0x180016b3d  call    GetAccountKey
0x180016b42  mov     ebx, eax
0x180016b44  test    eax, eax
0x180016b46  js      short loc_180016BA5
0x180016b48  mov     rcx, [rbp+hKey]; hKey
0x180016b4c  lea     rdx, aUserinfo; "UserInfo"
0x180016b53  call    cs:__imp_RegDeleteTreeW
0x180016b5a  nop     dword ptr [rax+rax+00h]
0x180016b5f  test    eax, eax
0x180016b61  jnz     short loc_180016B96
0x180016b63  mov     rcx, [rbp+hKey]; hKey
0x180016b67  lea     r9d, [rax+4]; dwType
0x180016b6b  mov     [rbp+Data], eax
0x180016b6e  lea     rdx, aCountofuserinf; "CountOfUserInfo"
0x180016b75  lea     rax, [rbp+Data]
0x180016b79  mov     [rsp+40h+cbData], r9d; cbData
0x180016b7e  xor     r8d, r8d; Reserved
0x180016b81  mov     [rsp+40h+lpData], rax; lpData
0x180016b86  call    cs:__imp_RegSetValueExW
0x180016b8d  nop     dword ptr [rax+rax+00h]
0x180016b92  test    eax, eax
0x180016b94  jz      short loc_180016BA5
0x180016b96  jg      short loc_180016B9C
0x180016b98  mov     ebx, eax
0x180016b9a  jmp     short loc_180016BA5
0x180016b9c  movzx   ebx, ax
0x180016b9f  or      ebx, 80070000h
0x180016ba5  mov     rcx, [rbp+hMem]; hMem
0x180016ba9  call    cs:__imp_LocalFree
0x180016bb0  nop     dword ptr [rax+rax+00h]
0x180016bb5  mov     rcx, [rbp+hObject]; hObject
0x180016bb9  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x180016bbe  mov     rcx, [rbp+hKey]; hKey
0x180016bc2  test    rcx, rcx
0x180016bc5  jz      short loc_180016BD3
0x180016bc7  call    cs:__imp_RegCloseKey
0x180016bce  nop     dword ptr [rax+rax+00h]
0x180016bd3  mov     rdi, [rsp+40h+arg_8]
0x180016bd8  mov     eax, ebx
0x180016bda  mov     rbx, [rsp+40h+arg_0]
0x180016bdf  add     rsp, 40h
0x180016be3  pop     rbp
0x180016be4  retn
```
