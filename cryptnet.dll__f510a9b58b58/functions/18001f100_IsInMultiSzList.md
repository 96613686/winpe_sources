# _IsInMultiSzList

- ea: `0x18001f100`
- end: `0x18001f173`
- name: `_IsInMultiSzList`
- size: `115`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x18001e834`
- `0x18001f17c`

## callees

- `0x18001f100`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f149`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001f149`

## pseudocode

```c
__int64 __fastcall IsInMultiSzList(PCNZWCH lpString1, PCNZWCH lpString2)
{
  const WCHAR *v3; // rbx
  __int64 v4; // rdi

  v3 = lpString1;
  if ( lpString1 )
  {
    while ( v3 )
    {
      v4 = -1;
      do
        ++v4;
      while ( v3[v4] );
      if ( !(_DWORD)v4 )
        break;
      if ( CompareStringW(0x409u, 1u, v3, -1, lpString2, -1) == 2 )
        return 1;
      v3 += (int)v4 + 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001f100  push    rbx
0x18001f102  push    rbp
0x18001f103  push    rsi
0x18001f104  push    rdi
0x18001f105  sub     rsp, 38h
0x18001f109  xor     ebp, ebp
0x18001f10b  mov     rsi, rdx
0x18001f10e  mov     rbx, rcx
0x18001f111  test    rcx, rcx
0x18001f114  jz      short loc_18001F168
0x18001f116  test    rbx, rbx
0x18001f119  jz      short loc_18001F168
0x18001f11b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f11f  inc     rdi
0x18001f122  cmp     [rbx+rdi*2], bp
0x18001f126  jnz     short loc_18001F11F
0x18001f128  test    edi, edi
0x18001f12a  jz      short loc_18001F168
0x18001f12c  or      r9d, 0FFFFFFFFh; cchCount1
0x18001f130  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001f138  mov     r8, rbx; lpString1
0x18001f13b  mov     [rsp+58h+lpString2], rsi; lpString2
0x18001f140  mov     ecx, 409h; Locale
0x18001f145  lea     edx, [r9+2]; dwCmpFlags
0x18001f149  call    cs:__imp_CompareStringW
0x18001f14f  cmp     eax, 2
0x18001f152  jz      short loc_18001F161
0x18001f154  movsxd  rax, edi
0x18001f157  lea     rbx, [rbx+rax*2]
0x18001f15b  add     rbx, 2
0x18001f15f  jmp     short loc_18001F116
0x18001f161  mov     eax, 1
0x18001f166  jmp     short loc_18001F16A
0x18001f168  xor     eax, eax
0x18001f16a  add     rsp, 38h
0x18001f16e  pop     rdi
0x18001f16f  pop     rsi
0x18001f170  pop     rbp
0x18001f171  pop     rbx
0x18001f172  retn
```
