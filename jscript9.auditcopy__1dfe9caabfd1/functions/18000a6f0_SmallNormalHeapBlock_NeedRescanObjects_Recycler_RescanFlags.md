# SmallNormalHeapBlock::NeedRescanObjects(Recycler *,RescanFlags)

- ea: `0x18000a6f0`
- end: `0x18000a7ea`
- name: `?NeedRescanObjects@SmallNormalHeapBlock@@QEAA_NPEAVRecycler@@W4RescanFlags@@@Z`
- size: `250`
- prototype: `bool __fastcall(__int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a02c`
- `0x18025a5ac`
- `0x18025a618`

## callees

- `0x18000a6f0`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18000a7c1`
- `KERNEL32!ResetWriteWatch` at `0x18000a7c1`
- `KERNEL32!GetWriteWatch` at `0x18000a789`
- `KERNEL32!GetWriteWatch` at `0x18000a789`

## pseudocode

```c
bool __fastcall SmallNormalHeapBlock::NeedRescanObjects(__int64 a1, __int64 a2, unsigned int a3)
{
  void *v3; // rdx
  DWORD dwGranularity; // [rsp+30h] [rbp-28h] BYREF
  ULONG_PTR dwCount; // [rsp+38h] [rbp-20h] BYREF
  PVOID Addresses; // [rsp+40h] [rbp-18h] BYREF

  if ( (a3 & 1) != 0 )
  {
    *(_BYTE *)(a1 + 120) = 0;
  }
  else if ( *(_BYTE *)(a1 + 120) )
  {
    if ( (a3 & 2) != 0 )
    {
      ResetWriteWatch(*(LPVOID *)(a1 + 8), 0x1000u);
      return 0;
    }
    return 0;
  }
  if ( !*(_WORD *)(a1 + 80) )
    return 0;
  if ( !*(_BYTE *)(a1 + 25) )
  {
    if ( !*(_BYTE *)(a2 + 12901) )
    {
      v3 = *(void **)(a1 + 8);
      dwCount = 1;
      dwGranularity = 4096;
      Addresses = 0;
      if ( !GetWriteWatch((a3 >> 1) & 1, v3, 0x1000u, &Addresses, &dwCount, &dwGranularity) )
        return dwCount != 0;
      return 1;
    }
    return 0;
  }
  if ( *(_BYTE *)(a2 + 12888) )
    return 0;
  *(_BYTE *)(a1 + 25) = 0;
  return 1;
}

```

## disassembly

```asm
0x18000a6f0  mov     [rsp+arg_10], r8d
0x18000a6f5  mov     [rsp+arg_8], rdx
0x18000a6fa  mov     [rsp+arg_0], rcx
0x18000a6ff  sub     rsp, 58h
0x18000a703  mov     r10d, [rsp+58h+arg_10]
0x18000a708  mov     rcx, [rsp+58h+arg_0]
0x18000a70d  test    r10b, 1
0x18000a711  jz      loc_18000A7A8
0x18000a717  mov     byte ptr [rcx+78h], 0
0x18000a71b  cmp     word ptr [rcx+50h], 0
0x18000a720  jz      loc_18000A7DA
0x18000a726  cmp     byte ptr [rcx+19h], 0
0x18000a72a  mov     rax, [rsp+58h+arg_8]
0x18000a72f  jnz     loc_18000A7D1
0x18000a735  cmp     byte ptr [rax+3265h], 0
0x18000a73c  jnz     loc_18000A7DA
0x18000a742  mov     rdx, [rcx+8]; lpBaseAddress
0x18000a746  lea     rax, [rsp+58h+dwGranularity]
0x18000a74b  mov     [rsp+58h+lpdwGranularity], rax; lpdwGranularity
0x18000a750  lea     r9, [rsp+58h+Addresses]; lpAddresses
0x18000a755  shr     r10d, 1
0x18000a758  lea     rax, [rsp+58h+dwCount]
0x18000a75d  and     r10d, 1
0x18000a761  mov     [rsp+58h+lpdwCount], rax; lpdwCount
0x18000a766  mov     ecx, r10d; dwFlags
0x18000a769  mov     [rsp+58h+dwCount], 1
0x18000a772  mov     r8d, 1000h; dwRegionSize
0x18000a778  mov     [rsp+58h+dwGranularity], 1000h
0x18000a780  mov     [rsp+58h+Addresses], 0
0x18000a789  call    cs:__imp_GetWriteWatch
0x18000a790  nop     dword ptr [rax+rax+00h]
0x18000a795  test    eax, eax
0x18000a797  jnz     short loc_18000A7E2
0x18000a799  cmp     [rsp+58h+dwCount], 0
0x18000a79f  setnz   al
0x18000a7a2  add     rsp, 58h
0x18000a7a6  retn
0x18000a7a8  cmp     byte ptr [rcx+78h], 0
0x18000a7ac  jz      loc_18000A71B
0x18000a7b2  test    r10b, 2
0x18000a7b6  jz      short loc_18000A7DA
0x18000a7b8  mov     rcx, [rcx+8]; lpBaseAddress
0x18000a7bc  mov     edx, 1000h; dwRegionSize
0x18000a7c1  call    cs:__imp_ResetWriteWatch
0x18000a7c8  nop     dword ptr [rax+rax+00h]
0x18000a7cd  xor     al, al
0x18000a7cf  jmp     short loc_18000A7A2
0x18000a7d1  cmp     byte ptr [rax+3258h], 0
0x18000a7d8  jz      short loc_18000A7DE
0x18000a7da  xor     al, al
0x18000a7dc  jmp     short loc_18000A7A2
0x18000a7de  mov     byte ptr [rcx+19h], 0
0x18000a7e2  mov     al, 1
0x18000a7e4  add     rsp, 58h
0x18000a7e8  retn
```
