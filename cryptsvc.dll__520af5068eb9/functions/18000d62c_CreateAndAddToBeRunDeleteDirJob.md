# CreateAndAddToBeRunDeleteDirJob

- ea: `0x18000d62c`
- end: `0x18000d6a0`
- name: `CreateAndAddToBeRunDeleteDirJob`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a620`

## callees

- `0x1800033a0`
- `0x1800068f0`
- `0x18000d62c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d66e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d68f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d66e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d68f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d640`

## pseudocode

```c
void __fastcall CreateAndAddToBeRunDeleteDirJob(__int64 a1)
{
  __int64 v2; // rax
  FILETIME v3; // rbx

  EnterCriticalSection(&JobsCriticalSection);
  if ( *(_QWORD *)(a1 + 88) || (v2 = PkiZeroAlloc(0x28u), (v3 = (FILETIME)v2) == 0) )
  {
    LeaveCriticalSection(&JobsCriticalSection);
  }
  else
  {
    *(_QWORD *)(v2 + 32) = a1;
    *(_QWORD *)(a1 + 88) = v2;
    LeaveCriticalSection(&JobsCriticalSection);
    AddToBeRunJobEx(v3, 6, 0, 0);
  }
}

```

## disassembly

```asm
0x18000d62c  mov     [rsp+arg_0], rbx
0x18000d631  push    rdi
0x18000d632  sub     rsp, 20h
0x18000d636  mov     rdi, rcx
0x18000d639  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d640  call    cs:__imp_EnterCriticalSection
0x18000d646  cmp     qword ptr [rdi+58h], 0
0x18000d64b  jnz     short loc_18000D688
0x18000d64d  mov     ecx, 28h ; '('; uBytes
0x18000d652  call    PkiZeroAlloc
0x18000d657  mov     rbx, rax
0x18000d65a  test    rax, rax
0x18000d65d  jz      short loc_18000D688
0x18000d65f  mov     [rax+20h], rdi
0x18000d663  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d66a  mov     [rdi+58h], rax
0x18000d66e  call    cs:__imp_LeaveCriticalSection
0x18000d674  xor     r9d, r9d
0x18000d677  xor     r8d, r8d
0x18000d67a  mov     rcx, rbx
0x18000d67d  lea     edx, [r9+6]
0x18000d681  call    AddToBeRunJobEx
0x18000d686  jmp     short loc_18000D695
0x18000d688  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d68f  call    cs:__imp_LeaveCriticalSection
0x18000d695  mov     rbx, [rsp+28h+arg_0]
0x18000d69a  add     rsp, 20h
0x18000d69e  pop     rdi
0x18000d69f  retn
```
