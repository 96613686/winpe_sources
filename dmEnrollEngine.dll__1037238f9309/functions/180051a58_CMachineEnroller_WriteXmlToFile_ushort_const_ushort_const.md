# CMachineEnroller::WriteXmlToFile(ushort const *,ushort const *)

- ea: `0x180051a58`
- end: `0x180051c08`
- name: `?WriteXmlToFile@CMachineEnroller@@SAJPEBG0@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18001390c`

## callees

- `0x180007120`
- `0x1800140d0`
- `0x180014148`
- `0x1800206a8`
- `0x180051a58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051be0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180051bb1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180051bb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180051b86`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180051b86`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x180051ade`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x180051b49`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x180051ade`
- `DMCmnUtils!SafeWideCharToMultiByte` at `0x180051b49`

## string_xrefs

- `0x180051a80`: `CMachineEnroller::WriteXmlToFile`

## pseudocode

```c
__int64 __fastcall CMachineEnroller::WriteXmlToFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  void *v4; // rdi
  char *v5; // r14
  char *v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax
  char *v10; // rax
  HANDLE FileW; // rax
  DWORD v12; // ebx
  unsigned int v13; // ebx
  _QWORD v15[2]; // [rsp+40h] [rbp-10h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+40h] BYREF

  v16 = 0;
  v4 = 0;
  NumberOfBytesWritten = 0;
  v5 = 0;
  v15[0] = "CMachineEnroller::WriteXmlToFile";
  v15[1] = &v16;
  if ( !a1 )
  {
    v16 = -2147467261;
    goto LABEL_17;
  }
  v16 = StringCchLengthW(a1, 0x7FFFFFFFu, 0);
  if ( v16 >= 0 )
  {
    v7 = SafeWideCharToMultiByte(0xFDE9u, 0, a1, -1, v6, (_DWORD)v6, v6, (int *)v6);
    v8 = v7;
    if ( !v7 )
      goto LABEL_5;
    v10 = (char *)SafeHeapAlloc(v7);
    v5 = v10;
    if ( !v10 )
    {
      v16 = -2147024882;
      goto LABEL_17;
    }
    if ( v8 != SafeWideCharToMultiByte(0xFDE9u, 0, a1, -1, v10, v8, 0, 0) )
      goto LABEL_5;
    if ( !v8 )
    {
      v16 = -2147024362;
      goto LABEL_17;
    }
    v16 = 0;
    FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 4u, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL
      || (v12 = v8 - 1, !WriteFile(FileW, v5, v12, &NumberOfBytesWritten, 0))
      || v12 != NumberOfBytesWritten )
    {
LABEL_5:
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v16 = LastError;
    }
  }
LABEL_17:
  SafeHeapFree(v5);
  if ( v4 )
    CloseHandle(v4);
  v13 = v16;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v15);
  return v13;
}

```

## disassembly

