# container::NamedPipe::CreateSymlink(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180025d24`
- end: `0x180025ecf`
- name: `?CreateSymlink@NamedPipe@container@@YAXPEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `427`
- prototype: `__int64 __fastcall(HANDLE FileHandle, void *Src, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002605c`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x180003614`
- `0x1800051b0`
- `0x18000b4bc`
- `0x180025d24`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180025e48`
- `ntdll!NtFsControlFile` at `0x180025e48`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall container::NamedPipe::CreateSymlink(HANDLE FileHandle, _QWORD *Src, _QWORD *a3)
{
  size_t v6; // rbp
  __int64 v7; // rbx
  _DWORD *InputBuffer; // r14
  _QWORD *v9; // rdx
  _QWORD *v10; // rdx
  NTSTATUS v11; // eax
  int IoStatusBlock; // [rsp+20h] [rbp-98h]
  int IoStatusBlocka; // [rsp+20h] [rbp-98h]
  struct _IO_STATUS_BLOCK v15; // [rsp+58h] [rbp-60h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]
  _QWORD *v17; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v16 = Src;
  v17 = a3;
  if ( (unsigned __int64)(2LL * Src[2]) > 0xFFF3 || (unsigned __int64)(2LL * a3[2]) > 0xFFFF )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\namedpipe_provider.cpp",
      (const char *)0xC000000DLL,
      IoStatusBlock);
  v6 = (unsigned __int16)(2 * *((_WORD *)Src + 8));
  v7 = (unsigned __int16)(2 * *((_WORD *)a3 + 8));
  InputBuffer = operator new[](v7 + v6 + 12);
  InputBuffer[2] = 1;
  *(_WORD *)InputBuffer = 12;
  *((_WORD *)InputBuffer + 1) = v6;
  *((_WORD *)InputBuffer + 2) = v6 + 12;
  *((_WORD *)InputBuffer + 3) = v7;
  if ( Src[3] <= 7u )
    v9 = Src;
  else
    v9 = (_QWORD *)*Src;
  memcpy_0(InputBuffer + 3, v9, v6);
  if ( a3[3] <= 7u )
    v10 = a3;
  else
    v10 = (_QWORD *)*a3;
  memcpy_0((char *)InputBuffer + *((unsigned __int16 *)InputBuffer + 2), v10, *((unsigned __int16 *)InputBuffer + 3));
  v15 = 0;
  v11 = NtFsControlFile(FileHandle, 0, 0, 0, &v15, 0x11004Cu, InputBuffer, v7 + v6 + 12, 0, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\namedpipe_provider.cpp",
      (const char *)(unsigned int)v11,
      IoStatusBlocka);
  operator delete(InputBuffer);
  std::wstring::~wstring(Src);
  return std::wstring::~wstring(a3);
}

```

## disassembly

```asm
0x180025d24  push    rbx
0x180025d26  push    rbp
0x180025d27  push    rsi
0x180025d28  push    rdi
0x180025d29  push    r12
0x180025d2b  push    r14
0x180025d2d  push    r15
0x180025d2f  sub     rsp, 80h
0x180025d36  mov     rax, cs:__security_cookie
0x180025d3d  xor     rax, rsp
0x180025d40  mov     [rsp+0B8h+var_40], rax
0x180025d45  mov     rdi, r8
0x180025d48  mov     rsi, rdx
0x180025d4b  mov     r15, rcx
0x180025d4e  mov     [rsp+0B8h+var_50], rdx
0x180025d53  mov     [rsp+0B8h+var_48], r8
0x180025d58  mov     rax, [rdx+10h]
0x180025d5c  add     rax, rax
0x180025d5f  cmp     rax, 0FFF3h
0x180025d65  ja      loc_180025EAF
0x180025d6b  mov     rax, [r8+10h]
0x180025d6f  add     rax, rax
0x180025d72  cmp     rax, 0FFFFh
0x180025d78  ja      loc_180025EAF
0x180025d7e  movzx   eax, word ptr [rdx+10h]
0x180025d82  add     ax, ax
0x180025d85  movzx   ebp, ax
0x180025d88  movzx   eax, word ptr [r8+10h]
0x180025d8d  add     ax, ax
0x180025d90  movzx   ebx, ax
0x180025d93  lea     r12, [rbp+0Ch]
0x180025d97  add     r12, rbx
0x180025d9a  mov     rcx, r12; unsigned __int64
0x180025d9d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025da2  mov     r14, rax
0x180025da5  mov     [rsp+0B8h+var_68], rax
0x180025daa  mov     dword ptr [rax+8], 1
0x180025db1  mov     eax, 0Ch
0x180025db6  mov     [r14], ax
0x180025dba  mov     [r14+2], bp
0x180025dbf  lea     ecx, [rax+rbp]
0x180025dc2  mov     [r14+4], cx
0x180025dc7  mov     [r14+6], bx
0x180025dcc  cmp     qword ptr [rsi+18h], 7
0x180025dd1  jbe     short loc_180025DD8
0x180025dd3  mov     rdx, [rsi]
0x180025dd6  jmp     short loc_180025DDB
0x180025dd8  mov     rdx, rsi; Src
0x180025ddb  lea     rcx, [r14+0Ch]; void *
0x180025ddf  mov     r8, rbp; Size
0x180025de2  call    memcpy_0
0x180025de7  cmp     qword ptr [rdi+18h], 7
0x180025dec  jbe     short loc_180025DF3
0x180025dee  mov     rdx, [rdi]
0x180025df1  jmp     short loc_180025DF6
0x180025df3  mov     rdx, rdi; Src
0x180025df6  movzx   r8d, word ptr [r14+6]; Size
0x180025dfb  movzx   ecx, word ptr [r14+4]
0x180025e00  add     rcx, r14; void *
0x180025e03  call    memcpy_0
0x180025e08  xorps   xmm0, xmm0
0x180025e0b  movups  xmmword ptr [rsp+0B8h+var_60], xmm0
0x180025e10  mov     [rsp+0B8h+OutputBufferLength], 0; OutputBufferLength
0x180025e18  mov     [rsp+0B8h+OutputBuffer], 0; OutputBuffer
0x180025e21  mov     [rsp+0B8h+InputBufferLength], r12d; InputBufferLength
0x180025e26  mov     [rsp+0B8h+InputBuffer], r14; InputBuffer
0x180025e2b  mov     [rsp+0B8h+FsControlCode], 11004Ch; FsControlCode
0x180025e33  lea     rax, [rsp+0B8h+var_60]
0x180025e38  mov     [rsp+0B8h+IoStatusBlock], rax; int
0x180025e3d  xor     r9d, r9d; ApcContext
0x180025e40  xor     r8d, r8d; ApcRoutine
0x180025e43  xor     edx, edx; Event
0x180025e45  mov     rcx, r15; FileHandle
0x180025e48  call    cs:__imp_NtFsControlFile
0x180025e4f  nop     dword ptr [rax+rax+00h]
0x180025e54  mov     rcx, [rsp+0B8h]; this
0x180025e5c  test    eax, eax
0x180025e5e  js      short loc_180025E9A
0x180025e60  mov     rcx, r14; void *
0x180025e63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025e68  nop
0x180025e69  mov     rcx, rsi
0x180025e6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025e71  nop
0x180025e72  mov     rcx, rdi
0x180025e75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025e7a  mov     rcx, [rsp+0B8h+var_40]
0x180025e7f  xor     rcx, rsp; StackCookie
0x180025e82  call    __security_check_cookie
0x180025e87  add     rsp, 80h
0x180025e8e  pop     r15
0x180025e90  pop     r14
0x180025e92  pop     r12
0x180025e94  pop     rdi
0x180025e95  pop     rsi
0x180025e96  pop     rbp
0x180025e97  pop     rbx
0x180025e98  retn
0x180025e9a  mov     r9d, eax; char *
0x180025e9d  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\container"...
0x180025ea4  mov     edx, 4Ah ; 'J'; void *
0x180025ea9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180025eaf  mov     rcx, [rsp+0B8h]; this
0x180025eb7  mov     r9d, 0C000000Dh; char *
0x180025ebd  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\container"...
0x180025ec4  mov     edx, 2Bh ; '+'; void *
0x180025ec9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
