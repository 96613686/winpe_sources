# CFileReadStream::Open(wchar_t const *)

- ea: `0x180144840`
- end: `0x180144922`
- name: `?Open@CFileReadStream@@UEAAJPEB_W@Z`
- size: `226`
- prototype: `int(CFileReadStream *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180144840`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801448c3`
- `KERNEL32!GetLastError` at `0x1801448cd`
- `KERNEL32!GetLastError` at `0x1801448c3`
- `KERNEL32!GetLastError` at `0x1801448cd`
- `KERNEL32!GetFileSize` at `0x1801448b5`
- `KERNEL32!GetFileSize` at `0x1801448b5`
- `KERNEL32!CreateFileW` at `0x18014489e`
- `KERNEL32!CreateFileW` at `0x18014489e`

## pseudocode

```c
__int64 __fastcall CFileReadStream::Open(CFileReadStream *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax

  if ( a2 && *a2 )
  {
    if ( *((_QWORD *)this + 2) == -1 )
    {
      FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
      *((_QWORD *)this + 2) = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, (LPDWORD)this + 7);
        *((_DWORD *)this + 6) = FileSize;
        if ( FileSize != -1 || !GetLastError() )
          return 0;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        return v3;
    }
    else
    {
      v3 = -2147221302;
    }
  }
  else
  {
    v3 = -2147221303;
  }
  (*(void (__fastcall **)(CFileReadStream *))(*(_QWORD *)this + 56LL))(this);
  return v3;
}

```

## disassembly

```asm
0x180144840  mov     [rsp+arg_0], rbx
0x180144845  push    rdi
0x180144846  sub     rsp, 40h
0x18014484a  mov     rax, rdx
0x18014484d  mov     rdi, rcx
0x180144850  test    rdx, rdx
0x180144853  jz      loc_180144900
0x180144859  cmp     word ptr [rdx], 0
0x18014485d  jz      loc_180144900
0x180144863  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x180144868  jz      short loc_180144874
0x18014486a  mov     ebx, 800400CAh
0x18014486f  jmp     loc_180144905
0x180144874  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18014487d  xor     r9d, r9d; lpSecurityAttributes
0x180144880  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180144888  mov     edx, 80000000h; dwDesiredAccess
0x18014488d  mov     r8d, 1; dwShareMode
0x180144893  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18014489b  mov     rcx, rax; lpFileName
0x18014489e  call    cs:__imp_CreateFileW
0x1801448a4  mov     [rdi+10h], rax
0x1801448a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801448ac  jz      short loc_1801448CD
0x1801448ae  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x1801448b2  mov     rcx, rax; hFile
0x1801448b5  call    cs:__imp_GetFileSize
0x1801448bb  mov     [rdi+18h], eax
0x1801448be  cmp     eax, 0FFFFFFFFh
0x1801448c1  jnz     short loc_1801448F3
0x1801448c3  call    cs:__imp_GetLastError
0x1801448c9  test    eax, eax
0x1801448cb  jz      short loc_1801448F3
0x1801448cd  call    cs:__imp_GetLastError
0x1801448d3  mov     ebx, eax
0x1801448d5  test    eax, eax
0x1801448d7  jle     short loc_1801448E2
0x1801448d9  movzx   ebx, ax
0x1801448dc  or      ebx, 80070000h
0x1801448e2  test    ebx, ebx
0x1801448e4  js      short loc_180144905
0x1801448e6  mov     eax, ebx
0x1801448e8  mov     rbx, [rsp+48h+arg_0]
0x1801448ed  add     rsp, 40h
0x1801448f1  pop     rdi
0x1801448f2  retn
0x1801448f3  xor     eax, eax
0x1801448f5  mov     rbx, [rsp+48h+arg_0]
0x1801448fa  add     rsp, 40h
0x1801448fe  pop     rdi
0x1801448ff  retn
0x180144900  mov     ebx, 800400C9h
0x180144905  mov     rax, [rdi]
0x180144908  mov     rcx, rdi
0x18014490b  mov     rax, [rax+38h]
0x18014490f  call    cs:__guard_dispatch_icall_fptr
0x180144915  mov     eax, ebx
0x180144917  mov     rbx, [rsp+48h+arg_0]
0x18014491c  add     rsp, 40h
0x180144920  pop     rdi
0x180144921  retn
```
