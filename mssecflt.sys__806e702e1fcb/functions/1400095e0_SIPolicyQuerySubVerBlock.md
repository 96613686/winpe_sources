# SIPolicyQuerySubVerBlock

- ea: `0x1400095e0`
- end: `0x140009844`
- name: `SIPolicyQuerySubVerBlock`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009004`

## callees

- `0x140008c60`
- `0x1400095e0`
- `0x14001008c`
- `0x140011650`
- `0x140044208`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140009756`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140009756`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009727`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009727`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySubVerBlock(_WORD *a1, WCHAR *a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  char v6; // bp
  _WORD *v8; // rbx
  unsigned int v9; // r12d
  __int16 UShortFromUser; // di
  __int16 v11; // ax
  unsigned __int16 v12; // r14
  __int64 v13; // rdi
  WCHAR v14; // ax
  WCHAR *v15; // r15
  int v16; // r14d
  unsigned __int16 v17; // ax
  __int16 *v18; // rcx
  __int16 v19; // si
  unsigned __int16 v20; // di
  unsigned int v21; // eax
  __int64 v22; // rax
  UNICODE_STRING String1; // [rsp+28h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-60h] BYREF

  v6 = a3;
  v8 = a1;
  v9 = -1073741275;
  String1 = 0;
  DestinationString = 0;
  if ( (BYTE8(xmmword_14001B740) & 0x20) != 0 )
  {
    UShortFromUser = *a1;
    v11 = a1[2];
  }
  else
  {
    if ( (_BYTE)a3 )
      UShortFromUser = RtlReadUShortFromUser(a1);
    else
      UShortFromUser = *a1;
    if ( v6 )
      v11 = RtlReadUShortFromUser(v8 + 2);
    else
      v11 = v8[2];
  }
  if ( v11 || (unsigned __int16)(UShortFromUser - 8) > 0x7FF8u || (UShortFromUser & 1) != 0 )
    return v9;
LABEL_14:
  while ( *a2 == 92 )
    ++a2;
  if ( (BYTE8(xmmword_14001B740) & 0x20) != 0 || !v6 )
    v12 = *v8;
  else
    v12 = RtlReadUShortFromUser(v8);
  LOBYTE(a3) = v6;
  v13 = SIPolicyCheckVerBlock(v8, v12, a3);
  if ( !v13 )
    return v9;
  v14 = *a2;
  if ( !*a2 )
  {
    v18 = v8 + 2;
    if ( (BYTE8(xmmword_14001B740) & 0x20) != 0 )
    {
      v19 = *v18;
    }
    else
    {
      if ( v6 )
        v19 = RtlReadUShortFromUser(v18);
      else
        v19 = *v18;
      if ( v6 )
      {
        v20 = RtlReadUShortFromUser(v8 + 1);
LABEL_36:
        *a5 = v20;
        v21 = wcslen_0(v8 + 3);
        if ( v20 && (v19 || v20 >= 2u) )
          v22 = (2 * v21 + 11) & 0xFFFFFFFC;
        else
          v22 = 2LL * v21 + 6;
        v9 = 0;
        *a4 = (char *)v8 + v22;
        return v9;
      }
    }
    v20 = v8[1];
    goto LABEL_36;
  }
  v15 = a2;
  do
  {
    if ( v14 == 92 )
      break;
    v14 = *++a2;
  }
  while ( *a2 );
  v16 = (_DWORD)v8 + v12;
  while ( 1 )
  {
    LOBYTE(a3) = v6;
    if ( !SIPolicyCheckVerBlock(v13, (unsigned int)(v16 - v13), a3) )
      return v9;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v13 + 6));
    String1.Buffer = v15;
    String1.Length = (_WORD)a2 - (_WORD)v15;
    String1.MaximumLength = (_WORD)a2 - (_WORD)v15;
    if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
    {
      v8 = (_WORD *)v13;
      goto LABEL_14;
    }
    if ( (BYTE8(xmmword_14001B740) & 0x20) != 0 || !v6 )
      v17 = *(_WORD *)v13;
    else
      v17 = RtlReadUShortFromUser(v13);
    v13 += (v17 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
  }
}

```

## disassembly

