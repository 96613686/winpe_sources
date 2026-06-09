# SString::VPrintf(char const *,char *)

- ea: `0x180032464`
- end: `0x180032653`
- name: `?VPrintf@SString@@QEAAXPEBDPEAD@Z`
- size: `495`
- prototype: `void(SString *__hidden this, const char *, char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032440`
- `0x180032874`

## callees

- `0x1800177e8`
- `0x180030568`
- `0x180030bf0`
- `0x180032464`
- `0x180032f44`
- `0x180034fd4`
- `0x1800351fc`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800324c7`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x180032590`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x1800324c7`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x180032590`
- `ucrtbase_clr0400!_errno` at `0x18003255e`
- `ucrtbase_clr0400!_errno` at `0x1800325a6`
- `ucrtbase_clr0400!_errno` at `0x1800325b5`
- `ucrtbase_clr0400!_errno` at `0x1800325c0`
- `ucrtbase_clr0400!_errno` at `0x1800325cb`
- `ucrtbase_clr0400!_errno` at `0x18003255e`
- `ucrtbase_clr0400!_errno` at `0x1800325a6`
- `ucrtbase_clr0400!_errno` at `0x1800325b5`
- `ucrtbase_clr0400!_errno` at `0x1800325c0`
- `ucrtbase_clr0400!_errno` at `0x1800325cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SString::VPrintf(SString *this, const char *a2, va_list a3)
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
  v8 = __stdio_common_vsnprintf_s(*v7, *((char **)this + 2), v6, 0xFFFFFFFFFFFFFFFFuLL, a2, 0, a3);
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
      SString::Resize(this, v10, 7);
      *_errno() = 0;
      v8 = __stdio_common_vsnprintf_s(
             *v11,
             *((char **)this + 2),
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
  SString::Resize(this, (unsigned int)v8, 7);
  v12[0] = 2;
  v12[1] = 2;
  v13 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::SetANSI((SString *)v12, a2);
  if ( (v13 & 8) != 0 )
    operator delete(lpMem);
}

```

## disassembly

