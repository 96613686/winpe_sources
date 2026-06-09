# RasFreeEapConfigErrorMemory

- ea: `0x18002c464`
- end: `0x18002c4eb`
- name: `RasFreeEapConfigErrorMemory`
- size: `135`
- prototype: `__int64 __fastcall(EAP_ERROR *pEapError)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028d20`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002c8d0`

## callees

- `0x18002c464`
- `0x18002cbac`

## import_xrefs

- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002c4ad`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18002c4ad`

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
0x18002c464  mov     [rsp+arg_0], rbx
0x18002c469  push    rdi
0x18002c46a  sub     rsp, 20h
0x18002c46e  mov     rbx, rcx
0x18002c471  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c478  lea     rdi, WPP_GLOBAL_Control
0x18002c47f  cmp     rcx, rdi
0x18002c482  jz      short loc_18002C4A5
0x18002c484  test    byte ptr [rcx+1Ch], 2
0x18002c488  jz      short loc_18002C4A5
0x18002c48a  cmp     byte ptr [rcx+19h], 6
0x18002c48e  jb      short loc_18002C4A5
0x18002c490  mov     rcx, [rcx+10h]
0x18002c494  mov     edx, 0Ch
0x18002c499  call    WPP_SF_
0x18002c49e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4a5  test    rbx, rbx
0x18002c4a8  jz      short loc_18002C4C0
0x18002c4aa  mov     rcx, rbx; pEapError
0x18002c4ad  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18002c4b4  nop     dword ptr [rax+rax+00h]
0x18002c4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4c0  cmp     rcx, rdi
0x18002c4c3  jz      short loc_18002C4DF
0x18002c4c5  test    byte ptr [rcx+1Ch], 2
0x18002c4c9  jz      short loc_18002C4DF
0x18002c4cb  cmp     byte ptr [rcx+19h], 6
0x18002c4cf  jb      short loc_18002C4DF
0x18002c4d1  mov     rcx, [rcx+10h]
0x18002c4d5  mov     edx, 0Dh
0x18002c4da  call    WPP_SF_
0x18002c4df  mov     rbx, [rsp+28h+arg_0]
0x18002c4e4  add     rsp, 20h
0x18002c4e8  pop     rdi
0x18002c4e9  retn
```
