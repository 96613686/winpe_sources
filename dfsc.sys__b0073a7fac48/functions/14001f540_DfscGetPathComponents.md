# DfscGetPathComponents

- ea: `0x14001f540`
- end: `0x14001f890`
- name: `DfscGetPathComponents`
- size: `848`
- prototype: `__int64 __fastcall(__int16 *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, PUNICODE_STRING DestinationString)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016070`
- `0x14001d110`
- `0x14001e3d0`
- `0x14001ef20`
- `0x14001f040`
- `0x14001fb50`
- `0x140021410`
- `0x1400281ac`

## callees

- `0x14001f540`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001f795`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f7ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f802`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f87f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f795`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f7ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f802`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f87f`

## pseudocode

```c
__int64 __fastcall DfscGetPathComponents(
        __int16 *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        PUNICODE_STRING DestinationString)
{
  struct _UNICODE_STRING *v5; // rdi
  struct _UNICODE_STRING *v8; // r10
  BOOL v9; // r15d
  BOOL v11; // ebp
  bool v12; // zf
  _WORD *v13; // r9
  BOOL v14; // ebx
  BOOL v15; // r13d
  unsigned __int16 v16; // dx
  unsigned __int16 v17; // di
  unsigned __int16 v18; // dx
  unsigned __int16 v19; // ax
  __int16 v20; // r8
  USHORT v21; // r8
  unsigned __int16 v22; // ax
  unsigned int v23; // r15d
  __int16 v24; // r10
  unsigned __int16 v25; // r11
  unsigned __int16 v26; // r8
  __int16 v27; // r9
  USHORT v28; // ax
  WCHAR *Buffer; // rax
  USHORT Length; // cx
  unsigned __int16 v31; // dx
  __int64 v32; // rax
  USHORT v33; // dx
  BOOL v35; // [rsp+70h] [rbp+8h]
  BOOL v37; // [rsp+80h] [rbp+18h]

  v5 = DestinationString;
  v8 = a2;
  v9 = a2 != 0;
  v35 = v9;
  v11 = a3 != 0;
  v12 = a4 == 0;
  v37 = v11;
  v13 = (_WORD *)*((_QWORD *)a1 + 1);
  v14 = !v12;
  v15 = DestinationString != 0;
  if ( !v13 || (v16 = *a1) == 0 )
  {
    v23 = 0;
    goto LABEL_34;
  }
  v17 = 0;
  if ( v16 >= 2u )
    v17 = *v13 == 92;
  if ( v16 >= 4u && v13[v17] == 92 )
    goto LABEL_44;
  v18 = v16 >> 1;
  v19 = v17;
  v20 = v17;
  if ( v17 >= v18 )
    goto LABEL_44;
  do
  {
    if ( v13[v19] == 92 )
      break;
    v20 = ++v19;
  }
  while ( v19 < v18 );
  if ( v19 == v17 )
  {
LABEL_44:
    v5 = DestinationString;
    v23 = -1073741811;
    goto LABEL_34;
  }
  if ( v8 )
  {
    v21 = 2 * (v20 - v17);
    v35 = 0;
    v8->Length = v21;
    v8->MaximumLength = v21;
    v8->Buffer = &v13[v17];
  }
  else
  {
    v35 = v9;
  }
  v22 = v19 + 1;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = v22;
  while ( v26 < (unsigned __int16)((unsigned __int16)*a1 >> 1) )
  {
    v27 = *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v26);
    if ( v27 == 58 )
    {
      if ( v24 )
        goto LABEL_16;
      v24 = v26++;
    }
    else
    {
      if ( v27 == 92 )
      {
        v25 = v26;
        break;
      }
LABEL_16:
      ++v26;
    }
  }
  if ( v26 <= v22 )
  {
    v14 = !v12;
    v5 = DestinationString;
    v8 = a2;
  }
  else
  {
    if ( !v25 )
    {
      if ( v24 )
        v26 = v24;
      v25 = v26;
    }
    if ( a3 )
    {
      v37 = 0;
      a3->Buffer = (PWSTR)(*((_QWORD *)a1 + 1) + 2LL * v22);
      v28 = 2 * (v25 - v22);
      a3->Length = v28;
      a3->MaximumLength = v28;
    }
    v11 = v37;
    v8 = a2;
    if ( a4 )
    {
      Buffer = a2->Buffer;
      v14 = 0;
      a4->Buffer = Buffer;
      Length = a2->Length;
      a4->Length = a2->Length;
      if ( v17 )
      {
        Length += 2;
        a4->Buffer = Buffer - 1;
        a4->Length = Length;
      }
      if ( a3->Length )
      {
        a4->Length = Length + 2;
        Length += a3->Length + 2;
        a4->Length = Length;
      }
      a4->MaximumLength = Length;
    }
    else
    {
      v14 = !v12;
    }
    v31 = (unsigned __int16)*a1 >> 1;
    if ( v25 < v31 && *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v25) == 92 )
      ++v25;
    v5 = DestinationString;
    if ( DestinationString && v25 < v31 )
    {
      v32 = *((_QWORD *)a1 + 1);
      v15 = 0;
      v33 = 2 * (v31 - v25);
      DestinationString->Length = v33;
      DestinationString->MaximumLength = v33;
      DestinationString->Buffer = (PWSTR)(v32 + 2LL * v25);
    }
  }
