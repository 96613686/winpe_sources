# DisplayLogAccessError(long,IConsole *,CLogInfo *)

- ea: `0x18001f2dc`
- end: `0x18001f39b`
- name: `?DisplayLogAccessError@@YAXJPEAUIConsole@@PEAVCLogInfo@@@Z`
- size: `191`
- prototype: `void __fastcall(DWORD dwMessageId, struct IConsole *, struct CLogInfo *this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005540`
- `0x18001d4cc`
- `0x18001daf4`

## callees

- `0x180016a98`
- `0x18001ef94`
- `0x18001f2dc`

## import_xrefs

- `msvcrt!wcschr` at `0x18001f348`
- `msvcrt!wcschr` at `0x18001f348`
- `KERNEL32!LocalFree` at `0x18001f385`
- `KERNEL32!LocalFree` at `0x18001f385`
- `KERNEL32!FormatMessageW` at `0x18001f321`
- `KERNEL32!FormatMessageW` at `0x18001f321`

## pseudocode

```c
void __fastcall DisplayLogAccessError(DWORD dwMessageId, struct IConsole *a2, struct CLogInfo *this)
{
  unsigned __int16 *DisplayName; // rax
  unsigned int v7; // edx
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  LPWSTR lpBuffer; // [rsp+20h] [rbp-28h]
  wchar_t *Str; // [rsp+68h] [rbp+20h] BYREF

  Str = 0;
  if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, (LPWSTR)&Str, 0, 0) )
  {
    v8 = wcschr(Str, 0xDu);
    if ( v8 )
      *v8 = 0;
    v9 = Str;
    DisplayName = CLogInfo::GetDisplayName(this);
    v7 = 287;
    lpBuffer = v9;
  }
  else
  {
    DisplayName = CLogInfo::GetDisplayName(this);
    v7 = 286;
    LODWORD(lpBuffer) = dwMessageId;
  }
  ConsoleMsgBox(a2, v7, 0x10u, DisplayName, lpBuffer);
  LocalFree(Str);
}

```

## disassembly

```asm
0x18001f2dc  mov     rax, rsp
0x18001f2df  mov     [rax+8], rbx
0x18001f2e3  mov     [rax+10h], rsi
0x18001f2e7  push    rdi
0x18001f2e8  sub     rsp, 40h
0x18001f2ec  mov     qword ptr [rax-18h], 0
0x18001f2f4  mov     rdi, r8
0x18001f2f7  mov     dword ptr [rax-20h], 0
0x18001f2fe  mov     rsi, rdx
0x18001f301  mov     qword ptr [rax+20h], 0
0x18001f309  lea     rax, [rax+20h]
0x18001f30d  mov     ebx, ecx
0x18001f30f  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x18001f314  mov     r8d, ecx; dwMessageId
0x18001f317  xor     r9d, r9d; dwLanguageId
0x18001f31a  xor     edx, edx; lpSource
0x18001f31c  mov     ecx, 1100h; dwFlags
0x18001f321  call    cs:__imp_FormatMessageW
0x18001f327  test    eax, eax
0x18001f329  jnz     short loc_18001F33E
0x18001f32b  mov     rcx, rdi; this
0x18001f32e  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x18001f333  mov     edx, 11Eh
0x18001f338  mov     dword ptr [rsp+48h+lpBuffer], ebx
0x18001f33c  jmp     short loc_18001F36F
0x18001f33e  mov     rcx, [rsp+48h+Str]; Str
0x18001f343  mov     edx, 0Dh; Ch
0x18001f348  call    cs:__imp_wcschr
0x18001f34e  test    rax, rax
0x18001f351  jz      short loc_18001F358
0x18001f353  xor     ecx, ecx
0x18001f355  mov     [rax], cx
0x18001f358  mov     rbx, [rsp+48h+Str]
0x18001f35d  mov     rcx, rdi; this
0x18001f360  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x18001f365  mov     edx, 11Fh; unsigned int
0x18001f36a  mov     [rsp+48h+lpBuffer], rbx
0x18001f36f  mov     r9, rax
0x18001f372  mov     r8d, 10h; unsigned int
0x18001f378  mov     rcx, rsi; struct IConsole *
0x18001f37b  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x18001f380  mov     rcx, [rsp+48h+Str]; hMem
0x18001f385  call    cs:__imp_LocalFree
0x18001f38b  mov     rbx, [rsp+48h+arg_0]
0x18001f390  mov     rsi, [rsp+48h+arg_8]
0x18001f395  add     rsp, 40h
0x18001f399  pop     rdi
0x18001f39a  retn
```
