# RfcommSendUA

- ea: `0x140015688`
- end: `0x1400157d6`
- name: `RfcommSendUA`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fc00`
- `0x14001127c`
- `0x140012590`
- `0x140019b64`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140015688`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400156f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400156f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001577e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001577e`

## string_xrefs

- `0x140015765`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommSendUA(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  char v5; // al
  __int64 v6; // rax
  __int64 v7; // rsi
  unsigned int v8; // edi
  int v9; // edx
  unsigned int v11; // [rsp+90h] [rbp+8h] BYREF

  v11 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      76,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v4 = a2 + 168;
  if ( !a2 )
    v4 = a1 + 208;
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( a2 )
    v5 = *(_BYTE *)(a2 + 184);
  else
    v5 = 0;
  v6 = RfcommFrameAllocLockedEx(a1, (__int64 *)a2, 99, 0, v5, 0, &v11, v4, 0);
  v7 = v6;
  v8 = v6 == 0 ? 0xC000009A : 0;
  if ( v6 )
    RefObj_AddRefEx(v6 + 24, 1346917442, 3546, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v7 )
    RfcommFrameWrite(a1, v7);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      77,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v8);
  return v8;
}

```

## disassembly

```asm
0x140015688  mov     rax, rsp
0x14001568b  push    rbx
0x14001568c  push    rbp
0x14001568d  push    rsi
0x14001568e  push    rdi
0x14001568f  push    r13
0x140015691  push    r15
0x140015693  sub     rsp, 58h
0x140015697  mov     rdi, rdx
0x14001569a  mov     dword ptr [rax+8], 0
0x1400156a1  mov     rbx, rcx
0x1400156a4  lea     r15, WPP_RECORDER_INITIALIZED
0x1400156ab  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400156b2  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400156b9  jz      short loc_1400156D9
0x1400156bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156c2  mov     r9d, 4Ch ; 'L'
0x1400156c8  mov     [rax-68h], r13
0x1400156cc  mov     rcx, [rcx+40h]
0x1400156d0  lea     r8d, [r9-49h]
0x1400156d4  call    WPP_RECORDER_SF_
0x1400156d9  lea     rax, [rbx+0D0h]
0x1400156e0  test    rdi, rdi
0x1400156e3  lea     rsi, [rdi+0A8h]
0x1400156ea  lea     rcx, [rbx+38h]; SpinLock
0x1400156ee  cmovz   rsi, rax
0x1400156f2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400156f9  nop     dword ptr [rax+rax+00h]
0x1400156fe  mov     [rbx+40h], al
0x140015701  test    rdi, rdi
0x140015704  jz      short loc_14001570E
0x140015706  mov     al, [rdi+0B8h]
0x14001570c  jmp     short loc_140015710
0x14001570e  xor     al, al
0x140015710  mov     [rsp+88h+var_48], 0
0x140015715  lea     rcx, [rsp+88h+arg_0]
0x14001571d  mov     [rsp+88h+var_50], rsi
0x140015722  xor     r9d, r9d
0x140015725  mov     [rsp+88h+var_58], rcx
0x14001572a  mov     r8b, 63h ; 'c'
0x14001572d  mov     [rsp+88h+var_60], 0
0x140015735  mov     rcx, rbx
0x140015738  mov     rdx, rdi
0x14001573b  mov     byte ptr [rsp+88h+var_68], al
0x14001573f  call    RfcommFrameAllocLockedEx
0x140015744  mov     rcx, rax
0x140015747  mov     rsi, rax
0x14001574a  neg     rcx
0x14001574d  sbb     edi, edi
0x14001574f  not     edi
0x140015751  and     edi, 0C000009Ah
0x140015757  test    rax, rax
0x14001575a  jz      short loc_140015777
0x14001575c  lea     rcx, [rax+18h]
0x140015760  mov     edx, 50485442h
0x140015765  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001576c  mov     r8d, 0DDAh
0x140015772  call    RefObj_AddRefEx
0x140015777  mov     dl, [rbx+40h]; NewIrql
0x14001577a  lea     rcx, [rbx+38h]; SpinLock
0x14001577e  call    cs:__imp_KeReleaseSpinLock
0x140015785  nop     dword ptr [rax+rax+00h]
0x14001578a  test    rsi, rsi
0x14001578d  jz      short loc_14001579A
0x14001578f  mov     rdx, rsi
0x140015792  mov     rcx, rbx
0x140015795  call    RfcommFrameWrite
0x14001579a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400157a1  jz      short loc_1400157C6
0x1400157a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157aa  mov     r9d, 4Dh ; 'M'
0x1400157b0  mov     [rsp+88h+var_60], edi
0x1400157b4  mov     [rsp+88h+var_68], r13
0x1400157b9  mov     rcx, [rcx+40h]
0x1400157bd  lea     r8d, [r9-4Ah]
0x1400157c1  call    WPP_RECORDER_SF_d
0x1400157c6  mov     eax, edi
0x1400157c8  add     rsp, 58h
0x1400157cc  pop     r15
0x1400157ce  pop     r13
0x1400157d0  pop     rdi
0x1400157d1  pop     rsi
0x1400157d2  pop     rbp
0x1400157d3  pop     rbx
0x1400157d4  retn
```
