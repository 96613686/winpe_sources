# BrbpReconfig

- ea: `0x14000ecd0`
- end: `0x14000ee65`
- name: `BrbpReconfig`
- size: `405`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400185c8`
- `0x14001898c`

## callees

- `0x140003bf4`
- `0x14000e094`
- `0x14000ecd0`
- `0x14000f8b0`
- `0x14001e74c`
- `0x14001fc70`

## string_xrefs

- `0x14000edde`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbpReconfig(__int64 a1, char a2, __int64 a3, char a4, __int64 a5)
{
  __int64 *v9; // rsi
  __int64 v10; // rax
  int v11; // edx
  _DWORD *v12; // rbx
  int v13; // edi

  v9 = (__int64 *)(a1 + 72);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sDDDqq(WPP_GLOBAL_Control->DeviceExtension, WORD2(a3), a3, 40);
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*v9 + 312))((unsigned int)(a2 != 0) + 33026, 1111647826);
  v12 = (_DWORD *)v10;
  if ( v10 )
  {
    *(_DWORD *)(v10 + 128) |= 0x40u;
    v13 = 0;
    *(_QWORD *)(v10 + 72) = a1;
    *(_QWORD *)(v10 + 112) = a3;
    *(_QWORD *)(v10 + 120) = a5;
    *(_DWORD *)(v10 + 192) |= 1u;
    if ( (a4 & 2) != 0 )
    {
      *(_DWORD *)(v10 + 192) |= 2u;
      *(_DWORD *)(v10 + 128) |= 0x80u;
      *(_WORD *)(v10 + 197) = 4159;
      *(_WORD *)(v10 + 203) = -1;
      *(_WORD *)(v10 + 208) = 1;
    }
    RefObj_AddRefEx(a1 + 24, 1413697091, 864, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
    BrbpCallDriverAsync(*v9, v12, (void (__fastcall *)(__int64, _DWORD *, __int64))BrbReconfigCompletion, a1, a1 + 240);
  }
  else
  {
    v13 = -1073741670;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3,
      41,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  if ( v13 >= 0 )
    return 259;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000ecd0  mov     r11, rsp
0x14000ecd3  push    rbx
0x14000ecd4  push    rbp
0x14000ecd5  push    rsi
0x14000ecd6  push    rdi
0x14000ecd7  push    r12
0x14000ecd9  push    r13
0x14000ecdb  push    r14
0x14000ecdd  push    r15
0x14000ecdf  sub     rsp, 68h
0x14000ece3  mov     r15d, r9d
0x14000ece6  mov     r14, r8
0x14000ece9  mov     bl, dl
0x14000eceb  mov     rbp, rcx
0x14000ecee  mov     r12, [rsp+0A8h+arg_20]
0x14000ecf6  lea     r13, WPP_RECORDER_INITIALIZED
0x14000ecfd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000ed04  lea     rsi, [rcx+48h]
0x14000ed08  jz      short loc_14000ED5D
0x14000ed0a  mov     r10, [rsi]
0x14000ed0d  lea     rcx, aResponse; "RESPONSE"
0x14000ed14  mov     rax, r8
0x14000ed17  mov     r9d, 28h ; '('
0x14000ed1d  shr     rax, 20h
0x14000ed21  movzx   edx, ax
0x14000ed24  test    bl, bl
0x14000ed26  lea     rax, aInitiate; "INITIATE"
0x14000ed2d  cmovz   rcx, rax
0x14000ed31  mov     rax, [r10+58h]
0x14000ed35  mov     [r11-58h], rax
0x14000ed39  mov     [r11-60h], r12
0x14000ed3d  mov     [r11-68h], r14d
0x14000ed41  mov     [rsp+0A8h+var_70], edx
0x14000ed45  mov     [r11-78h], r15d
0x14000ed49  mov     [r11-80h], rcx
0x14000ed4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed54  mov     rcx, [rcx+40h]
0x14000ed58  call    WPP_RECORDER_SF_sDDDqq
0x14000ed5d  mov     rax, [rsi]
0x14000ed60  neg     bl
0x14000ed62  mov     edx, 42426652h
0x14000ed67  sbb     ecx, ecx
0x14000ed69  neg     ecx
0x14000ed6b  mov     rax, [rax+138h]
0x14000ed72  add     ecx, 8102h
0x14000ed78  call    _guard_dispatch_icall
0x14000ed7d  mov     rbx, rax
0x14000ed80  test    rax, rax
0x14000ed83  jz      loc_14000EE13
0x14000ed89  or      dword ptr [rax+80h], 40h
0x14000ed90  xor     edi, edi
0x14000ed92  mov     [rax+48h], rbp
0x14000ed96  mov     [rax+70h], r14
0x14000ed9a  mov     [rax+78h], r12
0x14000ed9e  lea     edx, [rdi+1]
0x14000eda1  or      [rax+0C0h], edx
0x14000eda7  test    r15b, 2
0x14000edab  jz      short loc_14000EDD5
0x14000edad  or      dword ptr [rax+0C0h], 2
0x14000edb4  bts     dword ptr [rax+80h], 7
0x14000edbc  mov     word ptr [rax+0C5h], 103Fh
0x14000edc5  mov     word ptr [rax+0CBh], 0FFFFh
0x14000edce  mov     [rax+0D0h], dx
0x14000edd5  lea     rcx, [rbp+18h]
0x14000edd9  mov     edx, 54434E43h
0x14000edde  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ede5  mov     r8d, 360h
0x14000edeb  call    RefObj_AddRefEx
0x14000edf0  mov     rcx, [rsi]
0x14000edf3  lea     rax, [rbp+0F0h]
0x14000edfa  mov     r9, rbp
0x14000edfd  mov     [rsp+0A8h+var_88], rax
0x14000ee02  lea     r8, BrbReconfigCompletion
0x14000ee09  mov     rdx, rbx
0x14000ee0c  call    BrbpCallDriverAsync
0x14000ee11  jmp     short loc_14000EE18
0x14000ee13  mov     edi, 0C000009Ah
0x14000ee18  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000ee1f  jz      short loc_14000EE47
0x14000ee21  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee28  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000ee2f  mov     r9d, 29h ; ')'
0x14000ee35  mov     [rsp+0A8h+var_88], rax
0x14000ee3a  mov     rcx, [rcx+40h]
0x14000ee3e  lea     r8d, [r9-26h]
0x14000ee42  call    WPP_RECORDER_SF_
0x14000ee47  mov     eax, 103h
0x14000ee4c  test    edi, edi
0x14000ee4e  cmovns  edi, eax
0x14000ee51  mov     eax, edi
0x14000ee53  add     rsp, 68h
0x14000ee57  pop     r15
0x14000ee59  pop     r14
0x14000ee5b  pop     r13
0x14000ee5d  pop     r12
0x14000ee5f  pop     rdi
0x14000ee60  pop     rsi
0x14000ee61  pop     rbp
0x14000ee62  pop     rbx
0x14000ee63  retn
```
