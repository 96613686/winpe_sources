# MemProtectThreadContext::ScanStack(Memory::RecyclerScanMemoryCallback &)

- ea: `0x1801f1624`
- end: `0x1801f17cd`
- name: `?ScanStack@MemProtectThreadContext@@QEAA_KAEAVRecyclerScanMemoryCallback@Memory@@@Z`
- size: `425`
- prototype: `unsigned __int64 __fastcall(MemProtectThreadContext *__hidden this, struct Memory::RecyclerScanMemoryCallback *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801f1558`

## callees

- `0x1801f1624`
- `0x1801f17d4`
- `0x1801f1934`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f166f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f166f`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1801f16b5`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1801f1725`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1801f16b5`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x1801f1725`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f16cd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1703`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f173d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1763`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f16cd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1703`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f173d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f1763`

## pseudocode

```c
char *__fastcall MemProtectThreadContext::ScanStack(LPCVOID *this, struct Memory::RecyclerScanMemoryCallback *a2)
{
  __int64 v4; // rsi
  int v5; // ebx
  unsigned __int64 v6; // rbx
  const void *v7; // rcx
  __int16 Protect; // cx
  PVOID AllocationBase; // rax
  PVOID v10; // rsi
  SIZE_T RegionSize; // rax
  char *v12; // r8
  _BYTE *v13; // rdx
  char *v14; // rbx
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-30h] BYREF

  if ( MemProtectThreadContext::IsLeakedThread((MemProtectThreadContext *)this) )
    return 0;
  v4 = 0;
  if ( *((_DWORD *)this[3] + 13) == 1 )
  {
    v5 = *((_DWORD *)this + 20);
    if ( v5 != GetCurrentThreadId() )
    {
      v6 = ((unsigned __int64)this[33] + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      v7 = (const void *)*((_QWORD *)this[12] + 2);
      this[6] = v7;
      memset(&Buffer, 0, sizeof(Buffer));
      if ( !VirtualQuery(v7, &Buffer, 0x30u) )
        RaiseFailFastException(0, 0, 0);
      Protect = Buffer.Protect;
      if ( (Buffer.Protect & 0x100) != 0 )
      {
        AllocationBase = Buffer.AllocationBase;
        v10 = Buffer.AllocationBase;
        while ( (Protect & 0x100) != 0 )
        {
          RegionSize = Buffer.RegionSize;
          if ( !Buffer.RegionSize )
          {
            RaiseFailFastException(0, 0, 0);
            RegionSize = Buffer.RegionSize;
          }
          this[6] = (char *)this[6] + RegionSize;
          if ( !VirtualQuery(this[6], &Buffer, 0x30u) )
            RaiseFailFastException(0, 0, 0);
          AllocationBase = Buffer.AllocationBase;
          if ( Buffer.AllocationBase != v10 )
            goto LABEL_17;
          Protect = Buffer.Protect;
        }
        if ( AllocationBase == v10 )
          goto LABEL_18;
LABEL_17:
        RaiseFailFastException(0, 0, 0);
      }
LABEL_18:
      v12 = (char *)Buffer.BaseAddress + Buffer.RegionSize;
      this[7] = (char *)Buffer.BaseAddress + Buffer.RegionSize;
      if ( v6 > (unsigned __int64)this[6] && v6 < (unsigned __int64)v12 )
        this[6] = (LPCVOID)v6;
      v4 = 1232;
      Memory::Recycler::ScanMemoryInline<0,0>(*(_QWORD *)a2, this + 14, 1232);
    }
  }
  v13 = this[6];
  v14 = (char *)((_BYTE *)this[7] - v13);
  Memory::Recycler::ScanMemoryInline<0,0>(*(_QWORD *)a2, v13, v14);
  return &v14[v4];
}

