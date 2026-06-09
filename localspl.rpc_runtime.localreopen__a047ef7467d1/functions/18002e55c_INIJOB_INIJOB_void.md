# INIJOB::~INIJOB(void)

- ea: `0x18002e55c`
- end: `0x18002e705`
- name: `??1INIJOB@@QEAA@XZ`
- size: `425`
- prototype: `void __fastcall(INIJOB *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e530`

## callees

- `0x18002e55c`
- `0x18003513c`
- `0x180036028`
- `0x180054638`
- `0x180098bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e6c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e5e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e6c4`
- `SPOOLSS!DllFreeSplStr` at `0x18002e601`
- `SPOOLSS!DllFreeSplStr` at `0x18002e60b`
- `SPOOLSS!DllFreeSplStr` at `0x18002e615`
- `SPOOLSS!DllFreeSplStr` at `0x18002e622`
- `SPOOLSS!DllFreeSplStr` at `0x18002e62f`
- `SPOOLSS!DllFreeSplStr` at `0x18002e639`
- `SPOOLSS!DllFreeSplStr` at `0x18002e646`
- `SPOOLSS!DllFreeSplStr` at `0x18002e653`
- `SPOOLSS!DllFreeSplStr` at `0x18002e65d`
- `SPOOLSS!DllFreeSplStr` at `0x18002e66a`
- `SPOOLSS!DllFreeSplStr` at `0x18002e677`
- `SPOOLSS!DllFreeSplStr` at `0x18002e684`
- `SPOOLSS!DllFreeSplStr` at `0x18002e691`
- `SPOOLSS!DllFreeSplStr` at `0x18002e69e`
- `SPOOLSS!DllFreeSplStr` at `0x18002e601`
- `SPOOLSS!DllFreeSplStr` at `0x18002e60b`
- `SPOOLSS!DllFreeSplStr` at `0x18002e615`
- `SPOOLSS!DllFreeSplStr` at `0x18002e622`
- `SPOOLSS!DllFreeSplStr` at `0x18002e62f`
- `SPOOLSS!DllFreeSplStr` at `0x18002e639`
- `SPOOLSS!DllFreeSplStr` at `0x18002e646`
- `SPOOLSS!DllFreeSplStr` at `0x18002e653`
- `SPOOLSS!DllFreeSplStr` at `0x18002e65d`
- `SPOOLSS!DllFreeSplStr` at `0x18002e66a`
- `SPOOLSS!DllFreeSplStr` at `0x18002e677`
- `SPOOLSS!DllFreeSplStr` at `0x18002e684`
- `SPOOLSS!DllFreeSplStr` at `0x18002e691`
- `SPOOLSS!DllFreeSplStr` at `0x18002e69e`
- `SPOOLSS!DllFreeSplMem` at `0x18002e6ad`
- `SPOOLSS!DllFreeSplMem` at `0x18002e6ad`

## string_xrefs

- `0x18002e6d7`: `Failed to close token handle.  Error %d`

## pseudocode

