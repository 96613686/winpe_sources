# UlStartConfigGroupFacet

- ea: `0x1c00d88e0`
- end: `0x1c00d89f1`
- name: `UlStartConfigGroupFacet`
- size: `273`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f680`
- `0x1c00d88e0`
- `0x1c00d9388`

## import_xrefs

- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1c00d8948`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x1c00d8948`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x1c00d8970`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x1c00d8970`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d8918`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d8918`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd90e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd930`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd90e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd930`

## pseudocode

```c
__int64 __fastcall UlStartConfigGroupFacet(_QWORD *a1)
{
  _DWORD *PoolWithTagPriority; // rax
  _DWORD *v3; // rbx
  BOOLEAN IsThisAnNtAsSystem; // al
  __int64 v5; // rdx
  int v6; // edi
  __int64 CacheAwarePushLock; // rax
  PVOID v8; // rax
  PVOID P; // [rsp+38h] [rbp+10h] BYREF

  P = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_q(94, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a1);
  PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, 0x70u, 0x48436C55u, LowPoolPriority);
  v3 = PoolWithTagPriority;
  if ( PoolWithTagPriority )
  {
    memset(PoolWithTagPriority + 2, 0, 0x68u);
    *v3 = 1212378197;
    v3[1] = 10;
    IsThisAnNtAsSystem = MmIsThisAnNtAsSystem();
    v6 = UlCGCreateHashTable(IsThisAnNtAsSystem != 0 ? 64 : 2, v5, &P);
    if ( v6 >= 0 )
    {
      CacheAwarePushLock = ExAllocateCacheAwarePushLock(0);
      a1[170] = CacheAwarePushLock;
      if ( CacheAwarePushLock )
      {
        a1[164] = v3;
        a1[168] = a1 + 167;
        v6 = 0;
        a1[167] = a1 + 167;
        v3 = 0;
        v8 = P;
        P = 0;
        a1[169] = v8;
      }
      else
      {
        v6 = -1073741670;
      }
    }
  }
  else
  {
    v6 = -1073741801;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( v3 )
  {
    *v3 = 1751338101;
    ExFreePoolWithTag(v3, 0);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(95, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c00d88e0  mov     [rsp+arg_0], rbx
0x1c00d88e5  mov     [rsp+arg_10], rsi
0x1c00d88ea  push    rdi
0x1c00d88eb  sub     rsp, 20h
0x1c00d88ef  and     [rsp+28h+P], 0
0x1c00d88f5  mov     rsi, rcx
0x1c00d88f8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00d88fe  test    al, 8
0x1c00d8900  jnz     loc_1C00FD8E8
0x1c00d8906  xor     r9d, r9d; Priority
0x1c00d8909  mov     edi, 48436C55h
0x1c00d890e  mov     r8d, edi; Tag
0x1c00d8911  lea     edx, [r9+70h]; NumberOfBytes
0x1c00d8915  lea     ecx, [rdx-6Fh]; PoolType
0x1c00d8918  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d891f  nop     dword ptr [rax+rax+00h]
0x1c00d8924  mov     rbx, rax
0x1c00d8927  test    rax, rax
0x1c00d892a  jz      loc_1C00FD902
0x1c00d8930  xor     edx, edx; Val
0x1c00d8932  lea     rcx, [rax+8]; void *
0x1c00d8936  lea     r8d, [rdx+68h]; Size
0x1c00d893a  call    memset
0x1c00d893f  mov     [rbx], edi
0x1c00d8941  mov     dword ptr [rbx+4], 0Ah
0x1c00d8948  call    cs:__imp_MmIsThisAnNtAsSystem
0x1c00d894f  nop     dword ptr [rax+rax+00h]
0x1c00d8954  neg     al
0x1c00d8956  lea     r8, [rsp+28h+P]
0x1c00d895b  sbb     ecx, ecx
0x1c00d895d  and     ecx, 3Eh
0x1c00d8960  add     ecx, 2
0x1c00d8963  call    UlCGCreateHashTable
0x1c00d8968  mov     edi, eax
0x1c00d896a  test    eax, eax
0x1c00d896c  js      short loc_1C00D89B2
0x1c00d896e  xor     ecx, ecx
0x1c00d8970  call    cs:__imp_ExAllocateCacheAwarePushLock
0x1c00d8977  nop     dword ptr [rax+rax+00h]
0x1c00d897c  mov     [rsi+550h], rax
0x1c00d8983  test    rax, rax
0x1c00d8986  jz      short loc_1C00D89EA
0x1c00d8988  lea     rax, [rsi+538h]
0x1c00d898f  mov     [rsi+520h], rbx
0x1c00d8996  mov     [rax+8], rax
0x1c00d899a  xor     edi, edi
0x1c00d899c  mov     [rax], rax
0x1c00d899f  xor     ebx, ebx
0x1c00d89a1  mov     rax, [rsp+28h+P]
0x1c00d89a6  and     [rsp+28h+P], rbx
0x1c00d89ab  mov     [rsi+548h], rax
0x1c00d89b2  mov     rcx, [rsp+28h+P]; P
0x1c00d89b7  test    rcx, rcx
0x1c00d89ba  jnz     loc_1C00FD90C
0x1c00d89c0  test    rbx, rbx
0x1c00d89c3  jnz     loc_1C00FD925
0x1c00d89c9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00d89cf  test    al, 8
0x1c00d89d1  jnz     loc_1C00FD942
0x1c00d89d7  mov     rbx, [rsp+28h+arg_0]
0x1c00d89dc  mov     eax, edi
0x1c00d89de  mov     rsi, [rsp+28h+arg_10]
0x1c00d89e3  add     rsp, 20h
0x1c00d89e7  pop     rdi
0x1c00d89e8  retn
0x1c00d89ea  mov     edi, 0C000009Ah
0x1c00d89ef  jmp     short loc_1C00D89B2
0x1c00fd8e8  mov     ecx, 5Eh ; '^'
0x1c00fd8ed  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00fd8f4  mov     r8, rsi
0x1c00fd8f7  call    WPP_SF_q
0x1c00fd8fc  nop
0x1c00fd8fd  jmp     loc_1C00D8906
0x1c00fd902  mov     edi, 0C0000017h
0x1c00fd907  jmp     loc_1C00D89B2
0x1c00fd90c  xor     edx, edx; Tag
0x1c00fd90e  call    cs:__imp_ExFreePoolWithTag
0x1c00fd915  nop     dword ptr [rax+rax+00h]
0x1c00fd91a  and     [rsp+28h+P], 0
0x1c00fd920  jmp     loc_1C00D89C0
0x1c00fd925  xor     edx, edx; Tag
0x1c00fd927  mov     dword ptr [rbx], 68634C75h
0x1c00fd92d  mov     rcx, rbx; P
0x1c00fd930  call    cs:__imp_ExFreePoolWithTag
0x1c00fd937  nop     dword ptr [rax+rax+00h]
0x1c00fd93c  nop
0x1c00fd93d  jmp     loc_1C00D89C9
0x1c00fd942  mov     ecx, 5Fh ; '_'
0x1c00fd947  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00fd94e  mov     r8d, edi
0x1c00fd951  call    WPP_SF_D
0x1c00fd956  nop
0x1c00fd957  jmp     loc_1C00D89D7
```
