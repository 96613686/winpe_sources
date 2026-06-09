# VctBuildTransportAddress

- ea: `0x14008df10`
- end: `0x14008e361`
- name: `VctBuildTransportAddress`
- size: `1105`
- prototype: `__int64 __fastcall(__int64, unsigned int, const UNICODE_STRING *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140094bf0`

## callees

- `0x140059dc0`
- `0x140059f00`
- `0x14008df10`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14008df41`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14008df41`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x14008dfb8`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x14008dfb8`

## pseudocode

```c
__int64 __fastcall VctBuildTransportAddress(__int64 a1, unsigned int a2, const UNICODE_STRING *a3, _DWORD *a4)
{
  ULONG v8; // eax
  unsigned __int16 v9; // si
  int v10; // edx
  int Length; // ecx
  USHORT v12; // dx
  PCHAR Buffer; // r13
  int v14; // r9d
  int v15; // r15d
  PCHAR v16; // r10
  int v17; // r11d
  char v18; // bl
  char v19; // cl
  char v20; // al
  unsigned __int64 v21; // r8
  __int64 v22; // rbp
  __int64 v23; // rax
  char v24; // r15
  int v25; // ecx
  __int64 v26; // rcx
  unsigned __int16 *v27; // r12
  __int64 v28; // rcx
  int v29; // edx
  const char *v30; // rax
  char *v31; // rsi
  size_t v32; // r8
  _OWORD *v33; // rbx
  unsigned __int16 v34; // ax
  unsigned __int16 v35; // dx
  __int64 v36; // rax
  __int64 v37; // rdx
  int v39; // [rsp+20h] [rbp-68h] BYREF
  struct _STRING DestinationString; // [rsp+28h] [rbp-60h] BYREF
  __int128 v41; // [rsp+38h] [rbp-50h] BYREF

  DestinationString = 0;
  v8 = RtlxUnicodeStringToOemSize(a3);
  v9 = 18;
  v10 = 18;
  if ( v8 > 0x10 )
    v10 = v8 + 2;
  Length = a3->Length;
  if ( a2 < Length + v10 + 2 * (v10 + 316) )
    return 2147483653LL;
  if ( (unsigned __int16)Length > 0xFFu )
    return 3221225662LL;
  *(_WORD *)(a1 + 24) = 2;
  DestinationString.Length = a3->Length;
  DestinationString.MaximumLength = DestinationString.Length + 1;
  DestinationString.Buffer = (PCHAR)(a1 + 26);
  if ( RtlUpcaseUnicodeStringToOemString(&DestinationString, a3, 0) < 0 )
  {
    v12 = 0;
  }
  else
  {
    v12 = DestinationString.Length;
    if ( DestinationString.Length >= 0x10u )
      goto LABEL_8;
  }
  memmove(&DestinationString.Buffer[v12], "                ", 16LL - v12);
  v12 = 16;
  DestinationString.Length = 16;
LABEL_8:
  Buffer = DestinationString.Buffer;
  v39 = 0;
  if ( v12 == 16 )
  {
    v14 = 0;
    *(_QWORD *)&v41 = (char *)&v39 + 3;
    v15 = 0;
    v16 = DestinationString.Buffer;
    while ( v14 < 16 )
    {
      v17 = 0;
      v18 = 0;
      v19 = 0;
      while ( 1 )
      {
        v20 = 0;
        if ( v17 >= 4 )
          break;
        v21 = *v16;
        if ( (unsigned __int8)(v21 - 48) > 9u )
        {
          if ( (unsigned __int8)v21 > 0x2Eu )
            goto LABEL_25;
          v22 = 0x400100000001LL;
          if ( !_bittest64(&v22, v21) )
            goto LABEL_25;
          v23 = v41;
          ++v15;
          *(_BYTE *)v41 = v19;
          *(_QWORD *)&v41 = v23 - 1;
          if ( (_BYTE)v21 == 46 )
          {
            ++v16;
            v20 = 1;
            ++v14;
            break;
          }
          v20 = 0;
          if ( (_BYTE)v21 == 32 || !(_BYTE)v21 )
            break;
        }
        else
        {
          v18 = 1;
          v19 = v21 + 10 * v19 - 48;
        }
        ++v16;
        ++v14;
        ++v17;
      }
      if ( !v18 )
        goto LABEL_25;
      if ( v15 == 4 )
      {
        while ( v14 < 16 )
        {
          if ( (*v16 & 0xDF) != 0 )
            goto LABEL_25;
          ++v14;
          ++v16;
        }
        break;
      }
      if ( !v20 )
        goto LABEL_25;
    }
    v25 = v39;
    if ( (unsigned int)(v39 - 1) > 0xFFFFFFFD )
      return 3221225991LL;
    v24 = 1;
  }
  else
  {
LABEL_25:
    v24 = 0;
    v25 = 0;
  }
  *a4 = v25;
  if ( v12 > 0x10u )
    v9 = v12 + 2;
  *(_WORD *)(a1 + 6) = 22;
  v26 = (unsigned __int16)(v9 + 16);
  v27 = (unsigned __int16 *)(v26 + a1 + 8);
  *(_WORD *)(a1 + 4) = v26;
  *(_DWORD *)a1 = 3;
  if ( v24 )
  {
    v30 = "*SMBSERVER      ";
  }
  else
  {
    v28 = 0;
    v41 = *(_OWORD *)Buffer;
    while ( 1 )
    {
      if ( *((_BYTE *)&v41 + v28) == 46 )
        goto LABEL_36;
      v29 = v28 + 1;
      if ( *((_BYTE *)&v41 + (unsigned int)(v28 + 1)) == 46 )
        break;
      v29 = v28 + 2;
      if ( *((_BYTE *)&v41 + (unsigned int)(v28 + 2)) == 46 )
        break;
      v29 = v28 + 3;
      if ( *((_BYTE *)&v41 + (unsigned int)(v28 + 3)) == 46 )
        break;
      v28 = (unsigned int)(v28 + 4);
      if ( (unsigned int)v28 >= 0x10 )
        goto LABEL_35;
    }
    LODWORD(v28) = v29;
LABEL_35:
    if ( (_DWORD)v28 != 16 )
    {
LABEL_36:
      memmove((char *)&v41 + (unsigned int)v28, "                ", (unsigned int)(16 - v28));
      goto LABEL_37;
    }
    HIBYTE(v41) = 32;
LABEL_37:
    v30 = (const char *)&v41;
  }
  *(_OWORD *)(a1 + 8) = *(_OWORD *)v30;
  *v27 = v9;
  v27[1] = 17;
  memmove(v27 + 2, (const void *)(a1 + 24), v9);
  v31 = (char *)v27 + v9 + 4;
  v32 = 512;
  *(_DWORD *)v31 = 1573448;
  v33 = v31 + 42;
  *(_QWORD *)(v31 + 18) = v31 + 42;
  *((_WORD *)v31 + 2) = 2;
  *(_DWORD *)(v31 + 6) = 2;
  *(_DWORD *)(v31 + 10) = 2228256;
  *((_WORD *)v31 + 13) = a3->Length;
  *((_WORD *)v31 + 14) = 512;
  *(_QWORD *)(v31 + 34) = v31 + 76;
  if ( a3->Length < 0x200u )
    v32 = a3->Length;
  memmove(v31 + 76, a3->Buffer, v32);
  if ( v24 )
  {
    *v33 = *(_OWORD *)L"*SMBSERVER      ";
  }
  else
  {
    v34 = *((_WORD *)v31 + 5);
    *v33 = *(_OWORD *)L"                ";
    *(_OWORD *)(v31 + 58) = *(_OWORD *)L"        ";
    v35 = a3->Length;
    if ( v34 <= a3->Length )
      v35 = v34;
    memmove(v31 + 42, a3->Buffer, v35);
    v36 = 0;
    while ( 1 )
    {
      if ( *(_WORD *)&v31[2 * v36 + 42] == 46 )
        goto LABEL_50;
      v37 = (unsigned int)(v36 + 1);
      if ( *(_WORD *)&v31[2 * v37 + 42] == 46 )
        break;
      v37 = (unsigned int)(v36 + 2);
      if ( *(_WORD *)&v31[2 * v37 + 42] == 46 )
        break;
      v37 = (unsigned int)(v36 + 3);
      if ( *(_WORD *)&v31[2 * v37 + 42] == 46 )
        break;
      v36 = (unsigned int)(v36 + 4);
      if ( (unsigned int)v36 >= 0x10 )
        goto LABEL_49;
    }
    LODWORD(v36) = v37;
LABEL_49:
    if ( (_DWORD)v36 != 16 )
    {
LABEL_50:
      memmove(&v31[2 * (unsigned int)v36 + 42], L"                ", 2LL * (unsigned int)(16 - v36));
      return 0;
    }
    *((_WORD *)v31 + 36) = 32;
  }
  return 0;
}

```