```

## disassembly

```asm
0x1801f1624  mov     [rsp-28h+arg_10], rbx
0x1801f1629  mov     [rsp-28h+arg_8], rdx
0x1801f162e  mov     [rsp-28h+arg_0], rcx
0x1801f1633  push    rbp
0x1801f1634  push    rsi
0x1801f1635  push    rdi
0x1801f1636  push    r14
0x1801f1638  push    r15
0x1801f163a  mov     rbp, rsp
0x1801f163d  sub     rsp, 50h
0x1801f1641  mov     rdi, [rbp+arg_0]
0x1801f1645  mov     rcx, rdi; this
0x1801f1648  call    ?IsLeakedThread@MemProtectThreadContext@@QEAA_NXZ; MemProtectThreadContext::IsLeakedThread(void)
0x1801f164d  test    al, al
0x1801f164f  jz      short loc_1801F1658
0x1801f1651  xor     eax, eax
0x1801f1653  jmp     loc_1801F17B8
0x1801f1658  mov     rax, [rdi+18h]
0x1801f165c  xor     esi, esi
0x1801f165e  mov     r14, [rbp+arg_8]
0x1801f1662  cmp     dword ptr [rax+34h], 1
0x1801f1666  jnz     loc_1801F179E
0x1801f166c  mov     ebx, [rdi+50h]
0x1801f166f  call    cs:__imp_GetCurrentThreadId
0x1801f1676  nop     dword ptr [rax+rax+00h]
0x1801f167b  cmp     ebx, eax
0x1801f167d  jz      loc_1801F179E
0x1801f1683  mov     rax, [rdi+60h]
0x1801f1687  lea     r8d, [rsi+30h]; dwLength
0x1801f168b  mov     rbx, [rdi+108h]
0x1801f1692  lea     rdx, [rbp+Buffer]; lpBuffer
0x1801f1696  xorps   xmm0, xmm0
0x1801f1699  add     rbx, 7
0x1801f169d  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1801f16a1  mov     rcx, [rax+10h]; lpAddress
0x1801f16a5  mov     [rdi+30h], rcx
0x1801f16a9  movups  xmmword ptr [rbp+Buffer.BaseAddress], xmm0
0x1801f16ad  movups  xmmword ptr [rbp+Buffer.AllocationProtect], xmm0
0x1801f16b1  movups  xmmword ptr [rbp+Buffer.State], xmm0
0x1801f16b5  call    cs:__imp_VirtualQuery
0x1801f16bc  nop     dword ptr [rax+rax+00h]
0x1801f16c1  test    rax, rax
0x1801f16c4  jnz     short loc_1801F16D9
0x1801f16c6  xor     r8d, r8d; dwFlags
0x1801f16c9  xor     edx, edx; pContextRecord
0x1801f16cb  xor     ecx, ecx; pExceptionRecord
0x1801f16cd  call    cs:__imp_RaiseFailFastException
0x1801f16d4  nop     dword ptr [rax+rax+00h]
0x1801f16d9  mov     ecx, [rbp+Buffer.Protect]
0x1801f16dc  bt      ecx, 8
0x1801f16e0  jnb     loc_1801F176F
0x1801f16e6  mov     rax, [rbp+Buffer.AllocationBase]
0x1801f16ea  mov     rsi, rax
0x1801f16ed  bt      ecx, 8
0x1801f16f1  jnb     short loc_1801F1757
0x1801f16f3  mov     rax, [rbp+Buffer.RegionSize]
0x1801f16f7  test    rax, rax
0x1801f16fa  jnz     short loc_1801F1713
0x1801f16fc  xor     r8d, r8d; dwFlags
0x1801f16ff  xor     edx, edx; pContextRecord
0x1801f1701  xor     ecx, ecx; pExceptionRecord
0x1801f1703  call    cs:__imp_RaiseFailFastException
0x1801f170a  nop     dword ptr [rax+rax+00h]
0x1801f170f  mov     rax, [rbp+Buffer.RegionSize]
0x1801f1713  add     [rdi+30h], rax
0x1801f1717  lea     rdx, [rbp+Buffer]; lpBuffer
0x1801f171b  mov     rcx, [rdi+30h]; lpAddress
0x1801f171f  mov     r8d, 30h ; '0'; dwLength
0x1801f1725  call    cs:__imp_VirtualQuery
0x1801f172c  nop     dword ptr [rax+rax+00h]
0x1801f1731  test    rax, rax
0x1801f1734  jnz     short loc_1801F1749
0x1801f1736  xor     r8d, r8d; dwFlags
0x1801f1739  xor     edx, edx; pContextRecord
0x1801f173b  xor     ecx, ecx; pExceptionRecord
0x1801f173d  call    cs:__imp_RaiseFailFastException
0x1801f1744  nop     dword ptr [rax+rax+00h]
0x1801f1749  mov     rax, [rbp+Buffer.AllocationBase]
0x1801f174d  cmp     rax, rsi
0x1801f1750  jnz     short loc_1801F175C
0x1801f1752  mov     ecx, [rbp+Buffer.Protect]
0x1801f1755  jmp     short loc_1801F16ED
0x1801f1757  cmp     rax, rsi
0x1801f175a  jz      short loc_1801F176F
0x1801f175c  xor     r8d, r8d; dwFlags
0x1801f175f  xor     edx, edx; pContextRecord
0x1801f1761  xor     ecx, ecx; pExceptionRecord
0x1801f1763  call    cs:__imp_RaiseFailFastException
0x1801f176a  nop     dword ptr [rax+rax+00h]
0x1801f176f  mov     r8, [rbp+Buffer.BaseAddress]
0x1801f1773  add     r8, [rbp+Buffer.RegionSize]
0x1801f1777  mov     [rdi+38h], r8
0x1801f177b  cmp     rbx, [rdi+30h]
0x1801f177f  jbe     short loc_1801F178A
0x1801f1781  cmp     rbx, r8
0x1801f1784  jnb     short loc_1801F178A
0x1801f1786  mov     [rdi+30h], rbx
0x1801f178a  mov     rcx, [r14]
0x1801f178d  lea     rdx, [rdi+70h]
0x1801f1791  mov     esi, 4D0h
0x1801f1796  mov     r8d, esi
0x1801f1799  call    ??$ScanMemoryInline@$0A@$0A@@Recycler@Memory@@AEAAXPEAPEAX_K@Z; Memory::Recycler::ScanMemoryInline<0,0>(void * *,unsigned __int64)
0x1801f179e  mov     rdx, [rdi+30h]
0x1801f17a2  mov     rbx, [rdi+38h]
0x1801f17a6  mov     rcx, [r14]
0x1801f17a9  sub     rbx, rdx
0x1801f17ac  mov     r8, rbx
0x1801f17af  call    ??$ScanMemoryInline@$0A@$0A@@Recycler@Memory@@AEAAXPEAPEAX_K@Z; Memory::Recycler::ScanMemoryInline<0,0>(void * *,unsigned __int64)
0x1801f17b4  lea     rax, [rbx+rsi]
0x1801f17b8  mov     rbx, [rsp+50h+arg_10]
0x1801f17c0  add     rsp, 50h
0x1801f17c4  pop     r15
0x1801f17c6  pop     r14
0x1801f17c8  pop     rdi
0x1801f17c9  pop     rsi
0x1801f17ca  pop     rbp
0x1801f17cb  retn
```
