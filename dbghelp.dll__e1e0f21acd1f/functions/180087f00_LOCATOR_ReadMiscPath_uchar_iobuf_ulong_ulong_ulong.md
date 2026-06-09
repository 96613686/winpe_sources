# LOCATOR::ReadMiscPath(uchar *,_iobuf *,ulong,ulong,ulong)

- ea: `0x180087f00`
- end: `0x180088275`
- name: `?ReadMiscPath@LOCATOR@@AEAAXPEAEPEAU_iobuf@@KKK@Z`
- size: `885`
- prototype: `void(LOCATOR *__hidden this, unsigned __int8 *, struct _iobuf *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180084420`

## callees

- `0x18002641c`
- `0x180026980`
- `0x1800269f8`
- `0x180087f00`
- `0x180169420`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180087fa8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800880b8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180087fa8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800880b8`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180087f87`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18008809a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180087f87`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18008809a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008815b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800881aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18008815b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800881aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LOCATOR::ReadMiscPath(
        LOCATOR *this,
        unsigned __int8 *a2,
        struct _iobuf *a3,
        int a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v10; // r13
  int v11; // ebx
  unsigned int v12; // esi
  unsigned int v13; // ecx
  bool v14; // al
  __int64 (__fastcall *v15)(_QWORD, _QWORD, __int64, __int128 *); // rax
  int v16; // eax
  __int64 (__fastcall *v17)(_QWORD, __int64, __int64, __int128 *); // rax
  __int64 v18; // rdx
  size_t v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ecx
  bool v23; // al
  __int64 (__fastcall *v24)(_QWORD, _QWORD, _QWORD, CHAR *); // rax
  int v25; // eax
  __int64 (__fastcall *v26)(_QWORD, _QWORD, _QWORD, CHAR *); // rax
  unsigned __int64 v27; // rsi
  int v28; // eax
  unsigned __int64 cchWideChar; // rsi
  unsigned __int64 v30; // rax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v32; // rbp
  PSGSI1::EnumPubsByAddr *v33; // rbx
  PSGSI1::EnumPubsByAddr **v34; // rsi
  PSGSI1::EnumPubsByAddr *v35; // rcx
  PSGSI1::EnumPubsByAddr *v36; // rsi
  __int64 (__fastcall *v37)(_QWORD, __int64); // rax
  void (__fastcall *v38)(_QWORD, PSGSI1::EnumPubsByAddr *); // rax
  _QWORD v39[2]; // [rsp+30h] [rbp-188h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-178h] BYREF
  CHAR MultiByteStr[272]; // [rsp+50h] [rbp-168h] BYREF

  v39[1] = -2;
  v10 = 0;
  v11 = 0;
  v12 = a6;
  if ( a6 >= 0xC )
  {
    while ( 1 )
    {
      if ( a2 )
      {
        Buffer = *(_OWORD *)&a2[v11];
      }
      else
      {
        v13 = a4 + v11;
        if ( a3 )
        {
          if ( fseek(a3, v13, 0) )
            return;
          v14 = fread(&Buffer, 1u, 0xCu, a3) == 12;
        }
        else
        {
          v15 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int128 *))*((_QWORD *)this + 267);
          if ( v15 )
          {
            v16 = v15(*((_QWORD *)this + 257), v13, 12, &Buffer);
          }
          else
          {
            v17 = (__int64 (__fastcall *)(_QWORD, __int64, __int64, __int128 *))*((_QWORD *)this + 268);
            if ( !v17 )
              return;
            v18 = v11 + a5;
            if ( !(_DWORD)v18 )
              return;
            v16 = v17(*((_QWORD *)this + 257), v18, 12, &Buffer);
          }
          v14 = v16 >= 0;
        }
        if ( !v14 )
          return;
      }
      if ( DWORD1(Buffer) < 0xC || DWORD1(Buffer) > v12 )
        return;
      if ( (_DWORD)Buffer == 1 && !BYTE8(Buffer) )
        break;
      v12 -= DWORD1(Buffer);
      if ( v12 < 0xC )
        return;
      v11 += DWORD1(Buffer);
    }
    v19 = DWORD1(Buffer) - 12LL;
    if ( v19 <= 0x108 )
    {
      if ( a2 )
      {
        memcpy_0(MultiByteStr, &a2[v11 + 12], DWORD1(Buffer) - 12LL);
      }
      else
      {
        v22 = v11 + a4 + 12;
        if ( a3 )
        {
          if ( fseek(a3, v22, 0) )
            return;
          v23 = fread(MultiByteStr, 1u, v19, a3) == v19;
        }
        else
        {
          v24 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, CHAR *))*((_QWORD *)this + 267);
          if ( v24 )
          {
            v25 = v24(*((_QWORD *)this + 257), v22, (unsigned int)v19, MultiByteStr);
          }
          else
          {
            v26 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, CHAR *))*((_QWORD *)this + 268);
            if ( !v26 || !(v11 + a5 + 12) )
              return;
            v25 = v26(*((_QWORD *)this + 257), v11 + a5 + 12, (unsigned int)v19, MultiByteStr);
          }
          v23 = v25 >= 0;
        }
        if ( !v23 )
          return;
      }
      v27 = v19 - 1;
      if ( v27 >= 0x108 )
        _report_rangecheckfailure(v21, v20);
      MultiByteStr[v27] = 0;
      v28 = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
      cchWideChar = v28;
      if ( v28 > 0 )
      {
        v30 = 2LL * v28;
        if ( !is_mul_ok(cchWideChar, 2u) )
          v30 = -1;
        lpWideCharStr = (WCHAR *)operator new[](v30, (const struct std::nothrow_t *)&std::nothrow);
        v32 = lpWideCharStr;
        v33 = (PSGSI1::EnumPubsByAddr *)lpWideCharStr;
        v39[0] = lpWideCharStr;
        if ( lpWideCharStr )
        {
          if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, cchWideChar) <= 0 )
            goto LABEL_39;
          v34 = (PSGSI1::EnumPubsByAddr **)((char *)this + 3328);
          if ( (_QWORD *)((char *)this + 3328) != v39 )
          {
            v33 = 0;
            v39[0] = 0;
            v35 = *v34;
            *v34 = (PSGSI1::EnumPubsByAddr *)v32;
            if ( v35 )
              PSGSI1::EnumPubsByAddr::release(v35);
          }
          v36 = *v34;
          if ( !*((_BYTE *)this + 2088) )
          {
            *((_BYTE *)this + 2088) = 1;
            v37 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
            if ( v37 )
              v10 = v37(*((_QWORD *)this + 257), 9);
            *((_QWORD *)this + 262) = v10;
          }
          v38 = (void (__fastcall *)(_QWORD, PSGSI1::EnumPubsByAddr *))*((_QWORD *)this + 262);
          if ( v38 )
            v38(*((_QWORD *)this + 257), v36);
          if ( v33 )
LABEL_39:
            PSGSI1::EnumPubsByAddr::release(v33);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180087f00  push    rbx
0x180087f02  push    rbp
0x180087f03  push    rsi
0x180087f04  push    rdi
0x180087f05  push    r12
0x180087f07  push    r13
0x180087f09  push    r14
0x180087f0b  push    r15
0x180087f0d  sub     rsp, 178h
0x180087f14  mov     [rsp+1B8h+var_180], 0FFFFFFFFFFFFFFFEh
0x180087f1d  mov     rax, cs:__security_cookie
0x180087f24  xor     rax, rsp
0x180087f27  mov     [rsp+1B8h+var_58], rax
0x180087f2f  mov     r12d, r9d
0x180087f32  mov     rbp, r8
0x180087f35  mov     r14, rdx
0x180087f38  mov     rdi, rcx
0x180087f3b  xor     r13d, r13d
0x180087f3e  mov     ebx, r13d
0x180087f41  mov     esi, [rsp+1B8h+arg_28]
0x180087f48  cmp     esi, 0Ch
0x180087f4b  jb      loc_1800881BC
0x180087f51  mov     r15d, [rsp+1B8h+arg_20]
0x180087f59  nop     dword ptr [rax+00000000h]
0x180087f60  test    r14, r14
0x180087f63  jz      short loc_180087F76
0x180087f65  mov     eax, ebx
0x180087f67  movups  xmm0, xmmword ptr [rax+r14]
0x180087f6c  movups  [rsp+1B8h+Buffer], xmm0
0x180087f71  jmp     loc_180088020
0x180087f76  lea     ecx, [r12+rbx]
0x180087f7a  test    rbp, rbp
0x180087f7d  jz      short loc_180087FB7
0x180087f7f  xor     r8d, r8d; Origin
0x180087f82  mov     edx, ecx; Offset
0x180087f84  mov     rcx, rbp; Stream
0x180087f87  call    cs:__imp_fseek
0x180087f8d  test    eax, eax
0x180087f8f  jnz     loc_1800881BC
0x180087f95  mov     r9, rbp; Stream
0x180087f98  mov     edx, 1; ElementSize
0x180087f9d  mov     r8d, 0Ch; ElementCount
0x180087fa3  lea     rcx, [rsp+1B8h+Buffer]; Buffer
0x180087fa8  call    cs:__imp_fread
0x180087fae  cmp     rax, 0Ch
0x180087fb2  setz    al
0x180087fb5  jmp     short loc_180088018
0x180087fb7  mov     rax, [rdi+858h]
0x180087fbe  test    rax, rax
0x180087fc1  jz      short loc_180087FDF
0x180087fc3  mov     edx, ecx
0x180087fc5  lea     r9, [rsp+1B8h+Buffer]
0x180087fca  mov     r8d, 0Ch
0x180087fd0  mov     rcx, [rdi+808h]
0x180087fd7  call    cs:__guard_dispatch_icall_fptr
0x180087fdd  jmp     short loc_180088013
0x180087fdf  mov     rax, [rdi+860h]
0x180087fe6  test    rax, rax
0x180087fe9  jz      loc_1800881BC
0x180087fef  lea     edx, [rbx+r15]
0x180087ff3  test    edx, edx
0x180087ff5  jz      loc_1800881BC
0x180087ffb  lea     r9, [rsp+1B8h+Buffer]
0x180088000  mov     r8d, 0Ch
0x180088006  mov     rcx, [rdi+808h]
0x18008800d  call    cs:__guard_dispatch_icall_fptr
0x180088013  shr     eax, 1Fh
0x180088016  xor     al, 1
0x180088018  test    al, al
0x18008801a  jz      loc_1800881BC
0x180088020  mov     eax, dword ptr [rsp+1B8h+Buffer+4]
0x180088024  cmp     eax, 0Ch
0x180088027  jb      loc_1800881BC
0x18008802d  cmp     eax, esi
0x18008802f  ja      loc_1800881BC
0x180088035  cmp     dword ptr [rsp+1B8h+Buffer], 1
0x18008803a  jnz     short loc_180088043
0x18008803c  cmp     byte ptr [rsp+1B8h+Buffer+8], r13b
0x180088041  jz      short loc_180088055
0x180088043  sub     esi, eax
0x180088045  cmp     esi, 0Ch
0x180088048  jb      loc_1800881BC
0x18008804e  add     ebx, eax
0x180088050  jmp     loc_180087F60
0x180088055  lea     rsi, [rax-0Ch]
0x180088059  cmp     rsi, 108h
0x180088060  ja      loc_1800881BC
0x180088066  test    r14, r14
0x180088069  jz      short loc_180088086
0x18008806b  mov     edx, ebx
0x18008806d  add     rdx, 0Ch
0x180088071  add     rdx, r14; Src
0x180088074  mov     r8, rsi; Size
0x180088077  lea     rcx, [rsp+1B8h+MultiByteStr]; void *
0x18008807c  call    memcpy_0
0x180088081  jmp     loc_180088129
0x180088086  lea     ecx, [r12+0Ch]
0x18008808b  add     ecx, ebx
0x18008808d  test    rbp, rbp
0x180088090  jz      short loc_1800880C6
0x180088092  xor     r8d, r8d; Origin
0x180088095  mov     edx, ecx; Offset
0x180088097  mov     rcx, rbp; Stream
0x18008809a  call    cs:__imp_fseek
0x1800880a0  test    eax, eax
0x1800880a2  jnz     loc_1800881BC
0x1800880a8  mov     r9, rbp; Stream
0x1800880ab  mov     r8, rsi; ElementCount
0x1800880ae  mov     edx, 1; ElementSize
0x1800880b3  lea     rcx, [rsp+1B8h+MultiByteStr]; Buffer
0x1800880b8  call    cs:__imp_fread
0x1800880be  cmp     rax, rsi
0x1800880c1  setz    al
0x1800880c4  jmp     short loc_180088121
0x1800880c6  mov     rax, [rdi+858h]
0x1800880cd  test    rax, rax
0x1800880d0  jz      short loc_1800880EB
0x1800880d2  mov     r8d, esi
0x1800880d5  mov     edx, ecx
0x1800880d7  lea     r9, [rsp+1B8h+MultiByteStr]
0x1800880dc  mov     rcx, [rdi+808h]
0x1800880e3  call    cs:__guard_dispatch_icall_fptr
0x1800880e9  jmp     short loc_18008811C
0x1800880eb  mov     rax, [rdi+860h]
0x1800880f2  test    rax, rax
0x1800880f5  jz      loc_1800881BC
0x1800880fb  lea     edx, [r15+0Ch]
0x1800880ff  add     edx, ebx
0x180088101  jz      loc_1800881BC
0x180088107  mov     r8d, esi
0x18008810a  lea     r9, [rsp+1B8h+MultiByteStr]
0x18008810f  mov     rcx, [rdi+808h]
0x180088116  call    cs:__guard_dispatch_icall_fptr
0x18008811c  shr     eax, 1Fh
0x18008811f  xor     al, 1
0x180088121  test    al, al
0x180088123  jz      loc_1800881BC
0x180088129  dec     rsi
0x18008812c  cmp     rsi, 108h
0x180088133  jnb     loc_18008826F
0x180088139  mov     [rsp+rsi+1B8h+MultiByteStr], r13b
0x18008813e  mov     [rsp+1B8h+cchWideChar], r13d; cchWideChar
0x180088143  mov     [rsp+1B8h+lpWideCharStr], r13; lpWideCharStr
0x180088148  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18008814f  mov     r9d, r14d; cbMultiByte
0x180088152  lea     r8, [rsp+1B8h+MultiByteStr]; lpMultiByteStr
0x180088157  xor     edx, edx; dwFlags
0x180088159  xor     ecx, ecx; CodePage
0x18008815b  call    cs:__imp_MultiByteToWideChar
0x180088161  movsxd  rsi, eax
0x180088164  test    eax, eax
0x180088166  jle     short loc_1800881BC
0x180088168  mov     eax, 2
0x18008816d  mul     rsi
0x180088170  cmovb   rax, r14
0x180088174  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008817b  mov     rcx, rax; unsigned __int64
0x18008817e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180088183  mov     rbp, rax
0x180088186  mov     rbx, rax
0x180088189  mov     [rsp+1B8h+var_188], rax
0x18008818e  test    rax, rax
0x180088191  jnz     short loc_180088195
0x180088193  jmp     short loc_1800881BC
0x180088195  mov     [rsp+1B8h+cchWideChar], esi; cchWideChar
0x180088199  mov     [rsp+1B8h+lpWideCharStr], rbx; lpWideCharStr
0x18008819e  mov     r9d, r14d; cbMultiByte
0x1800881a1  lea     r8, [rsp+1B8h+MultiByteStr]; lpMultiByteStr
0x1800881a6  xor     edx, edx; dwFlags
0x1800881a8  xor     ecx, ecx; CodePage
0x1800881aa  call    cs:__imp_MultiByteToWideChar
0x1800881b0  test    eax, eax
0x1800881b2  jg      short loc_1800881E0
0x1800881b4  mov     rcx, rbx; this
0x1800881b7  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800881bc  mov     rcx, [rsp+1B8h+var_58]
0x1800881c4  xor     rcx, rsp; StackCookie
0x1800881c7  call    __security_check_cookie
0x1800881cc  add     rsp, 178h
0x1800881d3  pop     r15
0x1800881d5  pop     r14
0x1800881d7  pop     r13
0x1800881d9  pop     r12
0x1800881db  pop     rdi
0x1800881dc  pop     rsi
0x1800881dd  pop     rbp
0x1800881de  pop     rbx
0x1800881df  retn
0x1800881e0  lea     rsi, [rdi+0D00h]
0x1800881e7  lea     rax, [rsp+1B8h+var_188]
0x1800881ec  cmp     rsi, rax
0x1800881ef  jz      short loc_180088209
0x1800881f1  mov     rbx, r13
0x1800881f4  mov     [rsp+1B8h+var_188], rbx
0x1800881f9  mov     rcx, [rsi]; this
0x1800881fc  mov     [rsi], rbp
0x1800881ff  test    rcx, rcx
0x180088202  jz      short loc_180088209
0x180088204  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180088209  mov     rsi, [rsi]
0x18008820c  cmp     byte ptr [rdi+828h], 0
0x180088213  jnz     short loc_180088244
0x180088215  mov     byte ptr [rdi+828h], 1
0x18008821c  mov     rax, [rdi+810h]
0x180088223  test    rax, rax
0x180088226  jz      short loc_18008823D
0x180088228  mov     edx, 9
0x18008822d  mov     rcx, [rdi+808h]
0x180088234  call    cs:__guard_dispatch_icall_fptr
0x18008823a  mov     r13, rax
0x18008823d  mov     [rdi+830h], r13
0x180088244  mov     rax, [rdi+830h]
0x18008824b  test    rax, rax
0x18008824e  jz      short loc_180088261
0x180088250  mov     rdx, rsi
0x180088253  mov     rcx, [rdi+808h]
0x18008825a  call    cs:__guard_dispatch_icall_fptr
0x180088260  nop
0x180088261  test    rbx, rbx
0x180088264  jz      loc_1800881BC
0x18008826a  jmp     loc_1800881B4
0x18008826f  call    __report_rangecheckfailure
```
