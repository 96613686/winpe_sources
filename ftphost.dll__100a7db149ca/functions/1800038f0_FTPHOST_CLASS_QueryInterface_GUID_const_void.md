# FTPHOST_CLASS::QueryInterface(_GUID const &,void * *)

- ea: `0x1800038f0`
- end: `0x1800039bb`
- name: `?QueryInterface@FTPHOST_CLASS@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(FTPHOST_CLASS *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800038f0`
- `0x180005010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000393c`
- `iisutil!PuDbgPrintError` at `0x18000393c`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS::QueryInterface(FTPHOST_CLASS *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    v3 = 0;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89.Data4 )
    {
      *a3 = this;
    }
    else
    {
      if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_ISupportErrorInfo.Data1
        || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_ISupportErrorInfo.Data4 )
      {
        *a3 = 0;
        return (unsigned int)-2147467262;
      }
      *a3 = (char *)this + 32;
    }
    (*(void (__fastcall **)(FTPHOST_CLASS *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    v3 = -2147024809;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\ftphost_class.cxx",
        282,
        "FTPHOST_CLASS::QueryInterface",
        -2147024809,
        "FTPHOST_CLASS::QueryInterface, bad pointer\n");
  }
  return v3;
}

```

## disassembly

```asm
0x1800038f0  push    rbx
0x1800038f2  sub     rsp, 30h
0x1800038f6  test    r8, r8
0x1800038f9  jnz     short loc_180003944
0x1800038fb  test    cs:g_dwDebugFlags, 0Fh
0x180003902  mov     ebx, 80070057h
0x180003907  jz      loc_1800039B3
0x18000390d  mov     rcx, cs:g_pDebug
0x180003914  lea     rax, aFtphostClassQu; "FTPHOST_CLASS::QueryInterface, bad poin"...
0x18000391b  mov     [rsp+38h+var_10], rax
0x180003920  lea     r9, aFtphostClassQu_0; "FTPHOST_CLASS::QueryInterface"
0x180003927  mov     r8d, 11Ah
0x18000392d  mov     [rsp+38h+var_18], 80070057h
0x180003935  lea     rdx, aInetsrvIisIisr_0; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x18000393c  call    cs:__imp_PuDbgPrintError
0x180003942  jmp     short loc_1800039B3
0x180003944  mov     rax, [rdx]
0x180003947  xor     ebx, ebx
0x180003949  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180003950  jnz     short loc_18000395F
0x180003952  mov     rax, [rdx+8]
0x180003956  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000395d  jz      short loc_180003978
0x18000395f  mov     rax, [rdx]
0x180003962  cmp     rax, qword ptr cs:_GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89.Data1
0x180003969  jnz     short loc_18000397D
0x18000396b  mov     rax, [rdx+8]
0x18000396f  cmp     rax, qword ptr cs:_GUID_ee673f07_b5ab_4036_80ae_59c7b5d32d89.Data4
0x180003976  jnz     short loc_18000397D
0x180003978  mov     [r8], rcx
0x18000397b  jmp     short loc_18000399D
0x18000397d  mov     rax, [rdx]
0x180003980  cmp     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x180003987  jnz     short loc_1800039AB
0x180003989  mov     rax, [rdx+8]
0x18000398d  cmp     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x180003994  jnz     short loc_1800039AB
0x180003996  lea     rax, [rcx+20h]
0x18000399a  mov     [r8], rax
0x18000399d  mov     rax, [rcx]
0x1800039a0  mov     rax, [rax+8]
0x1800039a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a9  jmp     short loc_1800039B3
0x1800039ab  mov     [r8], rbx
0x1800039ae  mov     ebx, 80004002h
0x1800039b3  mov     eax, ebx
0x1800039b5  add     rsp, 30h
0x1800039b9  pop     rbx
0x1800039ba  retn
```
