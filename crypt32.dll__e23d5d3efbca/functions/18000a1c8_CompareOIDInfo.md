# CompareOIDInfo

- ea: `0x18000a1c8`
- end: `0x18000a371`
- name: `CompareOIDInfo`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009da0`

## callees

- `0x18000a1c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a340`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a340`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a303`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011546d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180115496`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801154c0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801154cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000a303`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011546d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180115496`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801154c0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801154cf`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000a244`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000a244`

## pseudocode

```c
__int64 __fastcall CompareOIDInfo(int a1, __int64 a2, int a3, int a4, __int64 a5)
{
  _DWORD *v8; // r12
  unsigned int v9; // ebx
  int v11; // eax
  int v12; // ecx
  const WCHAR *v13; // rax
  bool v14; // zf
  int v15; // ecx
  int v16; // eax
  const WCHAR *lpString2; // [rsp+20h] [rbp-48h]

  v8 = (_DWORD *)(a5 + 24);
  if ( !a3 || a3 == *v8 )
  {
    if ( *v8 != 3
      || (a1 & 0xFFFF0000) == 0
      || *(_DWORD *)(a5 + 32) < 4u
      || ((v12 = **(_DWORD **)(a5 + 40), a1 >= 0) || (v12 & 0x40000000) == 0)
      && ((a1 & 0x40000000) == 0 || v12 >= 0)
      && ((a1 & 0x8000000) == 0 || (v12 & 0x4000000) == 0)
      && ((v12 & 0x8000000) == 0 || (a1 & 0x4000000) == 0) )
    {
      v9 = 0;
      switch ( (unsigned __int16)a1 )
      {
        case 1u:
          if ( !a2 || !*(_BYTE *)a2 )
            return v9;
          v11 = CompareStringA(0x409u, 1u, (PCNZCH)a2, -1, *(PCNZCH *)(a5 + 8), -1);
LABEL_8:
          if ( v11 == 2 )
          {
            v9 = 1;
LABEL_10:
            if ( a4 && *v8 == 2 && *(_DWORD *)(a5 + 32) >= 4u && a4 != **(_DWORD **)(a5 + 40) )
              return 0;
          }
          return v9;
        case 2u:
          v13 = *(const WCHAR **)(a5 + 16);
          break;
        case 3u:
          v14 = *(_DWORD *)a2 == *(_DWORD *)(a5 + 28);
LABEL_33:
          LOBYTE(v9) = v14;
          if ( v9 )
            goto LABEL_10;
          return v9;
        case 4u:
          if ( *(_DWORD *)(a5 + 32) < 4u )
            v15 = 0;
          else
            v15 = **(_DWORD **)(a5 + 40);
          if ( *(_DWORD *)a2 != *(_DWORD *)(a5 + 28) || *(_DWORD *)(a2 + 4) != v15 )
            return v9;
          v9 = 1;
          goto LABEL_10;
        case 5u:
          v13 = *(const WCHAR **)(a5 + 48);
          break;
        case 6u:
          v16 = CompareStringW(0x409u, 1u, *(PCNZWCH *)a2, -1, L"PreHash", -1);
          lpString2 = *(const WCHAR **)(a5 + 48);
          if ( v16 == 2 )
          {
            if ( CompareStringW(0x409u, 1u, L"NoHash", -1, lpString2, -1) == 2 )
              return v9;
          }
          else if ( CompareStringW(0x409u, 1u, *(PCNZWCH *)a2, -1, lpString2, -1) != 2 )
          {
            return v9;
          }
          v11 = CompareStringW(0x409u, 1u, *(PCNZWCH *)(a2 + 8), -1, *(PCNZWCH *)(a5 + 56), -1);
          goto LABEL_8;
        default:
          SetLastError(0x80070057);
          return v9;
      }
      v14 = CompareStringW(0x409u, 1u, (PCNZWCH)a2, -1, v13, -1) == 2;
      goto LABEL_33;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a1c8  push    rbx
0x18000a1ca  push    rbp
0x18000a1cb  push    rsi
0x18000a1cc  push    rdi
0x18000a1cd  push    r12
0x18000a1cf  push    r13
0x18000a1d1  push    r14
0x18000a1d3  sub     rsp, 30h
0x18000a1d7  mov     rsi, [rsp+68h+arg_20]
0x18000a1df  mov     r14, rdx
0x18000a1e2  mov     r13d, r9d
0x18000a1e5  mov     edx, ecx
0x18000a1e7  lea     r12, [rsi+18h]
0x18000a1eb  test    r8d, r8d
0x18000a1ee  jnz     loc_18000A29A
0x18000a1f4  cmp     dword ptr [r12], 3
0x18000a1f9  jz      short loc_18000A271
0x18000a1fb  xor     ebx, ebx
0x18000a1fd  movzx   eax, dx
0x18000a200  sub     eax, 1
0x18000a203  jnz     loc_18000A2C9
0x18000a209  test    r14, r14
0x18000a20c  jnz     short loc_18000A21F
0x18000a20e  mov     eax, ebx
0x18000a210  add     rsp, 30h
0x18000a214  pop     r14
0x18000a216  pop     r13
0x18000a218  pop     r12
0x18000a21a  pop     rdi
0x18000a21b  pop     rsi
0x18000a21c  pop     rbp
0x18000a21d  pop     rbx
0x18000a21e  retn
0x18000a21f  cmp     [r14], bl
0x18000a222  jz      short loc_18000A20E
0x18000a224  mov     rax, [rsi+8]
0x18000a228  or      ebp, 0FFFFFFFFh
0x18000a22b  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18000a22f  mov     r9d, ebp; cchCount1
0x18000a232  mov     r8, r14; lpString1
0x18000a235  mov     [rsp+68h+lpString2], rax; lpString2
0x18000a23a  mov     ecx, 409h; Locale
0x18000a23f  lea     edi, [rbp+2]
0x18000a242  mov     edx, edi; dwCmpFlags
0x18000a244  call    cs:__imp_CompareStringA
0x18000a24a  cmp     eax, 2
0x18000a24d  jnz     short loc_18000A20E
0x18000a24f  mov     ebx, edi
0x18000a251  test    r13d, r13d
0x18000a254  jz      short loc_18000A20E
0x18000a256  cmp     dword ptr [r12], 2
0x18000a25b  jnz     short loc_18000A20E
0x18000a25d  cmp     dword ptr [rsi+20h], 4
0x18000a261  jb      short loc_18000A20E
0x18000a263  mov     rdx, [rsi+28h]
0x18000a267  xor     ecx, ecx
0x18000a269  cmp     r13d, [rdx]
0x18000a26c  cmovnz  ebx, ecx
0x18000a26f  jmp     short loc_18000A20E
0x18000a271  test    edx, 0FFFF0000h
0x18000a277  jz      short loc_18000A1FB
0x18000a279  cmp     dword ptr [rsi+20h], 4
0x18000a27d  jb      loc_18000A1FB
0x18000a283  mov     rax, [rsi+28h]
0x18000a287  mov     ecx, [rax]
0x18000a289  test    edx, edx
0x18000a28b  jns     short loc_18000A2A6
0x18000a28d  bt      ecx, 1Eh
0x18000a291  jnb     short loc_18000A2A6
0x18000a293  xor     eax, eax
0x18000a295  jmp     loc_18000A210
0x18000a29a  cmp     r8d, [r12]
0x18000a29e  jz      loc_18000A1F4
0x18000a2a4  jmp     short loc_18000A293
0x18000a2a6  bt      edx, 1Eh
0x18000a2aa  jb      short loc_18000A31C
0x18000a2ac  bt      edx, 1Bh
0x18000a2b0  jb      short loc_18000A326
0x18000a2b2  bt      ecx, 1Bh
0x18000a2b6  setb    cl
0x18000a2b9  bt      edx, 1Ah
0x18000a2bd  setb    al
0x18000a2c0  test    al, cl
0x18000a2c2  jnz     short loc_18000A293
0x18000a2c4  jmp     loc_18000A1FB
0x18000a2c9  sub     eax, 1
0x18000a2cc  jz      loc_18000A368
0x18000a2d2  sub     eax, 1
0x18000a2d5  jz      loc_18000A360
0x18000a2db  sub     eax, 1
0x18000a2de  jz      short loc_18000A34B
0x18000a2e0  sub     eax, 1
0x18000a2e3  jnz     short loc_18000A332
0x18000a2e5  mov     rax, [rsi+30h]
0x18000a2e9  or      ebp, 0FFFFFFFFh
0x18000a2ec  mov     r8, r14; lpString1
0x18000a2ef  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18000a2f3  mov     r9d, ebp; cchCount1
0x18000a2f6  mov     ecx, 409h; Locale
0x18000a2fb  mov     [rsp+68h+lpString2], rax; lpString2
0x18000a300  lea     edx, [rbp+2]; dwCmpFlags
0x18000a303  call    cs:__imp_CompareStringW
0x18000a309  cmp     eax, 2
0x18000a30c  setz    bl
0x18000a30f  test    ebx, ebx
0x18000a311  jz      loc_18000A20E
0x18000a317  jmp     loc_18000A251
0x18000a31c  test    ecx, ecx
0x18000a31e  js      loc_18000A293
0x18000a324  jmp     short loc_18000A2AC
0x18000a326  bt      ecx, 1Ah
0x18000a32a  jb      loc_18000A293
0x18000a330  jmp     short loc_18000A2B2
0x18000a332  cmp     eax, 1
0x18000a335  jz      loc_18011544A
0x18000a33b  mov     ecx, 80070057h; dwErrCode
0x18000a340  call    cs:__imp_SetLastError
0x18000a346  jmp     loc_18000A20E
0x18000a34b  cmp     dword ptr [rsi+20h], 4
0x18000a34f  jb      loc_1801154E0
0x18000a355  mov     rax, [rsi+28h]
0x18000a359  mov     ecx, [rax]
0x18000a35b  jmp     loc_1801154E2
0x18000a360  mov     eax, [rsi+1Ch]
0x18000a363  cmp     [r14], eax
0x18000a366  jmp     short loc_18000A30C
0x18000a368  mov     rax, [rsi+10h]
0x18000a36c  jmp     loc_18000A2E9
0x18011544a  mov     r8, [r14]; lpString1
0x18011544d  lea     rax, aPrehash; "PreHash"
0x180115454  or      ebp, 0FFFFFFFFh
0x180115457  mov     ecx, 409h; Locale
0x18011545c  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x180115460  mov     r9d, ebp; cchCount1
0x180115463  mov     [rsp+68h+lpString2], rax; lpString2
0x180115468  lea     edi, [rbp+2]
0x18011546b  mov     edx, edi; dwCmpFlags
0x18011546d  call    cs:__imp_CompareStringW
0x180115473  mov     rcx, [rsi+30h]
0x180115477  mov     r9d, ebp; cchCount1
0x18011547a  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x18011547e  mov     edx, edi; dwCmpFlags
0x180115480  mov     [rsp+68h+lpString2], rcx; lpString2
0x180115485  mov     ecx, 409h; Locale
0x18011548a  add     eax, 0FFFFFFFEh
0x18011548d  jnz     short loc_1801154CC
0x18011548f  lea     r8, aNohash; "NoHash"
0x180115496  call    cs:__imp_CompareStringW
0x18011549c  cmp     eax, 2
0x18011549f  jz      loc_18000A20E
0x1801154a5  mov     rax, [rsi+38h]
0x1801154a9  mov     r9d, ebp; cchCount1
0x1801154ac  mov     r8, [r14+8]; lpString1
0x1801154b0  mov     edx, edi; dwCmpFlags
0x1801154b2  mov     [rsp+68h+cchCount2], ebp; cchCount2
0x1801154b6  mov     ecx, 409h; Locale
0x1801154bb  mov     [rsp+68h+lpString2], rax; lpString2
0x1801154c0  call    cs:__imp_CompareStringW
0x1801154c6  nop
0x1801154c7  jmp     loc_18000A24A
0x1801154cc  mov     r8, [r14]; lpString1
0x1801154cf  call    cs:__imp_CompareStringW
0x1801154d5  cmp     eax, 2
0x1801154d8  jnz     loc_18000A20E
0x1801154de  jmp     short loc_1801154A5
0x1801154e0  xor     ecx, ecx
0x1801154e2  mov     eax, [rsi+1Ch]
0x1801154e5  cmp     [r14], eax
0x1801154e8  jnz     loc_18000A20E
0x1801154ee  cmp     [r14+4], ecx
0x1801154f2  jnz     loc_18000A20E
0x1801154f8  mov     ebx, 1
0x1801154fd  jmp     loc_18000A251
```
