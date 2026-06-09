# CRTFRead::HandleFieldSymbolFont(uchar *)

- ea: `0x18007e2a0`
- end: `0x18007e426`
- name: `?HandleFieldSymbolFont@CRTFRead@@AEAAHPEAE@Z`
- size: `390`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007e42c`

## callees

- `0x1800193e0`
- `0x18001e3e0`
- `0x18002cad4`
- `0x1800466f0`
- `0x18007b10c`
- `0x18007e2a0`
- `0x180093bca`
- `0x180093bd6`
- `0x180093c00`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18007e3c5`
- `msvcrt!wcscpy_s` at `0x18007e3c5`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleFieldSymbolFont(CRTFRead *this, unsigned __int8 *a2)
{
  __int16 v2; // bp
  __int64 v5; // r14
  int v6; // ecx
  int v7; // eax
  unsigned __int8 v8; // dl
  unsigned __int16 v9; // di
  const wchar_t *v10; // rsi
  wchar_t *v11; // rsi
  signed __int16 v12; // di
  __int64 result; // rax
  _BYTE v14[6]; // [rsp+20h] [rbp-88h] BYREF
  wchar_t String1[37]; // [rsp+26h] [rbp-82h] BYREF

  v2 = *((_WORD *)this + 4);
  memset_0(v14, 0, 0x4Cu);
  while ( *a2 && ((*a2 - 32) & 0xFD) == 0 )
    ++a2;
  v5 = *((_QWORD *)this + 17);
  v6 = 1;
  *((_QWORD *)this + 17) = a2;
  while ( 1 )
  {
    v8 = *a2;
    if ( !*a2 )
      break;
    if ( v8 == 34 )
    {
      *a2 = 59;
      break;
    }
    v7 = 0;
    if ( v8 <= 0x7Fu )
      v7 = v6;
    ++a2;
    v6 = v7;
  }
  CRTFRead::ReadFontName(this, (struct _textfont *)v14, v6 != 0, *((struct STATE **)this + 27));
  v9 = 0;
  if ( v2 > 0 )
  {
    while ( 1 )
    {
      v10 = (const wchar_t *)CArrayBase::Elem(this, v9);
      if ( !wcsncmp_0(String1, v10 + 3, 0x20u) )
        break;
      if ( (__int16)++v9 >= v2 )
        goto LABEL_16;
    }
    v12 = *v10;
    goto LABEL_20;
  }
LABEL_16:
  v11 = (wchar_t *)CArrayBase::ArAdd(this, 1, 0);
  if ( v11 )
  {
    v12 = v9 + 2048;
    *v11 = v12;
    wcscpy_s(v11 + 3, 0x21u, String1);
    v11[35] = 0;
    *((_BYTE *)v11 + 3) = 0;
    *((_BYTE *)v11 + 74) = 0;
    v11[36] = *((_WORD *)this + 294);
    *((_BYTE *)v11 + 2) = 1;
LABEL_20:
    CRTFRead::SelectCurrentFont(this, v12);
    goto LABEL_21;
  }
  CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 7) + 144LL));
  *((_DWORD *)this + 12) = 9;
LABEL_21:
  result = *((unsigned int *)this + 12);
  *((_QWORD *)this + 17) = v5;
  return result;
}

