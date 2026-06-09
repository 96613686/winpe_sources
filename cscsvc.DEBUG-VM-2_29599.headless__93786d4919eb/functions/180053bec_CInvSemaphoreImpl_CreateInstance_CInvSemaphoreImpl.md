# CInvSemaphoreImpl::CreateInstance(CInvSemaphoreImpl * *)

- ea: `0x180053bec`
- end: `0x180053caf`
- name: `?CreateInstance@CInvSemaphoreImpl@@SAJPEAPEAV1@@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct CInvSemaphoreImpl **)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180032a8c`
- `0x18004dfe0`
- `0x180055248`
- `0x180063c8c`
- `0x180065850`
- `0x1800693a8`

## callees

- `0x18001b150`
- `0x18002f10c`
- `0x1800391b8`
- `0x180053bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180053c82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180053c82`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053c47`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180053c47`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053c5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053c5d`

## pseudocode

```c
__int64 __fastcall CInvSemaphoreImpl::CreateInstance(struct CInvSemaphoreImpl **a1)
{
  int Error; // edi
  char *v3; // rax
  char *v4; // rbx
  HANDLE EventW; // rax

  *a1 = 0;
  Error = -2147024882;
  v3 = (char *)operator new(0x50u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    *((_QWORD *)v3 + 2) = 0;
    *(_QWORD *)v3 = &CInvSemaphoreImpl::`vftable';
    *((_DWORD *)v3 + 6) = 0;
    *((_DWORD *)v3 + 18) = 0;
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v3 + 32), 0) )
    {
      EventW = CreateEventW(0, 1, 1, 0);
      *((_QWORD *)v4 + 2) = EventW;
      if ( EventW )
      {
        *((_DWORD *)v4 + 18) = 1;
        Error = 0;
        goto LABEL_8;
      }
      Error = ResultFromLastError();
      DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    }
    else
    {
      Error = ResultFromLastError();
    }
    if ( Error < 0 )
    {
LABEL_9:
      CRefCounted::ReleaseReference((CRefCounted *)v4);
      return (unsigned int)Error;
    }
LABEL_8:
    *a1 = (struct CInvSemaphoreImpl *)v4;
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
    goto LABEL_9;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180053bec  push    rbx
0x180053bee  push    rbp
0x180053bef  push    rsi
0x180053bf0  push    rdi
0x180053bf1  sub     rsp, 28h
0x180053bf5  mov     rsi, rcx
0x180053bf8  mov     qword ptr [rcx], 0
0x180053bff  mov     ecx, 50h ; 'P'; Size
0x180053c04  mov     edi, 8007000Eh
0x180053c09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053c0e  mov     rbx, rax
0x180053c11  test    rax, rax
0x180053c14  jz      loc_180053CA4
0x180053c1a  mov     dword ptr [rax+8], 1
0x180053c21  lea     rcx, [rbx+20h]; lpCriticalSection
0x180053c25  lea     rax, ??_7CInvSemaphoreImpl@@6B@; const CInvSemaphoreImpl::`vftable'
0x180053c2c  mov     qword ptr [rbx+10h], 0
0x180053c34  xor     edx, edx; dwSpinCount
0x180053c36  mov     [rbx], rax
0x180053c39  mov     dword ptr [rbx+18h], 0
0x180053c40  mov     dword ptr [rbx+48h], 0
0x180053c47  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180053c4d  test    eax, eax
0x180053c4f  jz      short loc_180053C8A
0x180053c51  xor     r9d, r9d; lpName
0x180053c54  xor     ecx, ecx; lpEventAttributes
0x180053c56  lea     edx, [r9+1]; bManualReset
0x180053c5a  mov     r8d, edx; bInitialState
0x180053c5d  call    cs:__imp_CreateEventW
0x180053c63  mov     [rbx+10h], rax
0x180053c67  test    rax, rax
0x180053c6a  jz      short loc_180053C77
0x180053c6c  mov     dword ptr [rbx+48h], 1
0x180053c73  xor     edi, edi
0x180053c75  jmp     short loc_180053C95
0x180053c77  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180053c7c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180053c80  mov     edi, eax
0x180053c82  call    cs:__imp_DeleteCriticalSection
0x180053c88  jmp     short loc_180053C91
0x180053c8a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180053c8f  mov     edi, eax
0x180053c91  test    edi, edi
0x180053c93  js      short loc_180053C9C
0x180053c95  mov     [rsi], rbx
0x180053c98  lock inc dword ptr [rbx+8]
0x180053c9c  mov     rcx, rbx; this
0x180053c9f  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180053ca4  mov     eax, edi
0x180053ca6  add     rsp, 28h
0x180053caa  pop     rdi
0x180053cab  pop     rsi
0x180053cac  pop     rbp
0x180053cad  pop     rbx
0x180053cae  retn
```
