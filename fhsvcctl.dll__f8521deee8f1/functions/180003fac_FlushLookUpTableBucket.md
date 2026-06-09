# FlushLookUpTableBucket

- ea: `0x180003fac`
- end: `0x1800040c8`
- name: `FlushLookUpTableBucket`
- size: `284`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000444c`
- `0x180004830`

## callees

- `0x180003fac`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180004097`
- `ADVAPI32!EventWriteTransfer` at `0x180004097`
- `KERNEL32!HeapFree` at `0x1800040b2`
- `KERNEL32!HeapFree` at `0x1800040b2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000403a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000403a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003fd2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003fd2`
- `KERNEL32!GetProcessHeap` at `0x1800040a4`
- `KERNEL32!GetProcessHeap` at `0x1800040a4`

## pseudocode

```c
__int64 __fastcall FlushLookUpTableBucket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi
  RTL_SRWLOCK *v5; // rbp
  __int64 v6; // rdi
  unsigned int v7; // esi
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 *v12; // rdx
  REGHANDLE v13; // rbp
  PEVENT_DATA_DESCRIPTOR *v14; // rbx
  int v15; // edx
  __int64 v16; // rcx
  PEVENT_DATA_DESCRIPTOR v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  if ( !*(_QWORD *)(a1 + 8LL * a2) )
    return 0;
  v5 = (RTL_SRWLOCK *)(a1 + 264);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
  v6 = *(_QWORD *)(a1 + 8 * v2);
  *(_QWORD *)(a1 + 8 * v2) = 0;
  v7 = 0;
  v19 = v6;
  if ( v6 )
  {
    v8 = &v19;
    v9 = v6;
    do
    {
      v10 = *(_QWORD *)(v9 + 32);
      *(_QWORD *)(v9 + 32) = 0;
      v8 = (__int64 *)(*v8 + 24);
      v11 = *v8;
      if ( *v8 )
      {
        do
        {
          v12 = (__int64 *)(v11 + 32);
          v11 = *(_QWORD *)(v11 + 32);
        }
        while ( v11 );
      }
      else
      {
        v12 = v8;
      }
      *v12 = v10;
      ++v7;
      v9 = *v8;
    }
    while ( *v8 );
  }
  *(_DWORD *)(a1 + 256) -= v7;
  ReleaseSRWLockExclusive(v5);
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 328) + 32LL);
  while ( v6 )
  {
    v14 = (PEVENT_DATA_DESCRIPTOR *)(v6 + 16);
    v15 = 2;
    if ( (unsigned int)*(unsigned __int8 *)(v6 + 45) + 2 > 2 )
    {
      do
      {
        v16 = v15++;
        (*v14)[v16].Reserved1 = 0;
      }
      while ( v15 < *(unsigned __int8 *)(v6 + 45) + 2 );
    }
    EventWriteTransfer(v13, (PCEVENT_DESCRIPTOR)v6, 0, 0, *(unsigned __int8 *)(v6 + 44), *v14);
    v6 = *(_QWORD *)(v6 + 24);
    v17 = *v14;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
  }
  return v7;
}

```

## disassembly

```asm
0x180003fac  push    rbx
0x180003fae  push    rbp
0x180003faf  push    rsi
0x180003fb0  push    rdi
0x180003fb1  sub     rsp, 38h
0x180003fb5  mov     esi, edx
0x180003fb7  mov     rbx, rcx
0x180003fba  cmp     qword ptr [rcx+rsi*8], 0
0x180003fbf  jnz     short loc_180003FC8
0x180003fc1  xor     eax, eax
0x180003fc3  jmp     loc_1800040BF
0x180003fc8  lea     rbp, [rcx+108h]
0x180003fcf  mov     rcx, rbp; SRWLock
0x180003fd2  call    cs:__imp_AcquireSRWLockExclusive
0x180003fd8  mov     rdi, [rbx+rsi*8]
0x180003fdc  mov     qword ptr [rbx+rsi*8], 0
0x180003fe4  xor     esi, esi
0x180003fe6  mov     [rsp+58h+arg_0], rdi
0x180003feb  test    rdi, rdi
0x180003fee  jz      short loc_180004031
0x180003ff0  lea     rax, [rsp+58h+arg_0]
0x180003ff5  mov     rcx, rdi
0x180003ff8  mov     r8, [rcx+20h]
0x180003ffc  mov     qword ptr [rcx+20h], 0
0x180004004  mov     rax, [rax]
0x180004007  add     rax, 18h
0x18000400b  mov     rcx, [rax]
0x18000400e  test    rcx, rcx
0x180004011  jz      short loc_180004021
0x180004013  lea     rdx, [rcx+20h]
0x180004017  mov     rcx, [rdx]
0x18000401a  test    rcx, rcx
0x18000401d  jnz     short loc_180004013
0x18000401f  jmp     short loc_180004024
0x180004021  mov     rdx, rax
0x180004024  mov     [rdx], r8
0x180004027  inc     esi
0x180004029  mov     rcx, [rax]
0x18000402c  test    rcx, rcx
0x18000402f  jnz     short loc_180003FF8
0x180004031  sub     [rbx+100h], esi
0x180004037  mov     rcx, rbp; SRWLock
0x18000403a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004040  mov     rax, [rbx+148h]
0x180004047  mov     rbp, [rax+20h]
0x18000404b  jmp     short loc_1800040B8
0x18000404d  movzx   eax, byte ptr [rdi+2Dh]
0x180004051  lea     rbx, [rdi+10h]
0x180004055  mov     edx, 2
0x18000405a  add     eax, edx
0x18000405c  cmp     eax, edx
0x18000405e  jbe     short loc_18000407B
0x180004060  mov     rax, [rbx]
0x180004063  movsxd  rcx, edx
0x180004066  inc     edx
0x180004068  add     rcx, rcx
0x18000406b  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180004070  movzx   eax, byte ptr [rdi+2Dh]
0x180004074  add     eax, 2
0x180004077  cmp     edx, eax
0x180004079  jl      short loc_180004060
0x18000407b  movzx   ecx, byte ptr [rdi+2Ch]
0x18000407f  xor     r9d, r9d; RelatedActivityId
0x180004082  mov     rax, [rbx]
0x180004085  xor     r8d, r8d; ActivityId
0x180004088  mov     [rsp+58h+UserData], rax; UserData
0x18000408d  mov     rdx, rdi; EventDescriptor
0x180004090  mov     [rsp+58h+UserDataCount], ecx; UserDataCount
0x180004094  mov     rcx, rbp; RegHandle
0x180004097  call    cs:__imp_EventWriteTransfer
0x18000409d  mov     rdi, [rdi+18h]
0x1800040a1  mov     rbx, [rbx]
0x1800040a4  call    cs:__imp_GetProcessHeap
0x1800040aa  mov     r8, rbx; lpMem
0x1800040ad  xor     edx, edx; dwFlags
0x1800040af  mov     rcx, rax; hHeap
0x1800040b2  call    cs:__imp_HeapFree
0x1800040b8  test    rdi, rdi
0x1800040bb  jnz     short loc_18000404D
0x1800040bd  mov     eax, esi
0x1800040bf  add     rsp, 38h
0x1800040c3  pop     rdi
0x1800040c4  pop     rsi
0x1800040c5  pop     rbp
0x1800040c6  pop     rbx
0x1800040c7  retn
```
