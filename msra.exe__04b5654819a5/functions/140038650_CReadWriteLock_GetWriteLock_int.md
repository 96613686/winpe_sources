# CReadWriteLock::GetWriteLock(int *)

- ea: `0x140038650`
- end: `0x1400387d9`
- name: `?GetWriteLock@CReadWriteLock@@QEAAJPEAH@Z`
- size: `393`
- prototype: `__int64 __fastcall(CReadWriteLock *__hidden this, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ea24`
- `0x14002cb94`
- `0x140030460`

## callees

- `0x140034ce4`
- `0x140038650`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400386ef`
- `KERNEL32!GetLastError` at `0x140038706`
- `KERNEL32!GetLastError` at `0x1400386ef`
- `KERNEL32!GetLastError` at `0x140038706`
- `KERNEL32!ReleaseMutex` at `0x1400387a5`
- `KERNEL32!ReleaseMutex` at `0x1400387a5`
- `KERNEL32!WaitForSingleObject` at `0x14003869e`
- `KERNEL32!WaitForSingleObject` at `0x1400386db`
- `KERNEL32!WaitForSingleObject` at `0x14003869e`
- `KERNEL32!WaitForSingleObject` at `0x1400386db`
- `KERNEL32!ReleaseSemaphore` at `0x1400386c4`
- `KERNEL32!ReleaseSemaphore` at `0x1400386c4`

## string_xrefs

- `0x14003874f`: `base\diagnosis\ra\racommon\src\readwritelock.cpp`
- `0x140038783`: `base\diagnosis\ra\racommon\src\readwritelock.cpp`
- `0x140038748`: `CReadWriteLock::GetWriteLock`
- `0x140038769`: `CReadWriteLock::GetWriteLock`

## pseudocode

```c
__int64 __fastcall CReadWriteLock::GetWriteLock(CReadWriteLock *this, int *a2)
{
  CEventLogger *v3; // rcx
  unsigned int v5; // ebp
  int v6; // edi
  int *v7; // rbx
  CEventLogger *v8; // rcx
  void *v9; // rcx
  unsigned int v10; // r9d
  signed int LastError; // eax
  CEventLogger *v12; // rcx
  int PreviousCount; // [rsp+50h] [rbp+8h] BYREF

  PreviousCount = 0;
  v3 = (CEventLogger *)*((_QWORD *)this + 1);
  v5 = -2147019873;
  if ( !v3 || !*((_QWORD *)this + 2) )
  {
    v6 = -2147019873;
    CEventLogger::LogError(
      v3,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
      0x95u,
      L"CReadWriteLock::GetWriteLock",
      0x8007139F);
    v7 = (int *)((char *)this + 4);
    goto LABEL_16;
  }
  v6 = 0;
  v7 = (int *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) == 1 )
    goto LABEL_18;
  if ( WaitForSingleObject(v3, 0) )
  {
    v10 = 169;
    goto LABEL_13;
  }
  v9 = (void *)*((_QWORD *)this + 2);
  *v7 = 1;
  if ( ReleaseSemaphore(v9, 1, &PreviousCount) )
  {
    WaitForSingleObject(*((HANDLE *)this + 2), 0);
    v10 = 184;
LABEL_13:
    v6 = -2147024726;
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
      v10,
      L"CReadWriteLock::GetWriteLock",
      0x800700AA);
LABEL_16:
    if ( *v7 == 1 )
    {
      ReleaseMutex(*((HANDLE *)this + 1));
      *v7 = 0;
    }
    goto LABEL_18;
  }
  if ( GetLastError() != 298 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      CEventLogger::LogError(
        v12,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
        0xC3u,
        L"CReadWriteLock::GetWriteLock",
        v6);
      goto LABEL_16;
    }
  }
