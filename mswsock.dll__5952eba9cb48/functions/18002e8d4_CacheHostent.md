# CacheHostent

- ea: `0x18002e8d4`
- end: `0x18002ea39`
- name: `CacheHostent`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002fba0`

## callees

- `0x18002a52c`
- `0x18002a5d4`
- `0x18002e8d4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002e9e3`
- `ntdll!RtlFreeHeap` at `0x18002e9e3`
- `ntdll!NtQuerySystemTime` at `0x18002e900`
- `ntdll!NtQuerySystemTime` at `0x18002e900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e970`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e970`

## pseudocode

```c
void __fastcall CacheHostent(__int64 a1)
{
  unsigned int v2; // esi
  __int64 HeapRoutine; // rax
  _QWORD *v4; // rbx
  PVOID *v5; // rcx
  PVOID *v6; // r8
  PVOID *v7; // rax
  PVOID **v8; // rcx
  _QWORD *v9; // rax
  union _LARGE_INTEGER v10; // [rsp+40h] [rbp+18h] BYREF

  v10.QuadPart = 0;
  if ( *(_DWORD *)&MaxHostentCacheSize )
  {
    NtQuerySystemTime(&v10);
    v2 = BytesInHostent(a1) + 84;
    HeapRoutine = SockAllocateHeapRoutine(SockPrivateHeap, 0, v2);
    v4 = (_QWORD *)HeapRoutine;
    if ( HeapRoutine )
    {
      *(union _LARGE_INTEGER *)(HeapRoutine + 16) = v10;
      *(_QWORD *)(HeapRoutine + 24) = v10.QuadPart + 6000000000LL;
      CopyHostentToBuffer((char *)(HeapRoutine + 32), v2 - 64, a1);
      EnterCriticalSection(&MSWSOCK_SocketLock);
      if ( (unsigned int)CurrentHostentCacheSize >= *(_DWORD *)&MaxHostentCacheSize )
      {
        v5 = (PVOID *)HostentCacheListHead;
        v6 = 0;
        while ( v5 != &HostentCacheListHead )
        {
          if ( !v6 || (__int64)v5[2] < (__int64)v6[2] )
            v6 = v5;
          v5 = (PVOID *)*v5;
        }
        v7 = (PVOID *)*v6;
        if ( *((PVOID **)*v6 + 1) != v6 )
          goto LABEL_17;
        v8 = (PVOID **)v6[1];
        if ( *v8 != v6 )
          goto LABEL_17;
        *v8 = v7;
        v7[1] = v8;
        RtlFreeHeap(SockPrivateHeap, 0, v6);
      }
      else
      {
        ++CurrentHostentCacheSize;
      }
      v9 = HostentCacheListHead;
      if ( *((PVOID **)HostentCacheListHead + 1) == &HostentCacheListHead )
      {
        *v4 = HostentCacheListHead;
        v4[1] = &HostentCacheListHead;
        v9[1] = v4;
        HostentCacheListHead = v4;
        LeaveCriticalSection(&MSWSOCK_SocketLock);
        return;
      }
LABEL_17:
      __fastfail(3u);
    }
  }
}

```

## disassembly

