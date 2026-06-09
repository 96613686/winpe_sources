# _NewLoadedProviderHandle

- ea: `0x18003affc`
- end: `0x18003b16e`
- name: `_NewLoadedProviderHandle`
- size: `370`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003a46c`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003affc`
- `0x18009da40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18003b08d`
- `ntoskrnl!ExAllocatePool2` at `0x18003b08d`

## string_xrefs

- `0x18003b0b8`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b129`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18003affc  push    rbx
0x18003affe  push    rbp
0x18003afff  push    rsi
0x18003b000  push    rdi
0x18003b001  push    r12
0x18003b003  push    r14
0x18003b005  push    r15
0x18003b007  sub     rsp, 40h
0x18003b00b  mov     rax, [rcx+30h]
0x18003b00f  xor     r12d, r12d
0x18003b012  mov     r14, r8
0x18003b015  mov     [r8], r12
0x18003b018  mov     r15, rdx
0x18003b01b  mov     rbp, rcx
0x18003b01e  mov     r11, [rax]
0x18003b021  test    r11, r11
0x18003b024  jz      loc_18003B10A
0x18003b02a  mov     r10d, 800h
0x18003b030  mov     r9d, r10d
0x18003b033  cmp     [r11], r12w
0x18003b037  jz      short loc_18003B043
0x18003b039  add     r11, 2
0x18003b03d  sub     r9, 1
0x18003b041  jnz     short loc_18003B033
0x18003b043  mov     rax, r9
0x18003b046  neg     rax
0x18003b049  sbb     ecx, ecx
0x18003b04b  not     ecx
0x18003b04d  and     ecx, 80070057h
0x18003b053  test    r9, r9
0x18003b056  jz      loc_18003B10F
0x18003b05c  sub     r10, r9
0x18003b05f  add     r10, r10
0x18003b062  neg     r9
0x18003b065  sbb     rax, rax
0x18003b068  and     rax, r10
0x18003b06b  lea     rsi, [rax+2]
0x18003b06f  cmp     rsi, rax
0x18003b072  jb      loc_18003B0F8
0x18003b078  lea     rdx, [rsi+28h]
0x18003b07c  cmp     rdx, 28h ; '('
0x18003b080  jb      short loc_18003B0F8
0x18003b082  mov     ecx, 40h ; '@'
0x18003b087  mov     r8d, 62676E43h
0x18003b08d  call    cs:__imp_ExAllocatePool2
0x18003b094  nop     dword ptr [rax+rax+00h]
0x18003b099  mov     rbx, rax
0x18003b09c  test    rax, rax
0x18003b09f  jnz     short loc_18003B0C9
0x18003b0a1  mov     edi, 0C0000017h
0x18003b0a6  mov     r9d, 16Fh
0x18003b0ac  mov     ecx, 0C0000017h
0x18003b0b1  lea     rdx, aSresult; "sResult"
0x18003b0b8  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b0bf  call    DebugTraceError
0x18003b0c4  jmp     loc_18003B156
0x18003b0c9  lea     rcx, [rax+28h]; void *
0x18003b0cd  mov     r8, rsi; Size
0x18003b0d0  mov     [rax], rcx
0x18003b0d3  mov     edi, r12d
0x18003b0d6  mov     rdx, [rbp+30h]
0x18003b0da  mov     rdx, [rdx]; Src
0x18003b0dd  call    memmove
0x18003b0e2  movaps  xmm0, xmmword ptr [r15]
0x18003b0e6  movdqu  xmmword ptr [rbx+8], xmm0
0x18003b0eb  mov     dword ptr [rbx+18h], 2
0x18003b0f2  mov     [rbx+20h], r12
0x18003b0f6  jmp     short loc_18003B159
0x18003b0f8  mov     edi, 0C0000095h
0x18003b0fd  mov     r9d, 15Ch
0x18003b103  mov     ecx, 0C0000095h
0x18003b108  jmp     short loc_18003B0B1
0x18003b10a  mov     ecx, 80070057h
0x18003b10f  mov     rdx, cs:WPP_GLOBAL_Control
0x18003b116  lea     rax, WPP_GLOBAL_Control
0x18003b11d  cmp     rdx, rax
0x18003b120  jz      short loc_18003B151
0x18003b122  mov     eax, [rdx+2Ch]
0x18003b125  test    al, 1
0x18003b127  jz      short loc_18003B151
0x18003b129  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b130  mov     [rsp+78h+var_48], 152h
0x18003b138  mov     [rsp+78h+var_50], rax
0x18003b13d  lea     r9, aHresult; "hResult"
0x18003b144  mov     [rsp+78h+var_58], ecx
0x18003b148  mov     rcx, [rdx+18h]
0x18003b14c  call    WPP_SF_sDsd
0x18003b151  mov     edi, 0C000000Dh
0x18003b156  mov     rbx, r12
0x18003b159  mov     [r14], rbx
0x18003b15c  mov     eax, edi
0x18003b15e  add     rsp, 40h
0x18003b162  pop     r15
0x18003b164  pop     r14
0x18003b166  pop     r12
0x18003b168  pop     rdi
0x18003b169  pop     rsi
0x18003b16a  pop     rbp
0x18003b16b  pop     rbx
0x18003b16c  retn
```
