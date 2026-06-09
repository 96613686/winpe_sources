# FileLockHolder::Acquire(ushort const *,void *,int *)

- ea: `0x14000eb90`
- end: `0x14000ec87`
- name: `?Acquire@FileLockHolder@@UEAAXPEBGPEAXPEAH@Z`
- size: `247`
- prototype: `void __fastcall(FileLockHolder *this, const unsigned __int16 *, void *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x14000a148`
- `0x14000e4f4`
- `0x14000eb90`
- `0x140013f30`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14000ebe2`
- `KERNEL32!CreateFileW` at `0x14000ebe2`
- `KERNEL32!GetLastError` at `0x14000ebf2`
- `KERNEL32!GetLastError` at `0x14000ebf2`
- `KERNEL32!WaitForSingleObject` at `0x14000ec16`
- `KERNEL32!WaitForSingleObject` at `0x14000ec16`

## pseudocode

```c
void __fastcall FileLockHolder::Acquire(FileLockHolder *this, const unsigned __int16 *a2, void *a3, int *a4)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  struct IExecutionEngine *ExecutionEngine; // rax
  unsigned int v12; // ecx

  v4 = 0;
  if ( a4 )
    *a4 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x4000000u, 0);
    *((_QWORD *)this + 1) = FileW;
    if ( FileW != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( LastError != 32 )
    {
      if ( LastError != 5 || (++v4, v4 > 0xA) )
      {
        v12 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v12 = LastError;
        ThrowHR(v12);
      }
    }
    if ( a3 )
    {
      if ( !WaitForSingleObject(a3, 0x64u) )
      {
        if ( a4 )
          *a4 = 1;
        return;
      }
    }
    else
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 224LL))(
        ExecutionEngine,
        100);
    }
  }
}

```

## disassembly

```asm
0x14000eb90  mov     rax, rsp
0x14000eb93  mov     [rax+8], rbx
0x14000eb97  mov     [rax+10h], rbp
0x14000eb9b  mov     [rax+18h], rsi
0x14000eb9f  mov     [rax+20h], rdi
0x14000eba3  push    r14
0x14000eba5  sub     rsp, 40h
0x14000eba9  xor     edi, edi
0x14000ebab  mov     rbx, r9
0x14000ebae  mov     rsi, r8
0x14000ebb1  mov     rbp, rdx
0x14000ebb4  mov     r14, rcx
0x14000ebb7  test    r9, r9
0x14000ebba  jz      short loc_14000EBBF
0x14000ebbc  and     [r9], edi
0x14000ebbf  and     [rsp+48h+var_18], rdi
0x14000ebc4  mov     [rsp+48h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x14000ebcc  xor     r9d, r9d; lpSecurityAttributes
0x14000ebcf  xor     r8d, r8d; dwShareMode
0x14000ebd2  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x14000ebda  mov     edx, 40000000h; dwDesiredAccess
0x14000ebdf  mov     rcx, rbp; lpFileName
0x14000ebe2  call    cs:__imp_CreateFileW
0x14000ebe8  mov     [r14+8], rax
0x14000ebec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ebf0  jnz     short loc_14000EC2B
0x14000ebf2  call    cs:__imp_GetLastError
0x14000ebf8  cmp     eax, 20h ; ' '
0x14000ebfb  jz      short loc_14000EC09
0x14000ebfd  cmp     eax, 5
0x14000ec00  jnz     short loc_14000EC73
0x14000ec02  inc     edi
0x14000ec04  cmp     edi, 0Ah
0x14000ec07  ja      short loc_14000EC73
0x14000ec09  test    rsi, rsi
0x14000ec0c  jz      short loc_14000EC46
0x14000ec0e  mov     edx, 64h ; 'd'; dwMilliseconds
0x14000ec13  mov     rcx, rsi; hHandle
0x14000ec16  call    cs:__imp_WaitForSingleObject
0x14000ec1c  test    eax, eax
0x14000ec1e  jnz     short loc_14000EC68
0x14000ec20  test    rbx, rbx
0x14000ec23  jz      short loc_14000EC2B
0x14000ec25  mov     dword ptr [rbx], 1
0x14000ec2b  mov     rbx, [rsp+48h+arg_0]
0x14000ec30  mov     rbp, [rsp+48h+arg_8]
0x14000ec35  mov     rsi, [rsp+48h+arg_10]
0x14000ec3a  mov     rdi, [rsp+48h+arg_18]
0x14000ec3f  add     rsp, 40h
0x14000ec43  pop     r14
0x14000ec45  retn
0x14000ec46  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x14000ec4b  mov     r9, rax
0x14000ec4e  xor     r8d, r8d
0x14000ec51  mov     rcx, [rax]
0x14000ec54  lea     edx, [r8+64h]
0x14000ec58  mov     rax, [rcx+0E0h]
0x14000ec5f  mov     rcx, r9
0x14000ec62  call    cs:__guard_dispatch_icall_fptr
0x14000ec68  and     [rsp+48h+var_18], 0
0x14000ec6e  jmp     loc_14000EBC4
0x14000ec73  movzx   ecx, ax
0x14000ec76  or      ecx, 80070000h
0x14000ec7c  test    eax, eax
0x14000ec7e  cmovle  ecx, eax; int
0x14000ec81  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
