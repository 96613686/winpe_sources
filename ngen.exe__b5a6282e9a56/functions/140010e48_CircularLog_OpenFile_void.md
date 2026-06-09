# CircularLog::OpenFile(void)

- ea: `0x140010e48`
- end: `0x14001107a`
- name: `?OpenFile@CircularLog@@IEAAPEAXXZ`
- size: `562`
- prototype: `__int64 __fastcall(CircularLog *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140010938`

## callees

- `0x14000a148`
- `0x14000b010`
- `0x14000bad0`
- `0x140010e48`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x140010f8b`
- `KERNEL32!GetFileSizeEx` at `0x140010f8b`
- `KERNEL32!CreateFileW` at `0x140010ebe`
- `KERNEL32!CreateFileW` at `0x140010f0f`
- `KERNEL32!CreateFileW` at `0x140010ebe`
- `KERNEL32!CreateFileW` at `0x140010f0f`
- `KERNEL32!GetLastError` at `0x140010ece`
- `KERNEL32!GetLastError` at `0x140010f1e`
- `KERNEL32!GetLastError` at `0x140010ece`
- `KERNEL32!GetLastError` at `0x140010f1e`
- `KERNEL32!CloseHandle` at `0x140010f98`
- `KERNEL32!CloseHandle` at `0x140010f98`
- `KERNEL32!WriteFile` at `0x140010fcf`
- `KERNEL32!WriteFile` at `0x140011033`
- `KERNEL32!WriteFile` at `0x140010fcf`
- `KERNEL32!WriteFile` at `0x140011033`
- `KERNEL32!HeapFree` at `0x14001106c`
- `KERNEL32!HeapFree` at `0x14001106c`
- `KERNEL32!GetProcessHeap` at `0x140011057`
- `KERNEL32!GetProcessHeap` at `0x140011057`

## pseudocode

```c
__int64 __fastcall CircularLog::OpenFile(CircularLog *this)
{
  int v2; // esi
  SString *v3; // rdi
  const WCHAR *v4; // rcx
  __int64 result; // rax
  const WCHAR *v6; // rcx
  HANDLE FileW; // rax
  void *v8; // rbx
  struct IExecutionEngine *ExecutionEngine; // rax
  const char *UTF8; // rax
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  __int16 Buffer; // [rsp+48h] [rbp-C0h] BYREF
  char v14; // [rsp+4Ah] [rbp-BEh]
  unsigned int v15; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-B8h] BYREF
  LARGE_INTEGER FileSize; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+6Ch] [rbp-9Ch]
  LPVOID lpMem; // [rsp+78h] [rbp-90h]
  __int16 v21; // [rsp+80h] [rbp-88h] BYREF

  v2 = 0;
  v3 = (CircularLog *)((char *)this + 8);
  while ( 1 )
  {
    if ( v3 )
    {
      SString::ConvertToUnicode(v3);
      v4 = (const WCHAR *)*((_QWORD *)v3 + 2);
    }
    else
    {
      v4 = 0;
    }
    result = (__int64)CreateFileW(v4, 4u, 3u, 0, 3u, 0x80u, 0);
    if ( result != -1 )
      break;
    if ( GetLastError() == 2 )
    {
      if ( v3 )
      {
        SString::ConvertToUnicode(v3);
        v6 = (const WCHAR *)*((_QWORD *)v3 + 2);
      }
      else
      {
        v6 = 0;
      }
      FileW = CreateFileW(v6, 4u, 1u, 0, 4u, 0x80u, 0);
      v8 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( !GetFileSizeEx(FileW, &FileSize) )
        {
          CloseHandle(v8);
          return -1;
        }
        if ( !FileSize.QuadPart )
        {
          Buffer = -17425;
          v14 = -65;
          WriteFile(v8, &Buffer, 3u, NumberOfBytesWritten, 0);
          v19 = 256;
          lpMem = &v21;
          v18 = 2;
          v21 = 0;
          v15 = 0;
          UTF8 = SString::GetUTF8(
                   (CircularLog *)((char *)this + 32),
                   (struct SString::AbstractScratchBuffer *)&v18,
                   &v15);
          WriteFile(v8, UTF8, v15 - 1, NumberOfBytesWritten, 0);
          if ( (v19 & 0x800000000LL) != 0 )
          {
            v11 = lpMem;
            if ( lpMem )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v11);
            }
          }
        }
        return (__int64)v8;
      }
    }
    if ( GetLastError() == 32 )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 224LL))(
        ExecutionEngine,
        100);
      if ( ++v2 < 10 )
        continue;
    }
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x140010e48  mov     rax, rsp
0x140010e4b  mov     [rax+10h], rbx
0x140010e4f  mov     [rax+18h], rsi
0x140010e53  mov     [rax+20h], rdi
0x140010e57  push    rbp
0x140010e58  push    r14
0x140010e5a  push    r15
0x140010e5c  lea     rbp, [rax-0A8h]
0x140010e63  sub     rsp, 190h
0x140010e6a  mov     rax, cs:__security_cookie
0x140010e71  xor     rax, rsp
0x140010e74  mov     [rbp+0A0h+var_20], rax
0x140010e7b  mov     r14, rcx
0x140010e7e  xor     r15d, r15d
0x140010e81  mov     esi, r15d
0x140010e84  lea     rdi, [rcx+8]
0x140010e88  test    rdi, rdi
0x140010e8b  jnz     short loc_140010E92
0x140010e8d  mov     rcx, r15
0x140010e90  jmp     short loc_140010E9E
0x140010e92  mov     rcx, rdi; this
0x140010e95  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010e9a  mov     rcx, [rdi+10h]; lpFileName
0x140010e9e  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x140010ea3  mov     [rsp+1A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140010eab  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x140010eb3  xor     r9d, r9d; lpSecurityAttributes
0x140010eb6  lea     edx, [r9+4]; dwDesiredAccess
0x140010eba  lea     r8d, [r9+3]; dwShareMode
0x140010ebe  call    cs:__imp_CreateFileW
0x140010ec4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010ec8  jnz     loc_140010F57
0x140010ece  call    cs:__imp_GetLastError
0x140010ed4  cmp     eax, 2
0x140010ed7  jnz     short loc_140010F1E
0x140010ed9  test    rdi, rdi
0x140010edc  jnz     short loc_140010EE3
0x140010ede  mov     rcx, r15
0x140010ee1  jmp     short loc_140010EEF
0x140010ee3  mov     rcx, rdi; this
0x140010ee6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140010eeb  mov     rcx, [rdi+10h]; lpFileName
0x140010eef  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x140010ef4  mov     [rsp+1A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140010efc  mov     [rsp+1A0h+dwCreationDisposition], 4; dwCreationDisposition
0x140010f04  xor     r9d, r9d; lpSecurityAttributes
0x140010f07  lea     edx, [r9+4]; dwDesiredAccess
0x140010f0b  lea     r8d, [r9+1]; dwShareMode
0x140010f0f  call    cs:__imp_CreateFileW
0x140010f15  mov     rbx, rax
0x140010f18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010f1c  jnz     short loc_140010F83
0x140010f1e  call    cs:__imp_GetLastError
0x140010f24  cmp     eax, 20h ; ' '
0x140010f27  jnz     short loc_140010F53
0x140010f29  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x140010f2e  mov     rcx, rax
0x140010f31  mov     rax, [rax]
0x140010f34  xor     r8d, r8d
0x140010f37  lea     edx, [r8+64h]
0x140010f3b  mov     rax, [rax+0E0h]
0x140010f42  call    cs:__guard_dispatch_icall_fptr
0x140010f48  inc     esi
0x140010f4a  cmp     esi, 0Ah
0x140010f4d  jl      loc_140010E88
0x140010f53  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010f57  mov     rcx, [rbp+0A0h+var_20]
0x140010f5e  xor     rcx, rsp; StackCookie
0x140010f61  call    __security_check_cookie
0x140010f66  lea     r11, [rsp+1A0h+var_10]
0x140010f6e  mov     rbx, [r11+28h]
0x140010f72  mov     rsi, [r11+30h]
0x140010f76  mov     rdi, [r11+38h]
0x140010f7a  mov     rsp, r11
0x140010f7d  pop     r15
0x140010f7f  pop     r14
0x140010f81  pop     rbp
0x140010f82  retn
0x140010f83  lea     rdx, [rsp+1A0h+FileSize]; lpFileSize
0x140010f88  mov     rcx, rbx; hFile
0x140010f8b  call    cs:__imp_GetFileSizeEx
0x140010f91  test    eax, eax
0x140010f93  jnz     short loc_140010FA0
0x140010f95  mov     rcx, rbx; hObject
0x140010f98  call    cs:__imp_CloseHandle
0x140010f9e  jmp     short loc_140010F53
0x140010fa0  cmp     qword ptr [rsp+1A0h+FileSize], r15
0x140010fa5  jnz     loc_140011072
0x140010fab  mov     [rsp+1A0h+Buffer], 0BBEFh
0x140010fb2  mov     [rsp+1A0h+var_15E], 0BFh
0x140010fb7  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r15; lpOverlapped
0x140010fbc  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140010fc1  mov     r8d, 3; nNumberOfBytesToWrite
0x140010fc7  lea     rdx, [rsp+1A0h+Buffer]; lpBuffer
0x140010fcc  mov     rcx, rbx; hFile
0x140010fcf  call    cs:__imp_WriteFile
0x140010fd5  mov     qword ptr [rsp+1A0h+var_140], r15
0x140010fda  mov     qword ptr [rsp+64h], 100h
0x140010fe3  mov     [rsp+1A0h+lpMem], r15
0x140010fe8  lea     rax, [rsp+1A0h+var_128]
0x140010fed  mov     [rsp+1A0h+lpMem], rax
0x140010ff2  mov     [rsp+1A0h+var_140], 2
0x140010ffa  mov     rax, [rsp+1A0h+lpMem]
0x140010fff  mov     [rax], r15w
0x140011003  mov     [rsp+1A0h+var_15C], r15d
0x140011008  lea     rcx, [r14+20h]; this
0x14001100c  lea     r8, [rsp+1A0h+var_15C]; unsigned int *
0x140011011  lea     rdx, [rsp+1A0h+var_140]; struct SString::AbstractScratchBuffer *
0x140011016  call    ?GetUTF8@SString@@QEBAPEBDAEAVAbstractScratchBuffer@1@PEAI@Z; SString::GetUTF8(SString::AbstractScratchBuffer &,uint *)
0x14001101b  mov     r8d, [rsp+1A0h+var_15C]
0x140011020  dec     r8d; nNumberOfBytesToWrite
0x140011023  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r15; lpOverlapped
0x140011028  lea     r9, [rsp+1A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001102d  mov     rdx, rax; lpBuffer
0x140011030  mov     rcx, rbx; hFile
0x140011033  call    cs:__imp_WriteFile
0x140011039  nop
0x14001103a  test    byte ptr [rsp+1A0h+var_138], 8
0x14001103f  jz      short loc_140011072
0x140011041  mov     rdi, [rsp+1A0h+lpMem]
0x140011046  test    rdi, rdi
0x140011049  jz      short loc_140011072
0x14001104b  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140011052  test    rax, rax
0x140011055  jnz     short loc_140011064
0x140011057  call    cs:__imp_GetProcessHeap
0x14001105d  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140011064  mov     r8, rdi; lpMem
0x140011067  xor     edx, edx; dwFlags
0x140011069  mov     rcx, rax; hHeap
0x14001106c  call    cs:__imp_HeapFree
0x140011072  mov     rax, rbx
0x140011075  jmp     loc_140010F57
```
