# lldpProtOpenAdapterComplete

- ea: `0x140012790`
- end: `0x140012806`
- name: `lldpProtOpenAdapterComplete`
- size: `118`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011e30`

## callees

- `0x140004b00`
- `0x14001186c`
- `0x140012640`
- `0x140012730`
- `0x140012790`

## pseudocode

```c
void __fastcall lldpProtOpenAdapterComplete(_QWORD *P, unsigned int a2)
{
  _QWORD *i; // rbx

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_acd65dca497b3543092d0321cbce568c_Traceguids, a2);
    P[1] = 0;
    lldpDetachAllPortsFromBinding(P);
    lldpCleanupBinding(P);
  }
  else
  {
    for ( i = (_QWORD *)P[15]; i; i = (_QWORD *)i[5] )
      lldpActivatePort(i);
  }
}

```

## disassembly

```asm
0x140012790  push    rbx
0x140012792  sub     rsp, 20h
0x140012796  mov     r9d, edx
0x140012799  mov     rbx, rcx
0x14001279c  test    edx, edx
0x14001279e  jz      short loc_1400127E8
0x1400127a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127a7  lea     rax, WPP_GLOBAL_Control
0x1400127ae  cmp     rcx, rax
0x1400127b1  jz      short loc_1400127CE
0x1400127b3  cmp     byte ptr [rcx+29h], 2
0x1400127b7  jb      short loc_1400127CE
0x1400127b9  mov     rcx, [rcx+18h]
0x1400127bd  lea     r8, WPP_acd65dca497b3543092d0321cbce568c_Traceguids
0x1400127c4  mov     edx, 0Dh
0x1400127c9  call    WPP_SF_d
0x1400127ce  mov     rcx, rbx
0x1400127d1  mov     qword ptr [rbx+8], 0
0x1400127d9  call    lldpDetachAllPortsFromBinding
0x1400127de  mov     rcx, rbx; P
0x1400127e1  call    lldpCleanupBinding
0x1400127e6  jmp     short loc_1400127FF
0x1400127e8  mov     rbx, [rcx+78h]
0x1400127ec  jmp     short loc_1400127FA
0x1400127ee  mov     rcx, rbx; Context
0x1400127f1  call    lldpActivatePort
0x1400127f6  mov     rbx, [rbx+28h]
0x1400127fa  test    rbx, rbx
0x1400127fd  jnz     short loc_1400127EE
0x1400127ff  add     rsp, 20h
0x140012803  pop     rbx
0x140012804  retn
```
