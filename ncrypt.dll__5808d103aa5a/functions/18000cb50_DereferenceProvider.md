# DereferenceProvider

- ea: `0x18000cb50`
- end: `0x18000cbe3`
- name: `DereferenceProvider`
- size: `147`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007120`
- `0x18000c700`
- `0x18000f290`
- `0x180010c90`
- `0x180011310`
- `0x180011470`
- `0x180011950`
- `0x1800147a0`
- `0x1800175f0`
- `0x180017990`
- `0x18001c2c0`

## callees

- `0x180007234`
- `0x180007ca0`
- `0x18000a770`
- `0x18000cb50`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000cbcc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
__int64 __fastcall DereferenceProvider(__int64 a1)
{
  __int64 result; // rax
  int v3; // eax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 96))(*(_QWORD *)(a1 + 272));
    if ( v3 < 0 )
      DebugTraceError(
        (unsigned int)v3,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        128);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids, a1);
    UnloadProvider(*(_QWORD *)(a1 + 8));
    return MSCryptFree(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000cb50  push    rbx
0x18000cb52  sub     rsp, 20h
0x18000cb56  mov     rbx, rcx
0x18000cb59  mov     eax, 0FFFFFFFFh
0x18000cb5e  lock xadd [rcx+4], eax
0x18000cb63  cmp     eax, 1
0x18000cb66  jz      short loc_18000CB6E
0x18000cb68  add     rsp, 20h
0x18000cb6c  pop     rbx
0x18000cb6d  retn
0x18000cb6e  mov     rcx, [rcx+110h]
0x18000cb75  mov     rax, [rbx+60h]
0x18000cb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7e  test    eax, eax
0x18000cb80  js      short loc_18000CBC6
0x18000cb82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb89  lea     rax, WPP_GLOBAL_Control
0x18000cb90  cmp     rcx, rax
0x18000cb93  jz      short loc_18000CBB3
0x18000cb95  test    byte ptr [rcx+1Ch], 20h
0x18000cb99  jz      short loc_18000CBB3
0x18000cb9b  mov     rcx, [rcx+10h]
0x18000cb9f  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids
0x18000cba6  mov     edx, 0Ch
0x18000cbab  mov     r9, rbx
0x18000cbae  call    WPP_SF_q
0x18000cbb3  mov     rcx, [rbx+8]
0x18000cbb7  call    UnloadProvider
0x18000cbbc  mov     rcx, rbx
0x18000cbbf  call    MSCryptFree
0x18000cbc4  jmp     short loc_18000CB68
0x18000cbc6  mov     r9d, 80h
0x18000cbcc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cbd3  lea     rdx, aStatus; "Status"
0x18000cbda  mov     ecx, eax
0x18000cbdc  call    DebugTraceError
0x18000cbe1  jmp     short loc_18000CB82
```
