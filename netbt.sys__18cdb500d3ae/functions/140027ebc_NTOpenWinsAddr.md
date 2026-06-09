# NTOpenWinsAddr

- ea: `0x140027ebc`
- end: `0x14002803a`
- name: `NTOpenWinsAddr`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14004b7a0`

## callees

- `0x140027ebc`
- `0x14002ee74`
- `0x140031440`
- `0x1400400a4`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x140027ee2`
- `ntoskrnl!MmLockPagableDataSection` at `0x140027ee2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027f99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027f99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027fd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027fd5`
- `ntoskrnl!ExAllocatePool2` at `0x140027f2d`
- `ntoskrnl!ExAllocatePool2` at `0x140027f2d`

## pseudocode

```c
__int64 __fastcall NTOpenWinsAddr(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rsi
  void *Pool2; // rax
  __int64 v9; // rbx
  __int64 DeviceWithIPAddress; // rax
  int v11; // edx
  KIRQL v12; // r11
  __int64 v13; // rcx

  if ( !NbtDiscardableCodeHandle )
  {
    NbtDiscardableCodeHandle = (__int64)MmLockPagableDataSection(NTCloseWinsAddr);
    if ( !NbtDiscardableCodeHandle )
      return 3221225473LL;
  }
  if ( pWinsInfo )
  {
    v6 = -1073741823;
  }
  else
  {
    v7 = *(_QWORD *)(a2 + 184);
    Pool2 = (void *)ExAllocatePool2(64, 96, 1987338830);
    v9 = (__int64)Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x60u);
      *(_DWORD *)(v9 + 16) = 1936615767;
      *(_QWORD *)(v9 + 8) = v9;
      *(_QWORD *)v9 = v9;
      *(_QWORD *)(v9 + 32) = v9 + 24;
      *(_QWORD *)(v9 + 24) = v9 + 24;
      *(_QWORD *)(v9 + 48) = v9 + 40;
      *(_QWORD *)(v9 + 40) = v9 + 40;
      *(_DWORD *)(v9 + 76) = dword_140039644;
      *(_DWORD *)(v9 + 84) = dword_140039644;
      *(_DWORD *)(v9 + 20) = a3;
      KeAcquireSpinLockRaiseToDpc(&SpinLock);
      DeviceWithIPAddress = GetDeviceWithIPAddress(a3);
      v11 = LastWinsSignature;
      *(_DWORD *)(v9 + 88) = LastWinsSignature;
      LastWinsSignature = v11 + 1;
      *(_QWORD *)(v9 + 56) = DeviceWithIPAddress;
      pWinsInfo = v9;
      KeReleaseSpinLock(&SpinLock, v12);
      v13 = *(_QWORD *)(v7 + 48);
      v6 = 0;
      RefreshedYet = 0;
      *(_QWORD *)(v13 + 24) = pWinsInfo;
      *(_QWORD *)(*(_QWORD *)(v7 + 48) + 32LL) = 4;
    }
    else
    {
      v6 = -1073741670;
    }
  }
  if ( (BYTE2(xmmword_140038420) & 1) != 0 )
    WPP_SF_d(1040, 10, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x140027ebc  mov     [rsp+arg_0], rbx
0x140027ec1  mov     [rsp+arg_8], rsi
0x140027ec6  push    rdi
0x140027ec7  sub     rsp, 20h
0x140027ecb  cmp     cs:NbtDiscardableCodeHandle, 0
0x140027ed3  mov     edi, r8d
0x140027ed6  mov     rbx, rdx
0x140027ed9  jnz     short loc_140027F04
0x140027edb  lea     rcx, NTCloseWinsAddr; AddressWithinSection
0x140027ee2  call    cs:__imp_MmLockPagableDataSection
0x140027ee9  nop     dword ptr [rax+rax+00h]
0x140027eee  mov     cs:NbtDiscardableCodeHandle, rax
0x140027ef5  test    rax, rax
0x140027ef8  jnz     short loc_140027F04
0x140027efa  mov     eax, 0C0000001h
0x140027eff  jmp     loc_140028029
0x140027f04  cmp     cs:pWinsInfo, 0
0x140027f0c  jz      short loc_140027F18
0x140027f0e  mov     ebx, 0C0000001h
0x140027f13  jmp     loc_140028005
0x140027f18  mov     rsi, [rbx+0B8h]
0x140027f1f  mov     edx, 60h ; '`'
0x140027f24  mov     r8d, 7674624Eh
0x140027f2a  lea     ecx, [rdx-20h]
0x140027f2d  call    cs:__imp_ExAllocatePool2
0x140027f34  nop     dword ptr [rax+rax+00h]
0x140027f39  mov     rbx, rax
0x140027f3c  test    rax, rax
0x140027f3f  jnz     short loc_140027F4B
0x140027f41  mov     ebx, 0C000009Ah
0x140027f46  jmp     loc_140028005
0x140027f4b  xor     edx, edx; Val
0x140027f4d  mov     rcx, rbx; void *
0x140027f50  lea     r8d, [rdx+60h]; Size
0x140027f54  call    memset
0x140027f59  mov     dword ptr [rbx+10h], 736E6957h
0x140027f60  lea     rax, [rbx+18h]
0x140027f64  mov     [rbx+8], rbx
0x140027f68  lea     rcx, SpinLock; SpinLock
0x140027f6f  mov     [rbx], rbx
0x140027f72  mov     [rax+8], rax
0x140027f76  mov     [rax], rax
0x140027f79  lea     rax, [rbx+28h]
0x140027f7d  mov     [rax+8], rax
0x140027f81  mov     [rax], rax
0x140027f84  mov     eax, cs:dword_140039644
0x140027f8a  mov     [rbx+4Ch], eax
0x140027f8d  mov     eax, cs:dword_140039644
0x140027f93  mov     [rbx+54h], eax
0x140027f96  mov     [rbx+14h], edi
0x140027f99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027fa0  nop     dword ptr [rax+rax+00h]
0x140027fa5  mov     ecx, edi
0x140027fa7  mov     r11b, al
0x140027faa  call    GetDeviceWithIPAddress
0x140027faf  mov     edx, cs:LastWinsSignature
0x140027fb5  lea     rcx, SpinLock; SpinLock
0x140027fbc  mov     [rbx+58h], edx
0x140027fbf  inc     edx
0x140027fc1  mov     cs:LastWinsSignature, edx
0x140027fc7  mov     dl, r11b; NewIrql
0x140027fca  mov     [rbx+38h], rax
0x140027fce  mov     cs:pWinsInfo, rbx
0x140027fd5  call    cs:__imp_KeReleaseSpinLock
0x140027fdc  nop     dword ptr [rax+rax+00h]
0x140027fe1  mov     rcx, [rsi+30h]
0x140027fe5  xor     ebx, ebx
0x140027fe7  mov     rax, cs:pWinsInfo
0x140027fee  mov     cs:RefreshedYet, 0
0x140027ff5  mov     [rcx+18h], rax
0x140027ff9  mov     rax, [rsi+30h]
0x140027ffd  mov     qword ptr [rax+20h], 4
0x140028005  test    byte ptr cs:xmmword_140038420+2, 1
0x14002800c  jz      short loc_140028027
0x14002800e  mov     edx, 0Ah
0x140028013  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x14002801a  mov     ecx, 410h
0x14002801f  mov     r9d, ebx
0x140028022  call    WPP_SF_d
0x140028027  mov     eax, ebx
0x140028029  mov     rbx, [rsp+28h+arg_0]
0x14002802e  mov     rsi, [rsp+28h+arg_8]
0x140028033  add     rsp, 20h
0x140028037  pop     rdi
0x140028038  retn
```