## disassembly

```asm
0x14008df10  push    rbx
0x14008df12  push    rsi
0x14008df13  push    rdi
0x14008df14  push    r12
0x14008df16  push    r14
0x14008df18  sub     rsp, 60h
0x14008df1c  mov     rax, cs:__security_cookie
0x14008df23  xor     rax, rsp
0x14008df26  mov     [rsp+88h+var_40], rax
0x14008df2b  mov     r14, rcx
0x14008df2e  xorps   xmm0, xmm0
0x14008df31  mov     rcx, r8; UnicodeString
0x14008df34  mov     r12, r9
0x14008df37  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14008df3c  mov     rdi, r8
0x14008df3f  mov     ebx, edx
0x14008df41  call    cs:__imp_RtlxUnicodeStringToOemSize
0x14008df48  nop     dword ptr [rax+rax+00h]
0x14008df4d  mov     esi, 12h
0x14008df52  mov     edx, esi
0x14008df54  cmp     eax, 10h
0x14008df57  jbe     short loc_14008DF5C
0x14008df59  lea     edx, [rax+2]
0x14008df5c  movzx   ecx, word ptr [rdi]
0x14008df5f  lea     eax, [rdx+13Ch]
0x14008df65  lea     eax, [rdx+rax*2]
0x14008df68  add     eax, ecx
0x14008df6a  cmp     ebx, eax
0x14008df6c  jb      loc_14008E301
0x14008df72  mov     eax, 0FFh
0x14008df77  cmp     cx, ax
0x14008df7a  ja      loc_14008E2D1
0x14008df80  mov     word ptr [r14+18h], 2
0x14008df87  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14008df8c  movzx   eax, word ptr [rdi]
0x14008df8f  xor     r8d, r8d; AllocateDestinationString
0x14008df92  mov     [rsp+88h+DestinationString.Length], ax
0x14008df97  mov     rdx, rdi; SourceString
0x14008df9a  inc     ax
0x14008df9d  mov     [rsp+88h+arg_8], rbp
0x14008dfa5  mov     [rsp+88h+DestinationString.MaximumLength], ax
0x14008dfaa  lea     rax, [r14+1Ah]
0x14008dfae  mov     [rsp+88h+DestinationString.Buffer], rax
0x14008dfb3  mov     [rsp+88h+var_30], r13
0x14008dfb8  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x14008dfbf  nop     dword ptr [rax+rax+00h]
0x14008dfc4  mov     ebp, 10h
0x14008dfc9  test    eax, eax
0x14008dfcb  js      loc_14008E325
0x14008dfd1  movzx   edx, [rsp+88h+DestinationString.Length]
0x14008dfd6  cmp     dx, bp
0x14008dfd9  jnb     short loc_14008DFFD
0x14008dfdb  movzx   ecx, dx
0x14008dfde  mov     r8, rbp
0x14008dfe1  sub     r8, rcx; Size
0x14008dfe4  lea     rdx, asc_140062A40; "                "
0x14008dfeb  add     rcx, [rsp+88h+DestinationString.Buffer]; void *
0x14008dff0  call    memmove
0x14008dff5  movzx   edx, bp
0x14008dff8  mov     [rsp+88h+DestinationString.Length], dx
0x14008dffd  mov     r13, [rsp+88h+DestinationString.Buffer]
0x14008e002  mov     [rsp+88h+var_38], r15
0x14008e007  mov     [rsp+88h+var_68], 0
0x14008e00f  cmp     dx, bp
0x14008e012  jnz     loc_14008E0D3
0x14008e018  xor     r9d, r9d
0x14008e01b  lea     rax, [rsp+88h+var_68+3]
0x14008e020  mov     qword ptr [rsp+88h+var_50], rax
0x14008e025  xor     r15d, r15d
0x14008e028  mov     r10, r13
0x14008e02b  cmp     r9d, 10h
0x14008e02f  jge     loc_14008E30F
0x14008e035  xor     r11d, r11d
0x14008e038  xor     bl, bl
0x14008e03a  xor     cl, cl
0x14008e03c  xor     al, al
0x14008e03e  cmp     r11d, 4
0x14008e042  jge     short loc_14008E0B1
0x14008e044  movsx   r8, byte ptr [r10]
0x14008e048  lea     eax, [r8-30h]
0x14008e04c  cmp     al, 9
0x14008e04e  ja      short loc_14008E06D
0x14008e050  movzx   eax, cl
0x14008e053  mov     bl, 1
0x14008e055  shl     al, 2
0x14008e058  add     cl, al
0x14008e05a  add     cl, cl
0x14008e05c  sub     cl, 30h ; '0'
0x14008e05f  add     cl, r8b
0x14008e062  inc     r10
0x14008e065  inc     r9d
0x14008e068  inc     r11d
0x14008e06b  jmp     short loc_14008E03C
0x14008e06d  cmp     r8b, 2Eh ; '.'
0x14008e071  ja      short loc_14008E0D3
0x14008e073  mov     rbp, 400100000001h
0x14008e07d  bt      rbp, r8
0x14008e081  mov     ebp, 10h
0x14008e086  jnb     short loc_14008E0D3
0x14008e088  mov     rax, qword ptr [rsp+88h+var_50]
0x14008e08d  inc     r15d
0x14008e090  mov     [rax], cl
0x14008e092  dec     rax
0x14008e095  mov     qword ptr [rsp+88h+var_50], rax
0x14008e09a  cmp     r8b, 2Eh ; '.'
0x14008e09e  jz      loc_14008E32C
0x14008e0a4  xor     al, al
0x14008e0a6  cmp     r8b, 20h ; ' '
0x14008e0aa  jz      short loc_14008E0B1
0x14008e0ac  test    r8b, r8b
0x14008e0af  jnz     short loc_14008E062
0x14008e0b1  test    bl, bl
0x14008e0b3  jz      short loc_14008E0D3
0x14008e0b5  cmp     r15d, 4
0x14008e0b9  jnz     loc_14008E339
0x14008e0bf  cmp     r9d, 10h
0x14008e0c3  jge     loc_14008E30F
0x14008e0c9  test    byte ptr [r10], 0DFh
0x14008e0cd  jz      loc_14008E346
0x14008e0d3  xor     r15b, r15b
0x14008e0d6  xor     ecx, ecx
0x14008e0d8  mov     [r12], ecx
0x14008e0dc  cmp     dx, 10h
0x14008e0e0  ja      loc_14008E359
0x14008e0e6  lea     eax, [rsi+10h]
0x14008e0e9  mov     word ptr [r14+6], 16h
0x14008e0f0  movzx   ecx, ax
0x14008e0f3  lea     r12, [r14+8]
0x14008e0f7  add     r12, rcx
0x14008e0fa  mov     [r14+4], cx
0x14008e0ff  mov     dword ptr [r14], 3
0x14008e106  test    r15b, r15b
0x14008e109  jnz     loc_14008E2E2
0x14008e10f  movups  xmm0, xmmword ptr [r13+0]
0x14008e114  xor     ecx, ecx
0x14008e116  movups  [rsp+88h+var_50], xmm0
0x14008e11b  cmp     byte ptr [rsp+rcx+88h+var_50], 2Eh ; '.'
0x14008e120  jz      short loc_14008E15D
0x14008e122  lea     edx, [rcx+1]
0x14008e125  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e12a  jz      loc_14008E308
0x14008e130  lea     edx, [rcx+2]
0x14008e133  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e138  jz      loc_14008E308
0x14008e13e  lea     edx, [rcx+3]
0x14008e141  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e146  jz      loc_14008E308
0x14008e14c  add     ecx, 4
0x14008e14f  cmp     ecx, 10h
0x14008e152  jb      short loc_14008E11B
0x14008e154  cmp     ecx, 10h
0x14008e157  jz      loc_14008E2D8
0x14008e15d  mov     eax, ecx
0x14008e15f  lea     rdx, asc_140062A40; "                "
0x14008e166  mov     r8d, ebp
0x14008e169  sub     r8d, ecx; Size
0x14008e16c  lea     rcx, [rsp+88h+var_50]
0x14008e171  add     rcx, rax; void *
0x14008e174  call    memmove
0x14008e179  lea     rax, [rsp+88h+var_50]
0x14008e17e  movups  xmm0, xmmword ptr [rax]
0x14008e181  movzx   ebx, si
0x14008e184  lea     rcx, [r12+4]; void *
0x14008e189  mov     r8d, ebx; Size
0x14008e18c  lea     rdx, [r14+18h]; Src
0x14008e190  movups  xmmword ptr [r14+8], xmm0
0x14008e195  mov     [r12], si
0x14008e19a  mov     word ptr [r12+2], 11h
0x14008e1a2  call    memmove
0x14008e1a7  mov     eax, 2
0x14008e1ac  lea     rsi, [rbx+4]
0x14008e1b0  add     rsi, r12
0x14008e1b3  mov     r8d, 200h; Size
0x14008e1b9  mov     r14d, 20h ; ' '
0x14008e1bf  mov     dword ptr [rsi], 180248h
0x14008e1c5  lea     rbx, [rsi+2Ah]
0x14008e1c9  mov     [rsi+12h], rbx
0x14008e1cd  lea     rcx, [rsi+4Ch]; void *
0x14008e1d1  mov     [rsi+4], ax
0x14008e1d5  mov     [rsi+6], eax
0x14008e1d8  mov     dword ptr [rsi+0Ah], 220020h
0x14008e1df  movzx   eax, word ptr [rdi]
0x14008e1e2  mov     [rsi+1Ah], ax
0x14008e1e6  mov     [rsi+1Ch], r8w
0x14008e1eb  mov     [rsi+22h], rcx
0x14008e1ef  movzx   eax, word ptr [rdi]
0x14008e1f2  cmp     r8w, ax
0x14008e1f6  ja      loc_14008E2C5
0x14008e1fc  mov     rdx, [rdi+8]; Src
0x14008e200  call    memmove
0x14008e205  test    r15b, r15b
0x14008e208  jnz     loc_14008E2F5
0x14008e20e  movups  xmm0, xmmword ptr cs:asc_140062A18; "                "
0x14008e215  movzx   eax, word ptr [rsi+0Ah]
0x14008e219  mov     rcx, rbx; void *
0x14008e21c  movups  xmmword ptr [rbx], xmm0
0x14008e21f  movups  xmm1, xmmword ptr cs:asc_140062A18+10h; "        "
0x14008e226  movups  xmmword ptr [rbx+10h], xmm1
0x14008e22a  movzx   edx, word ptr [rdi]
0x14008e22d  cmp     ax, dx
0x14008e230  cmovbe  dx, ax
0x14008e234  movzx   r8d, dx; Size
0x14008e238  mov     rdx, [rdi+8]; Src
0x14008e23c  call    memmove
0x14008e241  xor     eax, eax
0x14008e243  cmp     word ptr [rsi+rax*2+2Ah], 2Eh ; '.'
0x14008e249  jz      short loc_14008E279
0x14008e24b  lea     edx, [rax+1]
0x14008e24e  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e254  jz      short loc_14008E2CD
0x14008e256  lea     edx, [rax+2]
0x14008e259  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e25f  jz      short loc_14008E2CD
0x14008e261  lea     edx, [rax+3]
0x14008e264  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e26a  jz      short loc_14008E2CD
0x14008e26c  add     eax, 4
0x14008e26f  cmp     eax, 10h
0x14008e272  jb      short loc_14008E243
0x14008e274  cmp     eax, 10h
0x14008e277  jz      short loc_14008E2EE
0x14008e279  mov     ecx, eax
0x14008e27b  lea     rdx, asc_140062A18; "                "
0x14008e282  add     rcx, 15h
0x14008e286  sub     ebp, eax
0x14008e288  mov     r8d, ebp
0x14008e28b  add     r8, r8; Size
0x14008e28e  lea     rcx, [rsi+rcx*2]; void *
0x14008e292  call    memmove
0x14008e297  xor     eax, eax
0x14008e299  mov     r15, [rsp+88h+var_38]
0x14008e29e  mov     rbp, [rsp+88h+arg_8]
0x14008e2a6  mov     r13, [rsp+88h+var_30]
0x14008e2ab  mov     rcx, [rsp+88h+var_40]
0x14008e2b0  xor     rcx, rsp; StackCookie
0x14008e2b3  call    __security_check_cookie
0x14008e2b8  add     rsp, 60h
0x14008e2bc  pop     r14
0x14008e2be  pop     r12
0x14008e2c0  pop     rdi
0x14008e2c1  pop     rsi
0x14008e2c2  pop     rbx
0x14008e2c3  retn
0x14008e2c5  mov     r8, rax
0x14008e2c8  jmp     loc_14008E1FC
0x14008e2cd  mov     eax, edx
0x14008e2cf  jmp     short loc_14008E274
0x14008e2d1  mov     eax, 0C00000BEh
0x14008e2d6  jmp     short loc_14008E2AB
0x14008e2d8  mov     byte ptr [rsp+88h+var_50+0Fh], 20h ; ' '
0x14008e2dd  jmp     loc_14008E179
0x14008e2e2  lea     rax, aSmbserver_0; "*SMBSERVER      "
0x14008e2e9  jmp     loc_14008E17E
0x14008e2ee  mov     [rsi+48h], r14w
0x14008e2f3  jmp     short loc_14008E297
0x14008e2f5  movups  xmm0, xmmword ptr cs:aSmbserver; "*SMBSERVER      "
0x14008e2fc  movups  xmmword ptr [rbx], xmm0
0x14008e2ff  jmp     short loc_14008E297
0x14008e301  mov     eax, 80000005h
0x14008e306  jmp     short loc_14008E2AB
0x14008e308  mov     ecx, edx
0x14008e30a  jmp     loc_14008E154
0x14008e30f  mov     ecx, [rsp+88h+var_68]
0x14008e313  lea     eax, [rcx-1]
0x14008e316  cmp     eax, 0FFFFFFFDh
0x14008e319  jbe     short loc_14008E351
0x14008e31b  mov     eax, 0C0000207h
0x14008e320  jmp     loc_14008E299
0x14008e325  xor     edx, edx
0x14008e327  jmp     loc_14008DFDB
0x14008e32c  inc     r10
0x14008e32f  mov     al, 1
0x14008e331  inc     r9d
0x14008e334  jmp     loc_14008E0B1
0x14008e339  test    al, al
0x14008e33b  jnz     loc_14008E02B
0x14008e341  jmp     loc_14008E0D3
0x14008e346  inc     r9d
0x14008e349  inc     r10
0x14008e34c  jmp     loc_14008E0BF
0x14008e351  mov     r15b, 1
0x14008e354  jmp     loc_14008E0D8
0x14008e359  lea     esi, [rdx+2]
0x14008e35c  jmp     loc_14008E0E6
```
