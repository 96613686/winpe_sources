# FTPHOST_CLASS::~FTPHOST_CLASS(void)

- ea: `0x1800033a8`
- end: `0x18000349f`
- name: `??1FTPHOST_CLASS@@AEAA@XZ`
- size: `247`
- prototype: `void __fastcall(FTPHOST_CLASS *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800039d0`

## callees

- `0x1800033a8`
- `0x180005010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180003476`
- `iisutil!PuDbgPrintError` at `0x180003476`

## string_xrefs

- `0x18000344b`: `Cannot Dispose Managed Host Service\n`

## pseudocode

```c
void __fastcall FTPHOST_CLASS::~FTPHOST_CLASS(FTPHOST_CLASS *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v3; // eax
  int v4; // edi
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &FTPHOST_CLASS::`vftable';
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  if ( v2 )
  {
    v5 = 0;
    v3 = (**v2)(v2, &GUID_805d7a98_d4af_3f0f_967f_e5cf45312d2c, &v5);
    if ( v3 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
          74,
          "FTPHOST_CLASS::~FTPHOST_CLASS",
          v3,
          "Cannot Dispose Managed Host Service\n");
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      v5 = 0;
      if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
          67,
          "FTPHOST_CLASS::~FTPHOST_CLASS",
          v4,
          "Dispose method failed\n");
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800033a8  mov     [rsp+arg_8], rbx
0x1800033ad  push    rdi
0x1800033ae  sub     rsp, 30h
0x1800033b2  lea     rax, ??_7FTPHOST_CLASS@@6B@; const FTPHOST_CLASS::`vftable'
0x1800033b9  mov     rbx, rcx
0x1800033bc  mov     [rcx], rax
0x1800033bf  mov     rcx, [rcx+10h]
0x1800033c3  test    rcx, rcx
0x1800033c6  jz      loc_180003494
0x1800033cc  mov     [rsp+38h+arg_0], 0
0x1800033d5  lea     r8, [rsp+38h+arg_0]
0x1800033da  mov     rax, [rcx]
0x1800033dd  lea     rdx, _GUID_805d7a98_d4af_3f0f_967f_e5cf45312d2c
0x1800033e4  mov     rax, [rax]
0x1800033e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ec  test    eax, eax
0x1800033ee  js      short loc_180003442
0x1800033f0  mov     rcx, [rsp+38h+arg_0]
0x1800033f5  mov     rax, [rcx]
0x1800033f8  mov     rax, [rax+38h]
0x1800033fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003401  mov     rcx, [rsp+38h+arg_0]
0x180003406  mov     edi, eax
0x180003408  mov     rdx, [rcx]
0x18000340b  mov     rax, [rdx+10h]
0x18000340f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003414  mov     [rsp+38h+arg_0], 0
0x18000341d  test    edi, edi
0x18000341f  jns     short loc_18000347C
0x180003421  test    cs:g_dwDebugFlags, 0Fh
0x180003428  jz      short loc_18000347C
0x18000342a  lea     rax, aDisposeMethodF; "Dispose method failed\n"
0x180003431  mov     r8d, 43h ; 'C'
0x180003437  mov     [rsp+38h+var_10], rax
0x18000343c  mov     [rsp+38h+var_18], edi
0x180003440  jmp     short loc_180003461
0x180003442  test    cs:g_dwDebugFlags, 0Fh
0x180003449  jz      short loc_18000347C
0x18000344b  lea     rcx, aCannotDisposeM; "Cannot Dispose Managed Host Service\n"
0x180003452  mov     r8d, 4Ah ; 'J'
0x180003458  mov     [rsp+38h+var_10], rcx
0x18000345d  mov     [rsp+38h+var_18], eax
0x180003461  mov     rcx, cs:g_pDebug
0x180003468  lea     r9, aFtphostClassFt; "FTPHOST_CLASS::~FTPHOST_CLASS"
0x18000346f  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003476  call    cs:__imp_PuDbgPrintError
0x18000347c  mov     rcx, [rbx+10h]
0x180003480  mov     rax, [rcx]
0x180003483  mov     rax, [rax+10h]
0x180003487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000348c  mov     qword ptr [rbx+10h], 0
0x180003494  mov     rbx, [rsp+38h+arg_8]
0x180003499  add     rsp, 30h
0x18000349d  pop     rdi
0x18000349e  retn
```
