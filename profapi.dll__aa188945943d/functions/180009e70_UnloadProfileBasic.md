# UnloadProfileBasic

- ea: `0x180009e70`
- end: `0x180009f7d`
- name: `UnloadProfileBasic`
- size: `269`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HKEY hKey)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005b60`
- `0x1800064b0`
- `0x180009e70`
- `0x18000a1c0`
- `0x18000a214`
- `0x18001064c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009e9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f40`
- `ext-ms-win-profile-extender-l1-1-0!UnloadProfileExtender` at `0x180009f60`
- `ext-ms-win-profile-extender-l1-1-0!UnloadProfileExtender` at `0x180009f60`

## pseudocode

```c
__int64 __fastcall UnloadProfileBasic(HANDLE TokenHandle, HKEY hKey)
{
  int SidString; // eax
  unsigned int v5; // ebx
  HLOCAL v6; // rbx
  int v7; // edi
  HLOCAL hMem[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !TokenHandle )
    return 2147942487LL;
  if ( hKey )
    RegCloseKey(hKey);
  hMem[0] = 0;
  hMem[1] = (HLOCAL)-1LL;
  hMem[2] = (HLOCAL)-1LL;
  SidString = GetSidString(TokenHandle, (unsigned __int16 **)hMem);
  v5 = SidString;
  if ( SidString >= 0 )
  {
    v6 = hMem[0];
    if ( StringIsEqual((const unsigned __int16 *)hMem[0], L"S-1-5-18")
      || StringIsEqual((const unsigned __int16 *)v6, L"S-1-5-19")
      || StringIsEqual((const unsigned __int16 *)v6, L"S-1-5-20") )
    {
LABEL_9:
      if ( v6 )
        LocalFree(v6);
      return 0;
    }
    if ( (unsigned __int8)IsUnloadProfileExtenderPresent() )
    {
      v7 = UnloadProfileExtender(TokenHandle);
      if ( v7 >= 0 )
        goto LABEL_9;
    }
    else
    {
      v7 = -2147467263;
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(hMem);
    return (unsigned int)v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x245,
    (unsigned int)"minio\\profapi\\load.cpp",
    (const char *)(unsigned int)SidString,
    (int)hMem[0]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return v5;
}

```

## disassembly

```asm
0x180009e70  mov     [rsp+arg_0], rbx
0x180009e75  push    rdi
0x180009e76  sub     rsp, 40h
0x180009e7a  mov     rdi, rcx
0x180009e7d  test    rcx, rcx
0x180009e80  jnz     short loc_180009E92
0x180009e82  mov     eax, 80070057h
0x180009e87  mov     rbx, [rsp+48h+arg_0]
0x180009e8c  add     rsp, 40h
0x180009e90  pop     rdi
0x180009e91  retn
0x180009e92  test    rdx, rdx
0x180009e95  jz      short loc_180009EA0
0x180009e97  mov     rcx, rdx; hKey
0x180009e9a  call    cs:__imp_RegCloseKey
0x180009ea0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009ea4  mov     [rsp+48h+hMem], 0; int
0x180009ead  lea     rdx, [rsp+48h+hMem]; unsigned __int16 **
0x180009eb2  mov     [rsp+48h+var_20], rax
0x180009eb7  mov     rcx, rdi; TokenHandle
0x180009eba  mov     [rsp+48h+var_18], rax
0x180009ebf  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x180009ec4  mov     ebx, eax
0x180009ec6  test    eax, eax
0x180009ec8  js      short loc_180009F1D
0x180009eca  mov     rbx, [rsp+48h+hMem]
0x180009ecf  lea     rdx, aS1518; "S-1-5-18"
0x180009ed6  mov     rcx, rbx; unsigned __int16 *
0x180009ed9  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180009ede  test    eax, eax
0x180009ee0  jnz     short loc_180009F08
0x180009ee2  lea     rdx, aS1519; "S-1-5-19"
0x180009ee9  mov     rcx, rbx; unsigned __int16 *
0x180009eec  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180009ef1  test    eax, eax
0x180009ef3  jnz     short loc_180009F08
0x180009ef5  lea     rdx, aS1520; "S-1-5-20"
0x180009efc  mov     rcx, rbx; unsigned __int16 *
0x180009eff  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180009f04  test    eax, eax
0x180009f06  jz      short loc_180009F4D
0x180009f08  test    rbx, rbx
0x180009f0b  jz      short loc_180009F16
0x180009f0d  mov     rcx, rbx; hMem
0x180009f10  call    cs:__imp_LocalFree
0x180009f16  xor     eax, eax
0x180009f18  jmp     loc_180009E87
0x180009f1d  mov     rcx, [rsp+48h]; this
0x180009f22  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180009f29  mov     r9d, ebx; char *
0x180009f2c  mov     edx, 245h; void *
0x180009f31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f36  mov     rcx, [rsp+48h+hMem]; hMem
0x180009f3b  test    rcx, rcx
0x180009f3e  jz      short loc_180009F46
0x180009f40  call    cs:__imp_LocalFree
0x180009f46  mov     eax, ebx
0x180009f48  jmp     loc_180009E87
0x180009f4d  call    IsUnloadProfileExtenderPresent
0x180009f52  test    al, al
0x180009f54  jnz     short loc_180009F5D
0x180009f56  mov     edi, 80004001h
0x180009f5b  jmp     short loc_180009F6C
0x180009f5d  mov     rcx, rdi
0x180009f60  call    cs:__imp_UnloadProfileExtender
0x180009f66  mov     edi, eax
0x180009f68  test    eax, eax
0x180009f6a  jns     short loc_180009F08
0x180009f6c  lea     rcx, [rsp+48h+hMem]
0x180009f71  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180009f76  mov     eax, edi
0x180009f78  jmp     loc_180009E87
```
