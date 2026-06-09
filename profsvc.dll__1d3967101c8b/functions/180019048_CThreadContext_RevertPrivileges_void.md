# CThreadContext::RevertPrivileges(void)

- ea: `0x180019048`
- end: `0x1800190ed`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017bdc`
- `0x180018370`
- `0x1800189c0`
- `0x180018bcc`
- `0x180018c40`

## callees

- `0x180004170`
- `0x180019048`
- `0x180024e34`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800190ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800190ce`
- `ntdll!RtlAdjustPrivilege` at `0x180019089`
- `ntdll!RtlAdjustPrivilege` at `0x180019089`

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
0x180019048  mov     [rsp+arg_8], rbx
0x18001904d  mov     [rsp+arg_10], rsi
0x180019052  push    rdi
0x180019053  sub     rsp, 20h
0x180019057  mov     eax, [rcx+18h]
0x18001905a  xor     esi, esi
0x18001905c  mov     [rsp+28h+OldValue], 0
0x180019061  mov     rbx, rcx
0x180019064  test    eax, eax
0x180019066  jz      short loc_1800190C8
0x180019068  xor     edi, edi
0x18001906a  test    eax, eax
0x18001906c  jz      short loc_18001909F
0x18001906e  mov     rax, [rbx+28h]
0x180019072  cmp     dword ptr [rax+rdi*4], 0
0x180019076  jz      short loc_180019098
0x180019078  mov     rcx, [rbx+20h]
0x18001907c  lea     r9, [rsp+28h+OldValue]; OldValue
0x180019081  mov     r8b, 1; ForThread
0x180019084  xor     edx, edx; NewValue
0x180019086  mov     ecx, [rcx+rdi*4]; Privilege
0x180019089  call    cs:__imp_RtlAdjustPrivilege
0x18001908f  mov     ecx, eax; int
0x180019091  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180019096  mov     esi, eax
0x180019098  inc     edi
0x18001909a  cmp     edi, [rbx+18h]
0x18001909d  jb      short loc_18001906E
0x18001909f  mov     rcx, [rbx+20h]; lpMem
0x1800190a3  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800190a8  mov     rcx, [rbx+28h]; lpMem
0x1800190ac  mov     qword ptr [rbx+20h], 0
0x1800190b4  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800190b9  mov     qword ptr [rbx+28h], 0
0x1800190c1  mov     dword ptr [rbx+18h], 0
0x1800190c8  cmp     dword ptr [rbx+10h], 0
0x1800190cc  jz      short loc_1800190DB
0x1800190ce  call    cs:__imp_RevertToSelf
0x1800190d4  mov     dword ptr [rbx+10h], 0
0x1800190db  mov     rbx, [rsp+28h+arg_8]
0x1800190e0  mov     eax, esi
0x1800190e2  mov     rsi, [rsp+28h+arg_10]
0x1800190e7  add     rsp, 20h
0x1800190eb  pop     rdi
0x1800190ec  retn
```
