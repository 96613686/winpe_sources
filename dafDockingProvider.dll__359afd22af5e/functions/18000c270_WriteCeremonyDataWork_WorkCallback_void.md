# WriteCeremonyDataWork::WorkCallback(void)

- ea: `0x18000c270`
- end: `0x18000c301`
- name: `?WorkCallback@WriteCeremonyDataWork@@UEAAXXZ`
- size: `145`
- prototype: `void __fastcall(WriteCeremonyDataWork *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c270`
- `0x18000c308`
- `0x18001f010`

## pseudocode

```c
void __fastcall WriteCeremonyDataWork::WorkCallback(WriteCeremonyDataWork *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1), 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
}

```

## disassembly

```asm
0x18000c270  mov     [rsp+arg_0], rbx
0x18000c275  push    rdi
0x18000c276  sub     rsp, 20h
0x18000c27a  mov     rbx, rcx
0x18000c27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c284  lea     rdi, WPP_GLOBAL_Control
0x18000c28b  cmp     rcx, rdi
0x18000c28e  jz      short loc_18000C2B4
0x18000c290  cmp     byte ptr [rcx+19h], 4
0x18000c294  jb      short loc_18000C2B4
0x18000c296  test    byte ptr [rcx+1Ch], 1
0x18000c29a  jz      short loc_18000C2B4
0x18000c29c  mov     rcx, [rcx+10h]
0x18000c2a0  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000c2a7  mov     edx, 1Bh
0x18000c2ac  mov     r9, rbx
0x18000c2af  call    WPP_SF_q
0x18000c2b4  mov     rcx, [rbx+8]
0x18000c2b8  xor     edx, edx
0x18000c2ba  mov     rax, [rcx]
0x18000c2bd  mov     rax, [rax+18h]
0x18000c2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2cd  cmp     rcx, rdi
0x18000c2d0  jz      short loc_18000C2F6
0x18000c2d2  cmp     byte ptr [rcx+19h], 4
0x18000c2d6  jb      short loc_18000C2F6
0x18000c2d8  test    byte ptr [rcx+1Ch], 1
0x18000c2dc  jz      short loc_18000C2F6
0x18000c2de  mov     rcx, [rcx+10h]
0x18000c2e2  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000c2e9  mov     edx, 1Ch
0x18000c2ee  mov     r9, rbx
0x18000c2f1  call    WPP_SF_q
0x18000c2f6  mov     rbx, [rsp+28h+arg_0]
0x18000c2fb  add     rsp, 20h
0x18000c2ff  pop     rdi
0x18000c300  retn
```
