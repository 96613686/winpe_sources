# CThreadContext::RevertPrivileges(void)

- ea: `0x18001c3e4`
- end: `0x18001c496`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001aa1c`
- `0x18001b8b0`
- `0x18001ba30`
- `0x18001c358`

## callees

- `0x180005370`
- `0x18001c3e4`
- `0x18001e658`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001c470`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001c470`
- `ntdll!RtlAdjustPrivilege` at `0x18001c425`
- `ntdll!RtlAdjustPrivilege` at `0x18001c425`

## pseudocode

```c
__int64 __fastcall CThreadContext::RevertPrivileges(CThreadContext *this)
{
  int v1; // eax
  unsigned int v2; // esi
  __int64 v4; // rdi
  NTSTATUS v5; // eax
  void *v6; // rcx
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 6);
  v2 = 0;
  OldValue = 0;
  if ( v1 )
  {
    v4 = 0;
    do
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v4) )
      {
        v5 = RtlAdjustPrivilege(*(_DWORD *)(*((_QWORD *)this + 4) + 4 * v4), 0, 1u, &OldValue);
        v2 = ResultFromWin32FromStatus(v5);
      }
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < *((_DWORD *)this + 6) );
    ResultFromHeapFree(*((void **)this + 4));
    v6 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 4) = 0;
    ResultFromHeapFree(v6);
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  if ( *((_DWORD *)this + 4) )
  {
    RevertToSelf();
    *((_DWORD *)this + 4) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18001c3e4  mov     [rsp+arg_8], rbx
0x18001c3e9  mov     [rsp+arg_10], rsi
0x18001c3ee  push    rdi
0x18001c3ef  sub     rsp, 20h
0x18001c3f3  mov     eax, [rcx+18h]
0x18001c3f6  xor     esi, esi
0x18001c3f8  mov     [rsp+28h+OldValue], 0
0x18001c3fd  mov     rbx, rcx
0x18001c400  test    eax, eax
0x18001c402  jz      short loc_18001C46A
0x18001c404  xor     edi, edi
0x18001c406  test    eax, eax
0x18001c408  jz      short loc_18001C441
0x18001c40a  mov     rax, [rbx+28h]
0x18001c40e  cmp     dword ptr [rax+rdi*4], 0
0x18001c412  jz      short loc_18001C43A
0x18001c414  mov     rcx, [rbx+20h]
0x18001c418  lea     r9, [rsp+28h+OldValue]; OldValue
0x18001c41d  mov     r8b, 1; ForThread
0x18001c420  xor     edx, edx; NewValue
0x18001c422  mov     ecx, [rcx+rdi*4]; Privilege
0x18001c425  call    cs:__imp_RtlAdjustPrivilege
0x18001c42c  nop     dword ptr [rax+rax+00h]
0x18001c431  mov     ecx, eax; int
0x18001c433  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18001c438  mov     esi, eax
0x18001c43a  inc     edi
0x18001c43c  cmp     edi, [rbx+18h]
0x18001c43f  jb      short loc_18001C40A
0x18001c441  mov     rcx, [rbx+20h]; lpMem
0x18001c445  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001c44a  mov     rcx, [rbx+28h]; lpMem
0x18001c44e  mov     qword ptr [rbx+20h], 0
0x18001c456  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001c45b  mov     qword ptr [rbx+28h], 0
0x18001c463  mov     dword ptr [rbx+18h], 0
0x18001c46a  cmp     dword ptr [rbx+10h], 0
0x18001c46e  jz      short loc_18001C483
0x18001c470  call    cs:__imp_RevertToSelf
0x18001c477  nop     dword ptr [rax+rax+00h]
0x18001c47c  mov     dword ptr [rbx+10h], 0
0x18001c483  mov     rbx, [rsp+28h+arg_8]
0x18001c488  mov     eax, esi
0x18001c48a  mov     rsi, [rsp+28h+arg_10]
0x18001c48f  add     rsp, 20h
0x18001c493  pop     rdi
0x18001c494  retn
```
