# CSharelock::CSharelock(int,int)

- ea: `0x180013610`
- end: `0x1800136dd`
- name: `??0CSharelock@@QEAA@HH@Z`
- size: `205`
- prototype: `CSharelock *__fastcall(CSharelock *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800135f0`
- `0x180016e00`

## callees

- `0x180013610`
- `0x18002e473`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180013664`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180013664`

## string_xrefs

- `0x180013679`: `Create semaphore in constructor for CSharelock`

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
0x180013610  push    rbx
0x180013612  sub     rsp, 30h
0x180013616  mov     dword ptr [rcx], 0
0x18001361c  mov     rbx, rcx
0x18001361f  mov     dword ptr [rcx+4], 0
0x180013626  mov     dword ptr [rcx+18h], 0
0x18001362d  test    edx, edx
0x18001362f  jle     loc_1800136BF
0x180013635  lea     eax, [r8-1]
0x180013639  mov     [rcx+8], edx
0x18001363c  cmp     eax, 0FFh
0x180013641  ja      short loc_1800136A1
0x180013643  mov     [rcx+0Ch], r8d
0x180013647  xor     r9d, r9d; lpName
0x18001364a  xor     ecx, ecx; lpSemaphoreAttributes
0x18001364c  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180013654  mov     r8d, 100h; lMaximumCount
0x18001365a  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180013662  xor     edx, edx; lInitialCount
0x180013664  call    cs:__imp_CreateSemaphoreExW
0x18001366b  nop     dword ptr [rax+rax+00h]
0x180013670  mov     [rbx+10h], rax
0x180013674  test    rax, rax
0x180013677  jnz     short loc_180013697
0x180013679  lea     rax, aCreateSemaphor; "Create semaphore in constructor for CSh"...
0x180013680  lea     rdx, _TI2PEAG; pThrowInfo
0x180013687  mov     [rsp+38h+pExceptionObject], rax
0x18001368c  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180013691  call    _CxxThrowException_0
0x180013697  mov     rax, rbx
0x18001369a  add     rsp, 30h
0x18001369e  pop     rbx
0x18001369f  retn
0x1800136a1  lea     rax, aMaximumShareIn; "Maximum share invalid in constructor fo"...
0x1800136a8  lea     rdx, _TI2PEAG; pThrowInfo
0x1800136af  mov     [rsp+38h+pExceptionObject], rax
0x1800136b4  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800136b9  call    _CxxThrowException_0
0x1800136bf  lea     rax, aMaximumSpinsIn; "Maximum spins invalid in constructor fo"...
0x1800136c6  lea     rdx, _TI2PEAG; pThrowInfo
0x1800136cd  mov     [rsp+38h+pExceptionObject], rax
0x1800136d2  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800136d7  call    _CxxThrowException_0
```
