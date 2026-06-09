# ReleaseBinFile(IMetabaseSchemaCompiler *,ushort * *)

- ea: `0x18002d78c`
- end: `0x18002d8ac`
- name: `?ReleaseBinFile@@YAXPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z`
- size: `288`
- prototype: `void __fastcall(struct IMetabaseSchemaCompiler *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bf8c`

## callees

- `0x180002af0`
- `0x18002d78c`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002d899`
- `ole32!CoTaskMemFree` at `0x18002d899`
- `IisRTL!PuDbgPrintW` at `0x18002d80d`
- `IisRTL!PuDbgPrintW` at `0x18002d80d`

## string_xrefs

- `0x18002d7ec`: `[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18002d801`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002d848`: `[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n`

## pseudocode

```c
void __fastcall ReleaseBinFile(struct IMetabaseSchemaCompiler *a1, LPVOID *a2)
{
  bool v2; // zf
  int SimpleObjectByIDEx; // eax
  int v5; // eax
  int v6; // [rsp+28h] [rbp-10h]
  int v7; // [rsp+28h] [rbp-10h]
  void *v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = a1;
  v2 = *a2 == 0;
  v8 = 0;
  v9 = 0;
  if ( !v2 )
  {
    SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v8);
    if ( SimpleObjectByIDEx >= 0 )
    {
      v5 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v8)(v8, &IID_IMetabaseSchemaCompiler, &v9);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v9 + 48LL))(v9, *a2);
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
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x18002d78c  mov     rax, rsp
0x18002d78f  mov     [rax+8], rcx
0x18002d793  push    rbx
0x18002d794  sub     rsp, 30h
0x18002d798  cmp     qword ptr [rdx], 0
0x18002d79c  mov     rbx, rdx
0x18002d79f  mov     qword ptr [rax+8], 0
0x18002d7a7  mov     qword ptr [rax+10h], 0
0x18002d7af  jz      loc_18002D891
0x18002d7b5  lea     r9, aIis; "IIS"
0x18002d7bc  mov     ecx, 1
0x18002d7c1  lea     r8, [rax+8]
0x18002d7c5  lea     rdx, IID_ISimpleTableDispenser2
0x18002d7cc  call    DllGetSimpleObjectByIDEx
0x18002d7d1  test    eax, eax
0x18002d7d3  jns     short loc_18002D815
0x18002d7d5  test    byte ptr cs:g_dwDebugFlags, 3
0x18002d7dc  jz      loc_18002D865
0x18002d7e2  mov     [rsp+38h+var_10], eax
0x18002d7e6  mov     r8d, 0EEh
0x18002d7ec  lea     rax, aReleasebinfile_1; "[ReleaseBinFile] DllGetSimpleObjectByID"...
0x18002d7f3  mov     rcx, cs:g_pDebug
0x18002d7fa  lea     r9, aReleasebinfile_0; "ReleaseBinFile"
0x18002d801  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002d808  mov     [rsp+38h+var_18], rax
0x18002d80d  call    cs:__imp_PuDbgPrintW
0x18002d813  jmp     short loc_18002D865
0x18002d815  mov     rcx, [rsp+38h+arg_0]
0x18002d81a  lea     r8, [rsp+38h+arg_8]
0x18002d81f  lea     rdx, IID_IMetabaseSchemaCompiler
0x18002d826  mov     rax, [rcx]
0x18002d829  mov     rax, [rax]
0x18002d82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d831  test    eax, eax
0x18002d833  jns     short loc_18002D851
0x18002d835  test    byte ptr cs:g_dwDebugFlags, 3
0x18002d83c  jz      short loc_18002D865
0x18002d83e  mov     [rsp+38h+var_10], eax
0x18002d842  mov     r8d, 0F8h
0x18002d848  lea     rax, aReleasebinfile; "[ReleaseBinFile] QueryInterface on comp"...
0x18002d84f  jmp     short loc_18002D7F3
0x18002d851  mov     rcx, [rsp+38h+arg_8]
0x18002d856  mov     rdx, [rbx]
0x18002d859  mov     rax, [rcx]
0x18002d85c  mov     rax, [rax+30h]
0x18002d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d865  mov     rcx, [rsp+38h+arg_0]
0x18002d86a  test    rcx, rcx
0x18002d86d  jz      short loc_18002D87B
0x18002d86f  mov     rax, [rcx]
0x18002d872  mov     rax, [rax+10h]
0x18002d876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d87b  mov     rcx, [rsp+38h+arg_8]
0x18002d880  test    rcx, rcx
0x18002d883  jz      short loc_18002D891
0x18002d885  mov     rax, [rcx]
0x18002d888  mov     rax, [rax+10h]
0x18002d88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d891  mov     rcx, [rbx]; pv
0x18002d894  test    rcx, rcx
0x18002d897  jz      short loc_18002D8A6
0x18002d899  call    cs:__imp_CoTaskMemFree
0x18002d89f  mov     qword ptr [rbx], 0
0x18002d8a6  add     rsp, 30h
0x18002d8aa  pop     rbx
0x18002d8ab  retn
```
