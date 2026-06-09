# CInvSemaphoreImpl::CreateInstance(CInvSemaphoreImpl * *)

- ea: `0x18003f9d8`
- end: `0x18003fa9b`
- name: `?CreateInstance@CInvSemaphoreImpl@@SAJPEAPEAV1@@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct CInvSemaphoreImpl **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019a20`

## callees

- `0x180006500`
- `0x180008a7c`
- `0x18000c1e8`
- `0x18003f9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fa49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fa49`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003fa6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003fa6e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003fa33`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003fa33`

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
      Error = ResultFromKnownLastError();
      DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 32));
    }
    else
    {
      Error = ResultFromKnownLastError();
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
0x18003f9d8  push    rbx
0x18003f9da  push    rbp
0x18003f9db  push    rsi
0x18003f9dc  push    rdi
0x18003f9dd  sub     rsp, 28h
0x18003f9e1  mov     rsi, rcx
0x18003f9e4  mov     qword ptr [rcx], 0
0x18003f9eb  mov     ecx, 50h ; 'P'; Size
0x18003f9f0  mov     edi, 8007000Eh
0x18003f9f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f9fa  mov     rbx, rax
0x18003f9fd  test    rax, rax
0x18003fa00  jz      loc_18003FA90
0x18003fa06  mov     dword ptr [rax+8], 1
0x18003fa0d  lea     rcx, [rbx+20h]; lpCriticalSection
0x18003fa11  lea     rax, ??_7CInvSemaphoreImpl@@6B@; const CInvSemaphoreImpl::`vftable'
0x18003fa18  mov     qword ptr [rbx+10h], 0
0x18003fa20  xor     edx, edx; dwSpinCount
0x18003fa22  mov     [rbx], rax
0x18003fa25  mov     dword ptr [rbx+18h], 0
0x18003fa2c  mov     dword ptr [rbx+48h], 0
0x18003fa33  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003fa39  test    eax, eax
0x18003fa3b  jz      short loc_18003FA76
0x18003fa3d  xor     r9d, r9d; lpName
0x18003fa40  xor     ecx, ecx; lpEventAttributes
0x18003fa42  lea     edx, [r9+1]; bManualReset
0x18003fa46  mov     r8d, edx; bInitialState
0x18003fa49  call    cs:__imp_CreateEventW
0x18003fa4f  mov     [rbx+10h], rax
0x18003fa53  test    rax, rax
0x18003fa56  jz      short loc_18003FA63
0x18003fa58  mov     dword ptr [rbx+48h], 1
0x18003fa5f  xor     edi, edi
0x18003fa61  jmp     short loc_18003FA81
0x18003fa63  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003fa68  lea     rcx, [rbx+20h]; lpCriticalSection
0x18003fa6c  mov     edi, eax
0x18003fa6e  call    cs:__imp_DeleteCriticalSection
0x18003fa74  jmp     short loc_18003FA7D
0x18003fa76  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003fa7b  mov     edi, eax
0x18003fa7d  test    edi, edi
0x18003fa7f  js      short loc_18003FA88
0x18003fa81  mov     [rsi], rbx
0x18003fa84  lock inc dword ptr [rbx+8]
0x18003fa88  mov     rcx, rbx; this
0x18003fa8b  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18003fa90  mov     eax, edi
0x18003fa92  add     rsp, 28h
0x18003fa96  pop     rdi
0x18003fa97  pop     rsi
0x18003fa98  pop     rbp
0x18003fa99  pop     rbx
0x18003fa9a  retn
```
