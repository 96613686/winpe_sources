# EEDBManager::DeleteEnrollment(_GUID)

- ea: `0x18000ddd0`
- end: `0x18000dea7`
- name: `?DeleteEnrollment@EEDBManager@@UEAAJU_GUID@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001a70`
- `0x180005aec`
- `0x18000ddd0`
- `0x18000deb0`
- `0x18000e938`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000de19`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000de19`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000de86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000de86`

## pseudocode

```c
__int64 __fastcall EEDBManager::DeleteEnrollment(EEDBManager *this, struct _GUID *a2)
{
  GUID v2; // xmm0
  int v3; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  GUID rguid; // [rsp+30h] [rbp-2D8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned __int16 v8[40]; // [rsp+90h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-228h] BYREF

  v2 = *a2;
  SubKey[0] = 0;
  rguid = v2;
  v8[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2(&rguid, sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, v8);
    if ( v3 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v8);
      if ( v3 >= 0 )
        RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ddd0  push    rbx
0x18000ddd2  sub     rsp, 300h
0x18000ddd9  mov     rax, cs:__security_cookie
0x18000dde0  xor     rax, rsp
0x18000dde3  mov     [rsp+308h+var_18], rax
0x18000ddeb  movups  xmm0, xmmword ptr [rdx]
0x18000ddee  xor     eax, eax
0x18000ddf0  lea     rdx, [rsp+308h+sz]; lpsz
0x18000ddf5  lea     rcx, [rsp+308h+rguid]; rguid
0x18000ddfa  mov     [rsp+308h+SubKey], ax
0x18000de02  movdqu  xmmword ptr [rsp+308h+rguid.Data1], xmm0
0x18000de08  mov     [rsp+308h+var_278], ax
0x18000de10  lea     r8d, [rax+27h]; cchMax
0x18000de14  mov     [rsp+308h+sz], ax
0x18000de19  call    cs:__imp_StringFromGUID2
0x18000de1f  cmp     eax, 27h ; '''
0x18000de22  jz      short loc_18000DE2B
0x18000de24  mov     ebx, 8000FFFFh
0x18000de29  jmp     short loc_18000DE8C
0x18000de2b  lea     rdx, [rsp+308h+var_278]; unsigned __int16 *
0x18000de33  lea     rcx, [rsp+308h+sz]; unsigned __int16 *
0x18000de38  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x18000de3d  mov     ebx, eax
0x18000de3f  test    eax, eax
0x18000de41  js      short loc_18000DE8C
0x18000de43  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18000de48  mov     r9, rax
0x18000de4b  lea     r8, aSS; "%s\\%s"
0x18000de52  lea     rax, [rsp+308h+var_278]
0x18000de5a  mov     edx, 104h; unsigned __int64
0x18000de5f  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x18000de67  mov     [rsp+308h+var_2E8], rax
0x18000de6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000de71  mov     ebx, eax
0x18000de73  test    eax, eax
0x18000de75  js      short loc_18000DE8C
0x18000de77  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x18000de7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000de86  call    cs:__imp_RegDeleteTreeW
0x18000de8c  mov     eax, ebx
0x18000de8e  mov     rcx, [rsp+308h+var_18]
0x18000de96  xor     rcx, rsp; StackCookie
0x18000de99  call    __security_check_cookie
0x18000de9e  add     rsp, 300h
0x18000dea5  pop     rbx
0x18000dea6  retn
```
