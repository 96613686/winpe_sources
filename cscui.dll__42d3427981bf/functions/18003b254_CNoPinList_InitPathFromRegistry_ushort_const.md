# CNoPinList::_InitPathFromRegistry(ushort const *)

- ea: `0x18003b254`
- end: `0x18003b377`
- name: `?_InitPathFromRegistry@CNoPinList@@AEAAJPEBG@Z`
- size: `291`
- prototype: `__int64 __fastcall(CNoPinList *__hidden this, LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003b380`

## callees

- `0x180011654`
- `0x18003b00c`
- `0x18003b254`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18003b2e1`
- `SHLWAPI!PathIsUNCW` at `0x18003b2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b331`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b296`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b296`

## pseudocode

```c
__int64 __fastcall CNoPinList::_InitPathFromRegistry(LPCWSTR ***this, LPCWSTR lpSrc)
{
  WCHAR v3; // ax
  HLOCAL v4; // rsi
  WCHAR *v5; // rcx
  const unsigned __int16 *v6; // rdx
  int RemotePath; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) - 1 <= 0x103 )
  {
    v3 = Dst[0];
    hMem = 0;
    v4 = 0;
    if ( Dst[0] )
    {
      v5 = Dst;
      do
      {
        if ( v3 == 47 )
          *v5 = 92;
        v3 = *++v5;
      }
      while ( *v5 );
    }
    if ( PathIsUNCW(Dst) )
    {
      v6 = Dst;
    }
    else
    {
      RemotePath = GetRemotePath(Dst, (unsigned __int16 **)&hMem);
      v4 = hMem;
      v8 = RemotePath;
      if ( RemotePath < 0 )
        goto LABEL_15;
      if ( RemotePath )
      {
        v6 = Dst;
        if ( RemotePath != 1 )
          v6 = 0;
      }
      else
      {
        v6 = (const unsigned __int16 *)hMem;
      }
    }
    v8 = CNoPinList::_AddPath(this, v6);
LABEL_15:
    if ( v4 )
      LocalFree(v4);
    return v8;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v8;
}

```

## disassembly

```asm
0x18003b254  mov     [rsp-8+arg_10], rbx
0x18003b259  mov     [rsp-8+arg_18], rsi
0x18003b25e  push    rbp
0x18003b25f  push    rdi
0x18003b260  push    r14
0x18003b262  lea     rbp, [rsp-150h]
0x18003b26a  sub     rsp, 250h
0x18003b271  mov     rax, cs:__security_cookie
0x18003b278  xor     rax, rsp
0x18003b27b  mov     [rbp+160h+var_20], rax
0x18003b282  mov     rax, rdx
0x18003b285  mov     r14, rcx
0x18003b288  mov     rcx, rax; lpSrc
0x18003b28b  lea     rdx, [rsp+260h+Dst]; lpDst
0x18003b290  mov     r8d, 104h; nSize
0x18003b296  call    cs:__imp_ExpandEnvironmentStringsW
0x18003b29c  dec     eax
0x18003b29e  cmp     eax, 103h
0x18003b2a3  ja      loc_18003B339
0x18003b2a9  movzx   eax, [rsp+260h+Dst]
0x18003b2ae  xor     edi, edi
0x18003b2b0  mov     [rsp+260h+hMem], rdi
0x18003b2b5  mov     esi, edi
0x18003b2b7  test    ax, ax
0x18003b2ba  jz      short loc_18003B2DC
0x18003b2bc  lea     rcx, [rsp+260h+Dst]
0x18003b2c1  mov     edx, 2Fh ; '/'
0x18003b2c6  cmp     dx, ax
0x18003b2c9  jnz     short loc_18003B2D0
0x18003b2cb  mov     word ptr [rcx], 5Ch ; '\'
0x18003b2d0  add     rcx, 2
0x18003b2d4  movzx   eax, word ptr [rcx]
0x18003b2d7  test    ax, ax
0x18003b2da  jnz     short loc_18003B2C1
0x18003b2dc  lea     rcx, [rsp+260h+Dst]; pszPath
0x18003b2e1  call    cs:__imp_PathIsUNCW
0x18003b2e7  test    eax, eax
0x18003b2e9  jz      short loc_18003B2F2
0x18003b2eb  lea     rdx, [rsp+260h+Dst]
0x18003b2f0  jmp     short loc_18003B31F
0x18003b2f2  lea     rdx, [rsp+260h+hMem]; unsigned __int16 **
0x18003b2f7  lea     rcx, [rsp+260h+Dst]; unsigned __int16 *
0x18003b2fc  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x18003b301  mov     rsi, [rsp+260h+hMem]
0x18003b306  mov     ebx, eax
0x18003b308  test    eax, eax
0x18003b30a  js      short loc_18003B329
0x18003b30c  jnz     short loc_18003B313
0x18003b30e  mov     rdx, rsi
0x18003b311  jmp     short loc_18003B31F
0x18003b313  cmp     eax, 1
0x18003b316  lea     rdx, [rsp+260h+Dst]
0x18003b31b  cmovnz  rdx, rdi; unsigned __int16 *
0x18003b31f  mov     rcx, r14; this
0x18003b322  call    ?_AddPath@CNoPinList@@AEAAJPEBG@Z; CNoPinList::_AddPath(ushort const *)
0x18003b327  mov     ebx, eax
0x18003b329  test    rsi, rsi
0x18003b32c  jz      short loc_18003B34E
0x18003b32e  mov     rcx, rsi; hMem
0x18003b331  call    cs:__imp_LocalFree
0x18003b337  jmp     short loc_18003B34E
0x18003b339  call    cs:__imp_GetLastError
0x18003b33f  mov     ebx, eax
0x18003b341  test    eax, eax
0x18003b343  jle     short loc_18003B34E
0x18003b345  movzx   ebx, ax
0x18003b348  or      ebx, 80070000h
0x18003b34e  mov     eax, ebx
0x18003b350  mov     rcx, [rbp+160h+var_20]
0x18003b357  xor     rcx, rsp; StackCookie
0x18003b35a  call    __security_check_cookie
0x18003b35f  lea     r11, [rsp+260h+var_10]
0x18003b367  mov     rbx, [r11+30h]
0x18003b36b  mov     rsi, [r11+38h]
0x18003b36f  mov     rsp, r11
0x18003b372  pop     r14
0x18003b374  pop     rdi
0x18003b375  pop     rbp
0x18003b376  retn
```
