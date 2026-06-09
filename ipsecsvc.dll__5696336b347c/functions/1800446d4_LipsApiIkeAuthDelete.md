# LipsApiIkeAuthDelete

- ea: `0x1800446d4`
- end: `0x180044729`
- name: `LipsApiIkeAuthDelete`
- size: `85`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bcb4`
- `0x18001bec0`
- `0x18001cac4`

## callees

- `0x18000f6ac`
- `0x1800446d4`
- `0x18004cd00`

## string_xrefs

- `0x1800446fa`: `LipsApiIkeAuthDelete`

## pseudocode

```c
__int64 __fastcall LipsApiIkeAuthDelete(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIkeAuthDelete");
  result = LipsIkeAuthDestroy(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x1800446d4  push    rbx
0x1800446d6  sub     rsp, 20h
0x1800446da  mov     rbx, rcx
0x1800446dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446e4  lea     rax, WPP_GLOBAL_Control
0x1800446eb  cmp     rcx, rax
0x1800446ee  jz      short loc_180044712
0x1800446f0  test    byte ptr [rcx+1Ch], 4
0x1800446f4  jz      short loc_180044712
0x1800446f6  mov     rcx, [rcx+10h]
0x1800446fa  lea     r9, aLipsapiikeauth_0; "LipsApiIkeAuthDelete"
0x180044701  mov     edx, 14h
0x180044706  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x18004470d  call    WPP_SF_s
0x180044712  lea     rcx, [rbx+28h]
0x180044716  call    LipsIkeAuthDestroy
0x18004471b  mov     qword ptr [rbx+28h], 0
0x180044723  add     rsp, 20h
0x180044727  pop     rbx
0x180044728  retn
```
