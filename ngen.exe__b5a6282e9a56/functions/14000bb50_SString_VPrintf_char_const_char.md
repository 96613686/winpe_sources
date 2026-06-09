# SString::VPrintf(char const *,char *)

- ea: `0x14000bb50`
- end: `0x14000bd3f`
- name: `?VPrintf@SString@@QEAAXPEBDPEAD@Z`
- size: `495`
- prototype: `void __fastcall(SString *this, const char *, va_list)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000bb2c`

## callees

- `0x1400010c0`
- `0x14000a10c`
- `0x14000ae44`
- `0x14000bb50`
- `0x14000c56c`
- `0x14000e4f4`
- `0x14000e71c`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000bbb3`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000bc7c`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000bbb3`
- `ucrtbase_clr0400!__stdio_common_vsnprintf_s` at `0x14000bc7c`
- `ucrtbase_clr0400!_errno` at `0x14000bc4a`
- `ucrtbase_clr0400!_errno` at `0x14000bc92`
- `ucrtbase_clr0400!_errno` at `0x14000bca1`
- `ucrtbase_clr0400!_errno` at `0x14000bcac`
- `ucrtbase_clr0400!_errno` at `0x14000bcb7`
- `ucrtbase_clr0400!_errno` at `0x14000bc4a`
- `ucrtbase_clr0400!_errno` at `0x14000bc92`
- `ucrtbase_clr0400!_errno` at `0x14000bca1`
- `ucrtbase_clr0400!_errno` at `0x14000bcac`
- `ucrtbase_clr0400!_errno` at `0x14000bcb7`

## pseudocode

```c
void __fastcall SString::VPrintf(SString *this, const char *a2, va_list a3)
{
  unsigned int v6; // ebx
  unsigned __int64 *v7; // rax
  signed int v8; // eax
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
      SString::Resize((__int64)this, v10, 7, 0);
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
  SString::Resize((__int64)this, v8, 7, 1);
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
0x14000bb50  mov     [rsp-18h+arg_0], rbx
0x14000bb55  mov     [rsp-18h+arg_8], rsi
0x14000bb5a  mov     [rsp-18h+arg_10], rdi
0x14000bb5f  push    rbp
0x14000bb60  push    r14
0x14000bb62  push    r15
0x14000bb64  mov     rbp, rsp
0x14000bb67  sub     rsp, 60h
0x14000bb6b  mov     r14, r8
0x14000bb6e  mov     rsi, rdx
0x14000bb71  mov     rdi, rcx
0x14000bb74  mov     ecx, [rcx+8]
0x14000bb77  not     ecx
0x14000bb79  and     ecx, 1
0x14000bb7c  mov     r9d, [rdi]
0x14000bb7f  shr     r9d, cl
0x14000bb82  lea     eax, [r9-1]
0x14000bb86  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000bb8a  test    eax, eax
0x14000bb8c  jz      short loc_14000BC03
0x14000bb8e  mov     ebx, r9d
0x14000bb91  call    __local_stdio_printf_options
0x14000bb96  mov     [rsp+60h+ArgList], r14; ArgList
0x14000bb9b  and     [rsp+60h+var_38], 0
0x14000bba1  mov     [rsp+60h+Format], rsi; Format
0x14000bba6  mov     r9, r15; MaxCount
0x14000bba9  mov     r8d, ebx; BufferCount
0x14000bbac  mov     rdx, [rdi+10h]; Buffer
0x14000bbb0  mov     rcx, [rax]; Options
0x14000bbb3  call    cs:__imp___stdio_common_vsnprintf_s
0x14000bbb9  test    eax, eax
0x14000bbbb  cmovs   eax, r15d
0x14000bbbf  test    eax, eax
0x14000bbc1  js      short loc_14000BC03
0x14000bbc3  lea     r9d, [r15+2]
0x14000bbc7  lea     r8d, [r15+8]
0x14000bbcb  mov     edx, eax
0x14000bbcd  mov     rcx, rdi
0x14000bbd0  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000bbd5  lea     eax, [r15+3]
0x14000bbd9  mov     [rbp+var_20], eax
0x14000bbdc  mov     [rbp+var_1C], eax
0x14000bbdf  mov     [rbp+var_18], 10h
0x14000bbe6  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x14000bbed  mov     [rbp+lpMem], rax
0x14000bbf1  mov     rdx, rsi; char *
0x14000bbf4  lea     rcx, [rbp+var_20]; this
0x14000bbf8  call    ?SetANSI@SString@@QEAAXPEBD@Z; SString::SetANSI(char const *)
0x14000bbfd  nop
0x14000bbfe  jmp     loc_14000BD05
0x14000bc03  mov     rax, r15
0x14000bc06  inc     rax
0x14000bc09  cmp     byte ptr [rsi+rax], 0
0x14000bc0d  jnz     short loc_14000BC06
0x14000bc0f  lea     edx, [rax+1]
0x14000bc12  mov     ecx, [rdi+8]
0x14000bc15  not     ecx
0x14000bc17  and     ecx, 1
0x14000bc1a  mov     ebx, [rdi]
0x14000bc1c  shr     ebx, cl
0x14000bc1e  dec     ebx
0x14000bc20  cmp     edx, ebx
0x14000bc22  cmovnb  ebx, edx
0x14000bc25  mov     eax, 14h
0x14000bc2a  cmp     ebx, eax
0x14000bc2c  cmovb   ebx, eax
0x14000bc2f  call    __local_stdio_printf_options
0x14000bc34  mov     r15, rax
0x14000bc37  add     ebx, ebx
0x14000bc39  xor     r9d, r9d
0x14000bc3c  lea     r8d, [r9+7]
0x14000bc40  mov     edx, ebx
0x14000bc42  mov     rcx, rdi
0x14000bc45  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000bc4a  call    cs:__imp__errno
0x14000bc50  and     dword ptr [rax], 0
0x14000bc53  mov     ecx, [rdi+8]
0x14000bc56  not     ecx
0x14000bc58  and     cl, 1
0x14000bc5b  mov     r8d, [rdi]
0x14000bc5e  shr     r8, cl; BufferCount
0x14000bc61  mov     [rsp+60h+ArgList], r14; ArgList
0x14000bc66  and     [rsp+60h+var_38], 0
0x14000bc6c  mov     [rsp+60h+Format], rsi; Format
0x14000bc71  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000bc75  mov     rdx, [rdi+10h]; Buffer
0x14000bc79  mov     rcx, [r15]; Options
0x14000bc7c  call    cs:__imp___stdio_common_vsnprintf_s
0x14000bc82  test    eax, eax
0x14000bc84  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000bc8b  cmovs   eax, ecx
0x14000bc8e  test    eax, eax
0x14000bc90  jns     short loc_14000BCC7
0x14000bc92  call    cs:__imp__errno
0x14000bc98  cmp     dword ptr [rax], 0Ch
0x14000bc9b  jz      loc_14000BD2E
0x14000bca1  call    cs:__imp__errno
0x14000bca7  cmp     dword ptr [rax], 0
0x14000bcaa  jz      short loc_14000BC37
0x14000bcac  call    cs:__imp__errno
0x14000bcb2  cmp     dword ptr [rax], 9
0x14000bcb5  jz      short loc_14000BC37
0x14000bcb7  call    cs:__imp__errno
0x14000bcbd  cmp     dword ptr [rax], 22h ; '"'
0x14000bcc0  jnz     short loc_14000BD34
0x14000bcc2  jmp     loc_14000BC37
0x14000bcc7  mov     r9d, 1
0x14000bccd  lea     r8d, [r9+6]
0x14000bcd1  mov     edx, eax
0x14000bcd3  mov     rcx, rdi
0x14000bcd6  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x14000bcdb  mov     eax, 2
0x14000bce0  mov     [rbp+var_20], eax
0x14000bce3  mov     [rbp+var_1C], eax
0x14000bce6  mov     [rbp+var_18], 10h
0x14000bced  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x14000bcf4  mov     [rbp+lpMem], rax
0x14000bcf8  mov     rdx, rsi; char *
0x14000bcfb  lea     rcx, [rbp+var_20]; this
0x14000bcff  call    ?SetANSI@SString@@QEAAXPEBD@Z; SString::SetANSI(char const *)
0x14000bd04  nop
0x14000bd05  test    byte ptr [rbp+var_18], 8
0x14000bd09  jz      short loc_14000BD14
0x14000bd0b  mov     rcx, [rbp+lpMem]; lpMem
0x14000bd0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000bd14  lea     r11, [rsp+60h+var_s0]
0x14000bd19  mov     rbx, [r11+20h]
0x14000bd1d  mov     rsi, [r11+28h]
0x14000bd21  mov     rdi, [r11+30h]
0x14000bd25  mov     rsp, r11
0x14000bd28  pop     r15
0x14000bd2a  pop     r14
0x14000bd2c  pop     rbp
0x14000bd2d  retn
0x14000bd2e  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
0x14000bd34  mov     ecx, 80070459h; int
0x14000bd39  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
