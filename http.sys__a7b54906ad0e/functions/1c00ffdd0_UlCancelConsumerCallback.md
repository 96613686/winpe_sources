# UlCancelConsumerCallback

- ea: `0x1c00ffdd0`
- end: `0x1c00ffeda`
- name: `UlCancelConsumerCallback`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1c00c7e80`

## callees

- `0x1c008f374`
- `0x1c008f680`
- `0x1c00ffdd0`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ffe3c`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ffe85`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ffe3c`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ffe85`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ffe1b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ffe1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ffe48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ffe91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ffe48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ffe91`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ffe08`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ffe08`

## pseudocode

```c
char __fastcall UlCancelConsumerCallback(__int64 *a1)
{
  char v2; // si
  __int64 v3; // rbx
  __int64 *v4; // rax
  __int64 **v5; // rcx

  v2 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(110, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1);
  v3 = *(_QWORD *)(a1[2] + 8);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v3 + 280));
  if ( *((_BYTE *)a1 + 32) )
  {
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
    v2 = 1;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(111, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x1c00ffdd0  mov     [rsp+arg_0], rbx
0x1c00ffdd5  mov     [rsp+arg_8], rsi
0x1c00ffdda  push    rdi
0x1c00ffddb  sub     rsp, 20h
0x1c00ffddf  mov     rdi, rcx
0x1c00ffde2  xor     esi, esi
0x1c00ffde4  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00ffdea  test    al, al
0x1c00ffdec  jns     short loc_1C00FFE00
0x1c00ffdee  lea     ecx, [rsi+6Eh]
0x1c00ffdf1  mov     r8, rdi
0x1c00ffdf4  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ffdfb  call    WPP_SF_q
0x1c00ffe00  mov     rax, [rdi+10h]
0x1c00ffe04  mov     rbx, [rax+8]
0x1c00ffe08  call    cs:__imp_KeEnterCriticalRegion
0x1c00ffe0f  nop     dword ptr [rax+rax+00h]
0x1c00ffe14  mov     rcx, [rbx+118h]
0x1c00ffe1b  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00ffe22  nop     dword ptr [rax+rax+00h]
0x1c00ffe27  cmp     [rdi+20h], sil
0x1c00ffe2b  jz      short loc_1C00FFE56
0x1c00ffe2d  mov     rax, [rdi+10h]
0x1c00ffe31  mov     rcx, [rax+8]
0x1c00ffe35  mov     rcx, [rcx+118h]
0x1c00ffe3c  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00ffe43  nop     dword ptr [rax+rax+00h]
0x1c00ffe48  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ffe4f  nop     dword ptr [rax+rax+00h]
0x1c00ffe54  jmp     short loc_1C00FFEA0
0x1c00ffe56  mov     rax, [rdi]
0x1c00ffe59  cmp     [rax+8], rdi
0x1c00ffe5d  jnz     short loc_1C00FFED3
0x1c00ffe5f  mov     rcx, [rdi+8]
0x1c00ffe63  cmp     [rcx], rdi
0x1c00ffe66  jnz     short loc_1C00FFED3
0x1c00ffe68  mov     [rcx], rax
0x1c00ffe6b  mov     [rax+8], rcx
0x1c00ffe6f  mov     [rdi], rsi
0x1c00ffe72  mov     [rdi+8], rsi
0x1c00ffe76  mov     rax, [rdi+10h]
0x1c00ffe7a  mov     rcx, [rax+8]
0x1c00ffe7e  mov     rcx, [rcx+118h]
0x1c00ffe85  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00ffe8c  nop     dword ptr [rax+rax+00h]
0x1c00ffe91  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ffe98  nop     dword ptr [rax+rax+00h]
0x1c00ffe9d  mov     sil, 1
0x1c00ffea0  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00ffea6  test    cl, cl
0x1c00ffea8  jns     short loc_1C00FFEBF
0x1c00ffeaa  movzx   r8d, sil
0x1c00ffeae  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00ffeb5  mov     ecx, 6Fh ; 'o'
0x1c00ffeba  call    WPP_SF_D
0x1c00ffebf  mov     rbx, [rsp+28h+arg_0]
0x1c00ffec4  mov     al, sil
0x1c00ffec7  mov     rsi, [rsp+28h+arg_8]
0x1c00ffecc  add     rsp, 20h
0x1c00ffed0  pop     rdi
0x1c00ffed1  retn
0x1c00ffed3  mov     ecx, 3
0x1c00ffed8  int     29h; Win8: RtlFailFast(ecx)
```
