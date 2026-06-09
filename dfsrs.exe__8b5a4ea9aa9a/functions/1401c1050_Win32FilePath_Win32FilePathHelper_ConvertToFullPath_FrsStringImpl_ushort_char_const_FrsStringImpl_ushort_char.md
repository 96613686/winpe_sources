# Win32FilePath::Win32FilePathHelper::ConvertToFullPath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)

- ea: `0x1401c1050`
- end: `0x1401c11ce`
- name: `?ConvertToFullPath@Win32FilePathHelper@Win32FilePath@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAV4@@Z`
- size: `382`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1401c0f90`
- `0x1401c1294`

## callees

- `0x140010680`
- `0x140028eec`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401c1050`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1401c108b`
- `KERNEL32!GetFullPathNameW` at `0x1401c1132`
- `KERNEL32!GetFullPathNameW` at `0x1401c108b`
- `KERNEL32!GetFullPathNameW` at `0x1401c1132`
- `KERNEL32!GetLastError` at `0x1401c10b9`
- `KERNEL32!GetLastError` at `0x1401c1150`
- `KERNEL32!GetLastError` at `0x1401c10b9`
- `KERNEL32!GetLastError` at `0x1401c1150`
- `KERNEL32!GetCurrentThreadId` at `0x1401c10ab`
- `KERNEL32!GetCurrentThreadId` at `0x1401c1142`
- `KERNEL32!GetCurrentThreadId` at `0x1401c10ab`
- `KERNEL32!GetCurrentThreadId` at `0x1401c1142`

## string_xrefs

- `0x1401c10a0`: `base\fs\remotefs\frs\src\util\win32filepath.cpp`
- `0x1401c1173`: `base\fs\remotefs\frs\src\util\win32filepath.cpp`
- `0x1401c1099`: `Win32FilePath::Win32FilePathHelper::ConvertToFullPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Win32FilePath::Win32FilePathHelper::ConvertToFullPath(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  DWORD FullPathNameW; // eax
  unsigned __int64 v6; // rbp
  DWORD v7; // ebx
  DWORD v8; // eax
  __int64 v9; // rcx
  WCHAR *v10; // rsi
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  WCHAR *v14; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  v14 = 0;
  FrsStringImpl<unsigned short,char>::SetEmpty(a2);
  FullPathNameW = GetFullPathNameW((LPCWSTR)(*(_QWORD *)a1 + 18LL), 0, 0, 0);
  v6 = FullPathNameW;
  if ( FullPathNameW
    || (v7 = GetCurrentThreadId(),
        v8 = GetLastError(),
        (v4 = FrsStatusList::PushNewError(
                v9,
                v8,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\win32filepath.cpp",
                "Win32FilePath::Win32FilePathHelper::ConvertToFullPath",
                2237,
                v7,
                0)) == 0) )
  {
    v10 = (WCHAR *)operator_new(saturated_mul(v6, 2u));
    v14 = v10;
    if ( GetFullPathNameW((LPCWSTR)(*(_QWORD *)a1 + 18LL), v6, v10, 0)
      || (CurrentThreadId = GetCurrentThreadId(),
          LastError = GetLastError(),
          (v4 = FrsStatusList::PushNewError(
                  "base\\fs\\remotefs\\frs\\src\\util\\win32filepath.cpp",
                  LastError,
                  0,
                  1,
                  "base\\fs\\remotefs\\frs\\src\\util\\win32filepath.cpp",
                  "Win32FilePath::Win32FilePathHelper::ConvertToFullPath",
                  2257,
                  CurrentThreadId,
                  0)) == 0) )
    {
      FrsStringImpl<unsigned short,char>::Set(a2, v10);
    }
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v14);
  return v4;
}

