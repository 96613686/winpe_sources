# VctBuildTransportAddress

- ea: `0x14008df60`
- end: `0x14008e3b1`
- name: `VctBuildTransportAddress`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140094c40`

## callees

- `0x140059dc0`
- `0x140059f00`
- `0x14008df60`

## import_xrefs

- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14008df91`
- `ntoskrnl!RtlxUnicodeStringToOemSize` at `0x14008df91`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x14008e008`
- `ntoskrnl!RtlUpcaseUnicodeStringToOemString` at `0x14008e008`

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
0x14008df60  push    rbx
0x14008df62  push    rsi
0x14008df63  push    rdi
0x14008df64  push    r12
0x14008df66  push    r14
0x14008df68  sub     rsp, 60h
0x14008df6c  mov     rax, cs:__security_cookie
0x14008df73  xor     rax, rsp
0x14008df76  mov     [rsp+88h+var_40], rax
0x14008df7b  mov     r14, rcx
0x14008df7e  xorps   xmm0, xmm0
0x14008df81  mov     rcx, r8; UnicodeString
0x14008df84  mov     r12, r9
0x14008df87  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14008df8c  mov     rdi, r8
0x14008df8f  mov     ebx, edx
0x14008df91  call    cs:__imp_RtlxUnicodeStringToOemSize
0x14008df98  nop     dword ptr [rax+rax+00h]
0x14008df9d  mov     esi, 12h
0x14008dfa2  mov     edx, esi
0x14008dfa4  cmp     eax, 10h
0x14008dfa7  jbe     short loc_14008DFAC
0x14008dfa9  lea     edx, [rax+2]
0x14008dfac  movzx   ecx, word ptr [rdi]
0x14008dfaf  lea     eax, [rdx+13Ch]
0x14008dfb5  lea     eax, [rdx+rax*2]
0x14008dfb8  add     eax, ecx
0x14008dfba  cmp     ebx, eax
0x14008dfbc  jb      loc_14008E351
0x14008dfc2  mov     eax, 0FFh
0x14008dfc7  cmp     cx, ax
0x14008dfca  ja      loc_14008E321
0x14008dfd0  mov     word ptr [r14+18h], 2
0x14008dfd7  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14008dfdc  movzx   eax, word ptr [rdi]
0x14008dfdf  xor     r8d, r8d; AllocateDestinationString
0x14008dfe2  mov     [rsp+88h+DestinationString.Length], ax
0x14008dfe7  mov     rdx, rdi; SourceString
0x14008dfea  inc     ax
0x14008dfed  mov     [rsp+88h+arg_8], rbp
0x14008dff5  mov     [rsp+88h+DestinationString.MaximumLength], ax
0x14008dffa  lea     rax, [r14+1Ah]
0x14008dffe  mov     [rsp+88h+DestinationString.Buffer], rax
0x14008e003  mov     [rsp+88h+var_30], r13
0x14008e008  call    cs:__imp_RtlUpcaseUnicodeStringToOemString
0x14008e00f  nop     dword ptr [rax+rax+00h]
0x14008e014  mov     ebp, 10h
0x14008e019  test    eax, eax
0x14008e01b  js      loc_14008E375
0x14008e021  movzx   edx, [rsp+88h+DestinationString.Length]
0x14008e026  cmp     dx, bp
0x14008e029  jnb     short loc_14008E04D
0x14008e02b  movzx   ecx, dx
0x14008e02e  mov     r8, rbp
0x14008e031  sub     r8, rcx; Size
0x14008e034  lea     rdx, asc_140062A50; "                "
0x14008e03b  add     rcx, [rsp+88h+DestinationString.Buffer]; void *
0x14008e040  call    memmove
0x14008e045  movzx   edx, bp
0x14008e048  mov     [rsp+88h+DestinationString.Length], dx
0x14008e04d  mov     r13, [rsp+88h+DestinationString.Buffer]
0x14008e052  mov     [rsp+88h+var_38], r15
0x14008e057  mov     [rsp+88h+var_68], 0
0x14008e05f  cmp     dx, bp
0x14008e062  jnz     loc_14008E123
0x14008e068  xor     r9d, r9d
0x14008e06b  lea     rax, [rsp+88h+var_68+3]
0x14008e070  mov     qword ptr [rsp+88h+var_50], rax
0x14008e075  xor     r15d, r15d
0x14008e078  mov     r10, r13
0x14008e07b  cmp     r9d, 10h
0x14008e07f  jge     loc_14008E35F
0x14008e085  xor     r11d, r11d
0x14008e088  xor     bl, bl
0x14008e08a  xor     cl, cl
0x14008e08c  xor     al, al
0x14008e08e  cmp     r11d, 4
0x14008e092  jge     short loc_14008E101
0x14008e094  movsx   r8, byte ptr [r10]
0x14008e098  lea     eax, [r8-30h]
0x14008e09c  cmp     al, 9
0x14008e09e  ja      short loc_14008E0BD
0x14008e0a0  movzx   eax, cl
0x14008e0a3  mov     bl, 1
0x14008e0a5  shl     al, 2
0x14008e0a8  add     cl, al
0x14008e0aa  add     cl, cl
0x14008e0ac  sub     cl, 30h ; '0'
0x14008e0af  add     cl, r8b
0x14008e0b2  inc     r10
0x14008e0b5  inc     r9d
0x14008e0b8  inc     r11d
0x14008e0bb  jmp     short loc_14008E08C
0x14008e0bd  cmp     r8b, 2Eh ; '.'
0x14008e0c1  ja      short loc_14008E123
0x14008e0c3  mov     rbp, 400100000001h
0x14008e0cd  bt      rbp, r8
0x14008e0d1  mov     ebp, 10h
0x14008e0d6  jnb     short loc_14008E123
0x14008e0d8  mov     rax, qword ptr [rsp+88h+var_50]
0x14008e0dd  inc     r15d
0x14008e0e0  mov     [rax], cl
0x14008e0e2  dec     rax
0x14008e0e5  mov     qword ptr [rsp+88h+var_50], rax
0x14008e0ea  cmp     r8b, 2Eh ; '.'
0x14008e0ee  jz      loc_14008E37C
0x14008e0f4  xor     al, al
0x14008e0f6  cmp     r8b, 20h ; ' '
0x14008e0fa  jz      short loc_14008E101
0x14008e0fc  test    r8b, r8b
0x14008e0ff  jnz     short loc_14008E0B2
0x14008e101  test    bl, bl
0x14008e103  jz      short loc_14008E123
0x14008e105  cmp     r15d, 4
0x14008e109  jnz     loc_14008E389
0x14008e10f  cmp     r9d, 10h
0x14008e113  jge     loc_14008E35F
0x14008e119  test    byte ptr [r10], 0DFh
0x14008e11d  jz      loc_14008E396
0x14008e123  xor     r15b, r15b
0x14008e126  xor     ecx, ecx
0x14008e128  mov     [r12], ecx
0x14008e12c  cmp     dx, 10h
0x14008e130  ja      loc_14008E3A9
0x14008e136  lea     eax, [rsi+10h]
0x14008e139  mov     word ptr [r14+6], 16h
0x14008e140  movzx   ecx, ax
0x14008e143  lea     r12, [r14+8]
0x14008e147  add     r12, rcx
0x14008e14a  mov     [r14+4], cx
0x14008e14f  mov     dword ptr [r14], 3
0x14008e156  test    r15b, r15b
0x14008e159  jnz     loc_14008E332
0x14008e15f  movups  xmm0, xmmword ptr [r13+0]
0x14008e164  xor     ecx, ecx
0x14008e166  movups  [rsp+88h+var_50], xmm0
0x14008e16b  cmp     byte ptr [rsp+rcx+88h+var_50], 2Eh ; '.'
0x14008e170  jz      short loc_14008E1AD
0x14008e172  lea     edx, [rcx+1]
0x14008e175  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e17a  jz      loc_14008E358
0x14008e180  lea     edx, [rcx+2]
0x14008e183  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e188  jz      loc_14008E358
0x14008e18e  lea     edx, [rcx+3]
0x14008e191  cmp     byte ptr [rsp+rdx+88h+var_50], 2Eh ; '.'
0x14008e196  jz      loc_14008E358
0x14008e19c  add     ecx, 4
0x14008e19f  cmp     ecx, 10h
0x14008e1a2  jb      short loc_14008E16B
0x14008e1a4  cmp     ecx, 10h
0x14008e1a7  jz      loc_14008E328
0x14008e1ad  mov     eax, ecx
0x14008e1af  lea     rdx, asc_140062A50; "                "
0x14008e1b6  mov     r8d, ebp
0x14008e1b9  sub     r8d, ecx; Size
0x14008e1bc  lea     rcx, [rsp+88h+var_50]
0x14008e1c1  add     rcx, rax; void *
0x14008e1c4  call    memmove
0x14008e1c9  lea     rax, [rsp+88h+var_50]
0x14008e1ce  movups  xmm0, xmmword ptr [rax]
0x14008e1d1  movzx   ebx, si
0x14008e1d4  lea     rcx, [r12+4]; void *
0x14008e1d9  mov     r8d, ebx; Size
0x14008e1dc  lea     rdx, [r14+18h]; Src
0x14008e1e0  movups  xmmword ptr [r14+8], xmm0
0x14008e1e5  mov     [r12], si
0x14008e1ea  mov     word ptr [r12+2], 11h
0x14008e1f2  call    memmove
0x14008e1f7  mov     eax, 2
0x14008e1fc  lea     rsi, [rbx+4]
0x14008e200  add     rsi, r12
0x14008e203  mov     r8d, 200h; Size
0x14008e209  mov     r14d, 20h ; ' '
0x14008e20f  mov     dword ptr [rsi], 180248h
0x14008e215  lea     rbx, [rsi+2Ah]
0x14008e219  mov     [rsi+12h], rbx
0x14008e21d  lea     rcx, [rsi+4Ch]; void *
0x14008e221  mov     [rsi+4], ax
0x14008e225  mov     [rsi+6], eax
0x14008e228  mov     dword ptr [rsi+0Ah], 220020h
0x14008e22f  movzx   eax, word ptr [rdi]
0x14008e232  mov     [rsi+1Ah], ax
0x14008e236  mov     [rsi+1Ch], r8w
0x14008e23b  mov     [rsi+22h], rcx
0x14008e23f  movzx   eax, word ptr [rdi]
0x14008e242  cmp     r8w, ax
0x14008e246  ja      loc_14008E315
0x14008e24c  mov     rdx, [rdi+8]; Src
0x14008e250  call    memmove
0x14008e255  test    r15b, r15b
0x14008e258  jnz     loc_14008E345
0x14008e25e  movups  xmm0, xmmword ptr cs:asc_140062A28; "                "
0x14008e265  movzx   eax, word ptr [rsi+0Ah]
0x14008e269  mov     rcx, rbx; void *
0x14008e26c  movups  xmmword ptr [rbx], xmm0
0x14008e26f  movups  xmm1, xmmword ptr cs:asc_140062A28+10h; "        "
0x14008e276  movups  xmmword ptr [rbx+10h], xmm1
0x14008e27a  movzx   edx, word ptr [rdi]
0x14008e27d  cmp     ax, dx
0x14008e280  cmovbe  dx, ax
0x14008e284  movzx   r8d, dx; Size
0x14008e288  mov     rdx, [rdi+8]; Src
0x14008e28c  call    memmove
0x14008e291  xor     eax, eax
0x14008e293  cmp     word ptr [rsi+rax*2+2Ah], 2Eh ; '.'
0x14008e299  jz      short loc_14008E2C9
0x14008e29b  lea     edx, [rax+1]
0x14008e29e  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e2a4  jz      short loc_14008E31D
0x14008e2a6  lea     edx, [rax+2]
0x14008e2a9  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e2af  jz      short loc_14008E31D
0x14008e2b1  lea     edx, [rax+3]
0x14008e2b4  cmp     word ptr [rsi+rdx*2+2Ah], 2Eh ; '.'
0x14008e2ba  jz      short loc_14008E31D
0x14008e2bc  add     eax, 4
0x14008e2bf  cmp     eax, 10h
0x14008e2c2  jb      short loc_14008E293
0x14008e2c4  cmp     eax, 10h
0x14008e2c7  jz      short loc_14008E33E
0x14008e2c9  mov     ecx, eax
0x14008e2cb  lea     rdx, asc_140062A28; "                "
0x14008e2d2  add     rcx, 15h
0x14008e2d6  sub     ebp, eax
0x14008e2d8  mov     r8d, ebp
0x14008e2db  add     r8, r8; Size
0x14008e2de  lea     rcx, [rsi+rcx*2]; void *
0x14008e2e2  call    memmove
0x14008e2e7  xor     eax, eax
0x14008e2e9  mov     r15, [rsp+88h+var_38]
0x14008e2ee  mov     rbp, [rsp+88h+arg_8]
0x14008e2f6  mov     r13, [rsp+88h+var_30]
0x14008e2fb  mov     rcx, [rsp+88h+var_40]
0x14008e300  xor     rcx, rsp; StackCookie
0x14008e303  call    __security_check_cookie
0x14008e308  add     rsp, 60h
0x14008e30c  pop     r14
0x14008e30e  pop     r12
0x14008e310  pop     rdi
0x14008e311  pop     rsi
0x14008e312  pop     rbx
0x14008e313  retn
0x14008e315  mov     r8, rax
0x14008e318  jmp     loc_14008E24C
0x14008e31d  mov     eax, edx
0x14008e31f  jmp     short loc_14008E2C4
0x14008e321  mov     eax, 0C00000BEh
0x14008e326  jmp     short loc_14008E2FB
0x14008e328  mov     byte ptr [rsp+88h+var_50+0Fh], 20h ; ' '
0x14008e32d  jmp     loc_14008E1C9
0x14008e332  lea     rax, aSmbserver_0; "*SMBSERVER      "
0x14008e339  jmp     loc_14008E1CE
0x14008e33e  mov     [rsi+48h], r14w
0x14008e343  jmp     short loc_14008E2E7
0x14008e345  movups  xmm0, xmmword ptr cs:aSmbserver; "*SMBSERVER      "
0x14008e34c  movups  xmmword ptr [rbx], xmm0
0x14008e34f  jmp     short loc_14008E2E7
0x14008e351  mov     eax, 80000005h
0x14008e356  jmp     short loc_14008E2FB
0x14008e358  mov     ecx, edx
0x14008e35a  jmp     loc_14008E1A4
0x14008e35f  mov     ecx, [rsp+88h+var_68]
0x14008e363  lea     eax, [rcx-1]
0x14008e366  cmp     eax, 0FFFFFFFDh
0x14008e369  jbe     short loc_14008E3A1
0x14008e36b  mov     eax, 0C0000207h
0x14008e370  jmp     loc_14008E2E9
0x14008e375  xor     edx, edx
0x14008e377  jmp     loc_14008E02B
0x14008e37c  inc     r10
0x14008e37f  mov     al, 1
0x14008e381  inc     r9d
0x14008e384  jmp     loc_14008E101
0x14008e389  test    al, al
0x14008e38b  jnz     loc_14008E07B
0x14008e391  jmp     loc_14008E123
0x14008e396  inc     r9d
0x14008e399  inc     r10
0x14008e39c  jmp     loc_14008E10F
0x14008e3a1  mov     r15b, 1
0x14008e3a4  jmp     loc_14008E128
0x14008e3a9  lea     esi, [rdx+2]
0x14008e3ac  jmp     loc_14008E136
```
