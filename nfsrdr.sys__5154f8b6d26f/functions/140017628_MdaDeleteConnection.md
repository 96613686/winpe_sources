# MdaDeleteConnection

- ea: `0x140017628`
- end: `0x14001775f`
- name: `MdaDeleteConnection`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017770`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140017628`

## import_xrefs

- `rdbss!RxFinalizeConnection` at `0x1400176e0`
- `rdbss!RxFinalizeConnection` at `0x1400176e0`

## pseudocode

```c
__int64 __fastcall MdaDeleteConnection(__int64 a1, _BYTE *a2)
{
  __int64 v3; // rdi
  unsigned __int8 *v4; // r15
  unsigned int v5; // r14d
  int v6; // ebx
  NTSTATUS v7; // ebx

  v3 = *(_QWORD *)(a1 + 72);
  v4 = *(unsigned __int8 **)(a1 + 552);
  v5 = *(_DWORD *)(a1 + 568);
  v6 = *(_DWORD *)(a1 + 120) & 2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
  if ( v6 )
  {
    if ( v5 >= 4 )
    {
      if ( v3 )
      {
        v7 = RxFinalizeConnection(*(PNET_ROOT *)(*(_QWORD *)(v3 + 40) + 32LL), *(PV_NET_ROOT *)(v3 + 40), *v4);
        if ( v7 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
        }
      }
      else
      {
        v7 = -1073741808;
      }
    }
    else
    {
      v7 = -1073741789;
    }
  }
  else
  {
    *a2 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
    v7 = -1069481981;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140017628  push    rbx
0x14001762a  push    rsi
0x14001762b  push    rdi
0x14001762c  push    r12
0x14001762e  push    r14
0x140017630  push    r15
0x140017632  sub     rsp, 38h
0x140017636  mov     rsi, rdx
0x140017639  mov     rdi, [rcx+48h]
0x14001763d  mov     r15, [rcx+228h]
0x140017644  mov     r14d, [rcx+238h]
0x14001764b  mov     ebx, [rcx+78h]
0x14001764e  and     ebx, 2
0x140017651  lea     r12, WPP_GLOBAL_Control
0x140017658  mov     rcx, cs:WPP_GLOBAL_Control
0x14001765f  cmp     rcx, r12
0x140017662  jz      short loc_140017680
0x140017664  mov     eax, [rcx+2Ch]
0x140017667  test    al, 8
0x140017669  jz      short loc_140017680
0x14001766b  mov     edx, 19h
0x140017670  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017677  mov     rcx, [rcx+18h]
0x14001767b  call    WPP_SF_
0x140017680  test    ebx, ebx
0x140017682  jnz     short loc_1400176B4
0x140017684  mov     byte ptr [rsi], 1
0x140017687  mov     rcx, cs:WPP_GLOBAL_Control
0x14001768e  cmp     rcx, r12
0x140017691  jz      short loc_1400176AD
0x140017693  mov     eax, [rcx+2Ch]
0x140017696  test    al, 8
0x140017698  jz      short loc_1400176AD
0x14001769a  lea     edx, [rbx+1Ah]
0x14001769d  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x1400176a4  mov     rcx, [rcx+18h]
0x1400176a8  call    WPP_SF_
0x1400176ad  mov     ebx, 0C0410003h
0x1400176b2  jmp     short loc_140017723
0x1400176b4  cmp     r14d, 4
0x1400176b8  jnb     short loc_1400176C1
0x1400176ba  mov     ebx, 0C0000023h
0x1400176bf  jmp     short loc_140017723
0x1400176c1  test    rdi, rdi
0x1400176c4  jnz     short loc_1400176D1
0x1400176c6  mov     ebx, 0C0000010h
0x1400176cb  mov     [rsp+68h+var_48], ebx
0x1400176cf  jmp     short loc_140017723
0x1400176d1  mov     rcx, [rdi+28h]
0x1400176d5  movzx   r8d, byte ptr [r15]; ForceFilesClosed
0x1400176d9  mov     rdx, rcx; VNetRoot
0x1400176dc  mov     rcx, [rcx+20h]; NetRoot
0x1400176e0  call    cs:__imp_RxFinalizeConnection
0x1400176e7  nop     dword ptr [rax+rax+00h]
0x1400176ec  mov     ebx, eax
0x1400176ee  mov     [rsp+68h+var_48], eax
0x1400176f2  test    eax, eax
0x1400176f4  jns     short loc_140017723
0x1400176f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176fd  cmp     rcx, r12
0x140017700  jz      short loc_140017723
0x140017702  mov     edx, [rcx+2Ch]
0x140017705  test    dl, 1
0x140017708  jz      short loc_140017723
0x14001770a  mov     edx, 1Bh
0x14001770f  mov     r9d, eax
0x140017712  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017719  mov     rcx, [rcx+18h]
0x14001771d  call    WPP_SF_d
0x140017722  nop
0x140017723  mov     rcx, cs:WPP_GLOBAL_Control
0x14001772a  cmp     rcx, r12
0x14001772d  jz      short loc_14001774E
0x14001772f  mov     eax, [rcx+2Ch]
0x140017732  test    al, 8
0x140017734  jz      short loc_14001774E
0x140017736  mov     edx, 1Ch
0x14001773b  mov     r9d, ebx
0x14001773e  lea     r8, WPP_ba892a05aac33e855608f00f5329cd3a_Traceguids
0x140017745  mov     rcx, [rcx+18h]
0x140017749  call    WPP_SF_d
0x14001774e  mov     eax, ebx
0x140017750  add     rsp, 38h
0x140017754  pop     r15
0x140017756  pop     r14
0x140017758  pop     r12
0x14001775a  pop     rdi
0x14001775b  pop     rsi
0x14001775c  pop     rbx
0x14001775d  retn
0x14003b5bd  push    rbp
0x14003b5bf  sub     rsp, 20h
0x14003b5c3  mov     rbp, rdx
0x14003b5c6  add     rsp, 20h
0x14003b5ca  pop     rbp
0x14003b5cb  retn
```
