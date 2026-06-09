# DfscRmDereferenceReferral

- ea: `0x14001d090`
- end: `0x14001d108`
- name: `DfscRmDereferenceReferral`
- size: `120`
- prototype: `void __fastcall(volatile signed __int32 *P)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x140001744`
- `0x140001df8`
- `0x140001f4c`
- `0x140002430`
- `0x140002cd0`
- `0x140003020`
- `0x1400051d0`
- `0x140011a78`
- `0x140014d30`
- `0x140015050`
- `0x14001520c`
- `0x140016070`
- `0x1400169f8`
- `0x1400172ec`
- `0x14001935c`
- `0x14001b230`
- `0x14001bfe4`
- `0x14001c310`
- `0x14001c8ac`
- `0x14001cb40`
- `0x14001d110`
- `0x14001fb50`
- `0x140022840`
- `0x140026d10`
- `0x14002774c`
- `0x140028f7c`

## callees

- `0x1400026a4`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001d0d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d0d4`

## pseudocode

```c
void __fastcall DfscRmDereferenceReferral(volatile signed __int32 *P)
{
  if ( P && _InterlockedExchangeAdd(P + 1, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        (unsigned int)WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
        (_DWORD)P,
        (__int64)(P + 36));
    }
    ExFreePoolWithTag((PVOID)P, 0);
  }
}

```

## disassembly

```asm
0x14001d090  test    rcx, rcx
0x14001d093  jz      short locret_14001D0B1
0x14001d095  push    rbx
0x14001d096  sub     rsp, 30h
0x14001d09a  mov     rbx, rcx
0x14001d09d  mov     eax, 0FFFFFFFFh
0x14001d0a2  lock xadd [rcx+4], eax
0x14001d0a7  cmp     eax, 1
0x14001d0aa  jz      short loc_14001D0B3
0x14001d0ac  add     rsp, 30h
0x14001d0b0  pop     rbx
0x14001d0b1  retn
0x14001d0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0ba  lea     rax, WPP_GLOBAL_Control
0x14001d0c1  cmp     rcx, rax
0x14001d0c4  jz      short loc_14001D0CF
0x14001d0c6  test    dword ptr [rcx+2Ch], 200000h
0x14001d0cd  jnz     short loc_14001D0E2
0x14001d0cf  xor     edx, edx; Tag
0x14001d0d1  mov     rcx, rbx; P
0x14001d0d4  call    cs:__imp_ExFreePoolWithTag
0x14001d0db  nop     dword ptr [rax+rax+00h]
0x14001d0e0  jmp     short loc_14001D0AC
0x14001d0e2  mov     rcx, [rcx+18h]
0x14001d0e6  lea     rax, [rbx+90h]
0x14001d0ed  mov     edx, 1Bh
0x14001d0f2  mov     [rsp+38h+var_18], rax
0x14001d0f7  mov     r9, rbx
0x14001d0fa  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14001d101  call    WPP_SF_qZ
0x14001d106  jmp     short loc_14001D0CF
```
