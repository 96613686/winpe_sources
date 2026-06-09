# DrDeleteConnection

- ea: `0x1400190e8`
- end: `0x140019218`
- name: `DrDeleteConnection`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400190e8`

## import_xrefs

- `rdbss!RxFinalizeConnection` at `0x14001918e`
- `rdbss!RxFinalizeConnection` at `0x14001918e`

## pseudocode

```c
__int64 __fastcall DrDeleteConnection(__int64 a1, int a2, _BYTE *a3)
{
  __int64 v5; // rdi
  int v6; // ebx
  LOGICAL v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // ebx

  v5 = *(_QWORD *)(a1 + 72);
  v6 = *(_DWORD *)(a1 + 120) & 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
  if ( v6 )
  {
    if ( v5 )
    {
      v8 = 1;
      if ( !a2 )
        v8 = 255;
      v9 = RxFinalizeConnection(*(PNET_ROOT *)(*(_QWORD *)(v5 + 40) + 32LL), *(PV_NET_ROOT *)(v5 + 40), v8);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids, v9);
    }
    else
    {
      return (unsigned int)-1073741808;
    }
    return v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
    *a3 = 1;
    return 3225485315LL;
  }
}

```

## disassembly

```asm
0x1400190e8  push    rbx
0x1400190ea  push    rsi
0x1400190eb  push    rdi
0x1400190ec  push    r14
0x1400190ee  push    r15
0x1400190f0  sub     rsp, 30h
0x1400190f4  mov     rsi, r8
0x1400190f7  mov     r14d, edx
0x1400190fa  mov     [rsp+58h+var_38], 0C0000001h
0x140019102  mov     rdi, [rcx+48h]
0x140019106  mov     ebx, [rcx+78h]
0x140019109  and     ebx, 2
0x14001910c  lea     r15, WPP_GLOBAL_Control
0x140019113  mov     rcx, cs:WPP_GLOBAL_Control
0x14001911a  cmp     rcx, r15
0x14001911d  jz      short loc_14001913A
0x14001911f  cmp     byte ptr [rcx+29h], 4
0x140019123  jb      short loc_14001913A
0x140019125  mov     edx, 20h ; ' '
0x14001912a  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x140019131  mov     rcx, [rcx+18h]
0x140019135  call    WPP_SF_
0x14001913a  test    ebx, ebx
0x14001913c  jnz     short loc_140019170
0x14001913e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019145  cmp     rcx, r15
0x140019148  jz      short loc_140019163
0x14001914a  cmp     byte ptr [rcx+29h], 4
0x14001914e  jb      short loc_140019163
0x140019150  lea     edx, [rbx+21h]
0x140019153  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001915a  mov     rcx, [rcx+18h]
0x14001915e  call    WPP_SF_
0x140019163  mov     byte ptr [rsi], 1
0x140019166  mov     eax, 0C0410003h
0x14001916b  jmp     loc_14001920B
0x140019170  test    rdi, rdi
0x140019173  jz      short loc_1400191CC
0x140019175  mov     rdx, [rdi+28h]; VNetRoot
0x140019179  mov     rcx, [rdx+20h]; NetRoot
0x14001917d  test    r14d, r14d
0x140019180  mov     r8d, 1
0x140019186  jnz     short loc_14001918E
0x140019188  mov     r8d, 0FFh; ForceFilesClosed
0x14001918e  call    cs:__imp_RxFinalizeConnection
0x140019195  nop     dword ptr [rax+rax+00h]
0x14001919a  mov     [rsp+58h+var_38], eax
0x14001919e  mov     ebx, eax
0x1400191a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191a7  cmp     rcx, r15
0x1400191aa  jz      short loc_1400191D5
0x1400191ac  cmp     byte ptr [rcx+29h], 4
0x1400191b0  jb      short loc_1400191D5
0x1400191b2  mov     edx, 22h ; '"'
0x1400191b7  mov     r9d, eax
0x1400191ba  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x1400191c1  mov     rcx, [rcx+18h]
0x1400191c5  call    WPP_SF_d
0x1400191ca  jmp     short loc_1400191D5
0x1400191cc  mov     ebx, 0C0000010h
0x1400191d1  mov     [rsp+58h+var_38], ebx
0x1400191d5  jmp     short loc_140019209
0x1400191d7  lea     rax, WPP_GLOBAL_Control
0x1400191de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191e5  cmp     rcx, rax
0x1400191e8  jz      short loc_140019205
0x1400191ea  cmp     byte ptr [rcx+29h], 4
0x1400191ee  jb      short loc_140019205
0x1400191f0  mov     edx, 23h ; '#'
0x1400191f5  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x1400191fc  mov     rcx, [rcx+18h]
0x140019200  call    WPP_SF_
0x140019205  mov     ebx, [rsp+58h+var_38]
0x140019209  mov     eax, ebx
0x14001920b  add     rsp, 30h
0x14001920f  pop     r15
0x140019211  pop     r14
0x140019213  pop     rdi
0x140019214  pop     rsi
0x140019215  pop     rbx
0x140019216  retn
```
