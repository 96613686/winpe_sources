# BiOpenStoreWithHash

- ea: `0x14072fda8`
- end: `0x14072fe6e`
- name: `BiOpenStoreWithHash`
- size: `198`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x14072fd90`
- `0x14078a2e4`
- `0x140791458`
- `0x140792ad0`
- `0x1407a00dc`
- `0x140ab2c14`
- `0x140af09b4`

## callees

- `0x14072fda8`
- `0x140992e34`
- `0x140993038`
- `0x140993244`
- `0x140993780`

## string_xrefs

- `0x14072fe42`: `Failed to open system store. Status: %x`
- `0x14072fdf9`: `Opening store. Flags: 0x%x`
- `0x14072fde5`: `BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x`

## pseudocode

```c
__int64 __fastcall BiOpenStoreWithHash(__int64 a1, unsigned int a2, __int64 a3, unsigned __int64 *a4)
{
  char v5; // di
  int v7; // eax
  unsigned int v8; // r10d
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  int v13; // eax

  v5 = a2 & 1;
  LOBYTE(a1) = a2 & 1;
  v7 = BiAcquireBcdSyncMutant(a1);
  if ( v7 >= 0 )
  {
    BiLogMessage(2, L"Opening store. Flags: 0x%x", a2);
    if ( v5 )
    {
      v11 = -1073741811;
    }
    else
    {
      if ( ((unsigned __int8)a2 & (unsigned __int8)v10) != 0 )
        BiLogMessage(v10, L"Store will be synchronized with firmware.", 0);
      else
        v12 = v10;
      v13 = BiOpenSystemStore(a4, v12);
      v11 = v13;
      if ( v13 < 0 )
        BiLogMessage(4, L"Failed to open system store. Status: %x", (unsigned int)v13);
    }
    LOBYTE(v10) = v5;
    BiReleaseBcdSyncMutant(v10);
    return v11;
  }
  else
  {
    BiLogMessage(
      4,
      L"BcdOpenStore: Failed to acquire BCD sync Mutant. Store: %ws Flags: 0x%x Status: %x",
      L"NULL",
      a2,
      v7);
    return v8;
  }
}

```

## disassembly

```asm
0x14072fda8  mov     [rsp+arg_0], rbx
0x14072fdad  mov     [rsp+arg_8], rsi
0x14072fdb2  push    rdi
0x14072fdb3  sub     rsp, 30h
0x14072fdb7  mov     dil, dl
0x14072fdba  mov     rsi, r9
0x14072fdbd  and     dil, 1
0x14072fdc1  mov     ebx, edx
0x14072fdc3  mov     cl, dil
0x14072fdc6  call    BiAcquireBcdSyncMutant
0x14072fdcb  mov     r10d, eax
0x14072fdce  test    eax, eax
0x14072fdd0  jns     short loc_14072FDF6
0x14072fdd2  mov     r9d, ebx
0x14072fdd5  mov     [rsp+38h+var_18], eax
0x14072fdd9  lea     r8, aNull; "NULL"
0x14072fde0  mov     ecx, 4
0x14072fde5  lea     rdx, aBcdopenstoreFa; "BcdOpenStore: Failed to acquire BCD syn"...
0x14072fdec  call    BiLogMessage
0x14072fdf1  mov     eax, r10d
0x14072fdf4  jmp     short loc_14072FE5D
0x14072fdf6  mov     r8d, ebx
0x14072fdf9  lea     rdx, aOpeningStoreFl; "Opening store. Flags: 0x%x"
0x14072fe00  mov     ecx, 2
0x14072fe05  call    BiLogMessage
0x14072fe0a  test    dil, dil
0x14072fe0d  jz      short loc_14072FE16
0x14072fe0f  mov     ebx, 0C000000Dh
0x14072fe14  jmp     short loc_14072FE53
0x14072fe16  test    cl, bl
0x14072fe18  jnz     short loc_14072FE1F
0x14072fe1a  mov     r8d, ecx
0x14072fe1d  jmp     short loc_14072FE2E
0x14072fe1f  xor     r8d, r8d
0x14072fe22  lea     rdx, aStoreWillBeSyn; "Store will be synchronized with firmwar"...
0x14072fe29  call    BiLogMessage
0x14072fe2e  mov     edx, r8d
0x14072fe31  mov     rcx, rsi
0x14072fe34  call    BiOpenSystemStore
0x14072fe39  mov     ebx, eax
0x14072fe3b  test    eax, eax
0x14072fe3d  jns     short loc_14072FE53
0x14072fe3f  mov     r8d, eax
0x14072fe42  lea     rdx, aFailedToOpenSy; "Failed to open system store. Status: %x"
0x14072fe49  mov     ecx, 4
0x14072fe4e  call    BiLogMessage
0x14072fe53  mov     cl, dil
0x14072fe56  call    BiReleaseBcdSyncMutant
0x14072fe5b  mov     eax, ebx
0x14072fe5d  mov     rbx, [rsp+38h+arg_0]
0x14072fe62  mov     rsi, [rsp+38h+arg_8]
0x14072fe67  add     rsp, 30h
0x14072fe6b  pop     rdi
0x14072fe6c  retn
```
