# PppoeCmIncomingCallComplete

- ea: `0x1400182e0`
- end: `0x1400183c0`
- name: `PppoeCmIncomingCallComplete`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140016534`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140002e0c`
- `0x140016014`
- `0x1400182e0`

## pseudocode

```c
void __fastcall PppoeCmIncomingCallComplete(unsigned int a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
  }
  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
    }
  }
  else
  {
    a1 = FsmAnswerCall(a2);
    if ( !a1 )
      return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
  }
  TpCmCallCleanup(a2, 0);
}

```

## disassembly

```asm
0x1400182e0  mov     [rsp+arg_0], rbx
0x1400182e5  mov     [rsp+arg_8], rbp
0x1400182ea  push    rdi
0x1400182eb  sub     rsp, 20h
0x1400182ef  mov     rdi, rdx
0x1400182f2  mov     ebx, ecx
0x1400182f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182fb  lea     rbp, WPP_GLOBAL_Control
0x140018302  cmp     rcx, rbp
0x140018305  jz      short loc_14001832B
0x140018307  test    dword ptr [rcx+2Ch], 8000h
0x14001830e  jz      short loc_14001832B
0x140018310  cmp     byte ptr [rcx+29h], 2
0x140018314  jb      short loc_14001832B
0x140018316  mov     rcx, [rcx+18h]
0x14001831a  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140018321  mov     edx, 22h ; '"'
0x140018326  call    WPP_SF_
0x14001832b  test    ebx, ebx
0x14001832d  jz      short loc_140018364
0x14001832f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018336  cmp     rcx, rbp
0x140018339  jz      short loc_140018372
0x14001833b  test    dword ptr [rcx+2Ch], 8000h
0x140018342  jz      short loc_140018372
0x140018344  cmp     byte ptr [rcx+29h], 1
0x140018348  jb      short loc_140018372
0x14001834a  mov     rcx, [rcx+18h]
0x14001834e  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140018355  mov     edx, 23h ; '#'
0x14001835a  mov     r9d, ebx
0x14001835d  call    WPP_SF_d
0x140018362  jmp     short loc_140018372
0x140018364  mov     rcx, rdi
0x140018367  call    FsmAnswerCall
0x14001836c  mov     ebx, eax
0x14001836e  test    eax, eax
0x140018370  jz      short loc_1400183AF
0x140018372  mov     rcx, cs:WPP_GLOBAL_Control
0x140018379  cmp     rcx, rbp
0x14001837c  jz      short loc_1400183A5
0x14001837e  test    dword ptr [rcx+2Ch], 8000h
0x140018385  jz      short loc_1400183A5
0x140018387  cmp     byte ptr [rcx+29h], 1
0x14001838b  jb      short loc_1400183A5
0x14001838d  mov     rcx, [rcx+18h]
0x140018391  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140018398  mov     edx, 24h ; '$'
0x14001839d  mov     r9d, ebx
0x1400183a0  call    WPP_SF_d
0x1400183a5  xor     edx, edx
0x1400183a7  mov     rcx, rdi
0x1400183aa  call    TpCmCallCleanup
0x1400183af  mov     rbx, [rsp+28h+arg_0]
0x1400183b4  mov     rbp, [rsp+28h+arg_8]
0x1400183b9  add     rsp, 20h
0x1400183bd  pop     rdi
0x1400183be  retn
```
