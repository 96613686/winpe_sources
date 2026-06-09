# DiscpSetGroupPresharedKey

- ea: `0x1800100f8`
- end: `0x180010264`
- name: `DiscpSetGroupPresharedKey`
- size: `364`
- prototype: `__int64 __fastcall(void *Src, size_t Size, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003e50`

## callees

- `0x18000f4a8`
- `0x18000ff88`
- `0x1800100f8`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x18001013e`
- `ISCSIUM!DiscpAllocMemory` at `0x18001013e`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18001019e`
- `ISCSIUM!DiscpSetRegistryValue` at `0x18001019e`
- `ISCSIUM!DiscpFreeMemory` at `0x1800101b6`
- `ISCSIUM!DiscpFreeMemory` at `0x18001022a`
- `ISCSIUM!DiscpFreeMemory` at `0x180010239`
- `ISCSIUM!DiscpFreeMemory` at `0x1800101b6`
- `ISCSIUM!DiscpFreeMemory` at `0x18001022a`
- `ISCSIUM!DiscpFreeMemory` at `0x180010239`
- `ntdll!RtlLeaveCriticalSection` at `0x180010168`
- `ntdll!RtlLeaveCriticalSection` at `0x1800101d0`
- `ntdll!RtlLeaveCriticalSection` at `0x180010168`
- `ntdll!RtlLeaveCriticalSection` at `0x1800101d0`
- `ntdll!RtlEnterCriticalSection` at `0x180010131`
- `ntdll!RtlEnterCriticalSection` at `0x180010131`
- `WMICLNT!WmiCloseBlock` at `0x180010247`
- `WMICLNT!WmiCloseBlock` at `0x180010247`

## pseudocode

```c
__int64 __fastcall DiscpSetGroupPresharedKey(void *Src, size_t Size, char a3)
{
  unsigned int v4; // esi
  void *v6; // rax
  void *v7; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // ebp
  __int64 v10; // rdi
  __int64 i; // rsi
  __int64 v13; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  v4 = Size;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( Src )
  {
    v6 = (void *)DiscpAllocMemory(v4);
    v7 = v6;
    if ( !v6 )
    {
      v8 = 8;
      RtlLeaveCriticalSection(&DiscpCritSection);
      return v8;
    }
    memcpy_0(v6, Src, v4);
  }
  else
  {
    v7 = 0;
  }
  v8 = 0;
  if ( !a3
    || (v8 = DiscpSetRegistryValue(
               0,
               L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
               L"GroupKey",
               3,
               Src,
               v4,
               1)) == 0 )
  {
    if ( DiscpGroupKey )
      DiscpFreeMemory(DiscpGroupKey);
    DiscpGroupKey = v7;
    LODWORD(DiscpGroupKeyLength) = v4;
  }
  RtlLeaveCriticalSection(&DiscpCritSection);
  if ( !v8 && !(unsigned int)DiscpGetInitiatorsSupportingSecurity(&v15, &v14, &v13) )
  {
    v9 = v14;
    v10 = 0;
    for ( i = v13; (unsigned int)v10 < v9; v10 = (unsigned int)(v10 + 1) )
    {
      DiscpSetGroupKeyForInitiator(v15, *(_QWORD *)(i + 8 * v10));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(i + 8 * v10) + 16LL), 0xFFFFFFFF) == 1 )
        DiscpFreeMemory(*(_QWORD *)(i + 8 * v10));
    }
    DiscpFreeMemory(i);
    WmiCloseBlock(v15);
  }
  return v8;
}

```

## disassembly

