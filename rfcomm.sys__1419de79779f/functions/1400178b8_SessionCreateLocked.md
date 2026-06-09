# SessionCreateLocked

- ea: `0x1400178b8`
- end: `0x140017aaf`
- name: `SessionCreateLocked`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017704`
- `0x140018e9c`

## callees

- `0x140003bf4`
- `0x140004b4c`
- `0x1400178b8`
- `0x14001e8f4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017a27`
- `ntoskrnl!ExAllocatePool2` at `0x14001791a`
- `ntoskrnl!ExAllocatePool2` at `0x14001791a`

## string_xrefs

- `0x14001793c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
__int64 __fastcall SessionCreateLocked(__int64 a1, __int64 a2, char a3, char *a4)
{
  __int64 Pool2; // rax
  __int64 *v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      10,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  *a4 = 0;
  Pool2 = ExAllocatePool2(64, 488, 1111713362);
  v10 = Pool2;
  if ( Pool2 )
  {
    RefObj_InitEx(
      Pool2 + 24,
      (unsigned int)SessionFree,
      1414090313,
      44,
      (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    *(_DWORD *)(v10 + 16) = 1296254546;
    *(_DWORD *)(v10 + 256) = -2147483647;
    *(_DWORD *)(v10 + 260) = -2147483647;
    *(_QWORD *)(v10 + 88) = v10 + 80;
    *(_QWORD *)(v10 + 80) = v10 + 80;
    *(_QWORD *)(v10 + 104) = v10 + 96;
    *(_QWORD *)(v10 + 96) = v10 + 96;
    *(_QWORD *)(v10 + 120) = v10 + 112;
    *(_QWORD *)(v10 + 112) = v10 + 112;
    *(_QWORD *)(v10 + 136) = v10 + 128;
    *(_QWORD *)(v10 + 128) = v10 + 128;
    *(_QWORD *)(v10 + 152) = v10 + 144;
    *(_QWORD *)(v10 + 144) = v10 + 144;
    *(_QWORD *)(v10 + 216) = v10 + 208;
    *(_QWORD *)(v10 + 208) = v10 + 208;
    *(_QWORD *)(v10 + 200) = v10 + 192;
    *(_QWORD *)(v10 + 192) = v10 + 192;
    *(_QWORD *)(v10 + 232) = v10 + 224;
    *(_QWORD *)(v10 + 224) = v10 + 224;
    *(_QWORD *)(v10 + 168) = v10 + 160;
    *(_QWORD *)(v10 + 160) = v10 + 160;
    *(_QWORD *)(v10 + 248) = v10 + 240;
    *(_QWORD *)(v10 + 240) = v10 + 240;
    *(_QWORD *)(v10 + 280) = 0;
    *(_DWORD *)(v10 + 48) = 0;
    *(_QWORD *)(v10 + 72) = a1;
    *(_QWORD *)(v10 + 264) = a2;
    *(_BYTE *)(v10 + 272) = a3;
    *(_DWORD *)(v10 + 480) = 0;
    *(_BYTE *)(v10 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 56));
    v11 = (_QWORD *)(a1 + 288);
    if ( (_QWORD *)*v11 == v11 )
      *a4 = 1;
    v9 = *(__int64 **)(a1 + 296);
    if ( (_QWORD *)*v9 != v11 )
      __fastfail(3u);
    *(_QWORD *)v10 = v11;
    *(_QWORD *)(v10 + 8) = v9;
    *v9 = v10;
    *(_QWORD *)(a1 + 296) = v10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      3,
      11,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v10,
      *a4);
  return v10;
}

```

## disassembly

```asm
0x1400178b8  push    rbx
0x1400178ba  push    rbp
0x1400178bb  push    rsi
0x1400178bc  push    rdi
0x1400178bd  push    r13
0x1400178bf  push    r14
0x1400178c1  sub     rsp, 48h
0x1400178c5  mov     rdi, r9
0x1400178c8  mov     bpl, r8b
0x1400178cb  mov     r14, rdx
0x1400178ce  mov     rsi, rcx
0x1400178d1  lea     r13, WPP_RECORDER_INITIALIZED
0x1400178d8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400178df  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x1400178e6  jz      short loc_140017907
0x1400178e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178ef  mov     r9d, 0Ah
0x1400178f5  mov     [rsp+78h+var_58], rax
0x1400178fa  mov     rcx, [rcx+40h]
0x1400178fe  lea     r8d, [r9-7]
0x140017902  call    WPP_RECORDER_SF_
0x140017907  mov     edx, 1E8h
0x14001790c  mov     byte ptr [rdi], 0
0x14001790f  mov     ecx, 40h ; '@'
0x140017914  mov     r8d, 42436652h
0x14001791a  call    cs:__imp_ExAllocatePool2
0x140017921  nop     dword ptr [rax+rax+00h]
0x140017926  mov     rbx, rax
0x140017929  test    rax, rax
0x14001792c  jz      loc_140017A63
0x140017932  lea     rcx, [rax+18h]
0x140017936  mov     r9d, 2Ch ; ','
0x14001793c  lea     rax, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140017943  mov     r8d, 54494E49h
0x140017949  lea     rdx, SessionFree
0x140017950  mov     [rsp+78h+var_58], rax
0x140017955  call    RefObj_InitEx
0x14001795a  mov     eax, 80000001h
0x14001795f  mov     dword ptr [rbx+10h], 4D434652h
0x140017966  mov     [rbx+100h], eax
0x14001796c  lea     rcx, [rbx+38h]; SpinLock
0x140017970  mov     [rbx+104h], eax
0x140017976  lea     rax, [rbx+50h]
0x14001797a  mov     [rax+8], rax
0x14001797e  mov     [rax], rax
0x140017981  lea     rax, [rbx+60h]
0x140017985  mov     [rax+8], rax
0x140017989  mov     [rax], rax
0x14001798c  lea     rax, [rbx+70h]
0x140017990  mov     [rax+8], rax
0x140017994  mov     [rax], rax
0x140017997  lea     rax, [rbx+80h]
0x14001799e  mov     [rax+8], rax
0x1400179a2  mov     [rax], rax
0x1400179a5  lea     rax, [rbx+90h]
0x1400179ac  mov     [rax+8], rax
0x1400179b0  mov     [rax], rax
0x1400179b3  lea     rax, [rbx+0D0h]
0x1400179ba  mov     [rax+8], rax
0x1400179be  mov     [rax], rax
0x1400179c1  lea     rax, [rbx+0C0h]
0x1400179c8  mov     [rax+8], rax
0x1400179cc  mov     [rax], rax
0x1400179cf  lea     rax, [rbx+0E0h]
0x1400179d6  mov     [rax+8], rax
0x1400179da  mov     [rax], rax
0x1400179dd  lea     rax, [rbx+0A0h]
0x1400179e4  mov     [rax+8], rax
0x1400179e8  mov     [rax], rax
0x1400179eb  lea     rax, [rbx+0F0h]
0x1400179f2  mov     [rax+8], rax
0x1400179f6  mov     [rax], rax
0x1400179f9  mov     qword ptr [rbx+118h], 0
0x140017a04  mov     dword ptr [rbx+30h], 0
0x140017a0b  mov     [rbx+48h], rsi
0x140017a0f  mov     [rbx+108h], r14
0x140017a16  mov     [rbx+110h], bpl
0x140017a1d  mov     dword ptr [rbx+1E0h], 0
0x140017a27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017a2e  nop     dword ptr [rax+rax+00h]
0x140017a33  mov     [rbx+40h], al
0x140017a36  lea     rax, [rsi+120h]
0x140017a3d  cmp     [rax], rax
0x140017a40  jnz     short loc_140017A45
0x140017a42  mov     byte ptr [rdi], 1
0x140017a45  mov     rdx, [rax+8]
0x140017a49  cmp     [rdx], rax
0x140017a4c  jz      short loc_140017A55
0x140017a4e  mov     ecx, 3
0x140017a53  int     29h; Win8: RtlFailFast(ecx)
0x140017a55  mov     [rbx], rax
0x140017a58  mov     [rbx+8], rdx
0x140017a5c  mov     [rdx], rbx
0x140017a5f  mov     [rax+8], rbx
0x140017a63  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140017a6a  jz      short loc_140017A9E
0x140017a6c  movzx   eax, byte ptr [rdi]
0x140017a6f  mov     r9d, 0Bh
0x140017a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a7c  mov     [rsp+78h+var_48], eax
0x140017a80  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017a87  mov     [rsp+78h+var_50], rbx
0x140017a8c  lea     r8d, [r9-8]
0x140017a90  mov     [rsp+78h+var_58], rax
0x140017a95  mov     rcx, [rcx+40h]
0x140017a99  call    WPP_RECORDER_SF_qD
0x140017a9e  mov     rax, rbx
0x140017aa1  add     rsp, 48h
0x140017aa5  pop     r14
0x140017aa7  pop     r13
0x140017aa9  pop     rdi
0x140017aaa  pop     rsi
0x140017aab  pop     rbp
0x140017aac  pop     rbx
0x140017aad  retn
```
