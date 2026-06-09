# DiscpRemoveTarget

- ea: `0x1800079ac`
- end: `0x180007a8e`
- name: `DiscpRemoveTarget`
- size: `226`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002ea0`
- `0x1800076dc`
- `0x180007bb4`

## callees

- `0x1800079ac`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180007a04`
- `ISCSIUM!DiscpFreeMemory` at `0x180007a04`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a11`
- `ntdll!RtlLeaveCriticalSection` at `0x180007a11`
- `ntdll!RtlEnterCriticalSection` at `0x1800079bc`
- `ntdll!RtlEnterCriticalSection` at `0x1800079bc`

## pseudocode

```c
__int64 __fastcall DiscpRemoveTarget(__int64 *a1)
{
  __int64 v2; // rax
  __int64 *v3; // rcx
  __int64 **v4; // rdx
  __int64 **v6; // rcx
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 **v9; // rdx
  __int64 *v10; // rax
  __int64 *v11; // rdx
  __int64 **v12; // rax

  RtlEnterCriticalSection(&DiscpCritSection);
  v2 = *a1;
  *((_DWORD *)a1 + 9) |= 0x80000000;
  if ( !v2 )
  {
    v3 = (__int64 *)a1[2];
    if ( (__int64 *)v3[1] == a1 + 2 )
    {
      v4 = (__int64 **)a1[3];
      if ( *v4 == a1 + 2 )
      {
        *v4 = v3;
        v3[1] = (__int64)v4;
        goto LABEL_5;
      }
    }
LABEL_15:
    __fastfail(3u);
  }
  if ( *(__int64 **)(v2 + 8) != a1 )
    goto LABEL_15;
  v6 = (__int64 **)a1[1];
  if ( *v6 != a1 )
    goto LABEL_15;
  *v6 = (__int64 *)v2;
  *(_QWORD *)(v2 + 8) = v6;
  v7 = a1 + 2;
  v8 = (__int64 *)a1[2];
  if ( v8 != a1 + 2 )
  {
    v9 = (__int64 **)off_180027018[0];
    if ( *(_UNKNOWN ***)off_180027018[0] != &DiscpTargetsList )
      goto LABEL_15;
    v10 = v8 - 2;
    v10[1] = (__int64)off_180027018[0];
    *v10 = (__int64)&DiscpTargetsList;
    *v9 = v10;
    off_180027018[0] = (_UNKNOWN **)v10;
    v11 = (__int64 *)*v7;
    if ( *(__int64 **)(*v7 + 8) != v7 )
      goto LABEL_15;
    v12 = (__int64 **)a1[3];
    if ( *v12 != v7 )
      goto LABEL_15;
    *v12 = v11;
    v11[1] = (__int64)v12;
  }
LABEL_5:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 8, 0xFFFFFFFF) == 1 )
    DiscpFreeMemory(a1);
  RtlLeaveCriticalSection(&DiscpCritSection);
  return 0;
}

```

## disassembly

```asm
0x1800079ac  push    rbx
0x1800079ae  sub     rsp, 20h
0x1800079b2  mov     rbx, rcx
0x1800079b5  lea     rcx, DiscpCritSection; CriticalSection
0x1800079bc  call    cs:__imp_RtlEnterCriticalSection
0x1800079c2  mov     rax, [rbx]
0x1800079c5  bts     dword ptr [rbx+24h], 1Fh
0x1800079ca  test    rax, rax
0x1800079cd  jnz     short loc_180007A1F
0x1800079cf  lea     rax, [rbx+10h]
0x1800079d3  mov     rcx, [rax]
0x1800079d6  cmp     [rcx+8], rax
0x1800079da  jnz     loc_180007A87
0x1800079e0  mov     rdx, [rax+8]
0x1800079e4  cmp     [rdx], rax
0x1800079e7  jnz     loc_180007A87
0x1800079ed  mov     [rdx], rcx
0x1800079f0  mov     [rcx+8], rdx
0x1800079f4  or      eax, 0FFFFFFFFh
0x1800079f7  lock xadd [rbx+20h], eax
0x1800079fc  cmp     eax, 1
0x1800079ff  jnz     short loc_180007A0A
0x180007a01  mov     rcx, rbx
0x180007a04  call    cs:__imp_DiscpFreeMemory
0x180007a0a  lea     rcx, DiscpCritSection; CriticalSection
0x180007a11  call    cs:__imp_RtlLeaveCriticalSection
0x180007a17  xor     eax, eax
0x180007a19  add     rsp, 20h
0x180007a1d  pop     rbx
0x180007a1e  retn
0x180007a1f  cmp     [rax+8], rbx
0x180007a23  jnz     short loc_180007A87
0x180007a25  mov     rcx, [rbx+8]
0x180007a29  cmp     [rcx], rbx
0x180007a2c  jnz     short loc_180007A87
0x180007a2e  mov     [rcx], rax
0x180007a31  mov     [rax+8], rcx
0x180007a35  lea     rcx, [rbx+10h]
0x180007a39  mov     rax, [rcx]
0x180007a3c  cmp     rax, rcx
0x180007a3f  jz      short loc_1800079F4
0x180007a41  mov     rdx, cs:off_180027018
0x180007a48  lea     r8, DiscpTargetsList
0x180007a4f  cmp     [rdx], r8
0x180007a52  jnz     short loc_180007A87
0x180007a54  add     rax, 0FFFFFFFFFFFFFFF0h
0x180007a58  mov     [rax+8], rdx
0x180007a5c  mov     [rax], r8
0x180007a5f  mov     [rdx], rax
0x180007a62  mov     cs:off_180027018, rax
0x180007a69  mov     rdx, [rcx]
0x180007a6c  cmp     [rdx+8], rcx
0x180007a70  jnz     short loc_180007A87
0x180007a72  mov     rax, [rcx+8]
0x180007a76  cmp     [rax], rcx
0x180007a79  jnz     short loc_180007A87
0x180007a7b  mov     [rax], rdx
0x180007a7e  mov     [rdx+8], rax
0x180007a82  jmp     loc_1800079F4
0x180007a87  mov     ecx, 3
0x180007a8c  int     29h; Win8: RtlFailFast(ecx)
```
