# FTPHOST_CLASS_FACTORY::QueryInterface(_GUID const &,void * *)

- ea: `0x180003230`
- end: `0x18000331c`
- name: `?QueryInterface@FTPHOST_CLASS_FACTORY@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `236`
- prototype: `__int64 __fastcall(FTPHOST_CLASS_FACTORY *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003230`
- `0x180005010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000330e`
- `iisutil!PuDbgPrintError` at `0x18000330e`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS_FACTORY::QueryInterface(
        FTPHOST_CLASS_FACTORY *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
    {
      *a3 = this;
      v3 = 0;
      (*(void (__fastcall **)(FTPHOST_CLASS_FACTORY *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      *a3 = 0;
      v3 = -2147467262;
      if ( *(_OWORD *)a2 != *(_OWORD *)&IID_IMarshal && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
          156,
          "FTPHOST_CLASS_FACTORY::QueryInterface",
          -2147467262,
          "QueryInterface on FTPHOST_CLASS_FACTORY object failed, IID not supported\n");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
        126,
        "FTPHOST_CLASS_FACTORY::QueryInterface",
        -2147024809,
        "QueryInterface on FTPHOST_CLASS_FACTORY object failed, bad pointer\n");
  }
  return v3;
}

```

## disassembly

```asm
0x180003230  push    rbx
0x180003232  sub     rsp, 30h
0x180003236  test    r8, r8
0x180003239  jnz     short loc_18000326C
0x18000323b  test    cs:g_dwDebugFlags, 0Fh
0x180003242  mov     ebx, 80070057h
0x180003247  jz      loc_180003314
0x18000324d  lea     rax, aQueryinterface_1; "QueryInterface on FTPHOST_CLASS_FACTORY"...
0x180003254  mov     r8d, 7Eh ; '~'
0x18000325a  mov     [rsp+38h+var_10], rax
0x18000325f  mov     [rsp+38h+var_18], 80070057h
0x180003267  jmp     loc_1800032F9
0x18000326c  mov     rax, [rdx]
0x18000326f  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003276  jnz     short loc_180003285
0x180003278  mov     rax, [rdx+8]
0x18000327c  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180003283  jz      short loc_18000329E
0x180003285  mov     rax, [rdx]
0x180003288  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000328f  jnz     short loc_1800032B1
0x180003291  mov     rax, [rdx+8]
0x180003295  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000329c  jnz     short loc_1800032B1
0x18000329e  mov     [r8], rcx
0x1800032a1  xor     ebx, ebx
0x1800032a3  mov     rax, [rcx]
0x1800032a6  mov     rax, [rax+8]
0x1800032aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032af  jmp     short loc_180003314
0x1800032b1  mov     qword ptr [r8], 0
0x1800032b8  mov     ebx, 80004002h
0x1800032bd  mov     rax, [rdx]
0x1800032c0  cmp     rax, qword ptr cs:IID_IMarshal.Data1
0x1800032c7  jnz     short loc_1800032D6
0x1800032c9  mov     rax, [rdx+8]
0x1800032cd  cmp     rax, qword ptr cs:IID_IMarshal.Data4
0x1800032d4  jz      short loc_180003314
0x1800032d6  test    cs:g_dwDebugFlags, 0Fh
0x1800032dd  jz      short loc_180003314
0x1800032df  lea     rax, aQueryinterface_0; "QueryInterface on FTPHOST_CLASS_FACTORY"...
0x1800032e6  mov     r8d, 9Ch
0x1800032ec  mov     [rsp+38h+var_10], rax
0x1800032f1  mov     [rsp+38h+var_18], 80004002h
0x1800032f9  mov     rcx, cs:g_pDebug
0x180003300  lea     r9, aFtphostClassFa_0; "FTPHOST_CLASS_FACTORY::QueryInterface"
0x180003307  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x18000330e  call    cs:__imp_PuDbgPrintError
0x180003314  mov     eax, ebx
0x180003316  add     rsp, 30h
0x18000331a  pop     rbx
0x18000331b  retn
```
