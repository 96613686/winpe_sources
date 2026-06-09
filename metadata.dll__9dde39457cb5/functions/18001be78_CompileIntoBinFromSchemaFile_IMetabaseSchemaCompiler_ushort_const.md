# CompileIntoBinFromSchemaFile(IMetabaseSchemaCompiler *,ushort const *)

- ea: `0x18001be78`
- end: `0x18001c0f7`
- name: `?CompileIntoBinFromSchemaFile@@YAJPEAUIMetabaseSchemaCompiler@@PEBG@Z`
- size: `639`
- prototype: `__int64 __fastcall(struct IMetabaseSchemaCompiler *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800120b4`
- `0x18001b98c`

## callees

- `0x18001be0c`
- `0x18001be78`
- `0x1800231ec`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18001bebf`
- `KERNEL32!CopyFileW` at `0x18001bebf`
- `KERNEL32!DeleteFileW` at `0x18001bf41`
- `KERNEL32!DeleteFileW` at `0x18001bf41`
- `KERNEL32!GetLastError` at `0x18001bf4f`
- `KERNEL32!GetLastError` at `0x18001c07f`
- `KERNEL32!GetLastError` at `0x18001bf4f`
- `KERNEL32!GetLastError` at `0x18001c07f`
- `IisRTL!PuDbgPrintW` at `0x18001bfaa`
- `IisRTL!PuDbgPrintW` at `0x18001c03b`
- `IisRTL!PuDbgPrintW` at `0x18001c0da`
- `IisRTL!PuDbgPrintW` at `0x18001bfaa`
- `IisRTL!PuDbgPrintW` at `0x18001c03b`
- `IisRTL!PuDbgPrintW` at `0x18001c0da`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bf10`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bffd`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001c077`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bf10`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bffd`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001c077`
- `IISADMIN!RetrieveTracingHandle` at `0x18001be98`
- `IISADMIN!RetrieveTracingHandle` at `0x18001be98`

## string_xrefs

- `0x18001bf99`: `[CompileIntoBinFromSchemaFile] Compile from schema file: %s succeeded, but cannot delete the extsions file: %s into which it was copied. Delete file failed with hr = 0x%x.\n`
- `0x18001bf75`: `CompileIntoBinFromSchemaFile`
- `0x18001c010`: `CompileIntoBinFromSchemaFile`
- `0x18001c0a5`: `CompileIntoBinFromSchemaFile`
- `0x18001c02f`: `[CompileIntoBinFromSchemaFile] Compile from schema file failed with hr = 0x%x.\n`
- `0x18001c0c9`: `[CompileIntoBinFromSchemaFile] Unable to copy %s to %s. CopyFile failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CompileIntoBinFromSchemaFile(struct IMetabaseSchemaCompiler *a1, const unsigned __int16 *a2)
{
  struct CEtwTracer *TracingHandle; // rdi
  _BYTE *v5; // rbx
  _DWORD *v6; // rsi
  signed int LastError; // eax
  signed int v8; // eax
  __int64 v10; // [rsp+28h] [rbp-30h]
  signed int v11; // [rsp+38h] [rbp-20h]
  signed int v12; // [rsp+38h] [rbp-20h]
  int v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = 0;
  TracingHandle = RetrieveTracingHandle();
  ResetFileAttributesIfNeeded((LPCSTR)g_wszSchemaExtensionFile, 1);
  if ( CopyFileW(a2, g_wszSchemaExtensionFile, 0) )
  {
    ResetFileAttributesIfNeeded((LPCSTR)g_wszSchemaExtensionFile, 1);
    v5 = (char *)TracingHandle + 40;
    if ( *((_DWORD *)TracingHandle + 2) && (*v5 & 1) != 0 )
    {
      v6 = (_DWORD *)((char *)TracingHandle + 44);
      if ( *((_DWORD *)TracingHandle + 11) >= 4u )
        CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x13u);
    }
    else
    {
      v6 = (_DWORD *)((char *)TracingHandle + 44);
    }
    v13 = CompileIntoBin(a1, g_wszSchemaExtensionFile, a2);
    if ( v13 < 0 )
    {
      if ( *((_DWORD *)TracingHandle + 2) && (*v5 & 1) != 0 && *v6 )
        CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x14u, &v13, 4, 0, 0);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v10) = v13;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          13089,
          "CompileIntoBinFromSchemaFile",
          L"[CompileIntoBinFromSchemaFile] Compile from schema file failed with hr = 0x%x.\n",
          v10);
      }
    }
    else if ( !DeleteFileW(g_wszSchemaExtensionFile) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v11 = LastError;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          13066,
          "CompileIntoBinFromSchemaFile",
          L"[CompileIntoBinFromSchemaFile] Compile from schema file: %s succeeded, but cannot delete the extsions file: %s"
           " into which it was copied. Delete file failed with hr = 0x%x.\n",
          a2,
          g_wszSchemaExtensionFile,
          v11);
      }
      v13 = 0;
    }
    if ( *((_DWORD *)TracingHandle + 2) && (*v5 & 1) != 0 && *v6 >= 4u )
      CEtwTracer::EtwTraceEvent(TracingHandle, (const struct _GUID *)IISAdminStatupGuid, 0x15u);
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v13 = v8;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v12 = v8;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        13111,
        "CompileIntoBinFromSchemaFile",
        L"[CompileIntoBinFromSchemaFile] Unable to copy %s to %s. CopyFile failed with hr = 0x%x.\n",
        a2,
        g_wszSchemaExtensionFile,
        v12);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001be78  mov     [rsp+arg_0], rbx
