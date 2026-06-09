# CFileListener::GetGlobalHelperAndCopySchemaFile(CWriterGlobalHelper * *)

- ea: `0x18000aed0`
- end: `0x18000afef`
- name: `?GetGlobalHelperAndCopySchemaFile@CFileListener@@AEAAJPEAPEAVCWriterGlobalHelper@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CFileListener *this, struct CWriterGlobalHelper **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d680`

## callees

- `0x18000aed0`
- `0x18001c508`
- `0x18002056c`
- `0x18002da58`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000afdc`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000afdc`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aee7`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aee7`
- `IisRTL!PuDbgPrintW` at `0x18000af65`
- `IisRTL!PuDbgPrintW` at `0x18000afb7`
- `IisRTL!PuDbgPrintW` at `0x18000af65`
- `IisRTL!PuDbgPrintW` at `0x18000afb7`

## string_xrefs

- `0x18000af41`: `[CFileListener::GetGlobalHelperAndCopySchemaFile] GetGlobalHelper failed with hr = 0x%x. Hence unable to get meta tables and hence unable to process changes.\n`
- `0x18000af4c`: `CFileListener::GetGlobalHelperAndCopySchemaFile`
- `0x18000af93`: `CFileListener::GetGlobalHelperAndCopySchemaFile`
- `0x18000afa5`: `[CFileListener::GetGlobalHelperAndCopySchemaFile] Copying schema file failed with hr = 0x%x. The schema file that is being stored with this version of edits may not be current.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::GetGlobalHelperAndCopySchemaFile(
        CFileListener *this,
        struct CWriterGlobalHelper **a2)
{
  int GlobalHelper; // eax
  unsigned int v5; // r9d
  unsigned int v6; // ebx
  int v7; // eax
  unsigned __int16 *v9; // [rsp+28h] [rbp-30h]
  int v10; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v11; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v12; // [rsp+40h] [rbp-18h]
  unsigned __int16 *v13; // [rsp+48h] [rbp-10h]

  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
  GlobalHelper = GetGlobalHelper(1, a2);
  v6 = GlobalHelper;
  if ( GlobalHelper >= 0 )
  {
    v7 = CopyFileWithSecurityDescriptor(*((unsigned __int16 **)this + 13), *((unsigned __int16 **)this + 29));
    v6 = v7;
    if ( v7 >= 0 )
    {
      *((_DWORD *)this + 138) = 1;
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v10 = v7;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          5213,
          "CFileListener::GetGlobalHelperAndCopySchemaFile",
          L"[CFileListener::GetGlobalHelperAndCopySchemaFile] Copying schema file failed with hr = 0x%x. The schema file t"
           "hat is being stored with this version of edits may not be current.\n",
          v10);
      }
      *((_DWORD *)this + 138) = 0;
      v6 = 0;
    }
  }
  else
  {
    LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C811, 1u, v5, GlobalHelper, 0, 0, v11, v12, v13);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v9) = v6;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        5203,
        "CFileListener::GetGlobalHelperAndCopySchemaFile",
        L"[CFileListener::GetGlobalHelperAndCopySchemaFile] GetGlobalHelper failed with hr = 0x%x. Hence unable to get met"
         "a tables and hence unable to process changes.\n",
        v9);
    }
  }
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  return v6;
}

```

## disassembly

```asm
0x18000aed0  mov     [rsp+arg_0], rbx
0x18000aed5  push    rdi
0x18000aed6  sub     rsp, 50h
0x18000aeda  mov     rdi, rcx
0x18000aedd  mov     rbx, rdx
0x18000aee0  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000aee7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000aeed  mov     rdx, rbx; struct CWriterGlobalHelper **
0x18000aef0  mov     ecx, 1; int
0x18000aef5  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x18000aefa  mov     ebx, eax
0x18000aefc  test    eax, eax
0x18000aefe  jns     short loc_18000AF6D
0x18000af00  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000af07  mov     edx, 0C002C811h; unsigned int
0x18000af0c  mov     [rsp+58h+var_28], 0; unsigned __int16 *
0x18000af15  mov     r8d, 1; unsigned int
0x18000af1b  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x18000af24  mov     dword ptr [rsp+58h+var_38], eax; char
0x18000af28  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000af2d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000af34  jz      loc_18000AFD5
0x18000af3a  mov     rcx, cs:g_pDebug
0x18000af41  lea     rax, aCfilelistenerG_5; "[CFileListener::GetGlobalHelperAndCopyS"...
0x18000af48  mov     dword ptr [rsp+58h+var_30], ebx
0x18000af4c  lea     r9, aCfilelistenerG_6; "CFileListener::GetGlobalHelperAndCopySc"...
0x18000af53  mov     r8d, 1453h
0x18000af59  mov     qword ptr [rsp+58h+var_38], rax
0x18000af5e  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000af65  call    cs:__imp_PuDbgPrintW
0x18000af6b  jmp     short loc_18000AFD5
0x18000af6d  mov     rdx, [rdi+0E8h]; unsigned __int16 *
0x18000af74  mov     rcx, [rdi+68h]; unsigned __int16 *
0x18000af78  call    ?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z; CopyFileWithSecurityDescriptor(ushort *,ushort *)
0x18000af7d  mov     ebx, eax
0x18000af7f  test    eax, eax
0x18000af81  jns     short loc_18000AFCB
0x18000af83  test    byte ptr cs:g_dwDebugFlags, 3
0x18000af8a  jz      short loc_18000AFBD
0x18000af8c  mov     rcx, cs:g_pDebug
0x18000af93  lea     r9, aCfilelistenerG_6; "CFileListener::GetGlobalHelperAndCopySc"...
0x18000af9a  mov     dword ptr [rsp+58h+var_30], eax
0x18000af9e  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000afa5  lea     rax, aCfilelistenerG_3; "[CFileListener::GetGlobalHelperAndCopyS"...
0x18000afac  mov     r8d, 145Dh
0x18000afb2  mov     qword ptr [rsp+58h+var_38], rax
0x18000afb7  call    cs:__imp_PuDbgPrintW
0x18000afbd  mov     dword ptr [rdi+228h], 0
0x18000afc7  xor     ebx, ebx
0x18000afc9  jmp     short loc_18000AFD5
0x18000afcb  mov     dword ptr [rdi+228h], 1
0x18000afd5  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18000afdc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000afe2  mov     eax, ebx
0x18000afe4  mov     rbx, [rsp+58h+arg_0]
0x18000afe9  add     rsp, 50h
0x18000afed  pop     rdi
0x18000afee  retn
```
