# ReleaseBinFile(IMetabaseSchemaCompiler *,ushort * *)

- ea: `0x18002d204`
- end: `0x18002d324`
- name: `?ReleaseBinFile@@YAXPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z`
- size: `288`
- prototype: `void __fastcall(struct IMetabaseSchemaCompiler *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b958`

## callees

- `0x180008a08`
- `0x18002d204`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002d286`
- `IisRTL!PuDbgPrintW` at `0x18002d286`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002d244`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002d244`

## string_xrefs

- `0x18002d265`: `[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18002d27a`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002d2c1`: `[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n`

## pseudocode

```c
void __fastcall ReleaseBinFile(struct IMetabaseSchemaCompiler *a1, unsigned __int16 **a2)
{
  bool v2; // zf
  int SimpleObjectByIDEx; // eax
  int v5; // eax
  int v6; // [rsp+28h] [rbp-10h]
  int v7; // [rsp+28h] [rbp-10h]
  struct IMetabaseSchemaCompiler *v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = a1;
  v2 = *a2 == 0;
  v8 = 0;
  v9 = 0;
  if ( !v2 )
  {
    SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v8, L"IIS");
    if ( SimpleObjectByIDEx >= 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(struct IMetabaseSchemaCompiler *, GUID *, __int64 *))v8)(
             v8,
             &IID_IMetabaseSchemaCompiler,
             &v9);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 48LL))(v9, *a2);
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        v7 = v5;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
          248,
          "ReleaseBinFile",
          L"[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n",
          v7);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      v6 = SimpleObjectByIDEx;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
        238,
        "ReleaseBinFile",
        L"[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        v6);
    }
    if ( v8 )
      (*(void (__fastcall **)(struct IMetabaseSchemaCompiler *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x18002d204  mov     rax, rsp
0x18002d207  mov     [rax+8], rcx
0x18002d20b  push    rbx
0x18002d20c  sub     rsp, 30h
0x18002d210  cmp     qword ptr [rdx], 0
0x18002d214  mov     rbx, rdx
0x18002d217  mov     qword ptr [rax+8], 0
0x18002d21f  mov     qword ptr [rax+10h], 0
0x18002d227  jz      loc_18002D30A
0x18002d22d  lea     r9, aIis; "IIS"
0x18002d234  mov     ecx, 1
0x18002d239  lea     r8, [rax+8]
0x18002d23d  lea     rdx, IID_ISimpleTableDispenser2
0x18002d244  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18002d24a  test    eax, eax
0x18002d24c  jns     short loc_18002D28E
0x18002d24e  test    byte ptr cs:g_dwDebugFlags, 3
0x18002d255  jz      loc_18002D2DE
0x18002d25b  mov     [rsp+38h+var_10], eax
0x18002d25f  mov     r8d, 0EEh
0x18002d265  lea     rax, aReleasebinfile_1; "[ReleaseBinFile] DllGetSimpleObjectByID"...
0x18002d26c  mov     rcx, cs:g_pDebug
0x18002d273  lea     r9, aReleasebinfile_0; "ReleaseBinFile"
0x18002d27a  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002d281  mov     [rsp+38h+var_18], rax
0x18002d286  call    cs:__imp_PuDbgPrintW
0x18002d28c  jmp     short loc_18002D2DE
0x18002d28e  mov     rcx, [rsp+38h+arg_0]
0x18002d293  lea     r8, [rsp+38h+arg_8]
0x18002d298  lea     rdx, IID_IMetabaseSchemaCompiler
0x18002d29f  mov     rax, [rcx]
0x18002d2a2  mov     rax, [rax]
0x18002d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2aa  test    eax, eax
0x18002d2ac  jns     short loc_18002D2CA
0x18002d2ae  test    byte ptr cs:g_dwDebugFlags, 3
0x18002d2b5  jz      short loc_18002D2DE
0x18002d2b7  mov     [rsp+38h+var_10], eax
0x18002d2bb  mov     r8d, 0F8h
0x18002d2c1  lea     rax, aReleasebinfile; "[ReleaseBinFile] QueryInterface on comp"...
0x18002d2c8  jmp     short loc_18002D26C
0x18002d2ca  mov     rcx, [rsp+38h+arg_8]
0x18002d2cf  mov     rdx, [rbx]
0x18002d2d2  mov     rax, [rcx]
0x18002d2d5  mov     rax, [rax+30h]
0x18002d2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2de  mov     rcx, [rsp+38h+arg_0]
0x18002d2e3  test    rcx, rcx
0x18002d2e6  jz      short loc_18002D2F4
0x18002d2e8  mov     rax, [rcx]
0x18002d2eb  mov     rax, [rax+10h]
0x18002d2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2f4  mov     rcx, [rsp+38h+arg_8]
0x18002d2f9  test    rcx, rcx
0x18002d2fc  jz      short loc_18002D30A
0x18002d2fe  mov     rax, [rcx]
0x18002d301  mov     rax, [rax+10h]
0x18002d305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d30a  mov     rcx, [rbx]; Block
0x18002d30d  test    rcx, rcx
0x18002d310  jz      short loc_18002D31E
0x18002d312  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d317  mov     qword ptr [rbx], 0
0x18002d31e  add     rsp, 30h
0x18002d322  pop     rbx
0x18002d323  retn
```
