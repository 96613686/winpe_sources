# _NewLoadedProviderHandle

- ea: `0x18003bafc`
- end: `0x18003bc6e`
- name: `_NewLoadedProviderHandle`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003af6c`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003bafc`
- `0x18009f780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18003bb8d`
- `ntoskrnl!ExAllocatePool2` at `0x18003bb8d`

## string_xrefs

- `0x18003bbb8`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003bc29`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18003bafc  push    rbx
0x18003bafe  push    rbp
0x18003baff  push    rsi
0x18003bb00  push    rdi
0x18003bb01  push    r12
0x18003bb03  push    r14
0x18003bb05  push    r15
0x18003bb07  sub     rsp, 40h
0x18003bb0b  mov     rax, [rcx+30h]
0x18003bb0f  xor     r12d, r12d
0x18003bb12  mov     r14, r8
0x18003bb15  mov     [r8], r12
0x18003bb18  mov     r15, rdx
0x18003bb1b  mov     rbp, rcx
0x18003bb1e  mov     r11, [rax]
0x18003bb21  test    r11, r11
0x18003bb24  jz      loc_18003BC0A
0x18003bb2a  mov     r10d, 800h
0x18003bb30  mov     r9d, r10d
0x18003bb33  cmp     [r11], r12w
0x18003bb37  jz      short loc_18003BB43
0x18003bb39  add     r11, 2
0x18003bb3d  sub     r9, 1
0x18003bb41  jnz     short loc_18003BB33
0x18003bb43  mov     rax, r9
0x18003bb46  neg     rax
0x18003bb49  sbb     ecx, ecx
0x18003bb4b  not     ecx
0x18003bb4d  and     ecx, 80070057h
0x18003bb53  test    r9, r9
0x18003bb56  jz      loc_18003BC0F
0x18003bb5c  sub     r10, r9
0x18003bb5f  add     r10, r10
0x18003bb62  neg     r9
0x18003bb65  sbb     rax, rax
0x18003bb68  and     rax, r10
0x18003bb6b  lea     rsi, [rax+2]
0x18003bb6f  cmp     rsi, rax
0x18003bb72  jb      loc_18003BBF8
0x18003bb78  lea     rdx, [rsi+28h]
0x18003bb7c  cmp     rdx, 28h ; '('
0x18003bb80  jb      short loc_18003BBF8
0x18003bb82  mov     ecx, 40h ; '@'
0x18003bb87  mov     r8d, 62676E43h
0x18003bb8d  call    cs:__imp_ExAllocatePool2
0x18003bb94  nop     dword ptr [rax+rax+00h]
0x18003bb99  mov     rbx, rax
0x18003bb9c  test    rax, rax
0x18003bb9f  jnz     short loc_18003BBC9
0x18003bba1  mov     edi, 0C0000017h
0x18003bba6  mov     r9d, 16Fh
0x18003bbac  mov     ecx, 0C0000017h
0x18003bbb1  lea     rdx, aSresult; "sResult"
0x18003bbb8  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003bbbf  call    DebugTraceError
0x18003bbc4  jmp     loc_18003BC56
0x18003bbc9  lea     rcx, [rax+28h]; void *
0x18003bbcd  mov     r8, rsi; Size
0x18003bbd0  mov     [rax], rcx
0x18003bbd3  mov     edi, r12d
0x18003bbd6  mov     rdx, [rbp+30h]
0x18003bbda  mov     rdx, [rdx]; Src
0x18003bbdd  call    memmove
0x18003bbe2  movaps  xmm0, xmmword ptr [r15]
0x18003bbe6  movdqu  xmmword ptr [rbx+8], xmm0
0x18003bbeb  mov     dword ptr [rbx+18h], 2
0x18003bbf2  mov     [rbx+20h], r12
0x18003bbf6  jmp     short loc_18003BC59
0x18003bbf8  mov     edi, 0C0000095h
0x18003bbfd  mov     r9d, 15Ch
0x18003bc03  mov     ecx, 0C0000095h
0x18003bc08  jmp     short loc_18003BBB1
0x18003bc0a  mov     ecx, 80070057h
0x18003bc0f  mov     rdx, cs:WPP_GLOBAL_Control
0x18003bc16  lea     rax, WPP_GLOBAL_Control
0x18003bc1d  cmp     rdx, rax
0x18003bc20  jz      short loc_18003BC51
0x18003bc22  mov     eax, [rdx+2Ch]
0x18003bc25  test    al, 1
0x18003bc27  jz      short loc_18003BC51
0x18003bc29  lea     rax, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003bc30  mov     [rsp+78h+var_48], 152h
0x18003bc38  mov     [rsp+78h+var_50], rax
0x18003bc3d  lea     r9, aHresult; "hResult"
0x18003bc44  mov     [rsp+78h+var_58], ecx
0x18003bc48  mov     rcx, [rdx+18h]
0x18003bc4c  call    WPP_SF_sDsd
0x18003bc51  mov     edi, 0C000000Dh
0x18003bc56  mov     rbx, r12
0x18003bc59  mov     [r14], rbx
0x18003bc5c  mov     eax, edi
0x18003bc5e  add     rsp, 40h
0x18003bc62  pop     r15
0x18003bc64  pop     r14
0x18003bc66  pop     r12
0x18003bc68  pop     rdi
0x18003bc69  pop     rsi
0x18003bc6a  pop     rbp
0x18003bc6b  pop     rbx
0x18003bc6c  retn
```
