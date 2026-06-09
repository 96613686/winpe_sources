# PsmpEvaluatePolicyAfterGlobalPoolUpdate

- ea: `0x180016bcc`
- end: `0x180016cb8`
- name: `PsmpEvaluatePolicyAfterGlobalPoolUpdate`
- size: `236`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180015050`
- `0x180015710`

## callees

- `0x1800032a0`
- `0x180003660`
- `0x180003700`
- `0x180014a30`
- `0x18001622c`
- `0x180016bcc`
- `0x18002250c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180016bfe`
- `ntdll!RtlReleaseSRWLockShared` at `0x180016c09`
- `ntdll!RtlReleaseSRWLockShared` at `0x180016bfe`
- `ntdll!RtlReleaseSRWLockShared` at `0x180016c09`
- `ntdll!RtlAcquireSRWLockShared` at `0x180016be5`
- `ntdll!RtlAcquireSRWLockShared` at `0x180016be5`

## pseudocode

```c
__int64 PsmpEvaluatePolicyAfterGlobalPoolUpdate()
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 result; // rax
  void *i; // rbx
  __int64 j; // rdx
  __int64 k; // rdx
  __int64 v7; // rcx
  __int64 NextApplication; // rax
  __int64 v9; // rdi
  __int64 NextUserContext; // rsi

  RtlAcquireSRWLockShared(PsmpBackgroundApplicationListLock);
  if ( (__int64 *)PsmpBackgroundApplicationList == &PsmpBackgroundApplicationList )
    return RtlReleaseSRWLockShared(PsmpBackgroundApplicationListLock, v0, v1, v2);
  RtlReleaseSRWLockShared(PsmpBackgroundApplicationListLock, v0, v1, v2);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids);
  result = PsmpGetNextManagerContext(0);
  for ( i = (void *)result; result; i = (void *)result )
  {
    for ( j = 0; ; j = NextUserContext )
    {
      NextUserContext = PsmpGetNextUserContext(i, j);
      if ( !NextUserContext )
        break;
      for ( k = 0; ; k = v9 )
      {
        NextApplication = PsmpGetNextApplication(NextUserContext, k);
        v9 = NextApplication;
        if ( !NextApplication )
          break;
        if ( *(_DWORD *)(NextApplication + 344) == 2 )
        {
          if ( (unsigned __int8)PsmpIsApplicationOverQuota(NextApplication, 2) )
            PsmpTryToResumeQuotaSuspendedApplication(v7, 1);
        }
      }
    }
    result = PsmpGetNextManagerContext(i);
  }
  return result;
}

```

## disassembly

```asm
0x180016bcc  mov     [rsp+arg_0], rbx
0x180016bd1  mov     [rsp+arg_8], rsi
0x180016bd6  push    rdi
0x180016bd7  sub     rsp, 20h
0x180016bdb  lea     rbx, PsmpBackgroundApplicationListLock
0x180016be2  mov     rcx, rbx
0x180016be5  call    cs:__imp_RtlAcquireSRWLockShared
0x180016beb  lea     rax, PsmpBackgroundApplicationList
0x180016bf2  mov     rcx, rbx
0x180016bf5  cmp     cs:PsmpBackgroundApplicationList, rax
0x180016bfc  jnz     short loc_180016C09
0x180016bfe  call    cs:__imp_RtlReleaseSRWLockShared
0x180016c04  jmp     loc_180016CA8
0x180016c09  call    cs:__imp_RtlReleaseSRWLockShared
0x180016c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c16  test    byte ptr [rcx+1Ch], 1
0x180016c1a  jz      short loc_180016C37
0x180016c1c  cmp     byte ptr [rcx+19h], 5
0x180016c20  jb      short loc_180016C37
0x180016c22  mov     rcx, [rcx+10h]
0x180016c26  lea     r8, WPP_c1878895bf8430c1024ddd3cf0a685b6_Traceguids
0x180016c2d  mov     edx, 1Ch
0x180016c32  call    WPP_SF_
0x180016c37  xor     ecx, ecx; P
0x180016c39  call    PsmpGetNextManagerContext
0x180016c3e  mov     rbx, rax
0x180016c41  test    rax, rax
0x180016c44  jz      short loc_180016CA8
0x180016c46  xor     edx, edx
0x180016c48  jmp     short loc_180016C88
0x180016c4a  xor     edx, edx
0x180016c4c  jmp     short loc_180016C75
0x180016c4e  cmp     dword ptr [rdi+158h], 2
0x180016c55  jnz     short loc_180016C72
0x180016c57  mov     edx, 2
0x180016c5c  mov     rcx, rdi
0x180016c5f  call    PsmpIsApplicationOverQuota
0x180016c64  test    al, al
0x180016c66  jz      short loc_180016C72
0x180016c68  mov     edx, 1
0x180016c6d  call    PsmpTryToResumeQuotaSuspendedApplication
0x180016c72  mov     rdx, rdi
0x180016c75  mov     rcx, rsi
0x180016c78  call    PsmpGetNextApplication
0x180016c7d  mov     rdi, rax
0x180016c80  test    rax, rax
0x180016c83  jnz     short loc_180016C4E
0x180016c85  mov     rdx, rsi
0x180016c88  mov     rcx, rbx
0x180016c8b  call    PsmpGetNextUserContext
0x180016c90  mov     rsi, rax
0x180016c93  test    rax, rax
0x180016c96  jnz     short loc_180016C4A
0x180016c98  mov     rcx, rbx; P
0x180016c9b  call    PsmpGetNextManagerContext
0x180016ca0  mov     rbx, rax
0x180016ca3  test    rax, rax
0x180016ca6  jnz     short loc_180016C46
0x180016ca8  mov     rbx, [rsp+28h+arg_0]
0x180016cad  mov     rsi, [rsp+28h+arg_8]
0x180016cb2  add     rsp, 20h
0x180016cb6  pop     rdi
0x180016cb7  retn
```
