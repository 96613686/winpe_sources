# CreateHistoryFile(ushort *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong)

- ea: `0x18001cf00`
- end: `0x18001d07d`
- name: `?CreateHistoryFile@@YAJPEAG0K0K0KK@Z`
- size: `381`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned int, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001d084`

## callees

- `0x180008a08`
- `0x18001c21c`
- `0x18001c508`
- `0x18001cf00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001cfff`
- `msvcrt!_wcsicmp` at `0x18001cfff`
- `IisRTL!PuDbgPrintW` at `0x18001cfae`
- `IisRTL!PuDbgPrintW` at `0x18001cff3`
- `IisRTL!PuDbgPrintW` at `0x18001d058`
- `IisRTL!PuDbgPrintW` at `0x18001cfae`
- `IisRTL!PuDbgPrintW` at `0x18001cff3`
- `IisRTL!PuDbgPrintW` at `0x18001d058`

## string_xrefs

- `0x18001cf9c`: `[CreateHistoryFile] Unable to construct history file name. ConstructHistoryFileName failed with hr = 0x%x\n.`
- `0x18001cf8a`: `CreateHistoryFile`
- `0x18001cfd5`: `CreateHistoryFile`
- `0x18001d02a`: `CreateHistoryFile`
- `0x18001cfc9`: `[CreateHistoryFile] Copying history file from %s to %s.\n`
- `0x18001d041`: `[CreateHistoryFile] Unable to create history file. CopyFileW from %s to %s failed with hr = 0x%x\n.`

## pseudocode

```c
__int64 __fastcall CreateHistoryFile(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8)
{
  int v9; // eax
  unsigned __int16 *v10; // rbx
  unsigned int v11; // edi
  int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-30h]
  __int64 v15; // [rsp+38h] [rbp-20h]
  wchar_t *String2; // [rsp+68h] [rbp+10h] BYREF

  String2 = 0;
  v9 = ConstructHistoryFileName(
         &String2,
         (unsigned __int16 *)g_wszHistoryFileDir,
         g_cchHistoryFileDir,
         a4,
         a5,
         a6,
         a7,
         a8,
         0);
  v10 = String2;
  v11 = v9;
  if ( v9 >= 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        10264,
        "CreateHistoryFile",
        L"[CreateHistoryFile] Copying history file from %s to %s.\n",
        a1,
        String2);
    if ( _wcsicmp(a1, v10) )
    {
      v12 = CopyFileWithSecurityDescriptor(a1, v10);
      v11 = v12;
      if ( v12 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v15) = v12;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          10284,
          "CreateHistoryFile",
          L"[CreateHistoryFile] Unable to create history file. CopyFileW from %s to %s failed with hr = 0x%x\n.",
          a1,
          v10,
          v15);
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v14) = v9;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      10253,
      "CreateHistoryFile",
      L"[CreateHistoryFile] Unable to construct history file name. ConstructHistoryFileName failed with hr = 0x%x\n.",
      v14);
  }
  if ( v10 )
    operator delete(v10);
  return v11;
}

