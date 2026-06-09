# CscBackpatchRemainingBackpatchedFobxs

- ea: `0x14004faf4`
- end: `0x14004fbd7`
- name: `CscBackpatchRemainingBackpatchedFobxs`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140088890`

## callees

- `0x1400190ec`
- `0x14004faf4`

## import_xrefs

- `rdbss!RxIterateOnFcbOpens` at `0x14004fb39`
- `rdbss!RxIterateOnFcbOpens` at `0x14004fb39`

## pseudocode

```c
unsigned __int8 __fastcall CscBackpatchRemainingBackpatchedFobxs(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v5; // di
  int v6; // r8d
  char v8; // [rsp+28h] [rbp-10h]

  *(_QWORD *)(a3 + 128) = 0;
  *(_QWORD *)(a3 + 136) = 0;
  v8 = 0;
  v5 = 1;
  RxIterateOnFcbOpens(a1, *(_QWORD *)(a3 + 16), 0, CscBackpatchUpdateFobxStateCallback, a3, v8);
  if ( !*(_QWORD *)(a3 + 136) )
  {
    *(_BYTE *)(a3 + 144) &= 0xFCu;
    *(_DWORD *)(*(_QWORD *)(a2 + 8) + 36LL) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + 8LL);
    *(_DWORD *)(*(_QWORD *)(a2 + 8) + 4LL) &= ~0x200u;
    v5 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    if ( *(_QWORD *)(a3 + 128) )
      v6 = *(_DWORD *)(*(_QWORD *)(a3 + 16) + 164LL);
    else
      v6 = -1;
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v5, v6);
  }
  return v5;
}

```

## disassembly

```asm
0x14004faf4  mov     rax, rsp
0x14004faf7  mov     [rax+8], rbx
0x14004fafb  mov     [rax+10h], rsi
0x14004faff  push    rdi
0x14004fb00  sub     rsp, 30h
0x14004fb04  mov     rbx, r8
0x14004fb07  mov     qword ptr [r8+80h], 0
0x14004fb12  mov     rsi, rdx
0x14004fb15  mov     qword ptr [r8+88h], 0
0x14004fb20  mov     byte ptr [rax-10h], 0
0x14004fb24  lea     r9, CscBackpatchUpdateFobxStateCallback
0x14004fb2b  xor     r8d, r8d
0x14004fb2e  mov     [rax-18h], rbx
0x14004fb32  mov     rdx, [rbx+10h]
0x14004fb36  mov     dil, 1
0x14004fb39  call    cs:__imp_RxIterateOnFcbOpens
0x14004fb40  nop     dword ptr [rax+rax+00h]
0x14004fb45  cmp     qword ptr [rbx+88h], 0
0x14004fb4d  jnz     short loc_14004FB70
0x14004fb4f  and     byte ptr [rbx+90h], 0FCh
0x14004fb56  mov     rax, [rsi+18h]
0x14004fb5a  mov     rcx, [rsi+8]
0x14004fb5e  mov     eax, [rax+8]
0x14004fb61  mov     [rcx+24h], eax
0x14004fb64  mov     rax, [rsi+8]
0x14004fb68  btr     dword ptr [rax+4], 9
0x14004fb6d  xor     dil, dil
0x14004fb70  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb77  lea     rax, WPP_GLOBAL_Control
0x14004fb7e  cmp     rcx, rax
0x14004fb81  jz      short loc_14004FBC3
0x14004fb83  mov     eax, [rcx+2Ch]
0x14004fb86  test    al, 40h
0x14004fb88  jz      short loc_14004FBC3
0x14004fb8a  cmp     qword ptr [rbx+80h], 0
0x14004fb92  jz      short loc_14004FBA1
0x14004fb94  mov     rax, [rbx+10h]
0x14004fb98  mov     r8d, [rax+0A4h]
0x14004fb9f  jmp     short loc_14004FBA5
0x14004fba1  or      r8d, 0FFFFFFFFh
0x14004fba5  mov     rcx, [rcx+18h]
0x14004fba9  mov     edx, 2Ch ; ','
0x14004fbae  mov     [rsp+38h+var_18], r8d
0x14004fbb3  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004fbba  movzx   r9d, dil
0x14004fbbe  call    WPP_SF_Dd
0x14004fbc3  mov     rbx, [rsp+38h+arg_0]
0x14004fbc8  mov     al, dil
0x14004fbcb  mov     rsi, [rsp+38h+arg_8]
0x14004fbd0  add     rsp, 30h
0x14004fbd4  pop     rdi
0x14004fbd5  retn
```
