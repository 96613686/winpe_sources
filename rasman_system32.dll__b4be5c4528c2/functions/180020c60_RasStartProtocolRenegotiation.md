# RasStartProtocolRenegotiation

- ea: `0x180020c60`
- end: `0x180020d25`
- name: `RasStartProtocolRenegotiation`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x180020c60`
- `0x180021b14`
- `0x180021fd4`

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
0x180020c60  mov     [rsp+arg_0], rbx
0x180020c65  push    rsi
0x180020c66  sub     rsp, 20h
0x180020c6a  mov     rbx, rcx
0x180020c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c74  lea     rsi, WPP_GLOBAL_Control
0x180020c7b  cmp     rcx, rsi
0x180020c7e  jz      short loc_180020CA4
0x180020c80  test    byte ptr [rcx+1Ch], 40h
0x180020c84  jz      short loc_180020CA4
0x180020c86  cmp     byte ptr [rcx+19h], 6
0x180020c8a  jb      short loc_180020CA4
0x180020c8c  mov     rcx, [rcx+10h]
0x180020c90  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020c97  mov     edx, 2A6h
0x180020c9c  mov     r9, rbx
0x180020c9f  call    WPP_SF_q
0x180020ca4  mov     ecx, 82h
0x180020ca9  mov     rdx, rbx
0x180020cac  call    SubmitLocalRequest
0x180020cb1  mov     ebx, eax
0x180020cb3  test    eax, eax
0x180020cb5  jz      short loc_180020CE7
0x180020cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cbe  cmp     rcx, rsi
0x180020cc1  jz      short loc_180020D17
0x180020cc3  test    byte ptr [rcx+1Ch], 40h
0x180020cc7  jz      short loc_180020CEE
0x180020cc9  cmp     byte ptr [rcx+19h], 2
0x180020ccd  jb      short loc_180020CEE
0x180020ccf  mov     rcx, [rcx+10h]
0x180020cd3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020cda  mov     edx, 2A7h
0x180020cdf  mov     r9d, eax
0x180020ce2  call    WPP_SF_d
0x180020ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cee  cmp     rcx, rsi
0x180020cf1  jz      short loc_180020D17
0x180020cf3  test    byte ptr [rcx+1Ch], 40h
0x180020cf7  jz      short loc_180020D17
0x180020cf9  cmp     byte ptr [rcx+19h], 6
0x180020cfd  jb      short loc_180020D17
0x180020cff  mov     rcx, [rcx+10h]
0x180020d03  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020d0a  mov     edx, 2A8h
0x180020d0f  mov     r9d, ebx
0x180020d12  call    WPP_SF_d
0x180020d17  mov     eax, ebx
0x180020d19  mov     rbx, [rsp+28h+arg_0]
0x180020d1e  add     rsp, 20h
0x180020d22  pop     rsi
0x180020d23  retn
```
