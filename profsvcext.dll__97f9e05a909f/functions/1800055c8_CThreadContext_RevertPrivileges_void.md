# CThreadContext::RevertPrivileges(void)

- ea: `0x1800055c8`
- end: `0x18000566d`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003090`
- `0x180005558`
- `0x180009770`
- `0x180009a2c`

## callees

- `0x1800055c8`
- `0x18000f9c8`
- `0x18001044c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000564e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000564e`
- `ntdll!RtlAdjustPrivilege` at `0x180005609`
- `ntdll!RtlAdjustPrivilege` at `0x180005609`

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
0x1800055c8  mov     [rsp+arg_8], rbx
0x1800055cd  mov     [rsp+arg_10], rsi
0x1800055d2  push    rdi
0x1800055d3  sub     rsp, 20h
0x1800055d7  mov     eax, [rcx+18h]
0x1800055da  xor     esi, esi
0x1800055dc  mov     [rsp+28h+OldValue], 0
0x1800055e1  mov     rbx, rcx
0x1800055e4  test    eax, eax
0x1800055e6  jz      short loc_180005648
0x1800055e8  xor     edi, edi
0x1800055ea  test    eax, eax
0x1800055ec  jz      short loc_18000561F
0x1800055ee  mov     rax, [rbx+28h]
0x1800055f2  cmp     dword ptr [rax+rdi*4], 0
0x1800055f6  jz      short loc_180005618
0x1800055f8  mov     rcx, [rbx+20h]
0x1800055fc  lea     r9, [rsp+28h+OldValue]; OldValue
0x180005601  mov     r8b, 1; ForThread
0x180005604  xor     edx, edx; NewValue
0x180005606  mov     ecx, [rcx+rdi*4]; Privilege
0x180005609  call    cs:__imp_RtlAdjustPrivilege
0x18000560f  mov     ecx, eax; int
0x180005611  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180005616  mov     esi, eax
0x180005618  inc     edi
0x18000561a  cmp     edi, [rbx+18h]
0x18000561d  jb      short loc_1800055EE
0x18000561f  mov     rcx, [rbx+20h]; lpMem
0x180005623  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005628  mov     rcx, [rbx+28h]; lpMem
0x18000562c  mov     qword ptr [rbx+20h], 0
0x180005634  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005639  mov     qword ptr [rbx+28h], 0
0x180005641  mov     dword ptr [rbx+18h], 0
0x180005648  cmp     dword ptr [rbx+10h], 0
0x18000564c  jz      short loc_18000565B
0x18000564e  call    cs:__imp_RevertToSelf
0x180005654  mov     dword ptr [rbx+10h], 0
0x18000565b  mov     rbx, [rsp+28h+arg_8]
0x180005660  mov     eax, esi
0x180005662  mov     rsi, [rsp+28h+arg_10]
0x180005667  add     rsp, 20h
0x18000566b  pop     rdi
0x18000566c  retn
```
