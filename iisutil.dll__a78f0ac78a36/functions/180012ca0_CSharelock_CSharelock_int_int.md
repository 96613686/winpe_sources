# CSharelock::CSharelock(int,int)

- ea: `0x180012ca0`
- end: `0x180012d66`
- name: `??0CSharelock@@QEAA@HH@Z`
- size: `198`
- prototype: `CSharelock *__fastcall(CSharelock *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c80`
- `0x180016230`

## callees

- `0x180012ca0`
- `0x18002c3dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012cf4`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012cf4`

## string_xrefs

- `0x180012d03`: `Create semaphore in constructor for CSharelock`

## pseudocode

```c
CSharelock *__fastcall CSharelock::CSharelock(CSharelock *this, int a2, int a3)
{
  HANDLE Semaphore; // rax
  const wchar_t *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF

  *(_DWORD *)this = 0;
  *((_DWORD *)this + 1) = 0;
  *((_DWORD *)this + 6) = 0;
  if ( a2 <= 0 )
  {
    pExceptionObject = L"Maximum spins invalid in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  *((_DWORD *)this + 2) = a2;
  if ( (unsigned int)(a3 - 1) > 0xFF )
  {
    pExceptionObject = L"Maximum share invalid in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  *((_DWORD *)this + 3) = a3;
  Semaphore = CreateSemaphoreExW(0, 0, 256, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 2) = Semaphore;
  if ( !Semaphore )
  {
    pExceptionObject = L"Create semaphore in constructor for CSharelock";
    throw (ushort **)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180012ca0  push    rbx
0x180012ca2  sub     rsp, 30h
0x180012ca6  mov     dword ptr [rcx], 0
0x180012cac  mov     rbx, rcx
0x180012caf  mov     dword ptr [rcx+4], 0
0x180012cb6  mov     dword ptr [rcx+18h], 0
0x180012cbd  test    edx, edx
0x180012cbf  jle     loc_180012D48
0x180012cc5  lea     eax, [r8-1]
0x180012cc9  mov     [rcx+8], edx
0x180012ccc  cmp     eax, 0FFh
0x180012cd1  ja      short loc_180012D2A
0x180012cd3  mov     [rcx+0Ch], r8d
0x180012cd7  xor     r9d, r9d; lpName
0x180012cda  xor     ecx, ecx; lpSemaphoreAttributes
0x180012cdc  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180012ce4  mov     r8d, 100h; lMaximumCount
0x180012cea  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180012cf2  xor     edx, edx; lInitialCount
0x180012cf4  call    cs:__imp_CreateSemaphoreExW
0x180012cfa  mov     [rbx+10h], rax
0x180012cfe  test    rax, rax
0x180012d01  jnz     short loc_180012D21
0x180012d03  lea     rax, aCreateSemaphor; "Create semaphore in constructor for CSh"...
0x180012d0a  lea     rdx, _TI2PEAG; pThrowInfo
0x180012d11  mov     [rsp+38h+pExceptionObject], rax
0x180012d16  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180012d1b  call    _CxxThrowException_0
0x180012d21  mov     rax, rbx
0x180012d24  add     rsp, 30h
0x180012d28  pop     rbx
0x180012d29  retn
0x180012d2a  lea     rax, aMaximumShareIn; "Maximum share invalid in constructor fo"...
0x180012d31  lea     rdx, _TI2PEAG; pThrowInfo
0x180012d38  mov     [rsp+38h+pExceptionObject], rax
0x180012d3d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180012d42  call    _CxxThrowException_0
0x180012d48  lea     rax, aMaximumSpinsIn; "Maximum spins invalid in constructor fo"...
0x180012d4f  lea     rdx, _TI2PEAG; pThrowInfo
0x180012d56  mov     [rsp+38h+pExceptionObject], rax
0x180012d5b  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180012d60  call    _CxxThrowException_0
```
