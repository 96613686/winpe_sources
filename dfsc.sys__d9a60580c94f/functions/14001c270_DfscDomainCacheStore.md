# DfscDomainCacheStore

- ea: `0x14001c270`
- end: `0x14001c2de`
- name: `DfscDomainCacheStore`
- size: `110`
- prototype: `ULONG_PTR __fastcall(__int64, ULONG_PTR)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400172ec`
- `0x14001abc0`
- `0x14001b230`
- `0x14001bfe4`
- `0x140022840`

## callees

- `0x1400026a4`
- `0x14001c270`
- `0x14001c2e4`
- `0x14001c310`

## pseudocode

```c
ULONG_PTR __fastcall DfscDomainCacheStore(__int64 a1, ULONG_PTR a2)
{
  __int64 v3; // rdx
  ULONG_PTR DomainCache; // rdi

  DomainCache = DfscGetDomainCache();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids,
      a2,
      v3 + 144);
  return DfscCacheStore(0, a2, DomainCache);
}

```

## disassembly

```asm
0x14001c270  mov     [rsp+arg_0], rbx
0x14001c275  push    rdi
0x14001c276  sub     rsp, 30h
0x14001c27a  mov     rbx, rdx
0x14001c27d  call    DfscGetDomainCache
0x14001c282  mov     rdi, rax
0x14001c285  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c28c  lea     rax, WPP_GLOBAL_Control
0x14001c293  cmp     rcx, rax
0x14001c296  jz      short loc_14001C2C5
0x14001c298  test    dword ptr [rcx+2Ch], 400000h
0x14001c29f  jz      short loc_14001C2C5
0x14001c2a1  mov     rcx, [rcx+18h]
0x14001c2a5  lea     r8, [rdx+90h]
0x14001c2ac  mov     [rsp+38h+var_18], r8
0x14001c2b1  mov     edx, 0Bh
0x14001c2b6  lea     r8, WPP_3c5c140b1540308376b7b4f9fe221567_Traceguids
0x14001c2bd  mov     r9, rbx
0x14001c2c0  call    WPP_SF_qZ
0x14001c2c5  mov     r8, rdi
0x14001c2c8  mov     rdx, rbx
0x14001c2cb  xor     ecx, ecx
0x14001c2cd  call    DfscCacheStore
0x14001c2d2  mov     rbx, [rsp+38h+arg_0]
0x14001c2d7  add     rsp, 30h
0x14001c2db  pop     rdi
0x14001c2dc  retn
```