```asm
0x1800100f8  mov     rax, rsp
0x1800100fb  mov     [rax+10h], rbx
0x1800100ff  mov     [rax+18h], rbp
0x180010103  push    rsi
0x180010104  push    rdi
0x180010105  push    r14
0x180010107  sub     rsp, 50h
0x18001010b  mov     rbp, rcx
0x18001010e  mov     esi, edx
0x180010110  lea     rcx, DiscpCritSection; CriticalSection
0x180010117  mov     dword ptr [rax+8], 0
0x18001011e  mov     r14b, r8b
0x180010121  mov     qword ptr [rax-28h], 0
0x180010129  mov     qword ptr [rax+20h], 0
0x180010131  call    cs:__imp_RtlEnterCriticalSection
0x180010137  test    rbp, rbp
0x18001013a  jz      short loc_180010173
0x18001013c  mov     ecx, esi
0x18001013e  call    cs:__imp_DiscpAllocMemory
0x180010144  mov     rdi, rax
0x180010147  test    rax, rax
0x18001014a  jz      short loc_18001015C
0x18001014c  mov     r8d, esi; Size
0x18001014f  mov     rdx, rbp; Src
0x180010152  mov     rcx, rax; void *
0x180010155  call    memcpy_0
0x18001015a  jmp     short loc_180010175
0x18001015c  lea     rcx, DiscpCritSection; CriticalSection
0x180010163  mov     ebx, 8
0x180010168  call    cs:__imp_RtlLeaveCriticalSection
0x18001016e  jmp     loc_18001024D
0x180010173  xor     edi, edi
0x180010175  xor     ebx, ebx
0x180010177  test    r14b, r14b
0x18001017a  jz      short loc_1800101AA
0x18001017c  mov     [rsp+68h+var_38], 1
0x180010181  lea     r9d, [rbx+3]
0x180010185  mov     [rsp+68h+var_40], esi
0x180010189  lea     r8, aGroupkey; "GroupKey"
0x180010190  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180010197  mov     [rsp+68h+var_48], rbp
0x18001019c  xor     ecx, ecx
0x18001019e  call    cs:__imp_DiscpSetRegistryValue
0x1800101a4  mov     ebx, eax
0x1800101a6  test    eax, eax
0x1800101a8  jnz     short loc_1800101C9
0x1800101aa  mov     rcx, cs:DiscpGroupKey
0x1800101b1  test    rcx, rcx
0x1800101b4  jz      short loc_1800101BC
0x1800101b6  call    cs:__imp_DiscpFreeMemory
0x1800101bc  mov     cs:DiscpGroupKey, rdi
0x1800101c3  mov     cs:DiscpGroupKeyLength, esi
0x1800101c9  lea     rcx, DiscpCritSection; CriticalSection
0x1800101d0  call    cs:__imp_RtlLeaveCriticalSection
0x1800101d6  test    ebx, ebx
0x1800101d8  jnz     short loc_18001024D
0x1800101da  lea     r8, [rsp+68h+var_28]
0x1800101df  lea     rdx, [rsp+68h+arg_0]
0x1800101e4  lea     rcx, [rsp+68h+arg_18]
0x1800101ec  call    DiscpGetInitiatorsSupportingSecurity
0x1800101f1  test    eax, eax
0x1800101f3  jnz     short loc_18001024D
0x1800101f5  mov     ebp, [rsp+68h+arg_0]
0x1800101f9  xor     edi, edi
0x1800101fb  mov     rsi, [rsp+68h+var_28]
0x180010200  test    ebp, ebp
0x180010202  jz      short loc_180010236
0x180010204  mov     rdx, [rsi+rdi*8]
0x180010208  mov     rcx, [rsp+68h+arg_18]
0x180010210  call    DiscpSetGroupKeyForInitiator
0x180010215  mov     rdx, [rsi+rdi*8]
0x180010219  or      eax, 0FFFFFFFFh
0x18001021c  lock xadd [rdx+10h], eax
0x180010221  cmp     eax, 1
0x180010224  jnz     short loc_180010230
0x180010226  mov     rcx, [rsi+rdi*8]
0x18001022a  call    cs:__imp_DiscpFreeMemory
0x180010230  inc     edi
0x180010232  cmp     edi, ebp
0x180010234  jb      short loc_180010204
0x180010236  mov     rcx, rsi
0x180010239  call    cs:__imp_DiscpFreeMemory
0x18001023f  mov     rcx, [rsp+68h+arg_18]
0x180010247  call    cs:__imp_WmiCloseBlock
0x18001024d  lea     r11, [rsp+68h+var_18]
0x180010252  mov     eax, ebx
0x180010254  mov     rbx, [r11+28h]
0x180010258  mov     rbp, [r11+30h]
0x18001025c  mov     rsp, r11
0x18001025f  pop     r14
0x180010261  pop     rdi
0x180010262  pop     rsi
0x180010263  retn
```
