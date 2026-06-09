# SString::VPrintf(ushort const *,char *)

- ea: `0x180032678`
- end: `0x180032871`
- name: `?VPrintf@SString@@QEAAXPEBGPEAD@Z`
- size: `505`
- prototype: `void(SString *__hidden this, const unsigned __int16 *, char *)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002d624`
- `0x18002d878`
- `0x18002e1d0`
- `0x18002e308`
- `0x18002e418`
- `0x180032654`
- `0x180032948`
- `0x18003b188`

## callees

- `0x1800177e8`
- `0x180030568`
- `0x180030ab8`
- `0x180032678`
- `0x180032f44`
- `0x180034fd4`
- `0x1800351fc`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x1800326e1`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x1800327aa`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x1800326e1`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x1800327aa`
- `ucrtbase_clr0400!_errno` at `0x180032779`
- `ucrtbase_clr0400!_errno` at `0x1800327c0`
- `ucrtbase_clr0400!_errno` at `0x1800327cf`
- `ucrtbase_clr0400!_errno` at `0x1800327da`
- `ucrtbase_clr0400!_errno` at `0x1800327e5`
- `ucrtbase_clr0400!_errno` at `0x180032779`
- `ucrtbase_clr0400!_errno` at `0x1800327c0`
- `ucrtbase_clr0400!_errno` at `0x1800327cf`
- `ucrtbase_clr0400!_errno` at `0x1800327da`
- `ucrtbase_clr0400!_errno` at `0x1800327e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SString::VPrintf(SString *this, const unsigned __int16 *a2, va_list a3)
{
  unsigned int v6; // ebx
  unsigned __int64 *v7; // rax
  int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // ebx
  unsigned __int64 *v11; // r15
  _DWORD v12[2]; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+48h] [rbp-18h]
  void *lpMem; // [rsp+50h] [rbp-10h]

  if ( *(_DWORD *)this >> ((*((_DWORD *)this + 2) & 1) == 0) == 1 )
    goto LABEL_5;
  v6 = *(_DWORD *)this >> ((*((_DWORD *)this + 2) & 1) == 0);
  v7 = _local_stdio_printf_options();
  v8 = __stdio_common_vsnwprintf_s(*v7, *((wchar_t **)this + 2), v6, 0xFFFFFFFFFFFFFFFFuLL, a2, 0, a3);
  if ( v8 < 0 )
    v8 = -1;
  if ( v8 < 0 )
  {
LABEL_5:
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = (*(_DWORD *)this >> ((*((_DWORD *)this + 2) & 1) == 0)) - 1;
    if ( (int)v9 + 1 >= v10 )
      v10 = v9 + 1;
    if ( v10 < 0x14 )
      v10 = 20;
    v11 = _local_stdio_printf_options();
    while ( 1 )
    {
      v10 *= 2;
      SString::Resize(this, v10, 4);
      *_errno() = 0;
      v8 = __stdio_common_vsnwprintf_s(
             *v11,
             *((wchar_t **)this + 2),
             (unsigned __int64)*(unsigned int *)this >> ((*((_DWORD *)this + 2) & 1) == 0),
             0xFFFFFFFFFFFFFFFFuLL,
             a2,
             0,
             a3);
      if ( v8 < 0 )
        v8 = -1;
      if ( v8 >= 0 )
        break;
      if ( *_errno() == 12 )
        ThrowOutOfMemory();
      if ( *_errno() && *_errno() != 9 && *_errno() != 34 )
        ThrowHR(-2147023783);
    }
  }
  SString::Resize(this, (unsigned int)v8, 4);
  v12[0] = 2;
  v12[1] = 2;
  v13 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set((SString *)v12, a2);
  if ( (v13 & 8) != 0 )
    operator delete(lpMem);
}

```

## disassembly

