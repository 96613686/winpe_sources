# UlCancelConsumerCallback

- ea: `0x1400b21a0`
- end: `0x1400b22a9`
- name: `UlCancelConsumerCallback`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140087de0`

## callees

- `0x1400b21a0`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b220e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b2257`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b220e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b2257`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b21ea`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b21ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b221a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2263`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b221a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2263`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b21d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b21d7`

## pseudocode

```c
unsigned __int8 __fastcall UlCancelConsumerCallback(__int64 *a1)
{
  __int64 v2; // rbx
  unsigned __int8 v3; // bl
  __int64 *v4; // rax
  __int64 **v5; // rcx

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 114, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1);
  v2 = *(_QWORD *)(a1[2] + 8);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v2 + 280));
  if ( *((_BYTE *)a1 + 32) )
  {
    v3 = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1[2] + 8) + 280LL));
    KeLeaveCriticalRegion();
  }
  else
  {
    v4 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v5 = (__int64 **)a1[1], *v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    v4[1] = (__int64)v5;
    *a1 = 0;
    a1[1] = 0;
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1[2] + 8) + 280LL));
    KeLeaveCriticalRegion();
    v3 = 1;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 115, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1400b21a0  mov     [rsp+arg_0], rbx
0x1400b21a5  push    rdi
0x1400b21a6  sub     rsp, 20h
0x1400b21aa  mov     rdi, rcx
0x1400b21ad  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400b21b4  jz      short loc_1400B21CF
0x1400b21b6  mov     edx, 72h ; 'r'
0x1400b21bb  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400b21c2  mov     ecx, 408h
0x1400b21c7  mov     r9, rdi
0x1400b21ca  call    WPP_SF_q
0x1400b21cf  mov     rax, [rdi+10h]
0x1400b21d3  mov     rbx, [rax+8]
0x1400b21d7  call    cs:__imp_KeEnterCriticalRegion
0x1400b21de  nop     dword ptr [rax+rax+00h]
0x1400b21e3  mov     rcx, [rbx+118h]
0x1400b21ea  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400b21f1  nop     dword ptr [rax+rax+00h]
0x1400b21f6  xor     edx, edx
0x1400b21f8  cmp     [rdi+20h], dl
0x1400b21fb  jz      short loc_1400B2228
0x1400b21fd  mov     rax, [rdi+10h]
0x1400b2201  mov     bl, dl
0x1400b2203  mov     rcx, [rax+8]
0x1400b2207  mov     rcx, [rcx+118h]
0x1400b220e  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b2215  nop     dword ptr [rax+rax+00h]
0x1400b221a  call    cs:__imp_KeLeaveCriticalRegion
0x1400b2221  nop     dword ptr [rax+rax+00h]
0x1400b2226  jmp     short loc_1400B2271
0x1400b2228  mov     rax, [rdi]
0x1400b222b  cmp     [rax+8], rdi
0x1400b222f  jnz     short loc_1400B22A2
0x1400b2231  mov     rcx, [rdi+8]
0x1400b2235  cmp     [rcx], rdi
0x1400b2238  jnz     short loc_1400B22A2
0x1400b223a  mov     [rcx], rax
0x1400b223d  mov     [rax+8], rcx
0x1400b2241  mov     [rdi], rdx
0x1400b2244  mov     [rdi+8], rdx
0x1400b2248  mov     rax, [rdi+10h]
0x1400b224c  mov     rcx, [rax+8]
0x1400b2250  mov     rcx, [rcx+118h]
0x1400b2257  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b225e  nop     dword ptr [rax+rax+00h]
0x1400b2263  call    cs:__imp_KeLeaveCriticalRegion
0x1400b226a  nop     dword ptr [rax+rax+00h]
0x1400b226f  mov     bl, 1
0x1400b2271  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400b2278  jz      short loc_1400B2294
0x1400b227a  movzx   r9d, bl
0x1400b227e  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400b2285  mov     edx, 73h ; 's'
0x1400b228a  mov     ecx, 408h
0x1400b228f  call    WPP_SF_d
0x1400b2294  mov     al, bl
0x1400b2296  mov     rbx, [rsp+28h+arg_0]
0x1400b229b  add     rsp, 20h
0x1400b229f  pop     rdi
0x1400b22a0  retn
0x1400b22a2  mov     ecx, 3
0x1400b22a7  int     29h; Win8: RtlFailFast(ecx)
```
