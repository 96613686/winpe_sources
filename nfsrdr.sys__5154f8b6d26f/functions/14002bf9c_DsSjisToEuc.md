# DsSjisToEuc

- ea: `0x14002bf9c`
- end: `0x14002c2d7`
- name: `DsSjisToEuc`
- size: `827`
- prototype: `__int64 __fastcall(STRING *SourceString, PSTRING DestinationString)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140004530`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x1400124ec`

## callees

- `0x140018310`
- `0x14002bf9c`
- `0x14002cb04`
- `0x14002cc34`
- `0x14003aba0`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCopyString` at `0x14002c24e`
- `ntoskrnl!RtlCopyString` at `0x14002c24e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c273`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c273`
- `ntoskrnl!ExAllocatePool2` at `0x14002c038`
- `ntoskrnl!ExAllocatePool2` at `0x14002c038`

## pseudocode

```c
__int64 __fastcall DsSjisToEuc(STRING *SourceString, PSTRING DestinationString)
{
  int v2; // ebx
  PCHAR v3; // r15
  PCHAR Buffer; // r12
  PCHAR Pool2; // rsi
  __int64 MaximumLength; // rbp
  unsigned int v9; // r11d
  unsigned int v10; // r8d
  unsigned int Length; // ecx
  __int16 v12; // dx
  _BYTE *v13; // rsi
  char v14; // r10
  char v15; // cl
  __int16 v16; // r9
  __int16 v17; // r9
  __int16 v18; // cx
  __int64 v19; // rdx
  PCHAR v20; // rax
  int Timer_high; // edx
  char v23[16]; // [rsp+40h] [rbp-58h] BYREF

  v2 = 0;
  v3 = 0;
  Buffer = SourceString->Buffer;
  Pool2 = DestinationString->Buffer;
  MaximumLength = DestinationString->MaximumLength;
  strcpy(v23, "DsSjisToEuc");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1ec26bf4b74e3e1c3379f1712f82824d_Traceguids, v23);
  if ( SourceString->Buffer == DestinationString->Buffer )
  {
    Pool2 = (PCHAR)ExAllocatePool2(258, MaximumLength, 810706510);
    v3 = Pool2;
    if ( !Pool2 )
      v2 = -1073741670;
  }
  v9 = 0;
  v10 = 0;
  while ( 1 )
  {
    if ( v2 < 0 )
      goto LABEL_48;
    Length = SourceString->Length;
    if ( v9 >= Length )
      break;
    v12 = (unsigned __int8)*Buffer++;
    if ( (v12 & 0x80u) == 0 )
    {
      if ( (_DWORD)MaximumLength )
      {
        *Pool2 = v12;
        ++v10;
        ++Pool2;
        LODWORD(MaximumLength) = MaximumLength - 1;
        goto LABEL_31;
      }
    }
    else if ( (unsigned __int8)(v12 + 95) > 0x3Eu )
    {
      if ( (unsigned __int8)(v12 + 127) > 0x1Eu && (unsigned __int8)(v12 + 32) > 0x1Cu )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sDdaZ(WPP_GLOBAL_Control->AttachedDevice, 17, v10, (unsigned int)v23, v12, v9, (__int64)SourceString);
LABEL_38:
        v2 = -1073741823;
LABEL_48:
        if ( SourceString->Buffer == DestinationString->Buffer )
        {
          if ( SourceString->Length <= DestinationString->MaximumLength )
            DestinationString->Length = SourceString->Length;
        }
        else
        {
          RtlCopyString(DestinationString, SourceString);
        }
        goto LABEL_52;
      }
      if ( ++v9 >= Length )
      {
        v2 = -1073741764;
        goto LABEL_48;
      }
      v14 = *Buffer;
      if ( (unsigned __int8)(*Buffer - 64) > 0xBCu || v14 == 127 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_sDdaZ(WPP_GLOBAL_Control->AttachedDevice, 16, v10, (unsigned int)v23, v14, v9, (__int64)SourceString);
        goto LABEL_38;
      }
      ++Buffer;
      v15 = v14;
      v16 = v12 - 64;
      if ( (unsigned __int8)v12 <= 0xDFu )
        v16 = v12;
      v17 = 2 * v16 - 225;
      if ( (unsigned __int8)v14 <= 0x9Eu )
      {
        if ( (unsigned __int8)v14 > 0x7Fu )
          v15 = v14 - 1;
      }
      else
      {
        v15 = v14 - 95;
        ++v17;
      }
      if ( (unsigned int)MaximumLength > 1 )
      {
        v18 = (v17 << 8) | (v15 - 31) & 0x7F | 0x8080;
        *Pool2 = HIBYTE(v18);
        v13 = Pool2 + 1;
        *v13 = v18;
        goto LABEL_14;
      }
    }
    else if ( (unsigned int)MaximumLength > 1 )
    {
      *Pool2 = -114;
      v13 = Pool2 + 1;
      *v13 = v12;
LABEL_14:
      Pool2 = v13 + 1;
      v10 += 2;
      LODWORD(MaximumLength) = MaximumLength - 2;
      goto LABEL_31;
    }
    v2 = -2147483643;
