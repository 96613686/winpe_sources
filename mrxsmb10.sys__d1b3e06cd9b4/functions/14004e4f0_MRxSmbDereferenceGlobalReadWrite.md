# MRxSmbDereferenceGlobalReadWrite

- ea: `0x14004e4f0`
- end: `0x14004e5a1`
- name: `MRxSmbDereferenceGlobalReadWrite`
- size: `177`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14004cfa0`

## callees

- `0x1400159f4`
- `0x14004e4f0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004e56b`
- `ntoskrnl!KeSetEvent` at `0x14004e56b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e57c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e57c`
- `rdbss!RxLowIoCompletion` at `0x14004e54d`
- `rdbss!RxLowIoCompletion` at `0x14004e54d`

## pseudocode

```c
__int64 __fastcall MRxSmbDereferenceGlobalReadWrite(PVOID P, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  int v5; // ebp
  signed __int32 v6; // ebx

  v3 = *((_QWORD *)P + 1);
  v5 = *(_DWORD *)(v3 + 120);
  v6 = _InterlockedDecrement((volatile signed __int32 *)P + 86);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 10, a3, P, v6);
  if ( !v6 )
  {
    *(_DWORD *)(v3 + 176) = *((_DWORD *)P + 90);
    RxLowIoCompletion((PRX_CONTEXT)v3);
    if ( (v5 & 0x1000) == 0 )
      KeSetEvent(*((PRKEVENT *)P + 44), 0, 0);
    ExFreePoolWithTag(P, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14004e4f0  push    rbx
0x14004e4f2  push    rbp
0x14004e4f3  push    rsi
0x14004e4f4  push    rdi
0x14004e4f5  sub     rsp, 38h
0x14004e4f9  mov     rsi, [rcx+8]
0x14004e4fd  mov     rdi, rcx
0x14004e500  mov     ebx, 0FFFFFFFFh
0x14004e505  mov     ebp, [rsi+78h]
0x14004e508  lock xadd [rcx+158h], ebx
0x14004e510  dec     ebx
0x14004e512  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004e519  lea     rax, WPP_GLOBAL_Control
0x14004e520  cmp     rcx, rax
0x14004e523  jz      short loc_14004E52E
0x14004e525  test    dword ptr [rcx+2Ch], 200h
0x14004e52c  jnz     short loc_14004E58A
0x14004e52e  test    ebx, ebx
0x14004e530  jz      short loc_14004E53E
0x14004e532  xor     eax, eax
0x14004e534  add     rsp, 38h
0x14004e538  pop     rdi
0x14004e539  pop     rsi
0x14004e53a  pop     rbp
0x14004e53b  pop     rbx
0x14004e53c  retn
0x14004e53e  mov     eax, [rdi+168h]
0x14004e544  mov     rcx, rsi; RxContext
0x14004e547  mov     [rsi+0B0h], eax
0x14004e54d  call    cs:__imp_RxLowIoCompletion
0x14004e554  nop     dword ptr [rax+rax+00h]
0x14004e559  bt      ebp, 0Ch
0x14004e55d  jb      short loc_14004E577
0x14004e55f  mov     rcx, [rdi+160h]; Event
0x14004e566  xor     r8d, r8d; Wait
0x14004e569  xor     edx, edx; Increment
0x14004e56b  call    cs:__imp_KeSetEvent
0x14004e572  nop     dword ptr [rax+rax+00h]
0x14004e577  xor     edx, edx; Tag
0x14004e579  mov     rcx, rdi; P
0x14004e57c  call    cs:__imp_ExFreePoolWithTag
0x14004e583  nop     dword ptr [rax+rax+00h]
0x14004e588  jmp     short loc_14004E532
0x14004e58a  mov     rcx, [rcx+18h]
0x14004e58e  mov     edx, 0Ah
0x14004e593  mov     r9, rdi
0x14004e596  mov     [rsp+58h+var_38], ebx
0x14004e59a  call    WPP_SF_qd
0x14004e59f  jmp     short loc_14004E52E
```
