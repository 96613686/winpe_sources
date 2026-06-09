# DeleteHostRoute

- ea: `0x14001f304`
- end: `0x14001f3ff`
- name: `DeleteHostRoute`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400188d0`

## callees

- `0x140004350`
- `0x140004444`
- `0x14001f304`
- `0x14001f408`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001f3d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f3d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f34c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f3c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f34c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f3c8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f322`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f390`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f322`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f390`

## pseudocode

```c
__int64 __fastcall DeleteHostRoute(__int16 *a1)
{
  __int16 v1; // si
  unsigned int v3; // edi
  volatile signed __int32 *RouteIntheList; // rbx
  unsigned int v5; // eax
  __int64 v6; // rdx
  volatile signed __int32 **v7; // rax

  v1 = *a1;
  v3 = 0;
  byte_14000A228 = KeAcquireSpinLockRaiseToDpc(&RouteListLock);
  RouteIntheList = (volatile signed __int32 *)FindRouteIntheList(a1);
  KeReleaseSpinLock(&RouteListLock, byte_14000A228);
  if ( RouteIntheList && _InterlockedExchangeAdd(RouteIntheList + 4, 0xFFFFFFFF) == 1 )
  {
    if ( v1 == 2 )
      v5 = NsiCliDeleteHostRoute(*((unsigned int *)RouteIntheList + 6));
    else
      v5 = NsiCliDeleteHostV6Route(RouteIntheList + 7);
    v3 = v5;
    byte_14000A228 = KeAcquireSpinLockRaiseToDpc(&RouteListLock);
    v6 = *(_QWORD *)RouteIntheList;
    if ( *(volatile signed __int32 **)(*(_QWORD *)RouteIntheList + 8LL) != RouteIntheList
      || (v7 = (volatile signed __int32 **)*((_QWORD *)RouteIntheList + 1), *v7 != RouteIntheList) )
    {
      __fastfail(3u);
    }
    *v7 = (volatile signed __int32 *)v6;
    *(_QWORD *)(v6 + 8) = v7;
    KeReleaseSpinLock(&RouteListLock, byte_14000A228);
    ExFreePoolWithTag((PVOID)RouteIntheList, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x14001f304  mov     [rsp+arg_0], rbx
0x14001f309  mov     [rsp+arg_8], rsi
0x14001f30e  push    rdi
0x14001f30f  sub     rsp, 20h
0x14001f313  movzx   esi, word ptr [rcx]
0x14001f316  mov     rbx, rcx
0x14001f319  lea     rcx, RouteListLock; SpinLock
0x14001f320  xor     edi, edi
0x14001f322  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f329  nop     dword ptr [rax+rax+00h]
0x14001f32e  mov     rcx, rbx
0x14001f331  mov     cs:byte_14000A228, al
0x14001f337  call    FindRouteIntheList
0x14001f33c  mov     dl, cs:byte_14000A228; NewIrql
0x14001f342  lea     rcx, RouteListLock; SpinLock
0x14001f349  mov     rbx, rax
0x14001f34c  call    cs:__imp_KeReleaseSpinLock
0x14001f353  nop     dword ptr [rax+rax+00h]
0x14001f358  test    rbx, rbx
0x14001f35b  jz      loc_14001F3E5
0x14001f361  or      eax, 0FFFFFFFFh
0x14001f364  lock xadd [rbx+10h], eax
0x14001f369  cmp     eax, 1
0x14001f36c  jnz     short loc_14001F3E5
0x14001f36e  cmp     si, 2
0x14001f372  jnz     short loc_14001F37E
0x14001f374  mov     ecx, [rbx+18h]
0x14001f377  call    NsiCliDeleteHostRoute
0x14001f37c  jmp     short loc_14001F387
0x14001f37e  lea     rcx, [rbx+1Ch]
0x14001f382  call    NsiCliDeleteHostV6Route
0x14001f387  lea     rcx, RouteListLock; SpinLock
0x14001f38e  mov     edi, eax
0x14001f390  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f397  nop     dword ptr [rax+rax+00h]
0x14001f39c  mov     cs:byte_14000A228, al
0x14001f3a2  mov     rdx, [rbx]
0x14001f3a5  cmp     [rdx+8], rbx
0x14001f3a9  jnz     short loc_14001F3F8
0x14001f3ab  mov     rax, [rbx+8]
0x14001f3af  cmp     [rax], rbx
0x14001f3b2  jnz     short loc_14001F3F8
0x14001f3b4  mov     [rax], rdx
0x14001f3b7  lea     rcx, RouteListLock; SpinLock
0x14001f3be  mov     [rdx+8], rax
0x14001f3c2  mov     dl, cs:byte_14000A228; NewIrql
0x14001f3c8  call    cs:__imp_KeReleaseSpinLock
0x14001f3cf  nop     dword ptr [rax+rax+00h]
0x14001f3d4  xor     edx, edx; Tag
0x14001f3d6  mov     rcx, rbx; P
0x14001f3d9  call    cs:__imp_ExFreePoolWithTag
0x14001f3e0  nop     dword ptr [rax+rax+00h]
0x14001f3e5  mov     rbx, [rsp+28h+arg_0]
0x14001f3ea  mov     eax, edi
0x14001f3ec  mov     rsi, [rsp+28h+arg_8]
0x14001f3f1  add     rsp, 20h
0x14001f3f5  pop     rdi
0x14001f3f6  retn
0x14001f3f8  mov     ecx, 3
0x14001f3fd  int     29h; Win8: RtlFailFast(ecx)
```