```asm
0x180032464  mov     [rsp-18h+arg_0], rbx
0x180032469  mov     [rsp-18h+arg_8], rsi
0x18003246e  mov     [rsp-18h+arg_10], rdi
0x180032473  push    rbp
0x180032474  push    r14
0x180032476  push    r15
0x180032478  mov     rbp, rsp
0x18003247b  sub     rsp, 60h
0x18003247f  mov     r14, r8
0x180032482  mov     rsi, rdx
0x180032485  mov     rdi, rcx
0x180032488  mov     ecx, [rcx+8]
0x18003248b  not     ecx
0x18003248d  and     ecx, 1
0x180032490  mov     r9d, [rdi]
0x180032493  shr     r9d, cl
0x180032496  lea     eax, [r9-1]
0x18003249a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003249e  test    eax, eax
0x1800324a0  jz      short loc_180032517
0x1800324a2  mov     ebx, r9d
0x1800324a5  call    __local_stdio_printf_options
0x1800324aa  mov     [rsp+60h+ArgList], r14; ArgList
0x1800324af  and     [rsp+60h+var_38], 0
0x1800324b5  mov     [rsp+60h+Format], rsi; Format
0x1800324ba  mov     r9, r15; MaxCount
0x1800324bd  mov     r8d, ebx; BufferCount
0x1800324c0  mov     rdx, [rdi+10h]; Buffer
0x1800324c4  mov     rcx, [rax]; Options
0x1800324c7  call    cs:__imp___stdio_common_vsnprintf_s
0x1800324cd  test    eax, eax
0x1800324cf  cmovs   eax, r15d
0x1800324d3  test    eax, eax
0x1800324d5  js      short loc_180032517
0x1800324d7  lea     r9d, [r15+2]
0x1800324db  lea     r8d, [r15+8]
0x1800324df  mov     edx, eax
0x1800324e1  mov     rcx, rdi
0x1800324e4  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x1800324e9  lea     eax, [r15+3]
0x1800324ed  mov     [rbp+var_20], eax
0x1800324f0  mov     [rbp+var_1C], eax
0x1800324f3  mov     [rbp+var_18], 10h
0x1800324fa  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180032501  mov     [rbp+lpMem], rax
0x180032505  mov     rdx, rsi; char *
0x180032508  lea     rcx, [rbp+var_20]; this
0x18003250c  call    ?SetANSI@SString@@QEAAXPEBD@Z; SString::SetANSI(char const *)
0x180032511  nop
0x180032512  jmp     loc_180032619
0x180032517  mov     rax, r15
0x18003251a  inc     rax
0x18003251d  cmp     byte ptr [rsi+rax], 0
0x180032521  jnz     short loc_18003251A
0x180032523  lea     edx, [rax+1]
0x180032526  mov     ecx, [rdi+8]
0x180032529  not     ecx
0x18003252b  and     ecx, 1
0x18003252e  mov     ebx, [rdi]
0x180032530  shr     ebx, cl
0x180032532  dec     ebx
0x180032534  cmp     edx, ebx
0x180032536  cmovnb  ebx, edx
0x180032539  mov     eax, 14h
0x18003253e  cmp     ebx, eax
0x180032540  cmovb   ebx, eax
0x180032543  call    __local_stdio_printf_options
0x180032548  mov     r15, rax
0x18003254b  add     ebx, ebx
0x18003254d  xor     r9d, r9d
0x180032550  lea     r8d, [r9+7]
0x180032554  mov     edx, ebx
0x180032556  mov     rcx, rdi
0x180032559  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x18003255e  call    cs:__imp__errno
0x180032564  and     dword ptr [rax], 0
0x180032567  mov     ecx, [rdi+8]
0x18003256a  not     ecx
0x18003256c  and     cl, 1
0x18003256f  mov     r8d, [rdi]
0x180032572  shr     r8, cl; BufferCount
0x180032575  mov     [rsp+60h+ArgList], r14; ArgList
0x18003257a  and     [rsp+60h+var_38], 0
0x180032580  mov     [rsp+60h+Format], rsi; Format
0x180032585  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180032589  mov     rdx, [rdi+10h]; Buffer
0x18003258d  mov     rcx, [r15]; Options
0x180032590  call    cs:__imp___stdio_common_vsnprintf_s
0x180032596  test    eax, eax
0x180032598  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003259f  cmovs   eax, ecx
0x1800325a2  test    eax, eax
0x1800325a4  jns     short loc_1800325DB
0x1800325a6  call    cs:__imp__errno
0x1800325ac  cmp     dword ptr [rax], 0Ch
0x1800325af  jz      loc_180032642
0x1800325b5  call    cs:__imp__errno
0x1800325bb  cmp     dword ptr [rax], 0
0x1800325be  jz      short loc_18003254B
0x1800325c0  call    cs:__imp__errno
0x1800325c6  cmp     dword ptr [rax], 9
0x1800325c9  jz      short loc_18003254B
0x1800325cb  call    cs:__imp__errno
0x1800325d1  cmp     dword ptr [rax], 22h ; '"'
0x1800325d4  jnz     short loc_180032648
0x1800325d6  jmp     loc_18003254B
0x1800325db  mov     r9d, 1
0x1800325e1  lea     r8d, [r9+6]
0x1800325e5  mov     edx, eax
0x1800325e7  mov     rcx, rdi
0x1800325ea  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x1800325ef  mov     eax, 2
0x1800325f4  mov     [rbp+var_20], eax
0x1800325f7  mov     [rbp+var_1C], eax
0x1800325fa  mov     [rbp+var_18], 10h
0x180032601  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180032608  mov     [rbp+lpMem], rax
0x18003260c  mov     rdx, rsi; char *
0x18003260f  lea     rcx, [rbp+var_20]; this
0x180032613  call    ?SetANSI@SString@@QEAAXPEBD@Z; SString::SetANSI(char const *)
0x180032618  nop
0x180032619  test    byte ptr [rbp+var_18], 8
0x18003261d  jz      short loc_180032628
0x18003261f  mov     rcx, [rbp+lpMem]; lpMem
0x180032623  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032628  lea     r11, [rsp+60h+var_s0]
0x18003262d  mov     rbx, [r11+20h]
0x180032631  mov     rsi, [r11+28h]
0x180032635  mov     rdi, [r11+30h]
0x180032639  mov     rsp, r11
0x18003263c  pop     r15
0x18003263e  pop     r14
0x180032640  pop     rbp
0x180032641  retn
0x180032642  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
0x180032648  mov     ecx, 80070459h; int
0x18003264d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
