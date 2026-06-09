# TErrorLogWriter::WriteDetailedErrors(tDETAILEDERRORSRow &,ulong *,ulong)

- ea: `0x1800125d0`
- end: `0x18001272d`
- name: `?WriteDetailedErrors@TErrorLogWriter@@QEAAJAEAUtDETAILEDERRORSRow@@PEAKK@Z`
- size: `349`
- prototype: `__int64 __fastcall(TErrorLogWriter *this, struct tDETAILEDERRORSRow *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180012734`

## callees

- `0x1800125d0`
- `0x180012940`
- `0x180012988`
- `0x180013428`
- `0x18002e110`

## import_xrefs

- `ADVAPI32!ReportEventW` at `0x18001269d`
- `ADVAPI32!ReportEventW` at `0x18001269d`
- `ADVAPI32!RegisterEventSourceW` at `0x180012604`
- `ADVAPI32!RegisterEventSourceW` at `0x180012604`

## pseudocode

```c
__int64 __fastcall TErrorLogWriter::WriteDetailedErrors(
        TErrorLogWriter *this,
        struct tDETAILEDERRORSRow *a2,
        unsigned int *a3)
{
  HANDLE v3; // rax
  DWORD *v5; // r9
  WORD *v6; // r8
  WORD *v7; // rdx
  HINSTANCE v8; // r8
  TextFileLogger *v9; // rax
  unsigned __int16 lpUserSid; // [rsp+20h] [rbp-A8h]
  _BYTE v12[56]; // [rsp+50h] [rbp-78h] BYREF
  LPCWSTR Strings[5]; // [rsp+88h] [rbp-40h] BYREF

  v3 = g_ErrorLogWriter;
  if ( !g_ErrorLogWriter )
  {
    v3 = RegisterEventSourceW(0, *((LPCWSTR *)a2 + 7));
    g_ErrorLogWriter = v3;
  }
  v5 = (DWORD *)*((_QWORD *)a2 + 13);
  v6 = (WORD *)*((_QWORD *)a2 + 9);
  v7 = (WORD *)*((_QWORD *)a2 + 8);
  Strings[0] = *((LPCWSTR *)a2 + 14);
  Strings[1] = *((LPCWSTR *)a2 + 15);
  Strings[2] = *((LPCWSTR *)a2 + 16);
  Strings[3] = *((LPCWSTR *)a2 + 17);
  Strings[4] = *((LPCWSTR *)a2 + 18);
  ReportEventW(v3, *v7, *v6, *v5, 0, 5u, 0, Strings, 0);
  v9 = TextFileLogger::TextFileLogger((TextFileLogger *)v12, *((const unsigned __int16 **)a2 + 7), v8);
  TextFileLogger::Report(
    v9,
    **((_WORD **)a2 + 8),
    **((_WORD **)a2 + 9),
    **((_DWORD **)a2 + 13),
    lpUserSid,
    0,
    (va_list *)Strings,
    0,
    0,
    0);
  TextFileLogger::~TextFileLogger((TextFileLogger *)v12);
  return 0;
}

```

## disassembly

