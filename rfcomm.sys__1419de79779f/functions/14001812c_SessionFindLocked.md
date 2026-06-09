# SessionFindLocked

- ea: `0x14001812c`
- end: `0x14001821d`
- name: `SessionFindLocked`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017704`
- `0x140018e9c`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x14001812c`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400181d2`

## string_xrefs

- `0x1400181b9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
__int64 *__fastcall SessionFindLocked(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 *v4; // rdi
  __int64 *v5; // rcx
  __int64 *v6; // rbx

  v2 = a2;
  v4 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      12,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  v5 = (__int64 *)(a1 + 288);
  v6 = *(__int64 **)(a1 + 288);
  if ( v6 != v5 )
  {
    LODWORD(a2) = *(unsigned __int16 *)(v2 + 4);
    while ( (unsigned __int16)WORD2(v6[33]) != (_WORD)a2
         || *((_DWORD *)v6 + 66) != *(_DWORD *)v2
         || *((_DWORD *)v6 + 12) == 6 )
    {
      v6 = (__int64 *)*v6;
      if ( v6 == v5 )
        goto LABEL_11;
    }
    v4 = v6;
    RefObj_AddRefEx(v6 + 3, 1145981254, 149, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    *((_BYTE *)v6 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v6 + 7);
  }
LABEL_11:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      13,
      (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids,
      v4);
  return v4;
}

```

## disassembly

```asm
0x14001812c  push    rbx
0x14001812e  push    rbp
0x14001812f  push    rsi
0x140018130  push    rdi
0x140018131  push    r15
0x140018133  sub     rsp, 30h
0x140018137  mov     rsi, rdx
0x14001813a  mov     rbx, rcx
0x14001813d  xor     edi, edi
0x14001813f  lea     rbp, WPP_RECORDER_INITIALIZED
0x140018146  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001814d  lea     r15, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140018154  jz      short loc_140018173
0x140018156  mov     rcx, cs:WPP_GLOBAL_Control
0x14001815d  lea     r9d, [rdi+0Ch]
0x140018161  lea     r8d, [rdi+3]
0x140018165  mov     [rsp+58h+var_38], r15
0x14001816a  mov     rcx, [rcx+40h]
0x14001816e  call    WPP_RECORDER_SF_
0x140018173  lea     rcx, [rbx+120h]
0x14001817a  mov     rbx, [rcx]
0x14001817d  cmp     rbx, rcx
0x140018180  jz      short loc_1400181E1
0x140018182  movzx   edx, word ptr [rsi+4]
0x140018186  mov     rax, [rbx+108h]
0x14001818d  shr     rax, 20h
0x140018191  cmp     ax, dx
0x140018194  jnz     short loc_1400181A6
0x140018196  mov     eax, [rsi]
0x140018198  cmp     [rbx+108h], eax
0x14001819e  jnz     short loc_1400181A6
0x1400181a0  cmp     dword ptr [rbx+30h], 6
0x1400181a4  jnz     short loc_1400181B0
0x1400181a6  mov     rbx, [rbx]
0x1400181a9  cmp     rbx, rcx
0x1400181ac  jnz     short loc_140018186
0x1400181ae  jmp     short loc_1400181E1
0x1400181b0  lea     rcx, [rbx+18h]
0x1400181b4  mov     edx, 444E4946h
0x1400181b9  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400181c0  mov     r8d, 95h
0x1400181c6  mov     rdi, rbx
0x1400181c9  call    RefObj_AddRefEx
0x1400181ce  lea     rcx, [rbx+38h]; SpinLock
0x1400181d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400181d9  nop     dword ptr [rax+rax+00h]
0x1400181de  mov     [rbx+40h], al
0x1400181e1  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400181e8  jz      short loc_14001820E
0x1400181ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181f1  mov     r9d, 0Dh
0x1400181f7  mov     [rsp+58h+var_30], rdi
0x1400181fc  mov     [rsp+58h+var_38], r15
0x140018201  mov     rcx, [rcx+40h]
0x140018205  lea     r8d, [r9-0Ah]
0x140018209  call    WPP_RECORDER_SF_q
0x14001820e  mov     rax, rdi
0x140018211  add     rsp, 30h
0x140018215  pop     r15
0x140018217  pop     rdi
0x140018218  pop     rsi
0x140018219  pop     rbp
0x14001821a  pop     rbx
0x14001821b  retn
```
