# CMsmqVssWriter::SaveComponents(ulong,void *)

- ea: `0x180093e3c`
- end: `0x180093f19`
- name: `?SaveComponents@CMsmqVssWriter@@AEAAJKPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091590`
- `0x1800929fc`

## callees

- `0x18002c61c`
- `0x18003c644`
- `0x180093e3c`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180093e7d`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180093e7d`
- `ADVAPI32!RegSetValueExW` at `0x180093ed4`
- `ADVAPI32!RegSetValueExW` at `0x180093ed4`
- `ADVAPI32!RegOpenKeyExW` at `0x180093e8d`
- `ADVAPI32!RegOpenKeyExW` at `0x180093e8d`

## string_xrefs

- `0x180093ef5`: `writer/mqwriter`
- `0x180093ec8`: `RestoreComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsmqVssWriter::SaveComponents(CMsmqVssWriter *this, int a2, void *a3)
{
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  signed int v5; // ebx
  bool v6; // sf
  unsigned __int16 v7; // r8
  LSTATUS v8; // eax
  int Data; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 4);
  if ( a3 )
    v4 = RegOpenKeyTransactedW(HKEY_LOCAL_MACHINE, v3, 0, 0xF003Fu, &hKey, a3, 0);
  else
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0xF003Fu, &hKey);
  v5 = v4;
  v6 = v4 < 0;
  if ( v4 )
  {
    if ( v4 > 0 )
    {
      v5 = (unsigned __int16)v4 | 0x80070000;
      v6 = 1;
    }
    if ( v6 )
    {
      v7 = 3140;
LABEL_14:
      LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", v7);
    }
  }
  else
  {
    v8 = RegSetValueExW(hKey, L"RestoreComponents", 0, 4u, (const BYTE *)&Data, 4u);
    v5 = v8;
    if ( !v8 )
    {
      v5 = 0;
      goto LABEL_16;
    }
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
    {
      v7 = 3160;
      goto LABEL_14;
    }
  }
LABEL_16:
  CRegHandle::~CRegHandle((CRegHandle *)&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180093e3c  mov     [rsp+Data], edx
0x180093e40  mov     r11, rsp
0x180093e43  push    rbx
0x180093e44  sub     rsp, 40h
0x180093e48  mov     qword ptr [r11+18h], 0
0x180093e50  mov     rdx, [rcx+20h]; lpSubKey
0x180093e54  lea     rax, [r11+18h]
0x180093e58  mov     r9d, 0F003Fh; samDesired
0x180093e5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093e65  test    r8, r8
0x180093e68  jz      short loc_180093E85
0x180093e6a  mov     qword ptr [r11-18h], 0
0x180093e72  mov     [r11-20h], r8
0x180093e76  mov     [r11-28h], rax
0x180093e7a  xor     r8d, r8d; ulOptions
0x180093e7d  call    cs:__imp_RegOpenKeyTransactedW
0x180093e83  jmp     short loc_180093E93
0x180093e85  mov     [rsp+48h+phkResult], rax; phkResult
0x180093e8a  xor     r8d, r8d; ulOptions
0x180093e8d  call    cs:__imp_RegOpenKeyExW
0x180093e93  mov     ebx, eax
0x180093e95  test    eax, eax
0x180093e97  jz      short loc_180093EB0
0x180093e99  jle     short loc_180093EA6
0x180093e9b  movzx   ebx, bx
0x180093e9e  or      ebx, 80070000h
0x180093ea4  test    ebx, ebx
0x180093ea6  jns     short loc_180093F07
0x180093ea8  mov     r8d, 0C44h
0x180093eae  jmp     short loc_180093EF5
0x180093eb0  mov     r9d, 4; dwType
0x180093eb6  mov     [rsp+48h+cbData], r9d; cbData
0x180093ebb  lea     rax, [rsp+48h+Data]
0x180093ec0  mov     [rsp+48h+phkResult], rax; lpData
0x180093ec5  xor     r8d, r8d; Reserved
0x180093ec8  lea     rdx, aRestorecompone; "RestoreComponents"
0x180093ecf  mov     rcx, [rsp+48h+hKey]; hKey
0x180093ed4  call    cs:__imp_RegSetValueExW
0x180093eda  mov     ebx, eax
0x180093edc  test    eax, eax
0x180093ede  jz      short loc_180093F05
0x180093ee0  jle     short loc_180093EEB
0x180093ee2  movzx   ebx, ax
0x180093ee5  or      ebx, 80070000h
0x180093eeb  test    ebx, ebx
0x180093eed  jns     short loc_180093F07
0x180093eef  mov     r8d, 0C58h; unsigned __int16
0x180093ef5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093efc  mov     ecx, ebx; int
0x180093efe  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093f03  jmp     short loc_180093F07
0x180093f05  xor     ebx, ebx
0x180093f07  lea     rcx, [rsp+48h+hKey]; this
0x180093f0c  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180093f11  mov     eax, ebx
0x180093f13  add     rsp, 40h
0x180093f17  pop     rbx
0x180093f18  retn
```