```asm
0x1800125d0  mov     [rsp+arg_0], rbx
0x1800125d5  push    rdi
0x1800125d6  sub     rsp, 0C0h
0x1800125dd  mov     rax, cs:__security_cookie
0x1800125e4  xor     rax, rsp
0x1800125e7  mov     [rsp+0C8h+var_18], rax
0x1800125ef  mov     rax, cs:?g_ErrorLogWriter@@3VTErrorLogWriter@@A; TErrorLogWriter g_ErrorLogWriter
0x1800125f6  mov     rdi, rdx
0x1800125f9  test    rax, rax
0x1800125fc  jnz     short loc_180012611
0x1800125fe  mov     rdx, [rdx+38h]; lpSourceName
0x180012602  xor     ecx, ecx; lpUNCServerName
0x180012604  call    cs:__imp_RegisterEventSourceW
0x18001260a  mov     cs:?g_ErrorLogWriter@@3VTErrorLogWriter@@A, rax; TErrorLogWriter g_ErrorLogWriter
0x180012611  mov     rcx, [rdi+70h]
0x180012615  mov     r9, [rdi+68h]
0x180012619  mov     r8, [rdi+48h]
0x18001261d  mov     rdx, [rdi+40h]
0x180012621  mov     [rsp+0C8h+Strings], rcx
0x180012629  mov     rcx, [rdi+78h]
0x18001262d  mov     [rsp+0C8h+var_38], rcx
0x180012635  mov     rcx, [rdi+80h]
0x18001263c  mov     [rsp+0C8h+var_30], rcx
0x180012644  mov     rcx, [rdi+88h]
0x18001264b  mov     [rsp+0C8h+var_28], rcx
0x180012653  mov     rcx, [rdi+90h]
0x18001265a  mov     [rsp+0C8h+var_20], rcx
0x180012662  lea     rcx, [rsp+0C8h+Strings]
0x18001266a  mov     r9d, [r9]; dwEventID
0x18001266d  movzx   r8d, word ptr [r8]; wCategory
0x180012671  movzx   edx, word ptr [rdx]; wType
0x180012674  mov     [rsp+0C8h+lpRawData], 0; lpRawData
0x18001267d  mov     [rsp+0C8h+lpStrings], rcx; lpStrings
0x180012682  mov     rcx, rax; hEventLog
0x180012685  mov     [rsp+0C8h+dwDataSize], 0; dwDataSize
0x18001268d  mov     [rsp+0C8h+wNumStrings], 5; wNumStrings
0x180012694  mov     [rsp+0C8h+lpUserSid], 0; unsigned __int16
0x18001269d  call    cs:__imp_ReportEventW
0x1800126a3  mov     rdx, [rdi+38h]; unsigned __int16 *
0x1800126a7  lea     rcx, [rsp+0C8h+var_78]; this
0x1800126ac  call    ??0TextFileLogger@@QEAA@PEBGPEAUHINSTANCE__@@K@Z; TextFileLogger::TextFileLogger(ushort const *,HINSTANCE__ *,ulong)
0x1800126b1  mov     r8, [rdi+48h]
0x1800126b5  lea     rcx, [rsp+0C8h+Strings]
0x1800126bd  mov     r9, [rdi+68h]
0x1800126c1  mov     rdx, [rdi+40h]
0x1800126c5  mov     [rsp+0C8h+var_80], 0; unsigned __int16 *
0x1800126ce  movzx   r8d, word ptr [r8]; unsigned __int16
0x1800126d2  mov     r9d, [r9]; unsigned int
0x1800126d5  movzx   edx, word ptr [rdx]; unsigned __int16
0x1800126d8  mov     [rsp+0C8h+lpRawData], 0; unsigned __int16 *
0x1800126e1  mov     [rsp+0C8h+lpStrings], 0; void *
0x1800126ea  mov     qword ptr [rsp+0C8h+dwDataSize], rcx; va_list *
0x1800126ef  mov     rcx, rax; this
0x1800126f2  mov     qword ptr [rsp+0C8h+wNumStrings], 0; unsigned __int64
0x1800126fb  call    ?Report@TextFileLogger@@QEAAXGGKG_KPEAPEBGPEAXPEBG3@Z; TextFileLogger::Report(ushort,ushort,ulong,ushort,unsigned __int64,ushort const * *,void *,ushort const *,ushort const *)
0x180012700  lea     rcx, [rsp+0C8h+var_78]; this
0x180012705  call    ??1TextFileLogger@@UEAA@XZ; TextFileLogger::~TextFileLogger(void)
0x18001270a  xor     eax, eax
0x18001270c  mov     rcx, [rsp+0C8h+var_18]
0x180012714  xor     rcx, rsp; StackCookie
0x180012717  call    __security_check_cookie
0x18001271c  mov     rbx, [rsp+0C8h+arg_0]
0x180012724  add     rsp, 0C0h
0x18001272b  pop     rdi
0x18001272c  retn
```
