# ResetFileAttributesIfNeeded(char *,int)

- ea: `0x1800231ec`
- end: `0x1800232c6`
- name: `?ResetFileAttributesIfNeeded@@YAXPEADH@Z`
- size: `218`
- prototype: `void __fastcall(LPCSTR lpFileName, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e104`
- `0x1800120b4`
- `0x18001be0c`
- `0x18001be78`
- `0x180024bc4`
- `0x180025990`

## callees

- `0x18002056c`
- `0x1800231ec`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x180023232`
- `KERNEL32!SetFileAttributesA` at `0x180023232`
- `KERNEL32!SetFileAttributesW` at `0x18002322a`
- `KERNEL32!SetFileAttributesW` at `0x18002322a`
- `KERNEL32!GetFileAttributesA` at `0x180023207`
- `KERNEL32!GetFileAttributesA` at `0x180023207`
- `KERNEL32!GetFileAttributesW` at `0x1800231ff`
- `KERNEL32!GetFileAttributesW` at `0x1800231ff`
- `KERNEL32!GetLastError` at `0x18002326f`
- `KERNEL32!GetLastError` at `0x18002326f`
- `IisRTL!PuDbgPrintW` at `0x1800232b5`
- `IisRTL!PuDbgPrintW` at `0x1800232b5`

## string_xrefs

- `0x1800232a3`: `[ResetFileAttributesIfNeeded] Unable to reset metabase file attributes. SetFileAttributes failed with hr=0x%x`
- `0x180023291`: `ResetFileAttributesIfNeeded`

## pseudocode

```c
void __fastcall ResetFileAttributesIfNeeded(const WCHAR *lpFileName, int a2)
{
  DWORD FileAttributesW; // eax
  BOOL v5; // eax
  unsigned int v6; // r9d
  signed int LastError; // eax
  unsigned __int16 *v8; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v9; // [rsp+40h] [rbp-18h]
  unsigned __int16 *v10; // [rsp+48h] [rbp-10h]

  if ( a2 )
    FileAttributesW = GetFileAttributesW(lpFileName);
  else
    FileAttributesW = GetFileAttributesA((LPCSTR)lpFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
  {
    if ( a2 )
      v5 = SetFileAttributesW(lpFileName, 0x80u);
    else
      v5 = SetFileAttributesA((LPCSTR)lpFileName, 0x80u);
    if ( v5 )
    {
      LogEvent(g_pEventLog, 0x8002C83A, 2u, v6, 0, 0, 0, v8, v9, v10);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          13614,
          "ResetFileAttributesIfNeeded",
          L"[ResetFileAttributesIfNeeded] Unable to reset metabase file attributes. SetFileAttributes failed with hr=0x%x",
          LastError);
    }
  }
}

```

## disassembly

```asm
0x1800231ec  mov     [rsp+arg_0], rbx
0x1800231f1  push    rdi
0x1800231f2  sub     rsp, 50h
0x1800231f6  mov     edi, edx
0x1800231f8  mov     rbx, rcx
0x1800231fb  test    edx, edx
0x1800231fd  jz      short loc_180023207
0x1800231ff  call    cs:__imp_GetFileAttributesW
0x180023205  jmp     short loc_18002320D
0x180023207  call    cs:__imp_GetFileAttributesA
0x18002320d  cmp     eax, 0FFFFFFFFh
0x180023210  jz      loc_1800232BB
0x180023216  test    al, 1
0x180023218  jz      loc_1800232BB
0x18002321e  mov     edx, 80h; dwFileAttributes
0x180023223  mov     rcx, rbx; lpFileName
0x180023226  test    edi, edi
0x180023228  jz      short loc_180023232
0x18002322a  call    cs:__imp_SetFileAttributesW
0x180023230  jmp     short loc_180023238
0x180023232  call    cs:__imp_SetFileAttributesA
0x180023238  test    eax, eax
0x18002323a  jz      short loc_18002326F
0x18002323c  mov     rcx, cs:?g_pEventLog@@3PEAUICatalogErrorLogger2@@EA; struct ICatalogErrorLogger2 *
0x180023243  mov     edx, 8002C83Ah; unsigned int
0x180023248  mov     [rsp+58h+var_28], 0; unsigned __int16 *
0x180023251  mov     r8d, 2; unsigned int
0x180023257  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x180023260  mov     dword ptr [rsp+58h+var_38], 0; char
0x180023268  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18002326d  jmp     short loc_1800232BB
0x18002326f  call    cs:__imp_GetLastError
0x180023275  test    eax, eax
0x180023277  jle     short loc_180023281
0x180023279  movzx   eax, ax
0x18002327c  or      eax, 80070000h
0x180023281  test    byte ptr cs:g_dwDebugFlags, 3
0x180023288  jz      short loc_1800232BB
0x18002328a  mov     rcx, cs:g_pDebug
0x180023291  lea     r9, aResetfileattri_0; "ResetFileAttributesIfNeeded"
0x180023298  mov     dword ptr [rsp+58h+var_30], eax
0x18002329c  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800232a3  lea     rax, aResetfileattri; "[ResetFileAttributesIfNeeded] Unable to"...
0x1800232aa  mov     r8d, 352Eh
0x1800232b0  mov     qword ptr [rsp+58h+var_38], rax
0x1800232b5  call    cs:__imp_PuDbgPrintW
0x1800232bb  mov     rbx, [rsp+58h+arg_0]
0x1800232c0  add     rsp, 50h
0x1800232c4  pop     rdi
0x1800232c5  retn
```
