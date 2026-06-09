# CReadWriteLock::Initialize(void)

- ea: `0x1400387e0`
- end: `0x1400388cc`
- name: `?Initialize@CReadWriteLock@@QEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400194c8`
- `0x140030460`

## callees

- `0x140034ce4`
- `0x1400387e0`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x14003880e`
- `KERNEL32!CreateMutexW` at `0x14003880e`
- `KERNEL32!CloseHandle` at `0x140038867`
- `KERNEL32!CloseHandle` at `0x140038867`
- `KERNEL32!CreateSemaphoreW` at `0x140038849`
- `KERNEL32!CreateSemaphoreW` at `0x140038849`

## string_xrefs

- `0x1400388a6`: `base\diagnosis\ra\racommon\src\readwritelock.cpp`
- `0x14003889f`: `CReadWriteLock::Initialize`

## pseudocode

```c
__int64 __fastcall CReadWriteLock::Initialize(CReadWriteLock *this)
{
  HANDLE MutexW; // rax
  CEventLogger *v3; // rcx
  unsigned int v4; // edi
  HANDLE SemaphoreW; // rax
  void *v6; // rcx

  if ( *((_QWORD *)this + 1) || *((_QWORD *)this + 2) )
  {
    v4 = -2147418113;
    CEventLogger::LogError(
      this,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
      0x15Du,
      L"CReadWriteLock::Initialize",
      0x8000FFFF);
  }
  else
  {
    MutexW = CreateMutexW(0, 0, L"Local\\RemoteAssistanceNoviceLock");
    *((_QWORD *)this + 1) = MutexW;
    if ( MutexW )
    {
      v4 = 0;
      SemaphoreW = CreateSemaphoreW(0, 64, 64, L"Local\\RemoteAssistanceExpertLock");
      *((_QWORD *)this + 2) = SemaphoreW;
      if ( !SemaphoreW )
      {
        v6 = (void *)*((_QWORD *)this + 1);
        if ( v6 )
        {
          CloseHandle(v6);
          *((_QWORD *)this + 1) = 0;
        }
        v4 = -2147467259;
        CEventLogger::LogError(
          (CEventLogger *)v6,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
          0x17Eu,
          L"CReadWriteLock::Initialize",
          0x80004005);
      }
    }
    else
    {
      v4 = -2147467259;
      CEventLogger::LogError(
        v3,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\readwritelock.cpp",
        0x167u,
        L"CReadWriteLock::Initialize",
        0x80004005);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400387e0  mov     [rsp+arg_0], rbx
0x1400387e5  push    rdi
0x1400387e6  sub     rsp, 30h
0x1400387ea  cmp     qword ptr [rcx+8], 0
0x1400387ef  mov     rbx, rcx
0x1400387f2  jnz     loc_14003888C
0x1400387f8  cmp     qword ptr [rcx+10h], 0
0x1400387fd  jnz     loc_14003888C
0x140038803  lea     r8, aLocalRemoteass; "Local\\RemoteAssistanceNoviceLock"
0x14003880a  xor     edx, edx; bInitialOwner
0x14003880c  xor     ecx, ecx; lpMutexAttributes
0x14003880e  call    cs:__imp_CreateMutexW
0x140038815  nop     dword ptr [rax+rax+00h]
0x14003881a  mov     [rbx+8], rax
0x14003881e  test    rax, rax
0x140038821  jnz     short loc_140038838
0x140038823  mov     edi, 80004005h
0x140038828  mov     [rsp+38h+var_10], 80004005h
0x140038830  mov     r9d, 167h
0x140038836  jmp     short loc_14003889F
0x140038838  xor     edi, edi
0x14003883a  lea     r9, aLocalRemoteass_1; "Local\\RemoteAssistanceExpertLock"
0x140038841  xor     ecx, ecx; lpSemaphoreAttributes
0x140038843  lea     edx, [rdi+40h]; lInitialCount
0x140038846  mov     r8d, edx; lMaximumCount
0x140038849  call    cs:__imp_CreateSemaphoreW
0x140038850  nop     dword ptr [rax+rax+00h]
0x140038855  mov     [rbx+10h], rax
0x140038859  test    rax, rax
0x14003885c  jnz     short loc_1400388BE
0x14003885e  mov     rcx, [rbx+8]; hObject
0x140038862  test    rcx, rcx
0x140038865  jz      short loc_140038877
0x140038867  call    cs:__imp_CloseHandle
0x14003886e  nop     dword ptr [rax+rax+00h]
0x140038873  mov     [rbx+8], rdi
0x140038877  mov     edi, 80004005h
0x14003887c  mov     [rsp+38h+var_10], 80004005h
0x140038884  mov     r9d, 17Eh
0x14003888a  jmp     short loc_14003889F
0x14003888c  mov     edi, 8000FFFFh
0x140038891  mov     [rsp+38h+var_10], 8000FFFFh; unsigned int
0x140038899  mov     r9d, 15Dh; unsigned int
0x14003889f  lea     rax, aCreadwritelock_1; "CReadWriteLock::Initialize"
0x1400388a6  lea     r8, aBaseDiagnosisR_20; "base\\diagnosis\\ra\\racommon\\src\\rea"...
0x1400388ad  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x1400388b2  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400388b9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400388be  mov     rbx, [rsp+38h+arg_0]
0x1400388c3  mov     eax, edi
0x1400388c5  add     rsp, 30h
0x1400388c9  pop     rdi
0x1400388ca  retn
```
