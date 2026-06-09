# LipsApiIkeFilterDelete

- ea: `0x18004482c`
- end: `0x180044922`
- name: `LipsApiIkeFilterDelete`
- size: `246`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022cac`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x18004482c`
- `0x180045808`

## string_xrefs

- `0x180044856`: `LipsApiIkeFilterDelete`
- `0x18004488d`: `LipsApiIkeFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsApiIkeFilterDelete(__int64 a1)
{
  _QWORD *v2; // rcx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIkeFilterDelete");
    v2 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(a1 + 40) & 0x100) != 0 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
      WPP_SF_s(v2[2], 26, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, "LipsApiIkeFilterDelete");
    return 0;
  }
  else
  {
    v4 = LipsStateIkeFilterDelete(*(_QWORD *)(a1 + 192), *(unsigned int *)(a1 + 184));
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v4);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
          WPP_SF_d(v6[2], 28, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v5);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18004482c  mov     [rsp+arg_0], rbx
0x180044831  push    rdi
0x180044832  sub     rsp, 20h
0x180044836  mov     rbx, rcx
0x180044839  mov     rcx, cs:WPP_GLOBAL_Control
0x180044840  lea     rdi, WPP_GLOBAL_Control
0x180044847  cmp     rcx, rdi
0x18004484a  jz      short loc_180044875
0x18004484c  test    byte ptr [rcx+1Ch], 4
0x180044850  jz      short loc_180044875
0x180044852  mov     rcx, [rcx+10h]
0x180044856  lea     r9, aLipsapiikefilt; "LipsApiIkeFilterDelete"
0x18004485d  mov     edx, 19h
0x180044862  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044869  call    WPP_SF_s
0x18004486e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044875  test    dword ptr [rbx+28h], 100h
0x18004487c  jz      short loc_1800448A9
0x18004487e  cmp     rcx, rdi
0x180044881  jz      short loc_1800448A5
0x180044883  test    byte ptr [rcx+1Ch], 4
0x180044887  jz      short loc_1800448A5
0x180044889  mov     rcx, [rcx+10h]
0x18004488d  lea     r9, aLipsapiikefilt; "LipsApiIkeFilterDelete"
0x180044894  mov     edx, 1Ah
0x180044899  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800448a0  call    WPP_SF_s
0x1800448a5  xor     eax, eax
0x1800448a7  jmp     short loc_180044917
0x1800448a9  mov     edx, [rbx+0B8h]
0x1800448af  mov     rcx, [rbx+0C0h]
0x1800448b6  call    LipsStateIkeFilterDelete
0x1800448bb  mov     ebx, eax
0x1800448bd  test    eax, eax
0x1800448bf  jz      short loc_180044915
0x1800448c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448c8  cmp     rcx, rdi
0x1800448cb  jz      short loc_180044915
0x1800448cd  test    byte ptr [rcx+1Ch], 10h
0x1800448d1  jz      short loc_1800448F2
0x1800448d3  mov     rcx, [rcx+10h]
0x1800448d7  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800448de  mov     edx, 1Bh
0x1800448e3  mov     r9d, eax
0x1800448e6  call    WPP_SF_d
0x1800448eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448f2  cmp     rcx, rdi
0x1800448f5  jz      short loc_180044915
0x1800448f7  test    byte ptr [rcx+1Ch], 10h
0x1800448fb  jz      short loc_180044915
0x1800448fd  mov     rcx, [rcx+10h]
0x180044901  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044908  mov     edx, 1Ch
0x18004490d  mov     r9d, ebx
0x180044910  call    WPP_SF_d
0x180044915  mov     eax, ebx
0x180044917  mov     rbx, [rsp+28h+arg_0]
0x18004491c  add     rsp, 20h
0x180044920  pop     rdi
0x180044921  retn
```