LABEL_18:
  *a2 = *v7;
  if ( v6 != -2147019873 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x140038650  mov     [rsp+arg_8], rbx
0x140038655  mov     [rsp+arg_10], rbp
0x14003865a  push    rsi
0x14003865b  push    rdi
0x14003865c  push    r14
0x14003865e  sub     rsp, 30h
0x140038662  mov     rsi, rcx
0x140038665  mov     [rsp+48h+PreviousCount], 0
0x14003866d  mov     rcx, [rcx+8]; this
0x140038671  mov     r14, rdx
0x140038674  mov     ebp, 8007139Fh
0x140038679  test    rcx, rcx
0x14003867c  jz      loc_140038769
0x140038682  cmp     qword ptr [rsi+10h], 0
0x140038687  jz      loc_140038769
0x14003868d  xor     edi, edi
0x14003868f  lea     rbx, [rsi+4]
0x140038693  cmp     dword ptr [rbx], 1
0x140038696  jz      loc_1400387B7
0x14003869c  xor     edx, edx; dwMilliseconds
0x14003869e  call    cs:__imp_WaitForSingleObject
0x1400386a5  nop     dword ptr [rax+rax+00h]
0x1400386aa  test    eax, eax
0x1400386ac  jnz     loc_140038735
0x1400386b2  mov     rcx, [rsi+10h]; hSemaphore
0x1400386b6  lea     r8, [rsp+48h+PreviousCount]; lpPreviousCount
0x1400386bb  lea     edx, [rdi+1]; lReleaseCount
0x1400386be  mov     dword ptr [rbx], 1
0x1400386c4  call    cs:__imp_ReleaseSemaphore
0x1400386cb  nop     dword ptr [rax+rax+00h]
0x1400386d0  cmp     eax, 1
0x1400386d3  jnz     short loc_1400386EF
0x1400386d5  mov     rcx, [rsi+10h]; hHandle
0x1400386d9  xor     edx, edx; dwMilliseconds
0x1400386db  call    cs:__imp_WaitForSingleObject
0x1400386e2  nop     dword ptr [rax+rax+00h]
0x1400386e7  mov     r9d, 0B8h
0x1400386ed  jmp     short loc_14003873B
0x1400386ef  call    cs:__imp_GetLastError
0x1400386f6  nop     dword ptr [rax+rax+00h]
0x1400386fb  cmp     eax, 12Ah
0x140038700  jz      loc_1400387B7
0x140038706  call    cs:__imp_GetLastError
0x14003870d  nop     dword ptr [rax+rax+00h]
0x140038712  mov     edi, eax
0x140038714  test    eax, eax
0x140038716  jle     short loc_140038721
0x140038718  movzx   edi, ax
0x14003871b  or      edi, 80070000h
0x140038721  test    edi, edi
0x140038723  jns     loc_1400387B7
0x140038729  mov     [rsp+48h+var_20], edi
0x14003872d  mov     r9d, 0C3h
0x140038733  jmp     short loc_140038748
0x140038735  mov     r9d, 0A9h; unsigned int
0x14003873b  mov     [rsp+48h+var_20], 800700AAh; unsigned int
0x140038743  mov     edi, 800700AAh
0x140038748  lea     rax, aCreadwritelock_2; "CReadWriteLock::GetWriteLock"
0x14003874f  lea     r8, aBaseDiagnosisR_20; "base\\diagnosis\\ra\\racommon\\src\\rea"...
0x140038756  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x14003875b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038762  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038767  jmp     short loc_14003879C
0x140038769  lea     rax, aCreadwritelock_2; "CReadWriteLock::GetWriteLock"
0x140038770  mov     [rsp+48h+var_20], 8007139Fh; unsigned int
0x140038778  mov     r9d, 95h; unsigned int
0x14003877e  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x140038783  lea     r8, aBaseDiagnosisR_20; "base\\diagnosis\\ra\\racommon\\src\\rea"...
0x14003878a  mov     edi, ebp
0x14003878c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038793  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038798  lea     rbx, [rsi+4]
0x14003879c  cmp     dword ptr [rbx], 1
0x14003879f  jnz     short loc_1400387B7
0x1400387a1  mov     rcx, [rsi+8]; hMutex
0x1400387a5  call    cs:__imp_ReleaseMutex
0x1400387ac  nop     dword ptr [rax+rax+00h]
0x1400387b1  mov     dword ptr [rbx], 0
0x1400387b7  mov     ecx, [rbx]
0x1400387b9  mov     rbx, [rsp+48h+arg_8]
0x1400387be  mov     [r14], ecx
0x1400387c1  xor     ecx, ecx
0x1400387c3  cmp     edi, ebp
0x1400387c5  cmovnz  ebp, ecx
0x1400387c8  mov     eax, ebp
0x1400387ca  mov     rbp, [rsp+48h+arg_10]
0x1400387cf  add     rsp, 30h
0x1400387d3  pop     r14
0x1400387d5  pop     rdi
0x1400387d6  pop     rsi
0x1400387d7  retn
```
