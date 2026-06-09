# SendControlFrame

- ea: `0x140018054`
- end: `0x14001810c`
- name: `SendControlFrame`
- size: `184`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140015e70`
- `0x140016414`
- `0x1400165a0`
- `0x140016734`
- `0x1400169a4`
- `0x140016f4c`
- `0x14001707c`
- `0x140017204`
- `0x140017550`

## callees

- `0x140002bd8`
- `0x140005ef0`
- `0x140014e50`
- `0x140018054`

## pseudocode

```c
void __fastcall SendControlFrame(__int64 a1, _BYTE *a2)
{
  unsigned int (__fastcall **v4)(_QWORD, void *); // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Au,
      (__int64)WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  v4 = (unsigned int (__fastcall **)(_QWORD, void *))SstpFsmGlobalInfo;
  a2[8] = 1;
  *(_QWORD *)a2 = 0;
  if ( !v4[14](*(_QWORD *)(a1 + 136), a2) )
    FsmTpiControlFrameSendComplete(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Bu,
      (__int64)WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140018054  mov     [rsp+arg_0], rbx
0x140018059  mov     [rsp+arg_8], rbp
0x14001805e  push    rdi
0x14001805f  sub     rsp, 20h
0x140018063  mov     rbx, rdx
0x140018066  mov     rdi, rcx
0x140018069  mov     rcx, cs:WPP_GLOBAL_Control
0x140018070  lea     rbp, WPP_GLOBAL_Control
0x140018077  cmp     rcx, rbp
0x14001807a  jz      short loc_14001809D
0x14001807c  mov     eax, [rcx+2Ch]
0x14001807f  and     eax, 84h
0x140018084  cmp     al, 84h
0x140018086  jnz     short loc_14001809D
0x140018088  mov     rcx, [rcx+18h]
0x14001808c  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140018093  mov     edx, 1Ah
0x140018098  call    WPP_SF_
0x14001809d  mov     rax, cs:SstpFsmGlobalInfo
0x1400180a4  mov     rdx, rbx
0x1400180a7  mov     byte ptr [rbx+8], 1
0x1400180ab  mov     qword ptr [rbx], 0
0x1400180b2  mov     rcx, [rdi+88h]
0x1400180b9  mov     rax, [rax+70h]
0x1400180bd  call    _guard_dispatch_icall
0x1400180c2  test    eax, eax
0x1400180c4  jnz     short loc_1400180CE
0x1400180c6  mov     rcx, rbx; Entry
0x1400180c9  call    FsmTpiControlFrameSendComplete
0x1400180ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180d5  cmp     rcx, rbp
0x1400180d8  jz      short loc_1400180FB
0x1400180da  mov     eax, [rcx+2Ch]
0x1400180dd  and     eax, 84h
0x1400180e2  cmp     al, 84h
0x1400180e4  jnz     short loc_1400180FB
0x1400180e6  mov     rcx, [rcx+18h]
0x1400180ea  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400180f1  mov     edx, 1Bh
0x1400180f6  call    WPP_SF_
0x1400180fb  mov     rbx, [rsp+28h+arg_0]
0x140018100  mov     rbp, [rsp+28h+arg_8]
0x140018105  add     rsp, 20h
0x140018109  pop     rdi
0x14001810a  retn
```
