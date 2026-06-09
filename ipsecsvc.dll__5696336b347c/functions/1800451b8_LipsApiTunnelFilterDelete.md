# LipsApiTunnelFilterDelete

- ea: `0x1800451b8`
- end: `0x1800452c8`
- name: `LipsApiTunnelFilterDelete`
- size: `272`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180031888`
- `0x180032b84`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x1800451b8`
- `0x1800452d0`
- `0x1800499e4`

## string_xrefs

- `0x1800451e2`: `LipsApiTunnelFilterDelete`
- `0x18004522b`: `LipsApiTunnelFilterDelete`
- `0x18004529f`: `LipsApiTunnelFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsApiTunnelFilterDelete(__int64 a1)
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
      69,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiTunnelFilterDelete");
    v2 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(a1 + 360) != 2 && *(_DWORD *)(a1 + 228) == 3 && *(_DWORD *)(a1 + 232) == 3 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
      WPP_SF_s(v2[2], 70, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, "LipsApiTunnelFilterDelete");
    return 0;
  }
  else
  {
    v4 = LipsStateTunnelFilterDelete(*(_QWORD *)(a1 + 280), *(unsigned int *)(a1 + 272));
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v4);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
          WPP_SF_sD(
            v6[2],
            72,
            (unsigned int)WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
            (unsigned int)"LipsApiTunnelFilterDelete",
            v5);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x1800451b8  mov     [rsp+arg_0], rbx
0x1800451bd  push    rdi
0x1800451be  sub     rsp, 30h
0x1800451c2  mov     rbx, rcx
0x1800451c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800451cc  lea     rdi, WPP_GLOBAL_Control
0x1800451d3  cmp     rcx, rdi
0x1800451d6  jz      short loc_180045201
0x1800451d8  test    byte ptr [rcx+1Ch], 4
0x1800451dc  jz      short loc_180045201
0x1800451de  mov     rcx, [rcx+10h]
0x1800451e2  lea     r9, aLipsapitunnelf; "LipsApiTunnelFilterDelete"
0x1800451e9  mov     edx, 45h ; 'E'
0x1800451ee  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800451f5  call    WPP_SF_s
0x1800451fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180045201  cmp     dword ptr [rbx+168h], 2
0x180045208  jz      short loc_180045247
0x18004520a  cmp     dword ptr [rbx+0E4h], 3
0x180045211  jnz     short loc_180045247
0x180045213  cmp     dword ptr [rbx+0E8h], 3
0x18004521a  jnz     short loc_180045247
0x18004521c  cmp     rcx, rdi
0x18004521f  jz      short loc_180045243
0x180045221  test    byte ptr [rcx+1Ch], 4
0x180045225  jz      short loc_180045243
0x180045227  mov     rcx, [rcx+10h]
0x18004522b  lea     r9, aLipsapitunnelf; "LipsApiTunnelFilterDelete"
0x180045232  mov     edx, 46h ; 'F'
0x180045237  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x18004523e  call    WPP_SF_s
0x180045243  xor     eax, eax
0x180045245  jmp     short loc_1800452BD
0x180045247  mov     edx, [rbx+110h]
0x18004524d  mov     rcx, [rbx+118h]
0x180045254  call    LipsStateTunnelFilterDelete
0x180045259  mov     ebx, eax
0x18004525b  test    eax, eax
0x18004525d  jz      short loc_1800452BB
0x18004525f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045266  cmp     rcx, rdi
0x180045269  jz      short loc_1800452BB
0x18004526b  test    byte ptr [rcx+1Ch], 10h
0x18004526f  jz      short loc_180045290
0x180045271  mov     rcx, [rcx+10h]
0x180045275  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x18004527c  mov     edx, 47h ; 'G'
0x180045281  mov     r9d, eax
0x180045284  call    WPP_SF_d
0x180045289  mov     rcx, cs:WPP_GLOBAL_Control
0x180045290  cmp     rcx, rdi
0x180045293  jz      short loc_1800452BB
0x180045295  test    byte ptr [rcx+1Ch], 10h
0x180045299  jz      short loc_1800452BB
0x18004529b  mov     rcx, [rcx+10h]
0x18004529f  lea     r9, aLipsapitunnelf; "LipsApiTunnelFilterDelete"
0x1800452a6  mov     edx, 48h ; 'H'
0x1800452ab  mov     [rsp+38h+var_18], ebx
0x1800452af  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800452b6  call    WPP_SF_sD
0x1800452bb  mov     eax, ebx
0x1800452bd  mov     rbx, [rsp+38h+arg_0]
0x1800452c2  add     rsp, 30h
0x1800452c6  pop     rdi
0x1800452c7  retn
```
