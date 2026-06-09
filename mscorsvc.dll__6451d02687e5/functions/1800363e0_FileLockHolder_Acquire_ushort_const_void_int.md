# FileLockHolder::Acquire(ushort const *,void *,int *)

- ea: `0x1800363e0`
- end: `0x1800364bf`
- name: `?Acquire@FileLockHolder@@UEAAXPEBGPEAXPEAH@Z`
- size: `223`
- prototype: `void __fastcall(FileLockHolder *this, const unsigned __int16 *, void *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005df0`
- `0x180013cd0`

## callees

- `0x18003069c`
- `0x180034fd4`
- `0x1800363e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180036432`
- `KERNEL32!CreateFileW` at `0x180036432`
- `KERNEL32!WaitForSingleObject` at `0x180036466`
- `KERNEL32!WaitForSingleObject` at `0x180036466`
- `KERNEL32!GetLastError` at `0x180036442`
- `KERNEL32!GetLastError` at `0x180036442`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FileLockHolder::Acquire(FileLockHolder *this, const unsigned __int16 *a2, void *a3, int *a4)
{
  unsigned int v4; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  int v11; // edx
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
      ClrSleepEx(0x64u, v11);
    }
  }
}

```

## disassembly

```asm
0x1800363e0  mov     rax, rsp
0x1800363e3  mov     [rax+8], rbx
0x1800363e7  mov     [rax+10h], rbp
0x1800363eb  mov     [rax+18h], rsi
0x1800363ef  mov     [rax+20h], rdi
0x1800363f3  push    r14
0x1800363f5  sub     rsp, 40h
0x1800363f9  xor     edi, edi
0x1800363fb  mov     rbx, r9
0x1800363fe  mov     rsi, r8
0x180036401  mov     rbp, rdx
0x180036404  mov     r14, rcx
0x180036407  test    r9, r9
0x18003640a  jz      short loc_18003640F
0x18003640c  and     [r9], edi
0x18003640f  and     [rsp+48h+var_18], rdi
0x180036414  mov     [rsp+48h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18003641c  xor     r9d, r9d; lpSecurityAttributes
0x18003641f  xor     r8d, r8d; dwShareMode
0x180036422  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18003642a  mov     edx, 40000000h; dwDesiredAccess
0x18003642f  mov     rcx, rbp; lpFileName
0x180036432  call    cs:__imp_CreateFileW
0x180036438  mov     [r14+8], rax
0x18003643c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036440  jnz     short loc_18003647B
0x180036442  call    cs:__imp_GetLastError
0x180036448  cmp     eax, 20h ; ' '
0x18003644b  jz      short loc_180036459
0x18003644d  cmp     eax, 5
0x180036450  jnz     short loc_1800364AB
0x180036452  inc     edi
0x180036454  cmp     edi, 0Ah
0x180036457  ja      short loc_1800364AB
0x180036459  test    rsi, rsi
0x18003645c  jz      short loc_180036496
0x18003645e  mov     edx, 64h ; 'd'; dwMilliseconds
0x180036463  mov     rcx, rsi; hHandle
0x180036466  call    cs:__imp_WaitForSingleObject
0x18003646c  test    eax, eax
0x18003646e  jnz     short loc_1800364A0
0x180036470  test    rbx, rbx
0x180036473  jz      short loc_18003647B
0x180036475  mov     dword ptr [rbx], 1
0x18003647b  mov     rbx, [rsp+48h+arg_0]
0x180036480  mov     rbp, [rsp+48h+arg_8]
0x180036485  mov     rsi, [rsp+48h+arg_10]
0x18003648a  mov     rdi, [rsp+48h+arg_18]
0x18003648f  add     rsp, 40h
0x180036493  pop     r14
0x180036495  retn
0x180036496  mov     ecx, 64h ; 'd'; unsigned int
0x18003649b  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x1800364a0  and     [rsp+48h+var_18], 0
0x1800364a6  jmp     loc_180036414
0x1800364ab  movzx   ecx, ax
0x1800364ae  or      ecx, 80070000h
0x1800364b4  test    eax, eax
0x1800364b6  cmovle  ecx, eax; int
0x1800364b9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
