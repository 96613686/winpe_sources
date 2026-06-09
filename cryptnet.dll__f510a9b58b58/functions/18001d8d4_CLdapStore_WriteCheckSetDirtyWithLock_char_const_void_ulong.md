# CLdapStore::WriteCheckSetDirtyWithLock(char const *,void *,ulong)

- ea: `0x18001d8d4`
- end: `0x18001d95f`
- name: `?WriteCheckSetDirtyWithLock@CLdapStore@@AEAAHPEBDPEAXK@Z`
- size: `139`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const char *, void *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d490`
- `0x18001d4b0`
- `0x18001d4d0`
- `0x18001d640`
- `0x18001d660`
- `0x18001d680`

## callees

- `0x180012f9c`
- `0x18001d8d4`
- `0x180025008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d939`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d8f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d939`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d901`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d94e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d94e`

## pseudocode

```c
__int64 __fastcall CLdapStore::WriteCheckSetDirtyWithLock(
        LPCRITICAL_SECTION lpCriticalSection,
        const char *a2,
        void *a3,
        int a4)
{
  void *CorrespondingObject; // rax
  unsigned int v10; // edi

  if ( (lpCriticalSection[2].SpinCount & 0x8000) != 0 )
  {
    SetLastError(5u);
    return 0;
  }
  else
  {
    EnterCriticalSection(lpCriticalSection);
    if ( (a4 & 0xFFFF0000) == 0x40000
      && (CorrespondingObject = ObjectContextFindCorrespondingObject(lpCriticalSection[2].LockSemaphore, a2, a3)) != 0 )
    {
      ObjectContextFree(a2, CorrespondingObject);
      SetLastError(0x80092005);
      v10 = 0;
    }
    else
    {
      v10 = 1;
      HIDWORD(lpCriticalSection[2].SpinCount) = 1;
    }
    LeaveCriticalSection(lpCriticalSection);
    return v10;
  }
}

```

## disassembly

```asm
0x18001d8d4  push    rbx
0x18001d8d6  push    rbp
0x18001d8d7  push    rsi
0x18001d8d8  push    rdi
0x18001d8d9  sub     rsp, 28h
0x18001d8dd  test    dword ptr [rcx+70h], 8000h
0x18001d8e4  mov     edi, r9d
0x18001d8e7  mov     rbp, r8
0x18001d8ea  mov     rsi, rdx
0x18001d8ed  mov     rbx, rcx
0x18001d8f0  jz      short loc_18001D901
0x18001d8f2  mov     ecx, 5; dwErrCode
0x18001d8f7  call    cs:__imp_SetLastError
0x18001d8fd  xor     eax, eax
0x18001d8ff  jmp     short loc_18001D956
0x18001d901  call    cs:__imp_EnterCriticalSection
0x18001d907  and     edi, 0FFFF0000h
0x18001d90d  cmp     edi, 40000h
0x18001d913  jnz     short loc_18001D943
0x18001d915  mov     rcx, [rbx+68h]; hCertStore
0x18001d919  mov     r8, rbp; void *
0x18001d91c  mov     rdx, rsi; char *
0x18001d91f  call    ?ObjectContextFindCorrespondingObject@@YAPEAXPEAXPEBD0@Z; ObjectContextFindCorrespondingObject(void *,char const *,void *)
0x18001d924  test    rax, rax
0x18001d927  jz      short loc_18001D943
0x18001d929  mov     rdx, rax; void *
0x18001d92c  mov     rcx, rsi; char *
0x18001d92f  call    ?ObjectContextFree@@YAXPEBDPEAX@Z; ObjectContextFree(char const *,void *)
0x18001d934  mov     ecx, 80092005h; dwErrCode
0x18001d939  call    cs:__imp_SetLastError
0x18001d93f  xor     edi, edi
0x18001d941  jmp     short loc_18001D94B
0x18001d943  mov     edi, 1
0x18001d948  mov     [rbx+74h], edi
0x18001d94b  mov     rcx, rbx; lpCriticalSection
0x18001d94e  call    cs:__imp_LeaveCriticalSection
0x18001d954  mov     eax, edi
0x18001d956  add     rsp, 28h
0x18001d95a  pop     rdi
0x18001d95b  pop     rsi
0x18001d95c  pop     rbp
0x18001d95d  pop     rbx
0x18001d95e  retn
```
