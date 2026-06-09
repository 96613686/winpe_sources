# PrSendNetBufferListChainComplete

- ea: `0x140015cf0`
- end: `0x140015dda`
- name: `PrSendNetBufferListChainComplete`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002574`
- `0x14000400c`
- `0x140006b80`
- `0x140015cf0`

## pseudocode

```c
__int64 __fastcall PrSendNetBufferListChainComplete(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rbp
  __int64 v6; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a1, a2);
  }
  result = a2;
  if ( a2 )
  {
    do
    {
      v5 = *(_QWORD *)result;
      v6 = *(_QWORD *)(result + 64);
      *(_QWORD *)result = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
        (*(void (**)(void))(v6 + 8))();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 408), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(a1 + 416))(a1 + 408);
      DereferenceBinding(a1);
      result = v5;
    }
    while ( v5 );
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x140015cf0  push    rbx
0x140015cf2  push    rbp
0x140015cf3  push    rsi
0x140015cf4  push    rdi
0x140015cf5  push    r15
0x140015cf7  sub     rsp, 30h
0x140015cfb  mov     rbx, rdx
0x140015cfe  mov     rdi, rcx
0x140015d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d08  lea     r15, WPP_GLOBAL_Control
0x140015d0f  cmp     rcx, r15
0x140015d12  jz      short loc_140015D3E
0x140015d14  mov     eax, [rcx+2Ch]
0x140015d17  test    al, 4
0x140015d19  jz      short loc_140015D3E
0x140015d1b  cmp     byte ptr [rcx+29h], 4
0x140015d1f  jb      short loc_140015D3E
0x140015d21  mov     rcx, [rcx+18h]
0x140015d25  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015d2c  mov     edx, 4Dh ; 'M'
0x140015d31  mov     [rsp+58h+var_38], rbx
0x140015d36  mov     r9, rdi
0x140015d39  call    WPP_SF_qq
0x140015d3e  mov     rax, rbx
0x140015d41  test    rbx, rbx
0x140015d44  jz      short loc_140015D98
0x140015d46  lea     rsi, [rdi+198h]
0x140015d4d  mov     rbp, [rax]
0x140015d50  mov     rcx, [rax+40h]
0x140015d54  mov     qword ptr [rax], 0
0x140015d5b  or      eax, 0FFFFFFFFh
0x140015d5e  lock xadd [rcx], eax
0x140015d62  cmp     eax, 1
0x140015d65  jnz     short loc_140015D70
0x140015d67  mov     rax, [rcx+8]
0x140015d6b  call    _guard_dispatch_icall
0x140015d70  or      eax, 0FFFFFFFFh
0x140015d73  lock xadd [rsi], eax
0x140015d77  cmp     eax, 1
0x140015d7a  jnz     short loc_140015D88
0x140015d7c  mov     rax, [rsi+8]
0x140015d80  mov     rcx, rsi
0x140015d83  call    _guard_dispatch_icall
0x140015d88  mov     rcx, rdi
0x140015d8b  call    DereferenceBinding
0x140015d90  mov     rax, rbp
0x140015d93  test    rbp, rbp
0x140015d96  jnz     short loc_140015D4D
0x140015d98  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d9f  cmp     rcx, r15
0x140015da2  jz      short loc_140015DCE
0x140015da4  mov     eax, [rcx+2Ch]
0x140015da7  test    al, 4
0x140015da9  jz      short loc_140015DCE
0x140015dab  cmp     byte ptr [rcx+29h], 4
0x140015daf  jb      short loc_140015DCE
0x140015db1  mov     rcx, [rcx+18h]
0x140015db5  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015dbc  mov     edx, 4Eh ; 'N'
0x140015dc1  mov     [rsp+58h+var_38], rbx
0x140015dc6  mov     r9, rdi
0x140015dc9  call    WPP_SF_qq
0x140015dce  add     rsp, 30h
0x140015dd2  pop     r15
0x140015dd4  pop     rdi
0x140015dd5  pop     rsi
0x140015dd6  pop     rbp
0x140015dd7  pop     rbx
0x140015dd8  retn
```
