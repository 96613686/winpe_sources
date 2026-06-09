# CIISVssWriter::OnPrepareSnapshot(void)

- ea: `0x180003e80`
- end: `0x180003f06`
- name: `?OnPrepareSnapshot@CIISVssWriter@@UEAA_NXZ`
- size: `134`
- prototype: `bool __fastcall(CIISVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003e80`
- `0x180005010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180003ef4`
- `IisRTL!PuDbgPrint` at `0x180003ef4`

## string_xrefs

- `0x180003edb`: `inetsrv\iis\mb\iisadmin\mdwriter.cxx`
- `0x180003e95`: `%windir%\system32\inetsrv`
- `0x180003ed0`: `CIISVssWriter::OnPrepareSnapshot`

## pseudocode

```c
char __fastcall CIISVssWriter::OnPrepareSnapshot(CIISVssWriter *this)
{
  __int64 v2; // rcx
  int v3; // eax

  v2 = *((_QWORD *)this + 1);
  if ( !v2 )
    return 1;
  if ( !(*(unsigned __int8 (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v2 + 104LL))(
          v2,
          L"%windir%\\system32\\inetsrv") )
    return 1;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 160LL))(*((_QWORD *)this + 2));
  if ( v3 >= 0 )
    return 1;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
      293,
      "CIISVssWriter::OnPrepareSnapshot",
      "Error on saving the metabase.  hr = %x\n",
      v3);
  return 0;
}

```

## disassembly

```asm
0x180003e80  push    rbx
0x180003e82  sub     rsp, 30h
0x180003e86  mov     rbx, rcx
0x180003e89  mov     rcx, [rcx+8]
0x180003e8d  test    rcx, rcx
0x180003e90  jz      short loc_180003EFE
0x180003e92  mov     rax, [rcx]
0x180003e95  lea     rdx, aWindirSystem32; "%windir%\\system32\\inetsrv"
0x180003e9c  mov     rax, [rax+68h]
0x180003ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea5  test    al, al
0x180003ea7  jz      short loc_180003EFE
0x180003ea9  mov     rcx, [rbx+10h]
0x180003ead  mov     rax, [rcx]
0x180003eb0  mov     rax, [rax+0A0h]
0x180003eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ebc  test    eax, eax
0x180003ebe  jns     short loc_180003EFE
0x180003ec0  test    byte ptr cs:g_dwDebugFlags, 3
0x180003ec7  jz      short loc_180003EFA
0x180003ec9  mov     rcx, cs:g_pDebug
0x180003ed0  lea     r9, aCiisvsswriterO_0; "CIISVssWriter::OnPrepareSnapshot"
0x180003ed7  mov     [rsp+38h+var_10], eax
0x180003edb  lea     rdx, aInetsrvIisMbIi; "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cx"...
0x180003ee2  lea     rax, aErrorOnSavingT; "Error on saving the metabase.  hr = %x"...
0x180003ee9  mov     r8d, 125h
0x180003eef  mov     [rsp+38h+var_18], rax
0x180003ef4  call    cs:__imp_PuDbgPrint
0x180003efa  xor     al, al
0x180003efc  jmp     short loc_180003F00
0x180003efe  mov     al, 1
0x180003f00  add     rsp, 30h
0x180003f04  pop     rbx
0x180003f05  retn
```
