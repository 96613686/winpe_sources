# LipsApiIpsecFilterUpdate

- ea: `0x180044c20`
- end: `0x180044ce1`
- name: `LipsApiIpsecFilterUpdate`
- size: `193`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001e9f0`
- `0x18001f08c`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044c20`
- `0x180046bdc`

## string_xrefs

- `0x180044c52`: `LipsApiIpsecFilterUpdate`

## pseudocode

```c
__int64 __fastcall LipsApiIpsecFilterUpdate(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIpsecFilterUpdate");
  v4 = LipsStateIpsecFilterUpdate(a1, a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_d(v6[2], 45, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180044c20  mov     [rsp+arg_0], rbx
0x180044c25  mov     [rsp+arg_8], rsi
0x180044c2a  push    rdi
0x180044c2b  sub     rsp, 20h
0x180044c2f  mov     rbx, rdx
0x180044c32  mov     rdi, rcx
0x180044c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c3c  lea     rsi, WPP_GLOBAL_Control
0x180044c43  cmp     rcx, rsi
0x180044c46  jz      short loc_180044C6A
0x180044c48  test    byte ptr [rcx+1Ch], 4
0x180044c4c  jz      short loc_180044C6A
0x180044c4e  mov     rcx, [rcx+10h]
0x180044c52  lea     r9, aLipsapiipsecfi; "LipsApiIpsecFilterUpdate"
0x180044c59  mov     edx, 2Bh ; '+'
0x180044c5e  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044c65  call    WPP_SF_s
0x180044c6a  mov     rdx, rbx
0x180044c6d  mov     rcx, rdi
0x180044c70  call    LipsStateIpsecFilterUpdate
0x180044c75  mov     ebx, eax
0x180044c77  test    eax, eax
0x180044c79  jz      short loc_180044CCF
0x180044c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c82  cmp     rcx, rsi
0x180044c85  jz      short loc_180044CCF
0x180044c87  test    byte ptr [rcx+1Ch], 10h
0x180044c8b  jz      short loc_180044CAC
0x180044c8d  mov     rcx, [rcx+10h]
0x180044c91  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044c98  mov     edx, 2Ch ; ','
0x180044c9d  mov     r9d, eax
0x180044ca0  call    WPP_SF_d
0x180044ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cac  cmp     rcx, rsi
0x180044caf  jz      short loc_180044CCF
0x180044cb1  test    byte ptr [rcx+1Ch], 10h
0x180044cb5  jz      short loc_180044CCF
0x180044cb7  mov     rcx, [rcx+10h]
0x180044cbb  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044cc2  mov     edx, 2Dh ; '-'
0x180044cc7  mov     r9d, ebx
0x180044cca  call    WPP_SF_d
0x180044ccf  mov     rsi, [rsp+28h+arg_8]
0x180044cd4  mov     eax, ebx
0x180044cd6  mov     rbx, [rsp+28h+arg_0]
0x180044cdb  add     rsp, 20h
0x180044cdf  pop     rdi
0x180044ce0  retn
```
