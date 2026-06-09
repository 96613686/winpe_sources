# CheckPrinterJobToken(ushort *,unsigned __int64,ushort const *,ulong *,_INIPRINTER * *,INIJOB * *,void * *,bool *,_INISPOOLER * const)

- ea: `0x180057288`
- end: `0x18005757c`
- name: `?CheckPrinterJobToken@@YAKPEAG_KPEBGPEAKPEAPEAU_INIPRINTER@@PEAPEAVINIJOB@@PEAPEAXPEA_NQEAU_INISPOOLER@@@Z`
- size: `756`
- prototype: `unsigned int __usercall@<eax>(unsigned __int16 *@<rcx>, unsigned __int64@<rdx>, const unsigned __int16 *@<r8>, unsigned int *@<r9>, struct _INIPRINTER **, struct INIJOB **, void **, bool *, struct _INISPOOLER *const)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18005640c`

## callees

- `0x180008520`
- `0x180008560`
- `0x180009630`
- `0x18000b9ec`
- `0x18000d0d8`
- `0x180011f00`
- `0x18002ea64`
- `0x180033230`
- `0x180038fec`
- `0x18003ea2c`
- `0x1800424d8`
- `0x180054638`
- `0x180057288`
- `0x1800e38a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057408`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800574fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800574fa`
- `SPOOLSS!DllFreeSplStr` at `0x180057426`
- `SPOOLSS!DllFreeSplStr` at `0x180057556`
- `SPOOLSS!DllFreeSplStr` at `0x180057426`
- `SPOOLSS!DllFreeSplStr` at `0x180057556`
- `SPOOLSS!RevertToPrinterSelf` at `0x180057399`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800574bb`
- `SPOOLSS!RevertToPrinterSelf` at `0x180057399`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800574bb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800573d9`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180057527`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800573d9`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180057527`

## string_xrefs

- `0x18005733e`: `CheckPrinterJobToken`
- `0x180057375`: `CheckPrinterJobToken`
- `0x1800573e3`: `Client impersonation failed.`
- `0x180057531`: `Client impersonation failed.`
- `0x1800573f2`: `Failed to get filepool reader handle.`
- `0x180057411`: `CreateFile for %ws, GENERIC_READ failed with error %d`

## pseudocode

