# Network::GetIconFromDisk(wchar_t const *,int,ulong,ulong *,uchar * *)

- ea: `0x1800e4198`
- end: `0x1800e4349`
- name: `?GetIconFromDisk@Network@@AEAAJPEB_WHKPEAKPEAPEAE@Z`
- size: `433`
- prototype: `__int64 __fastcall(Network *__hidden this, const wchar_t *, int, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800e3ca0`

## callees

- `0x180014d80`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800caf10`
- `0x1800e4198`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e430a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e430a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e42b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e42b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e42f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e42f7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e42a6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e42a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e428a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e428a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e42dd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e42dd`

## pseudocode

```c
__int64 __fastcall Network::GetIconFromDisk(
        wchar_t *this,
        const wchar_t *a2,
        int a3,
        int a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  signed int System32Directory; // ebx
  const char *v11; // r9
  HANDLE FileW; // rax
  void *v13; // rdi
  DWORD FileSize; // eax
  DWORD v15; // r14d
  unsigned __int8 *v16; // rax
  __int64 result; // rax
  DWORD FileSizeHigh; // [rsp+40h] [rbp-468h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-464h] BYREF
  WCHAR FileName[520]; // [rsp+50h] [rbp-458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  memset_0(FileName, 0, sizeof(FileName));
  *a5 = 0;
  *a6 = 0;
  if ( a3 )
  {
    StringCchPrintfW(FileName, 0x208u, L"%s_%d.bin", a2, a4);
  }
  else if ( !this[68] )
  {
    System32Directory = GetSystem32Directory(this + 68);
    if ( System32Directory )
      goto LABEL_14;
    StringCchPrintfW(FileName, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", this + 68, a2, a4);
  }
  System32Directory = 2;
  FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_15:
    System32Directory = (unsigned __int16)System32Directory | 0x80070000;
    goto LABEL_16;
  }
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  v15 = FileSize;
  if ( FileSize != -1 )
  {
    v16 = (unsigned __int8 *)CoTaskMemAlloc(FileSize);
    *a6 = v16;
    if ( v16 )
    {
      NumberOfBytesRead = 0;
      if ( ReadFile(v13, v16, v15, &NumberOfBytesRead, 0) )
      {
        *a5 = NumberOfBytesRead;
        System32Directory = 0;
      }
      else
      {
        CoTaskMemFree(*a6);
        *a6 = 0;
      }
    }
    else
    {
      System32Directory = 14;
    }
  }
  CloseHandle(v13);
LABEL_14:
  if ( System32Directory > 0 )
    goto LABEL_15;
LABEL_16:
  result = (unsigned int)System32Directory;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      FileSizeHigh = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0xC3,
                       (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\profilei.cpp",
                       v11);
      result = FileSizeHigh;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800e4198  push    rbx
0x1800e419a  push    rsi
0x1800e419b  push    rdi
0x1800e419c  push    r12
0x1800e419e  push    r13
0x1800e41a0  push    r14
0x1800e41a2  push    r15
0x1800e41a4  sub     rsp, 470h
0x1800e41ab  mov     rax, cs:__security_cookie
0x1800e41b2  xor     rax, rsp
0x1800e41b5  mov     [rsp+4A8h+var_48], rax
0x1800e41bd  mov     r15d, r9d
0x1800e41c0  mov     ebx, r8d
0x1800e41c3  mov     r14, rdx
0x1800e41c6  mov     rdi, rcx
0x1800e41c9  mov     r12, [rsp+4A8h+arg_20]
0x1800e41d1  mov     rsi, [rsp+4A8h+arg_28]
0x1800e41d9  xor     edx, edx; Val
0x1800e41db  mov     r8d, 410h; Size
0x1800e41e1  lea     rcx, [rsp+4A8h+FileName]; void *
0x1800e41e6  call    memset_0
0x1800e41eb  xor     r13d, r13d
0x1800e41ee  mov     [r12], r13d
0x1800e41f2  mov     [rsi], r13
0x1800e41f5  test    ebx, ebx
0x1800e41f7  jnz     short loc_1800E4242
0x1800e41f9  cmp     [rdi+88h], r13w
0x1800e4201  jnz     short loc_1800E4260
0x1800e4203  lea     rcx, [rdi+88h]; wchar_t *
0x1800e420a  call    ?GetSystem32Directory@@YAKPEA_W@Z; GetSystem32Directory(wchar_t *)
0x1800e420f  mov     ebx, eax
0x1800e4211  test    eax, eax
0x1800e4213  jnz     loc_1800E4310
0x1800e4219  mov     [rsp+4A8h+dwFlagsAndAttributes], r15d
0x1800e421e  mov     qword ptr [rsp+4A8h+dwCreationDisposition], r14
0x1800e4223  lea     r9, [rdi+88h]
0x1800e422a  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800e4231  mov     edx, 208h; unsigned __int64
0x1800e4236  lea     rcx, [rsp+4A8h+FileName]; wchar_t *
0x1800e423b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800e4240  jmp     short loc_1800E4260
0x1800e4242  mov     [rsp+4A8h+dwCreationDisposition], r15d
0x1800e4247  mov     r9, r14
0x1800e424a  lea     r8, aSDBin; "%s_%d.bin"
0x1800e4251  mov     edx, 208h; unsigned __int64
0x1800e4256  lea     rcx, [rsp+4A8h+FileName]; wchar_t *
0x1800e425b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800e4260  mov     ebx, 2
0x1800e4265  mov     [rsp+4A8h+hTemplateFile], r13; hTemplateFile
0x1800e426a  mov     [rsp+4A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e4272  mov     [rsp+4A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e427a  xor     r9d, r9d; lpSecurityAttributes
0x1800e427d  xor     r8d, r8d; dwShareMode
0x1800e4280  mov     edx, 80000000h; dwDesiredAccess
0x1800e4285  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x1800e428a  call    cs:__imp_CreateFileW
0x1800e4290  mov     rdi, rax
0x1800e4293  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e4297  jz      short loc_1800E4314
0x1800e4299  mov     [rsp+4A8h+FileSizeHigh], r13d
0x1800e429e  lea     rdx, [rsp+4A8h+FileSizeHigh]; lpFileSizeHigh
0x1800e42a3  mov     rcx, rax; hFile
0x1800e42a6  call    cs:__imp_GetFileSize
0x1800e42ac  mov     r14d, eax
0x1800e42af  cmp     eax, 0FFFFFFFFh
0x1800e42b2  jz      short loc_1800E4307
0x1800e42b4  mov     ecx, r14d; cb
0x1800e42b7  call    cs:__imp_CoTaskMemAlloc
0x1800e42bd  mov     [rsi], rax
0x1800e42c0  test    rax, rax
0x1800e42c3  jz      short loc_1800E4302
0x1800e42c5  mov     [rsp+4A8h+NumberOfBytesRead], r13d
0x1800e42ca  mov     qword ptr [rsp+4A8h+dwCreationDisposition], r13; lpOverlapped
0x1800e42cf  lea     r9, [rsp+4A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e42d4  mov     r8d, r14d; nNumberOfBytesToRead
0x1800e42d7  mov     rdx, rax; lpBuffer
0x1800e42da  mov     rcx, rdi; hFile
0x1800e42dd  call    cs:__imp_ReadFile
0x1800e42e3  test    eax, eax
0x1800e42e5  jz      short loc_1800E42F4
0x1800e42e7  mov     eax, [rsp+4A8h+NumberOfBytesRead]
0x1800e42eb  mov     [r12], eax
0x1800e42ef  mov     ebx, r13d
0x1800e42f2  jmp     short loc_1800E4307
0x1800e42f4  mov     rcx, [rsi]; pv
0x1800e42f7  call    cs:__imp_CoTaskMemFree
0x1800e42fd  mov     [rsi], r13
0x1800e4300  jmp     short loc_1800E4307
0x1800e4302  mov     ebx, 0Eh
0x1800e4307  mov     rcx, rdi; hObject
0x1800e430a  call    cs:__imp_CloseHandle
0x1800e4310  test    ebx, ebx
0x1800e4312  jle     short loc_1800E431D
0x1800e4314  movzx   ebx, bx
0x1800e4317  or      ebx, 80070000h
0x1800e431d  mov     eax, ebx
0x1800e431f  jmp     short loc_1800E4325
0x1800e4321  mov     eax, [rsp+4A8h+FileSizeHigh]
0x1800e4325  mov     rcx, [rsp+4A8h+var_48]
0x1800e432d  xor     rcx, rsp; StackCookie
0x1800e4330  call    __security_check_cookie
0x1800e4335  add     rsp, 470h
0x1800e433c  pop     r15
0x1800e433e  pop     r14
0x1800e4340  pop     r13
0x1800e4342  pop     r12
0x1800e4344  pop     rdi
0x1800e4345  pop     rsi
0x1800e4346  pop     rbx
0x1800e4347  retn
```