```

## disassembly

```asm
0x1401c1050  mov     rax, rsp
0x1401c1053  mov     [rax+8], rbx
0x1401c1057  mov     [rax+10h], rbp
0x1401c105b  mov     [rax+20h], rsi
0x1401c105f  push    rdi
0x1401c1060  push    r13
0x1401c1062  push    r14
0x1401c1064  sub     rsp, 50h
0x1401c1068  mov     rdi, rdx
0x1401c106b  mov     r14, rcx
0x1401c106e  xor     ebx, ebx
0x1401c1070  and     [rax+18h], rbx
0x1401c1074  mov     rcx, rdx
0x1401c1077  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401c107c  mov     rcx, [r14]
0x1401c107f  add     rcx, 12h; lpFileName
0x1401c1083  xor     r9d, r9d; lpFilePart
0x1401c1086  xor     r8d, r8d; lpBuffer
0x1401c1089  xor     edx, edx; nBufferLength
0x1401c108b  call    cs:__imp_GetFullPathNameW
0x1401c1092  nop     dword ptr [rax+rax+00h]
0x1401c1097  mov     ebp, eax
0x1401c1099  lea     r13, aWin32filepathW_0; "Win32FilePath::Win32FilePathHelper::Con"...
0x1401c10a0  lea     rsi, aBaseFsRemotefs_68; "base\\fs\\remotefs\\frs\\src\\util\\win"...
0x1401c10a7  test    eax, eax
0x1401c10a9  jnz     short loc_1401C10FD
0x1401c10ab  call    cs:__imp_GetCurrentThreadId
0x1401c10b2  nop     dword ptr [rax+rax+00h]
0x1401c10b7  mov     ebx, eax
0x1401c10b9  call    cs:__imp_GetLastError
0x1401c10c0  nop     dword ptr [rax+rax+00h]
0x1401c10c5  and     [rsp+68h+var_28], 0
0x1401c10cb  mov     [rsp+68h+var_30], ebx
0x1401c10cf  mov     [rsp+68h+var_38], 8BDh
0x1401c10d7  mov     [rsp+68h+var_40], r13
0x1401c10dc  mov     [rsp+68h+var_48], rsi
0x1401c10e1  mov     r9d, 1
0x1401c10e7  xor     r8d, r8d
0x1401c10ea  mov     edx, eax
0x1401c10ec  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c10f1  mov     rbx, rax
0x1401c10f4  test    rax, rax
0x1401c10f7  jnz     loc_1401C11A3
0x1401c10fd  mov     eax, 2
0x1401c1102  mul     rbp
0x1401c1105  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401c110c  cmovo   rax, rcx
0x1401c1110  mov     rcx, rax; unsigned __int64
0x1401c1113  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c1118  mov     rsi, rax
0x1401c111b  mov     [rsp+68h+arg_10], rax
0x1401c1123  mov     rcx, [r14]
0x1401c1126  add     rcx, 12h; lpFileName
0x1401c112a  xor     r9d, r9d; lpFilePart
0x1401c112d  mov     r8, rax; lpBuffer
0x1401c1130  mov     edx, ebp; nBufferLength
0x1401c1132  call    cs:__imp_GetFullPathNameW
0x1401c1139  nop     dword ptr [rax+rax+00h]
0x1401c113e  test    eax, eax
0x1401c1140  jnz     short loc_1401C1197
0x1401c1142  call    cs:__imp_GetCurrentThreadId
0x1401c1149  nop     dword ptr [rax+rax+00h]
0x1401c114e  mov     ebx, eax
0x1401c1150  call    cs:__imp_GetLastError
0x1401c1157  nop     dword ptr [rax+rax+00h]
0x1401c115c  and     [rsp+68h+var_28], 0
0x1401c1162  mov     [rsp+68h+var_30], ebx
0x1401c1166  mov     [rsp+68h+var_38], 8D1h
0x1401c116e  mov     [rsp+68h+var_40], r13
0x1401c1173  lea     rcx, aBaseFsRemotefs_68; "base\\fs\\remotefs\\frs\\src\\util\\win"...
0x1401c117a  mov     [rsp+68h+var_48], rcx
0x1401c117f  mov     r9d, 1
0x1401c1185  xor     r8d, r8d
0x1401c1188  mov     edx, eax
0x1401c118a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c118f  mov     rbx, rax
0x1401c1192  test    rax, rax
0x1401c1195  jnz     short loc_1401C11A3
0x1401c1197  mov     rdx, rsi
0x1401c119a  mov     rcx, rdi
0x1401c119d  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401c11a2  nop
0x1401c11a3  lea     rcx, [rsp+68h+arg_10]
0x1401c11ab  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401c11b0  mov     rax, rbx
0x1401c11b3  lea     r11, [rsp+68h+var_18]
0x1401c11b8  mov     rbx, [r11+20h]
0x1401c11bc  mov     rbp, [r11+28h]
0x1401c11c0  mov     rsi, [r11+38h]
0x1401c11c4  mov     rsp, r11
0x1401c11c7  pop     r14
0x1401c11c9  pop     r13
0x1401c11cb  pop     rdi
0x1401c11cc  retn
```
