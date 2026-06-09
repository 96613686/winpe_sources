# RasFreeEapConfigErrorMemory

- ea: `0x18002b428`
- end: `0x18002b4a8`
- name: `RasFreeEapConfigErrorMemory`
- size: `128`
- prototype: `__int64 __fastcall(EAP_ERROR *pEapError)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180027e60`
- `0x18002a350`
- `0x18002a7e0`
- `0x18002b87c`

## callees

- `0x18002b428`
- `0x18002bb54`

## import_xrefs

- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002b471`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002b471`

## pseudocode

```c
void __fastcall RasFreeEapConfigErrorMemory(EAP_ERROR *pEapError)
{
  _QWORD *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
    v2 = WPP_GLOBAL_Control;
  }
  if ( pEapError )
  {
    EapHostPeerFreeErrorMemory(pEapError);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 13);
}

```

## disassembly

```asm
0x18002b428  mov     [rsp+arg_0], rbx
0x18002b42d  push    rdi
0x18002b42e  sub     rsp, 20h
0x18002b432  mov     rbx, rcx
0x18002b435  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b43c  lea     rdi, WPP_GLOBAL_Control
0x18002b443  cmp     rcx, rdi
0x18002b446  jz      short loc_18002B469
0x18002b448  test    byte ptr [rcx+1Ch], 2
0x18002b44c  jz      short loc_18002B469
0x18002b44e  cmp     byte ptr [rcx+19h], 6
0x18002b452  jb      short loc_18002B469
0x18002b454  mov     rcx, [rcx+10h]
0x18002b458  mov     edx, 0Ch
0x18002b45d  call    WPP_SF_
0x18002b462  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b469  test    rbx, rbx
0x18002b46c  jz      short loc_18002B47E
0x18002b46e  mov     rcx, rbx; pEapError
0x18002b471  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18002b477  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b47e  cmp     rcx, rdi
0x18002b481  jz      short loc_18002B49D
0x18002b483  test    byte ptr [rcx+1Ch], 2
0x18002b487  jz      short loc_18002B49D
0x18002b489  cmp     byte ptr [rcx+19h], 6
0x18002b48d  jb      short loc_18002B49D
0x18002b48f  mov     rcx, [rcx+10h]
0x18002b493  mov     edx, 0Dh
0x18002b498  call    WPP_SF_
0x18002b49d  mov     rbx, [rsp+28h+arg_0]
0x18002b4a2  add     rsp, 20h
0x18002b4a6  pop     rdi
0x18002b4a7  retn
```
