# GetBinFile(IMetabaseSchemaCompiler *,ushort * *)

- ea: `0x18002c9cc`
- end: `0x18002cb94`
- name: `?GetBinFile@@YAJPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct IMetabaseSchemaCompiler *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cf48`

## callees

- `0x180002af0`
- `0x18002c9cc`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002cb7d`
- `ole32!CoTaskMemFree` at `0x18002cb7d`
- `ole32!CoTaskMemAlloc` at `0x18002cadb`
- `ole32!CoTaskMemAlloc` at `0x18002cadb`
- `IisRTL!PuDbgPrintW` at `0x18002cb41`
- `IisRTL!PuDbgPrintW` at `0x18002cb41`

## string_xrefs

- `0x18002ca35`: `[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18002cb35`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002ca78`: `[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n`
- `0x18002cab7`: `[GetBinFile] Unable to get the count of chars in the bin file name. IMetabaseSchemaCompiler::GetBinFileName failed with hr = 0x%x.\n`
- `0x18002cb20`: `[GetBinFile] Unable to get the bin file name. IMetabaseSchemaCompiler::GetBinFileName failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall GetBinFile(struct IMetabaseSchemaCompiler *a1, LPVOID *a2)
{
  int SimpleObjectByIDEx; // eax
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  unsigned __int16 *v7; // rax
  int v8; // eax
  int v10; // [rsp+50h] [rbp+20h] BYREF
  int v11; // [rsp+54h] [rbp+24h]
  __int64 v12; // [rsp+58h] [rbp+28h] BYREF
  void *v13; // [rsp+60h] [rbp+30h] BYREF

  v11 = HIDWORD(a1);
  *a2 = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v13);
  v4 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v13)(v13, &IID_IMetabaseSchemaCompiler, &v12);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v12 + 32LL))(v12, 0, &v10);
      v4 = v6;
      if ( v6 >= 0 )
      {
        v7 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul((unsigned int)(v10 + 1), 2u));
        *a2 = v7;
        if ( v7 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, int *))(*(_QWORD *)v12 + 32LL))(v12, v7, &v10);
          v4 = v8;
          if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
              158,
              "GetBinFile",
              L"[GetBinFile] Unable to get the bin file name. IMetabaseSchemaCompiler::GetBinFileName failed with hr = 0x%x.\n",
              v8);
        }
        else
        {
          v4 = -2147024882;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
          141,
          "GetBinFile",
          L"[GetBinFile] Unable to get the count of chars in the bin file name. IMetabaseSchemaCompiler::GetBinFileName fa"
           "iled with hr = 0x%x.\n",
          v6);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
        129,
        "GetBinFile",
        L"[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n",
        v5);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
      119,
      "GetBinFile",
      L"[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
      SimpleObjectByIDEx);
  }
  if ( v13 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v4 < 0 && *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c9cc  mov     [rsp-18h+arg_0], rcx
0x18002c9d1  push    rbp
0x18002c9d2  push    rbx
0x18002c9d3  push    rdi
0x18002c9d4  mov     rbp, rsp
0x18002c9d7  sub     rsp, 30h
0x18002c9db  mov     rdi, rdx
0x18002c9de  mov     qword ptr [rdx], 0
0x18002c9e5  lea     rdx, IID_ISimpleTableDispenser2
0x18002c9ec  mov     dword ptr [rbp+arg_0], 0
0x18002c9f3  lea     r9, aIis; "IIS"
0x18002c9fa  mov     [rbp+arg_10], 0
0x18002ca02  lea     r8, [rbp+arg_10]
0x18002ca06  mov     [rbp+arg_8], 0
0x18002ca0e  mov     ecx, 1
0x18002ca13  call    DllGetSimpleObjectByIDEx
0x18002ca18  mov     ebx, eax
0x18002ca1a  test    eax, eax
0x18002ca1c  jns     short loc_18002CA41
0x18002ca1e  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ca25  jz      loc_18002CB47
0x18002ca2b  mov     [rsp+30h+var_8], eax
0x18002ca2f  mov     r8d, 77h ; 'w'
0x18002ca35  lea     rax, aReleasebinfile_1; "[ReleaseBinFile] DllGetSimpleObjectByID"...
0x18002ca3c  jmp     loc_18002CB27
0x18002ca41  mov     rcx, [rbp+arg_10]
0x18002ca45  lea     r8, [rbp+arg_8]
0x18002ca49  lea     rdx, IID_IMetabaseSchemaCompiler
0x18002ca50  mov     rax, [rcx]
0x18002ca53  mov     rax, [rax]
0x18002ca56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca5b  mov     ebx, eax
0x18002ca5d  test    eax, eax
0x18002ca5f  jns     short loc_18002CA84
0x18002ca61  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ca68  jz      loc_18002CB47
0x18002ca6e  mov     [rsp+30h+var_8], eax
0x18002ca72  mov     r8d, 81h
0x18002ca78  lea     rax, aReleasebinfile; "[ReleaseBinFile] QueryInterface on comp"...
0x18002ca7f  jmp     loc_18002CB27
0x18002ca84  mov     rcx, [rbp+arg_8]
0x18002ca88  lea     r8, [rbp+arg_0]
0x18002ca8c  xor     edx, edx
0x18002ca8e  mov     rax, [rcx]
0x18002ca91  mov     rax, [rax+20h]
0x18002ca95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca9a  mov     ebx, eax
0x18002ca9c  test    eax, eax
0x18002ca9e  jns     short loc_18002CAC0
0x18002caa0  test    byte ptr cs:g_dwDebugFlags, 3
0x18002caa7  jz      loc_18002CB47
0x18002caad  mov     [rsp+30h+var_8], eax
0x18002cab1  mov     r8d, 8Dh
0x18002cab7  lea     rax, aGetbinfileUnab; "[GetBinFile] Unable to get the count of"...
0x18002cabe  jmp     short loc_18002CB27
0x18002cac0  mov     ecx, dword ptr [rbp+arg_0]
0x18002cac3  mov     eax, 2
0x18002cac8  inc     ecx
0x18002caca  mul     rcx
0x18002cacd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cad4  cmovb   rax, rcx
0x18002cad8  mov     rcx, rax; cb
0x18002cadb  call    cs:__imp_CoTaskMemAlloc
0x18002cae1  mov     [rdi], rax
0x18002cae4  mov     rdx, rax
0x18002cae7  test    rax, rax
0x18002caea  jnz     short loc_18002CAF3
0x18002caec  mov     ebx, 8007000Eh
0x18002caf1  jmp     short loc_18002CB47
0x18002caf3  mov     rcx, [rbp+arg_8]
0x18002caf7  lea     r8, [rbp+arg_0]
0x18002cafb  mov     rax, [rcx]
0x18002cafe  mov     rax, [rax+20h]
0x18002cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb07  mov     ebx, eax
0x18002cb09  test    eax, eax
0x18002cb0b  jns     short loc_18002CB47
0x18002cb0d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002cb14  jz      short loc_18002CB47
0x18002cb16  mov     [rsp+30h+var_8], eax
0x18002cb1a  mov     r8d, 9Eh
0x18002cb20  lea     rax, aGetbinfileUnab_0; "[GetBinFile] Unable to get the bin file"...
0x18002cb27  mov     rcx, cs:g_pDebug
0x18002cb2e  lea     r9, aGetbinfile; "GetBinFile"
0x18002cb35  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002cb3c  mov     [rsp+30h+var_10], rax
0x18002cb41  call    cs:__imp_PuDbgPrintW
0x18002cb47  mov     rcx, [rbp+arg_10]
0x18002cb4b  test    rcx, rcx
0x18002cb4e  jz      short loc_18002CB5C
0x18002cb50  mov     rax, [rcx]
0x18002cb53  mov     rax, [rax+10h]
0x18002cb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb5c  mov     rcx, [rbp+arg_8]
0x18002cb60  test    rcx, rcx
0x18002cb63  jz      short loc_18002CB71
0x18002cb65  mov     rax, [rcx]
0x18002cb68  mov     rax, [rax+10h]
0x18002cb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb71  test    ebx, ebx
0x18002cb73  jns     short loc_18002CB8A
0x18002cb75  mov     rcx, [rdi]; pv
0x18002cb78  test    rcx, rcx
0x18002cb7b  jz      short loc_18002CB8A
0x18002cb7d  call    cs:__imp_CoTaskMemFree
0x18002cb83  mov     qword ptr [rdi], 0
0x18002cb8a  mov     eax, ebx
0x18002cb8c  add     rsp, 30h
0x18002cb90  pop     rdi
0x18002cb91  pop     rbx
0x18002cb92  pop     rbp
0x18002cb93  retn
```
