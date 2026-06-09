# _NewLoadedProviderHandle

- ea: `0x18004508c`
- end: `0x1800451fe`
- name: `_NewLoadedProviderHandle`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800444fc`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18004508c`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18004511d`
- `ntoskrnl!ExAllocatePool2` at `0x18004511d`

## string_xrefs

- `0x180045148`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800451b9`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall NewLoadedProviderHandle(__int64 a1, _OWORD *a2, _QWORD *a3)
{
  _WORD **v3; // rax
  _WORD *v7; // r11
  __int64 v8; // r9
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  size_t v11; // rsi
  _QWORD *Pool2; // rax
  _QWORD *v13; // rbx
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx

  v3 = *(_WORD ***)(a1 + 48);
  *a3 = 0;
  v7 = *v3;
  if ( !*v3 )
  {
    LOBYTE(v9) = 87;
    goto LABEL_14;
  }
  v8 = 2048;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_14:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        (unsigned int)"hResult",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        82);
    v14 = -1073741811;
    goto LABEL_18;
  }
  v10 = (2 * (2048 - v8)) & -(__int64)(v8 != 0);
  v11 = v10 + 2;
  if ( v10 + 2 < v10 || v11 >= 0xFFFFFFFFFFFFFFD8uLL )
  {
    v14 = -1073741675;
    v15 = 348;
    v16 = 3221225621LL;
    goto LABEL_10;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, v10 + 42, 1650945603);
  v13 = Pool2;
  if ( !Pool2 )
  {
    v14 = -1073741801;
    v15 = 367;
    v16 = 3221225495LL;
LABEL_10:
    DebugTraceError(v16, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v15);
LABEL_18:
    v13 = 0;
    goto LABEL_19;
  }
  *Pool2 = Pool2 + 5;
  v14 = 0;
  memmove(Pool2 + 5, **(const void ***)(a1 + 48), v11);
  *(_OWORD *)(v13 + 1) = *a2;
  *((_DWORD *)v13 + 6) = 2;
  v13[4] = 0;
LABEL_19:
  *a3 = v13;
  return v14;
}

```

## disassembly

```asm
0x18004508c  push    rbx
0x18004508e  push    rbp
0x18004508f  push    rsi
0x180045090  push    rdi
0x180045091  push    r12
0x180045093  push    r14
0x180045095  push    r15
0x180045097  sub     rsp, 40h
0x18004509b  mov     rax, [rcx+30h]
0x18004509f  xor     r12d, r12d
0x1800450a2  mov     r14, r8
0x1800450a5  mov     [r8], r12
0x1800450a8  mov     r15, rdx
0x1800450ab  mov     rbp, rcx
0x1800450ae  mov     r11, [rax]
0x1800450b1  test    r11, r11
0x1800450b4  jz      loc_18004519A
0x1800450ba  mov     r10d, 800h
0x1800450c0  mov     r9d, r10d
0x1800450c3  cmp     [r11], r12w
0x1800450c7  jz      short loc_1800450D3
0x1800450c9  add     r11, 2
0x1800450cd  sub     r9, 1
0x1800450d1  jnz     short loc_1800450C3
0x1800450d3  mov     rax, r9
0x1800450d6  neg     rax
0x1800450d9  sbb     ecx, ecx
0x1800450db  not     ecx
0x1800450dd  and     ecx, 80070057h
0x1800450e3  test    r9, r9
0x1800450e6  jz      loc_18004519F
0x1800450ec  sub     r10, r9
0x1800450ef  add     r10, r10
0x1800450f2  neg     r9
0x1800450f5  sbb     rax, rax
0x1800450f8  and     rax, r10
0x1800450fb  lea     rsi, [rax+2]
0x1800450ff  cmp     rsi, rax
0x180045102  jb      loc_180045188
0x180045108  lea     rdx, [rsi+28h]
0x18004510c  cmp     rdx, 28h ; '('
0x180045110  jb      short loc_180045188
0x180045112  mov     ecx, 40h ; '@'
0x180045117  mov     r8d, 62676E43h
0x18004511d  call    cs:__imp_ExAllocatePool2
0x180045124  nop     dword ptr [rax+rax+00h]
0x180045129  mov     rbx, rax
0x18004512c  test    rax, rax
0x18004512f  jnz     short loc_180045159
0x180045131  mov     edi, 0C0000017h
0x180045136  mov     r9d, 16Fh
0x18004513c  mov     ecx, 0C0000017h
0x180045141  lea     rdx, aSresult; "sResult"
0x180045148  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004514f  call    DebugTraceError
0x180045154  jmp     loc_1800451E6
0x180045159  lea     rcx, [rax+28h]; void *
0x18004515d  mov     r8, rsi; Size
0x180045160  mov     [rax], rcx
0x180045163  mov     edi, r12d
0x180045166  mov     rdx, [rbp+30h]
0x18004516a  mov     rdx, [rdx]; Src
0x18004516d  call    memmove
0x180045172  movaps  xmm0, xmmword ptr [r15]
0x180045176  movdqu  xmmword ptr [rbx+8], xmm0
0x18004517b  mov     dword ptr [rbx+18h], 2
0x180045182  mov     [rbx+20h], r12
0x180045186  jmp     short loc_1800451E9
0x180045188  mov     edi, 0C0000095h
0x18004518d  mov     r9d, 15Ch
0x180045193  mov     ecx, 0C0000095h
0x180045198  jmp     short loc_180045141
0x18004519a  mov     ecx, 80070057h
0x18004519f  mov     rdx, cs:WPP_GLOBAL_Control
0x1800451a6  lea     rax, WPP_GLOBAL_Control
0x1800451ad  cmp     rdx, rax
0x1800451b0  jz      short loc_1800451E1
0x1800451b2  mov     eax, [rdx+2Ch]
0x1800451b5  test    al, 1
0x1800451b7  jz      short loc_1800451E1
0x1800451b9  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800451c0  mov     [rsp+78h+var_48], 152h
0x1800451c8  mov     [rsp+78h+var_50], rax
0x1800451cd  lea     r9, aHresult; "hResult"
0x1800451d4  mov     [rsp+78h+var_58], ecx
0x1800451d8  mov     rcx, [rdx+18h]
0x1800451dc  call    WPP_SF_sDsd
0x1800451e1  mov     edi, 0C000000Dh
0x1800451e6  mov     rbx, r12
0x1800451e9  mov     [r14], rbx
0x1800451ec  mov     eax, edi
0x1800451ee  add     rsp, 40h
0x1800451f2  pop     r15
0x1800451f4  pop     r14
0x1800451f6  pop     r12
0x1800451f8  pop     rdi
0x1800451f9  pop     rsi
0x1800451fa  pop     rbp
0x1800451fb  pop     rbx
0x1800451fc  retn
```