```asm
0x18002e8d4  mov     rax, rsp
0x18002e8d7  mov     [rax+8], rbx
0x18002e8db  mov     [rax+10h], rsi
0x18002e8df  push    rdi
0x18002e8e0  sub     rsp, 20h
0x18002e8e4  cmp     cs:MaxHostentCacheSize, 0
0x18002e8eb  mov     rdi, rcx
0x18002e8ee  mov     qword ptr [rax+18h], 0
0x18002e8f6  jz      loc_18002EA21
0x18002e8fc  lea     rcx, [rax+18h]; SystemTime
0x18002e900  call    cs:__imp_NtQuerySystemTime
0x18002e907  nop     dword ptr [rax+rax+00h]
0x18002e90c  mov     rcx, rdi
0x18002e90f  call    BytesInHostent
0x18002e914  mov     rcx, cs:SockPrivateHeap
0x18002e91b  xor     edx, edx
0x18002e91d  lea     esi, [rax+54h]
0x18002e920  mov     rax, cs:SockAllocateHeapRoutine
0x18002e927  mov     r8d, esi
0x18002e92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e92f  mov     rbx, rax
0x18002e932  test    rax, rax
0x18002e935  jz      loc_18002EA21
0x18002e93b  mov     rcx, [rsp+28h+arg_10]
0x18002e940  mov     r8, rdi
0x18002e943  mov     [rax+10h], rcx
0x18002e947  mov     rax, 165A0BC00h
0x18002e951  mov     rdx, [rsp+28h+arg_10]
0x18002e956  lea     rcx, [rbx+20h]; void *
0x18002e95a  add     rdx, rax
0x18002e95d  mov     [rbx+18h], rdx
0x18002e961  lea     edx, [rsi-40h]
0x18002e964  call    CopyHostentToBuffer
0x18002e969  lea     rcx, MSWSOCK_SocketLock; lpCriticalSection
0x18002e970  call    cs:__imp_EnterCriticalSection
0x18002e977  nop     dword ptr [rax+rax+00h]
0x18002e97c  mov     eax, cs:CurrentHostentCacheSize
0x18002e982  lea     rdi, HostentCacheListHead
0x18002e989  cmp     eax, cs:MaxHostentCacheSize
0x18002e98f  jnb     short loc_18002E99B
0x18002e991  inc     eax
0x18002e993  mov     cs:CurrentHostentCacheSize, eax
0x18002e999  jmp     short loc_18002E9EF
0x18002e99b  mov     rcx, cs:HostentCacheListHead
0x18002e9a2  xor     r8d, r8d
0x18002e9a5  jmp     short loc_18002E9BC
0x18002e9a7  test    r8, r8
0x18002e9aa  jz      short loc_18002E9B6
0x18002e9ac  mov     rax, [r8+10h]
0x18002e9b0  cmp     [rcx+10h], rax
0x18002e9b4  jge     short loc_18002E9B9
0x18002e9b6  mov     r8, rcx; P
0x18002e9b9  mov     rcx, [rcx]
0x18002e9bc  cmp     rcx, rdi
0x18002e9bf  jnz     short loc_18002E9A7
0x18002e9c1  mov     rax, [r8]
0x18002e9c4  cmp     [rax+8], r8
0x18002e9c8  jnz     short loc_18002EA32
0x18002e9ca  mov     rcx, [r8+8]
0x18002e9ce  cmp     [rcx], r8
0x18002e9d1  jnz     short loc_18002EA32
0x18002e9d3  mov     [rcx], rax
0x18002e9d6  xor     edx, edx; Flags
0x18002e9d8  mov     [rax+8], rcx
0x18002e9dc  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002e9e3  call    cs:__imp_RtlFreeHeap
0x18002e9ea  nop     dword ptr [rax+rax+00h]
0x18002e9ef  mov     rax, cs:HostentCacheListHead
0x18002e9f6  cmp     [rax+8], rdi
0x18002e9fa  jnz     short loc_18002EA32
0x18002e9fc  mov     [rbx], rax
0x18002e9ff  lea     rcx, MSWSOCK_SocketLock; lpCriticalSection
0x18002ea06  mov     [rbx+8], rdi
0x18002ea0a  mov     [rax+8], rbx
0x18002ea0e  mov     cs:HostentCacheListHead, rbx
0x18002ea15  call    cs:__imp_LeaveCriticalSection
0x18002ea1c  nop     dword ptr [rax+rax+00h]
0x18002ea21  mov     rbx, [rsp+28h+arg_0]
0x18002ea26  mov     rsi, [rsp+28h+arg_8]
0x18002ea2b  add     rsp, 20h
0x18002ea2f  pop     rdi
0x18002ea30  retn
0x18002ea32  mov     ecx, 3
0x18002ea37  int     29h; Win8: RtlFailFast(ecx)
```