LABEL_31:
    ++v9;
  }
  if ( v10 > DestinationString->MaximumLength )
  {
    v2 = -2147483643;
    goto LABEL_48;
  }
  DestinationString->Length = v10;
  if ( v3 )
    memmove(DestinationString->Buffer, v3, (unsigned __int16)v10);
  v19 = DestinationString->Length;
  if ( v19 + 1 <= (unsigned __int64)DestinationString->MaximumLength )
  {
    v20 = DestinationString->Buffer;
    if ( v20[v19] )
      v20[v19] = 0;
  }
LABEL_52:
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 8) != 0 )
      WPP_SF_sDaZaZ(
        WPP_GLOBAL_Control->AttachedDevice,
        Timer_high,
        v10,
        (unsigned int)v23,
        v2,
        (__int64)SourceString,
        (__int64)DestinationString);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002bf9c  mov     [rsp+arg_10], rbx
0x14002bfa1  push    rbp
0x14002bfa2  push    rsi
0x14002bfa3  push    rdi
0x14002bfa4  push    r12
0x14002bfa6  push    r13
0x14002bfa8  push    r14
0x14002bfaa  push    r15
0x14002bfac  sub     rsp, 60h
0x14002bfb0  mov     rax, cs:__security_cookie
0x14002bfb7  xor     rax, rsp
0x14002bfba  mov     [rsp+98h+var_48], rax
0x14002bfbf  movsd   xmm0, qword ptr cs:aDssjistoeuc; "DsSjisToEuc"
0x14002bfc7  xor     ebx, ebx
0x14002bfc9  mov     eax, dword ptr cs:aDssjistoeuc+8; "Euc"
0x14002bfcf  xor     r15d, r15d
0x14002bfd2  mov     r12, [rcx+8]
0x14002bfd6  mov     rdi, rdx
0x14002bfd9  mov     rsi, [rdx+8]
0x14002bfdd  mov     r14, rcx
0x14002bfe0  movzx   ebp, word ptr [rdx+2]
0x14002bfe4  movsd   qword ptr [rsp+98h+var_58], xmm0
0x14002bfea  mov     dword ptr [rsp+98h+var_58+8], eax
0x14002bfee  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bff5  lea     rax, WPP_GLOBAL_Control
0x14002bffc  cmp     rcx, rax
0x14002bfff  jz      short loc_14002C020
0x14002c001  mov     eax, [rcx+2Ch]
0x14002c004  test    al, 8
0x14002c006  jz      short loc_14002C020
0x14002c008  mov     rcx, [rcx+18h]
0x14002c00c  lea     edx, [rbx+0Fh]
0x14002c00f  lea     r9, [rsp+98h+var_58]
0x14002c014  lea     r8, WPP_1ec26bf4b74e3e1c3379f1712f82824d_Traceguids
0x14002c01b  call    WPP_SF_s
0x14002c020  mov     rax, [rdi+8]
0x14002c024  cmp     [r14+8], rax
0x14002c028  jnz     short loc_14002C055
0x14002c02a  mov     rdx, rbp
0x14002c02d  mov     ecx, 102h
0x14002c032  mov     r8d, 3052664Eh
0x14002c038  call    cs:__imp_ExAllocatePool2
0x14002c03f  nop     dword ptr [rax+rax+00h]
0x14002c044  mov     rsi, rax
0x14002c047  mov     r15, rax
0x14002c04a  test    rsi, rsi
0x14002c04d  mov     eax, 0C000009Ah
0x14002c052  cmovz   ebx, eax
0x14002c055  xor     r11d, r11d
0x14002c058  xor     r8d, r8d
0x14002c05b  lea     r13d, [r11+1]
0x14002c05f  test    ebx, ebx
0x14002c061  js      loc_14002C237
0x14002c067  movzx   ecx, word ptr [r14]
0x14002c06b  cmp     r11d, ecx
0x14002c06e  jnb     loc_14002C1E9
0x14002c074  movzx   edx, byte ptr [r12]
0x14002c079  add     r12, r13
0x14002c07c  test    dl, dl
0x14002c07e  jns     loc_14002C14F
0x14002c084  lea     eax, [rdx+5Fh]
0x14002c087  cmp     al, 3Eh ; '>'
0x14002c089  ja      short loc_14002C0AB
0x14002c08b  cmp     ebp, r13d
0x14002c08e  jbe     loc_14002C15F
0x14002c094  mov     byte ptr [rsi], 8Eh
0x14002c097  add     rsi, r13
0x14002c09a  mov     [rsi], dl
0x14002c09c  add     rsi, r13
0x14002c09f  add     r8d, 2
0x14002c0a3  add     ebp, 0FFFFFFFEh
0x14002c0a6  jmp     loc_14002C164
0x14002c0ab  lea     eax, [rdx+7Fh]
0x14002c0ae  cmp     al, 1Eh
0x14002c0b0  jbe     short loc_14002C0BD
0x14002c0b2  lea     eax, [rdx+20h]
0x14002c0b5  cmp     al, 1Ch
0x14002c0b7  ja      loc_14002C16C
0x14002c0bd  inc     r11d
0x14002c0c0  cmp     r11d, ecx
0x14002c0c3  jnb     loc_14002C1E2
0x14002c0c9  movzx   r10d, byte ptr [r12]
0x14002c0ce  lea     eax, [r10-40h]
0x14002c0d2  cmp     al, 0BCh
0x14002c0d4  ja      loc_14002C19E
0x14002c0da  cmp     r10b, 7Fh
0x14002c0de  jz      loc_14002C19E
0x14002c0e4  movzx   eax, dx
0x14002c0e7  add     r12, r13
0x14002c0ea  cmp     dl, 0DFh
0x14002c0ed  movzx   ecx, r10w
0x14002c0f1  lea     r9d, [rax-40h]
0x14002c0f5  mov     eax, 0E1h
0x14002c0fa  cmovbe  r9w, dx
0x14002c0ff  add     r9w, r9w
0x14002c103  sub     r9w, ax
0x14002c107  cmp     r10b, 9Eh
0x14002c10b  jbe     short loc_14002C117
0x14002c10d  sub     cx, 5Fh ; '_'
0x14002c111  add     r9w, r13w
0x14002c115  jmp     short loc_14002C121
0x14002c117  cmp     r10b, 7Fh
0x14002c11b  jbe     short loc_14002C121
0x14002c11d  sub     cx, r13w
0x14002c121  cmp     ebp, r13d
0x14002c124  jbe     short loc_14002C15F
0x14002c126  sub     cx, 1Fh
0x14002c12a  shl     r9w, 8
0x14002c12f  and     cx, 7Fh
0x14002c133  or      cx, r9w
0x14002c137  or      cx, 8080h
0x14002c13c  movzx   eax, cx
0x14002c13f  shr     ax, 8
0x14002c143  mov     [rsi], al
0x14002c145  add     rsi, r13
0x14002c148  mov     [rsi], cl
0x14002c14a  jmp     loc_14002C09C
0x14002c14f  test    ebp, ebp
0x14002c151  jz      short loc_14002C15F
0x14002c153  mov     [rsi], dl
0x14002c155  add     r8d, r13d
0x14002c158  add     rsi, r13
0x14002c15b  dec     ebp
0x14002c15d  jmp     short loc_14002C164
0x14002c15f  mov     ebx, 80000005h
0x14002c164  add     r11d, r13d
0x14002c167  jmp     loc_14002C05F
0x14002c16c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c173  lea     rsi, WPP_GLOBAL_Control
0x14002c17a  cmp     rcx, rsi
0x14002c17d  jz      short loc_14002C1DB
0x14002c17f  mov     eax, [rcx+2Ch]
0x14002c182  test    r13b, al
0x14002c185  jz      short loc_14002C1DB
0x14002c187  mov     eax, edx
0x14002c189  mov     [rsp+98h+var_68], r14
0x14002c18e  mov     dword ptr [rsp+98h+var_70], r11d
0x14002c193  mov     edx, 11h
0x14002c198  mov     [rsp+98h+var_78], eax
0x14002c19c  jmp     short loc_14002C1CD
0x14002c19e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c1a5  lea     rsi, WPP_GLOBAL_Control
0x14002c1ac  cmp     rcx, rsi
0x14002c1af  jz      short loc_14002C1DB
0x14002c1b1  mov     eax, [rcx+2Ch]
0x14002c1b4  test    r13b, al
0x14002c1b7  jz      short loc_14002C1DB
0x14002c1b9  mov     [rsp+98h+var_68], r14
0x14002c1be  mov     edx, 10h
0x14002c1c3  mov     dword ptr [rsp+98h+var_70], r11d
0x14002c1c8  mov     [rsp+98h+var_78], r10d
0x14002c1cd  mov     rcx, [rcx+18h]
0x14002c1d1  lea     r9, [rsp+98h+var_58]
0x14002c1d6  call    WPP_SF_sDdaZ
0x14002c1db  mov     ebx, 0C0000001h
0x14002c1e0  jmp     short loc_14002C23E
0x14002c1e2  mov     ebx, 0C000003Ch
0x14002c1e7  jmp     short loc_14002C237
0x14002c1e9  movzx   eax, word ptr [rdi+2]
0x14002c1ed  cmp     r8d, eax
0x14002c1f0  ja      short loc_14002C232
0x14002c1f2  mov     [rdi], r8w
0x14002c1f6  test    r15, r15
0x14002c1f9  jz      short loc_14002C20B
0x14002c1fb  mov     rcx, [rdi+8]; void *
0x14002c1ff  mov     rdx, r15; Src
0x14002c202  movzx   r8d, r8w; Size
0x14002c206  call    memmove
0x14002c20b  movzx   edx, word ptr [rdi]
0x14002c20e  movzx   eax, word ptr [rdi+2]
0x14002c212  lea     rcx, [rdx+1]
0x14002c216  cmp     rcx, rax
0x14002c219  ja      short loc_14002C229
0x14002c21b  mov     rax, [rdi+8]
0x14002c21f  cmp     byte ptr [rdx+rax], 0
0x14002c223  jz      short loc_14002C229
0x14002c225  mov     byte ptr [rdx+rax], 0
0x14002c229  lea     rsi, WPP_GLOBAL_Control
0x14002c230  jmp     short loc_14002C269
0x14002c232  mov     ebx, 80000005h
0x14002c237  lea     rsi, WPP_GLOBAL_Control
0x14002c23e  mov     rax, [rdi+8]
0x14002c242  cmp     [r14+8], rax
0x14002c246  jz      short loc_14002C25C
0x14002c248  mov     rdx, r14; SourceString
0x14002c24b  mov     rcx, rdi; DestinationString
0x14002c24e  call    cs:__imp_RtlCopyString
0x14002c255  nop     dword ptr [rax+rax+00h]
0x14002c25a  jmp     short loc_14002C269
0x14002c25c  movzx   eax, word ptr [r14]
0x14002c260  cmp     ax, [rdi+2]
0x14002c264  ja      short loc_14002C269
0x14002c266  mov     [rdi], ax
0x14002c269  test    r15, r15
0x14002c26c  jz      short loc_14002C27F
0x14002c26e  xor     edx, edx; Tag
0x14002c270  mov     rcx, r15; P
0x14002c273  call    cs:__imp_ExFreePoolWithTag
0x14002c27a  nop     dword ptr [rax+rax+00h]
0x14002c27f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c286  cmp     rcx, rsi
0x14002c289  jz      short loc_14002C2AF
0x14002c28b  mov     edx, [rcx+2Ch]
0x14002c28e  test    dl, 8
0x14002c291  jz      short loc_14002C2AF
0x14002c293  mov     rcx, [rcx+18h]
0x14002c297  lea     r9, [rsp+98h+var_58]
0x14002c29c  mov     [rsp+98h+var_68], rdi
0x14002c2a1  mov     [rsp+98h+var_70], r14
0x14002c2a6  mov     [rsp+98h+var_78], ebx
0x14002c2aa  call    WPP_SF_sDaZaZ
0x14002c2af  mov     eax, ebx
0x14002c2b1  mov     rcx, [rsp+98h+var_48]
0x14002c2b6  xor     rcx, rsp; StackCookie
0x14002c2b9  call    __security_check_cookie
0x14002c2be  mov     rbx, [rsp+98h+arg_10]
0x14002c2c6  add     rsp, 60h
0x14002c2ca  pop     r15
0x14002c2cc  pop     r14
0x14002c2ce  pop     r13
0x14002c2d0  pop     r12
0x14002c2d2  pop     rdi
0x14002c2d3  pop     rsi
0x14002c2d4  pop     rbp
0x14002c2d5  retn
```
