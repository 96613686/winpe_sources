# ClDeregisterSapComplete

- ea: `0x140006a50`
- end: `0x140006b71`
- name: `ClDeregisterSapComplete`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006080`

## callees

- `0x140006430`
- `0x140006a50`
- `0x14000a290`
- `0x14000a68c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a7c`
- `NDIS!NdisClCloseAddressFamily` at `0x140006ab9`
- `NDIS!NdisClCloseAddressFamily` at `0x140006ab9`
- `NDIS!NdisClNotifyCloseAddressFamilyComplete` at `0x140006b31`
- `NDIS!NdisClNotifyCloseAddressFamilyComplete` at `0x140006b31`

## pseudocode

```c
void __fastcall ClDeregisterSapComplete(int a1, __int64 a2)
{
  KIRQL v3; // al
  unsigned int v4; // edx
  NDIS_STATUS v5; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a2, a1);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 88));
  v4 = *(_DWORD *)(a2 + 24) & 0xFFFFFEFD;
  *(_BYTE *)(a2 + 96) = v3;
  *(_DWORD *)(a2 + 24) = v4 | 8;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 88), v3);
  if ( (*(_DWORD *)(a2 + 24) & 0x400) != 0 )
    NdisClNotifyCloseAddressFamilyComplete(*(NDIS_HANDLE *)(a2 + 56), 0);
  v5 = NdisClCloseAddressFamily(*(NDIS_HANDLE *)(a2 + 56));
  if ( v5 != 259 )
    ClCloseAfComplete(v5, (_QWORD *)a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x140006a50  mov     [rsp+arg_0], rbx
0x140006a55  mov     [rsp+arg_8], rbp
0x140006a5a  push    rdi
0x140006a5b  sub     rsp, 30h
0x140006a5f  mov     rdi, rdx
0x140006a62  mov     r8d, ecx
0x140006a65  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a6c  lea     rbp, WPP_GLOBAL_Control
0x140006a73  cmp     rcx, rbp
0x140006a76  jnz     short loc_140006AF2
0x140006a78  lea     rcx, [rdi+58h]; SpinLock
0x140006a7c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006a83  nop     dword ptr [rax+rax+00h]
0x140006a88  mov     edx, [rdi+18h]
0x140006a8b  lea     rcx, [rdi+58h]; SpinLock
0x140006a8f  and     edx, 0FFFFFEFDh
0x140006a95  mov     [rdi+60h], al
0x140006a98  or      edx, 8
0x140006a9b  mov     [rdi+18h], edx
0x140006a9e  mov     dl, al; NewIrql
0x140006aa0  call    cs:__imp_KeReleaseSpinLock
0x140006aa7  nop     dword ptr [rax+rax+00h]
0x140006aac  test    dword ptr [rdi+18h], 400h
0x140006ab3  jnz     short loc_140006B2B
0x140006ab5  mov     rcx, [rdi+38h]; NdisAfHandle
0x140006ab9  call    cs:__imp_NdisClCloseAddressFamily
0x140006ac0  nop     dword ptr [rax+rax+00h]
0x140006ac5  cmp     eax, 103h
0x140006aca  jnz     short loc_140006B42
0x140006acc  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ad3  cmp     rcx, rbp
0x140006ad6  jz      short loc_140006AE1
0x140006ad8  test    dword ptr [rcx+2Ch], 8000h
0x140006adf  jnz     short loc_140006B51
0x140006ae1  mov     rbx, [rsp+38h+arg_0]
0x140006ae6  mov     rbp, [rsp+38h+arg_8]
0x140006aeb  add     rsp, 30h
0x140006aef  pop     rdi
0x140006af0  retn
0x140006af2  test    dword ptr [rcx+2Ch], 8000h
0x140006af9  jz      loc_140006A78
0x140006aff  cmp     byte ptr [rcx+29h], 5
0x140006b03  jb      loc_140006A78
0x140006b09  mov     rcx, [rcx+18h]
0x140006b0d  mov     edx, 17h
0x140006b12  mov     [rsp+38h+var_18], r8d
0x140006b17  mov     r9, rdi
0x140006b1a  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006b21  call    WPP_SF_qD
0x140006b26  jmp     loc_140006A78
0x140006b2b  mov     rcx, [rdi+38h]; NdisAfHandle
0x140006b2f  xor     edx, edx; Status
0x140006b31  call    cs:__imp_NdisClNotifyCloseAddressFamilyComplete
0x140006b38  nop     dword ptr [rax+rax+00h]
0x140006b3d  jmp     loc_140006AB5
0x140006b42  mov     rdx, rdi
0x140006b45  mov     ecx, eax
0x140006b47  call    ClCloseAfComplete
0x140006b4c  jmp     loc_140006ACC
0x140006b51  cmp     byte ptr [rcx+29h], 5
0x140006b55  jb      short loc_140006AE1
0x140006b57  mov     rcx, [rcx+18h]
0x140006b5b  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006b62  mov     edx, 18h
0x140006b67  call    WPP_SF_
0x140006b6c  jmp     loc_140006AE1
```