```

## disassembly

```asm
0x18007e2a0  mov     [rsp+arg_10], rbx
0x18007e2a5  push    rbp
0x18007e2a6  push    rsi
0x18007e2a7  push    rdi
0x18007e2a8  push    r14
0x18007e2aa  push    r15
0x18007e2ac  sub     rsp, 80h
0x18007e2b3  mov     rax, cs:__security_cookie
0x18007e2ba  xor     rax, rsp
0x18007e2bd  mov     [rsp+0A8h+var_38], rax
0x18007e2c2  movzx   ebp, word ptr [rcx+8]
0x18007e2c6  mov     rdi, rdx
0x18007e2c9  xor     edx, edx; Val
0x18007e2cb  mov     rbx, rcx
0x18007e2ce  lea     rcx, [rsp+0A8h+var_88]; void *
0x18007e2d3  lea     r8d, [rdx+4Ch]; Size
0x18007e2d7  call    memset_0
0x18007e2dc  mov     r15d, 1
0x18007e2e2  jmp     short loc_18007E2ED
0x18007e2e4  sub     al, 20h ; ' '
0x18007e2e6  test    al, 0FDh
0x18007e2e8  jnz     short loc_18007E2F3
0x18007e2ea  add     rdi, r15
0x18007e2ed  mov     al, [rdi]
0x18007e2ef  test    al, al
0x18007e2f1  jnz     short loc_18007E2E4
0x18007e2f3  mov     r14, [rbx+88h]
0x18007e2fa  mov     ecx, r15d
0x18007e2fd  mov     [rbx+88h], rdi
0x18007e304  jmp     short loc_18007E318
0x18007e306  cmp     dl, 22h ; '"'
0x18007e309  jz      short loc_18007E320
0x18007e30b  xor     eax, eax
0x18007e30d  cmp     dl, 7Fh
0x18007e310  cmovbe  eax, ecx
0x18007e313  add     rdi, r15
0x18007e316  mov     ecx, eax
0x18007e318  mov     dl, [rdi]
0x18007e31a  test    dl, dl
0x18007e31c  jnz     short loc_18007E306
0x18007e31e  jmp     short loc_18007E323
0x18007e320  mov     byte ptr [rdi], 3Bh ; ';'
0x18007e323  mov     r9, [rbx+0D8h]; struct STATE *
0x18007e32a  lea     rdx, [rsp+0A8h+var_88]; struct _textfont *
0x18007e32f  xor     r8d, r8d
0x18007e332  test    ecx, ecx
0x18007e334  mov     rcx, rbx; this
0x18007e337  setnz   r8b; int
0x18007e33b  call    ?ReadFontName@CRTFRead@@AEAAXPEAU_textfont@@HPEAUSTATE@@@Z; CRTFRead::ReadFontName(_textfont *,int,STATE *)
0x18007e340  xor     eax, eax
0x18007e342  xor     edi, edi
0x18007e344  cmp     ax, bp
0x18007e347  jge     short loc_18007E378
0x18007e349  movzx   edx, di; int
0x18007e34c  mov     rcx, rbx; this
0x18007e34f  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18007e354  mov     r8d, 20h ; ' '; MaxCount
0x18007e35a  lea     rcx, [rsp+0A8h+String1]; String1
0x18007e35f  mov     rsi, rax
0x18007e362  lea     rdx, [rax+6]; String2
0x18007e366  call    wcsncmp_0
0x18007e36b  test    eax, eax
0x18007e36d  jz      short loc_18007E3A7
0x18007e36f  add     di, r15w
0x18007e373  cmp     di, bp
0x18007e376  jl      short loc_18007E349
0x18007e378  xor     r8d, r8d; int *
0x18007e37b  mov     edx, r15d; int
0x18007e37e  mov     rcx, rbx; this
0x18007e381  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18007e386  mov     rsi, rax
0x18007e389  test    rax, rax
0x18007e38c  jnz     short loc_18007E3AC
0x18007e38e  mov     rcx, [rbx+38h]
0x18007e392  mov     rcx, [rcx+90h]; this
0x18007e399  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18007e39e  mov     dword ptr [rbx+30h], 9
0x18007e3a5  jmp     short loc_18007E3F7
0x18007e3a7  movzx   edi, word ptr [rsi]
0x18007e3aa  jmp     short loc_18007E3EC
0x18007e3ac  mov     eax, 800h
0x18007e3b1  lea     rcx, [rsi+6]; Destination
0x18007e3b5  add     di, ax
0x18007e3b8  lea     r8, [rsp+0A8h+String1]; Source
0x18007e3bd  mov     edx, 21h ; '!'; SizeInWords
0x18007e3c2  mov     [rsi], di
0x18007e3c5  call    cs:__imp_wcscpy_s
0x18007e3cc  nop     dword ptr [rax+rax+00h]
0x18007e3d1  xor     eax, eax
0x18007e3d3  mov     [rsi+46h], ax
0x18007e3d7  mov     [rsi+3], al
0x18007e3da  mov     [rsi+4Ah], al
0x18007e3dd  movzx   eax, word ptr [rbx+24Ch]
0x18007e3e4  mov     [rsi+48h], ax
0x18007e3e8  mov     [rsi+2], r15b
0x18007e3ec  movsx   edx, di; int
0x18007e3ef  mov     rcx, rbx; this
0x18007e3f2  call    ?SelectCurrentFont@CRTFRead@@AEAAPEAU_textfont@@H@Z; CRTFRead::SelectCurrentFont(int)
0x18007e3f7  mov     eax, [rbx+30h]
0x18007e3fa  mov     [rbx+88h], r14
0x18007e401  mov     rcx, [rsp+0A8h+var_38]
0x18007e406  xor     rcx, rsp; StackCookie
0x18007e409  call    __security_check_cookie
0x18007e40e  mov     rbx, [rsp+0A8h+arg_10]
0x18007e416  add     rsp, 80h
0x18007e41d  pop     r15
0x18007e41f  pop     r14
0x18007e421  pop     rdi
0x18007e422  pop     rsi
0x18007e423  pop     rbp
0x18007e424  retn
```
