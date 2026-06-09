# DeleteHistoryFile(ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)

- ea: `0x18001d1e8`
- end: `0x18001d30c`
- name: `?DeleteHistoryFile@@YAJPEAGK0K0KKK@Z`
- size: `292`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b5dc`

## callees

- `0x180008a08`
- `0x18001c21c`
- `0x18001d1e8`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18001d299`
- `KERNEL32!DeleteFileW` at `0x18001d299`
- `KERNEL32!GetLastError` at `0x18001d2a3`
- `KERNEL32!GetLastError` at `0x18001d2a3`
- `IisRTL!PuDbgPrintW` at `0x18001d289`
- `IisRTL!PuDbgPrintW` at `0x18001d2f1`
- `IisRTL!PuDbgPrintW` at `0x18001d289`
- `IisRTL!PuDbgPrintW` at `0x18001d2f1`

## string_xrefs

- `0x18001d277`: `[DeleteHistoryFile] Unable to cleanup history files. ConstructHistoryFileName failed with hr = 0x%x.\n`
- `0x18001d265`: `DeleteHistoryFile`
- `0x18001d2d3`: `DeleteHistoryFile`
- `0x18001d2c8`: `[DeleteHistoryFile] Unable to cleanup history file: %s. DeleteFileW failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall DeleteHistoryFile(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  int v8; // eax
  unsigned int v9; // ebx
  WCHAR *v10; // rdi
  signed int LastError; // eax
  __int64 v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp+8h] BYREF

  lpFileName = 0;
  v8 = ConstructHistoryFileName(
         (unsigned __int16 **)&lpFileName,
         (unsigned __int16 *)g_wszHistoryFileDir,
         g_cchHistoryFileDir,
         a3,
         a4,
         a5,
         a6,
         a7,
         a8);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = (WCHAR *)lpFileName;
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v14) = v9;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          10957,
          "DeleteHistoryFile",
          L"[DeleteHistoryFile] Unable to cleanup history file: %s. DeleteFileW failed with hr = 0x%x.\n",
          v10,
          v14);
      }
    }
    operator delete(v10);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v13) = v8;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      10947,
      "DeleteHistoryFile",
      L"[DeleteHistoryFile] Unable to cleanup history files. ConstructHistoryFileName failed with hr = 0x%x.\n",
      v13);
  }
  return v9;
}

```

## disassembly

```asm
0x18001d1e8  mov     r11, rsp
0x18001d1eb  mov     [r11+10h], rbx
0x18001d1ef  mov     [r11+8], rcx
0x18001d1f3  push    rdi
0x18001d1f4  sub     rsp, 50h
0x18001d1f8  mov     eax, [rsp+58h+arg_38]
0x18001d1ff  lea     rcx, [r11+8]; unsigned __int16 **
0x18001d203  mov     rdx, cs:?g_wszHistoryFileDir@@3PEAGEA; unsigned __int16 *
0x18001d20a  mov     [rsp+58h+var_18], eax; unsigned int
0x18001d20e  mov     eax, [rsp+58h+arg_30]
0x18001d215  mov     [rsp+58h+var_20], eax; unsigned int
0x18001d219  mov     eax, [rsp+58h+arg_28]
0x18001d220  mov     dword ptr [rsp+58h+var_28], eax; unsigned int
0x18001d224  mov     rax, [rsp+58h+arg_20]
0x18001d22c  mov     [r11-30h], rax
0x18001d230  mov     [r11-38h], r9d
0x18001d234  mov     r9, r8; unsigned __int16 *
0x18001d237  mov     r8d, cs:?g_cchHistoryFileDir@@3KA; unsigned int
0x18001d23e  mov     qword ptr [r11+8], 0
0x18001d246  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x18001d24b  mov     ebx, eax
0x18001d24d  test    eax, eax
0x18001d24f  jns     short loc_18001D291
0x18001d251  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d258  jz      loc_18001D2FF
0x18001d25e  mov     rcx, cs:g_pDebug
0x18001d265  lea     r9, aDeletehistoryf; "DeleteHistoryFile"
0x18001d26c  mov     dword ptr [rsp+58h+var_30], eax
0x18001d270  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d277  lea     rax, aDeletehistoryf_1; "[DeleteHistoryFile] Unable to cleanup h"...
0x18001d27e  mov     r8d, 2AC3h
0x18001d284  mov     [rsp+58h+var_38], rax
0x18001d289  call    cs:__imp_PuDbgPrintW
0x18001d28f  jmp     short loc_18001D2FF
0x18001d291  mov     rdi, [rsp+58h+lpFileName]
0x18001d296  mov     rcx, rdi; lpFileName
0x18001d299  call    cs:__imp_DeleteFileW
0x18001d29f  test    eax, eax
0x18001d2a1  jnz     short loc_18001D2F7
0x18001d2a3  call    cs:__imp_GetLastError
0x18001d2a9  mov     ebx, eax
0x18001d2ab  test    eax, eax
0x18001d2ad  jle     short loc_18001D2B8
0x18001d2af  movzx   ebx, ax
0x18001d2b2  or      ebx, 80070000h
0x18001d2b8  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d2bf  jz      short loc_18001D2F7
0x18001d2c1  mov     rcx, cs:g_pDebug
0x18001d2c8  lea     rax, aDeletehistoryf_0; "[DeleteHistoryFile] Unable to cleanup h"...
0x18001d2cf  mov     dword ptr [rsp+58h+var_28], ebx
0x18001d2d3  lea     r9, aDeletehistoryf; "DeleteHistoryFile"
0x18001d2da  mov     [rsp+58h+var_30], rdi
0x18001d2df  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d2e6  mov     r8d, 2ACDh
0x18001d2ec  mov     [rsp+58h+var_38], rax
0x18001d2f1  call    cs:__imp_PuDbgPrintW
0x18001d2f7  mov     rcx, rdi; Block
0x18001d2fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d2ff  mov     eax, ebx
0x18001d301  mov     rbx, [rsp+58h+arg_8]
0x18001d306  add     rsp, 50h
0x18001d30a  pop     rdi
0x18001d30b  retn
```
