# IsFormatInRange(KSDATAFORMAT *,KSDATAFORMAT *)

- ea: `0x18001cf28`
- end: `0x18001d2dc`
- name: `?IsFormatInRange@@YAJPEATKSDATAFORMAT@@0@Z`
- size: `948`
- prototype: `__int64 __fastcall(union KSDATAFORMAT *, union KSDATAFORMAT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180030188`

## callees

- `0x18001cf28`
- `0x18001f620`
- `0x180025860`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18001d0ca`
- `USER32!IsRectEmpty` at `0x18001d139`
- `USER32!IsRectEmpty` at `0x18001d0ca`
- `USER32!IsRectEmpty` at `0x18001d139`
- `USER32!SetRect` at `0x18001d0f1`
- `USER32!SetRect` at `0x18001d0f1`

## pseudocode

```c
__int64 __fastcall IsFormatInRange(union KSDATAFORMAT *a1, union KSDATAFORMAT *a2)
{
  LONGLONG v4; // rax
  LONGLONG v5; // rax
  bool v6; // zf
  LONGLONG *v7; // rax
  LONGLONG v8; // rcx
  LONGLONG v9; // rcx
  LONGLONG v10; // rcx
  LONGLONG v11; // rcx
  LONGLONG v12; // rax
  RECT v13; // xmm0
  ULONG Reserved; // esi
  RECT v15; // xmm1
  signed int Data1; // edi
  int yBottom; // eax
  int v18; // r15d
  int v19; // edi
  int v20; // r14d
  int v21; // esi
  signed int FormatSize; // ecx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  signed int Flags; // ecx
  int v26; // ecx
  signed int v27; // r8d
  RECT v29; // [rsp+30h] [rbp-48h] BYREF
  RECT rc; // [rsp+40h] [rbp-38h] BYREF
  struct tagRECT v31; // [rsp+50h] [rbp-28h] BYREF

  v31 = 0;
  v29 = 0;
  rc = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids);
  v4 = *(&a2->Alignment + 2) - *(_QWORD *)&GUID_73646976_0000_0010_8000_00aa00389b71.Data1;
  if ( !v4 )
    v4 = *(&a2->Alignment + 3) - *(_QWORD *)GUID_73646976_0000_0010_8000_00aa00389b71.Data4;
  if ( v4 )
    return 2147500037LL;
  v5 = *(&a2->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v5 )
    v5 = *(&a2->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  v6 = v5 == 0;
  v7 = &a1->Alignment + 6;
  if ( !v6 )
    goto LABEL_16;
  v8 = *v7 - *(_QWORD *)&GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1;
  if ( *v7 == *(_QWORD *)&GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1 )
    v8 = *(&a1->Alignment + 7) - *(_QWORD *)GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4;
  if ( v8 )
    goto LABEL_16;
  v9 = *(&a2->Alignment + 4) - *(&a1->Alignment + 4);
  if ( !v9 )
    v9 = *(&a2->Alignment + 5) - *(&a1->Alignment + 5);
  if ( v9 )
  {
LABEL_16:
    v10 = *(&a2->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v10 )
      v10 = *(&a2->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v10 )
      return 2147500037LL;
    v11 = *v7 - *(_QWORD *)&GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1;
    if ( *v7 == *(_QWORD *)&GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1 )
      v11 = *(&a1->Alignment + 7) - *(_QWORD *)GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4;
    if ( v11 )
      return 2147500037LL;
    v12 = *(&a2->Alignment + 4) - *(&a1->Alignment + 4);
    if ( !v12 )
      v12 = *(&a2->Alignment + 5) - *(&a1->Alignment + 5);
    if ( v12 || a1->FormatSize < 0x140 || a2->FormatSize < 0xB0 )
      return 2147500037LL;
    v13 = *(RECT *)&a2[1].FormatSize;
    Reserved = a2[2].Reserved;
    v15 = (RECT)*((_OWORD *)&a2[1].Alignment + 1);
    Data1 = a2[2].MajorFormat.Data1;
  }
  else
  {
    if ( a1->FormatSize < 0x128 || a2->FormatSize < 0x98 )
      return 2147500037LL;
    v13 = *(RECT *)&a2[1].FormatSize;
    Reserved = *((_DWORD *)&a2[1].Alignment + 13);
    v15 = (RECT)*((_OWORD *)&a2[1].Alignment + 1);
    Data1 = *((_DWORD *)&a2[1].Alignment + 14);
  }
  rc = v15;
  v29 = v13;
  if ( IsRectEmpty(&rc) )
  {
    yBottom = -Data1;
    if ( Data1 > 0 )
      yBottom = Data1;
    SetRect(&v31, 0, 0, Reserved, yBottom);
  }
  else
  {
    v31 = rc;
  }
  v18 = v31.right - v31.left;
  v19 = v31.top - v31.bottom;
  if ( v31.top - v31.bottom < 0 )
    v19 = v31.bottom - v31.top;
  v20 = v29.right - v29.left;
  v21 = v29.bottom - v29.top;
  if ( !IsRectEmpty(&v29) )
  {
    if ( v20 < *((_DWORD *)&a1[1].Alignment + 11)
      || v20 > *((_DWORD *)&a1[1].Alignment + 13)
      || v21 < (signed int)a1[1].Specifier.Data1
      || v21 > *((_DWORD *)&a1[1].Alignment + 14) )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        return 2147500037LL;
      v24 = 46;
      goto LABEL_75;
    }
    if ( *((_DWORD *)&a1[1].Alignment + 15) )
    {
      FormatSize = a1[2].FormatSize;
      if ( FormatSize )
      {
        if ( v20 % *((_DWORD *)&a1[1].Alignment + 15) || v21 % FormatSize )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
            return 2147500037LL;
          v24 = 47;
          goto LABEL_75;
        }
      }
    }
    Flags = a1[2].Flags;
    if ( Flags && a1[2].SampleSize && v29.left % Flags || v29.top % (signed int)a1[2].SampleSize )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        return 2147500037LL;
      v24 = 48;
      goto LABEL_75;
    }
  }
  if ( v18 < (signed int)a1[2].Reserved
    || v18 > *((_DWORD *)&a1[2].Alignment + 5)
    || v19 < (signed int)a1[2].MajorFormat.Data1
    || v19 > *((_DWORD *)&a1[2].Alignment + 6) )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      return 2147500037LL;
    v24 = 49;
    goto LABEL_75;
  }
  v26 = *((_DWORD *)&a1[2].Alignment + 7);
  if ( !v26 )
    return 0;
  v27 = a1[2].SubFormat.Data1;
  if ( !v27 || !(v18 % v26) && !(v19 % v27) )
    return 0;
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v24 = 50;
LABEL_75:
    WPP_SF_(v23[2], v24, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001cf28  push    rbp
0x18001cf2a  push    rbx
0x18001cf2b  push    rsi
0x18001cf2c  push    rdi
0x18001cf2d  push    r12
0x18001cf2f  push    r13
0x18001cf31  push    r14
0x18001cf33  push    r15
0x18001cf35  mov     rbp, rsp
0x18001cf38  sub     rsp, 78h
0x18001cf3c  mov     rax, cs:__security_cookie
0x18001cf43  xor     rax, rsp
0x18001cf46  mov     [rbp+var_18], rax
0x18001cf4a  xorps   xmm0, xmm0
0x18001cf4d  xorps   xmm1, xmm1
0x18001cf50  movups  xmmword ptr [rbp+var_28.left], xmm0
0x18001cf54  mov     rdi, rdx
0x18001cf57  mov     rbx, rcx
0x18001cf5a  movups  xmmword ptr [rbp+var_48.left], xmm1
0x18001cf5e  movups  xmmword ptr [rbp+rc.left], xmm0
0x18001cf62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf69  lea     r12, WPP_GLOBAL_Control
0x18001cf70  lea     r13, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x18001cf77  cmp     rcx, r12
0x18001cf7a  jz      short loc_18001CF93
0x18001cf7c  cmp     byte ptr [rcx+19h], 3
0x18001cf80  jb      short loc_18001CF93
0x18001cf82  mov     rcx, [rcx+10h]
0x18001cf86  mov     edx, 2Dh ; '-'
0x18001cf8b  mov     r8, r13
0x18001cf8e  call    WPP_SF_
0x18001cf93  mov     rax, [rdi+10h]
0x18001cf97  sub     rax, qword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x18001cf9e  jnz     short loc_18001CFAB
0x18001cfa0  mov     rax, [rdi+18h]
0x18001cfa4  sub     rax, qword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data4
0x18001cfab  test    rax, rax
0x18001cfae  jnz     loc_18001D2B9
0x18001cfb4  mov     rax, [rdi+30h]
0x18001cfb8  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18001cfbf  jnz     short loc_18001CFCC
0x18001cfc1  mov     rax, [rdi+38h]
0x18001cfc5  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18001cfcc  test    rax, rax
0x18001cfcf  lea     rax, [rbx+30h]
0x18001cfd3  jnz     short loc_18001D00C
0x18001cfd5  mov     rcx, [rax]
0x18001cfd8  sub     rcx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x18001cfdf  jnz     short loc_18001CFEC
0x18001cfe1  mov     rcx, [rax+8]
0x18001cfe5  sub     rcx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4
0x18001cfec  test    rcx, rcx
0x18001cfef  jnz     short loc_18001D00C
0x18001cff1  mov     rcx, [rdi+20h]
0x18001cff5  sub     rcx, [rbx+20h]
0x18001cff9  jnz     short loc_18001D003
0x18001cffb  mov     rcx, [rdi+28h]
0x18001cfff  sub     rcx, [rbx+28h]
0x18001d003  test    rcx, rcx
0x18001d006  jz      loc_18001D096
0x18001d00c  mov     rcx, [rdi+30h]
0x18001d010  sub     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18001d017  jnz     short loc_18001D024
0x18001d019  mov     rcx, [rdi+38h]
0x18001d01d  sub     rcx, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18001d024  test    rcx, rcx
0x18001d027  jnz     loc_18001D2B9
0x18001d02d  mov     rcx, [rax]
0x18001d030  sub     rcx, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x18001d037  jnz     short loc_18001D044
0x18001d039  mov     rcx, [rax+8]
0x18001d03d  sub     rcx, qword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4
0x18001d044  test    rcx, rcx
0x18001d047  jnz     loc_18001D2B9
0x18001d04d  mov     rax, [rdi+20h]
0x18001d051  sub     rax, [rbx+20h]
0x18001d055  jnz     short loc_18001D05F
0x18001d057  mov     rax, [rdi+28h]
0x18001d05b  sub     rax, [rbx+28h]
0x18001d05f  test    rax, rax
0x18001d062  jnz     loc_18001D2B9
0x18001d068  cmp     dword ptr [rbx], 140h
0x18001d06e  jb      loc_18001D2B9
0x18001d074  cmp     dword ptr [rdi], 0B0h
0x18001d07a  jb      loc_18001D2B9
0x18001d080  movups  xmm0, xmmword ptr [rdi+40h]
0x18001d084  mov     esi, [rdi+8Ch]
0x18001d08a  movups  xmm1, xmmword ptr [rdi+50h]
0x18001d08e  mov     edi, [rdi+90h]
0x18001d094  jmp     short loc_18001D0BC
0x18001d096  cmp     dword ptr [rbx], 128h
0x18001d09c  jb      loc_18001D2B9
0x18001d0a2  cmp     dword ptr [rdi], 98h
0x18001d0a8  jb      loc_18001D2B9
0x18001d0ae  movups  xmm0, xmmword ptr [rdi+40h]
0x18001d0b2  mov     esi, [rdi+74h]
0x18001d0b5  movups  xmm1, xmmword ptr [rdi+50h]
0x18001d0b9  mov     edi, [rdi+78h]
0x18001d0bc  lea     rcx, [rbp+rc]; lprc
0x18001d0c0  movdqu  xmmword ptr [rbp+rc.left], xmm1
0x18001d0c5  movdqu  xmmword ptr [rbp+var_48.left], xmm0
0x18001d0ca  call    cs:__imp_IsRectEmpty
0x18001d0d1  nop     dword ptr [rax+rax+00h]
0x18001d0d6  test    eax, eax
0x18001d0d8  jz      short loc_18001D0FF
0x18001d0da  mov     eax, edi
0x18001d0dc  lea     rcx, [rbp+var_28]; lprc
0x18001d0e0  neg     eax
0x18001d0e2  mov     r9d, esi; xRight
0x18001d0e5  cmovs   eax, edi
0x18001d0e8  xor     r8d, r8d; yTop
0x18001d0eb  xor     edx, edx; xLeft
0x18001d0ed  mov     [rsp+78h+yBottom], eax; yBottom
0x18001d0f1  call    cs:__imp_SetRect
0x18001d0f8  nop     dword ptr [rax+rax+00h]
0x18001d0fd  jmp     short loc_18001D108
0x18001d0ff  movaps  xmm0, xmmword ptr [rbp+rc.left]
0x18001d103  movdqa  xmmword ptr [rbp+var_28.left], xmm0
0x18001d108  mov     rcx, qword ptr [rbp+var_28.right]
0x18001d10c  mov     rax, qword ptr [rbp+var_28.left]
0x18001d110  mov     r15d, ecx
0x18001d113  mov     r14d, [rbp+var_48.right]
0x18001d117  sub     r15d, eax
0x18001d11a  mov     esi, [rbp+var_48.bottom]
0x18001d11d  shr     rcx, 20h
0x18001d121  shr     rax, 20h
0x18001d125  sub     ecx, eax
0x18001d127  mov     edi, ecx
0x18001d129  neg     edi
0x18001d12b  cmovs   edi, ecx
0x18001d12e  sub     r14d, [rbp+var_48.left]
0x18001d132  sub     esi, [rbp+var_48.top]
0x18001d135  lea     rcx, [rbp+var_48]; lprc
0x18001d139  call    cs:__imp_IsRectEmpty
0x18001d140  nop     dword ptr [rax+rax+00h]
0x18001d145  test    eax, eax
0x18001d147  jnz     loc_18001D22D
0x18001d14d  cmp     r14d, [rbx+6Ch]
0x18001d151  jl      loc_18001D209
0x18001d157  cmp     r14d, [rbx+74h]
0x18001d15b  jg      loc_18001D209
0x18001d161  cmp     esi, [rbx+70h]
0x18001d164  jl      loc_18001D209
0x18001d16a  cmp     esi, [rbx+78h]
0x18001d16d  jg      loc_18001D209
0x18001d173  cmp     [rbx+7Ch], eax
0x18001d176  jz      short loc_18001D1BA
0x18001d178  mov     ecx, [rbx+80h]
0x18001d17e  test    ecx, ecx
0x18001d180  jz      short loc_18001D1BA
0x18001d182  mov     eax, r14d
0x18001d185  cdq
0x18001d186  idiv    dword ptr [rbx+7Ch]
0x18001d189  test    edx, edx
0x18001d18b  jnz     short loc_18001D196
0x18001d18d  mov     eax, esi
0x18001d18f  cdq
0x18001d190  idiv    ecx
0x18001d192  test    edx, edx
0x18001d194  jz      short loc_18001D1BA
0x18001d196  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d19d  cmp     rcx, r12
0x18001d1a0  jz      loc_18001D2B9
0x18001d1a6  cmp     byte ptr [rcx+19h], 5
0x18001d1aa  jb      loc_18001D2B9
0x18001d1b0  mov     edx, 2Fh ; '/'
0x18001d1b5  jmp     loc_18001D2AD
0x18001d1ba  mov     ecx, [rbx+84h]
0x18001d1c0  test    ecx, ecx
0x18001d1c2  jz      short loc_18001D1D7
0x18001d1c4  cmp     dword ptr [rbx+88h], 0
0x18001d1cb  jz      short loc_18001D1D7
0x18001d1cd  mov     eax, [rbp+var_48.left]
0x18001d1d0  cdq
0x18001d1d1  idiv    ecx
0x18001d1d3  test    edx, edx
0x18001d1d5  jnz     short loc_18001D1E5
0x18001d1d7  mov     eax, [rbp+var_48.top]
0x18001d1da  cdq
0x18001d1db  idiv    dword ptr [rbx+88h]
0x18001d1e1  test    edx, edx
0x18001d1e3  jz      short loc_18001D22D
0x18001d1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1ec  cmp     rcx, r12
0x18001d1ef  jz      loc_18001D2B9
0x18001d1f5  cmp     byte ptr [rcx+19h], 5
0x18001d1f9  jb      loc_18001D2B9
0x18001d1ff  mov     edx, 30h ; '0'
0x18001d204  jmp     loc_18001D2AD
0x18001d209  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d210  cmp     rcx, r12
0x18001d213  jz      loc_18001D2B9
0x18001d219  cmp     byte ptr [rcx+19h], 5
0x18001d21d  jb      loc_18001D2B9
0x18001d223  mov     edx, 2Eh ; '.'
0x18001d228  jmp     loc_18001D2AD
0x18001d22d  cmp     r15d, [rbx+8Ch]
0x18001d234  jl      short loc_18001D296
0x18001d236  cmp     r15d, [rbx+94h]
0x18001d23d  jg      short loc_18001D296
0x18001d23f  cmp     edi, [rbx+90h]
0x18001d245  jl      short loc_18001D296
0x18001d247  cmp     edi, [rbx+98h]
0x18001d24d  jg      short loc_18001D296
0x18001d24f  mov     ecx, [rbx+9Ch]
0x18001d255  test    ecx, ecx
0x18001d257  jz      short loc_18001D292
0x18001d259  mov     r8d, [rbx+0A0h]
0x18001d260  test    r8d, r8d
0x18001d263  jz      short loc_18001D292
0x18001d265  mov     eax, r15d
0x18001d268  cdq
0x18001d269  idiv    ecx
0x18001d26b  test    edx, edx
0x18001d26d  jnz     short loc_18001D279
0x18001d26f  mov     eax, edi
0x18001d271  cdq
0x18001d272  idiv    r8d
0x18001d275  test    edx, edx
0x18001d277  jz      short loc_18001D292
0x18001d279  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d280  cmp     rcx, r12
0x18001d283  jz      short loc_18001D2B9
0x18001d285  cmp     byte ptr [rcx+19h], 5
0x18001d289  jb      short loc_18001D2B9
0x18001d28b  mov     edx, 32h ; '2'
0x18001d290  jmp     short loc_18001D2AD
0x18001d292  xor     eax, eax
0x18001d294  jmp     short loc_18001D2BE
0x18001d296  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d29d  cmp     rcx, r12
0x18001d2a0  jz      short loc_18001D2B9
0x18001d2a2  cmp     byte ptr [rcx+19h], 5
0x18001d2a6  jb      short loc_18001D2B9
0x18001d2a8  mov     edx, 31h ; '1'
0x18001d2ad  mov     rcx, [rcx+10h]
0x18001d2b1  mov     r8, r13
0x18001d2b4  call    WPP_SF_
0x18001d2b9  mov     eax, 80004005h
0x18001d2be  mov     rcx, [rbp+var_18]
0x18001d2c2  xor     rcx, rsp; StackCookie
0x18001d2c5  call    __security_check_cookie
0x18001d2ca  add     rsp, 78h
0x18001d2ce  pop     r15
0x18001d2d0  pop     r14
0x18001d2d2  pop     r13
0x18001d2d4  pop     r12
0x18001d2d6  pop     rdi
0x18001d2d7  pop     rsi
0x18001d2d8  pop     rbx
0x18001d2d9  pop     rbp
0x18001d2da  retn
```
