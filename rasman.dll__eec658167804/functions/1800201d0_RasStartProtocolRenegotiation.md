# RasStartProtocolRenegotiation

- ea: `0x1800201d0`
- end: `0x180020294`
- name: `RasStartProtocolRenegotiation`
- size: `196`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800201d0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasStartProtocolRenegotiation(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 678, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v2 = SubmitLocalRequest(0x82u, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 679, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 680, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800201d0  mov     [rsp+arg_0], rbx
0x1800201d5  push    rsi
0x1800201d6  sub     rsp, 20h
0x1800201da  mov     rbx, rcx
0x1800201dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201e4  lea     rsi, WPP_GLOBAL_Control
0x1800201eb  cmp     rcx, rsi
0x1800201ee  jz      short loc_180020214
0x1800201f0  test    byte ptr [rcx+1Ch], 40h
0x1800201f4  jz      short loc_180020214
0x1800201f6  cmp     byte ptr [rcx+19h], 6
0x1800201fa  jb      short loc_180020214
0x1800201fc  mov     rcx, [rcx+10h]
0x180020200  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020207  mov     edx, 2A6h
0x18002020c  mov     r9, rbx
0x18002020f  call    WPP_SF_q
0x180020214  mov     ecx, 82h
0x180020219  mov     rdx, rbx
0x18002021c  call    SubmitLocalRequest
0x180020221  mov     ebx, eax
0x180020223  test    eax, eax
0x180020225  jz      short loc_180020257
0x180020227  mov     rcx, cs:WPP_GLOBAL_Control
0x18002022e  cmp     rcx, rsi
0x180020231  jz      short loc_180020287
0x180020233  test    byte ptr [rcx+1Ch], 40h
0x180020237  jz      short loc_18002025E
0x180020239  cmp     byte ptr [rcx+19h], 2
0x18002023d  jb      short loc_18002025E
0x18002023f  mov     rcx, [rcx+10h]
0x180020243  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002024a  mov     edx, 2A7h
0x18002024f  mov     r9d, eax
0x180020252  call    WPP_SF_d
0x180020257  mov     rcx, cs:WPP_GLOBAL_Control
0x18002025e  cmp     rcx, rsi
0x180020261  jz      short loc_180020287
0x180020263  test    byte ptr [rcx+1Ch], 40h
0x180020267  jz      short loc_180020287
0x180020269  cmp     byte ptr [rcx+19h], 6
0x18002026d  jb      short loc_180020287
0x18002026f  mov     rcx, [rcx+10h]
0x180020273  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18002027a  mov     edx, 2A8h
0x18002027f  mov     r9d, ebx
0x180020282  call    WPP_SF_d
0x180020287  mov     eax, ebx
0x180020289  mov     rbx, [rsp+28h+arg_0]
0x18002028e  add     rsp, 20h
0x180020292  pop     rsi
0x180020293  retn
```