LABEL_34:
  if ( v35 )
    RtlInitUnicodeString(v8, 0);
  if ( v11 )
    RtlInitUnicodeString(a3, 0);
  if ( v14 )
    RtlInitUnicodeString(a4, 0);
  if ( v15 )
    RtlInitUnicodeString(v5, 0);
  return v23;
}

```

## disassembly

```asm
0x14001f540  mov     [rsp+arg_8], rdx
0x14001f545  push    rbx
0x14001f546  push    rbp
0x14001f547  push    rsi
0x14001f548  push    rdi
0x14001f549  push    r12
0x14001f54b  push    r13
0x14001f54d  push    r14
0x14001f54f  push    r15
0x14001f551  sub     rsp, 28h
0x14001f555  mov     rdi, [rsp+68h+DestinationString]
0x14001f55d  xor     r15d, r15d
0x14001f560  test    rdx, rdx
0x14001f563  mov     r14, r9
0x14001f566  mov     r12, r8
0x14001f569  mov     r10, rdx
0x14001f56c  setnz   r15b
0x14001f570  mov     rsi, rcx
0x14001f573  xor     ebp, ebp
0x14001f575  mov     [rsp+68h+arg_0], r15d
0x14001f57a  test    r8, r8
0x14001f57d  setnz   bpl
0x14001f581  xor     ebx, ebx
0x14001f583  test    r9, r9
0x14001f586  mov     [rsp+68h+arg_10], ebp
0x14001f58d  mov     r9, [rcx+8]
0x14001f591  setnz   bl
0x14001f594  xor     r13d, r13d
0x14001f597  test    rdi, rdi
0x14001f59a  mov     [rsp+68h+arg_18], ebx
0x14001f5a1  setnz   r13b
0x14001f5a5  test    r9, r9
0x14001f5a8  jz      loc_14001F85B
0x14001f5ae  movzx   edx, word ptr [rcx]
0x14001f5b1  test    dx, dx
0x14001f5b4  jz      loc_14001F85B
0x14001f5ba  xor     edi, edi
0x14001f5bc  cmp     dx, 2
0x14001f5c0  jnb     loc_14001F7B6
0x14001f5c6  cmp     dx, 4
0x14001f5ca  jnb     loc_14001F7CB
0x14001f5d0  shr     dx, 1
0x14001f5d3  movzx   eax, di
0x14001f5d6  movzx   r8d, di
0x14001f5da  cmp     di, dx
0x14001f5dd  jnb     loc_14001F7DA
0x14001f5e3  movzx   ecx, ax
0x14001f5e6  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x14001f5ec  jz      short loc_14001F5FA
0x14001f5ee  inc     ax
0x14001f5f1  movzx   r8d, ax
0x14001f5f5  cmp     ax, dx
0x14001f5f8  jb      short loc_14001F5E3
0x14001f5fa  cmp     ax, di
0x14001f5fd  jz      loc_14001F7DA
0x14001f603  test    r10, r10
0x14001f606  jz      loc_14001F851
0x14001f60c  movzx   edx, di
0x14001f60f  sub     r8w, di
0x14001f613  add     r8w, r8w
0x14001f617  mov     [rsp+68h+arg_0], 0
0x14001f61f  mov     [r10], r8w
0x14001f623  mov     [r10+2], r8w
0x14001f628  lea     rdx, [r9+rdx*2]
0x14001f62c  mov     [r10+8], rdx
0x14001f630  movzx   ebx, word ptr [rsi]
0x14001f633  inc     ax
0x14001f636  xor     r15d, r15d
0x14001f639  xor     r10d, r10d
0x14001f63c  xor     r11d, r11d
0x14001f63f  movzx   ebp, ax
0x14001f642  movzx   r8d, ax
0x14001f646  shr     bx, 1
0x14001f649  nop     dword ptr [rax+00000000h]
0x14001f650  cmp     r8w, bx
0x14001f654  jnb     short loc_14001F67F
0x14001f656  mov     rcx, [rsi+8]
0x14001f65a  movzx   edx, r8w
0x14001f65e  movzx   r9d, word ptr [rcx+rdx*2]
0x14001f663  cmp     r9w, 3Ah ; ':'
0x14001f668  jz      loc_14001F863
0x14001f66e  cmp     r9w, 5Ch ; '\'
0x14001f673  jz      short loc_14001F67B
0x14001f675  inc     r8w
0x14001f679  jmp     short loc_14001F650
0x14001f67b  movzx   r11d, r8w
0x14001f67f  cmp     r8w, ax
0x14001f683  jbe     loc_14001F831
0x14001f689  test    r11w, r11w
0x14001f68d  jz      loc_14001F81F
0x14001f693  test    r12, r12
0x14001f696  jz      short loc_14001F6C5
0x14001f698  movzx   ecx, ax
0x14001f69b  mov     rax, [rsi+8]
0x14001f69f  mov     [rsp+68h+arg_10], r15d
0x14001f6a7  lea     rcx, [rax+rcx*2]
0x14001f6ab  movzx   eax, r11w
0x14001f6af  sub     ax, bp
0x14001f6b2  mov     [r12+8], rcx
0x14001f6b7  add     ax, ax
0x14001f6ba  mov     [r12], ax
0x14001f6bf  mov     [r12+2], ax
0x14001f6c5  mov     ebp, [rsp+68h+arg_10]
0x14001f6cc  mov     r10, [rsp+68h+arg_8]
0x14001f6d1  test    r14, r14
0x14001f6d4  jz      loc_14001F813
0x14001f6da  mov     rax, [r10+8]
0x14001f6de  xor     ebx, ebx
0x14001f6e0  mov     [r14+8], rax
0x14001f6e4  movzx   ecx, word ptr [r10]
0x14001f6e8  mov     [r14], cx
0x14001f6ec  test    di, di
0x14001f6ef  jz      short loc_14001F701
0x14001f6f1  add     rax, 0FFFFFFFFFFFFFFFEh
0x14001f6f5  add     cx, 2
0x14001f6f9  mov     [r14+8], rax
0x14001f6fd  mov     [r14], cx
0x14001f701  cmp     [r12], bx
0x14001f706  jbe     short loc_14001F71C
0x14001f708  lea     eax, [rcx+2]
0x14001f70b  add     cx, 2
0x14001f70f  mov     [r14], ax
0x14001f713  add     cx, [r12]
0x14001f718  mov     [r14], cx
0x14001f71c  mov     [r14+2], cx
0x14001f721  movzx   eax, word ptr [rsi]
0x14001f724  shr     ax, 1
0x14001f727  movzx   edx, ax
0x14001f72a  cmp     r11w, ax
0x14001f72e  jnb     short loc_14001F743
0x14001f730  mov     rax, [rsi+8]
0x14001f734  movzx   ecx, r11w
0x14001f738  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x14001f73d  jnz     short loc_14001F743
0x14001f73f  inc     r11w
0x14001f743  mov     rdi, [rsp+68h+DestinationString]
0x14001f74b  test    rdi, rdi
0x14001f74e  jz      short loc_14001F777
0x14001f750  cmp     r11w, dx
0x14001f754  jnb     short loc_14001F777
0x14001f756  mov     rax, [rsi+8]
0x14001f75a  xor     r13d, r13d
0x14001f75d  movzx   ecx, r11w
0x14001f761  sub     dx, r11w
0x14001f765  add     dx, dx
0x14001f768  mov     [rdi], dx
0x14001f76b  mov     [rdi+2], dx
0x14001f76f  lea     rcx, [rax+rcx*2]
0x14001f773  mov     [rdi+8], rcx
0x14001f777  mov     eax, [rsp+68h+arg_0]
0x14001f77b  test    eax, eax
0x14001f77d  jnz     loc_14001F87A
0x14001f783  test    ebp, ebp
0x14001f785  jnz     short loc_14001F7FD
0x14001f787  test    ebx, ebx
0x14001f789  jnz     short loc_14001F7EA
0x14001f78b  test    r13d, r13d
0x14001f78e  jz      short loc_14001F7A1
0x14001f790  xor     edx, edx; SourceString
0x14001f792  mov     rcx, rdi; DestinationString
0x14001f795  call    cs:__imp_RtlInitUnicodeString
0x14001f79c  nop     dword ptr [rax+rax+00h]
0x14001f7a1  mov     eax, r15d
0x14001f7a4  add     rsp, 28h
0x14001f7a8  pop     r15
0x14001f7aa  pop     r14
0x14001f7ac  pop     r13
0x14001f7ae  pop     r12
0x14001f7b0  pop     rdi
0x14001f7b1  pop     rsi
0x14001f7b2  pop     rbp
0x14001f7b3  pop     rbx
0x14001f7b4  retn
0x14001f7b6  cmp     word ptr [r9], 5Ch ; '\'
0x14001f7bb  jnz     loc_14001F5C6
0x14001f7c1  mov     edi, 1
0x14001f7c6  jmp     loc_14001F5C6
0x14001f7cb  movzx   eax, di
0x14001f7ce  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14001f7d4  jnz     loc_14001F5D0
0x14001f7da  mov     rdi, [rsp+68h+DestinationString]
0x14001f7e2  mov     r15d, 0C000000Dh
0x14001f7e8  jmp     short loc_14001F777
0x14001f7ea  xor     edx, edx; SourceString
0x14001f7ec  mov     rcx, r14; DestinationString
0x14001f7ef  call    cs:__imp_RtlInitUnicodeString
0x14001f7f6  nop     dword ptr [rax+rax+00h]
0x14001f7fb  jmp     short loc_14001F78B
0x14001f7fd  xor     edx, edx; SourceString
0x14001f7ff  mov     rcx, r12; DestinationString
0x14001f802  call    cs:__imp_RtlInitUnicodeString
0x14001f809  nop     dword ptr [rax+rax+00h]
0x14001f80e  jmp     loc_14001F787
0x14001f813  mov     ebx, [rsp+68h+arg_18]
0x14001f81a  jmp     loc_14001F721
0x14001f81f  test    r10w, r10w
0x14001f823  cmovnz  r8w, r10w
0x14001f828  movzx   r11d, r8w
0x14001f82c  jmp     loc_14001F693
0x14001f831  mov     ebp, [rsp+68h+arg_10]
0x14001f838  mov     ebx, [rsp+68h+arg_18]
0x14001f83f  mov     rdi, [rsp+68h+DestinationString]
0x14001f847  mov     r10, [rsp+68h+arg_8]
0x14001f84c  jmp     loc_14001F777
0x14001f851  mov     [rsp+68h+arg_0], r15d
0x14001f856  jmp     loc_14001F630
0x14001f85b  xor     r15d, r15d
0x14001f85e  jmp     loc_14001F777
0x14001f863  test    r10w, r10w
0x14001f867  jnz     loc_14001F675
0x14001f86d  movzx   r10d, r8w
0x14001f871  inc     r8w
0x14001f875  jmp     loc_14001F650
0x14001f87a  xor     edx, edx; SourceString
0x14001f87c  mov     rcx, r10; DestinationString
0x14001f87f  call    cs:__imp_RtlInitUnicodeString
0x14001f886  nop     dword ptr [rax+rax+00h]
0x14001f88b  jmp     loc_14001F783
```
