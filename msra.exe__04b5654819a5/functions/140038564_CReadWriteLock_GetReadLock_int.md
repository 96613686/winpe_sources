# CReadWriteLock::GetReadLock(int *)

- ea: `0x140038564`
- end: `0x140038648`
- name: `?GetReadLock@CReadWriteLock@@QEAAJPEAH@Z`
- size: `228`
- prototype: `__int64 __fastcall(CReadWriteLock *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002cb94`

## callees

- `0x140034ce4`
- `0x140038564`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x14003861f`
- `KERNEL32!ReleaseMutex` at `0x14003861f`
- `KERNEL32!WaitForSingleObject` at `0x140038591`
- `KERNEL32!WaitForSingleObject` at `0x1400385bc`
- `KERNEL32!WaitForSingleObject` at `0x140038591`
- `KERNEL32!WaitForSingleObject` at `0x1400385bc`

## string_xrefs

- `0x1400385fc`: `CReadWriteLock::GetReadLock`
- `0x140038603`: `base\diagnosis\ra\racommon\src\readwritelock.cpp`

## pseudocode

```c
__int64 __fastcall CReadWriteLock::GetReadLock(CReadWriteLock *this, int *a2)
{
  CReadWriteLock *v3; // rsi
  unsigned int v4; // edi
  CEventLogger *v5; // rcx
  CEventLogger *v6; // rcx

  v3 = this;
  if ( *((_QWORD *)this + 2) && (this = (CReadWriteLock *)*((_QWORD *)this + 1)) != 0 )
  {
    v4 = 0;
    if ( *(_DWORD *)v3 != 1 )
    {
      if ( WaitForSingleObject(this, 0) )
      {
        v4 = -2147024726;
        CEventLogger::LogError(
          v5,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
          0x4Du,
          L"CReadWriteLock::GetReadLock",
          0x800700AA);
      }
      else if ( WaitForSingleObject(*((HANDLE *)v3 + 2), 0) )
      {
        v4 = -2147024726;
        CEventLogger::LogError(
          v6,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
          0x56u,
          L"CReadWriteLock::GetReadLock",
          0x800700AA);
      }
      else
      {
        *(_DWORD *)v3 = 1;
      }
    }
  }
  else
  {
    v4 = -2147019873;
    CEventLogger::LogError(
      this,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
      0x3Eu,
      L"CReadWriteLock::GetReadLock",
      0x8007139F);
  }
  ReleaseMutex(*((HANDLE *)v3 + 1));
  *a2 = *(_DWORD *)v3;
  if ( v4 != -2147019873 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x140038564  push    rbx
0x140038566  push    rsi
0x140038567  push    rdi
0x140038568  push    r14
0x14003856a  sub     rsp, 38h
0x14003856e  cmp     qword ptr [rcx+10h], 0
0x140038573  mov     r14, rdx
0x140038576  mov     rsi, rcx
0x140038579  jz      short loc_1400385E9
0x14003857b  mov     rcx, [rcx+8]; hHandle
0x14003857f  test    rcx, rcx
0x140038582  jz      short loc_1400385E9
0x140038584  xor     edi, edi
0x140038586  cmp     dword ptr [rsi], 1
0x140038589  jz      loc_14003861B
0x14003858f  xor     edx, edx; dwMilliseconds
0x140038591  call    cs:__imp_WaitForSingleObject
0x140038598  nop     dword ptr [rax+rax+00h]
0x14003859d  test    eax, eax
0x14003859f  jz      short loc_1400385B6
0x1400385a1  mov     edi, 800700AAh
0x1400385a6  mov     [rsp+58h+var_30], 800700AAh
0x1400385ae  mov     r9d, 4Dh ; 'M'
0x1400385b4  jmp     short loc_1400385FC
0x1400385b6  mov     rcx, [rsi+10h]; hHandle
0x1400385ba  xor     edx, edx; dwMilliseconds
0x1400385bc  call    cs:__imp_WaitForSingleObject
0x1400385c3  nop     dword ptr [rax+rax+00h]
0x1400385c8  test    eax, eax
0x1400385ca  jz      short loc_1400385E1
0x1400385cc  mov     edi, 800700AAh
0x1400385d1  mov     [rsp+58h+var_30], 800700AAh
0x1400385d9  mov     r9d, 56h ; 'V'
0x1400385df  jmp     short loc_1400385FC
0x1400385e1  mov     dword ptr [rsi], 1
0x1400385e7  jmp     short loc_14003861B
0x1400385e9  mov     edi, 8007139Fh
0x1400385ee  mov     [rsp+58h+var_30], 8007139Fh; unsigned int
0x1400385f6  mov     r9d, 3Eh ; '>'; unsigned int
0x1400385fc  lea     rax, aCreadwritelock_3; "CReadWriteLock::GetReadLock"
0x140038603  lea     r8, aBaseDiagnosisR_20; "base\\diagnosis\\ra\\racommon\\src\\rea"...
0x14003860a  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x14003860f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038616  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003861b  mov     rcx, [rsi+8]; hMutex
0x14003861f  call    cs:__imp_ReleaseMutex
0x140038626  nop     dword ptr [rax+rax+00h]
0x14003862b  mov     ecx, [rsi]
0x14003862d  mov     [r14], ecx
0x140038630  xor     ecx, ecx
0x140038632  cmp     edi, 8007139Fh
0x140038638  cmovnz  edi, ecx
0x14003863b  mov     eax, edi
0x14003863d  add     rsp, 38h
0x140038641  pop     r14
0x140038643  pop     rdi
0x140038644  pop     rsi
0x140038645  pop     rbx
0x140038646  retn
```
