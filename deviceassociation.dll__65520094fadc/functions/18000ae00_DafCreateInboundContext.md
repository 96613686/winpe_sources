# DafCreateInboundContext

- ea: `0x18000ae00`
- end: `0x18000ae75`
- name: `DafCreateInboundContext`
- size: `117`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002284`
- `0x180002f10`
- `0x18000ae00`
- `0x18000bbc2`

## pseudocode

```c
__int64 __fastcall DafCreateInboundContext(RPC_BINDING_HANDLE **a1)
{
  _DWORD v3[18]; // [rsp+20h] [rbp-48h] BYREF

  memset_0(v3, 0, 0x40u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_61e63e094b87365e371089d0260af5a5_Traceguids);
  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v3[0] = 6;
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v3, a1);
}

```

## disassembly

```asm
0x18000ae00  push    rbx
0x18000ae02  sub     rsp, 60h
0x18000ae06  xor     edx, edx; Val
0x18000ae08  mov     rbx, rcx
0x18000ae0b  lea     rcx, [rsp+68h+var_48]; void *
0x18000ae10  lea     r8d, [rdx+40h]; Size
0x18000ae14  call    memset_0
0x18000ae19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae20  lea     rax, WPP_GLOBAL_Control
0x18000ae27  cmp     rcx, rax
0x18000ae2a  jz      short loc_18000AE47
0x18000ae2c  cmp     byte ptr [rcx+19h], 4
0x18000ae30  jb      short loc_18000AE47
0x18000ae32  mov     rcx, [rcx+10h]
0x18000ae36  lea     r8, WPP_61e63e094b87365e371089d0260af5a5_Traceguids
0x18000ae3d  mov     edx, 0Ah
0x18000ae42  call    WPP_SF_s
0x18000ae47  test    rbx, rbx
0x18000ae4a  jnz     short loc_18000AE53
0x18000ae4c  mov     eax, 80070057h
0x18000ae51  jmp     short loc_18000AE6F
0x18000ae53  mov     rdx, rbx; struct _DAC_CLIENT_CONTEXT **
0x18000ae56  mov     qword ptr [rbx], 0
0x18000ae5d  lea     rcx, [rsp+68h+var_48]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x18000ae62  mov     [rsp+68h+var_48], 6
0x18000ae6a  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x18000ae6f  add     rsp, 60h
0x18000ae73  pop     rbx
0x18000ae74  retn
```
