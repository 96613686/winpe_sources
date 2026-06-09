# SString::VPrintf(ushort const *,char *)

- ea: `0x14000bd64`
- end: `0x14000bf5d`
- name: `?VPrintf@SString@@QEAAXPEBGPEAD@Z`
- size: `505`
- prototype: `void __fastcall(SString *this, const unsigned __int16 *, va_list)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006ee4`
- `0x14000bd40`
- `0x14000bf84`

## callees

- `0x1400010c0`
- `0x14000a10c`
- `0x14000ad80`
- `0x14000bd64`
- `0x14000c56c`
- `0x14000e4f4`
- `0x14000e71c`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x14000bdcd`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x14000be96`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x14000bdcd`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x14000be96`
- `ucrtbase_clr0400!_errno` at `0x14000be65`
- `ucrtbase_clr0400!_errno` at `0x14000beac`
- `ucrtbase_clr0400!_errno` at `0x14000bebb`
- `ucrtbase_clr0400!_errno` at `0x14000bec6`
- `ucrtbase_clr0400!_errno` at `0x14000bed1`
- `ucrtbase_clr0400!_errno` at `0x14000be65`
- `ucrtbase_clr0400!_errno` at `0x14000beac`
- `ucrtbase_clr0400!_errno` at `0x14000bebb`
- `ucrtbase_clr0400!_errno` at `0x14000bec6`
- `ucrtbase_clr0400!_errno` at `0x14000bed1`

## pseudocode

```c
void __fastcall SString::VPrintf(SString *this, const unsigned __int16 *a2, va_list a3)
{
  unsigned int v6; // ebx
  unsigned __int64 *v7; // rax
  signed int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // ebx
  unsigned __int64 *v11; // r15
  __int64 v12; // [rsp+40h] [rbp-20h] BYREF
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
      SString::Resize((__int64)this, v10, 4, 0);
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
  SString::Resize((__int64)this, v8, 4, 1);
  v12 = 0x200000002LL;
  v13 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  SString::Set((wchar_t **)&v12, a2);
  if ( (v13 & 8) != 0 )
    operator delete(lpMem);
}

```

## disassembly