0x18001be7d  mov     [rsp+arg_8], rbp
0x18001be82  push    rsi
0x18001be83  push    rdi
0x18001be84  push    r14
0x18001be86  sub     rsp, 40h
0x18001be8a  mov     rbp, rdx
0x18001be8d  mov     [rsp+58h+arg_10], 0
0x18001be95  mov     r14, rcx
0x18001be98  call    cs:__imp_?RetrieveTracingHandle@@YAPEAVCEtwTracer@@XZ; RetrieveTracingHandle(void)
0x18001be9e  mov     rcx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; lpFileName
0x18001bea5  mov     edx, 1; int
0x18001beaa  mov     rdi, rax
0x18001bead  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x18001beb2  mov     rdx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; lpNewFileName
0x18001beb9  xor     r8d, r8d; bFailIfExists
0x18001bebc  mov     rcx, rbp; lpExistingFileName
0x18001bebf  call    cs:__imp_CopyFileW
0x18001bec5  test    eax, eax
0x18001bec7  jz      loc_18001C07F
0x18001becd  mov     rcx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; lpFileName
0x18001bed4  mov     edx, 1; int
0x18001bed9  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x18001bede  cmp     dword ptr [rdi+8], 0
0x18001bee2  lea     rbx, [rdi+28h]
0x18001bee6  jz      short loc_18001BF18
0x18001bee8  test    byte ptr [rbx], 1
0x18001beeb  jz      short loc_18001BF18
0x18001beed  lea     rsi, [rdi+2Ch]
0x18001bef1  cmp     dword ptr [rsi], 4
0x18001bef4  jb      short loc_18001BF1C
0x18001bef6  xor     r9d, r9d
0x18001bef9  mov     [rsp+58h+var_38], 0
0x18001bf02  lea     rdx, IISAdminStatupGuid
0x18001bf09  mov     rcx, rdi
0x18001bf0c  lea     r8d, [r9+13h]
0x18001bf10  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001bf16  jmp     short loc_18001BF1C
0x18001bf18  lea     rsi, [rdi+2Ch]
0x18001bf1c  mov     rdx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; unsigned __int16 *
0x18001bf23  mov     r8, rbp; unsigned __int16 *
0x18001bf26  mov     rcx, r14; struct IMetabaseSchemaCompiler *
0x18001bf29  call    ?CompileIntoBin@@YAJPEAUIMetabaseSchemaCompiler@@PEBG1@Z; CompileIntoBin(IMetabaseSchemaCompiler *,ushort const *,ushort const *)
0x18001bf2e  mov     [rsp+58h+arg_10], eax
0x18001bf32  test    eax, eax
0x18001bf34  js      loc_18001BFBD
0x18001bf3a  mov     rcx, cs:?g_wszSchemaExtensionFile@@3PEAGEA; lpFileName
0x18001bf41  call    cs:__imp_DeleteFileW
0x18001bf47  test    eax, eax
0x18001bf49  jnz     loc_18001C041
0x18001bf4f  call    cs:__imp_GetLastError
0x18001bf55  test    eax, eax
0x18001bf57  jle     short loc_18001BF61
0x18001bf59  movzx   eax, ax
0x18001bf5c  or      eax, 80070000h
0x18001bf61  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bf68  mov     [rsp+58h+arg_10], eax
0x18001bf6c  jz      short loc_18001BFB0
0x18001bf6e  mov     rcx, cs:g_pDebug
0x18001bf75  lea     r9, aCompileintobin_1; "CompileIntoBinFromSchemaFile"
0x18001bf7c  mov     [rsp+58h+var_20], eax
0x18001bf80  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bf87  mov     rax, cs:?g_wszSchemaExtensionFile@@3PEAGEA; ushort * g_wszSchemaExtensionFile
0x18001bf8e  mov     r8d, 330Ah
0x18001bf94  mov     [rsp+58h+var_28], rax
0x18001bf99  lea     rax, aCompileintobin; "[CompileIntoBinFromSchemaFile] Compile "...
0x18001bfa0  mov     [rsp+58h+var_30], rbp
0x18001bfa5  mov     [rsp+58h+var_38], rax
0x18001bfaa  call    cs:__imp_PuDbgPrintW
0x18001bfb0  mov     [rsp+58h+arg_10], 0
0x18001bfb8  jmp     loc_18001C041
0x18001bfbd  cmp     dword ptr [rdi+8], 0
0x18001bfc1  jz      short loc_18001C003
0x18001bfc3  test    byte ptr [rbx], 1
0x18001bfc6  jz      short loc_18001C003
0x18001bfc8  cmp     dword ptr [rsi], 1
0x18001bfcb  jb      short loc_18001C003
0x18001bfcd  mov     [rsp+58h+var_28], 0
0x18001bfd6  lea     r9, [rsp+58h+arg_10]
0x18001bfdb  mov     [rsp+58h+var_30], 0
0x18001bfe4  lea     rdx, IISAdminStatupGuid
0x18001bfeb  mov     r8d, 14h
0x18001bff1  mov     [rsp+58h+var_38], 4
0x18001bffa  mov     rcx, rdi
0x18001bffd  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001c003  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c00a  jz      short loc_18001C041
0x18001c00c  mov     eax, [rsp+58h+arg_10]
0x18001c010  lea     r9, aCompileintobin_1; "CompileIntoBinFromSchemaFile"
0x18001c017  mov     rcx, cs:g_pDebug
0x18001c01e  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001c025  mov     dword ptr [rsp+58h+var_30], eax
0x18001c029  mov     r8d, 3321h
0x18001c02f  lea     rax, aCompileintobin_2; "[CompileIntoBinFromSchemaFile] Compile "...
0x18001c036  mov     [rsp+58h+var_38], rax
0x18001c03b  call    cs:__imp_PuDbgPrintW
0x18001c041  cmp     dword ptr [rdi+8], 0
0x18001c045  jz      loc_18001C0E0
0x18001c04b  test    byte ptr [rbx], 1
0x18001c04e  jz      loc_18001C0E0
0x18001c054  cmp     dword ptr [rsi], 4
0x18001c057  jb      loc_18001C0E0
0x18001c05d  xor     r9d, r9d
0x18001c060  mov     [rsp+58h+var_38], 0
0x18001c069  lea     rdx, IISAdminStatupGuid
0x18001c070  mov     rcx, rdi
0x18001c073  lea     r8d, [r9+15h]
0x18001c077  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001c07d  jmp     short loc_18001C0E0
0x18001c07f  call    cs:__imp_GetLastError
0x18001c085  test    eax, eax
0x18001c087  jle     short loc_18001C091
0x18001c089  movzx   eax, ax
0x18001c08c  or      eax, 80070000h
0x18001c091  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c098  mov     [rsp+58h+arg_10], eax
0x18001c09c  jz      short loc_18001C0E0
0x18001c09e  mov     rcx, cs:g_pDebug
0x18001c0a5  lea     r9, aCompileintobin_1; "CompileIntoBinFromSchemaFile"
0x18001c0ac  mov     [rsp+58h+var_20], eax
0x18001c0b0  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001c0b7  mov     rax, cs:?g_wszSchemaExtensionFile@@3PEAGEA; ushort * g_wszSchemaExtensionFile
0x18001c0be  mov     r8d, 3337h
0x18001c0c4  mov     [rsp+58h+var_28], rax
0x18001c0c9  lea     rax, aCompileintobin_0; "[CompileIntoBinFromSchemaFile] Unable t"...
0x18001c0d0  mov     [rsp+58h+var_30], rbp
0x18001c0d5  mov     [rsp+58h+var_38], rax
0x18001c0da  call    cs:__imp_PuDbgPrintW
0x18001c0e0  mov     eax, [rsp+58h+arg_10]
0x18001c0e4  mov     rbx, [rsp+58h+arg_0]
0x18001c0e9  mov     rbp, [rsp+58h+arg_8]
0x18001c0ee  add     rsp, 40h
0x18001c0f2  pop     r14
0x18001c0f4  pop     rdi
0x18001c0f5  pop     rsi
0x18001c0f6  retn
```
