# SetBackupPath(char *)

- ea: `0x1800256b8`
- end: `0x1800257f7`
- name: `?SetBackupPath@@YAJPEAD@Z`
- size: `319`
- prototype: `__int64 __fastcall(LPCSTR lpPathName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180025800`

## callees

- `0x1800089c8`
- `0x18001adb8`
- `0x1800256b8`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1800256fe`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x1800256fe`
- `KERNEL32!CreateDirectoryA` at `0x180025738`
- `KERNEL32!CreateDirectoryA` at `0x180025738`
- `KERNEL32!GetFileAttributesA` at `0x1800256e1`
- `KERNEL32!GetFileAttributesA` at `0x1800256e1`
- `KERNEL32!LocalFree` at `0x1800257d2`
- `KERNEL32!LocalFree` at `0x1800257d2`
- `KERNEL32!GetLastError` at `0x180025708`
- `KERNEL32!GetLastError` at `0x180025742`
- `KERNEL32!GetLastError` at `0x180025708`
- `KERNEL32!GetLastError` at `0x180025742`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025789`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025789`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025774`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025774`

## pseudocode

```c
__int64 __fastcall SetBackupPath(LPCSTR lpPathName)
{
  DWORD FileAttributesA; // edi
  signed int LastError; // ebx
  STR *v4; // rax
  STR *v5; // rax
  unsigned int v6; // edx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  FileAttributesA = GetFileAttributesA(lpPathName);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorA(
          "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    goto LABEL_19;
  }
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 1;
  if ( FileAttributesA == -1 )
  {
    if ( CreateDirectoryA(lpPathName, &SecurityAttributes) )
      LastError = 0;
    else
      LastError = GetLastError();
    if ( LastError )
      goto LABEL_19;
  }
  else
  {
    LastError = 267;
    if ( (FileAttributesA & 0x10) == 0 )
      goto LABEL_19;
  }
  v4 = (STR *)operator new(0x38u);
  if ( !v4 )
  {
    g_pstrBackupFilePath = 0;
    goto LABEL_18;
  }
  v5 = STR::STR(v4, lpPathName);
  g_pstrBackupFilePath = v5;
  if ( !v5 )
  {
LABEL_18:
    LastError = 8;
    goto LABEL_19;
  }
  if ( STR::IsValid(v5) )
  {
    LastError = 0;
  }
  else
  {
    LastError = 8;
    if ( g_pstrBackupFilePath )
      STR::`scalar deleting destructor'(g_pstrBackupFilePath, v6);
    g_pstrBackupFilePath = 0;
  }
LABEL_19:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800256b8  mov     r11, rsp
0x1800256bb  mov     [r11+8], rbx
0x1800256bf  mov     [r11+18h], rsi
0x1800256c3  push    rdi
0x1800256c4  sub     rsp, 40h
0x1800256c8  xorps   xmm0, xmm0
0x1800256cb  mov     qword ptr [r11+10h], 0
0x1800256d3  xor     eax, eax
0x1800256d5  mov     rsi, rcx
0x1800256d8  movups  xmmword ptr [rsp+48h+SecurityAttributes.nLength], xmm0
0x1800256dd  mov     [r11-18h], rax
0x1800256e1  call    cs:__imp_GetFileAttributesA
0x1800256e7  xor     r9d, r9d; SecurityDescriptorSize
0x1800256ea  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1800256ef  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)"
0x1800256f6  mov     edi, eax
0x1800256f8  lea     ebx, [r9+1]
0x1800256fc  mov     edx, ebx; StringSDRevision
0x1800256fe  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorA
0x180025704  test    eax, eax
0x180025706  jnz     short loc_180025715
0x180025708  call    cs:__imp_GetLastError
0x18002570e  mov     ebx, eax
0x180025710  jmp     loc_1800257C8
0x180025715  mov     rax, [rsp+48h+SecurityDescriptor]
0x18002571a  mov     [rsp+48h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002571f  mov     [rsp+48h+SecurityAttributes.nLength], 18h
0x180025727  mov     [rsp+48h+SecurityAttributes.bInheritHandle], ebx
0x18002572b  cmp     edi, 0FFFFFFFFh
0x18002572e  jnz     short loc_180025754
0x180025730  lea     rdx, [rsp+48h+SecurityAttributes]; lpSecurityAttributes
0x180025735  mov     rcx, rsi; lpPathName
0x180025738  call    cs:__imp_CreateDirectoryA
0x18002573e  test    eax, eax
0x180025740  jnz     short loc_18002574C
0x180025742  call    cs:__imp_GetLastError
0x180025748  mov     ebx, eax
0x18002574a  jmp     short loc_18002574E
0x18002574c  xor     ebx, ebx
0x18002574e  test    ebx, ebx
0x180025750  jz      short loc_18002575F
0x180025752  jmp     short loc_1800257C8
0x180025754  mov     ebx, 10Bh
0x180025759  test    dil, 10h
0x18002575d  jz      short loc_1800257C8
0x18002575f  mov     ecx, 38h ; '8'; Size
0x180025764  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025769  test    rax, rax
0x18002576c  jz      short loc_1800257B8
0x18002576e  mov     rdx, rsi
0x180025771  mov     rcx, rax
0x180025774  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x18002577a  mov     cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA, rax; STR * g_pstrBackupFilePath
0x180025781  test    rax, rax
0x180025784  jz      short loc_1800257C3
0x180025786  mov     rcx, rax
0x180025789  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x18002578f  test    eax, eax
0x180025791  jnz     short loc_1800257B4
0x180025793  mov     rcx, cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA; this
0x18002579a  lea     ebx, [rax+8]
0x18002579d  test    rcx, rcx
0x1800257a0  jz      short loc_1800257A7
0x1800257a2  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x1800257a7  mov     cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA, 0; STR * g_pstrBackupFilePath
0x1800257b2  jmp     short loc_1800257C8
0x1800257b4  xor     ebx, ebx
0x1800257b6  jmp     short loc_1800257C8
0x1800257b8  mov     cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA, 0; STR * g_pstrBackupFilePath
0x1800257c3  mov     ebx, 8
0x1800257c8  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x1800257cd  test    rcx, rcx
0x1800257d0  jz      short loc_1800257D8
0x1800257d2  call    cs:__imp_LocalFree
0x1800257d8  test    ebx, ebx
0x1800257da  jle     short loc_1800257E5
0x1800257dc  movzx   ebx, bx
0x1800257df  or      ebx, 80070000h
0x1800257e5  mov     rsi, [rsp+48h+arg_10]
0x1800257ea  mov     eax, ebx
0x1800257ec  mov     rbx, [rsp+48h+arg_0]
0x1800257f1  add     rsp, 40h
0x1800257f5  pop     rdi
0x1800257f6  retn
```
