# CreateHistoryFiles(ushort *,ushort *,ulong,ulong)

- ea: `0x18001d084`
- end: `0x18001d1e0`
- name: `?CreateHistoryFiles@@YAJPEAG0KK@Z`
- size: `348`
- prototype: `signed int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eec8`
- `0x180024bc4`

## callees

- `0x18001b5dc`
- `0x18001cf00`
- `0x18001d084`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18001d107`
- `KERNEL32!CreateDirectoryW` at `0x18001d107`
- `KERNEL32!GetFileAttributesW` at `0x18001d0af`
- `KERNEL32!GetFileAttributesW` at `0x18001d0af`
- `KERNEL32!GetLastError` at `0x18001d0be`
- `KERNEL32!GetLastError` at `0x18001d111`
- `KERNEL32!GetLastError` at `0x18001d0be`
- `KERNEL32!GetLastError` at `0x18001d111`
- `IisRTL!PuDbgPrintW` at `0x18001d15a`
- `IisRTL!PuDbgPrintW` at `0x18001d15a`

## string_xrefs

- `0x18001d136`: `[CreateHistoryFile] Unable to create history directory. CreateDirectoryW failed with hr = 0x%x. \n`
- `0x18001d141`: `CreateHistoryFiles`

## pseudocode

```c
signed int __fastcall CreateHistoryFiles(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3, unsigned int a4)
{
  unsigned __int16 *v8; // rdx
  unsigned int v9; // r8d
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rdx
  unsigned int v14; // r8d
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-48h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( GetFileAttributesW(g_wszHistoryFileDir) != -1 )
  {
LABEL_11:
    if ( (int)CreateHistoryFile(
                a1,
                v8,
                v9,
                g_wszRealFileNameWithoutPathWithoutExtension,
                g_cchRealFileNameWithoutPathWithoutExtension,
                g_wszRealFileNameExtension,
                g_cchRealFileNameExtension,
                a3) >= 0 )
      CreateHistoryFile(
        a2,
        v13,
        v14,
        g_wszSchemaFileNameWithoutPathWithoutExtension,
        g_cchSchemaFileNameWithoutPathWithoutExtension,
        g_wszSchemaFileNameExtension,
        g_cchSchemaFileNameExtension,
        a3);
    return CleanupObsoleteHistoryFiles(a4, a3);
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( (unsigned int)(result + 2147024894) <= 1 )
  {
    SecurityAttributes.lpSecurityDescriptor = qword_180048AE8;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    if ( !CreateDirectoryW(g_wszHistoryFileDir, &SecurityAttributes) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          10156,
          "CreateHistoryFiles",
          L"[CreateHistoryFile] Unable to create history directory. CreateDirectoryW failed with hr = 0x%x. \n",
          v12);
      return v12;
    }
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x18001d084  push    rbx
0x18001d086  push    rbp
0x18001d087  push    rsi
0x18001d088  push    rdi
0x18001d089  sub     rsp, 68h
0x18001d08d  mov     rbp, rcx
0x18001d090  xorps   xmm0, xmm0
0x18001d093  mov     rcx, cs:?g_wszHistoryFileDir@@3PEAGEA; lpFileName
0x18001d09a  xor     eax, eax
0x18001d09c  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x18001d0a1  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], rax
0x18001d0a6  mov     edi, r9d
0x18001d0a9  mov     ebx, r8d
0x18001d0ac  mov     rsi, rdx
0x18001d0af  call    cs:__imp_GetFileAttributesW
0x18001d0b5  cmp     eax, 0FFFFFFFFh
0x18001d0b8  jnz     loc_18001D164
0x18001d0be  call    cs:__imp_GetLastError
0x18001d0c4  test    eax, eax
0x18001d0c6  jle     short loc_18001D0D0
0x18001d0c8  movzx   eax, ax
0x18001d0cb  or      eax, 80070000h
0x18001d0d0  lea     ecx, [rax+7FF8FFFEh]
0x18001d0d6  cmp     ecx, 1
0x18001d0d9  ja      loc_18001D1D7
0x18001d0df  mov     rcx, cs:?g_wszHistoryFileDir@@3PEAGEA; lpPathName
0x18001d0e6  lea     rax, qword_180048AE8
0x18001d0ed  lea     rdx, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x18001d0f2  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001d0f7  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x18001d0ff  mov     [rsp+88h+SecurityAttributes.bInheritHandle], 0
0x18001d107  call    cs:__imp_CreateDirectoryW
0x18001d10d  test    eax, eax
0x18001d10f  jnz     short loc_18001D164
0x18001d111  call    cs:__imp_GetLastError
0x18001d117  mov     ebx, eax
0x18001d119  test    eax, eax
0x18001d11b  jle     short loc_18001D126
0x18001d11d  movzx   ebx, ax
0x18001d120  or      ebx, 80070000h
0x18001d126  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d12d  jz      short loc_18001D160
0x18001d12f  mov     rcx, cs:g_pDebug
0x18001d136  lea     rax, aCreatehistoryf_0; "[CreateHistoryFile] Unable to create hi"...
0x18001d13d  mov     dword ptr [rsp+88h+var_60], ebx
0x18001d141  lea     r9, aCreatehistoryf; "CreateHistoryFiles"
0x18001d148  mov     r8d, 27ACh
0x18001d14e  mov     qword ptr [rsp+88h+var_68], rax
0x18001d153  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d15a  call    cs:__imp_PuDbgPrintW
0x18001d160  mov     eax, ebx
0x18001d162  jmp     short loc_18001D1D7
0x18001d164  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x18001d16a  mov     rcx, rbp; unsigned __int16 *
0x18001d16d  mov     r9, cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x18001d174  mov     [rsp+88h+var_50], ebx; unsigned int
0x18001d178  mov     [rsp+88h+var_58], eax; unsigned int
0x18001d17c  mov     rax, cs:?g_wszRealFileNameExtension@@3PEAGEA; ushort * g_wszRealFileNameExtension
0x18001d183  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18001d188  mov     eax, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x18001d18e  mov     [rsp+88h+var_68], eax; unsigned int
0x18001d192  call    ?CreateHistoryFile@@YAJPEAG0K0K0KK@Z; CreateHistoryFile(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong)
0x18001d197  test    eax, eax
0x18001d199  js      short loc_18001D1CE
0x18001d19b  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x18001d1a1  mov     rcx, rsi; unsigned __int16 *
0x18001d1a4  mov     r9, cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA; unsigned __int16 *
0x18001d1ab  mov     [rsp+88h+var_50], ebx; unsigned int
0x18001d1af  mov     [rsp+88h+var_58], eax; unsigned int
0x18001d1b3  mov     rax, cs:?g_wszSchemaFileNameExtension@@3PEAGEA; ushort * g_wszSchemaFileNameExtension
0x18001d1ba  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18001d1bf  mov     eax, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x18001d1c5  mov     [rsp+88h+var_68], eax; unsigned int
0x18001d1c9  call    ?CreateHistoryFile@@YAJPEAG0K0K0KK@Z; CreateHistoryFile(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong)
0x18001d1ce  mov     edx, ebx; unsigned int
0x18001d1d0  mov     ecx, edi; unsigned int
0x18001d1d2  call    ?CleanupObsoleteHistoryFiles@@YAJKK@Z; CleanupObsoleteHistoryFiles(ulong,ulong)
0x18001d1d7  add     rsp, 68h
0x18001d1db  pop     rdi
0x18001d1dc  pop     rsi
0x18001d1dd  pop     rbp
0x18001d1de  pop     rbx
0x18001d1df  retn
```
