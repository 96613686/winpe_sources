# RasFreeEapMemory

- ea: `0x180008000`
- end: `0x18000808e`
- name: `RasFreeEapMemory`
- size: `142`
- prototype: `__int64 __fastcall(BYTE *pData)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008094`
- `0x180008154`

## callees

- `0x180008000`
- `0x180008518`

## import_xrefs

- `eappcfg!EapHostPeerFreeMemory` at `0x180008050`
- `eappcfg!EapHostPeerFreeMemory` at `0x180008050`

## pseudocode

```c
void __fastcall RasFreeEapMemory(BYTE *pData)
{
  _UNKNOWN **v2; // rcx

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( pData )
  {
    EapHostPeerFreeMemory(pData);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_((TRACEHANDLE)v2[2], 0xBu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
}

```

## disassembly

```asm
0x180008000  mov     [rsp+arg_0], rbx
0x180008005  push    rdi
0x180008006  sub     rsp, 20h
0x18000800a  mov     rbx, rcx
0x18000800d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008014  lea     rdi, WPP_GLOBAL_Control
0x18000801b  cmp     rcx, rdi
0x18000801e  jz      short loc_180008048
0x180008020  test    byte ptr [rcx+1Ch], 2
0x180008024  jz      short loc_180008048
0x180008026  cmp     byte ptr [rcx+19h], 6
0x18000802a  jb      short loc_180008048
0x18000802c  mov     rcx, [rcx+10h]
0x180008030  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180008037  mov     edx, 0Ah
0x18000803c  call    WPP_SF_
0x180008041  mov     rcx, cs:WPP_GLOBAL_Control
0x180008048  test    rbx, rbx
0x18000804b  jz      short loc_18000805D
0x18000804d  mov     rcx, rbx; pData
0x180008050  call    cs:__imp_EapHostPeerFreeMemory
0x180008056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000805d  cmp     rcx, rdi
0x180008060  jz      short loc_180008083
0x180008062  test    byte ptr [rcx+1Ch], 2
0x180008066  jz      short loc_180008083
0x180008068  cmp     byte ptr [rcx+19h], 6
0x18000806c  jb      short loc_180008083
0x18000806e  mov     rcx, [rcx+10h]
0x180008072  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180008079  mov     edx, 0Bh
0x18000807e  call    WPP_SF_
0x180008083  mov     rbx, [rsp+28h+arg_0]
0x180008088  add     rsp, 20h
0x18000808c  pop     rdi
0x18000808d  retn
```
