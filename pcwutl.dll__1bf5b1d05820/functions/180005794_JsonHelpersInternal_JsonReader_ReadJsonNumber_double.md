# JsonHelpersInternal::JsonReader::ReadJsonNumber(double *)

- ea: `0x180005794`
- end: `0x180005a66`
- name: `?ReadJsonNumber@JsonReader@JsonHelpersInternal@@QEAAJPEAN@Z`
- size: `722`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, double *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005ef4`

## callees

- `0x180005794`
- `0x180007f8c`
- `0x180008164`

## import_xrefs

- `msvcrt!_wtof` at `0x180005a23`
- `msvcrt!_wtof` at `0x180005a23`
- `KERNEL32!GetProcessHeap` at `0x1800057b3`
- `KERNEL32!GetProcessHeap` at `0x1800057b9`
- `KERNEL32!GetProcessHeap` at `0x1800057b3`
- `KERNEL32!GetProcessHeap` at `0x1800057b9`
- `KERNEL32!HeapFree` at `0x180005a45`
- `KERNEL32!HeapFree` at `0x180005a45`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonNumber(JsonHelpersInternal::JsonReader *this, double *a2)
{
  __int64 v4; // r9
  unsigned __int64 v5; // r8
  __int16 v6; // cx
  int v7; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  bool v12; // zf
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 v15; // rcx
  unsigned __int16 v16; // r8
  unsigned __int64 v17; // r8
  HANDLE hHeap; // [rsp+20h] [rbp-30h] BYREF
  __int128 v20; // [rsp+28h] [rbp-28h]
  __int64 v21; // [rsp+38h] [rbp-18h]
  wchar_t *String[2]; // [rsp+40h] [rbp-10h]
  __int16 v23; // [rsp+90h] [rbp+40h] BYREF

  GetProcessHeap();
  v21 = 4096;
  hHeap = GetProcessHeap();
  v20 = 0;
  *(_OWORD *)String = 0;
  v4 = *((_QWORD *)this + 1);
  while ( 1 )
  {
    v5 = *(_QWORD *)this;
    v6 = *(_WORD *)(v4 + 2LL * *(_QWORD *)this);
    if ( v6 != 9
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v4 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v5 + 1;
    if ( !v6 )
      *(_QWORD *)this = v5;
  }
  v23 = *(_WORD *)(v4 + 2LL * *(_QWORD *)this);
  *(_QWORD *)this = v5 + 1;
  if ( v6 )
  {
    if ( v6 == 45 )
    {
      v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v5);
      if ( v7 < 0 )
        goto LABEL_45;
      v8 = *(_QWORD *)this;
      v6 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
      if ( !v6 )
        *(_QWORD *)this = v8;
      v23 = v6;
    }
  }
  else
  {
    *(_QWORD *)this = v5;
  }
  if ( (unsigned __int16)(v6 - 48) > 9u )
    goto LABEL_44;
  v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v5);
  if ( v7 < 0 )
    goto LABEL_45;
  if ( v23 == 48 && *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *(_QWORD *)this) != 46 )
  {
LABEL_42:
    v7 = RtlMemoryStream::WriteString((RtlMemoryStream *)&hHeap, v9, (const unsigned __int16 *)v10);
    if ( v7 >= 0 )
    {
      *a2 = _wtof(String[1]);
      v7 = 0;
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    v11 = *(_QWORD *)this;
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    v10 = v9[*(_QWORD *)this];
    if ( (unsigned __int16)(v10 - 48) > 9u )
      break;
    *(_QWORD *)this = v11 + 1;
    if ( !(_WORD)v10 )
      *(_QWORD *)this = v11;
    v23 = v10;
    v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v10);
    if ( v7 < 0 )
      goto LABEL_45;
  }
  if ( (_WORD)v10 != 46 )
  {
    LOWORD(v10) = v10 - 69;
    v12 = (v10 & 0xFFDF) == 0;
LABEL_32:
    if ( v12 )
    {
LABEL_33:
      v14 = v9[v11];
      *(_QWORD *)this = v11 + 1;
      if ( !(_WORD)v14 )
        *(_QWORD *)this = v11;
      v23 = v14;
      v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v14);
      if ( v7 < 0 )
        goto LABEL_45;
      v15 = *(_QWORD *)this;
      v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
      v16 = v9[*(_QWORD *)this];
      if ( (unsigned __int16)(v16 - 48) <= 9u || ((v16 - 43) & 0xFFFD) == 0 )
      {
        while ( 1 )
        {
          v17 = v9[v15];
          *(_QWORD *)this = v15 + 1;
          if ( !(_WORD)v17 )
            *(_QWORD *)this = v15;
          v23 = v17;
          v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v17);
          if ( v7 < 0 )
            goto LABEL_45;
          v15 = *(_QWORD *)this;
          v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
          if ( (unsigned __int16)(v9[*(_QWORD *)this] - 48) > 9u )
            goto LABEL_42;
        }
      }
LABEL_44:
      v7 = -2147024883;
      goto LABEL_45;
    }
    goto LABEL_42;
  }
  while ( 1 )
  {
    v13 = v9[v11];
    *(_QWORD *)this = v11 + 1;
    if ( !(_WORD)v13 )
      *(_QWORD *)this = v11;
    v23 = v13;
    v7 = RtlMemoryStream::Write((RtlMemoryStream *)&hHeap, &v23, v13);
    if ( v7 < 0 )
      break;
    v11 = *(_QWORD *)this;
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    if ( (unsigned __int16)(v9[*(_QWORD *)this] - 48) > 9u )
    {
      if ( v9[v11] == 69 )
        goto LABEL_33;
      v12 = v9[v11] == 101;
      goto LABEL_32;
    }
  }
LABEL_45:
  if ( String[1] )
    HeapFree(hHeap, 0, String[1]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005794  mov     [rsp-28h+arg_0], rbx
0x180005799  mov     [rsp-28h+arg_8], rsi
0x18000579e  push    rbp
0x18000579f  push    rdi
0x1800057a0  push    r12
0x1800057a2  push    r14
0x1800057a4  push    r15
0x1800057a6  mov     rbp, rsp
0x1800057a9  sub     rsp, 50h
0x1800057ad  mov     rsi, rdx
0x1800057b0  mov     rdi, rcx
0x1800057b3  call    cs:__imp_GetProcessHeap
0x1800057b9  call    cs:__imp_GetProcessHeap
0x1800057bf  xorps   xmm0, xmm0
0x1800057c2  mov     [rbp+var_18], 1000h
0x1800057ca  xorps   xmm1, xmm1
0x1800057cd  mov     [rbp+hHeap], rax
0x1800057d1  movdqu  [rbp+var_28], xmm0
0x1800057d6  movdqu  xmmword ptr [rbp+String], xmm1
0x1800057db  mov     r9, [rdi+8]
0x1800057df  mov     r12d, 9
0x1800057e5  mov     r8, [rdi]; unsigned __int64
0x1800057e8  movzx   ecx, word ptr [r9+r8*2]
0x1800057ed  mov     edx, ecx
0x1800057ef  sub     edx, r12d
0x1800057f2  jz      short loc_180005803
0x1800057f4  sub     edx, 1
0x1800057f7  jz      short loc_180005803
0x1800057f9  sub     edx, 3
0x1800057fc  jz      short loc_180005803
0x1800057fe  cmp     edx, 13h
0x180005801  jnz     short loc_180005816
0x180005803  lea     rax, [r8+1]
0x180005807  mov     [rdi], rax
0x18000580a  xor     eax, eax
0x18000580c  cmp     ax, cx
0x18000580f  jnz     short loc_1800057E5
0x180005811  mov     [rdi], r8
0x180005814  jmp     short loc_1800057E5
0x180005816  lea     rax, [r8+1]
0x18000581a  mov     [rbp+arg_10], cx
0x18000581e  mov     [rdi], rax
0x180005821  xor     eax, eax
0x180005823  cmp     ax, cx
0x180005826  jnz     short loc_18000582D
0x180005828  mov     [rdi], r8
0x18000582b  jmp     short loc_18000586E
0x18000582d  mov     eax, 2Dh ; '-'
0x180005832  cmp     ax, cx
0x180005835  jnz     short loc_18000586E
0x180005837  lea     rdx, [rbp+arg_10]; void *
0x18000583b  lea     rcx, [rbp+hHeap]; this
0x18000583f  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x180005844  mov     ebx, eax
0x180005846  test    eax, eax
0x180005848  js      loc_180005A36
0x18000584e  mov     rdx, [rdi]
0x180005851  mov     rax, [rdi+8]
0x180005855  movzx   ecx, word ptr [rax+rdx*2]
0x180005859  lea     rax, [rdx+1]
0x18000585d  mov     [rdi], rax
0x180005860  xor     eax, eax
0x180005862  cmp     ax, cx
0x180005865  jnz     short loc_18000586A
0x180005867  mov     [rdi], rdx
0x18000586a  mov     [rbp+arg_10], cx
0x18000586e  mov     r14d, 30h ; '0'
0x180005874  sub     cx, r14w
0x180005878  cmp     cx, r12w
0x18000587c  ja      loc_180005A31
0x180005882  lea     rdx, [rbp+arg_10]; void *
0x180005886  lea     rcx, [rbp+hHeap]; this
0x18000588a  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18000588f  mov     ebx, eax
0x180005891  test    eax, eax
0x180005893  js      loc_180005A36
0x180005899  lea     r15d, [r14-2]
0x18000589d  cmp     r14w, [rbp+arg_10]
0x1800058a2  jnz     short loc_1800058B6
0x1800058a4  mov     rcx, [rdi]
0x1800058a7  mov     rax, [rdi+8]
0x1800058ab  cmp     r15w, [rax+rcx*2]
0x1800058b0  jnz     loc_180005A10
0x1800058b6  mov     rcx, [rdi]
0x1800058b9  mov     rdx, [rdi+8]
0x1800058bd  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x1800058c2  movzx   eax, r8w
0x1800058c6  sub     ax, r14w
0x1800058ca  cmp     ax, r12w
0x1800058ce  ja      short loc_1800058FF
0x1800058d0  lea     rax, [rcx+1]
0x1800058d4  mov     [rdi], rax
0x1800058d7  xor     eax, eax
0x1800058d9  cmp     ax, r8w
0x1800058dd  jnz     short loc_1800058E2
0x1800058df  mov     [rdi], rcx
0x1800058e2  lea     rdx, [rbp+arg_10]; void *
0x1800058e6  mov     [rbp+arg_10], r8w
0x1800058eb  lea     rcx, [rbp+hHeap]; this
0x1800058ef  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x1800058f4  mov     ebx, eax
0x1800058f6  test    eax, eax
0x1800058f8  jns     short loc_1800058B6
0x1800058fa  jmp     loc_180005A36
0x1800058ff  cmp     r8w, r15w
0x180005903  jz      short loc_180005915
0x180005905  sub     r8w, 45h ; 'E'
0x18000590a  mov     eax, 0FFDFh
0x18000590f  test    ax, r8w
0x180005913  jmp     short loc_180005969
0x180005915  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x18000591a  lea     rax, [rcx+1]
0x18000591e  mov     [rdi], rax
0x180005921  xor     eax, eax
0x180005923  cmp     ax, r8w
0x180005927  jnz     short loc_18000592C
0x180005929  mov     [rdi], rcx
0x18000592c  lea     rdx, [rbp+arg_10]; void *
0x180005930  mov     [rbp+arg_10], r8w
0x180005935  lea     rcx, [rbp+hHeap]; this
0x180005939  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x18000593e  mov     ebx, eax
0x180005940  test    eax, eax
0x180005942  js      loc_180005A36
0x180005948  mov     rcx, [rdi]
0x18000594b  mov     rdx, [rdi+8]
0x18000594f  movzx   eax, word ptr [rdx+rcx*2]
0x180005953  sub     ax, r14w
0x180005957  cmp     ax, r12w
0x18000595b  jbe     short loc_180005915
0x18000595d  cmp     word ptr [rdx+rcx*2], 45h ; 'E'
0x180005962  jz      short loc_18000596F
0x180005964  cmp     word ptr [rdx+rcx*2], 65h ; 'e'
0x180005969  jnz     loc_180005A10
0x18000596f  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x180005974  lea     rax, [rcx+1]
0x180005978  mov     [rdi], rax
0x18000597b  xor     eax, eax
0x18000597d  cmp     ax, r8w
0x180005981  jnz     short loc_180005986
0x180005983  mov     [rdi], rcx
0x180005986  lea     rdx, [rbp+arg_10]; void *
0x18000598a  mov     [rbp+arg_10], r8w
0x18000598f  lea     rcx, [rbp+hHeap]; this
0x180005993  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x180005998  mov     ebx, eax
0x18000599a  test    eax, eax
0x18000599c  js      loc_180005A36
0x1800059a2  mov     rcx, [rdi]
0x1800059a5  mov     rdx, [rdi+8]
0x1800059a9  movzx   r8d, word ptr [rdx+rcx*2]
0x1800059ae  movzx   eax, r8w
0x1800059b2  sub     ax, r14w
0x1800059b6  cmp     ax, r12w
0x1800059ba  jbe     short loc_1800059CC
0x1800059bc  sub     r8w, 2Bh ; '+'
0x1800059c1  mov     eax, 0FFFDh
0x1800059c6  test    ax, r8w
0x1800059ca  jnz     short loc_180005A31
0x1800059cc  movzx   r8d, word ptr [rdx+rcx*2]; unsigned __int64
0x1800059d1  lea     rax, [rcx+1]
0x1800059d5  mov     [rdi], rax
0x1800059d8  xor     eax, eax
0x1800059da  cmp     ax, r8w
0x1800059de  jnz     short loc_1800059E3
0x1800059e0  mov     [rdi], rcx
0x1800059e3  lea     rdx, [rbp+arg_10]; void *
0x1800059e7  mov     [rbp+arg_10], r8w
0x1800059ec  lea     rcx, [rbp+hHeap]; this
0x1800059f0  call    ?Write@RtlMemoryStream@@QEAAKPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x1800059f5  mov     ebx, eax
0x1800059f7  test    eax, eax
0x1800059f9  js      short loc_180005A36
0x1800059fb  mov     rcx, [rdi]
0x1800059fe  mov     rdx, [rdi+8]; unsigned __int16 *
0x180005a02  movzx   eax, word ptr [rdx+rcx*2]
0x180005a06  sub     ax, r14w
0x180005a0a  cmp     ax, r12w
0x180005a0e  jbe     short loc_1800059CC
0x180005a10  lea     rcx, [rbp+hHeap]; this
0x180005a14  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x180005a19  mov     ebx, eax
0x180005a1b  test    eax, eax
0x180005a1d  js      short loc_180005A36
0x180005a1f  mov     rcx, [rbp+String+8]; String
0x180005a23  call    cs:__imp__wtof
0x180005a29  movsd   qword ptr [rsi], xmm0
0x180005a2d  xor     ebx, ebx
0x180005a2f  jmp     short loc_180005A36
0x180005a31  mov     ebx, 8007000Dh
0x180005a36  mov     r8, [rbp+String+8]; lpMem
0x180005a3a  test    r8, r8
0x180005a3d  jz      short loc_180005A4B
0x180005a3f  mov     rcx, [rbp+hHeap]; hHeap
0x180005a43  xor     edx, edx; dwFlags
0x180005a45  call    cs:__imp_HeapFree
0x180005a4b  lea     r11, [rsp+50h+var_s0]
0x180005a50  mov     eax, ebx
0x180005a52  mov     rbx, [r11+30h]
0x180005a56  mov     rsi, [r11+38h]
0x180005a5a  mov     rsp, r11
0x180005a5d  pop     r15
0x180005a5f  pop     r14
0x180005a61  pop     r12
0x180005a63  pop     rdi
0x180005a64  pop     rbp
0x180005a65  retn
```
