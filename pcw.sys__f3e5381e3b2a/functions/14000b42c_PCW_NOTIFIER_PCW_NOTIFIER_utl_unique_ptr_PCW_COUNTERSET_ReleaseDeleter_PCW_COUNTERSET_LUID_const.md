# PCW_NOTIFIER::PCW_NOTIFIER(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,_LUID const &)

- ea: `0x14000b42c`
- end: `0x14000b4dd`
- name: `??0PCW_NOTIFIER@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@AEBU_LUID@@@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bbb0`

## callees

- `0x14000b42c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b463`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b463`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b4bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b475`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b475`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b4b1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b4b1`

## pseudocode

```c
__int64 __fastcall PCW_NOTIFIER::PCW_NOTIFIER(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 *v3; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 **v7; // rcx

  *(_DWORD *)a1 = 2;
  v3 = (__int64 *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = *a3;
  v5 = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 32) = v5;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v5 + 104, 0);
  v6 = *(_QWORD *)(a1 + 32) + 112LL;
  v7 = *(__int64 ***)(*(_QWORD *)(a1 + 32) + 120LL);
  if ( *v7 != (__int64 *)v6 )
    __fastfail(3u);
  v3[1] = (__int64)v7;
  *v3 = v6;
  *v7 = v3;
  *(_QWORD *)(v6 + 8) = v3;
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 32) + 104LL, 0);
  KeLeaveCriticalRegion();
  return a1;
}

```

## disassembly

```asm
0x14000b42c  mov     [rsp+arg_0], rbx
0x14000b431  mov     [rsp+arg_8], rsi
0x14000b436  push    rdi
0x14000b437  sub     rsp, 20h
0x14000b43b  mov     dword ptr [rcx], 2
0x14000b441  lea     rdi, [rcx+8]
0x14000b445  xorps   xmm0, xmm0
0x14000b448  mov     rsi, rcx
0x14000b44b  movups  xmmword ptr [rdi], xmm0
0x14000b44e  mov     rax, [r8]
0x14000b451  mov     [rcx+18h], rax
0x14000b455  mov     rbx, [rdx]
0x14000b458  mov     qword ptr [rdx], 0
0x14000b45f  mov     [rcx+20h], rbx
0x14000b463  call    cs:__imp_KeEnterCriticalRegion
0x14000b46a  nop     dword ptr [rax+rax+00h]
0x14000b46f  lea     rcx, [rbx+68h]
0x14000b473  xor     edx, edx
0x14000b475  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b47c  nop     dword ptr [rax+rax+00h]
0x14000b481  mov     rax, [rsi+20h]
0x14000b485  add     rax, 70h ; 'p'
0x14000b489  mov     rcx, [rax+8]
0x14000b48d  cmp     [rcx], rax
0x14000b490  jz      short loc_14000B499
0x14000b492  mov     ecx, 3
0x14000b497  int     29h; Win8: RtlFailFast(ecx)
0x14000b499  mov     [rdi+8], rcx
0x14000b49d  xor     edx, edx
0x14000b49f  mov     [rdi], rax
0x14000b4a2  mov     [rcx], rdi
0x14000b4a5  mov     [rax+8], rdi
0x14000b4a9  mov     rcx, [rsi+20h]
0x14000b4ad  add     rcx, 68h ; 'h'
0x14000b4b1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b4b8  nop     dword ptr [rax+rax+00h]
0x14000b4bd  call    cs:__imp_KeLeaveCriticalRegion
0x14000b4c4  nop     dword ptr [rax+rax+00h]
0x14000b4c9  mov     rbx, [rsp+28h+arg_0]
0x14000b4ce  mov     rax, rsi
0x14000b4d1  mov     rsi, [rsp+28h+arg_8]
0x14000b4d6  add     rsp, 20h
0x14000b4da  pop     rdi
0x14000b4db  retn
```