```asm
0x1400095e0  push    rbx
0x1400095e2  push    rbp
0x1400095e3  push    rsi
0x1400095e4  push    rdi
0x1400095e5  push    r12
0x1400095e7  push    r13
0x1400095e9  push    r14
0x1400095eb  push    r15
0x1400095ed  sub     rsp, 58h
0x1400095f1  mov     rax, cs:__security_cookie
0x1400095f8  xor     rax, rsp
0x1400095fb  mov     [rsp+98h+var_50], rax
0x140009600  mov     r15, [rsp+98h+arg_20]
0x140009608  xorps   xmm0, xmm0
0x14000960b  mov     [rsp+98h+var_78], r15
0x140009610  xorps   xmm1, xmm1
0x140009613  xor     r15d, r15d
0x140009616  mov     r13, r9
0x140009619  test    byte ptr cs:xmmword_14001B740+8, 20h
0x140009620  mov     bpl, r8b
0x140009623  mov     rsi, rdx
0x140009626  mov     rbx, rcx
0x140009629  mov     r12d, 0C0000225h
0x14000962f  movups  xmmword ptr [rsp+98h+String1.Length], xmm0
0x140009634  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm1
0x140009639  jz      short loc_140009644
0x14000963b  movzx   edi, word ptr [rcx]
0x14000963e  movzx   eax, word ptr [rcx+4]
0x140009642  jmp     short loc_14000966A
0x140009644  test    bpl, bpl
0x140009647  jz      short loc_140009653
0x140009649  call    RtlReadUShortFromUser
0x14000964e  movzx   edi, ax
0x140009651  jmp     short loc_140009656
0x140009653  movzx   edi, word ptr [rcx]
0x140009656  test    bpl, bpl
0x140009659  jz      short loc_140009666
0x14000965b  lea     rcx, [rbx+4]
0x14000965f  call    RtlReadUShortFromUser
0x140009664  jmp     short loc_14000966A
0x140009666  movzx   eax, word ptr [rbx+4]
0x14000966a  test    ax, ax
0x14000966d  jnz     loc_140009822
0x140009673  lea     eax, [rdi-8]
0x140009676  mov     ecx, 7FF8h
0x14000967b  cmp     ax, cx
0x14000967e  ja      loc_140009822
0x140009684  test    dil, 1
0x140009688  jnz     loc_140009822
0x14000968e  mov     eax, 2
0x140009693  jmp     short loc_140009698
0x140009695  add     rsi, rax
0x140009698  cmp     word ptr [rsi], 5Ch ; '\'
0x14000969c  jz      short loc_140009695
0x14000969e  test    byte ptr cs:xmmword_14001B740+8, 20h
0x1400096a5  jnz     short loc_1400096BA
0x1400096a7  test    bpl, bpl
0x1400096aa  jz      short loc_1400096BA
0x1400096ac  mov     rcx, rbx
0x1400096af  call    RtlReadUShortFromUser
0x1400096b4  movzx   r14d, ax
0x1400096b8  jmp     short loc_1400096BE
0x1400096ba  movzx   r14d, word ptr [rbx]
0x1400096be  movzx   edx, r14w
0x1400096c2  mov     r8b, bpl
0x1400096c5  mov     rcx, rbx
0x1400096c8  call    SIPolicyCheckVerBlock
0x1400096cd  mov     rdi, rax
0x1400096d0  test    rax, rax
0x1400096d3  jz      loc_140009822
0x1400096d9  movzx   eax, word ptr [rsi]
0x1400096dc  test    ax, ax
0x1400096df  jz      loc_14000979F
0x1400096e5  mov     r15, rsi
0x1400096e8  mov     edx, 2
0x1400096ed  cmp     ax, 5Ch ; '\'
0x1400096f1  jz      short loc_1400096FE
0x1400096f3  add     rsi, rdx
0x1400096f6  movzx   eax, word ptr [rsi]
0x1400096f9  test    ax, ax
0x1400096fc  jnz     short loc_1400096ED
0x1400096fe  movzx   r14d, r14w
0x140009702  add     r14d, ebx
0x140009705  mov     edx, r14d
0x140009708  mov     r8b, bpl
0x14000970b  sub     edx, edi
0x14000970d  mov     rcx, rdi
0x140009710  call    SIPolicyCheckVerBlock
0x140009715  test    rax, rax
0x140009718  jz      loc_140009822
0x14000971e  lea     rdx, [rdi+6]; SourceString
0x140009722  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140009727  call    cs:__imp_RtlInitUnicodeString
0x14000972e  nop     dword ptr [rax+rax+00h]
0x140009733  movzx   eax, si
0x140009736  mov     [rsp+98h+String1.Buffer], r15
0x14000973b  sub     ax, r15w
0x14000973f  lea     rdx, [rsp+98h+DestinationString]; String2
0x140009744  mov     r8b, 1; CaseInSensitive
0x140009747  mov     [rsp+98h+String1.Length], ax
0x14000974c  lea     rcx, [rsp+98h+String1]; String1
0x140009751  mov     [rsp+98h+String1.MaximumLength], ax
0x140009756  call    cs:__imp_RtlCompareUnicodeString
0x14000975d  nop     dword ptr [rax+rax+00h]
0x140009762  test    eax, eax
0x140009764  jz      short loc_140009794
0x140009766  test    byte ptr cs:xmmword_14001B740+8, 20h
0x14000976d  jnz     short loc_14000977E
0x14000976f  test    bpl, bpl
0x140009772  jz      short loc_14000977E
0x140009774  mov     rcx, rdi
0x140009777  call    RtlReadUShortFromUser
0x14000977c  jmp     short loc_140009781
0x14000977e  movzx   eax, word ptr [rdi]
0x140009781  movzx   eax, ax
0x140009784  add     rax, 3
0x140009788  and     rax, 0FFFFFFFFFFFFFFFCh
0x14000978c  add     rdi, rax
0x14000978f  jmp     loc_140009705
0x140009794  mov     rbx, rdi
0x140009797  xor     r15d, r15d
0x14000979a  jmp     loc_14000968E
0x14000979f  test    byte ptr cs:xmmword_14001B740+8, 20h
0x1400097a6  lea     rcx, [rbx+4]
0x1400097aa  jz      short loc_1400097E9
0x1400097ac  movzx   esi, word ptr [rcx]
0x1400097af  movzx   edi, word ptr [rbx+2]
0x1400097b3  mov     rcx, [rsp+98h+var_78]
0x1400097b8  movzx   eax, di
0x1400097bb  mov     [rcx], rax
0x1400097be  lea     rcx, [rbx+6]; Str
0x1400097c2  call    wcslen_0
0x1400097c7  lea     ecx, ds:0Bh[rax*2]
0x1400097ce  and     ecx, 0FFFFFFFCh
0x1400097d1  test    di, di
0x1400097d4  jz      short loc_14000980E
0x1400097d6  test    si, si
0x1400097d9  jnz     short loc_1400097E5
0x1400097db  mov     edx, 2
0x1400097e0  cmp     di, dx
0x1400097e3  jb      short loc_14000980E
0x1400097e5  mov     eax, ecx
0x1400097e7  jmp     short loc_140009818
0x1400097e9  test    bpl, bpl
0x1400097ec  jz      short loc_1400097F8
0x1400097ee  call    RtlReadUShortFromUser
0x1400097f3  movzx   esi, ax
0x1400097f6  jmp     short loc_1400097FB
0x1400097f8  movzx   esi, word ptr [rcx]
0x1400097fb  test    bpl, bpl
0x1400097fe  jz      short loc_1400097AF
0x140009800  lea     rcx, [rbx+2]
0x140009804  call    RtlReadUShortFromUser
0x140009809  movzx   edi, ax
0x14000980c  jmp     short loc_1400097B3
0x14000980e  mov     eax, eax
0x140009810  lea     rax, ds:6[rax*2]
0x140009818  add     rax, rbx
0x14000981b  mov     r12d, r15d
0x14000981e  mov     [r13+0], rax
0x140009822  mov     eax, r12d
0x140009825  mov     rcx, [rsp+98h+var_50]
0x14000982a  xor     rcx, rsp; StackCookie
0x14000982d  call    __security_check_cookie
0x140009832  add     rsp, 58h
0x140009836  pop     r15
0x140009838  pop     r14
0x14000983a  pop     r13
0x14000983c  pop     r12
0x14000983e  pop     rdi
0x14000983f  pop     rsi
0x140009840  pop     rbp
0x140009841  pop     rbx
0x140009842  retn
```
