# LipsApiIkePolicyDelete

- ea: `0x180044af4`
- end: `0x180044b53`
- name: `LipsApiIkePolicyDelete`
- size: `95`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001a860`
- `0x18001ad54`
- `0x18001b128`

## callees

- `0x18000f6ac`
- `0x180044af4`
- `0x18004ba94`

## string_xrefs

- `0x180044b1a`: `LipsApiIkePolicyDelete`

## pseudocode

```c
_UNKNOWN **__fastcall LipsApiIkePolicyDelete(__int64 a1)
{
  _UNKNOWN **result; // rax
  _QWORD *v3; // rbx

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    result = (_UNKNOWN **)WPP_SF_s(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            36,
                            WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
                            "LipsApiIkePolicyDelete");
  v3 = (_QWORD *)(a1 + 56);
  if ( v3 )
  {
    if ( *v3 )
    {
      result = (_UNKNOWN **)LipsIkePolicyDestroy(v3);
      *v3 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180044af4  push    rbx
0x180044af6  sub     rsp, 20h
0x180044afa  mov     rbx, rcx
0x180044afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b04  lea     rax, WPP_GLOBAL_Control
0x180044b0b  cmp     rcx, rax
0x180044b0e  jz      short loc_180044B32
0x180044b10  test    byte ptr [rcx+1Ch], 4
0x180044b14  jz      short loc_180044B32
0x180044b16  mov     rcx, [rcx+10h]
0x180044b1a  lea     r9, aLipsapiikepoli; "LipsApiIkePolicyDelete"
0x180044b21  mov     edx, 24h ; '$'
0x180044b26  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044b2d  call    WPP_SF_s
0x180044b32  add     rbx, 38h ; '8'
0x180044b36  jz      short loc_180044B4D
0x180044b38  cmp     qword ptr [rbx], 0
0x180044b3c  jz      short loc_180044B4D
0x180044b3e  mov     rcx, rbx
0x180044b41  call    LipsIkePolicyDestroy
0x180044b46  mov     qword ptr [rbx], 0
0x180044b4d  add     rsp, 20h
0x180044b51  pop     rbx
0x180044b52  retn
```
