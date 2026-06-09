# TextFileLogger::InitFile(void)

- ea: `0x180013140`
- end: `0x1800133dd`
- name: `?InitFile@TextFileLogger@@AEAAXXZ`
- size: `669`
- prototype: `void __fastcall(TextFileLogger *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180013428`

## callees

- `0x180012b68`
- `0x180013140`
- `0x180013bb0`
- `0x180013c30`
- `0x180013cd8`
- `0x18002e0ca`
- `0x18002e110`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180013215`
- `msvcrt!wcsncpy_s` at `0x180013215`
- `KERNEL32!DeleteFileW` at `0x18001326c`
- `KERNEL32!DeleteFileW` at `0x18001329c`
- `KERNEL32!DeleteFileW` at `0x18001326c`
- `KERNEL32!DeleteFileW` at `0x18001329c`
- `KERNEL32!WriteFile` at `0x180013312`
- `KERNEL32!WriteFile` at `0x180013312`
- `KERNEL32!GetFileAttributesExW` at `0x1800131aa`
- `KERNEL32!GetFileAttributesExW` at `0x1800131aa`
- `KERNEL32!CreateFileW` at `0x1800132cd`
- `KERNEL32!CreateFileW` at `0x180013367`
- `KERNEL32!CreateFileW` at `0x1800132cd`
- `KERNEL32!CreateFileW` at `0x180013367`
- `KERNEL32!GetLastError` at `0x180013276`
- `KERNEL32!GetLastError` at `0x1800132dd`
- `KERNEL32!GetLastError` at `0x18001337b`
- `KERNEL32!GetLastError` at `0x180013276`
- `KERNEL32!GetLastError` at `0x1800132dd`
- `KERNEL32!GetLastError` at `0x18001337b`
- `IisRTL!PuDbgPrint` at `0x1800133d2`
- `IisRTL!PuDbgPrint` at `0x1800133d2`

## string_xrefs

- `0x1800133b9`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TextFileLogger::InitFile(TextFileLogger *this)
{
  unsigned int v2; // r14d
  unsigned int v3; // esi
  __int64 v4; // rbx
  TLogData *v5; // rcx
  unsigned __int16 v6; // r8
  TextFileLogger *v7; // rcx
  HANDLE v8; // rax
  void *v9; // rcx
  HANDLE FileW; // rax
  int v11; // eax
  __int16 Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-98h]
  _BYTE v16[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v17; // [rsp+90h] [rbp-70h]
  wchar_t Destination[274]; // [rsp+9Ch] [rbp-64h] BYREF
  int v19; // [rsp+2C0h] [rbp+1C0h]
  unsigned int v20[3]; // [rsp+2C4h] [rbp+1C4h] BYREF

  if ( g_wszFileCur )
  {
    v15 = 0;
    memset(FileInformation, 0, sizeof(FileInformation));
    if ( GetFileAttributesExW(&g_wszFileCur, GetFileExInfoStandard, FileInformation) )
    {
      if ( (FileInformation[0] & 1) == 0 )
      {
        v2 = v15;
        v3 = *((_DWORD *)this + 2) / *((_DWORD *)this + 3);
        if ( v15 < v3 )
        {
          FileW = CreateFileW(&g_wszFileCur, 0x40000000u, 3u, 0, 4u, 0x80000080, 0);
          *((_QWORD *)this + 3) = FileW;
          if ( FileW != (HANDLE)-1LL || GetLastError() != 5 )
          {
LABEL_8:
            if ( *((_QWORD *)this + 3) != -1
              || (v8 = CreateFileW(&g_wszFileCur, 0x40000000u, 3u, 0, 4u, 0x80000080, 0),
                  *((_QWORD *)this + 3) = v8,
                  v8 != (HANDLE)-1LL) )
            {
              if ( GetLastError() != 183 )
              {
                v9 = (void *)*((_QWORD *)this + 3);
                NumberOfBytesWritten = 0;
                Buffer[0] = -257;
                WriteFile(v9, Buffer, 2u, &NumberOfBytesWritten, 0);
              }
            }
            return;
          }
        }
        else
        {
          v4 = g_idxNumPart;
          memset_0(v16, 0, 0x250u);
          v20[0] = 0;
          v20[1] = v3;
          v17 = v2;
          wcsncpy_s(Destination, 0x104u, &g_wszFileCur, 0x103u);
          Destination[259] = 0;
          v19 = v4;
          TLogData::WstrToUl(v5, &Destination[v4], v6, v20);
          TextFileLogger::SetGlobalFile(v7, &g_wszFileCur, g_idxNumPart, v20[0] + 1);
          TLogData::SetVersion((TLogData *)v16, v20[0] + 1);
          if ( DeleteFileW(Destination) || GetLastError() == 2 )
          {
            TLogData::SetVersion((TLogData *)v16, v20[0] - *((_DWORD *)this + 3));
            DeleteFileW(Destination);
            goto LABEL_8;
          }
        }
      }
    }
  }
  v11 = TextFileLogger::DetermineFile(this);
  if ( v11 >= 0 )
    goto LABEL_8;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
      507,
      "TextFileLogger::InitFile",
      "DetermineFile failed, hr=0x%x\n",
      v11);
}

```

