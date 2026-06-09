# GetExecutablePathFromCommandLine(ushort const *,ushort * *)

- ea: `0x14000a0d4`
- end: `0x14000a273`
- name: `?GetExecutablePathFromCommandLine@@YAJPEBGPEAPEAG@Z`
- size: `415`
- prototype: `__int64 __fastcall(wchar_t *Str, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005b10`

## callees

- `0x140001af3`
- `0x140005ffc`
- `0x14000a0d4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000a13a`
- `msvcrt!wcsrchr` at `0x14000a13a`
- `ole32!CoTaskMemAlloc` at `0x14000a1f4`
- `ole32!CoTaskMemAlloc` at `0x14000a1f4`
- `ole32!CoTaskMemFree` at `0x14000a22e`
- `ole32!CoTaskMemFree` at `0x14000a22e`

## pseudocode

```c
__int64 __fastcall GetExecutablePathFromCommandLine(wchar_t *Str, unsigned __int16 **a2)
{
  wchar_t *j; // rsi
  wchar_t i; // ax
  wchar_t v6; // ax
  wchar_t v7; // r15
  __int64 v8; // rcx
  wchar_t *v9; // rax
  signed int v10; // ebx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rbp
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rax
  unsigned __int64 v18; // [rsp+70h] [rbp+8h]

  while ( *Str == 32 || *Str == 9 )
    ++Str;
  if ( *Str == 34 )
  {
    j = ++Str;
    for ( i = *Str; i && i != 34; i = *j )
      ++j;
  }
  else
  {
    j = wcsrchr(Str, 0x5Cu);
    if ( j )
      goto LABEL_14;
    for ( j = Str; ; ++j )
    {
      v6 = *j;
      if ( !*j || v6 == 32 || v6 == 9 )
        break;
LABEL_14:
      ;
    }
  }
  v7 = *j;
  v8 = 2147483646;
  *j = 0;
  v9 = Str;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  v11 = (2147483646 - v8) & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64);
  HIDWORD(v18) = HIDWORD(v11);
  if ( v8 )
  {
    v12 = 0;
    if ( v11 )
    {
      v13 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v13 < (unsigned int)v11 || (LODWORD(v18) = v11 + 1, v14 = 2 * v13, v14 > 0xFFFFFFFF) )
      {
        v10 = -2147024362;
      }
      else
      {
        v15 = v14;
        v16 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v14);
        v12 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, v15);
          v10 = StringCchCopyW(v12, v18, Str);
          if ( v10 < 0 )
          {
            CoTaskMemFree(v12);
            v12 = 0;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
    }
    *a2 = v12;
  }
  if ( v10 >= 0 && !*a2 )
    v10 = -2147024809;
  *j = v7;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a0d4  push    rbx
0x14000a0d6  push    rbp
0x14000a0d7  push    rsi
0x14000a0d8  push    rdi
0x14000a0d9  push    r12
0x14000a0db  push    r13
0x14000a0dd  push    r14
0x14000a0df  push    r15
0x14000a0e1  sub     rsp, 28h
0x14000a0e5  mov     ebx, 20h ; ' '
0x14000a0ea  mov     r12, rdx
0x14000a0ed  mov     r14, rcx
0x14000a0f0  lea     ebp, [rbx-17h]
0x14000a0f3  cmp     bx, [r14]
0x14000a0f7  jz      short loc_14000A0FF
0x14000a0f9  cmp     bp, [r14]
0x14000a0fd  jnz     short loc_14000A105
0x14000a0ff  add     r14, 2
0x14000a103  jmp     short loc_14000A0F3
0x14000a105  mov     ecx, 22h ; '"'
0x14000a10a  cmp     cx, [r14]
0x14000a10e  jnz     short loc_14000A132
0x14000a110  add     r14, 2
0x14000a114  mov     rsi, r14
0x14000a117  xor     edi, edi
0x14000a119  movzx   eax, word ptr [r14]
0x14000a11d  jmp     short loc_14000A12B
0x14000a11f  cmp     cx, ax
0x14000a122  jz      short loc_14000A16B
0x14000a124  add     rsi, 2
0x14000a128  movzx   eax, word ptr [rsi]
0x14000a12b  cmp     di, ax
0x14000a12e  jnz     short loc_14000A11F
0x14000a130  jmp     short loc_14000A16B
0x14000a132  mov     edx, 5Ch ; '\'; Ch
0x14000a137  mov     rcx, r14; Str
0x14000a13a  call    cs:__imp_wcsrchr
0x14000a141  nop     dword ptr [rax+rax+00h]
0x14000a146  xor     edi, edi
0x14000a148  mov     rsi, rax
0x14000a14b  test    rax, rax
0x14000a14e  jnz     short loc_14000A15F
0x14000a150  mov     rsi, r14
0x14000a153  jmp     short loc_14000A163
0x14000a155  cmp     bx, ax
0x14000a158  jz      short loc_14000A16B
0x14000a15a  cmp     bp, ax
0x14000a15d  jz      short loc_14000A16B
0x14000a15f  add     rsi, 2
0x14000a163  movzx   eax, word ptr [rsi]
0x14000a166  cmp     di, ax
0x14000a169  jnz     short loc_14000A155
0x14000a16b  movzx   r15d, word ptr [rsi]
0x14000a16f  mov     r8d, 7FFFFFFEh
0x14000a175  mov     ecx, r8d
0x14000a178  mov     [rsi], di
0x14000a17b  mov     rax, r14
0x14000a17e  cmp     [rax], di
0x14000a181  jz      short loc_14000A18D
0x14000a183  add     rax, 2
0x14000a187  sub     rcx, 1
0x14000a18b  jnz     short loc_14000A17E
0x14000a18d  mov     rax, rcx
0x14000a190  mov     r13d, 80070057h
0x14000a196  neg     rax
0x14000a199  sbb     ebx, ebx
0x14000a19b  not     ebx
0x14000a19d  and     ebx, r13d
0x14000a1a0  test    rcx, rcx
0x14000a1a3  jz      short loc_14000A1B2
0x14000a1a5  mov     rax, r8
0x14000a1a8  sub     rax, rcx
0x14000a1ab  mov     [rsp+68h+arg_0], rax
0x14000a1b0  jmp     short loc_14000A1B7
0x14000a1b2  mov     [rsp+68h+arg_0], rdi
0x14000a1b7  sub     r8, rcx
0x14000a1ba  mov     rax, rcx
0x14000a1bd  neg     rax
0x14000a1c0  sbb     rdx, rdx
0x14000a1c3  and     rdx, r8
0x14000a1c6  mov     [rsp+68h+arg_0], rdx
0x14000a1cb  test    rcx, rcx
0x14000a1ce  jz      short loc_14000A24F
0x14000a1d0  mov     rbp, rdi
0x14000a1d3  test    rdx, rdx
0x14000a1d6  jz      short loc_14000A24B
0x14000a1d8  lea     eax, [rdx+1]
0x14000a1db  cmp     eax, edx
0x14000a1dd  jb      short loc_14000A246
0x14000a1df  mov     dword ptr [rsp+68h+arg_0], eax
0x14000a1e3  mov     ecx, 0FFFFFFFFh
0x14000a1e8  add     rax, rax
0x14000a1eb  cmp     rax, rcx
0x14000a1ee  ja      short loc_14000A246
0x14000a1f0  mov     ecx, eax; cb
0x14000a1f2  mov     ebx, eax
0x14000a1f4  call    cs:__imp_CoTaskMemAlloc
0x14000a1fb  nop     dword ptr [rax+rax+00h]
0x14000a200  mov     rbp, rax
0x14000a203  test    rax, rax
0x14000a206  jz      short loc_14000A23F
0x14000a208  mov     r8d, ebx; Size
0x14000a20b  xor     edx, edx; Val
0x14000a20d  mov     rcx, rax; void *
0x14000a210  call    memset_0
0x14000a215  mov     rdx, [rsp+68h+arg_0]; unsigned __int64
0x14000a21a  mov     r8, r14; unsigned __int16 *
0x14000a21d  mov     rcx, rbp; unsigned __int16 *
0x14000a220  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a225  mov     ebx, eax
0x14000a227  test    eax, eax
0x14000a229  jns     short loc_14000A24B
0x14000a22b  mov     rcx, rbp; pv
0x14000a22e  call    cs:__imp_CoTaskMemFree
0x14000a235  nop     dword ptr [rax+rax+00h]
0x14000a23a  mov     rbp, rdi
0x14000a23d  jmp     short loc_14000A24B
0x14000a23f  mov     ebx, 8007000Eh
0x14000a244  jmp     short loc_14000A24B
0x14000a246  mov     ebx, 80070216h
0x14000a24b  mov     [r12], rbp
0x14000a24f  test    ebx, ebx
0x14000a251  js      short loc_14000A25B
0x14000a253  cmp     [r12], rdi
0x14000a257  cmovz   ebx, r13d
0x14000a25b  mov     [rsi], r15w
0x14000a25f  mov     eax, ebx
0x14000a261  add     rsp, 28h
0x14000a265  pop     r15
0x14000a267  pop     r14
0x14000a269  pop     r13
0x14000a26b  pop     r12
0x14000a26d  pop     rdi
0x14000a26e  pop     rsi
0x14000a26f  pop     rbp
0x14000a270  pop     rbx
0x14000a271  retn
```
