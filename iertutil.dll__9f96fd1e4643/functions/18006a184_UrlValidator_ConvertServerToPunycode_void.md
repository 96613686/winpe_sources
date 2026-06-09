# UrlValidator::ConvertServerToPunycode(void)

- ea: `0x18006a184`
- end: `0x18006a40c`
- name: `?ConvertServerToPunycode@UrlValidator@@QEAA_NXZ`
- size: `648`
- prototype: `bool __fastcall(UrlValidator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006b994`

## callees

- `0x18006a184`
- `0x18006a4e8`
- `0x180083c10`

## import_xrefs

- `msvcrt!memmove_s` at `0x18006a3b7`
- `msvcrt!memmove_s` at `0x18006a3b7`
- `msvcrt!memcpy_s` at `0x18006a223`
- `msvcrt!memcpy_s` at `0x18006a362`
- `msvcrt!memcpy_s` at `0x18006a3d1`
- `msvcrt!memcpy_s` at `0x18006a223`
- `msvcrt!memcpy_s` at `0x18006a362`
- `msvcrt!memcpy_s` at `0x18006a3d1`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18006a2fa`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x18006a2fa`

## pseudocode

```c
char __fastcall UrlValidator::ConvertServerToPunycode(UrlValidator *this)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  unsigned int v4; // ecx
  char v5; // r8
  unsigned int i; // ebp
  __int64 v7; // rax
  unsigned __int16 v8; // ax
  unsigned int v9; // esi
  int v10; // eax
  unsigned __int64 v11; // rdx
  __int64 v12; // r9
  WCHAR *v13; // rcx
  WCHAR *v14; // r8
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rsi
  unsigned int v18; // ecx
  __int64 v19; // rdx
  unsigned int v21[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Destination[256]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR ASCIICharStr[256]; // [rsp+240h] [rbp-238h] BYREF

  if ( !*((_DWORD *)this + 2) || !*(_BYTE *)this )
    return 1;
  if ( *((_DWORD *)this + 2) > 0xFFu )
    return 0;
  v2 = *((int *)this + 1028);
  if ( (unsigned int)v2 > 2 && (_DWORD)v2 != 7 && (unsigned int)(v2 - 8) > 1 )
    return 1;
  v3 = LODWORD(qword_1801073A8[2 * v2]);
  memcpy_s(Destination, 0x1FEu, (char *)this + 12, 2 * v3);
  v4 = v3;
  v21[0] = v3;
  v5 = 0;
  for ( i = v3; ; ++i )
  {
    v7 = *((unsigned int *)this + 2);
    if ( i > (unsigned int)v7 )
      break;
    v8 = *((_WORD *)this + i + 6);
    if ( v8 <= 0x7Fu )
    {
      if ( v8 == 46 )
        goto LABEL_18;
    }
    else
    {
      v5 = 1;
    }
    if ( v8 != 12290 && v8 != 0xFF0E && v8 != 0xFF61 )
    {
      if ( i != *((_DWORD *)this + 2) && v8 != 58 )
        continue;
      goto LABEL_19;
    }
LABEL_18:
    *((_WORD *)this + i + 6) = 46;
LABEL_19:
    v9 = i - v4;
    if ( v5 )
    {
      if ( *((_WORD *)this + v4 + 6) == 46 )
      {
        if ( (unsigned int)(255 - v3) <= 1 )
          return 0;
        Destination[v3] = 46;
        IncrementIndex(v21);
        v4 = v21[0];
        v3 = (unsigned int)(v3 + 1);
        --v9;
      }
      v10 = IdnToAscii(1u, (LPCWSTR)this + v4 + 6, v9, ASCIICharStr, 255);
      v9 = v10;
      if ( v10 <= 0 )
        return 0;
      v11 = 255LL - (unsigned int)v3;
      if ( v11 < (unsigned int)v10 )
        return 0;
      v12 = v10;
      v13 = &Destination[v3];
      v14 = ASCIICharStr;
    }
    else
    {
      v11 = 255LL - (unsigned int)v3;
      v12 = v9;
      if ( v9 > v11 )
        return 0;
      v15 = v4 + 6LL;
      v13 = &Destination[v3];
      v14 = (WCHAR *)((char *)this + 2 * v15);
    }
    if ( memcpy_s(v13, 2 * v11, v14, 2 * v12) )
      return 0;
    v3 = v9 + (unsigned int)v3;
    v4 = i;
    v21[0] = i;
    v5 = 0;
  }
  if ( (unsigned int)v3 <= (unsigned int)v7 )
    return 1;
  v16 = *((_DWORD *)this + 1);
  if ( (unsigned int)v7 <= v16 )
  {
    v17 = (unsigned int)(v3 - v7);
    if ( (int)v3 - (int)v7 >= 0 )
    {
      v18 = v16 - v7;
      v19 = 2048 - v18 - (unsigned int)v7;
      if ( v18 <= (unsigned int)v19 )
      {
        memmove_s((char *)this + 2 * v7 + 2 * v17 + 12, 2 * v19, (char *)this + 2 * v7 + 12, 2LL * v18);
        *((_DWORD *)this + 1) += v17;
        memcpy_s((char *)this + 12, 2LL * (unsigned int)v3, Destination, 2LL * (unsigned int)v3);
        *((_DWORD *)this + 2) = v3;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006a184  mov     [rsp+arg_8], rbx
0x18006a189  mov     [rsp+arg_10], rbp
0x18006a18e  push    rsi
0x18006a18f  push    rdi
0x18006a190  push    r12
0x18006a192  push    r13
0x18006a194  push    r14
0x18006a196  sub     rsp, 450h
0x18006a19d  mov     rax, cs:__security_cookie
0x18006a1a4  xor     rax, rsp
0x18006a1a7  mov     [rsp+478h+var_38], rax
0x18006a1af  cmp     dword ptr [rcx+8], 0
0x18006a1b3  mov     rdi, rcx
0x18006a1b6  jz      loc_18006A3DA
0x18006a1bc  cmp     byte ptr [rcx], 0
0x18006a1bf  jz      loc_18006A3DA
0x18006a1c5  mov     r12d, 0FFh
0x18006a1cb  cmp     [rcx+8], r12d
0x18006a1cf  ja      loc_18006A408
0x18006a1d5  movsxd  rdx, dword ptr [rcx+1010h]
0x18006a1dc  mov     ecx, edx
0x18006a1de  test    edx, edx
0x18006a1e0  jz      short loc_18006A1FF
0x18006a1e2  sub     ecx, 1
0x18006a1e5  jz      short loc_18006A1FF
0x18006a1e7  sub     ecx, 1
0x18006a1ea  jz      short loc_18006A1FF
0x18006a1ec  sub     ecx, 5
0x18006a1ef  jz      short loc_18006A1FF
0x18006a1f1  sub     ecx, 1
0x18006a1f4  jz      short loc_18006A1FF
0x18006a1f6  cmp     ecx, 1
0x18006a1f9  jnz     loc_18006A3DA
0x18006a1ff  mov     rax, rdx
0x18006a202  lea     rbx, qword_1801073A8
0x18006a209  add     rax, rax
0x18006a20c  lea     r8, [rdi+0Ch]; Source
0x18006a210  mov     edx, 1FEh; DestinationSize
0x18006a215  lea     rcx, [rsp+478h+Destination]; Destination
0x18006a21a  mov     ebx, [rbx+rax*8]
0x18006a21d  mov     r9d, ebx
0x18006a220  add     r9, r9; SourceSize
0x18006a223  call    cs:__imp_memcpy_s
0x18006a229  mov     ecx, ebx
0x18006a22b  mov     [rsp+478h+var_448], ebx
0x18006a22f  xor     r8b, r8b
0x18006a232  mov     ebp, ebx
0x18006a234  mov     r13d, 2Eh ; '.'
0x18006a23a  mov     eax, [rdi+8]
0x18006a23d  cmp     ebp, eax
0x18006a23f  ja      loc_18006A382
0x18006a245  mov     edx, ebp
0x18006a247  movzx   eax, word ptr [rdi+rdx*2+0Ch]
0x18006a24c  cmp     ax, 7Fh
0x18006a250  jbe     short loc_18006A257
0x18006a252  mov     r8b, 1
0x18006a255  jmp     short loc_18006A25D
0x18006a257  cmp     ax, r13w
0x18006a25b  jz      short loc_18006A298
0x18006a25d  mov     r9d, 3002h
0x18006a263  cmp     ax, r9w
0x18006a267  jz      short loc_18006A298
0x18006a269  mov     r9d, 0FF0Eh
0x18006a26f  cmp     ax, r9w
0x18006a273  jz      short loc_18006A298
0x18006a275  mov     r9d, 0FF61h
0x18006a27b  cmp     ax, r9w
0x18006a27f  jz      short loc_18006A298
0x18006a281  cmp     ax, r13w
0x18006a285  jz      short loc_18006A29E
0x18006a287  cmp     ebp, [rdi+8]
0x18006a28a  jz      short loc_18006A29E
0x18006a28c  cmp     ax, 3Ah ; ':'
0x18006a290  jnz     loc_18006A37B
0x18006a296  jmp     short loc_18006A29E
0x18006a298  mov     [rdi+rdx*2+0Ch], r13w
0x18006a29e  mov     esi, ebp
0x18006a2a0  sub     esi, ecx
0x18006a2a2  test    r8b, r8b
0x18006a2a5  jz      loc_18006A334
0x18006a2ab  mov     eax, ecx
0x18006a2ad  cmp     [rdi+rax*2+0Ch], r13w
0x18006a2b3  jnz     short loc_18006A2DB
0x18006a2b5  mov     eax, r12d
0x18006a2b8  sub     eax, ebx
0x18006a2ba  cmp     eax, 1
0x18006a2bd  jbe     loc_18006A408
0x18006a2c3  lea     rcx, [rsp+478h+var_448]
0x18006a2c8  mov     [rsp+rbx*2+478h+Destination], r13w
0x18006a2ce  call    IncrementIndex
0x18006a2d3  mov     ecx, [rsp+478h+var_448]
0x18006a2d7  inc     ebx
0x18006a2d9  dec     esi
0x18006a2db  mov     eax, ecx
0x18006a2dd  lea     r9, [rsp+478h+ASCIICharStr]; lpASCIICharStr
0x18006a2e5  add     rax, 6
0x18006a2e9  mov     [rsp+478h+cchASCIIChar], r12d; cchASCIIChar
0x18006a2ee  mov     r8d, esi; cchUnicodeChar
0x18006a2f1  mov     ecx, 1; dwFlags
0x18006a2f6  lea     rdx, [rdi+rax*2]; lpUnicodeCharStr
0x18006a2fa  call    cs:__imp_IdnToAscii
0x18006a300  movsxd  rsi, eax
0x18006a303  test    eax, eax
0x18006a305  jle     loc_18006A408
0x18006a30b  mov     ecx, ebx
0x18006a30d  mov     rdx, r12
0x18006a310  sub     rdx, rcx
0x18006a313  mov     eax, esi
0x18006a315  cmp     rdx, rax
0x18006a318  jb      loc_18006A408
0x18006a31e  lea     rax, [rsp+478h+Destination]
0x18006a323  mov     r9, rsi
0x18006a326  lea     rcx, [rax+rbx*2]
0x18006a32a  lea     r8, [rsp+478h+ASCIICharStr]
0x18006a332  jmp     short loc_18006A35C
0x18006a334  mov     r10d, ebx
0x18006a337  mov     rdx, r12
0x18006a33a  sub     rdx, r10
0x18006a33d  mov     r9d, esi
0x18006a340  cmp     r9, rdx
0x18006a343  ja      loc_18006A408
0x18006a349  mov     eax, ecx
0x18006a34b  lea     rcx, [rsp+478h+Destination]
0x18006a350  add     rax, 6
0x18006a354  lea     rcx, [rcx+rbx*2]; Destination
0x18006a358  lea     r8, [rdi+rax*2]; Source
0x18006a35c  add     r9, r9; SourceSize
0x18006a35f  add     rdx, rdx; DestinationSize
0x18006a362  call    cs:__imp_memcpy_s
0x18006a368  test    eax, eax
0x18006a36a  jnz     loc_18006A408
0x18006a370  add     ebx, esi
0x18006a372  mov     ecx, ebp
0x18006a374  mov     [rsp+478h+var_448], ecx
0x18006a378  xor     r8b, r8b
0x18006a37b  inc     ebp
0x18006a37d  jmp     loc_18006A23A
0x18006a382  cmp     ebx, eax
0x18006a384  jbe     short loc_18006A3DA
0x18006a386  mov     ecx, [rdi+4]
0x18006a389  cmp     eax, ecx
0x18006a38b  ja      short loc_18006A408
0x18006a38d  mov     esi, ebx
0x18006a38f  sub     esi, eax
0x18006a391  js      short loc_18006A408
0x18006a393  sub     ecx, eax
0x18006a395  mov     edx, 800h
0x18006a39a  sub     edx, ecx
0x18006a39c  sub     edx, eax
0x18006a39e  cmp     ecx, edx
0x18006a3a0  ja      short loc_18006A408
0x18006a3a2  mov     r9d, ecx
0x18006a3a5  add     rax, 6
0x18006a3a9  add     r9, r9; SourceSize
0x18006a3ac  add     rdx, rdx; DestinationSize
0x18006a3af  lea     r8, [rdi+rax*2]; Source
0x18006a3b3  lea     rcx, [r8+rsi*2]; Destination
0x18006a3b7  call    cs:__imp_memmove_s
0x18006a3bd  add     [rdi+4], esi
0x18006a3c0  lea     r8, [rsp+478h+Destination]; Source
0x18006a3c5  mov     edx, ebx
0x18006a3c7  lea     rcx, [rdi+0Ch]; Destination
0x18006a3cb  add     rdx, rdx; DestinationSize
0x18006a3ce  mov     r9, rdx; SourceSize
0x18006a3d1  call    cs:__imp_memcpy_s
0x18006a3d7  mov     [rdi+8], ebx
0x18006a3da  mov     al, 1
0x18006a3dc  mov     rcx, [rsp+478h+var_38]
0x18006a3e4  xor     rcx, rsp; StackCookie
0x18006a3e7  call    __security_check_cookie
0x18006a3ec  lea     r11, [rsp+478h+var_28]
0x18006a3f4  mov     rbx, [r11+38h]
0x18006a3f8  mov     rbp, [r11+40h]
0x18006a3fc  mov     rsp, r11
0x18006a3ff  pop     r14
0x18006a401  pop     r13
0x18006a403  pop     r12
0x18006a405  pop     rdi
0x18006a406  pop     rsi
0x18006a407  retn
0x18006a408  xor     al, al
0x18006a40a  jmp     short loc_18006A3DC
```