```c
void __fastcall INIJOB::~INIJOB(INIJOB *this)
{
  unsigned int v2; // ecx
  __int64 v3; // rax
  unsigned __int16 *v4; // r8
  unsigned int v5; // r9d
  unsigned int v6; // edx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  char *v12; // rcx
  DWORD LastError; // eax
  struct _GUID v14; // [rsp+30h] [rbp-18h] BYREF

  v2 = *((_DWORD *)this + 109);
  v3 = *((_QWORD *)this + 11);
  if ( v3 )
    v4 = *(unsigned __int16 **)(v3 + 24);
  else
    v4 = (unsigned __int16 *)&qword_1800EBF90;
  v5 = *((_DWORD *)this + 8);
  v6 = *((_DWORD *)this + 10);
  v14 = *(struct _GUID *)((char *)this + 600);
  LocalSpoolerTelemetry::LogJobDeleted(&v14, v6, v4, v5, v2);
  v7 = (void *)*((_QWORD *)this + 28);
  if ( v7 )
    CloseHandle(v7);
  v8 = (void *)*((_QWORD *)this + 44);
  if ( v8 )
    CloseHandle(v8);
  v9 = (void *)*((_QWORD *)this + 27);
  if ( v9 )
    CloseHandle(v9);
  v10 = (void *)*((_QWORD *)this + 29);
  if ( v10 )
    CloseHandle(v10);
  if ( *((_QWORD *)this + 33) )
    DeleteDocumentSecurity(this);
  DllFreeSplStr(*((_QWORD *)this + 9));
  DllFreeSplStr(*((_QWORD *)this + 7));
  DllFreeSplStr(*((_QWORD *)this + 6));
  DllFreeSplStr(*((_QWORD *)this + 16));
  DllFreeSplStr(*((_QWORD *)this + 53));
  DllFreeSplStr(*((_QWORD *)this + 8));
  DllFreeSplStr(*((_QWORD *)this + 17));
  DllFreeSplStr(*((_QWORD *)this + 24));
  DllFreeSplStr(*((_QWORD *)this + 10));
  DllFreeSplStr(*((_QWORD *)this + 55));
  DllFreeSplStr(*((_QWORD *)this + 48));
  DllFreeSplStr(*((_QWORD *)this + 51));
  DllFreeSplStr(*((_QWORD *)this + 68));
  DllFreeSplStr(*((_QWORD *)this + 69));
  v11 = *((_QWORD *)this + 13);
  if ( v11 )
    DllFreeSplMem(v11);
  v12 = (char *)*((_QWORD *)this + 32);
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !CloseHandle(v12) )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "INIJOB::~INIJOB",
      L"Failed to close token handle.  Error %d",
      LastError);
  }
  *((_QWORD *)this + 58) = &NAdvancedLibrary::THashTable<JobPropertyHashTableElem,JobPropertyHashTableAdaptorTString,NCoreLibrary::TString,NAdvancedLibrary::TNULLLock,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable';
  NAdvancedLibrary::THashTableBase::~THashTableBase((INIJOB *)((char *)this + 464));
}

```

## disassembly