```c
__int64 __fastcall CheckPrinterJobToken(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct _INIPRINTER **a5,
        struct INIJOB **a6,
        void **a7,
        bool *a8,
        struct _INISPOOLER *const a9)
{
  bool *v9; // r13
  struct INIJOB **v12; // rax
  unsigned __int16 *v14; // rdi
  struct _INIPRINTER *IniKey; // r12
  __int64 v16; // rbx
  __int64 Job; // rax
  __int64 v18; // rcx
  struct INIJOB *v19; // r14
  struct INIJOB *v21; // rax
  struct INIJOB *v22; // rbp
  HANDLE v23; // rax
  void **v24; // r13
  struct FileListItem *v25; // rcx
  int v26; // r8d
  DWORD LastError; // eax
  unsigned int NameFromHandle; // eax
  int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rcx
  bool *v32; // rax
  DWORD v33; // edx
  HANDLE FileW; // rax
  void **v35; // rbp
  unsigned __int16 *v36; // [rsp+40h] [rbp-58h] BYREF
  HANDLE hToken; // [rsp+A8h] [rbp+10h] BYREF

  HIDWORD(hToken) = HIDWORD(a2);
  v9 = a8;
  LODWORD(hToken) = 0;
  v36 = 0;
  v12 = a6;
  *a8 = 0;
  v14 = 0;
  *v12 = 0;
  *a5 = 0;
  if ( wcsncmp_0(a3, L"Job ", 4u) )
    return 0;
  IniKey = (struct _INIPRINTER *)FindIniKey(*((_QWORD *)a9 + 5), a1, (char *)a9 + 392);
  if ( !IniKey )
    return 0;
  v16 = (unsigned int)Myatol(a3 + 4);
  Job = FindJob(IniKey, v16, &hToken);
  v19 = (struct INIJOB *)Job;
  if ( !Job )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CheckPrinterJobToken", L"Failed to find job %d", (unsigned int)v16);
    return 0;
  }
  if ( (*(_DWORD *)(Job + 32) & 0x100) == 0 )
  {
    v21 = *(struct INIJOB **)(Job + 312);
    v22 = v19;
    if ( v21 )
      v22 = v21;
    if ( *((_QWORD *)v22 + 49) == -1 )
    {
      GetFullNameFromId(*((_QWORD *)v22 + 11), *((_DWORD *)v22 + 10), 1, (_DWORD)a1, 539, 0);
      LeaveSplSem(v31);
      v32 = (bool *)RevertToPrinterSelf();
      v33 = 8 * (*((_DWORD *)v22 + 8) & 0x8000000 | 0xF0000000);
      a8 = v32;
      FileW = CreateFileW(a1, v33, 7u, 0, 3u, 0x80u, 0);
      v35 = a7;
      *v9 = 0;
      *v35 = FileW;
      EnterSplSem(0);
      if ( a8 && !ImpersonatePrinterClient(a8) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError("CheckPrinterJobToken", L"Client impersonation failed.");
        goto LABEL_15;
      }
      if ( *v35 == (void *)-1LL )
        goto LABEL_15;
    }
    else
    {
      LeaveSplSem(v18);
      v23 = RevertToPrinterSelf();
      v24 = a7;
      v25 = (struct FileListItem *)*((_QWORD *)v22 + 49);
      hToken = v23;
      GetReaderFromHandle(v25, a7);
      *a8 = 1;
      if ( hToken && !ImpersonatePrinterClient(hToken) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError("CheckPrinterJobToken", L"Client impersonation failed.");
LABEL_14:
        LocalSpoolerTelemetry::WriteDbgTraceWarning("CheckPrinterJobToken", L"Failed to get filepool reader handle.");
        EnterSplSem(0);
LABEL_15:
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "CheckPrinterJobToken",
          L"CreateFile for %ws, GENERIC_READ failed with error %d",
          a1,
          LastError);
        DllFreeSplStr(v14);
        return 2;
      }
      if ( (char *)*v24 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_14;
      NameFromHandle = GetNameFromHandle(*((void **)v22 + 49), &v36, v26);
      v29 = BoolFromHResult(NameFromHandle);
      v14 = v36;
      if ( !v29 )
        goto LABEL_14;
      if ( !v36 )
        goto LABEL_14;
      v30 = StringCchCopyW(a1, 0x21Bu, v36);
      if ( !(unsigned int)BoolFromHResult(v30) )
        goto LABEL_14;
      EnterSplSem(0);
    }
    *a4 |= 2u;
    goto LABEL_26;
  }
  *a4 |= 0xAu;
LABEL_26:
  DllFreeSplStr(v14);
  *a6 = v19;
  *a5 = IniKey;
  return 1;
}

```

## disassembly

