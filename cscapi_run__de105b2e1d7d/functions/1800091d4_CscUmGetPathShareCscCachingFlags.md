# CscUmGetPathShareCscCachingFlags

- ea: `0x1800091d4`
- end: `0x1800092e9`
- name: `CscUmGetPathShareCscCachingFlags`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007880`

## callees

- `0x180002db0`
- `0x1800091d4`
- `0x1800092f0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800092b3`
- `ntdll!NtFsControlFile` at `0x1800092b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092cf`

## pseudocode

```c
__int64 __fastcall CscUmGetPathShareCscCachingFlags(const UNICODE_STRING *a1, _DWORD *a2)
{
  PWSTR Buffer; // rax
  __int64 v5; // rdx
  int IsCscByPassPath; // ebx
  int InputBuffer; // [rsp+30h] [rbp-30h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-10h] BYREF
  char v10; // [rsp+90h] [rbp+30h] BYREF
  int OutputBuffer; // [rsp+98h] [rbp+38h] BYREF
  HANDLE FileHandle; // [rsp+A0h] [rbp+40h] BYREF

  FileHandle = 0;
  OutputBuffer = 0;
  IoStatusBlock = 0;
  v10 = 0;
  *a2 = 48;
  if ( a1->Length >= 4u && (Buffer = a1->Buffer, *Buffer == 92) && Buffer[1] == 92 )
  {
    IsCscByPassPath = CscUmIsCscByPassPath(a1, &v10);
    if ( IsCscByPassPath >= 0 && !v10 )
    {
      IsCscByPassPath = CscDriverOpenItemWithDispositionEx(&FileHandle, v5, a1, 0, 1048704, 7u, InputBuffer, 0);
      if ( IsCscByPassPath >= 0 )
      {
        IsCscByPassPath = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401F4u, 0, 0, &OutputBuffer, 4u);
        if ( IsCscByPassPath >= 0 )
        {
          IsCscByPassPath = 0;
          *a2 = OutputBuffer;
        }
      }
    }
    if ( FileHandle )
      CloseHandle(FileHandle);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)IsCscByPassPath;
}

```

## disassembly

```asm
0x1800091d4  push    rbp
0x1800091d6  push    rbx
0x1800091d7  push    rsi
0x1800091d8  push    rdi
0x1800091d9  push    r15
0x1800091db  mov     rbp, rsp
0x1800091de  sub     rsp, 60h
0x1800091e2  mov     r15d, 4
0x1800091e8  mov     [rbp+FileHandle], 0
0x1800091f0  xorps   xmm0, xmm0
0x1800091f3  mov     rsi, rdx
0x1800091f6  mov     rdi, rcx
0x1800091f9  mov     [rbp+arg_8], 0
0x180009200  movups  xmmword ptr [rbp+var_10], xmm0
0x180009204  mov     [rbp+arg_0], 0
0x180009208  mov     dword ptr [rdx], 30h ; '0'
0x18000920e  cmp     [rcx], r15w
0x180009212  jb      loc_1800092D7
0x180009218  mov     rax, [rcx+8]
0x18000921c  cmp     word ptr [rax], 5Ch ; '\'
0x180009220  jnz     loc_1800092D7
0x180009226  cmp     word ptr [rax+2], 5Ch ; '\'
0x18000922b  jnz     loc_1800092D7
0x180009231  lea     rdx, [rbp+arg_0]
0x180009235  call    CscUmIsCscByPassPath
0x18000923a  mov     ebx, eax
0x18000923c  test    eax, eax
0x18000923e  js      loc_1800092C6
0x180009244  cmp     [rbp+arg_0], 0
0x180009248  jnz     short loc_1800092C6
0x18000924a  mov     [rsp+60h+InputBufferLength], 0; int
0x180009252  lea     rcx, [rbp+FileHandle]; FileHandle
0x180009256  mov     [rsp+60h+FsControlCode], 7; ULONG
0x18000925e  xor     r9d, r9d
0x180009261  mov     r8, rdi
0x180009264  mov     dword ptr [rsp+60h+IoStatusBlock], 100080h; int
0x18000926c  call    CscDriverOpenItemWithDispositionEx
0x180009271  mov     ebx, eax
0x180009273  test    eax, eax
0x180009275  js      short loc_1800092C6
0x180009277  mov     rcx, [rbp+FileHandle]; FileHandle
0x18000927b  lea     rax, [rbp+arg_8]
0x18000927f  mov     [rsp+60h+OutputBufferLength], r15d; OutputBufferLength
0x180009284  xor     r9d, r9d; ApcContext
0x180009287  mov     [rsp+60h+OutputBuffer], rax; OutputBuffer
0x18000928c  xor     r8d, r8d; ApcRoutine
0x18000928f  mov     [rsp+60h+InputBufferLength], 0; InputBufferLength
0x180009297  lea     rax, [rbp+var_10]
0x18000929b  mov     [rsp+60h+InputBuffer], 0; InputBuffer
0x1800092a4  xor     edx, edx; Event
0x1800092a6  mov     [rsp+60h+FsControlCode], 1401F4h; FsControlCode
0x1800092ae  mov     [rsp+60h+IoStatusBlock], rax; IoStatusBlock
0x1800092b3  call    cs:__imp_NtFsControlFile
0x1800092b9  mov     ebx, eax
0x1800092bb  test    eax, eax
0x1800092bd  js      short loc_1800092C6
0x1800092bf  mov     eax, [rbp+arg_8]
0x1800092c2  xor     ebx, ebx
0x1800092c4  mov     [rsi], eax
0x1800092c6  mov     rcx, [rbp+FileHandle]; hObject
0x1800092ca  test    rcx, rcx
0x1800092cd  jz      short loc_1800092DC
0x1800092cf  call    cs:__imp_CloseHandle
0x1800092d5  jmp     short loc_1800092DC
0x1800092d7  mov     ebx, 0C000000Dh
0x1800092dc  mov     eax, ebx
0x1800092de  add     rsp, 60h
0x1800092e2  pop     r15
0x1800092e4  pop     rdi
0x1800092e5  pop     rsi
0x1800092e6  pop     rbx
0x1800092e7  pop     rbp
0x1800092e8  retn
```