```asm
0x18002e55c  push    rbx
0x18002e55e  sub     rsp, 40h
0x18002e562  mov     rbx, rcx
0x18002e565  mov     ecx, [rcx+1B4h]
0x18002e56b  mov     rax, [rbx+58h]
0x18002e56f  test    rax, rax
0x18002e572  jz      short loc_18002E57A
0x18002e574  mov     r8, [rax+18h]
0x18002e578  jmp     short loc_18002E581
0x18002e57a  lea     r8, qword_1800EBF90; unsigned __int16 *
0x18002e581  movups  xmm0, xmmword ptr [rbx+258h]
0x18002e588  mov     r9d, [rbx+20h]; unsigned int
0x18002e58c  mov     edx, [rbx+28h]; unsigned int
0x18002e58f  mov     [rsp+48h+var_28], ecx; unsigned int
0x18002e593  lea     rcx, [rsp+48h+var_18]; struct _GUID *
0x18002e598  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18002e59e  call    ?LogJobDeleted@LocalSpoolerTelemetry@@SAXU_GUID@@KPEAGKK@Z; LocalSpoolerTelemetry::LogJobDeleted(_GUID,ulong,ushort *,ulong,ulong)
0x18002e5a3  mov     rcx, [rbx+0E0h]; hObject
0x18002e5aa  test    rcx, rcx
0x18002e5ad  jz      short loc_18002E5B5
0x18002e5af  call    cs:__imp_CloseHandle
0x18002e5b5  mov     rcx, [rbx+160h]; hObject
0x18002e5bc  test    rcx, rcx
0x18002e5bf  jz      short loc_18002E5C7
0x18002e5c1  call    cs:__imp_CloseHandle
0x18002e5c7  mov     rcx, [rbx+0D8h]; hObject
0x18002e5ce  test    rcx, rcx
0x18002e5d1  jz      short loc_18002E5D9
0x18002e5d3  call    cs:__imp_CloseHandle
0x18002e5d9  mov     rcx, [rbx+0E8h]; hObject
0x18002e5e0  test    rcx, rcx
0x18002e5e3  jz      short loc_18002E5EB
0x18002e5e5  call    cs:__imp_CloseHandle
0x18002e5eb  cmp     qword ptr [rbx+108h], 0
0x18002e5f3  jz      short loc_18002E5FD
0x18002e5f5  mov     rcx, rbx; struct INIJOB *
0x18002e5f8  call    ?DeleteDocumentSecurity@@YAHPEAVINIJOB@@@Z; DeleteDocumentSecurity(INIJOB *)
0x18002e5fd  mov     rcx, [rbx+48h]
0x18002e601  call    cs:__imp_DllFreeSplStr
0x18002e607  mov     rcx, [rbx+38h]
0x18002e60b  call    cs:__imp_DllFreeSplStr
0x18002e611  mov     rcx, [rbx+30h]
0x18002e615  call    cs:__imp_DllFreeSplStr
0x18002e61b  mov     rcx, [rbx+80h]
0x18002e622  call    cs:__imp_DllFreeSplStr
0x18002e628  mov     rcx, [rbx+1A8h]
0x18002e62f  call    cs:__imp_DllFreeSplStr
0x18002e635  mov     rcx, [rbx+40h]
0x18002e639  call    cs:__imp_DllFreeSplStr
0x18002e63f  mov     rcx, [rbx+88h]
0x18002e646  call    cs:__imp_DllFreeSplStr
0x18002e64c  mov     rcx, [rbx+0C0h]
0x18002e653  call    cs:__imp_DllFreeSplStr
0x18002e659  mov     rcx, [rbx+50h]
0x18002e65d  call    cs:__imp_DllFreeSplStr
0x18002e663  mov     rcx, [rbx+1B8h]
0x18002e66a  call    cs:__imp_DllFreeSplStr
0x18002e670  mov     rcx, [rbx+180h]
0x18002e677  call    cs:__imp_DllFreeSplStr
0x18002e67d  mov     rcx, [rbx+198h]
0x18002e684  call    cs:__imp_DllFreeSplStr
0x18002e68a  mov     rcx, [rbx+220h]
0x18002e691  call    cs:__imp_DllFreeSplStr
0x18002e697  mov     rcx, [rbx+228h]
0x18002e69e  call    cs:__imp_DllFreeSplStr
0x18002e6a4  mov     rcx, [rbx+68h]
0x18002e6a8  test    rcx, rcx
0x18002e6ab  jz      short loc_18002E6B3
0x18002e6ad  call    cs:__imp_DllFreeSplMem
0x18002e6b3  mov     rcx, [rbx+100h]; hObject
0x18002e6ba  lea     rax, [rcx-1]
0x18002e6be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e6c2  ja      short loc_18002E6EA
0x18002e6c4  call    cs:__imp_CloseHandle
0x18002e6ca  test    eax, eax
0x18002e6cc  jnz     short loc_18002E6EA
0x18002e6ce  call    cs:__imp_GetLastError
0x18002e6d4  mov     r8d, eax
0x18002e6d7  lea     rdx, aFailedToCloseT; "Failed to close token handle.  Error %d"
0x18002e6de  lea     rcx, aInijobInijob; "INIJOB::~INIJOB"
0x18002e6e5  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002e6ea  lea     rcx, [rbx+1D0h]; this
0x18002e6f1  lea     rax, ??_7?$THashTable@VJobPropertyHashTableElem@@VJobPropertyHashTableAdaptorTString@@VTString@NCoreLibrary@@VTNULLLock@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@6B@; const NAdvancedLibrary::THashTable<JobPropertyHashTableElem,JobPropertyHashTableAdaptorTString,NCoreLibrary::TString,NAdvancedLibrary::TNULLLock,NAdvancedLibrary::TDefaultLockAdaptor>::`vftable'
0x18002e6f8  mov     [rcx], rax
0x18002e6fb  add     rsp, 40h
0x18002e6ff  pop     rbx
0x18002e700  jmp     ??1THashTableBase@NAdvancedLibrary@@UEAA@XZ; NAdvancedLibrary::THashTableBase::~THashTableBase(void)
```