```asm
0x180032678  mov     rax, rsp
0x18003267b  mov     [rax+8], rbx
0x18003267f  mov     [rax+10h], rsi
0x180032683  mov     [rax+18h], rdi
0x180032687  mov     [rax+20h], r12
0x18003268b  push    rbp
0x18003268c  push    r14
0x18003268e  push    r15
0x180032690  mov     rbp, rsp
0x180032693  sub     rsp, 60h
0x180032697  mov     r14, r8
0x18003269a  mov     rsi, rdx
0x18003269d  mov     rdi, rcx
0x1800326a0  mov     ecx, [rcx+8]
0x1800326a3  not     ecx
0x1800326a5  and     ecx, 1
0x1800326a8  mov     r9d, [rdi]
0x1800326ab  shr     r9d, cl
0x1800326ae  lea     eax, [r9-1]
0x1800326b2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800326b6  xor     r12d, r12d
0x1800326b9  test    eax, eax
0x1800326bb  jz      short loc_180032731
0x1800326bd  mov     ebx, r9d
0x1800326c0  call    __local_stdio_printf_options
0x1800326c5  mov     [rsp+60h+ArgList], r14; ArgList
0x1800326ca  mov     [rsp+60h+Locale], r12; Locale
0x1800326cf  mov     [rsp+60h+Format], rsi; Format
0x1800326d4  mov     r9, r15; MaxCount
0x1800326d7  mov     r8d, ebx; BufferCount
0x1800326da  mov     rdx, [rdi+10h]; Buffer
0x1800326de  mov     rcx, [rax]; Options
0x1800326e1  call    cs:__imp___stdio_common_vsnwprintf_s
0x1800326e7  test    eax, eax
0x1800326e9  cmovs   eax, r15d
0x1800326ed  test    eax, eax
0x1800326ef  js      short loc_180032731
0x1800326f1  lea     r9d, [r15+2]
0x1800326f5  lea     r8d, [r15+5]
0x1800326f9  mov     edx, eax
0x1800326fb  mov     rcx, rdi
0x1800326fe  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180032703  lea     eax, [r15+3]
0x180032707  mov     [rbp+var_20], eax
0x18003270a  mov     [rbp+var_1C], eax
0x18003270d  mov     [rbp+var_18], 10h
0x180032714  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18003271b  mov     [rbp+lpMem], rax
0x18003271f  mov     rdx, rsi; unsigned __int16 *
0x180032722  lea     rcx, [rbp+var_20]; this
0x180032726  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18003272b  nop
0x18003272c  jmp     loc_180032833
0x180032731  mov     rax, r15
0x180032734  inc     rax
0x180032737  cmp     [rsi+rax*2], r12w
0x18003273c  jnz     short loc_180032734
0x18003273e  lea     edx, [rax+1]
0x180032741  mov     ecx, [rdi+8]
0x180032744  not     ecx
0x180032746  and     ecx, 1
0x180032749  mov     ebx, [rdi]
0x18003274b  shr     ebx, cl
0x18003274d  dec     ebx
0x18003274f  cmp     edx, ebx
0x180032751  cmovnb  ebx, edx
0x180032754  mov     eax, 14h
0x180032759  cmp     ebx, eax
0x18003275b  cmovb   ebx, eax
0x18003275e  call    __local_stdio_printf_options
0x180032763  mov     r15, rax
0x180032766  add     ebx, ebx
0x180032768  xor     r9d, r9d
0x18003276b  lea     r8d, [r9+4]
0x18003276f  mov     edx, ebx
0x180032771  mov     rcx, rdi
0x180032774  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180032779  call    cs:__imp__errno
0x18003277f  mov     [rax], r12d
0x180032782  mov     ecx, [rdi+8]
0x180032785  not     ecx
0x180032787  and     cl, 1
0x18003278a  mov     r8d, [rdi]
0x18003278d  shr     r8, cl; BufferCount
0x180032790  mov     [rsp+60h+ArgList], r14; ArgList
0x180032795  mov     [rsp+60h+Locale], r12; Locale
0x18003279a  mov     [rsp+60h+Format], rsi; Format
0x18003279f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800327a3  mov     rdx, [rdi+10h]; Buffer
0x1800327a7  mov     rcx, [r15]; Options
0x1800327aa  call    cs:__imp___stdio_common_vsnwprintf_s
0x1800327b0  test    eax, eax
0x1800327b2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800327b9  cmovs   eax, ecx
0x1800327bc  test    eax, eax
0x1800327be  jns     short loc_1800327F5
0x1800327c0  call    cs:__imp__errno
0x1800327c6  cmp     dword ptr [rax], 0Ch
0x1800327c9  jz      loc_180032860
0x1800327cf  call    cs:__imp__errno
0x1800327d5  cmp     [rax], r12d
0x1800327d8  jz      short loc_180032766
0x1800327da  call    cs:__imp__errno
0x1800327e0  cmp     dword ptr [rax], 9
0x1800327e3  jz      short loc_180032766
0x1800327e5  call    cs:__imp__errno
0x1800327eb  cmp     dword ptr [rax], 22h ; '"'
0x1800327ee  jnz     short loc_180032866
0x1800327f0  jmp     loc_180032766
0x1800327f5  mov     r9d, 1
0x1800327fb  lea     r8d, [r9+3]
0x1800327ff  mov     edx, eax
0x180032801  mov     rcx, rdi
0x180032804  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180032809  mov     eax, 2
0x18003280e  mov     [rbp+var_20], eax
0x180032811  mov     [rbp+var_1C], eax
0x180032814  mov     [rbp+var_18], 10h
0x18003281b  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180032822  mov     [rbp+lpMem], rax
0x180032826  mov     rdx, rsi; unsigned __int16 *
0x180032829  lea     rcx, [rbp+var_20]; this
0x18003282d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180032832  nop
0x180032833  test    byte ptr [rbp+var_18], 8
0x180032837  jz      short loc_180032842
0x180032839  mov     rcx, [rbp+lpMem]; lpMem
0x18003283d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032842  lea     r11, [rsp+60h+var_s0]
0x180032847  mov     rbx, [r11+20h]
0x18003284b  mov     rsi, [r11+28h]
0x18003284f  mov     rdi, [r11+30h]
0x180032853  mov     r12, [r11+38h]
0x180032857  mov     rsp, r11
0x18003285a  pop     r15
0x18003285c  pop     r14
0x18003285e  pop     rbp
0x18003285f  retn
0x180032860  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
0x180032866  mov     ecx, 80070459h; int
0x18003286b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
