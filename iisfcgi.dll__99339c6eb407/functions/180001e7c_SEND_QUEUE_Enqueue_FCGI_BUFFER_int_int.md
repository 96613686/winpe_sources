# SEND_QUEUE::Enqueue(FCGI_BUFFER *,int,int *)

- ea: `0x180001e7c`
- end: `0x180001f7c`
- name: `?Enqueue@SEND_QUEUE@@QEAAJPEAVFCGI_BUFFER@@HPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(SEND_QUEUE *__hidden this, struct FCGI_BUFFER *, int, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800036b8`
- `0x180006a0c`
- `0x180006bcc`

## callees

- `0x180001e7c`
- `0x180002004`
- `0x180009128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ea9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ea9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f45`

## pseudocode

```c
__int64 __fastcall SEND_QUEUE::Enqueue(struct _RTL_CRITICAL_SECTION *this, struct FCGI_BUFFER *a2, int a3, int *a4)
{
  int SpinCount_high; // r12d
  int v9; // edi
  SEND_QUEUE **SpinCount; // rdx
  int v11; // eax

  SpinCount_high = 1;
  if ( !a3 )
    *a4 = 0;
  EnterCriticalSection(this + 1);
  if ( HIDWORD(this[2].DebugInfo) )
  {
    v9 = -2147023901;
  }
  else if ( a3 || HIDWORD(this->OwningThread) <= LODWORD(this->OwningThread) )
  {
    if ( *((_DWORD *)a2 + 7) == 6 )
      HIDWORD(this[2].OwningThread) = 1;
    SpinCount = (SEND_QUEUE **)this->SpinCount;
    if ( *SpinCount != (SEND_QUEUE *)&this->LockSemaphore )
      __fastfail(3u);
    SpinCount_high = HIDWORD(this[2].SpinCount);
    *((_QWORD *)a2 + 4) = &this->LockSemaphore;
    v9 = 0;
    *((_QWORD *)a2 + 5) = SpinCount;
    *SpinCount = (struct FCGI_BUFFER *)((char *)a2 + 32);
    this->SpinCount = (ULONG_PTR)a2 + 32;
    v11 = *((_DWORD *)a2 + 2);
    a2 = 0;
    HIDWORD(this->OwningThread) += v11;
    if ( !a3 && HIDWORD(this->OwningThread) > LODWORD(this->OwningThread) && !LODWORD(this[2].SpinCount) )
    {
      LODWORD(this[2].SpinCount) = 1;
      *a4 = 1;
    }
    if ( LODWORD(this[2].LockSemaphore)
      && (HIDWORD(this->OwningThread) >= LODWORD(this[2].OwningThread) || HIDWORD(this[2].OwningThread)) )
    {
      HIDWORD(this[2].LockSemaphore) = 1;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  LeaveCriticalSection(this + 1);
  if ( v9 >= 0 && !SpinCount_high )
    v9 = SEND_QUEUE::Send(this);
  if ( a2 )
    FCGI_BUFFER::Free(a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001e7c  push    rbx
0x180001e7e  push    rbp
0x180001e7f  push    rsi
0x180001e80  push    rdi
0x180001e81  push    r12
0x180001e83  push    r14
0x180001e85  push    r15
0x180001e87  sub     rsp, 20h
0x180001e8b  mov     r14, r9
0x180001e8e  mov     ebp, r8d
0x180001e91  mov     rsi, rdx
0x180001e94  mov     rbx, rcx
0x180001e97  mov     r12d, 1
0x180001e9d  test    r8d, r8d
0x180001ea0  jnz     short loc_180001EA5
0x180001ea2  mov     [r9], r8d
0x180001ea5  add     rcx, 28h ; '('; lpCriticalSection
0x180001ea9  call    cs:__imp_EnterCriticalSection
0x180001eaf  cmp     dword ptr [rbx+54h], 0
0x180001eb3  jz      short loc_180001EBF
0x180001eb5  mov     edi, 800703E3h
0x180001eba  jmp     loc_180001F41
0x180001ebf  test    ebp, ebp
0x180001ec1  jnz     short loc_180001ED2
0x180001ec3  mov     eax, [rbx+10h]
0x180001ec6  cmp     [rbx+14h], eax
0x180001ec9  jbe     short loc_180001ED2
0x180001ecb  mov     edi, 8007000Eh
0x180001ed0  jmp     short loc_180001F41
0x180001ed2  cmp     dword ptr [rsi+1Ch], 6
0x180001ed6  mov     r8d, r12d
0x180001ed9  jnz     short loc_180001EDF
0x180001edb  mov     [rbx+64h], r12d
0x180001edf  lea     rcx, [rbx+18h]
0x180001ee3  mov     rdx, [rcx+8]
0x180001ee7  cmp     [rdx], rcx
0x180001eea  jz      short loc_180001EF3
0x180001eec  mov     ecx, 3
0x180001ef1  int     29h; Win8: RtlFailFast(ecx)
0x180001ef3  mov     r12d, [rbx+74h]
0x180001ef7  lea     rax, [rsi+20h]
0x180001efb  mov     [rax], rcx
0x180001efe  xor     edi, edi
0x180001f00  mov     [rax+8], rdx
0x180001f04  mov     [rdx], rax
0x180001f07  mov     [rcx+8], rax
0x180001f0b  mov     eax, [rsi+8]
0x180001f0e  xor     esi, esi
0x180001f10  add     [rbx+14h], eax
0x180001f13  mov     eax, [rbx+14h]
0x180001f16  test    ebp, ebp
0x180001f18  jnz     short loc_180001F2B
0x180001f1a  cmp     eax, [rbx+10h]
0x180001f1d  jbe     short loc_180001F2B
0x180001f1f  cmp     [rbx+70h], esi
0x180001f22  jnz     short loc_180001F2B
0x180001f24  mov     [rbx+70h], r8d
0x180001f28  mov     [r14], r8d
0x180001f2b  cmp     [rbx+68h], esi
0x180001f2e  jz      short loc_180001F41
0x180001f30  mov     eax, [rbx+60h]
0x180001f33  cmp     [rbx+14h], eax
0x180001f36  jnb     short loc_180001F3D
0x180001f38  cmp     [rbx+64h], esi
0x180001f3b  jz      short loc_180001F41
0x180001f3d  mov     [rbx+6Ch], r8d
0x180001f41  lea     rcx, [rbx+28h]; lpCriticalSection
0x180001f45  call    cs:__imp_LeaveCriticalSection
0x180001f4b  test    edi, edi
0x180001f4d  js      short loc_180001F5E
0x180001f4f  test    r12d, r12d
0x180001f52  jnz     short loc_180001F5E
0x180001f54  mov     rcx, rbx; this
0x180001f57  call    ?Send@SEND_QUEUE@@AEAAJXZ; SEND_QUEUE::Send(void)
0x180001f5c  mov     edi, eax
0x180001f5e  test    rsi, rsi
0x180001f61  jz      short loc_180001F6B
0x180001f63  mov     rcx, rsi; this
0x180001f66  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180001f6b  mov     eax, edi
0x180001f6d  add     rsp, 20h
0x180001f71  pop     r15
0x180001f73  pop     r14
0x180001f75  pop     r12
0x180001f77  pop     rdi
0x180001f78  pop     rsi
0x180001f79  pop     rbp
0x180001f7a  pop     rbx
0x180001f7b  retn
```
