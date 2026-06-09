# CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)

- ea: `0x18002cbe0`
- end: `0x18002ccbf`
- name: `?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z`
- size: `223`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, struct ISimpleTableDispenser2 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002cf48`

## callees

- `0x18002cbe0`
- `0x180030010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002cc61`
- `IisRTL!PuDbgPrintW` at `0x18002cc61`

## string_xrefs

- `0x18002cc37`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002cc55`: `[GetInternalTableName] Reading table: %s from file: %s.\n`
- `0x18002cc29`: `CWriterGlobalHelper::GetInternalTableName`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::GetInternalTableName(
        CWriterGlobalHelper *this,
        struct ISimpleTableDispenser2 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  bool v4; // zf
  __int64 result; // rax
  int v8; // [rsp+50h] [rbp+8h] BYREF
  struct ISimpleTableDispenser2 *v9; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v4 = *((_QWORD *)this + 8) == 0;
  v8 = 1;
  LODWORD(v9) = 0;
  if ( v4 )
    return 2147942487LL;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
      1065,
      "CWriterGlobalHelper::GetInternalTableName",
      L"[GetInternalTableName] Reading table: %s from file: %s.\n",
      L"TABLEMETA",
      *((_QWORD *)this + 31));
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 **, struct ISimpleTableDispenser2 **))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             0,
             &v10,
             &v9);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, unsigned __int16 **))(**((_QWORD **)this + 8)
                                                                                                  + 32LL))(
             *((_QWORD *)this + 8),
             (unsigned int)v9,
             1,
             &v8,
             0,
             a4);
  return result;
}

```

## disassembly

```asm
0x18002cbe0  mov     rax, rsp
0x18002cbe3  mov     [rax+20h], rbx
0x18002cbe7  mov     [rax+18h], r8
0x18002cbeb  mov     [rax+10h], rdx
0x18002cbef  push    rdi
0x18002cbf0  sub     rsp, 40h
0x18002cbf4  cmp     qword ptr [rcx+40h], 0
0x18002cbf9  mov     rdi, r9
0x18002cbfc  mov     rbx, rcx
0x18002cbff  mov     dword ptr [rax+8], 1
0x18002cc06  mov     dword ptr [rax+10h], 0
0x18002cc0d  jnz     short loc_18002CC19
0x18002cc0f  mov     eax, 80070057h
0x18002cc14  jmp     loc_18002CCB4
0x18002cc19  test    byte ptr cs:g_dwDebugFlags, 3
0x18002cc20  jz      short loc_18002CC67
0x18002cc22  mov     rax, [rcx+0F8h]
0x18002cc29  lea     r9, aCwriterglobalh_1; "CWriterGlobalHelper::GetInternalTableNa"...
0x18002cc30  mov     rcx, cs:g_pDebug
0x18002cc37  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002cc3e  mov     [rsp+48h+var_18], rax
0x18002cc43  mov     r8d, 429h
0x18002cc49  lea     rax, aTablemeta; "TABLEMETA"
0x18002cc50  mov     [rsp+48h+var_20], rax
0x18002cc55  lea     rax, aGetinternaltab; "[GetInternalTableName] Reading table: %"...
0x18002cc5c  mov     [rsp+48h+var_28], rax
0x18002cc61  call    cs:__imp_PuDbgPrintW
0x18002cc67  mov     rcx, [rbx+40h]
0x18002cc6b  lea     r9, [rsp+48h+arg_8]
0x18002cc70  lea     r8, [rsp+48h+arg_10]
0x18002cc75  xor     edx, edx
0x18002cc77  mov     rax, [rcx]
0x18002cc7a  mov     rax, [rax+18h]
0x18002cc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc83  test    eax, eax
0x18002cc85  js      short loc_18002CCB4
0x18002cc87  mov     rcx, [rbx+40h]
0x18002cc8b  lea     r9, [rsp+48h+arg_0]
0x18002cc90  mov     edx, dword ptr [rsp+48h+arg_8]
0x18002cc94  mov     r8d, 1
0x18002cc9a  mov     [rsp+48h+var_20], rdi
0x18002cc9f  mov     [rsp+48h+var_28], 0
0x18002cca8  mov     rax, [rcx]
0x18002ccab  mov     rax, [rax+20h]
0x18002ccaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccb4  mov     rbx, [rsp+48h+arg_18]
0x18002ccb9  add     rsp, 40h
0x18002ccbd  pop     rdi
0x18002ccbe  retn
```
