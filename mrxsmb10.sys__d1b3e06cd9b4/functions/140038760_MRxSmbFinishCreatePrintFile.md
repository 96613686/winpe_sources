# MRxSmbFinishCreatePrintFile

- ea: `0x140038760`
- end: `0x140038896`
- name: `MRxSmbFinishCreatePrintFile`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x14000dfa8`
- `0x140010660`
- `0x140016560`
- `0x1400169c0`
- `0x140038760`
- `0x1400499e0`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishCreatePrintFile(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v2; // rsi
  PMRX_SRV_OPEN pRelevantSrvOpen; // r14
  _DWORD *p_NodeTypeCode; // rdi
  unsigned __int16 v7; // bx
  __int64 v8; // rdx
  unsigned int FileSuccessTail; // ebx
  __int64 v11[10]; // [rsp+40h] [rbp-88h] BYREF

  v2 = *(struct _RX_CONTEXT **)(a1 + 24);
  pRelevantSrvOpen = v2->pRelevantSrvOpen;
  p_NodeTypeCode = &v2->pFcb->Header.NodeTypeCode;
  memset(v11, 0, 0x48u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  v7 = *(_WORD *)(a2 + 1);
  memset(v11, 0, 0x48u);
  LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
  FileSuccessTail = MRxSmbCreateFileSuccessTail(v2, v8, 7, v7, *(_DWORD *)(a1 + 52), 0, 1u, (__int64)v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      57,
      (unsigned int)p_NodeTypeCode[41],
      FileSuccessTail,
      p_NodeTypeCode[39],
      p_NodeTypeCode[41],
      p_NodeTypeCode[40]);
  return FileSuccessTail;
}

```

## disassembly

```asm
0x140038760  mov     [rsp+arg_10], rbx
0x140038765  push    rbp
0x140038766  push    rsi
0x140038767  push    rdi
0x140038768  push    r13
0x14003876a  push    r14
0x14003876c  sub     rsp, 0A0h
0x140038773  mov     rax, cs:__security_cookie
0x14003877a  xor     rax, rsp
0x14003877d  mov     [rsp+0C8h+var_38], rax
0x140038785  mov     rsi, [rcx+18h]
0x140038789  mov     rbx, rdx
0x14003878c  xor     edx, edx; Val
0x14003878e  mov     rbp, rcx
0x140038791  lea     rcx, [rsp+0C8h+var_88]; void *
0x140038796  mov     r14, [rsi+48h]
0x14003879a  mov     rdi, [rsi+38h]
0x14003879e  lea     r8d, [rdx+48h]; Size
0x1400387a2  call    memset
0x1400387a7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400387ae  lea     r13, WPP_GLOBAL_Control
0x1400387b5  cmp     rcx, r13
0x1400387b8  jz      short loc_1400387D8
0x1400387ba  test    dword ptr [rcx+2Ch], 400h
0x1400387c1  jz      short loc_1400387D8
0x1400387c3  mov     rcx, [rcx+18h]
0x1400387c7  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400387ce  mov     edx, 38h ; '8'
0x1400387d3  call    WPP_SF_
0x1400387d8  movzx   ebx, word ptr [rbx+1]
0x1400387dc  lea     rcx, [rsp+0C8h+var_88]; void *
0x1400387e1  xor     edx, edx; Val
0x1400387e3  lea     r8d, [rdx+48h]; Size
0x1400387e7  call    memset
0x1400387ec  btr     dword ptr [r14+48h], 14h
0x1400387f2  lea     rax, [rsp+0C8h+var_88]
0x1400387f7  mov     [rsp+0C8h+var_90], rax; __int64
0x1400387fc  movzx   r9d, bx
0x140038800  mov     eax, [rbp+34h]
0x140038803  mov     r8d, 7
0x140038809  mov     [rsp+0C8h+var_98], 1; int
0x140038811  mov     rcx, rsi; RxContext
0x140038814  mov     [rsp+0C8h+var_A0], 0; char
0x140038819  mov     [rsp+0C8h+var_A8], eax; int
0x14003881d  call    MRxSmbCreateFileSuccessTail
0x140038822  mov     ebx, eax
0x140038824  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003882b  cmp     rcx, r13
0x14003882e  jz      short loc_14003886C
0x140038830  test    dword ptr [rcx+2Ch], 400h
0x140038837  jz      short loc_14003886C
0x140038839  mov     r8d, [rdi+0A0h]
0x140038840  mov     edx, 39h ; '9'
0x140038845  mov     eax, [rdi+9Ch]
0x14003884b  mov     r9d, ebx
0x14003884e  mov     rcx, [rcx+18h]
0x140038852  mov     [rsp+0C8h+var_98], r8d
0x140038857  mov     r8d, [rdi+0A4h]
0x14003885e  mov     dword ptr [rsp+0C8h+var_A0], r8d
0x140038863  mov     [rsp+0C8h+var_A8], eax
0x140038867  call    WPP_SF_LDDD
0x14003886c  mov     eax, ebx
0x14003886e  mov     rcx, [rsp+0C8h+var_38]
0x140038876  xor     rcx, rsp; StackCookie
0x140038879  call    __security_check_cookie
0x14003887e  mov     rbx, [rsp+0C8h+arg_10]
0x140038886  add     rsp, 0A0h
0x14003888d  pop     r14
0x14003888f  pop     r13
0x140038891  pop     rdi
0x140038892  pop     rsi
0x140038893  pop     rbp
0x140038894  retn
```
