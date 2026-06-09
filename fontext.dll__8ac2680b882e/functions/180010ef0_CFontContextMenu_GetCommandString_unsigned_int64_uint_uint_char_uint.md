# CFontContextMenu::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x180010ef0`
- end: `0x180010f6f`
- name: `?GetCommandString@CFontContextMenu@@UEAAJ_KIPEAIPEADI@Z`
- size: `127`
- prototype: `__int64 __fastcall(CFontContextMenu *__hidden this, unsigned __int64, unsigned int, unsigned int *, LPWSTR lpBuffer, unsigned int cchBufferMax)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006624`
- `0x180010ef0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010f4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010f4a`

## string_xrefs

- `0x180010f26`: `install`
- `0x180010f0a`: `installLink`
- `0x180010f18`: `installAllUsers`

## pseudocode

```c
__int64 __fastcall CFontContextMenu::GetCommandString(
        CFontContextMenu *this,
        __int64 a2,
        int a3,
        unsigned int *a4,
        LPWSTR lpBuffer,
        unsigned int cchBufferMax)
{
  __int64 v6; // rdx
  UINT v7; // edx
  const unsigned __int16 *v8; // rax
  int v9; // r8d

  if ( a2 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 2147549183LL;
      v7 = 1300;
      v8 = L"installLink";
    }
    else
    {
      v7 = 344;
      v8 = L"installAllUsers";
    }
  }
  else
  {
    v7 = 341;
    v8 = L"install";
  }
  v9 = a3 - 4;
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      LoadStringW(g_hInstance, v7, lpBuffer, cchBufferMax);
      return 0;
    }
  }
  else
  {
    StringCchCopyW(lpBuffer, cchBufferMax, v8);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180010ef0  sub     rsp, 28h
0x180010ef4  test    rdx, rdx
0x180010ef7  jz      short loc_180010F21
0x180010ef9  sub     rdx, 1
0x180010efd  jz      short loc_180010F13
0x180010eff  cmp     rdx, 1
0x180010f03  jnz     short loc_180010F65
0x180010f05  mov     edx, 514h
0x180010f0a  lea     rax, c_szShellVerb_InstallLink; "installLink"
0x180010f11  jmp     short loc_180010F2D
0x180010f13  mov     edx, 158h
0x180010f18  lea     rax, c_szShellVerb_InstallAllUsers; "installAllUsers"
0x180010f1f  jmp     short loc_180010F2D
0x180010f21  mov     edx, 155h; uID
0x180010f26  lea     rax, aInstall; "install"
0x180010f2d  sub     r8d, 4
0x180010f31  jz      short loc_180010F54
0x180010f33  cmp     r8d, 1
0x180010f37  jnz     short loc_180010F65
0x180010f39  mov     r9d, [rsp+28h+cchBufferMax]; cchBufferMax
0x180010f3e  mov     r8, [rsp+28h+lpBuffer]; lpBuffer
0x180010f43  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180010f4a  call    cs:__imp_LoadStringW
0x180010f50  xor     eax, eax
0x180010f52  jmp     short loc_180010F6A
0x180010f54  mov     edx, [rsp+28h+cchBufferMax]; unsigned __int64
0x180010f58  mov     r8, rax; unsigned __int16 *
0x180010f5b  mov     rcx, [rsp+28h+lpBuffer]; unsigned __int16 *
0x180010f60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010f65  mov     eax, 8000FFFFh
0x180010f6a  add     rsp, 28h
0x180010f6e  retn
```
