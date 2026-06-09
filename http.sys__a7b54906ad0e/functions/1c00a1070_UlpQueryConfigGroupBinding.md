# UlpQueryConfigGroupBinding

- ea: `0x1c00a1070`
- end: `0x1c00a1131`
- name: `UlpQueryConfigGroupBinding`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1c00a0f8c`

## callees

- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c00a1070`
- `0x1c00a1138`
- `0x1c00a8364`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a10df`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00dd40e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a10df`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00dd40e`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a10ad`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a10ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a10eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00dd41a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a10eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00dd41a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a1098`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a1098`

## pseudocode

```c
__int64 __fastcall UlpQueryConfigGroupBinding(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  unsigned int AutoConfigGroup; // edi

  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(142, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  *a2 = 0;
  a2[1] = 0;
  KeEnterCriticalRegion();
  v4 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 280), 0);
  if ( *(_BYTE *)(a1 + 136) && (v5 = *(volatile signed __int32 **)(a1 + 128)) != 0 )
  {
    _InterlockedIncrement(v5 + 1);
    ExReleaseCacheAwarePushLockSharedEx(v4, 0);
    KeLeaveCriticalRegion();
    AutoConfigGroup = UlGetAutoConfigGroup(v5, a2);
    if ( _InterlockedExchangeAdd(v5 + 1, 0xFFFFFFFF) == 1 )
      UlFreeServerSession((PVOID)v5);
  }
  else
  {
    ExReleaseCacheAwarePushLockSharedEx(v4, 0);
    KeLeaveCriticalRegion();
    AutoConfigGroup = -1073741811;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(143, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return AutoConfigGroup;
}

```

## disassembly

```asm
0x1c00a1070  mov     [rsp+arg_8], rbx
0x1c00a1075  push    rdi
0x1c00a1076  sub     rsp, 20h
0x1c00a107a  mov     rdi, rdx
0x1c00a107d  mov     rbx, rcx
0x1c00a1080  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a1086  test    al, al
0x1c00a1088  js      loc_1C00DD3DE
0x1c00a108e  xorps   xmm0, xmm0
0x1c00a1091  movups  xmmword ptr [rdi], xmm0
0x1c00a1094  movups  xmmword ptr [rdi+10h], xmm0
0x1c00a1098  call    cs:__imp_KeEnterCriticalRegion
0x1c00a109f  nop     dword ptr [rax+rax+00h]
0x1c00a10a4  mov     rcx, [rbx+118h]
0x1c00a10ab  xor     edx, edx
0x1c00a10ad  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00a10b4  nop     dword ptr [rax+rax+00h]
0x1c00a10b9  cmp     byte ptr [rbx+88h], 0
0x1c00a10c0  jz      loc_1C00DD409
0x1c00a10c6  mov     rbx, [rbx+80h]
0x1c00a10cd  test    rbx, rbx
0x1c00a10d0  jz      loc_1C00DD409
0x1c00a10d6  lock inc dword ptr [rbx+4]
0x1c00a10da  xor     edx, edx
0x1c00a10dc  mov     rcx, rax
0x1c00a10df  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00a10e6  nop     dword ptr [rax+rax+00h]
0x1c00a10eb  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a10f2  nop     dword ptr [rax+rax+00h]
0x1c00a10f7  mov     rdx, rdi
0x1c00a10fa  mov     rcx, rbx
0x1c00a10fd  call    UlGetAutoConfigGroup
0x1c00a1102  mov     edi, eax
0x1c00a1104  or      edx, 0FFFFFFFFh
0x1c00a1107  lock xadd [rbx+4], edx
0x1c00a110c  cmp     edx, 1
0x1c00a110f  jz      loc_1C00DD3FB
0x1c00a1115  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a111b  test    al, al
0x1c00a111d  js      loc_1C00DD430
0x1c00a1123  mov     rbx, [rsp+28h+arg_8]
0x1c00a1128  mov     eax, edi
0x1c00a112a  add     rsp, 20h
0x1c00a112e  pop     rdi
0x1c00a112f  retn
0x1c00dd3de  mov     ecx, 8Eh
0x1c00dd3e3  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00dd3ea  mov     r9, rdi
0x1c00dd3ed  mov     r8, rbx
0x1c00dd3f0  call    WPP_SF_qq
0x1c00dd3f5  nop
0x1c00dd3f6  jmp     loc_1C00A108E
0x1c00dd3fb  mov     rcx, rbx; P
0x1c00dd3fe  call    UlFreeServerSession
0x1c00dd403  nop
0x1c00dd404  jmp     loc_1C00A1115
0x1c00dd409  xor     edx, edx
0x1c00dd40b  mov     rcx, rax
0x1c00dd40e  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00dd415  nop     dword ptr [rax+rax+00h]
0x1c00dd41a  call    cs:__imp_KeLeaveCriticalRegion
0x1c00dd421  nop     dword ptr [rax+rax+00h]
0x1c00dd426  mov     edi, 0C000000Dh
0x1c00dd42b  jmp     loc_1C00A1115
0x1c00dd430  mov     ecx, 8Fh
0x1c00dd435  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00dd43c  mov     r8d, edi
0x1c00dd43f  call    WPP_SF_D
0x1c00dd444  nop
0x1c00dd445  jmp     loc_1C00A1123
```
