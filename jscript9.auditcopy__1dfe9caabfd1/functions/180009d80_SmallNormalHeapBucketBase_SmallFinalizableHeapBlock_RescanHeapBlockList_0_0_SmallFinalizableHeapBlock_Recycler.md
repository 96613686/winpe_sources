# SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(SmallFinalizableHeapBlock *,Recycler *,RescanFlags)

- ea: `0x180009d80`
- end: `0x180009ea0`
- name: `??$RescanHeapBlockList@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KA_KPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@W4RescanFlags@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(SmallFinalizableHeapBlock *this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a02c`

## callees

- `0x180009d80`
- `0x180009ea8`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x180009e78`
- `KERNEL32!ResetWriteWatch` at `0x180009e78`
- `KERNEL32!GetWriteWatch` at `0x180009e1f`
- `KERNEL32!GetWriteWatch` at `0x180009e1f`

## pseudocode

```c
__int64 __fastcall SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanHeapBlockList<0,0>(
        SmallFinalizableHeapBlock *this,
        __int64 a2,
        unsigned int a3)
{
  SmallFinalizableHeapBlock *v3; // rbx
  __int64 v4; // rdi
  int v6; // ebp
  void *v7; // rdx
  DWORD dwGranularity; // [rsp+30h] [rbp-48h] BYREF
  ULONG_PTR dwCount; // [rsp+38h] [rbp-40h] BYREF
  PVOID Addresses; // [rsp+40h] [rbp-38h] BYREF

  v3 = this;
  v4 = 0;
  if ( this )
  {
    v6 = a3 & 1;
    do
    {
      if ( v6 )
      {
        *((_BYTE *)v3 + 120) = 0;
      }
      else if ( *((_BYTE *)v3 + 120) )
      {
        if ( (a3 & 2) != 0 )
          ResetWriteWatch(*((LPVOID *)v3 + 1), 0x1000u);
        goto LABEL_10;
      }
      if ( *((_WORD *)v3 + 40) )
      {
        if ( *((_BYTE *)v3 + 25) )
        {
          if ( !*(_BYTE *)(a2 + 12888) )
          {
            *((_BYTE *)v3 + 25) = 0;
LABEL_19:
            SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>(v3, a2);
LABEL_11:
            ++v4;
            goto LABEL_12;
          }
        }
        else if ( !*(_BYTE *)(a2 + 12901) )
        {
          v7 = (void *)*((_QWORD *)v3 + 1);
          dwCount = 1;
          dwGranularity = 4096;
          Addresses = 0;
          if ( GetWriteWatch((a3 >> 1) & 1, v7, 0x1000u, &Addresses, &dwCount, &dwGranularity) || dwCount )
            goto LABEL_19;
        }
      }
LABEL_10:
      if ( *((_BYTE *)v3 + 120) )
        goto LABEL_11;
LABEL_12:
      v3 = (SmallFinalizableHeapBlock *)*((_QWORD *)v3 + 4);
    }
    while ( v3 );
  }
  return v4;
}

```

## disassembly

```asm
0x180009d80  mov     rax, rsp
0x180009d83  mov     [rax+18h], r8d
0x180009d87  mov     [rax+10h], rdx
0x180009d8b  mov     [rax+8], rcx
0x180009d8f  push    rbx
0x180009d90  push    rbp
0x180009d91  push    rsi
0x180009d92  push    rdi
0x180009d93  push    r15
0x180009d95  sub     rsp, 50h
0x180009d99  xor     r15d, r15d
0x180009d9c  mov     rbx, rcx
0x180009d9f  mov     edi, r15d
0x180009da2  test    rcx, rcx
0x180009da5  jz      loc_180009E4C
0x180009dab  mov     ebp, r8d
0x180009dae  mov     rsi, rdx
0x180009db1  and     ebp, 1
0x180009db4  test    ebp, ebp
0x180009db6  jz      loc_180009E5B
0x180009dbc  mov     [rbx+78h], r15b
0x180009dc0  cmp     [rbx+50h], r15w
0x180009dc5  jz      short loc_180009E36
0x180009dc7  cmp     [rbx+19h], r15b
0x180009dcb  jnz     loc_180009E86
0x180009dd1  cmp     [rsi+3265h], r15b
0x180009dd8  jnz     short loc_180009E36
0x180009dda  mov     ecx, [rsp+78h+arg_10]
0x180009de1  lea     rax, [rsp+78h+dwGranularity]
0x180009de6  mov     rdx, [rbx+8]; lpBaseAddress
0x180009dea  lea     r9, [rsp+78h+Addresses]; lpAddresses
0x180009def  mov     [rsp+78h+lpdwGranularity], rax; lpdwGranularity
0x180009df4  mov     r8d, 1000h; dwRegionSize
0x180009dfa  shr     ecx, 1
0x180009dfc  lea     rax, [rsp+78h+dwCount]
0x180009e01  and     ecx, 1; dwFlags
0x180009e04  mov     [rsp+78h+lpdwCount], rax; lpdwCount
0x180009e09  mov     [rsp+78h+dwCount], 1
0x180009e12  mov     [rsp+78h+dwGranularity], 1000h
0x180009e1a  mov     [rsp+78h+Addresses], r15
0x180009e1f  call    cs:__imp_GetWriteWatch
0x180009e26  nop     dword ptr [rax+rax+00h]
0x180009e2b  test    eax, eax
0x180009e2d  jnz     short loc_180009E93
0x180009e2f  cmp     [rsp+78h+dwCount], r15
0x180009e34  jnz     short loc_180009E93
0x180009e36  cmp     [rbx+78h], r15b
0x180009e3a  jz      short loc_180009E3F
0x180009e3c  inc     rdi
0x180009e3f  mov     rbx, [rbx+20h]
0x180009e43  test    rbx, rbx
0x180009e46  jnz     loc_180009DB4
0x180009e4c  mov     rax, rdi
0x180009e4f  add     rsp, 50h
0x180009e53  pop     r15
0x180009e55  pop     rdi
0x180009e56  pop     rsi
0x180009e57  pop     rbp
0x180009e58  pop     rbx
0x180009e59  retn
0x180009e5b  cmp     [rbx+78h], r15b
0x180009e5f  jz      loc_180009DC0
0x180009e65  test    byte ptr [rsp+78h+arg_10], 2
0x180009e6d  jz      short loc_180009E36
0x180009e6f  mov     rcx, [rbx+8]; lpBaseAddress
0x180009e73  mov     edx, 1000h; dwRegionSize
0x180009e78  call    cs:__imp_ResetWriteWatch
0x180009e7f  nop     dword ptr [rax+rax+00h]
0x180009e84  jmp     short loc_180009E36
0x180009e86  cmp     [rsi+3258h], r15b
0x180009e8d  jnz     short loc_180009E36
0x180009e8f  mov     [rbx+19h], r15b
0x180009e93  mov     rdx, rsi
0x180009e96  mov     rcx, rbx; this
0x180009e99  call    ??$RescanObjects@$0A@$0A@@?$SmallNormalHeapBucketBase@VSmallFinalizableHeapBlock@@@@KAXPEAVSmallFinalizableHeapBlock@@PEAVRecycler@@@Z; SmallNormalHeapBucketBase<SmallFinalizableHeapBlock>::RescanObjects<0,0>(SmallFinalizableHeapBlock *,Recycler *)
0x180009e9e  jmp     short loc_180009E3C
```
