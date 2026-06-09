# pSetupConcatenatePaths

- ea: `0x180006e28`
- end: `0x180006f15`
- name: `pSetupConcatenatePaths`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004658`
- `0x1800076d4`
- `0x1800077d0`
- `0x1800079f0`

## callees

- `0x1800034e8`
- `0x180006e28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ef8`

## pseudocode

```c
_BOOL8 __fastcall pSetupConcatenatePaths(__int64 a1, const wchar_t *a2, unsigned int a3)
{
  __int64 v3; // r10
  unsigned int v4; // r11d
  __int64 v5; // r9
  int v7; // ecx
  __int64 v8; // rax
  DWORD v9; // ebx
  HRESULT v10; // eax

  v3 = -1;
  v4 = a3;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  do
    ++v3;
  while ( a2[v3] );
  if ( (_DWORD)v5
    && (*(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 92 || *(_WORD *)(a1 + 2LL * (unsigned int)v5 - 2) == 47) )
  {
    LODWORD(v5) = v5 - 1;
  }
  if ( *a2 == 92 || *a2 == 47 )
  {
    v7 = 1;
    LODWORD(v3) = v3 - 1;
  }
  else
  {
    v7 = 0;
  }
  if ( (int)v5 + (int)v3 + 2 > a3 )
  {
    v9 = 206;
LABEL_25:
    SetLastError(v9);
    return v9 == 0;
  }
  if ( !v7 )
  {
    if ( (unsigned int)v5 >= a3 )
    {
LABEL_17:
      v9 = 206;
      goto LABEL_20;
    }
    v8 = (unsigned int)v5;
    LODWORD(v5) = v5 + 1;
    *(_WORD *)(a1 + 2 * v8) = 92;
  }
  if ( (unsigned int)v5 >= a3 )
    goto LABEL_17;
  v9 = 0;
  v10 = StringCchCopyW((STRSAFE_LPWSTR)(a1 + 2LL * (unsigned int)v5), a3 - (unsigned int)v5, a2);
  if ( v10 < 0 )
    v9 = (unsigned __int16)v10;
LABEL_20:
  if ( v4 )
    *(_WORD *)(a1 + 2LL * (v4 - 1)) = 0;
  if ( v9 )
    goto LABEL_25;
  return v9 == 0;
}

```

## disassembly

```asm
0x180006e28  mov     [rsp+arg_0], rbx
0x180006e2d  mov     [rsp+arg_8], rsi
0x180006e32  push    rdi
0x180006e33  sub     rsp, 20h
0x180006e37  or      r10, 0FFFFFFFFFFFFFFFFh
0x180006e3b  mov     r11d, r8d
0x180006e3e  mov     r9, r10
0x180006e41  xor     esi, esi
0x180006e43  mov     r8, rdx; pszSrc
0x180006e46  mov     rdi, rcx
0x180006e49  inc     r9
0x180006e4c  cmp     [rcx+r9*2], si
0x180006e51  jnz     short loc_180006E49
0x180006e53  inc     r10
0x180006e56  cmp     [rdx+r10*2], si
0x180006e5b  jnz     short loc_180006E53
0x180006e5d  or      ebx, 0FFFFFFFFh
0x180006e60  mov     edx, 5Ch ; '\'
0x180006e65  test    r9d, r9d
0x180006e68  jz      short loc_180006E7F
0x180006e6a  mov     eax, r9d
0x180006e6d  cmp     [rcx+rax*2-2], dx
0x180006e72  jz      short loc_180006E7C
0x180006e74  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x180006e7a  jnz     short loc_180006E7F
0x180006e7c  add     r9d, ebx
0x180006e7f  cmp     [r8], dx
0x180006e83  jz      short loc_180006E90
0x180006e85  cmp     word ptr [r8], 2Fh ; '/'
0x180006e8a  jz      short loc_180006E90
0x180006e8c  mov     ecx, esi
0x180006e8e  jmp     short loc_180006E98
0x180006e90  mov     ecx, 1
0x180006e95  add     r10d, ebx
0x180006e98  lea     eax, [r10+2]
0x180006e9c  add     eax, r9d
0x180006e9f  cmp     eax, r11d
0x180006ea2  ja      short loc_180006EF1
0x180006ea4  test    ecx, ecx
0x180006ea6  jnz     short loc_180006EB7
0x180006ea8  cmp     r9d, r11d
0x180006eab  jnb     short loc_180006EBC
0x180006ead  mov     eax, r9d
0x180006eb0  inc     r9d
0x180006eb3  mov     [rdi+rax*2], dx
0x180006eb7  cmp     r9d, r11d
0x180006eba  jb      short loc_180006EC3
0x180006ebc  mov     ebx, 0CEh
0x180006ec1  jmp     short loc_180006EDE
0x180006ec3  mov     eax, r9d
0x180006ec6  mov     edx, r11d
0x180006ec9  sub     edx, r9d; cchDest
0x180006ecc  mov     ebx, esi
0x180006ece  lea     rcx, [rdi+rax*2]; pszDest
0x180006ed2  call    StringCchCopyW
0x180006ed7  test    eax, eax
0x180006ed9  jns     short loc_180006EDE
0x180006edb  movzx   ebx, ax
0x180006ede  test    r11d, r11d
0x180006ee1  jz      short loc_180006EEB
0x180006ee3  lea     eax, [r11-1]
0x180006ee7  mov     [rdi+rax*2], si
0x180006eeb  test    ebx, ebx
0x180006eed  jz      short loc_180006EFE
0x180006eef  jmp     short loc_180006EF6
0x180006ef1  mov     ebx, 0CEh
0x180006ef6  mov     ecx, ebx; dwErrCode
0x180006ef8  call    cs:__imp_SetLastError
0x180006efe  test    ebx, ebx
0x180006f00  mov     eax, esi
0x180006f02  mov     rbx, [rsp+28h+arg_0]
0x180006f07  mov     rsi, [rsp+28h+arg_8]
0x180006f0c  setz    al
0x180006f0f  add     rsp, 20h
0x180006f13  pop     rdi
0x180006f14  retn
```