## disassembly

```asm
0x180013140  mov     [rsp-8+arg_8], rbx
0x180013145  mov     [rsp-8+arg_10], rsi
0x18001314a  push    rbp
0x18001314b  push    rdi
0x18001314c  push    r12
0x18001314e  push    r14
0x180013150  push    r15
0x180013152  lea     rbp, [rsp-1E0h]
0x18001315a  sub     rsp, 2E0h
0x180013161  mov     rax, cs:__security_cookie
0x180013168  xor     rax, rsp
0x18001316b  mov     [rbp+200h+var_30], rax
0x180013172  xor     r15d, r15d
0x180013175  lea     r12, ?g_wszFileCur@@3PAGA; ushort near * g_wszFileCur
0x18001317c  cmp     cs:?g_wszFileCur@@3PAGA, r15w; ushort near * g_wszFileCur
0x180013184  mov     rdi, rcx
0x180013187  jz      loc_18001338A
0x18001318d  xorps   xmm0, xmm0
0x180013190  lea     r8, [rsp+300h+FileInformation]; lpFileInformation
0x180013195  xor     eax, eax
0x180013197  xor     edx, edx; fInfoLevelId
0x180013199  mov     rcx, r12; lpFileName
0x18001319c  mov     [rsp+300h+var_298], eax
0x1800131a0  movups  [rsp+300h+FileInformation], xmm0
0x1800131a5  movups  [rsp+300h+var_2A8], xmm0
0x1800131aa  call    cs:__imp_GetFileAttributesExW
0x1800131b0  test    eax, eax
0x1800131b2  jz      loc_18001338A
0x1800131b8  test    byte ptr [rsp+300h+FileInformation], 1
0x1800131bd  jnz     loc_18001338A
0x1800131c3  mov     eax, [rdi+8]
0x1800131c6  xor     edx, edx
0x1800131c8  div     dword ptr [rdi+0Ch]
0x1800131cb  mov     r14d, [rsp+300h+var_298]
0x1800131d0  mov     esi, eax
0x1800131d2  cmp     r14d, eax
0x1800131d5  jb      loc_180013343
0x1800131db  mov     ebx, cs:?g_idxNumPart@@3KA; ulong g_idxNumPart
0x1800131e1  lea     rcx, [rsp+300h+var_290]; void *
0x1800131e6  xor     edx, edx; Val
0x1800131e8  mov     r8d, 250h; Size
0x1800131ee  call    memset_0
0x1800131f3  mov     r9d, 103h; MaxCount
0x1800131f9  mov     [rbp+200h+var_3C], r15d
0x180013200  mov     r8, r12; Source
0x180013203  mov     [rbp+200h+var_38], esi
0x180013209  lea     rcx, [rbp+200h+Destination]; Destination
0x18001320d  mov     [rbp+200h+var_270], r14d
0x180013211  lea     edx, [r9+1]; SizeInWords
0x180013215  call    cs:__imp_wcsncpy_s
0x18001321b  lea     rdx, [rbp+200h+Destination]
0x18001321f  mov     [rbp+200h+var_5E], r15w
0x180013227  lea     rdx, [rdx+rbx*2]; unsigned __int16 *
0x18001322b  mov     [rbp+200h+var_40], ebx
0x180013231  lea     r9, [rbp+200h+var_3C]; unsigned int *
0x180013238  call    ?WstrToUl@TLogData@@AEAA_NPEBGGPEAK@Z; TLogData::WstrToUl(ushort const *,ushort,ulong *)
0x18001323d  mov     r9d, [rbp+200h+var_3C]
0x180013244  mov     rdx, r12; unsigned __int16 *
0x180013247  mov     r8d, cs:?g_idxNumPart@@3KA; unsigned int
0x18001324e  inc     r9d; unsigned int
0x180013251  call    ?SetGlobalFile@TextFileLogger@@AEAAXPEBGKK@Z; TextFileLogger::SetGlobalFile(ushort const *,ulong,ulong)
0x180013256  mov     edx, [rbp+200h+var_3C]
0x18001325c  lea     rcx, [rsp+300h+var_290]; this
0x180013261  inc     edx; unsigned int
0x180013263  call    ?SetVersion@TLogData@@QEAAXK@Z; TLogData::SetVersion(ulong)
0x180013268  lea     rcx, [rbp+200h+Destination]; lpFileName
0x18001326c  call    cs:__imp_DeleteFileW
0x180013272  test    eax, eax
0x180013274  jnz     short loc_180013285
0x180013276  call    cs:__imp_GetLastError
0x18001327c  cmp     eax, 2
0x18001327f  jnz     loc_18001338A
0x180013285  mov     edx, [rbp+200h+var_3C]
0x18001328b  lea     rcx, [rsp+300h+var_290]; this
0x180013290  sub     edx, [rdi+0Ch]; unsigned int
0x180013293  call    ?SetVersion@TLogData@@QEAAXK@Z; TLogData::SetVersion(ulong)
0x180013298  lea     rcx, [rbp+200h+Destination]; lpFileName
0x18001329c  call    cs:__imp_DeleteFileW
0x1800132a2  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800132a7  jnz     short loc_1800132DD
0x1800132a9  xor     r9d, r9d; lpSecurityAttributes
0x1800132ac  mov     [rsp+300h+hTemplateFile], r15; hTemplateFile
0x1800132b1  mov     [rsp+300h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x1800132b9  mov     edx, 40000000h; dwDesiredAccess
0x1800132be  mov     rcx, r12; lpFileName
0x1800132c1  mov     [rsp+300h+dwCreationDisposition], 4; dwCreationDisposition
0x1800132c9  lea     r8d, [r9+3]; dwShareMode
0x1800132cd  call    cs:__imp_CreateFileW
0x1800132d3  mov     [rdi+18h], rax
0x1800132d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800132db  jz      short loc_180013318
0x1800132dd  call    cs:__imp_GetLastError
0x1800132e3  cmp     eax, 0B7h
0x1800132e8  jz      short loc_180013318
0x1800132ea  mov     rcx, [rdi+18h]; hFile
0x1800132ee  lea     r9, [rsp+300h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800132f3  mov     eax, 0FEFFh
0x1800132f8  mov     [rsp+300h+NumberOfBytesWritten], r15d
0x1800132fd  mov     r8d, 2; nNumberOfBytesToWrite
0x180013303  mov     [rsp+300h+Buffer], ax
0x180013308  lea     rdx, [rsp+300h+Buffer]; lpBuffer
0x18001330d  mov     qword ptr [rsp+300h+dwCreationDisposition], r15; lpOverlapped
0x180013312  call    cs:__imp_WriteFile
0x180013318  mov     rcx, [rbp+200h+var_30]
0x18001331f  xor     rcx, rsp; StackCookie
0x180013322  call    __security_check_cookie
0x180013327  lea     r11, [rsp+300h+var_20]
0x18001332f  mov     rbx, [r11+38h]
0x180013333  mov     rsi, [r11+40h]
0x180013337  mov     rsp, r11
0x18001333a  pop     r15
0x18001333c  pop     r14
0x18001333e  pop     r12
0x180013340  pop     rdi
0x180013341  pop     rbp
0x180013342  retn
0x180013343  xor     r9d, r9d; lpSecurityAttributes
0x180013346  mov     [rsp+300h+hTemplateFile], r15; hTemplateFile
0x18001334b  mov     [rsp+300h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x180013353  mov     edx, 40000000h; dwDesiredAccess
0x180013358  mov     rcx, r12; lpFileName
0x18001335b  mov     [rsp+300h+dwCreationDisposition], 4; dwCreationDisposition
0x180013363  lea     r8d, [r9+3]; dwShareMode
0x180013367  call    cs:__imp_CreateFileW
0x18001336d  mov     [rdi+18h], rax
0x180013371  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013375  jnz     loc_1800132A2
0x18001337b  call    cs:__imp_GetLastError
0x180013381  cmp     eax, 5
0x180013384  jnz     loc_1800132A2
0x18001338a  mov     rcx, rdi; this
0x18001338d  call    ?DetermineFile@TextFileLogger@@AEAAJXZ; TextFileLogger::DetermineFile(void)
0x180013392  test    eax, eax
0x180013394  jns     loc_1800132A2
0x18001339a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800133a1  jz      loc_180013318
0x1800133a7  mov     rcx, cs:g_pDebug
0x1800133ae  lea     r9, aTextfilelogger_4; "TextFileLogger::InitFile"
0x1800133b5  mov     [rsp+300h+dwFlagsAndAttributes], eax
0x1800133b9  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x1800133c0  lea     rax, aDeterminefileF; "DetermineFile failed, hr=0x%x\n"
0x1800133c7  mov     r8d, 1FBh
0x1800133cd  mov     qword ptr [rsp+300h+dwCreationDisposition], rax
0x1800133d2  call    cs:__imp_PuDbgPrint
0x1800133d8  jmp     loc_180013318
```
