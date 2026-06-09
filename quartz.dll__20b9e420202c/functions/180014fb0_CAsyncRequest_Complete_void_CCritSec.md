# CAsyncRequest::Complete(void *,CCritSec *)

- ea: `0x180014fb0`
- end: `0x180015098`
- name: `?Complete@CAsyncRequest@@QEAAJPEAXPEAVCCritSec@@@Z`
- size: `232`
- prototype: `int(CAsyncRequest *__hidden this, void *, struct CCritSec *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014d00`
- `0x180014ef0`
- `0x180028930`
- `0x1800fd468`

## callees

- `0x180014fb0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001500c`
- `KERNEL32!LeaveCriticalSection` at `0x180015080`
- `KERNEL32!LeaveCriticalSection` at `0x18001500c`
- `KERNEL32!LeaveCriticalSection` at `0x180015080`
- `KERNEL32!EnterCriticalSection` at `0x180014fc5`
- `KERNEL32!EnterCriticalSection` at `0x180014fc5`
- `KERNEL32!GetLastError` at `0x180014fee`
- `KERNEL32!GetLastError` at `0x18001504f`
- `KERNEL32!GetLastError` at `0x180014fee`
- `KERNEL32!GetLastError` at `0x18001504f`
- `KERNEL32!SetFilePointer` at `0x180014fdd`
- `KERNEL32!SetFilePointer` at `0x180014fdd`
- `KERNEL32!ReadFile` at `0x18001503f`
- `KERNEL32!ReadFile` at `0x18001503f`

## pseudocode

```c
__int64 __fastcall CAsyncRequest::Complete(CAsyncRequest *this, void *a2, struct _RTL_CRITICAL_SECTION *a3)
{
  DWORD LastError; // ebp
  unsigned int v7; // ebp
  DWORD v9; // r8d
  void *v10; // rdx
  DWORD v11; // ebx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  EnterCriticalSection(a3);
  if ( SetFilePointer(a2, *(_DWORD *)this, (PLONG)this + 1, 0) == -1 && (LastError = GetLastError()) != 0 )
  {
    v7 = LastError | 0x80070000;
    *((_DWORD *)this + 10) = v7;
    LeaveCriticalSection(a3);
    return v7;
  }
  else
  {
    v9 = *((_DWORD *)this + 2);
    v10 = (void *)*((_QWORD *)this + 2);
    NumberOfBytesRead = 0;
    if ( ReadFile(a2, v10, v9, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == *((_DWORD *)this + 2) )
      {
        v11 = 0;
      }
      else
      {
        *((_DWORD *)this + 2) = NumberOfBytesRead;
        v11 = 1;
      }
    }
    else
    {
      v11 = GetLastError() | 0x80070000;
    }
    *((_DWORD *)this + 10) = v11;
    LeaveCriticalSection(a3);
    return v11;
  }
}

```

## disassembly

```asm
0x180014fb0  push    rbx
0x180014fb2  push    rbp
0x180014fb3  push    rsi
0x180014fb4  push    rdi
0x180014fb5  sub     rsp, 38h
0x180014fb9  mov     rdi, rcx
0x180014fbc  mov     rsi, r8
0x180014fbf  mov     rcx, r8; lpCriticalSection
0x180014fc2  mov     rbx, rdx
0x180014fc5  call    cs:__imp_EnterCriticalSection
0x180014fcc  nop     dword ptr [rax+rax+00h]
0x180014fd1  mov     edx, [rdi]; lDistanceToMove
0x180014fd3  lea     r8, [rdi+4]; lpDistanceToMoveHigh
0x180014fd7  xor     r9d, r9d; dwMoveMethod
0x180014fda  mov     rcx, rbx; hFile
0x180014fdd  call    cs:__imp_SetFilePointer
0x180014fe4  nop     dword ptr [rax+rax+00h]
0x180014fe9  cmp     eax, 0FFFFFFFFh
0x180014fec  jnz     short loc_180015024
0x180014fee  call    cs:__imp_GetLastError
0x180014ff5  nop     dword ptr [rax+rax+00h]
0x180014ffa  mov     ebp, eax
0x180014ffc  test    eax, eax
0x180014ffe  jz      short loc_180015024
0x180015000  or      ebp, 80070000h
0x180015006  mov     rcx, rsi; lpCriticalSection
0x180015009  mov     [rdi+28h], ebp
0x18001500c  call    cs:__imp_LeaveCriticalSection
0x180015013  nop     dword ptr [rax+rax+00h]
0x180015018  mov     eax, ebp
0x18001501a  add     rsp, 38h
0x18001501e  pop     rdi
0x18001501f  pop     rsi
0x180015020  pop     rbp
0x180015021  pop     rbx
0x180015022  retn
0x180015024  mov     r8d, [rdi+8]; nNumberOfBytesToRead
0x180015028  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001502d  mov     rdx, [rdi+10h]; lpBuffer
0x180015031  xor     ebp, ebp
0x180015033  mov     rcx, rbx; hFile
0x180015036  mov     [rsp+58h+NumberOfBytesRead], ebp
0x18001503a  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x18001503f  call    cs:__imp_ReadFile
0x180015046  nop     dword ptr [rax+rax+00h]
0x18001504b  test    eax, eax
0x18001504d  jnz     short loc_180015065
0x18001504f  call    cs:__imp_GetLastError
0x180015056  nop     dword ptr [rax+rax+00h]
0x18001505b  mov     ebx, eax
0x18001505d  or      ebx, 80070000h
0x180015063  jmp     short loc_18001507A
0x180015065  mov     eax, [rsp+58h+NumberOfBytesRead]
0x180015069  cmp     eax, [rdi+8]
0x18001506c  jz      short loc_180015078
0x18001506e  mov     [rdi+8], eax
0x180015071  mov     ebx, 1
0x180015076  jmp     short loc_18001507A
0x180015078  mov     ebx, ebp
0x18001507a  mov     rcx, rsi; lpCriticalSection
0x18001507d  mov     [rdi+28h], ebx
0x180015080  call    cs:__imp_LeaveCriticalSection
0x180015087  nop     dword ptr [rax+rax+00h]
0x18001508c  mov     eax, ebx
0x18001508e  add     rsp, 38h
0x180015092  pop     rdi
0x180015093  pop     rsi
0x180015094  pop     rbp
0x180015095  pop     rbx
0x180015096  retn
```
