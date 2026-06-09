# DfscRefCacheStore

- ea: `0x14001a718`
- end: `0x14001a794`
- name: `DfscRefCacheStore`
- size: `124`
- prototype: `ULONG_PTR __fastcall(__int64, __int64, ULONG_PTR)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002cd0`
- `0x140003020`
- `0x140016070`
- `0x1400169f8`
- `0x14001b230`

## callees

- `0x1400026a4`
- `0x14001a718`
- `0x14001a79c`
- `0x14001c310`

## pseudocode

```c
ULONG_PTR __fastcall DfscRefCacheStore(__int64 a1, __int64 a2, ULONG_PTR a3)
{
  ULONG_PTR ReferralCache; // rsi
  __int64 v6; // r8

  ReferralCache = DfscGetReferralCache(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids,
      a3,
      v6 + 144);
  return DfscCacheStore(a2, a3, ReferralCache);
}

```

## disassembly

```asm
0x14001a718  mov     [rsp+arg_0], rbx
0x14001a71d  mov     [rsp+arg_8], rsi
0x14001a722  push    rdi
0x14001a723  sub     rsp, 30h
0x14001a727  mov     rbx, r8
0x14001a72a  mov     rdi, rdx
0x14001a72d  call    DfscGetReferralCache
0x14001a732  mov     rsi, rax
0x14001a735  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a73c  lea     rax, WPP_GLOBAL_Control
0x14001a743  cmp     rcx, rax
0x14001a746  jz      short loc_14001A775
0x14001a748  test    dword ptr [rcx+2Ch], 400000h
0x14001a74f  jz      short loc_14001A775
0x14001a751  mov     rcx, [rcx+18h]
0x14001a755  add     r8, 90h
0x14001a75c  mov     [rsp+38h+var_18], r8
0x14001a761  mov     edx, 0Ah
0x14001a766  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001a76d  mov     r9, rbx
0x14001a770  call    WPP_SF_qZ
0x14001a775  mov     r8, rsi
0x14001a778  mov     rdx, rbx
0x14001a77b  mov     rcx, rdi
0x14001a77e  call    DfscCacheStore
0x14001a783  mov     rbx, [rsp+38h+arg_0]
0x14001a788  mov     rsi, [rsp+38h+arg_8]
0x14001a78d  add     rsp, 30h
0x14001a791  pop     rdi
0x14001a792  retn
```
