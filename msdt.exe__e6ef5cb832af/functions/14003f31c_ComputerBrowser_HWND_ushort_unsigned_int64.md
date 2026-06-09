# ComputerBrowser(HWND__ *,ushort *,unsigned __int64)

- ea: `0x14003f31c`
- end: `0x14003f45e`
- name: `?ComputerBrowser@@YAJPEAUHWND__@@PEAG_K@Z`
- size: `322`
- prototype: `__int64 __fastcall(HWND, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002e470`

## callees

- `0x1400039b1`
- `0x140020420`
- `0x14003f31c`
- `0x140041c54`
- `0x140061c90`

## import_xrefs

- `SHELL32!SHBrowseForFolderW` at `0x14003f3fe`
- `SHELL32!SHBrowseForFolderW` at `0x14003f3fe`
- `SHELL32!SHGetKnownFolderIDList` at `0x14003f3ba`
- `SHELL32!SHGetKnownFolderIDList` at `0x14003f3ba`
- `ole32!CoTaskMemFree` at `0x14003f417`
- `ole32!CoTaskMemFree` at `0x14003f42d`
- `ole32!CoTaskMemFree` at `0x14003f417`
- `ole32!CoTaskMemFree` at `0x14003f42d`

## string_xrefs

- `0x14003f38b`: `ComputerBrowser`

## pseudocode

```c
__int64 __fastcall ComputerBrowser(HWND a1, unsigned __int16 *a2)
{
  HRESULT LocalString; // eax
  unsigned int v5; // ebx
  int v6; // r9d
  LPITEMIDLIST v7; // rax
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  _browseinfoW bi; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  ppidl = 0;
  memset_0(&bi, 0, sizeof(bi));
  *a2 = 0;
  Buffer[0] = 0;
  LocalString = DwzLoadLocalString(0xFBu, Buffer, 0x100u);
  v5 = LocalString;
  if ( LocalString < 0 )
  {
    v6 = 69;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ComputerBrowser", v6, LocalString);
    goto LABEL_9;
  }
  LocalString = SHGetKnownFolderIDList(&FOLDERID_NetworkFolder, 0, 0, &ppidl);
  v5 = LocalString;
  if ( LocalString < 0 )
  {
    v6 = 79;
    goto LABEL_3;
  }
  bi.hwndOwner = a1;
  bi.lpszTitle = Buffer;
  bi.pidlRoot = ppidl;
  bi.ulFlags = 4096;
  bi.pszDisplayName = a2;
  v7 = SHBrowseForFolderW(&bi);
  if ( v7 )
    CoTaskMemFree(v7);
  else
    v5 = 1;
LABEL_9:
  if ( ppidl )
    CoTaskMemFree(ppidl);
  return v5;
}

```

## disassembly

```asm
0x14003f31c  mov     [rsp-8+arg_10], rbx
0x14003f321  push    rbp
0x14003f322  push    rsi
0x14003f323  push    rdi
0x14003f324  lea     rbp, [rsp-190h]
0x14003f32c  sub     rsp, 290h
0x14003f333  mov     rax, cs:__security_cookie
0x14003f33a  xor     rax, rsp
0x14003f33d  mov     [rbp+1A0h+var_20], rax
0x14003f344  mov     rdi, rdx
0x14003f347  mov     [rsp+2A0h+ppidl], 0
0x14003f350  xor     edx, edx; Val
0x14003f352  mov     rsi, rcx
0x14003f355  lea     rcx, [rsp+2A0h+bi]; void *
0x14003f35a  lea     r8d, [rdx+40h]; Size
0x14003f35e  call    memset_0
0x14003f363  xor     eax, eax
0x14003f365  lea     rdx, [rbp+1A0h+Buffer]; lpBuffer
0x14003f369  mov     r8d, 100h; cchBufferMax
0x14003f36f  mov     [rdi], ax
0x14003f372  mov     [rbp+1A0h+Buffer], ax
0x14003f376  lea     ecx, [r8-5]; uID
0x14003f37a  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x14003f37f  mov     ebx, eax
0x14003f381  test    eax, eax
0x14003f383  jns     short loc_14003F3A9
0x14003f385  mov     r9d, 45h ; 'E'
0x14003f38b  lea     r8, aComputerbrowse; "ComputerBrowser"
0x14003f392  mov     [rsp+2A0h+var_280], eax
0x14003f396  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003f39d  mov     ecx, 1; Level
0x14003f3a2  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003f3a7  jmp     short loc_14003F423
0x14003f3a9  lea     r9, [rsp+2A0h+ppidl]; ppidl
0x14003f3ae  xor     r8d, r8d; hToken
0x14003f3b1  xor     edx, edx; dwFlags
0x14003f3b3  lea     rcx, FOLDERID_NetworkFolder; rfid
0x14003f3ba  call    cs:__imp_SHGetKnownFolderIDList
0x14003f3c1  nop     dword ptr [rax+rax+00h]
0x14003f3c6  mov     ebx, eax
0x14003f3c8  test    eax, eax
0x14003f3ca  jns     short loc_14003F3D4
0x14003f3cc  mov     r9d, 4Fh ; 'O'
0x14003f3d2  jmp     short loc_14003F38B
0x14003f3d4  lea     rax, [rbp+1A0h+Buffer]
0x14003f3d8  mov     [rsp+2A0h+bi.hwndOwner], rsi
0x14003f3dd  mov     [rsp+2A0h+bi.lpszTitle], rax
0x14003f3e2  lea     rcx, [rsp+2A0h+bi]; lpbi
0x14003f3e7  mov     rax, [rsp+2A0h+ppidl]
0x14003f3ec  mov     [rsp+2A0h+bi.pidlRoot], rax
0x14003f3f1  mov     [rsp+2A0h+bi.ulFlags], 1000h
0x14003f3f9  mov     [rsp+2A0h+bi.pszDisplayName], rdi
0x14003f3fe  call    cs:__imp_SHBrowseForFolderW
0x14003f405  nop     dword ptr [rax+rax+00h]
0x14003f40a  test    rax, rax
0x14003f40d  jnz     short loc_14003F414
0x14003f40f  lea     ebx, [rax+1]
0x14003f412  jmp     short loc_14003F423
0x14003f414  mov     rcx, rax; pv
0x14003f417  call    cs:__imp_CoTaskMemFree
0x14003f41e  nop     dword ptr [rax+rax+00h]
0x14003f423  mov     rcx, [rsp+2A0h+ppidl]; pv
0x14003f428  test    rcx, rcx
0x14003f42b  jz      short loc_14003F439
0x14003f42d  call    cs:__imp_CoTaskMemFree
0x14003f434  nop     dword ptr [rax+rax+00h]
0x14003f439  mov     eax, ebx
0x14003f43b  mov     rcx, [rbp+1A0h+var_20]
0x14003f442  xor     rcx, rsp; StackCookie
0x14003f445  call    __security_check_cookie
0x14003f44a  mov     rbx, [rsp+2A0h+arg_10]
0x14003f452  add     rsp, 290h
0x14003f459  pop     rdi
0x14003f45a  pop     rsi
0x14003f45b  pop     rbp
0x14003f45c  retn
```
