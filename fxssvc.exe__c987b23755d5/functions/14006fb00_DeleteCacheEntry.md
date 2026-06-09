# DeleteCacheEntry

- ea: `0x14006fb00`
- end: `0x14006fc91`
- name: `DeleteCacheEntry`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004e1cc`
- `0x14007e844`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x14006fb00`
- `0x140070020`
- `0x1400708c4`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006fc6c`
- `ADVAPI32!RegCloseKey` at `0x14006fc6c`
- `KERNEL32!GetLastError` at `0x14006fb78`
- `KERNEL32!GetLastError` at `0x14006fc31`
- `KERNEL32!GetLastError` at `0x14006fb78`
- `KERNEL32!GetLastError` at `0x14006fc31`

## string_xrefs

- `0x14006fb5a`: `Software\Microsoft\Fax\Devices Cache`

## pseudocode

```c
__int64 __fastcall DeleteCacheEntry(unsigned int a1)
{
  HKEY v2; // rdi
  DWORD v3; // ebx
  int v4; // eax
  DWORD LastError; // eax
  unsigned __int16 v7[12]; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
  }
  v2 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Devices Cache", 0, 0x2001Fu);
  if ( v2 )
  {
    v4 = StringCchPrintfW(v7, 0xAu, L"%08lx", a1);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v3 = 0;
      if ( !(unsigned int)DeleteRegistryKey(v2, v7) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids, LastError);
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids,
          (unsigned int)v4);
      }
      if ( (v3 & 0x1FFF0000) == 0x70000 )
        v3 = (unsigned __int16)v3;
    }
    RegCloseKey(v2);
  }
  else
  {
    v3 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14006fb00  mov     [rsp+arg_8], rbx
0x14006fb05  mov     [rsp+arg_10], rbp
0x14006fb0a  push    rdi
0x14006fb0b  sub     rsp, 40h
0x14006fb0f  mov     rax, cs:__security_cookie
0x14006fb16  xor     rax, rsp
0x14006fb19  mov     [rsp+48h+var_10], rax
0x14006fb1e  mov     ebx, ecx
0x14006fb20  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fb27  lea     rbp, WPP_GLOBAL_Control
0x14006fb2e  cmp     rcx, rbp
0x14006fb31  jz      short loc_14006FB54
0x14006fb33  test    byte ptr [rcx+1Ch], 2
0x14006fb37  jz      short loc_14006FB54
0x14006fb39  cmp     byte ptr [rcx+19h], 5
0x14006fb3d  jb      short loc_14006FB54
0x14006fb3f  mov     rcx, [rcx+10h]
0x14006fb43  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14006fb4a  mov     edx, 1Bh
0x14006fb4f  call    WPP_SF_
0x14006fb54  mov     r9d, 2001Fh
0x14006fb5a  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Fax\\Devices Cache"
0x14006fb61  xor     r8d, r8d
0x14006fb64  mov     rcx, 0FFFFFFFF80000002h
0x14006fb6b  call    OpenRegistryKey
0x14006fb70  mov     rdi, rax
0x14006fb73  test    rax, rax
0x14006fb76  jnz     short loc_14006FBBC
0x14006fb78  call    cs:__imp_GetLastError
0x14006fb7e  mov     ebx, eax
0x14006fb80  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fb87  cmp     rcx, rbp
0x14006fb8a  jz      loc_14006FC72
0x14006fb90  test    byte ptr [rcx+1Ch], 2
0x14006fb94  jz      loc_14006FC72
0x14006fb9a  cmp     byte ptr [rcx+19h], 2
0x14006fb9e  jb      loc_14006FC72
0x14006fba4  mov     rcx, [rcx+10h]
0x14006fba8  lea     edx, [rdi+1Ch]
0x14006fbab  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14006fbb2  call    WPP_SF_
0x14006fbb7  jmp     loc_14006FC72
0x14006fbbc  mov     r9d, ebx
0x14006fbbf  lea     r8, a08lx; "%08lx"
0x14006fbc6  mov     edx, 0Ah; unsigned __int64
0x14006fbcb  lea     rcx, [rsp+48h+var_28]; unsigned __int16 *
0x14006fbd0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006fbd5  mov     ebx, eax
0x14006fbd7  test    eax, eax
0x14006fbd9  jns     short loc_14006FC1E
0x14006fbdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fbe2  cmp     rcx, rbp
0x14006fbe5  jz      short loc_14006FC0B
0x14006fbe7  test    byte ptr [rcx+1Ch], 2
0x14006fbeb  jz      short loc_14006FC0B
0x14006fbed  cmp     byte ptr [rcx+19h], 2
0x14006fbf1  jb      short loc_14006FC0B
0x14006fbf3  mov     rcx, [rcx+10h]
0x14006fbf7  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14006fbfe  mov     edx, 1Dh
0x14006fc03  mov     r9d, eax
0x14006fc06  call    WPP_SF_d
0x14006fc0b  mov     eax, ebx
0x14006fc0d  and     eax, 1FFF0000h
0x14006fc12  cmp     eax, 70000h
0x14006fc17  jnz     short loc_14006FC69
0x14006fc19  movzx   ebx, bx
0x14006fc1c  jmp     short loc_14006FC69
0x14006fc1e  lea     rdx, [rsp+48h+var_28]
0x14006fc23  mov     rcx, rdi
0x14006fc26  xor     ebx, ebx
0x14006fc28  call    DeleteRegistryKey
0x14006fc2d  test    eax, eax
0x14006fc2f  jnz     short loc_14006FC69
0x14006fc31  call    cs:__imp_GetLastError
0x14006fc37  mov     ebx, eax
0x14006fc39  mov     rcx, cs:WPP_GLOBAL_Control
0x14006fc40  cmp     rcx, rbp
0x14006fc43  jz      short loc_14006FC69
0x14006fc45  test    byte ptr [rcx+1Ch], 2
0x14006fc49  jz      short loc_14006FC69
0x14006fc4b  cmp     byte ptr [rcx+19h], 2
0x14006fc4f  jb      short loc_14006FC69
0x14006fc51  mov     rcx, [rcx+10h]
0x14006fc55  lea     r8, WPP_ebb6bf7812d636f87cf144a865c22f79_Traceguids
0x14006fc5c  mov     edx, 1Eh
0x14006fc61  mov     r9d, eax
0x14006fc64  call    WPP_SF_d
0x14006fc69  mov     rcx, rdi; hKey
0x14006fc6c  call    cs:__imp_RegCloseKey
0x14006fc72  mov     eax, ebx
0x14006fc74  mov     rcx, [rsp+48h+var_10]
0x14006fc79  xor     rcx, rsp; StackCookie
0x14006fc7c  call    __security_check_cookie
0x14006fc81  mov     rbx, [rsp+48h+arg_8]
0x14006fc86  mov     rbp, [rsp+48h+arg_10]
0x14006fc8b  add     rsp, 40h
0x14006fc8f  pop     rdi
0x14006fc90  retn
```