```asm
0x180051a58  mov     [rsp-28h+arg_8], rbx
0x180051a5d  push    rbp
0x180051a5e  push    rsi
0x180051a5f  push    rdi
0x180051a60  push    r14
0x180051a62  push    r15
0x180051a64  mov     rbp, rsp
0x180051a67  sub     rsp, 50h
0x180051a6b  mov     r15, rdx
0x180051a6e  mov     rsi, rcx
0x180051a71  mov     [rbp+arg_0], 0
0x180051a78  xor     edi, edi
0x180051a7a  mov     [rbp+NumberOfBytesWritten], edi
0x180051a7d  xor     r14d, r14d
0x180051a80  lea     rax, aCmachineenroll_15; "CMachineEnroller::WriteXmlToFile"
0x180051a87  mov     [rbp+var_10], rax
0x180051a8b  lea     rax, [rbp+arg_0]
0x180051a8f  mov     [rbp+var_8], rax
0x180051a93  test    rcx, rcx
0x180051a96  jnz     short loc_180051AA4
0x180051a98  mov     [rbp+arg_0], 80004003h
0x180051a9f  jmp     loc_180051BD0
0x180051aa4  xor     r8d, r8d; unsigned __int64 *
0x180051aa7  mov     edx, 7FFFFFFFh; unsigned __int64
0x180051aac  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180051ab1  mov     [rbp+arg_0], eax
0x180051ab4  test    eax, eax
0x180051ab6  js      loc_180051BD0
0x180051abc  mov     [rsp+50h+var_18], r8
0x180051ac1  mov     [rsp+50h+hTemplateFile], r8
0x180051ac6  mov     [rsp+50h+dwFlagsAndAttributes], r8d
0x180051acb  mov     qword ptr [rsp+50h+dwCreationDisposition], r8
0x180051ad0  or      r9d, 0FFFFFFFFh
0x180051ad4  mov     r8, rsi
0x180051ad7  xor     edx, edx
0x180051ad9  mov     ecx, 0FDE9h
0x180051ade  call    cs:__imp_?SafeWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; SafeWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180051ae4  mov     ebx, eax
0x180051ae6  test    eax, eax
0x180051ae8  jnz     short loc_180051B04
0x180051aea  call    cs:__imp_GetLastError
0x180051af0  test    eax, eax
0x180051af2  jle     short loc_180051AFC
0x180051af4  movzx   eax, ax
0x180051af7  or      eax, 80070000h
0x180051afc  mov     [rbp+arg_0], eax
0x180051aff  jmp     loc_180051BD0
0x180051b04  mov     rcx, rbx; unsigned __int64
0x180051b07  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180051b0c  mov     r14, rax
0x180051b0f  test    rax, rax
0x180051b12  jnz     short loc_180051B20
0x180051b14  mov     [rbp+arg_0], 8007000Eh
0x180051b1b  jmp     loc_180051BD0
0x180051b20  mov     [rsp+50h+var_18], 0
0x180051b29  mov     [rsp+50h+hTemplateFile], 0
0x180051b32  mov     [rsp+50h+dwFlagsAndAttributes], ebx
0x180051b36  mov     qword ptr [rsp+50h+dwCreationDisposition], r14
0x180051b3b  or      r9d, 0FFFFFFFFh
0x180051b3f  mov     r8, rsi
0x180051b42  xor     edx, edx
0x180051b44  mov     ecx, 0FDE9h
0x180051b49  call    cs:__imp_?SafeWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; SafeWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x180051b4f  cmp     ebx, eax
0x180051b51  jnz     short loc_180051AEA
0x180051b53  cmp     ebx, 1
0x180051b56  jb      short loc_180051BC9
0x180051b58  mov     [rbp+arg_0], 0
0x180051b5f  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180051b68  mov     [rsp+50h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x180051b70  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x180051b78  xor     r9d, r9d; lpSecurityAttributes
0x180051b7b  xor     r8d, r8d; dwShareMode
0x180051b7e  mov     edx, 40000000h; dwDesiredAccess
0x180051b83  mov     rcx, r15; lpFileName
0x180051b86  call    cs:__imp_CreateFileW
0x180051b8c  mov     rdi, rax
0x180051b8f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051b93  jz      loc_180051AEA
0x180051b99  dec     ebx
0x180051b9b  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180051ba4  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180051ba8  mov     r8d, ebx; nNumberOfBytesToWrite
0x180051bab  mov     rdx, r14; lpBuffer
0x180051bae  mov     rcx, rax; hFile
0x180051bb1  call    cs:__imp_WriteFile
0x180051bb7  test    eax, eax
0x180051bb9  jz      loc_180051AEA
0x180051bbf  cmp     ebx, [rbp+NumberOfBytesWritten]
0x180051bc2  jz      short loc_180051BD0
0x180051bc4  jmp     loc_180051AEA
0x180051bc9  mov     [rbp+arg_0], 80070216h
0x180051bd0  mov     rcx, r14; void *
0x180051bd3  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180051bd8  test    rdi, rdi
0x180051bdb  jz      short loc_180051BE6
0x180051bdd  mov     rcx, rdi; hObject
0x180051be0  call    cs:__imp_CloseHandle
0x180051be6  mov     ebx, [rbp+arg_0]
0x180051be9  lea     rcx, [rbp+var_10]; this
0x180051bed  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180051bf2  mov     eax, ebx
0x180051bf4  mov     rbx, [rsp+50h+arg_8]
0x180051bfc  add     rsp, 50h
0x180051c00  pop     r15
0x180051c02  pop     r14
0x180051c04  pop     rdi
0x180051c05  pop     rsi
0x180051c06  pop     rbp
0x180051c07  retn
```
