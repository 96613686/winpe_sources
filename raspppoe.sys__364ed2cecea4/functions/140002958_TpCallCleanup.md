# TpCallCleanup

- ea: `0x140002958`
- end: `0x140002a58`
- name: `TpCallCleanup`
- size: `256`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400059a0`
- `0x140005c90`
- `0x140014884`

## callees

- `0x14000110c`
- `0x140002958`
- `0x140006b80`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x140002a0d`
- `NDIS!NdisFreeMemory` at `0x140002a0d`

## pseudocode

```c
void __fastcall TpCallCleanup(_QWORD *VirtualAddress)
{
  __int64 v2; // rcx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x34u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  v2 = VirtualAddress[93];
  if ( v2 && _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    (*(void (**)(void))(v2 + 8))();
  v3 = (_QWORD *)VirtualAddress[94];
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      *v3 = 0;
      v5 = *(unsigned __int16 *)(v3[2] + 10LL) + v3[2] + 16LL;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
        (*(void (**)(void))(v5 + 8))();
      v3 = v4;
    }
    while ( v4 );
  }
  NdisFreeMemory(VirtualAddress, 0x358u, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x35u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
}

```

## disassembly

```asm
0x140002958  mov     [rsp+arg_0], rbx
0x14000295d  mov     [rsp+arg_8], rsi
0x140002962  push    rdi
0x140002963  sub     rsp, 20h
0x140002967  mov     rbx, rcx
0x14000296a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002971  lea     rsi, WPP_GLOBAL_Control
0x140002978  cmp     rcx, rsi
0x14000297b  jz      short loc_14000299F
0x14000297d  mov     eax, [rcx+2Ch]
0x140002980  test    al, 2
0x140002982  jz      short loc_14000299F
0x140002984  cmp     byte ptr [rcx+29h], 3
0x140002988  jb      short loc_14000299F
0x14000298a  mov     rcx, [rcx+18h]
0x14000298e  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002995  mov     edx, 34h ; '4'
0x14000299a  call    WPP_SF_
0x14000299f  mov     rcx, [rbx+2E8h]
0x1400029a6  test    rcx, rcx
0x1400029a9  jz      short loc_1400029C0
0x1400029ab  or      eax, 0FFFFFFFFh
0x1400029ae  lock xadd [rcx], eax
0x1400029b2  cmp     eax, 1
0x1400029b5  jnz     short loc_1400029C0
0x1400029b7  mov     rax, [rcx+8]
0x1400029bb  call    _guard_dispatch_icall
0x1400029c0  mov     rcx, [rbx+2F0h]
0x1400029c7  test    rcx, rcx
0x1400029ca  jz      short loc_140002A02
0x1400029cc  mov     rdi, [rcx]
0x1400029cf  mov     qword ptr [rcx], 0
0x1400029d6  mov     rcx, [rcx+10h]
0x1400029da  movzx   eax, word ptr [rcx+0Ah]
0x1400029de  add     rcx, 10h
0x1400029e2  add     rcx, rax
0x1400029e5  or      eax, 0FFFFFFFFh
0x1400029e8  lock xadd [rcx], eax
0x1400029ec  cmp     eax, 1
0x1400029ef  jnz     short loc_1400029FA
0x1400029f1  mov     rax, [rcx+8]
0x1400029f5  call    _guard_dispatch_icall
0x1400029fa  mov     rcx, rdi
0x1400029fd  test    rdi, rdi
0x140002a00  jnz     short loc_1400029CC
0x140002a02  xor     r8d, r8d; MemoryFlags
0x140002a05  mov     edx, 358h; Length
0x140002a0a  mov     rcx, rbx; VirtualAddress
0x140002a0d  call    cs:__imp_NdisFreeMemory
0x140002a14  nop     dword ptr [rax+rax+00h]
0x140002a19  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a20  cmp     rcx, rsi
0x140002a23  jz      short loc_140002A47
0x140002a25  mov     eax, [rcx+2Ch]
0x140002a28  test    al, 2
0x140002a2a  jz      short loc_140002A47
0x140002a2c  cmp     byte ptr [rcx+29h], 3
0x140002a30  jb      short loc_140002A47
0x140002a32  mov     rcx, [rcx+18h]
0x140002a36  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002a3d  mov     edx, 35h ; '5'
0x140002a42  call    WPP_SF_
0x140002a47  mov     rbx, [rsp+28h+arg_0]
0x140002a4c  mov     rsi, [rsp+28h+arg_8]
0x140002a51  add     rsp, 20h
0x140002a55  pop     rdi
0x140002a56  retn
```
