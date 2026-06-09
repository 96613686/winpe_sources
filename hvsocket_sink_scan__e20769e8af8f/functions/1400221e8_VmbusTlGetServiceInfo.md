# VmbusTlGetServiceInfo

- ea: `0x1400221e8`
- end: `0x1400222a9`
- name: `VmbusTlGetServiceInfo`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14001ac90`

## callees

- `0x140009df0`
- `0x1400221e8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022269`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022269`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002225d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002225d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022201`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022201`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022214`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022214`

## string_xrefs

- `0x140022287`: `VmbusTlGetServiceInfo`

## pseudocode

```c
__int64 __fastcall VmbusTlGetServiceInfo(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v6; // edi
  struct _FAST_MUTEX *v7; // r14
  __int64 **v8; // rbx
  __int64 *i; // rcx

  v6 = -1073741811;
  KeEnterCriticalRegion();
  v7 = (struct _FAST_MUTEX *)(a1 + 16);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  v8 = (__int64 **)(a1 + 360);
  for ( i = *v8; i != (__int64 *)v8; i = (__int64 *)*i )
  {
    if ( i[2] == *a2 && i[3] == a2[1] )
    {
      v6 = 0;
      *(_OWORD *)a3 = *((_OWORD *)i + 1);
      *(_BYTE *)(a3 + 16) = *((_BYTE *)i + 32);
      break;
    }
  }
  ExReleaseFastMutexUnsafe(v7);
  KeLeaveCriticalRegion();
  if ( v6 < 0 && (unsigned int)dword_140013058 > 2 )
    HvsocketTraceGuidError("VmbusTlGetServiceInfo", 1076, (unsigned int)v6, a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400221e8  push    rbx
0x1400221ea  push    rbp
0x1400221eb  push    rsi
0x1400221ec  push    rdi
0x1400221ed  push    r14
0x1400221ef  sub     rsp, 20h
0x1400221f3  mov     rbp, r8
0x1400221f6  mov     rsi, rdx
0x1400221f9  mov     rbx, rcx
0x1400221fc  mov     edi, 0C000000Dh
0x140022201  call    cs:__imp_KeEnterCriticalRegion
0x140022208  nop     dword ptr [rax+rax+00h]
0x14002220d  lea     r14, [rbx+10h]
0x140022211  mov     rcx, r14; FastMutex
0x140022214  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002221b  nop     dword ptr [rax+rax+00h]
0x140022220  add     rbx, 168h
0x140022227  mov     rcx, [rbx]
0x14002222a  jmp     short loc_140022242
0x14002222c  mov     rax, [rcx+10h]
0x140022230  cmp     rax, [rsi]
0x140022233  jnz     short loc_14002223F
0x140022235  mov     rax, [rcx+18h]
0x140022239  cmp     rax, [rsi+8]
0x14002223d  jz      short loc_140022249
0x14002223f  mov     rcx, [rcx]
0x140022242  cmp     rcx, rbx
0x140022245  jnz     short loc_14002222C
0x140022247  jmp     short loc_14002225A
0x140022249  movups  xmm0, xmmword ptr [rcx+10h]
0x14002224d  xor     edi, edi
0x14002224f  movdqu  xmmword ptr [rbp+0], xmm0
0x140022254  mov     al, [rcx+20h]
0x140022257  mov     [rbp+10h], al
0x14002225a  mov     rcx, r14; FastMutex
0x14002225d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022264  nop     dword ptr [rax+rax+00h]
0x140022269  call    cs:__imp_KeLeaveCriticalRegion
0x140022270  nop     dword ptr [rax+rax+00h]
0x140022275  test    edi, edi
0x140022277  jns     short loc_14002229B
0x140022279  mov     ecx, cs:dword_140013058
0x14002227f  cmp     ecx, 2
0x140022282  jbe     short loc_14002229B
0x140022284  mov     r9, rsi
0x140022287  lea     rcx, aVmbustlgetserv; "VmbusTlGetServiceInfo"
0x14002228e  mov     r8d, edi
0x140022291  mov     edx, 434h
0x140022296  call    HvsocketTraceGuidError
0x14002229b  mov     eax, edi
0x14002229d  add     rsp, 20h
0x1400222a1  pop     r14
0x1400222a3  pop     rdi
0x1400222a4  pop     rsi
0x1400222a5  pop     rbp
0x1400222a6  pop     rbx
0x1400222a7  retn
```
