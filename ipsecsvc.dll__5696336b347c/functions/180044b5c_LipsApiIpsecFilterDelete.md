# LipsApiIpsecFilterDelete

- ea: `0x180044b5c`
- end: `0x180044c17`
- name: `LipsApiIpsecFilterDelete`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d89c`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044b5c`
- `0x18004674c`

## string_xrefs

- `0x180044b86`: `LipsApiIpsecFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsApiIpsecFilterDelete(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIpsecFilterDelete");
  v2 = LipsStateIpsecFilterDelete(*(_QWORD *)(a1 + 200), *(unsigned int *)(a1 + 192));
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v2);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
        WPP_SF_d(v4[2], 42, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180044b5c  mov     [rsp+arg_0], rbx
0x180044b61  push    rdi
0x180044b62  sub     rsp, 20h
0x180044b66  mov     rbx, rcx
0x180044b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b70  lea     rdi, WPP_GLOBAL_Control
0x180044b77  cmp     rcx, rdi
0x180044b7a  jz      short loc_180044B9E
0x180044b7c  test    byte ptr [rcx+1Ch], 4
0x180044b80  jz      short loc_180044B9E
0x180044b82  mov     rcx, [rcx+10h]
0x180044b86  lea     r9, aLipsapiipsecfi_0; "LipsApiIpsecFilterDelete"
0x180044b8d  mov     edx, 28h ; '('
0x180044b92  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044b99  call    WPP_SF_s
0x180044b9e  mov     edx, [rbx+0C0h]
0x180044ba4  mov     rcx, [rbx+0C8h]
0x180044bab  call    LipsStateIpsecFilterDelete
0x180044bb0  mov     ebx, eax
0x180044bb2  test    eax, eax
0x180044bb4  jz      short loc_180044C0A
0x180044bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180044bbd  cmp     rcx, rdi
0x180044bc0  jz      short loc_180044C0A
0x180044bc2  test    byte ptr [rcx+1Ch], 10h
0x180044bc6  jz      short loc_180044BE7
0x180044bc8  mov     rcx, [rcx+10h]
0x180044bcc  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044bd3  mov     edx, 29h ; ')'
0x180044bd8  mov     r9d, eax
0x180044bdb  call    WPP_SF_d
0x180044be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180044be7  cmp     rcx, rdi
0x180044bea  jz      short loc_180044C0A
0x180044bec  test    byte ptr [rcx+1Ch], 10h
0x180044bf0  jz      short loc_180044C0A
0x180044bf2  mov     rcx, [rcx+10h]
0x180044bf6  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044bfd  mov     edx, 2Ah ; '*'
0x180044c02  mov     r9d, ebx
0x180044c05  call    WPP_SF_d
0x180044c0a  mov     eax, ebx
0x180044c0c  mov     rbx, [rsp+28h+arg_0]
0x180044c11  add     rsp, 20h
0x180044c15  pop     rdi
0x180044c16  retn
```
