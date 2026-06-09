# GetBinFile(IMetabaseSchemaCompiler *,ushort * *)

- ea: `0x18002c17c`
- end: `0x18002c343`
- name: `?GetBinFile@@YAJPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z`
- size: `455`
- prototype: `__int64 __fastcall(struct IMetabaseSchemaCompiler *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c8fc`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x18002c17c`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002c2f1`
- `IisRTL!PuDbgPrintW` at `0x18002c2f1`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002c1c3`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002c1c3`

## string_xrefs

- `0x18002c1e6`: `[ReleaseBinFile] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18002c2e5`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002c229`: `[ReleaseBinFile] QueryInterface on compiler failed with hr = 0x%x.\n`
- `0x18002c268`: `[GetBinFile] Unable to get the count of chars in the bin file name. IMetabaseSchemaCompiler::GetBinFileName failed with hr = 0x%x.\n`
- `0x18002c2d0`: `[GetBinFile] Unable to get the bin file name. IMetabaseSchemaCompiler::GetBinFileName failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall GetBinFile(struct IMetabaseSchemaCompiler *a1, unsigned __int16 **a2)
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
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF

  v11 = HIDWORD(a1);
  *a2 = 0;
  v10 = 0;
  v13 = 0;
  v12 = 0;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v13, L"IIS");
  v4 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_IMetabaseSchemaCompiler, &v12);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v12 + 32LL))(v12, 0, &v10);
      v4 = v6;
      if ( v6 >= 0 )
      {
        v7 = (unsigned __int16 *)operator new(saturated_mul((unsigned int)(v10 + 1), 2u));
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v4 < 0 && *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c17c  mov     [rsp-18h+arg_0], rcx
0x18002c181  push    rbp
0x18002c182  push    rbx
0x18002c183  push    rdi
0x18002c184  mov     rbp, rsp
0x18002c187  sub     rsp, 30h
0x18002c18b  mov     rdi, rdx
0x18002c18e  mov     qword ptr [rdx], 0
0x18002c195  lea     rdx, IID_ISimpleTableDispenser2
0x18002c19c  mov     dword ptr [rbp+arg_0], 0
0x18002c1a3  lea     r9, aIis; "IIS"
0x18002c1aa  mov     [rbp+arg_10], 0
0x18002c1b2  lea     r8, [rbp+arg_10]
0x18002c1b6  mov     [rbp+arg_8], 0
0x18002c1be  mov     ecx, 1
0x18002c1c3  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18002c1c9  mov     ebx, eax
0x18002c1cb  test    eax, eax
0x18002c1cd  jns     short loc_18002C1F2
0x18002c1cf  test    byte ptr cs:g_dwDebugFlags, 3
0x18002c1d6  jz      loc_18002C2F7
0x18002c1dc  mov     [rsp+30h+var_8], eax
0x18002c1e0  mov     r8d, 77h ; 'w'
0x18002c1e6  lea     rax, aReleasebinfile_1; "[ReleaseBinFile] DllGetSimpleObjectByID"...
0x18002c1ed  jmp     loc_18002C2D7
0x18002c1f2  mov     rcx, [rbp+arg_10]
0x18002c1f6  lea     r8, [rbp+arg_8]
0x18002c1fa  lea     rdx, IID_IMetabaseSchemaCompiler
0x18002c201  mov     rax, [rcx]
0x18002c204  mov     rax, [rax]
0x18002c207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c20c  mov     ebx, eax
0x18002c20e  test    eax, eax
0x18002c210  jns     short loc_18002C235
0x18002c212  test    byte ptr cs:g_dwDebugFlags, 3
0x18002c219  jz      loc_18002C2F7
0x18002c21f  mov     [rsp+30h+var_8], eax
0x18002c223  mov     r8d, 81h
0x18002c229  lea     rax, aReleasebinfile; "[ReleaseBinFile] QueryInterface on comp"...
0x18002c230  jmp     loc_18002C2D7
0x18002c235  mov     rcx, [rbp+arg_8]
0x18002c239  lea     r8, [rbp+arg_0]
0x18002c23d  xor     edx, edx
0x18002c23f  mov     rax, [rcx]
0x18002c242  mov     rax, [rax+20h]
0x18002c246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c24b  mov     ebx, eax
0x18002c24d  test    eax, eax
0x18002c24f  jns     short loc_18002C271
0x18002c251  test    byte ptr cs:g_dwDebugFlags, 3
0x18002c258  jz      loc_18002C2F7
0x18002c25e  mov     [rsp+30h+var_8], eax
0x18002c262  mov     r8d, 8Dh
0x18002c268  lea     rax, aGetbinfileUnab; "[GetBinFile] Unable to get the count of"...
0x18002c26f  jmp     short loc_18002C2D7
0x18002c271  mov     ecx, dword ptr [rbp+arg_0]
0x18002c274  mov     eax, 2
0x18002c279  inc     ecx
0x18002c27b  mul     rcx
0x18002c27e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c285  cmovb   rax, rcx
0x18002c289  mov     rcx, rax; Size
0x18002c28c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c291  mov     [rdi], rax
0x18002c294  mov     rdx, rax
0x18002c297  test    rax, rax
0x18002c29a  jnz     short loc_18002C2A3
0x18002c29c  mov     ebx, 8007000Eh
0x18002c2a1  jmp     short loc_18002C2F7
0x18002c2a3  mov     rcx, [rbp+arg_8]
0x18002c2a7  lea     r8, [rbp+arg_0]
0x18002c2ab  mov     rax, [rcx]
0x18002c2ae  mov     rax, [rax+20h]
0x18002c2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2b7  mov     ebx, eax
0x18002c2b9  test    eax, eax
0x18002c2bb  jns     short loc_18002C2F7
0x18002c2bd  test    byte ptr cs:g_dwDebugFlags, 3
0x18002c2c4  jz      short loc_18002C2F7
0x18002c2c6  mov     [rsp+30h+var_8], eax
0x18002c2ca  mov     r8d, 9Eh
0x18002c2d0  lea     rax, aGetbinfileUnab_0; "[GetBinFile] Unable to get the bin file"...
0x18002c2d7  mov     rcx, cs:g_pDebug
0x18002c2de  lea     r9, aGetbinfile; "GetBinFile"
0x18002c2e5  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002c2ec  mov     [rsp+30h+var_10], rax
0x18002c2f1  call    cs:__imp_PuDbgPrintW
0x18002c2f7  mov     rcx, [rbp+arg_10]
0x18002c2fb  test    rcx, rcx
0x18002c2fe  jz      short loc_18002C30C
0x18002c300  mov     rax, [rcx]
0x18002c303  mov     rax, [rax+10h]
0x18002c307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c30c  mov     rcx, [rbp+arg_8]
0x18002c310  test    rcx, rcx
0x18002c313  jz      short loc_18002C321
0x18002c315  mov     rax, [rcx]
0x18002c318  mov     rax, [rax+10h]
0x18002c31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c321  test    ebx, ebx
0x18002c323  jns     short loc_18002C339
0x18002c325  mov     rcx, [rdi]; Block
0x18002c328  test    rcx, rcx
0x18002c32b  jz      short loc_18002C339
0x18002c32d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c332  mov     qword ptr [rdi], 0
0x18002c339  mov     eax, ebx
0x18002c33b  add     rsp, 30h
0x18002c33f  pop     rdi
0x18002c340  pop     rbx
0x18002c341  pop     rbp
0x18002c342  retn
```
