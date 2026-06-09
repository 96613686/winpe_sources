# Win32LiveSystemProvider::EnumThreadsUsingToolHelp(ulong *)

- ea: `0x180012214`
- end: `0x180012302`
- name: `?EnumThreadsUsingToolHelp@Win32LiveSystemProvider@@AEAAJPEAK@Z`
- size: `238`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180012140`

## callees

- `0x180001710`
- `0x180012214`
- `0x180015238`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012294`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::EnumThreadsUsingToolHelp(Win32LiveSystemProvider *this, unsigned int *a2)
{
  unsigned int v2; // edi
  void *v4; // rsi
  Win32LiveSystemProvider *v5; // rbx
  unsigned int (__fastcall *v6)(void *, tagTHREADENTRY32 *); // rax
  unsigned int v7; // eax
  signed int LastError; // eax
  bool v9; // zf
  tagTHREADENTRY32 v11; // [rsp+20h] [rbp-48h] BYREF

  v9 = *((_DWORD *)this + 171) == 0;
  v2 = *((_DWORD *)this + 166);
  v4 = (void *)*((_QWORD *)this + 84);
  v5 = this;
  memset(&v11.cntUsage, 0, 24);
  v11.dwSize = 28;
  if ( !v9 )
    goto LABEL_11;
  v6 = (unsigned int (__fastcall *)(void *, tagTHREADENTRY32 *))*((_QWORD *)this + 33);
  if ( !v6 )
  {
    v7 = -2147467263;
    goto LABEL_12;
  }
  if ( v6(v4, &v11) )
  {
    v7 = 0;
    if ( v11.th32OwnerProcessID == v2 )
      goto LABEL_12;
    this = v5;
LABEL_11:
    v7 = Win32LiveSystemProvider::ProcessThread32Next(this, v4, v2, &v11);
    goto LABEL_12;
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v9 = LastError == 0;
    if ( LastError <= 0 )
      goto LABEL_13;
    v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = -2147467259;
  }
LABEL_12:
  v9 = v7 == 0;
LABEL_13:
  if ( !v9 )
    return 1;
  *a2 = v11.th32ThreadID;
  ++*((_DWORD *)v5 + 171);
  return 0;
}

```

## disassembly

```asm
0x180012214  mov     [rsp+arg_10], rbx
0x180012219  push    rsi
0x18001221a  push    rdi
0x18001221b  push    r14
0x18001221d  sub     rsp, 50h
0x180012221  mov     rax, cs:__security_cookie
0x180012228  xor     rax, rsp
0x18001222b  mov     [rsp+68h+var_28], rax
0x180012230  cmp     dword ptr [rcx+2ACh], 0
0x180012237  xorps   xmm0, xmm0
0x18001223a  mov     edi, [rcx+298h]
0x180012240  mov     r14, rdx
0x180012243  mov     rsi, [rcx+2A0h]
0x18001224a  mov     rbx, rcx
0x18001224d  movdqu  xmmword ptr [rsp+68h+var_48.cntUsage], xmm0
0x180012253  mov     qword ptr [rsp+68h+var_48.tpDeltaPri], 0
0x18001225c  mov     [rsp+68h+var_48.dwSize], 1Ch
0x180012264  jnz     short loc_1800122BA
0x180012266  mov     rax, [rcx+108h]
0x18001226d  test    rax, rax
0x180012270  jnz     short loc_180012279
0x180012272  mov     eax, 80004001h
0x180012277  jmp     short loc_1800122CA
0x180012279  lea     rdx, [rsp+68h+var_48]
0x18001227e  mov     rcx, rsi
0x180012281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012286  test    eax, eax
0x180012288  jnz     short loc_1800122AF
0x18001228a  call    cs:__imp_GetLastError
0x180012290  test    eax, eax
0x180012292  jz      short loc_1800122A8
0x180012294  call    cs:__imp_GetLastError
0x18001229a  test    eax, eax
0x18001229c  jle     short loc_1800122CC
0x18001229e  movzx   eax, ax
0x1800122a1  or      eax, 80070000h
0x1800122a6  jmp     short loc_1800122CA
0x1800122a8  mov     eax, 80004005h
0x1800122ad  jmp     short loc_1800122CA
0x1800122af  xor     eax, eax
0x1800122b1  cmp     [rsp+68h+var_48.th32OwnerProcessID], edi
0x1800122b5  jz      short loc_1800122CA
0x1800122b7  mov     rcx, rbx; this
0x1800122ba  lea     r9, [rsp+68h+var_48]; struct tagTHREADENTRY32 *
0x1800122bf  mov     r8d, edi; unsigned int
0x1800122c2  mov     rdx, rsi; void *
0x1800122c5  call    ?ProcessThread32Next@Win32LiveSystemProvider@@IEAAJPEAXKPEAUtagTHREADENTRY32@@@Z; Win32LiveSystemProvider::ProcessThread32Next(void *,ulong,tagTHREADENTRY32 *)
0x1800122ca  test    eax, eax
0x1800122cc  jnz     short loc_1800122DF
0x1800122ce  mov     eax, [rsp+68h+var_48.th32ThreadID]
0x1800122d2  mov     [r14], eax
0x1800122d5  inc     dword ptr [rbx+2ACh]
0x1800122db  xor     eax, eax
0x1800122dd  jmp     short loc_1800122E4
0x1800122df  mov     eax, 1
0x1800122e4  mov     rcx, [rsp+68h+var_28]
0x1800122e9  xor     rcx, rsp; StackCookie
0x1800122ec  call    __security_check_cookie
0x1800122f1  mov     rbx, [rsp+68h+arg_10]
0x1800122f9  add     rsp, 50h
0x1800122fd  pop     r14
0x1800122ff  pop     rdi
0x180012300  pop     rsi
0x180012301  retn
```