```asm
0x180057288  mov     rax, rsp
0x18005728b  mov     [rax+10h], rdx
0x18005728f  push    rbx
0x180057290  push    rbp
0x180057291  push    rsi
0x180057292  push    rdi
0x180057293  push    r12
0x180057295  push    r13
0x180057297  push    r14
0x180057299  push    r15
0x18005729b  sub     rsp, 58h
0x18005729f  mov     r13, [rsp+98h+arg_38]
0x1800572a7  lea     rdx, aJob; "Job "
0x1800572ae  xor     ebp, ebp
0x1800572b0  mov     rbx, r8
0x1800572b3  mov     [rax+10h], ebp
0x1800572b6  mov     r15, rcx
0x1800572b9  mov     [rax-58h], rbp
0x1800572bd  mov     rcx, rbx; String1
0x1800572c0  mov     rax, [rsp+98h+arg_28]
0x1800572c8  mov     rsi, r9
0x1800572cb  lea     r8d, [rbp+4]; MaxCount
0x1800572cf  mov     [r13+0], bpl
0x1800572d3  mov     edi, ebp
0x1800572d5  mov     [rax], rbp
0x1800572d8  mov     rax, [rsp+98h+arg_20]
0x1800572e0  mov     [rax], rbp
0x1800572e3  call    wcsncmp_0
0x1800572e8  test    eax, eax
0x1800572ea  jnz     short loc_18005734A
0x1800572ec  mov     rcx, [rsp+98h+arg_40]
0x1800572f4  mov     rdx, r15
0x1800572f7  lea     r8, [rcx+188h]
0x1800572fe  mov     rcx, [rcx+28h]
0x180057302  call    FindIniKey
0x180057307  mov     r12, rax
0x18005730a  test    rax, rax
0x18005730d  jz      short loc_18005734A
0x18005730f  lea     rcx, [rbx+8]
0x180057313  call    Myatol
0x180057318  lea     r8, [rsp+98h+hToken]
0x180057320  mov     edx, eax
0x180057322  mov     rcx, r12
0x180057325  mov     ebx, eax
0x180057327  call    FindJob
0x18005732c  mov     r14, rax
0x18005732f  test    rax, rax
0x180057332  jnz     short loc_18005735D
0x180057334  mov     r8d, ebx
0x180057337  lea     rdx, aFailedToFindJo; "Failed to find job %d"
0x18005733e  lea     rcx, aCheckprinterjo; "CheckPrinterJobToken"
0x180057345  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005734a  xor     eax, eax
0x18005734c  add     rsp, 58h
0x180057350  pop     r15
0x180057352  pop     r14
0x180057354  pop     r13
0x180057356  pop     r12
0x180057358  pop     rdi
0x180057359  pop     rsi
0x18005735a  pop     rbp
0x18005735b  pop     rbx
0x18005735c  retn
0x18005735d  test    dword ptr [rax+20h], 100h
0x180057364  jz      short loc_18005736E
0x180057366  or      dword ptr [rsi], 0Ah
0x180057369  jmp     loc_180057553
0x18005736e  mov     rax, [rax+138h]
0x180057375  lea     rbx, aCheckprinterjo; "CheckPrinterJobToken"
0x18005737c  test    rax, rax
0x18005737f  mov     rbp, r14
0x180057382  cmovnz  rbp, rax
0x180057386  cmp     qword ptr [rbp+188h], 0FFFFFFFFFFFFFFFFh
0x18005738e  jz      loc_180057494
0x180057394  call    LeaveSplSem
0x180057399  call    cs:__imp_RevertToPrinterSelf
0x18005739f  mov     r13, [rsp+98h+arg_30]
0x1800573a7  mov     rcx, [rbp+188h]; struct FileListItem *
0x1800573ae  mov     rdx, r13; void **
0x1800573b1  mov     [rsp+98h+hToken], rax
0x1800573b9  call    ?GetReaderFromHandle@@YAJPEAXPEAPEAX@Z; GetReaderFromHandle(void *,void * *)
0x1800573be  mov     rax, [rsp+98h+arg_38]
0x1800573c6  mov     byte ptr [rax], 1
0x1800573c9  mov     rax, [rsp+98h+hToken]
0x1800573d1  test    rax, rax
0x1800573d4  jz      short loc_180057436
0x1800573d6  mov     rcx, rax; hToken
0x1800573d9  call    cs:__imp_ImpersonatePrinterClient
0x1800573df  test    eax, eax
0x1800573e1  jnz     short loc_180057436
0x1800573e3  lea     rdx, aClientImperson; "Client impersonation failed."
0x1800573ea  mov     rcx, rbx; char *
0x1800573ed  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800573f2  lea     rdx, aFailedToGetFil; "Failed to get filepool reader handle."
0x1800573f9  mov     rcx, rbx; char *
0x1800573fc  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180057401  xor     ecx, ecx
0x180057403  call    EnterSplSem
0x180057408  call    cs:__imp_GetLastError
0x18005740e  mov     r8, r15
0x180057411  lea     rdx, aCreatefileForW; "CreateFile for %ws, GENERIC_READ failed"...
0x180057418  mov     r9d, eax
0x18005741b  mov     rcx, rbx; char *
0x18005741e  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180057423  mov     rcx, rdi
0x180057426  call    cs:__imp_DllFreeSplStr
0x18005742c  mov     eax, 2
0x180057431  jmp     loc_18005734C
0x180057436  mov     rax, [r13+0]
0x18005743a  dec     rax
0x18005743d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180057441  ja      short loc_1800573F2
0x180057443  mov     rcx, [rbp+188h]; void *
0x18005744a  lea     rdx, [rsp+98h+var_58]; unsigned __int16 **
0x18005744f  call    ?GetNameFromHandle@@YAJPEAXPEAPEAGH@Z; GetNameFromHandle(void *,ushort * *,int)
0x180057454  mov     ecx, eax
0x180057456  call    BoolFromHResult
0x18005745b  mov     rdi, [rsp+98h+var_58]
0x180057460  test    eax, eax
0x180057462  jz      short loc_1800573F2
0x180057464  test    rdi, rdi
0x180057467  jz      short loc_1800573F2
0x180057469  mov     r8, rdi; unsigned __int16 *
0x18005746c  mov     edx, 21Bh; unsigned __int64
0x180057471  mov     rcx, r15; unsigned __int16 *
0x180057474  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057479  mov     ecx, eax
0x18005747b  call    BoolFromHResult
0x180057480  test    eax, eax
0x180057482  jz      loc_1800573F2
0x180057488  xor     ecx, ecx
0x18005748a  call    EnterSplSem
0x18005748f  jmp     loc_180057550
0x180057494  mov     edx, [rbp+28h]
0x180057497  mov     r9, r15
0x18005749a  mov     rcx, [rbp+58h]
0x18005749e  mov     r8d, 1
0x1800574a4  mov     [rsp+98h+dwFlagsAndAttributes], edi
0x1800574a8  mov     qword ptr [rsp+98h+dwCreationDisposition], 21Bh
0x1800574b1  call    GetFullNameFromId
0x1800574b6  call    LeaveSplSem
0x1800574bb  call    cs:__imp_RevertToPrinterSelf
0x1800574c1  mov     edx, [rbp+20h]
0x1800574c4  xor     r9d, r9d; lpSecurityAttributes
0x1800574c7  and     edx, 0F8000000h
0x1800574cd  mov     [rsp+98h+hTemplateFile], rdi; hTemplateFile
0x1800574d2  or      edx, 0F0000000h
0x1800574d8  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800574e0  shl     edx, 3; dwDesiredAccess
0x1800574e3  mov     rcx, r15; lpFileName
0x1800574e6  lea     r8d, [r9+7]; dwShareMode
0x1800574ea  mov     [rsp+98h+arg_38], rax
0x1800574f2  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x1800574fa  call    cs:__imp_CreateFileW
0x180057500  mov     rbp, [rsp+98h+arg_30]
0x180057508  xor     ecx, ecx
0x18005750a  mov     [r13+0], dil
0x18005750e  mov     [rbp+0], rax
0x180057512  call    EnterSplSem
0x180057517  mov     rax, [rsp+98h+arg_38]
0x18005751f  test    rax, rax
0x180057522  jz      short loc_180057545
0x180057524  mov     rcx, rax; hToken
0x180057527  call    cs:__imp_ImpersonatePrinterClient
0x18005752d  test    eax, eax
0x18005752f  jnz     short loc_180057545
0x180057531  lea     rdx, aClientImperson; "Client impersonation failed."
0x180057538  mov     rcx, rbx; char *
0x18005753b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180057540  jmp     loc_180057408
0x180057545  cmp     qword ptr [rbp+0], 0FFFFFFFFFFFFFFFFh
0x18005754a  jz      loc_180057408
0x180057550  or      dword ptr [rsi], 2
0x180057553  mov     rcx, rdi
0x180057556  call    cs:__imp_DllFreeSplStr
0x18005755c  mov     rax, [rsp+98h+arg_28]
0x180057564  mov     [rax], r14
0x180057567  mov     rax, [rsp+98h+arg_20]
0x18005756f  mov     [rax], r12
0x180057572  mov     eax, 1
0x180057577  jmp     loc_18005734C
```
