# SymGetSymbolFileW

- ea: `0x1801addb0`
- end: `0x1801ae27a`
- name: `SymGetSymbolFileW`
- size: `1226`
- prototype: `BOOL __stdcall(HANDLE hProcess, PCWSTR SymPath, PCWSTR ImageFile, DWORD Type, PWSTR SymbolFile, size_t cSymbolFile, PWSTR DbgFile, size_t cDbgFile)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1801adca0`

## callees

- `0x180005764`
- `0x18000aeec`
- `0x180012e6c`
- `0x1800193fc`
- `0x180019480`
- `0x18001a590`
- `0x180027430`
- `0x180168f90`
- `0x1801adaa8`
- `0x1801addb0`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801adfe1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801adfe1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ae248`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ae248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ae03e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ae03e`

## pseudocode

```c
BOOL __stdcall SymGetSymbolFileW(
        HANDLE hProcess,
        PCWSTR SymPath,
        PCWSTR ImageFile,
        DWORD Type,
        PWSTR SymbolFile,
        size_t cSymbolFile,
        PWSTR DbgFile,
        size_t cDbgFile)
{
  HANDLE v10; // r13
  unsigned __int64 v12; // r9
  struct _PROCESS_ENTRY *ProcessEntry; // rax
  char *FileW; // r13
  int ImageDebugInfo; // ebx
  DWORD v17; // ecx
  unsigned int Data1; // ecx
  DWORD sig; // edx
  DWORD age; // r8d
  WCHAR *v21; // r8
  struct SYMSRV_INDEX_INFOW two; // [rsp+60h] [rbp-A0h] BYREF
  SYMSRV_INDEX_INFOW v24; // [rsp+6B0h] [rbp+5B0h] BYREF
  WCHAR v25[264]; // [rsp+D00h] [rbp+C00h] BYREF
  WCHAR FileName[264]; // [rsp+F10h] [rbp+E10h] BYREF
  WCHAR v27[264]; // [rsp+1120h] [rbp+1020h] BYREF
  WCHAR v28[264]; // [rsp+1330h] [rbp+1230h] BYREF
  WCHAR FoundFile[264]; // [rsp+1540h] [rbp+1440h] BYREF

  v10 = hProcess;
  memset_0(two.file, 0, 0x644u);
  two.sizeofstruct = 1608;
  memset_0(v24.file, 0, 0x644u);
  v24.sizeofstruct = 1608;
  if ( !SymPath || !*SymPath )
  {
    ProcessEntry = FindProcessEntry(v10);
    if ( !ProcessEntry )
      goto LABEL_38;
    SymPath = (PCWSTR)*((_QWORD *)ProcessEntry + 8);
    if ( !SymPath )
      goto LABEL_38;
  }
  if ( !SymbolFileName(ImageFile, Type, FileName, v12) )
    goto LABEL_38;
  wcscpy_s_ex(SymbolFile, cSymbolFile, ImageFile);
  ReadImageIndexInfo(ImageFile, &two);
  if ( !Type )
  {
    wcscpy_s_ex(SymbolFile, cSymbolFile, FileName);
    if ( SymFindFileInPathW(
           v10,
           SymPath,
           FileName,
           (PVOID)two.timestamp,
           two.size,
           0,
           2u,
           FoundFile,
           cbFindFileInPath,
           &two) )
    {
      wcscpy_s_ex(SymbolFile, cSymbolFile, FoundFile);
      return 1;
    }
    return 0;
  }
  v25[0] = 0;
  wcscpy_s_ex(SymbolFile, cSymbolFile, FileName);
  if ( two.stripped )
  {
    wcscpy_s_ex(SymbolFile, cSymbolFile, two.dbgfile);
    if ( !SymFindFileInPathW(
            v10,
            SymPath,
            two.dbgfile,
            (PVOID)two.timestamp,
            two.size,
            0,
            2u,
            v25,
            cbFindFileInPath,
            &two) )
      return 0;
    FileW = (char *)CreateFileW(v25, 0x80000000, 1u, 0, 3u, 0, 0);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return 0;
    wcscpy_s_ex(SymbolFile, cSymbolFile, v25);
    if ( DbgFile )
      wcscpy_s_ex(DbgFile, cDbgFile, v25);
    ImageDebugInfo = GetImageDebugInfo(FileW, &v24);
    CloseHandle(FileW);
    if ( !ImageDebugInfo )
    {
      v17 = 193;
LABEL_39:
      SetLastError(v17);
      return 0;
    }
    wcscpy_s_ex(two.pdbfile, 0x105u, v24.pdbfile);
    Data1 = v24.guid.Data1;
    sig = v24.sig;
    age = v24.age;
    v10 = hProcess;
    two.guid = v24.guid;
    two.sig = v24.sig;
    two.age = v24.age;
  }
  else
  {
    age = two.age;
    sig = two.sig;
    Data1 = two.guid.Data1;
  }
  if ( Type == 1 )
  {
    wcscpy_s_ex(SymbolFile, cSymbolFile, v25);
    if ( !v25[0] )
    {
      if ( two.stripped )
        v17 = 34817;
      else
        v17 = 34816;
      goto LABEL_39;
    }
    return 1;
  }
  v27[0] = 0;
  if ( Type == 2 )
  {
    if ( two.pdbfile[0] )
    {
      if ( sig )
        Data1 = sig;
      two.guid.Data1 = Data1;
      if ( !SymFindFileInPathW(v10, SymPath, two.pdbfile, &two.guid, age, 0, 8u, v27, cbFindFileInPath, &two) )
        return 0;
      v21 = v27;
      goto LABEL_30;
    }
LABEL_35:
    v17 = 34818;
    goto LABEL_39;
  }
  if ( Type != 3 )
  {
LABEL_38:
    v17 = 87;
    goto LABEL_39;
  }
  v28[0] = 0;
  if ( sig )
    Data1 = sig;
  two.guid.Data1 = Data1;
  if ( !(unsigned int)ValidGuid(&two.guid) )
    goto LABEL_35;
  wcscpy_s_ex(SymbolFile, cSymbolFile, FileName);
  if ( SymFindFileInPathW(v10, SymPath, FileName, &two.guid, two.age, 0, 8u, v28, cbFindFileInPath, &two) )
  {
    v21 = v28;
LABEL_30:
    wcscpy_s_ex(SymbolFile, cSymbolFile, v21);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1801addb0  mov     [rsp-8+arg_18], rbx
0x1801addb5  push    rbp
0x1801addb6  push    rsi
0x1801addb7  push    rdi
0x1801addb8  push    r12
0x1801addba  push    r13
0x1801addbc  push    r14
0x1801addbe  push    r15
0x1801addc0  lea     rbp, [rsp-1660h]
0x1801addc8  mov     eax, 1760h
0x1801addcd  call    _alloca_probe
0x1801addd2  sub     rsp, rax
0x1801addd5  mov     rax, cs:__security_cookie
0x1801adddc  xor     rax, rsp
0x1801adddf  mov     [rbp+1690h+var_40], rax
0x1801adde6  mov     rax, [rbp+1690h+DbgFile]
0x1801added  mov     rbx, r8
0x1801addf0  mov     r14, [rbp+1690h+SymbolFile]
0x1801addf7  mov     r15, rdx
0x1801addfa  mov     r13, rcx
0x1801addfd  mov     [rsp+1790h+hprocess], rcx
0x1801ade02  mov     esi, 644h
0x1801ade07  mov     [rsp+1790h+var_1740], rax
0x1801ade0c  mov     r8d, esi; Size
0x1801ade0f  lea     rcx, [rsp+1790h+var_1730.file]; void *
0x1801ade14  xor     edx, edx; Val
0x1801ade16  mov     r12d, r9d
0x1801ade19  call    memset_0
0x1801ade1e  lea     edi, [rsi+4]
0x1801ade21  mov     r8d, esi; Size
0x1801ade24  xor     edx, edx; Val
0x1801ade26  mov     [rsp+1790h+var_1730.sizeofstruct], edi
0x1801ade2a  lea     rcx, [rbp+1690h+var_10E0.file]; void *
0x1801ade31  call    memset_0
0x1801ade36  xor     esi, esi
0x1801ade38  mov     [rbp+1690h+var_10E0.sizeofstruct], edi
0x1801ade3e  test    r15, r15
0x1801ade41  jz      short loc_1801ADE49
0x1801ade43  cmp     [r15], si
0x1801ade47  jnz     short loc_1801ADE67
0x1801ade49  mov     rcx, r13; void *
0x1801ade4c  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801ade51  test    rax, rax
0x1801ade54  jz      loc_1801AE243
0x1801ade5a  mov     r15, [rax+40h]
0x1801ade5e  test    r15, r15
0x1801ade61  jz      loc_1801AE243
0x1801ade67  lea     r8, [rbp+1690h+FileName]; unsigned __int16 *
0x1801ade6e  mov     edx, r12d; unsigned int
0x1801ade71  mov     rcx, rbx; unsigned __int16 *
0x1801ade74  call    ?SymbolFileName@@YAPEAGPEBGKPEAG_K@Z; SymbolFileName(ushort const *,ulong,ushort *,unsigned __int64)
0x1801ade79  test    rax, rax
0x1801ade7c  jz      loc_1801AE243
0x1801ade82  mov     rdi, [rbp+1690h+cSymbolFile]
0x1801ade89  mov     r8, rbx; unsigned __int16 *
0x1801ade8c  mov     rdx, rdi; unsigned __int64
0x1801ade8f  mov     rcx, r14; unsigned __int16 *
0x1801ade92  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ade97  lea     rdx, [rsp+1790h+var_1730]; struct SYMSRV_INDEX_INFOW *
0x1801ade9c  mov     rcx, rbx; unsigned __int16 *
0x1801ade9f  call    ?ReadImageIndexInfo@@YAHPEBGPEAUSYMSRV_INDEX_INFOW@@@Z; ReadImageIndexInfo(ushort const *,SYMSRV_INDEX_INFOW *)
0x1801adea4  lea     r8, [rbp+1690h+FileName]; unsigned __int16 *
0x1801adeab  mov     rdx, rdi; unsigned __int64
0x1801adeae  mov     rcx, r14; unsigned __int16 *
0x1801adeb1  test    r12d, r12d
0x1801adeb4  jnz     short loc_1801ADF30
0x1801adeb6  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801adebb  mov     r9d, [rbp+1690h+var_1730.timestamp]; id
0x1801adec2  lea     rax, [rsp+1790h+var_1730]
0x1801adec7  mov     [rsp+1790h+context], rax; context
0x1801adecc  lea     r8, [rbp+1690h+FileName]; FileName
0x1801aded3  lea     rax, ?cbFindFileInPath@@YAHPEBGPEAX@Z; cbFindFileInPath(ushort const *,void *)
0x1801adeda  mov     rdx, r15; SearchPathA
0x1801adedd  mov     [rsp+1790h+callback], rax; callback
0x1801adee2  mov     rcx, r13; hprocess
0x1801adee5  lea     rax, [rbp+1690h+var_250]
0x1801adeec  mov     [rsp+1790h+FoundFile], rax; FoundFile
0x1801adef1  mov     eax, [rbp+1690h+var_1730.size]
0x1801adef7  mov     [rsp+1790h+flags], 2; flags
0x1801adeff  mov     [rsp+1790h+three], esi; three
0x1801adf03  mov     [rsp+1790h+two], eax; two
0x1801adf07  call    SymFindFileInPathW
0x1801adf0c  test    eax, eax
0x1801adf0e  jz      loc_1801AE24E
0x1801adf14  lea     r8, [rbp+1690h+var_250]; unsigned __int16 *
0x1801adf1b  mov     rdx, rdi; unsigned __int64
0x1801adf1e  mov     rcx, r14; unsigned __int16 *
0x1801adf21  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801adf26  lea     eax, [r12+1]
0x1801adf2b  jmp     loc_1801AE250
0x1801adf30  mov     [rbp+1690h+var_A90], si
0x1801adf37  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801adf3c  xor     r9d, r9d
0x1801adf3f  lea     rbx, ?cbFindFileInPath@@YAHPEBGPEAX@Z; cbFindFileInPath(ushort const *,void *)
0x1801adf46  mov     esi, 1
0x1801adf4b  cmp     [rbp+1690h+var_1730.stripped], r9d
0x1801adf52  jz      loc_1801AE0BD
0x1801adf58  lea     r8, [rbp+1690h+var_1730.dbgfile]; unsigned __int16 *
0x1801adf5f  mov     rdx, rdi; unsigned __int64
0x1801adf62  mov     rcx, r14; unsigned __int16 *
0x1801adf65  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801adf6a  mov     r9d, [rbp+1690h+var_1730.timestamp]; id
0x1801adf71  lea     rax, [rsp+1790h+var_1730]
0x1801adf76  mov     [rsp+1790h+context], rax; context
0x1801adf7b  lea     r8, [rbp+1690h+var_1730.dbgfile]; FileName
0x1801adf82  mov     [rsp+1790h+callback], rbx; callback
0x1801adf87  lea     rax, [rbp+1690h+var_A90]
0x1801adf8e  mov     [rsp+1790h+FoundFile], rax; FoundFile
0x1801adf93  xor     ebx, ebx
0x1801adf95  mov     eax, [rbp+1690h+var_1730.size]
0x1801adf9b  mov     rdx, r15; SearchPathA
0x1801adf9e  mov     [rsp+1790h+flags], 2; flags
0x1801adfa6  mov     rcx, r13; hprocess
0x1801adfa9  mov     [rsp+1790h+three], ebx; three
0x1801adfad  mov     [rsp+1790h+two], eax; two
0x1801adfb1  call    SymFindFileInPathW
0x1801adfb6  test    eax, eax
0x1801adfb8  jz      loc_1801AE24E
0x1801adfbe  mov     qword ptr [rsp+1790h+flags], rbx; hTemplateFile
0x1801adfc3  lea     rcx, [rbp+1690h+var_A90]; lpFileName
0x1801adfca  mov     [rsp+1790h+three], ebx; dwFlagsAndAttributes
0x1801adfce  xor     r9d, r9d; lpSecurityAttributes
0x1801adfd1  mov     r8d, esi; dwShareMode
0x1801adfd4  mov     [rsp+1790h+two], 3; dwCreationDisposition
0x1801adfdc  mov     edx, 80000000h; dwDesiredAccess
0x1801adfe1  call    cs:__imp_CreateFileW
0x1801adfe7  mov     r13, rax
0x1801adfea  lea     rdx, [rax-1]
0x1801adfee  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801adff2  ja      loc_1801AE24E
0x1801adff8  lea     r8, [rbp+1690h+var_A90]; unsigned __int16 *
0x1801adfff  mov     rdx, rdi; unsigned __int64
0x1801ae002  mov     rcx, r14; unsigned __int16 *
0x1801ae005  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae00a  mov     rax, [rsp+1790h+var_1740]
0x1801ae00f  test    rax, rax
0x1801ae012  jz      short loc_1801AE02A
0x1801ae014  mov     rdx, [rbp+1690h+cDbgFile]; unsigned __int64
0x1801ae01b  lea     r8, [rbp+1690h+var_A90]; unsigned __int16 *
0x1801ae022  mov     rcx, rax; unsigned __int16 *
0x1801ae025  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae02a  lea     rdx, [rbp+1690h+var_10E0]; struct SYMSRV_INDEX_INFOW *
0x1801ae031  mov     rcx, r13; void *
0x1801ae034  call    ?GetImageDebugInfo@@YAHPEAXPEAUSYMSRV_INDEX_INFOW@@@Z; GetImageDebugInfo(void *,SYMSRV_INDEX_INFOW *)
0x1801ae039  mov     rcx, r13; hObject
0x1801ae03c  mov     ebx, eax
0x1801ae03e  call    cs:__imp_CloseHandle
0x1801ae044  test    ebx, ebx
0x1801ae046  jnz     short loc_1801AE052
0x1801ae048  mov     ecx, 0C1h
0x1801ae04d  jmp     loc_1801AE248
0x1801ae052  lea     r8, [rbp+1690h+var_10E0.pdbfile]; unsigned __int16 *
0x1801ae059  mov     edx, 105h; unsigned __int64
0x1801ae05e  lea     rcx, [rbp+1690h+var_1730.pdbfile]; unsigned __int16 *
0x1801ae065  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae06a  movsd   xmm0, qword ptr [rbp+1690h+var_10E0.guid.Data2]
0x1801ae072  lea     rbx, ?cbFindFileInPath@@YAHPEBGPEAX@Z; cbFindFileInPath(ushort const *,void *)
0x1801ae079  mov     ecx, [rbp+1690h+var_10E0.guid.Data1]
0x1801ae07f  xor     r9d, r9d
0x1801ae082  mov     eax, dword ptr [rbp+1690h+var_10E0.guid.Data4+4]
0x1801ae088  mov     edx, [rbp+1690h+var_10E0.sig]
0x1801ae08e  mov     r8d, [rbp+1690h+var_10E0.age]
0x1801ae095  mov     r13, [rsp+1790h+hprocess]
0x1801ae09a  movsd   qword ptr [rbp+1690h+var_1730.guid.Data2], xmm0
0x1801ae0a2  mov     [rbp+1690h+var_1730.guid.Data1], ecx
0x1801ae0a8  mov     dword ptr [rbp+1690h+var_1730.guid.Data4+4], eax
0x1801ae0ae  mov     [rbp+1690h+var_1730.sig], edx
0x1801ae0b4  mov     [rbp+1690h+var_1730.age], r8d
0x1801ae0bb  jmp     short loc_1801AE0D0
0x1801ae0bd  mov     r8d, [rbp+1690h+var_1730.age]
0x1801ae0c4  mov     edx, [rbp+1690h+var_1730.sig]
0x1801ae0ca  mov     ecx, [rbp+1690h+var_1730.guid.Data1]
0x1801ae0d0  cmp     r12d, esi
0x1801ae0d3  jnz     short loc_1801AE115
0x1801ae0d5  lea     r8, [rbp+1690h+var_A90]; unsigned __int16 *
0x1801ae0dc  mov     rdx, rdi; unsigned __int64
0x1801ae0df  mov     rcx, r14; unsigned __int16 *
0x1801ae0e2  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae0e7  xor     eax, eax
0x1801ae0e9  cmp     [rbp+1690h+var_A90], ax
0x1801ae0f0  jz      short loc_1801AE0F9
0x1801ae0f2  mov     eax, esi
0x1801ae0f4  jmp     loc_1801AE250
0x1801ae0f9  cmp     [rbp+1690h+var_1730.stripped], eax
0x1801ae0ff  jz      short loc_1801AE10B
0x1801ae101  mov     ecx, 8801h
0x1801ae106  jmp     loc_1801AE248
0x1801ae10b  mov     ecx, 8800h
0x1801ae110  jmp     loc_1801AE248
0x1801ae115  mov     [rbp+1690h+var_670], r9w
0x1801ae11d  cmp     r12d, 2
0x1801ae121  jnz     short loc_1801AE1A1
0x1801ae123  cmp     [rbp+1690h+var_1730.pdbfile], r9w
0x1801ae12b  jz      loc_1801AE1CE
0x1801ae131  test    edx, edx
0x1801ae133  lea     rax, [rsp+1790h+var_1730]
0x1801ae138  mov     [rsp+1790h+context], rax; context
0x1801ae13d  lea     rax, [rbp+1690h+var_670]
0x1801ae144  mov     [rsp+1790h+callback], rbx; callback
0x1801ae149  cmovnz  ecx, edx
0x1801ae14c  mov     [rsp+1790h+FoundFile], rax; FoundFile
0x1801ae151  mov     rdx, r15; SearchPathA
0x1801ae154  mov     [rsp+1790h+flags], 8; flags
0x1801ae15c  mov     [rsp+1790h+three], r9d; three
0x1801ae161  lea     r9, [rbp+1690h+var_1730.guid]; id
0x1801ae168  mov     [rsp+1790h+two], r8d; two
0x1801ae16d  lea     r8, [rbp+1690h+var_1730.pdbfile]; FileName
0x1801ae174  mov     [rbp+1690h+var_1730.guid.Data1], ecx
0x1801ae17a  mov     rcx, r13; hprocess
0x1801ae17d  call    SymFindFileInPathW
0x1801ae182  test    eax, eax
0x1801ae184  jz      loc_1801AE24E
0x1801ae18a  lea     r8, [rbp+1690h+var_670]; unsigned __int16 *
0x1801ae191  mov     rdx, rdi; unsigned __int64
0x1801ae194  mov     rcx, r14; unsigned __int16 *
0x1801ae197  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae19c  jmp     loc_1801AE0F2
0x1801ae1a1  cmp     r12d, 3
0x1801ae1a5  jnz     loc_1801AE243
0x1801ae1ab  test    edx, edx
0x1801ae1ad  mov     [rbp+1690h+var_460], r9w
0x1801ae1b5  cmovnz  ecx, edx
0x1801ae1b8  mov     [rbp+1690h+var_1730.guid.Data1], ecx
0x1801ae1be  lea     rcx, [rbp+1690h+var_1730.guid]; struct _GUID *
0x1801ae1c5  call    ?ValidGuid@@YAHPEAU_GUID@@@Z; ValidGuid(_GUID *)
0x1801ae1ca  test    eax, eax
0x1801ae1cc  jnz     short loc_1801AE1D5
0x1801ae1ce  mov     ecx, 8802h
0x1801ae1d3  jmp     short loc_1801AE248
0x1801ae1d5  lea     r8, [rbp+1690h+FileName]; unsigned __int16 *
0x1801ae1dc  mov     rdx, rdi; unsigned __int64
0x1801ae1df  mov     rcx, r14; unsigned __int16 *
0x1801ae1e2  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801ae1e7  lea     rax, [rsp+1790h+var_1730]
0x1801ae1ec  mov     rdx, r15; SearchPathA
0x1801ae1ef  mov     [rsp+1790h+context], rax; context
0x1801ae1f4  lea     r9, [rbp+1690h+var_1730.guid]; id
0x1801ae1fb  mov     [rsp+1790h+callback], rbx; callback
0x1801ae200  lea     rax, [rbp+1690h+var_460]
0x1801ae207  mov     [rsp+1790h+FoundFile], rax; FoundFile
0x1801ae20c  lea     r8, [rbp+1690h+FileName]; FileName
0x1801ae213  mov     eax, [rbp+1690h+var_1730.age]
0x1801ae219  xor     ebx, ebx
0x1801ae21b  mov     [rsp+1790h+flags], 8; flags
0x1801ae223  mov     rcx, r13; hprocess
0x1801ae226  mov     [rsp+1790h+three], ebx; three
0x1801ae22a  mov     [rsp+1790h+two], eax; two
0x1801ae22e  call    SymFindFileInPathW
0x1801ae233  test    eax, eax
0x1801ae235  jz      short loc_1801AE24E
0x1801ae237  lea     r8, [rbp+1690h+var_460]
0x1801ae23e  jmp     loc_1801AE191
0x1801ae243  mov     ecx, 57h ; 'W'; dwErrCode
0x1801ae248  call    cs:__imp_SetLastError
0x1801ae24e  xor     eax, eax
0x1801ae250  mov     rcx, [rbp+1690h+var_40]
0x1801ae257  xor     rcx, rsp; StackCookie
0x1801ae25a  call    __security_check_cookie
0x1801ae25f  mov     rbx, [rsp+1790h+arg_18]
0x1801ae267  add     rsp, 1760h
0x1801ae26e  pop     r15
0x1801ae270  pop     r14
0x1801ae272  pop     r13
0x1801ae274  pop     r12
0x1801ae276  pop     rdi
0x1801ae277  pop     rsi
0x1801ae278  pop     rbp
0x1801ae279  retn
```
