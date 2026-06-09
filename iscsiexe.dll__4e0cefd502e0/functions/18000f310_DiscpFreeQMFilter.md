# DiscpFreeQMFilter

- ea: `0x18000f310`
- end: `0x18000f382`
- name: `DiscpFreeQMFilter`
- size: `114`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800066f0`
- `0x1800112b8`
- `0x180012348`

## callees

- `0x1800068cc`
- `0x18000f310`
- `0x180016b2c`
- `0x180016bb4`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x18000f34b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000f34b`

## pseudocode

```c
__int64 __fastcall DiscpFreeQMFilter(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rdx
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // edi

  v2 = *(unsigned int *)(a1 + 20);
  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(unsigned int *)(a1 + 64);
  if ( (v2 & 4) != 0 )
  {
    DiscpRemoveFilters(v2, v4, v3);
    v5 = DiscpRemovePolicy((GUID *)(a1 + 80));
  }
  else
  {
    v5 = DiscpRemoveFilters(v2, v4, v3);
  }
  v6 = *(_QWORD *)(a1 + 72);
  v7 = v5;
  *(_DWORD *)(a1 + 20) &= 0xFFFFFFF3;
  DiscpFreeMemory(v6);
  *(_DWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    DiscpFreeTargetPortal(a1);
  return v7;
}

```

## disassembly

```asm
0x18000f310  mov     [rsp+arg_0], rbx
0x18000f315  push    rdi
0x18000f316  sub     rsp, 20h
0x18000f31a  mov     rbx, rcx
0x18000f31d  mov     ecx, [rcx+14h]
0x18000f320  mov     r8, [rbx+48h]
0x18000f324  mov     edx, [rbx+40h]
0x18000f327  test    cl, 4
0x18000f32a  jz      short loc_18000F33C
0x18000f32c  call    DiscpRemoveFilters
0x18000f331  lea     rcx, [rbx+50h]; key
0x18000f335  call    DiscpRemovePolicy
0x18000f33a  jmp     short loc_18000F341
0x18000f33c  call    DiscpRemoveFilters
0x18000f341  mov     rcx, [rbx+48h]
0x18000f345  mov     edi, eax
0x18000f347  and     dword ptr [rbx+14h], 0FFFFFFF3h
0x18000f34b  call    cs:__imp_DiscpFreeMemory
0x18000f351  or      eax, 0FFFFFFFFh
0x18000f354  mov     dword ptr [rbx+40h], 0
0x18000f35b  mov     qword ptr [rbx+48h], 0
0x18000f363  lock xadd [rbx+10h], eax
0x18000f368  cmp     eax, 1
0x18000f36b  jnz     short loc_18000F375
0x18000f36d  mov     rcx, rbx
0x18000f370  call    DiscpFreeTargetPortal
0x18000f375  mov     rbx, [rsp+28h+arg_0]
0x18000f37a  mov     eax, edi
0x18000f37c  add     rsp, 20h
0x18000f380  pop     rdi
0x18000f381  retn
```
