# DeleteHostRoute

- ea: `0x14001c1a0`
- end: `0x14001c29b`
- name: `DeleteHostRoute`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400133d0`

## callees

- `0x1400070cc`
- `0x1400071c0`
- `0x14001c1a0`
- `0x14001c2a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c275`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c275`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c1e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c264`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c1e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c264`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c1be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c22c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c1be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c22c`

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
  byte_14000B2F8 = KeAcquireSpinLockRaiseToDpc(&RouteListLock);
  RouteIntheList = (volatile signed __int32 *)FindRouteIntheList(a1);
  KeReleaseSpinLock(&RouteListLock, byte_14000B2F8);
  if ( RouteIntheList && _InterlockedExchangeAdd(RouteIntheList + 4, 0xFFFFFFFF) == 1 )
  {
    if ( v1 == 2 )
      v5 = NsiCliDeleteHostRoute(*((unsigned int *)RouteIntheList + 6));
    else
      v5 = NsiCliDeleteHostV6Route(RouteIntheList + 7);
    v3 = v5;
    byte_14000B2F8 = KeAcquireSpinLockRaiseToDpc(&RouteListLock);
    v6 = *(_QWORD *)RouteIntheList;
    if ( *(volatile signed __int32 **)(*(_QWORD *)RouteIntheList + 8LL) != RouteIntheList
      || (v7 = (volatile signed __int32 **)*((_QWORD *)RouteIntheList + 1), *v7 != RouteIntheList) )
    {
      __fastfail(3u);
    }
    *v7 = (volatile signed __int32 *)v6;
    *(_QWORD *)(v6 + 8) = v7;
    KeReleaseSpinLock(&RouteListLock, byte_14000B2F8);
    ExFreePoolWithTag((PVOID)RouteIntheList, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x14001c1a0  mov     [rsp+arg_0], rbx
0x14001c1a5  mov     [rsp+arg_8], rsi
0x14001c1aa  push    rdi
0x14001c1ab  sub     rsp, 20h
0x14001c1af  movzx   esi, word ptr [rcx]
0x14001c1b2  mov     rbx, rcx
0x14001c1b5  lea     rcx, RouteListLock; SpinLock
0x14001c1bc  xor     edi, edi
0x14001c1be  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c1c5  nop     dword ptr [rax+rax+00h]
0x14001c1ca  mov     rcx, rbx
0x14001c1cd  mov     cs:byte_14000B2F8, al
0x14001c1d3  call    FindRouteIntheList
0x14001c1d8  mov     dl, cs:byte_14000B2F8; NewIrql
0x14001c1de  lea     rcx, RouteListLock; SpinLock
0x14001c1e5  mov     rbx, rax
0x14001c1e8  call    cs:__imp_KeReleaseSpinLock
0x14001c1ef  nop     dword ptr [rax+rax+00h]
0x14001c1f4  test    rbx, rbx
0x14001c1f7  jz      loc_14001C281
0x14001c1fd  or      eax, 0FFFFFFFFh
0x14001c200  lock xadd [rbx+10h], eax
0x14001c205  cmp     eax, 1
0x14001c208  jnz     short loc_14001C281
0x14001c20a  cmp     si, 2
0x14001c20e  jnz     short loc_14001C21A
0x14001c210  mov     ecx, [rbx+18h]
0x14001c213  call    NsiCliDeleteHostRoute
0x14001c218  jmp     short loc_14001C223
0x14001c21a  lea     rcx, [rbx+1Ch]
0x14001c21e  call    NsiCliDeleteHostV6Route
0x14001c223  lea     rcx, RouteListLock; SpinLock
0x14001c22a  mov     edi, eax
0x14001c22c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c233  nop     dword ptr [rax+rax+00h]
0x14001c238  mov     cs:byte_14000B2F8, al
0x14001c23e  mov     rdx, [rbx]
0x14001c241  cmp     [rdx+8], rbx
0x14001c245  jnz     short loc_14001C294
0x14001c247  mov     rax, [rbx+8]
0x14001c24b  cmp     [rax], rbx
0x14001c24e  jnz     short loc_14001C294
0x14001c250  mov     [rax], rdx
0x14001c253  lea     rcx, RouteListLock; SpinLock
0x14001c25a  mov     [rdx+8], rax
0x14001c25e  mov     dl, cs:byte_14000B2F8; NewIrql
0x14001c264  call    cs:__imp_KeReleaseSpinLock
0x14001c26b  nop     dword ptr [rax+rax+00h]
0x14001c270  xor     edx, edx; Tag
0x14001c272  mov     rcx, rbx; P
0x14001c275  call    cs:__imp_ExFreePoolWithTag
0x14001c27c  nop     dword ptr [rax+rax+00h]
0x14001c281  mov     rbx, [rsp+28h+arg_0]
0x14001c286  mov     eax, edi
0x14001c288  mov     rsi, [rsp+28h+arg_8]
0x14001c28d  add     rsp, 20h
0x14001c291  pop     rdi
0x14001c292  retn
0x14001c294  mov     ecx, 3
0x14001c299  int     29h; Win8: RtlFailFast(ecx)
```
