# FTPHOST_CLASS_FACTORY::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003030`
- end: `0x1800031ce`
- name: `?CreateInstance@FTPHOST_CLASS_FACTORY@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `414`
- prototype: `__int64 __fastcall(FTPHOST_CLASS_FACTORY *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x180003030`
- `0x180005010`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x1800030fe`
- `KERNEL32!InitializeSRWLock` at `0x1800030fe`
- `iisutil!PuDbgPrintError` at `0x180003162`
- `iisutil!PuDbgPrintError` at `0x1800031b6`
- `iisutil!PuDbgPrintError` at `0x180003162`
- `iisutil!PuDbgPrintError` at `0x1800031b6`

## string_xrefs

- `0x18000314a`: `FTPHOST_CLASS_FACTORY::CreateInstance`
- `0x1800031a8`: `FTPHOST_CLASS_FACTORY::CreateInstance`
- `0x180003099`: `Creating FTPHOST instance failed, aggregation attempted\n`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS_FACTORY::CreateInstance(
        FTPHOST_CLASS_FACTORY *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // edi
  void *v7; // rax
  GUID *v8; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      v6 = -2147221232;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
          318,
          "FTPHOST_CLASS_FACTORY::CreateInstance",
          -2147221232,
          "Creating FTPHOST instance failed, aggregation attempted\n");
    }
    else
    {
      v7 = operator new(0x40u);
      v8 = (GUID *)v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 1;
        *(_QWORD *)v7 = &FTPHOST_CLASS::`vftable';
        *((_QWORD *)v7 + 2) = 0;
        *((_QWORD *)v7 + 4) = &FTPHOST_CLASS_SUPPORT_ERROR_INFO::`vftable';
        *((_QWORD *)v7 + 5) = 0;
        InitializeSRWLock((PSRWLOCK)v7 + 3);
        *(_QWORD *)v8[2].Data4 = v8;
        v8[3] = GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89;
        v6 = (**(__int64 (__fastcall ***)(GUID *, const struct _GUID *, void **))&v8->Data1)(v8, a3, a4);
        if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
            351,
            "FTPHOST_CLASS_FACTORY::CreateInstance",
            v6,
            "QueryInterface on FTPHOST instance failed\n");
        (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v8->Data1 + 16LL))(v8);
      }
      else
      {
        v6 = -2147024882;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
            334,
            "FTPHOST_CLASS_FACTORY::CreateInstance",
            -2147024882,
            "Allocating FTP_HOST failed\n");
      }
    }
  }
  else
  {
    v6 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class_factory.cxx",
        302,
        "FTPHOST_CLASS_FACTORY::CreateInstance",
        -2147024809,
        "Creating FTPHOST instance failed, bad pointer\n");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003030  mov     [rsp+arg_0], rbx
0x180003035  mov     [rsp+arg_8], rsi
0x18000303a  push    rdi
0x18000303b  sub     rsp, 30h
0x18000303f  mov     rdi, r9
0x180003042  mov     rsi, r8
0x180003045  test    r9, r9
0x180003048  jnz     short loc_18000307B
0x18000304a  test    cs:g_dwDebugFlags, 0Fh
0x180003051  mov     edi, 80070057h
0x180003056  jz      loc_1800031BC
0x18000305c  lea     rax, aCreatingFtphos; "Creating FTPHOST instance failed, bad p"...
0x180003063  mov     r8d, 12Eh
0x180003069  mov     [rsp+38h+var_10], rax
0x18000306e  mov     [rsp+38h+var_18], 80070057h
0x180003076  jmp     loc_1800031A1
0x18000307b  mov     qword ptr [r9], 0
0x180003082  test    rdx, rdx
0x180003085  jz      short loc_1800030B8
0x180003087  test    cs:g_dwDebugFlags, 0Fh
0x18000308e  mov     edi, 80040110h
0x180003093  jz      loc_1800031BC
0x180003099  lea     rax, aCreatingFtphos_0; "Creating FTPHOST instance failed, aggre"...
0x1800030a0  mov     r8d, 13Eh
0x1800030a6  mov     [rsp+38h+var_10], rax
0x1800030ab  mov     [rsp+38h+var_18], 80040110h
0x1800030b3  jmp     loc_1800031A1
0x1800030b8  mov     ecx, 40h ; '@'; Size
0x1800030bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030c2  mov     rbx, rax
0x1800030c5  test    rax, rax
0x1800030c8  jz      loc_180003179
0x1800030ce  lea     rax, ??_7FTPHOST_CLASS@@6B@; const FTPHOST_CLASS::`vftable'
0x1800030d5  mov     dword ptr [rbx+8], 1
0x1800030dc  mov     [rbx], rax
0x1800030df  lea     rcx, [rbx+18h]; SRWLock
0x1800030e3  lea     rax, ??_7FTPHOST_CLASS_SUPPORT_ERROR_INFO@@6B@; const FTPHOST_CLASS_SUPPORT_ERROR_INFO::`vftable'
0x1800030ea  mov     qword ptr [rbx+10h], 0
0x1800030f2  mov     [rbx+20h], rax
0x1800030f6  mov     qword ptr [rbx+28h], 0
0x1800030fe  call    cs:__imp_InitializeSRWLock
0x180003104  mov     [rbx+28h], rbx
0x180003108  mov     r8, rdi
0x18000310b  movups  xmm0, xmmword ptr cs:_GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89.Data1
0x180003112  mov     rdx, rsi
0x180003115  mov     rcx, rbx
0x180003118  movdqu  xmmword ptr [rbx+30h], xmm0
0x18000311d  mov     rax, [rbx]
0x180003120  mov     rax, [rax]
0x180003123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003128  mov     edi, eax
0x18000312a  test    eax, eax
0x18000312c  jns     short loc_180003168
0x18000312e  test    cs:g_dwDebugFlags, 0Fh
0x180003135  jz      short loc_180003168
0x180003137  mov     rcx, cs:g_pDebug
0x18000313e  lea     rax, aQueryinterface; "QueryInterface on FTPHOST instance fail"...
0x180003145  mov     [rsp+38h+var_10], rax
0x18000314a  lea     r9, aFtphostClassFa; "FTPHOST_CLASS_FACTORY::CreateInstance"
0x180003151  mov     r8d, 15Fh
0x180003157  mov     [rsp+38h+var_18], edi
0x18000315b  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003162  call    cs:__imp_PuDbgPrintError
0x180003168  mov     rax, [rbx]
0x18000316b  mov     rcx, rbx
0x18000316e  mov     rax, [rax+10h]
0x180003172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003177  jmp     short loc_1800031BC
0x180003179  test    cs:g_dwDebugFlags, 0Fh
0x180003180  mov     edi, 8007000Eh
0x180003185  jz      short loc_1800031BC
0x180003187  lea     rax, aAllocatingFtpH; "Allocating FTP_HOST failed\n"
0x18000318e  mov     r8d, 14Eh
0x180003194  mov     [rsp+38h+var_10], rax
0x180003199  mov     [rsp+38h+var_18], 8007000Eh
0x1800031a1  mov     rcx, cs:g_pDebug
0x1800031a8  lea     r9, aFtphostClassFa; "FTPHOST_CLASS_FACTORY::CreateInstance"
0x1800031af  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x1800031b6  call    cs:__imp_PuDbgPrintError
0x1800031bc  mov     rbx, [rsp+38h+arg_0]
0x1800031c1  mov     eax, edi
0x1800031c3  mov     rsi, [rsp+38h+arg_8]
0x1800031c8  add     rsp, 30h
0x1800031cc  pop     rdi
0x1800031cd  retn
```
