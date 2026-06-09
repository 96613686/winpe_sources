# CThreadContext::RevertPrivileges(void)

- ea: `0x1800061a4`
- end: `0x180006242`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006de0`
- `0x18000a2d8`
- `0x18000a7c4`
- `0x18000ccec`

## callees

- `0x1800061a4`
- `0x180007c60`
- `0x18000a7a0`
- `0x18000a848`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180006231`
- `ntdll!RtlAdjustPrivilege` at `0x180006231`

## pseudocode

```c
__int64 __fastcall CThreadContext::RevertPrivileges(CThreadContext *this)
{
  int v1; // eax
  unsigned int v2; // esi
  __int64 v5; // rdi
  void *v6; // rcx
  NTSTATUS v7; // eax
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 6);
  v2 = 0;
  OldValue = 0;
  if ( v1 )
  {
    v5 = 0;
    do
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v5) )
      {
        v7 = RtlAdjustPrivilege(*(_DWORD *)(*((_QWORD *)this + 4) + 4 * v5), 0, 1u, &OldValue);
        v2 = ResultFromWin32FromStatus(v7);
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < *((_DWORD *)this + 6) );
    ResultFromHeapFree(*((void **)this + 4));
    v6 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 4) = 0;
    ResultFromHeapFree(v6);
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  CThreadContext::RevertToSelf(this);
  return v2;
}

```

## disassembly

```asm
0x1800061a4  mov     [rsp+arg_8], rbx
0x1800061a9  mov     [rsp+arg_10], rsi
0x1800061ae  push    rdi
0x1800061af  sub     rsp, 20h
0x1800061b3  mov     eax, [rcx+18h]
0x1800061b6  xor     esi, esi
0x1800061b8  mov     [rsp+28h+OldValue], 0
0x1800061bd  mov     rbx, rcx
0x1800061c0  test    eax, eax
0x1800061c2  jnz     short loc_1800061DE
0x1800061c4  mov     rcx, rbx; this
0x1800061c7  call    ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x1800061cc  mov     rbx, [rsp+28h+arg_8]
0x1800061d1  mov     eax, esi
0x1800061d3  mov     rsi, [rsp+28h+arg_10]
0x1800061d8  add     rsp, 20h
0x1800061dc  pop     rdi
0x1800061dd  retn
0x1800061de  xor     edi, edi
0x1800061e0  test    eax, eax
0x1800061e2  jz      short loc_1800061F5
0x1800061e4  mov     rax, [rbx+28h]
0x1800061e8  cmp     dword ptr [rax+rdi*4], 0
0x1800061ec  jnz     short loc_180006220
0x1800061ee  inc     edi
0x1800061f0  cmp     edi, [rbx+18h]
0x1800061f3  jb      short loc_1800061E4
0x1800061f5  mov     rcx, [rbx+20h]; lpMem
0x1800061f9  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800061fe  mov     rcx, [rbx+28h]; lpMem
0x180006202  mov     qword ptr [rbx+20h], 0
0x18000620a  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000620f  mov     qword ptr [rbx+28h], 0
0x180006217  mov     dword ptr [rbx+18h], 0
0x18000621e  jmp     short loc_1800061C4
0x180006220  mov     rcx, [rbx+20h]
0x180006224  lea     r9, [rsp+28h+OldValue]; OldValue
0x180006229  mov     r8b, 1; ForThread
0x18000622c  xor     edx, edx; NewValue
0x18000622e  mov     ecx, [rcx+rdi*4]; Privilege
0x180006231  call    cs:__imp_RtlAdjustPrivilege
0x180006237  mov     ecx, eax; int
0x180006239  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000623e  mov     esi, eax
0x180006240  jmp     short loc_1800061EE
```