```

## disassembly

```asm
0x18001cf00  mov     r11, rsp
0x18001cf03  mov     [r11+8], rbx
0x18001cf07  mov     [r11+18h], rsi
0x18001cf0b  mov     [r11+10h], rdx
0x18001cf0f  push    rdi
0x18001cf10  sub     rsp, 50h
0x18001cf14  mov     eax, [rsp+58h+arg_38]
0x18001cf1b  mov     rsi, rcx
0x18001cf1e  mov     r8d, cs:?g_cchHistoryFileDir@@3KA; unsigned int
0x18001cf25  lea     rcx, [r11+10h]; unsigned __int16 **
0x18001cf29  mov     rdx, cs:?g_wszHistoryFileDir@@3PEAGEA; unsigned __int16 *
0x18001cf30  mov     [rsp+58h+var_18], 0; unsigned int
0x18001cf38  mov     dword ptr [rsp+58h+var_20], eax; unsigned int
0x18001cf3c  mov     eax, [rsp+58h+arg_30]
0x18001cf43  mov     [rsp+58h+var_28], eax; unsigned int
0x18001cf47  mov     rax, [rsp+58h+arg_28]
0x18001cf4f  mov     [r11-30h], rax
0x18001cf53  mov     eax, [rsp+58h+arg_20]
0x18001cf5a  mov     [rsp+58h+var_38], eax; unsigned int
0x18001cf5e  mov     qword ptr [r11+10h], 0
0x18001cf66  call    ?ConstructHistoryFileName@@YAJPEAPEAGPEAGK1K1KKK@Z; ConstructHistoryFileName(ushort * *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ulong,ulong)
0x18001cf6b  mov     rbx, [rsp+58h+String2]
0x18001cf70  mov     edi, eax
0x18001cf72  test    eax, eax
0x18001cf74  jns     short loc_18001CFB9
0x18001cf76  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cf7d  jz      loc_18001D05E
0x18001cf83  mov     rcx, cs:g_pDebug
0x18001cf8a  lea     r9, aCreatehistoryf_4; "CreateHistoryFile"
0x18001cf91  mov     dword ptr [rsp+58h+var_30], eax
0x18001cf95  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001cf9c  lea     rax, aCreatehistoryf_3; "[CreateHistoryFile] Unable to construct"...
0x18001cfa3  mov     r8d, 280Dh
0x18001cfa9  mov     qword ptr [rsp+58h+var_38], rax
0x18001cfae  call    cs:__imp_PuDbgPrintW
0x18001cfb4  jmp     loc_18001D05E
0x18001cfb9  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cfc0  jz      short loc_18001CFF9
0x18001cfc2  mov     rcx, cs:g_pDebug
0x18001cfc9  lea     rax, aCreatehistoryf_2; "[CreateHistoryFile] Copying history fil"...
0x18001cfd0  mov     qword ptr [rsp+58h+var_28], rbx
0x18001cfd5  lea     r9, aCreatehistoryf_4; "CreateHistoryFile"
0x18001cfdc  mov     [rsp+58h+var_30], rsi
0x18001cfe1  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001cfe8  mov     r8d, 2818h
0x18001cfee  mov     qword ptr [rsp+58h+var_38], rax
0x18001cff3  call    cs:__imp_PuDbgPrintW
0x18001cff9  mov     rdx, rbx; String2
0x18001cffc  mov     rcx, rsi; String1
0x18001cfff  call    cs:__imp__wcsicmp
0x18001d005  test    eax, eax
0x18001d007  jz      short loc_18001D05E
0x18001d009  mov     rdx, rbx; unsigned __int16 *
0x18001d00c  mov     rcx, rsi; unsigned __int16 *
0x18001d00f  call    ?CopyFileWithSecurityDescriptor@@YAJPEAG0@Z; CopyFileWithSecurityDescriptor(ushort *,ushort *)
0x18001d014  mov     edi, eax
0x18001d016  test    eax, eax
0x18001d018  jns     short loc_18001D05E
0x18001d01a  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d021  jz      short loc_18001D05E
0x18001d023  mov     rcx, cs:g_pDebug
0x18001d02a  lea     r9, aCreatehistoryf_4; "CreateHistoryFile"
0x18001d031  mov     dword ptr [rsp+58h+var_20], eax
0x18001d035  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d03c  mov     qword ptr [rsp+58h+var_28], rbx
0x18001d041  lea     rax, aCreatehistoryf_1; "[CreateHistoryFile] Unable to create hi"...
0x18001d048  mov     [rsp+58h+var_30], rsi
0x18001d04d  mov     r8d, 282Ch
0x18001d053  mov     qword ptr [rsp+58h+var_38], rax
0x18001d058  call    cs:__imp_PuDbgPrintW
0x18001d05e  test    rbx, rbx
0x18001d061  jz      short loc_18001D06B
0x18001d063  mov     rcx, rbx; Block
0x18001d066  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d06b  mov     rbx, [rsp+58h+arg_0]
0x18001d070  mov     eax, edi
0x18001d072  mov     rsi, [rsp+58h+arg_10]
0x18001d077  add     rsp, 50h
0x18001d07b  pop     rdi
0x18001d07c  retn
```
