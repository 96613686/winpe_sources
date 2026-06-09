# CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)

- ea: `0x18002c390`
- end: `0x18002c46f`
- name: `?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z`
- size: `223`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, struct ISimpleTableDispenser2 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c8fc`

## callees

- `0x18002c390`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002c411`
- `IisRTL!PuDbgPrintW` at `0x18002c411`

## string_xrefs

- `0x18002c3e7`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002c405`: `[GetInternalTableName] Reading table: %s from file: %s.\n`
- `0x18002c3d9`: `CWriterGlobalHelper::GetInternalTableName`

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
0x18002c390  mov     rax, rsp
0x18002c393  mov     [rax+20h], rbx
0x18002c397  mov     [rax+18h], r8
0x18002c39b  mov     [rax+10h], rdx
0x18002c39f  push    rdi
0x18002c3a0  sub     rsp, 40h
0x18002c3a4  cmp     qword ptr [rcx+40h], 0
0x18002c3a9  mov     rdi, r9
0x18002c3ac  mov     rbx, rcx
0x18002c3af  mov     dword ptr [rax+8], 1
0x18002c3b6  mov     dword ptr [rax+10h], 0
0x18002c3bd  jnz     short loc_18002C3C9
0x18002c3bf  mov     eax, 80070057h
0x18002c3c4  jmp     loc_18002C464
0x18002c3c9  test    byte ptr cs:g_dwDebugFlags, 3
0x18002c3d0  jz      short loc_18002C417
0x18002c3d2  mov     rax, [rcx+0F8h]
0x18002c3d9  lea     r9, aCwriterglobalh_1; "CWriterGlobalHelper::GetInternalTableNa"...
0x18002c3e0  mov     rcx, cs:g_pDebug
0x18002c3e7  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002c3ee  mov     [rsp+48h+var_18], rax
0x18002c3f3  mov     r8d, 429h
0x18002c3f9  lea     rax, aTablemeta; "TABLEMETA"
0x18002c400  mov     [rsp+48h+var_20], rax
0x18002c405  lea     rax, aGetinternaltab; "[GetInternalTableName] Reading table: %"...
0x18002c40c  mov     [rsp+48h+var_28], rax
0x18002c411  call    cs:__imp_PuDbgPrintW
0x18002c417  mov     rcx, [rbx+40h]
0x18002c41b  lea     r9, [rsp+48h+arg_8]
0x18002c420  lea     r8, [rsp+48h+arg_10]
0x18002c425  xor     edx, edx
0x18002c427  mov     rax, [rcx]
0x18002c42a  mov     rax, [rax+18h]
0x18002c42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c433  test    eax, eax
0x18002c435  js      short loc_18002C464
0x18002c437  mov     rcx, [rbx+40h]
0x18002c43b  lea     r9, [rsp+48h+arg_0]
0x18002c440  mov     edx, dword ptr [rsp+48h+arg_8]
0x18002c444  mov     r8d, 1
0x18002c44a  mov     [rsp+48h+var_20], rdi
0x18002c44f  mov     [rsp+48h+var_28], 0
0x18002c458  mov     rax, [rcx]
0x18002c45b  mov     rax, [rax+20h]
0x18002c45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c464  mov     rbx, [rsp+48h+arg_18]
0x18002c469  add     rsp, 40h
0x18002c46d  pop     rdi
0x18002c46e  retn
```
