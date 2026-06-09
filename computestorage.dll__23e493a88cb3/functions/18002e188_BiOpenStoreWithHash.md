# BiOpenStoreWithHash

- ea: `0x18002e188`
- end: `0x18002e357`
- name: `BiOpenStoreWithHash`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dfe4`
- `0x180020880`

## callees

- `0x180003bb5`
- `0x18002d940`
- `0x18002d9b0`
- `0x18002dfa8`
- `0x18002e188`
- `0x18002e360`
- `0x180032a28`
- `0x180034254`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002e32d`
- `ntdll!RtlFreeHeap` at `0x18002e32d`
- `ntdll!RtlAllocateHeap` at `0x18002e22e`
- `ntdll!RtlAllocateHeap` at `0x18002e22e`

## string_xrefs

- `0x18002e1cf`: `BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x`
- `0x18002e1f5`: `Opening store. Flags: 0x%x`
- `0x18002e273`: `Store path: "%s"`
- `0x18002e2c1`: `BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x`
- `0x18002e28d`: `Store will be accessed with offline registry APIs.`
- `0x18002e2e0`: `GuidCache`

## pseudocode

```c
__int64 __fastcall BiOpenStoreWithHash(const void **a1, __int64 a2, __int64 a3, __int64 *a4)
{
  const void **v4; // rbx
  int v6; // edi
  const wchar_t *v7; // r8
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // edi
  _DWORD *Heap; // rax
  void *v14; // r14
  _DWORD *v15; // rdi
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdi
  int v19; // eax
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v20 = a3;
  v4 = a1;
  LOBYTE(a1) = 1;
  v6 = BiAcquireBcdSyncMutant(a1);
  if ( v6 >= 0 )
  {
    v20 = 0;
    v9 = 2;
    BiLogMessage(2, L"Opening store. Flags: 0x%x");
    if ( v4 )
    {
      v12 = *(unsigned __int16 *)v4 + 14;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      v14 = Heap;
      if ( Heap )
      {
        Heap[1] = v12;
        v15 = Heap + 3;
        *Heap = 1;
        Heap[2] = 3;
        memcpy_0(Heap + 3, v4[1], *(unsigned __int16 *)v4);
        *((_WORD *)v15 + ((unsigned __int64)*(unsigned __int16 *)v4 >> 1)) = 0;
        BiLogMessage(2, L"Store path: \"%s\"", v15);
        BiLogMessage(2, L"Store will be accessed with offline registry APIs.");
        v17 = BiAddStoreFromFile(v14, 32, v16, &v20);
        v11 = v17;
        if ( v17 >= 0 )
        {
          v18 = v20;
          BiDeleteRegistryValue(v20, L"GuidCache");
          v19 = BiMarkTreatAsSystemStore(v18, 0);
          v11 = v19;
          if ( v19 >= 0 )
            *a4 = v18 | 2;
          else
            BiLogMessage(4, L"Failed to clear system store flag. Status: %x", (unsigned int)v19);
        }
        else
        {
          if ( v17 != -1073741809 )
            v9 = 4;
          BiLogMessage(
            v9,
            L"BcdOpenStore: Failed to add store from file %ws. StoreFlags: 0x%x Status: %x",
            v15,
            32,
            v17);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      }
      else
      {
        v11 = -1073741801;
      }
    }
    else
    {
      v11 = -1073741811;
    }
    LOBYTE(v10) = 1;
    BiReleaseBcdSyncMutant(v10);
    return v11;
  }
  else
  {
    if ( v4 )
      v7 = (const wchar_t *)v4[1];
    else
      v7 = L"NULL";
    BiLogMessage(4, L"BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x", v7);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18002e188  mov     [rsp+arg_0], rbx
0x18002e18d  mov     [rsp+arg_8], rsi
0x18002e192  mov     [rsp+arg_10], r8
0x18002e197  push    rdi
0x18002e198  push    r14
0x18002e19a  push    r15
0x18002e19c  sub     rsp, 30h
0x18002e1a0  mov     rbx, rcx
0x18002e1a3  mov     r15, r9
0x18002e1a6  mov     cl, 1
0x18002e1a8  call    BiAcquireBcdSyncMutant
0x18002e1ad  mov     edi, eax
0x18002e1af  test    eax, eax
0x18002e1b1  jns     short loc_18002E1E6
0x18002e1b3  test    rbx, rbx
0x18002e1b6  jz      short loc_18002E1BE
0x18002e1b8  mov     r8, [rbx+8]
0x18002e1bc  jmp     short loc_18002E1C5
0x18002e1be  lea     r8, aNull; "NULL"
0x18002e1c5  mov     r9d, 1
0x18002e1cb  mov     [rsp+48h+var_28], edi
0x18002e1cf  lea     rdx, aBcdopenstoreFa; "BcdOpenStore: Failed to acquire BCD syn"...
0x18002e1d6  lea     ecx, [r9+3]
0x18002e1da  call    BiLogMessage
0x18002e1df  mov     eax, edi
0x18002e1e1  jmp     loc_18002E342
0x18002e1e6  mov     r8d, 1
0x18002e1ec  mov     [rsp+48h+arg_10], 0
0x18002e1f5  lea     rdx, aOpeningStoreFl; "Opening store. Flags: 0x%x"
0x18002e1fc  lea     esi, [r8+1]
0x18002e200  mov     ecx, esi
0x18002e202  call    BiLogMessage
0x18002e207  test    rbx, rbx
0x18002e20a  jnz     short loc_18002E216
0x18002e20c  mov     ebx, 0C000000Dh
0x18002e211  jmp     loc_18002E339
0x18002e216  mov     rcx, gs:60h
0x18002e21f  xor     edx, edx; Flags
0x18002e221  movzx   edi, word ptr [rbx]
0x18002e224  add     edi, 0Eh
0x18002e227  mov     r8d, edi; Size
0x18002e22a  mov     rcx, [rcx+30h]; HeapHandle
0x18002e22e  call    cs:__imp_RtlAllocateHeap
0x18002e235  nop     dword ptr [rax+rax+00h]
0x18002e23a  mov     r14, rax
0x18002e23d  test    rax, rax
0x18002e240  jnz     short loc_18002E24C
0x18002e242  mov     ebx, 0C0000017h
0x18002e247  jmp     loc_18002E339
0x18002e24c  mov     [rax+4], edi
0x18002e24f  lea     rdi, [rax+0Ch]
0x18002e253  mov     dword ptr [rax], 1
0x18002e259  mov     rcx, rdi; void *
0x18002e25c  mov     dword ptr [rax+8], 3
0x18002e263  movzx   r8d, word ptr [rbx]; Size
0x18002e267  mov     rdx, [rbx+8]; Src
0x18002e26b  call    memcpy_0
0x18002e270  movzx   ecx, word ptr [rbx]
0x18002e273  lea     rdx, aStorePathS; "Store path: \"%s\""
0x18002e27a  shr     rcx, 1
0x18002e27d  xor     eax, eax
0x18002e27f  mov     r8, rdi
0x18002e282  mov     [rdi+rcx*2], ax
0x18002e286  mov     ecx, esi
0x18002e288  call    BiLogMessage
0x18002e28d  lea     rdx, aStoreWillBeAcc; "Store will be accessed with offline reg"...
0x18002e294  mov     ecx, esi
0x18002e296  call    BiLogMessage
0x18002e29b  lea     r9, [rsp+48h+arg_10]
0x18002e2a0  mov     edx, 20h ; ' '
0x18002e2a5  mov     rcx, r14
0x18002e2a8  call    BiAddStoreFromFile
0x18002e2ad  mov     ebx, eax
0x18002e2af  test    eax, eax
0x18002e2b1  jns     short loc_18002E2DB
0x18002e2b3  mov     ecx, 4
0x18002e2b8  mov     [rsp+48h+var_28], eax
0x18002e2bc  cmp     eax, 0C000000Fh
0x18002e2c1  lea     rdx, aBcdopenstoreFa_0; "BcdOpenStore: Failed to add store from "...
0x18002e2c8  mov     r8, rdi
0x18002e2cb  cmovnz  esi, ecx
0x18002e2ce  lea     r9d, [rcx+1Ch]
0x18002e2d2  mov     ecx, esi
0x18002e2d4  call    BiLogMessage
0x18002e2d9  jmp     short loc_18002E31B
0x18002e2db  mov     rdi, [rsp+48h+arg_10]
0x18002e2e0  lea     rdx, aGuidcache; "GuidCache"
0x18002e2e7  mov     rcx, rdi
0x18002e2ea  call    BiDeleteRegistryValue
0x18002e2ef  xor     edx, edx
0x18002e2f1  mov     rcx, rdi
0x18002e2f4  call    BiMarkTreatAsSystemStore
0x18002e2f9  mov     ebx, eax
0x18002e2fb  test    eax, eax
0x18002e2fd  jns     short loc_18002E315
0x18002e2ff  mov     r8d, eax
0x18002e302  lea     rdx, aFailedToClearS; "Failed to clear system store flag. Stat"...
0x18002e309  mov     ecx, 4
0x18002e30e  call    BiLogMessage
0x18002e313  jmp     short loc_18002E31B
0x18002e315  or      rdi, rsi
0x18002e318  mov     [r15], rdi
0x18002e31b  mov     rcx, gs:60h
0x18002e324  mov     r8, r14; P
0x18002e327  xor     edx, edx; Flags
0x18002e329  mov     rcx, [rcx+30h]; HeapHandle
0x18002e32d  call    cs:__imp_RtlFreeHeap
0x18002e334  nop     dword ptr [rax+rax+00h]
0x18002e339  mov     cl, 1
0x18002e33b  call    BiReleaseBcdSyncMutant
0x18002e340  mov     eax, ebx
0x18002e342  mov     rbx, [rsp+48h+arg_0]
0x18002e347  mov     rsi, [rsp+48h+arg_8]
0x18002e34c  add     rsp, 30h
0x18002e350  pop     r15
0x18002e352  pop     r14
0x18002e354  pop     rdi
0x18002e355  retn
```
