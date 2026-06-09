# UlCancelConsumerCallback

- ea: `0x1400b20c0`
- end: `0x1400b21c9`
- name: `UlCancelConsumerCallback`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140087dc0`

## callees

- `0x1400b20c0`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b212e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b2177`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b212e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b2177`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b210a`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b210a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b213a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2183`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b213a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b2183`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b20f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b20f7`

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
0x1400b20c0  mov     [rsp+arg_0], rbx
0x1400b20c5  push    rdi
0x1400b20c6  sub     rsp, 20h
0x1400b20ca  mov     rdi, rcx
0x1400b20cd  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400b20d4  jz      short loc_1400B20EF
0x1400b20d6  mov     edx, 72h ; 'r'
0x1400b20db  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400b20e2  mov     ecx, 408h
0x1400b20e7  mov     r9, rdi
0x1400b20ea  call    WPP_SF_q
0x1400b20ef  mov     rax, [rdi+10h]
0x1400b20f3  mov     rbx, [rax+8]
0x1400b20f7  call    cs:__imp_KeEnterCriticalRegion
0x1400b20fe  nop     dword ptr [rax+rax+00h]
0x1400b2103  mov     rcx, [rbx+118h]
0x1400b210a  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400b2111  nop     dword ptr [rax+rax+00h]
0x1400b2116  xor     edx, edx
0x1400b2118  cmp     [rdi+20h], dl
0x1400b211b  jz      short loc_1400B2148
0x1400b211d  mov     rax, [rdi+10h]
0x1400b2121  mov     bl, dl
0x1400b2123  mov     rcx, [rax+8]
0x1400b2127  mov     rcx, [rcx+118h]
0x1400b212e  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b2135  nop     dword ptr [rax+rax+00h]
0x1400b213a  call    cs:__imp_KeLeaveCriticalRegion
0x1400b2141  nop     dword ptr [rax+rax+00h]
0x1400b2146  jmp     short loc_1400B2191
0x1400b2148  mov     rax, [rdi]
0x1400b214b  cmp     [rax+8], rdi
0x1400b214f  jnz     short loc_1400B21C2
0x1400b2151  mov     rcx, [rdi+8]
0x1400b2155  cmp     [rcx], rdi
0x1400b2158  jnz     short loc_1400B21C2
0x1400b215a  mov     [rcx], rax
0x1400b215d  mov     [rax+8], rcx
0x1400b2161  mov     [rdi], rdx
0x1400b2164  mov     [rdi+8], rdx
0x1400b2168  mov     rax, [rdi+10h]
0x1400b216c  mov     rcx, [rax+8]
0x1400b2170  mov     rcx, [rcx+118h]
0x1400b2177  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b217e  nop     dword ptr [rax+rax+00h]
0x1400b2183  call    cs:__imp_KeLeaveCriticalRegion
0x1400b218a  nop     dword ptr [rax+rax+00h]
0x1400b218f  mov     bl, 1
0x1400b2191  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400b2198  jz      short loc_1400B21B4
0x1400b219a  movzx   r9d, bl
0x1400b219e  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400b21a5  mov     edx, 73h ; 's'
0x1400b21aa  mov     ecx, 408h
0x1400b21af  call    WPP_SF_d
0x1400b21b4  mov     al, bl
0x1400b21b6  mov     rbx, [rsp+28h+arg_0]
0x1400b21bb  add     rsp, 20h
0x1400b21bf  pop     rdi
0x1400b21c0  retn
0x1400b21c2  mov     ecx, 3
0x1400b21c7  int     29h; Win8: RtlFailFast(ecx)
```
