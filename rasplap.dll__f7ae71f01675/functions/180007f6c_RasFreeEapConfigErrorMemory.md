# RasFreeEapConfigErrorMemory

- ea: `0x180007f6c`
- end: `0x180007ffa`
- name: `RasFreeEapConfigErrorMemory`
- size: `142`
- prototype: `__int64 __fastcall(EAP_ERROR *pEapError)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007288`
- `0x180008234`

## callees

- `0x180007f6c`
- `0x180008518`

## import_xrefs

- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180007fbc`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x180007fbc`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( pEapError )
  {
    EapHostPeerFreeErrorMemory(pEapError);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 13, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
}

```

## disassembly

```asm
0x180007f6c  mov     [rsp+arg_0], rbx
0x180007f71  push    rdi
0x180007f72  sub     rsp, 20h
0x180007f76  mov     rbx, rcx
0x180007f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f80  lea     rdi, WPP_GLOBAL_Control
0x180007f87  cmp     rcx, rdi
0x180007f8a  jz      short loc_180007FB4
0x180007f8c  test    byte ptr [rcx+1Ch], 2
0x180007f90  jz      short loc_180007FB4
0x180007f92  cmp     byte ptr [rcx+19h], 6
0x180007f96  jb      short loc_180007FB4
0x180007f98  mov     rcx, [rcx+10h]
0x180007f9c  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007fa3  mov     edx, 0Ch
0x180007fa8  call    WPP_SF_
0x180007fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fb4  test    rbx, rbx
0x180007fb7  jz      short loc_180007FC9
0x180007fb9  mov     rcx, rbx; pEapError
0x180007fbc  call    cs:__imp_EapHostPeerFreeErrorMemory
0x180007fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fc9  cmp     rcx, rdi
0x180007fcc  jz      short loc_180007FEF
0x180007fce  test    byte ptr [rcx+1Ch], 2
0x180007fd2  jz      short loc_180007FEF
0x180007fd4  cmp     byte ptr [rcx+19h], 6
0x180007fd8  jb      short loc_180007FEF
0x180007fda  mov     rcx, [rcx+10h]
0x180007fde  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007fe5  mov     edx, 0Dh
0x180007fea  call    WPP_SF_
0x180007fef  mov     rbx, [rsp+28h+arg_0]
0x180007ff4  add     rsp, 20h
0x180007ff8  pop     rdi
0x180007ff9  retn
```