```asm
0x14000bd64  mov     rax, rsp
0x14000bd67  mov     [rax+8], rbx
0x14000bd6b  mov     [rax+10h], rsi
0x14000bd6f  mov     [rax+18h], rdi
0x14000bd73  mov     [rax+20h], r12
0x14000bd77  push    rbp
0x14000bd78  push    r14
0x14000bd7a  push    r15
0x14000bd7c  mov     rbp, rsp
0x14000bd7f  sub     rsp, 60h
0x14000bd83  mov     r14, r8
0x14000bd86  mov     rsi, rdx
0x14000bd89  mov     rdi, rcx
0x14000bd8c  mov     ecx, [rcx+8]
0x14000bd8f  not     ecx
0x14000bd91  and     ecx, 1
0x14000bd94  mov     r9d, [rdi]
0x14000bd97  shr     r9d, cl
0x14000bd9a  lea     eax, [r9-1]
0x14000bd9e  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000bda2  xor     r12d, r12d
0x14000bda5  test    eax, eax
0x14000bda7  jz      short loc_14000BE1D
0x14000bda9  mov     ebx, r9d
0x14000bdac  call    __local_stdio_printf_options
0x14000bdb1  mov     [rsp+60h+ArgList], r14; ArgList
0x14000bdb6  mov     [rsp+60h+Locale], r12; Locale
0x14000bdbb  mov     [rsp+60h+Format], rsi; Format
0x14000bdc0  mov     r9, r15; MaxCount
0x14000bdc3  mov     r8d, ebx; BufferCount
0x14000bdc6  mov     rdx, [rdi+10h]; Buffer
0x14000bdca  mov     rcx, [rax]; Options
0x14000bdcd  call    cs:__imp___stdio_common_vsnwprintf_s
0x14000bdd3  test    eax, eax
0x14000bdd5  cmovs   eax, r15d
0x14000bdd9  test    eax, eax
0x14000bddb  js      short loc_14000BE1D
0x14000bddd  lea     r9d, [r15+2]
0x14000bde1  lea     r8d, [r15+5]
0x14000bde5  mov     edx, eax
0x14000bde7  mov     rcx, rdi
0x14000bdea  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000bdef  lea     eax, [r15+3]
0x14000bdf3  mov     [rbp+var_20], eax
0x14000bdf6  mov     [rbp+var_1C], eax
0x14000bdf9  mov     [rbp+var_18], 10h
0x14000be00  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x14000be07  mov     [rbp+lpMem], rax
0x14000be0b  mov     rdx, rsi; unsigned __int16 *
0x14000be0e  lea     rcx, [rbp+var_20]; this
0x14000be12  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x14000be17  nop
0x14000be18  jmp     loc_14000BF1F
0x14000be1d  mov     rax, r15
0x14000be20  inc     rax
0x14000be23  cmp     [rsi+rax*2], r12w
0x14000be28  jnz     short loc_14000BE20
0x14000be2a  lea     edx, [rax+1]
0x14000be2d  mov     ecx, [rdi+8]
0x14000be30  not     ecx
0x14000be32  and     ecx, 1
0x14000be35  mov     ebx, [rdi]
0x14000be37  shr     ebx, cl
0x14000be39  dec     ebx
0x14000be3b  cmp     edx, ebx
0x14000be3d  cmovnb  ebx, edx
0x14000be40  mov     eax, 14h
0x14000be45  cmp     ebx, eax
0x14000be47  cmovb   ebx, eax
0x14000be4a  call    __local_stdio_printf_options
0x14000be4f  mov     r15, rax
0x14000be52  add     ebx, ebx
0x14000be54  xor     r9d, r9d
0x14000be57  lea     r8d, [r9+4]
0x14000be5b  mov     edx, ebx
0x14000be5d  mov     rcx, rdi
0x14000be60  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000be65  call    cs:__imp__errno
0x14000be6b  mov     [rax], r12d
0x14000be6e  mov     ecx, [rdi+8]
0x14000be71  not     ecx
0x14000be73  and     cl, 1
0x14000be76  mov     r8d, [rdi]
0x14000be79  shr     r8, cl; BufferCount
0x14000be7c  mov     [rsp+60h+ArgList], r14; ArgList
0x14000be81  mov     [rsp+60h+Locale], r12; Locale
0x14000be86  mov     [rsp+60h+Format], rsi; Format
0x14000be8b  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000be8f  mov     rdx, [rdi+10h]; Buffer
0x14000be93  mov     rcx, [r15]; Options
0x14000be96  call    cs:__imp___stdio_common_vsnwprintf_s
0x14000be9c  test    eax, eax
0x14000be9e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000bea5  cmovs   eax, ecx
0x14000bea8  test    eax, eax
0x14000beaa  jns     short loc_14000BEE1
0x14000beac  call    cs:__imp__errno
0x14000beb2  cmp     dword ptr [rax], 0Ch
0x14000beb5  jz      loc_14000BF4C
0x14000bebb  call    cs:__imp__errno
0x14000bec1  cmp     [rax], r12d
0x14000bec4  jz      short loc_14000BE52
0x14000bec6  call    cs:__imp__errno
0x14000becc  cmp     dword ptr [rax], 9
0x14000becf  jz      short loc_14000BE52
0x14000bed1  call    cs:__imp__errno
0x14000bed7  cmp     dword ptr [rax], 22h ; '"'
0x14000beda  jnz     short loc_14000BF52
0x14000bedc  jmp     loc_14000BE52
0x14000bee1  mov     r9d, 1
0x14000bee7  lea     r8d, [r9+3]
0x14000beeb  mov     edx, eax
0x14000beed  mov     rcx, rdi
0x14000bef0  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000bef5  mov     eax, 2
0x14000befa  mov     [rbp+var_20], eax
0x14000befd  mov     [rbp+var_1C], eax
0x14000bf00  mov     [rbp+var_18], 10h
0x14000bf07  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x14000bf0e  mov     [rbp+lpMem], rax
0x14000bf12  mov     rdx, rsi; unsigned __int16 *
0x14000bf15  lea     rcx, [rbp+var_20]; this
0x14000bf19  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x14000bf1e  nop
0x14000bf1f  test    byte ptr [rbp+var_18], 8
0x14000bf23  jz      short loc_14000BF2E
0x14000bf25  mov     rcx, [rbp+lpMem]; lpMem
0x14000bf29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bf2e  lea     r11, [rsp+60h+var_s0]
0x14000bf33  mov     rbx, [r11+20h]
0x14000bf37  mov     rsi, [r11+28h]
0x14000bf3b  mov     rdi, [r11+30h]
0x14000bf3f  mov     r12, [r11+38h]
0x14000bf43  mov     rsp, r11
0x14000bf46  pop     r15
0x14000bf48  pop     r14
0x14000bf4a  pop     rbp
0x14000bf4b  retn
0x14000bf4c  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
0x14000bf52  mov     ecx, 80070459h; int
0x14000bf57  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
