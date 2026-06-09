# RasGetNumPortOpen

- ea: `0x180019de0`
- end: `0x180019e9c`
- name: `RasGetNumPortOpen`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800030d0`
- `0x180019de0`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
__int64 RasGetNumPortOpen()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 536, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v0 = SubmitLocalRequest(0x1Cu);
  v1 = v0;
  if ( !v0 )
    goto LABEL_10;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 537, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v0);
LABEL_10:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 538, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180019de0  mov     [rsp+arg_0], rbx
0x180019de5  push    rsi
0x180019de6  sub     rsp, 20h
0x180019dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180019df1  lea     rsi, WPP_GLOBAL_Control
0x180019df8  cmp     rcx, rsi
0x180019dfb  jz      short loc_180019E1E
0x180019dfd  test    byte ptr [rcx+1Ch], 40h
0x180019e01  jz      short loc_180019E1E
0x180019e03  cmp     byte ptr [rcx+19h], 6
0x180019e07  jb      short loc_180019E1E
0x180019e09  mov     rcx, [rcx+10h]
0x180019e0d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019e14  mov     edx, 218h
0x180019e19  call    WPP_SF_
0x180019e1e  mov     ecx, 1Ch
0x180019e23  call    SubmitLocalRequest
0x180019e28  mov     ebx, eax
0x180019e2a  test    eax, eax
0x180019e2c  jz      short loc_180019E5E
0x180019e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e35  cmp     rcx, rsi
0x180019e38  jz      short loc_180019E8E
0x180019e3a  test    byte ptr [rcx+1Ch], 40h
0x180019e3e  jz      short loc_180019E65
0x180019e40  cmp     byte ptr [rcx+19h], 2
0x180019e44  jb      short loc_180019E65
0x180019e46  mov     rcx, [rcx+10h]
0x180019e4a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019e51  mov     edx, 219h
0x180019e56  mov     r9d, eax
0x180019e59  call    WPP_SF_d
0x180019e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e65  cmp     rcx, rsi
0x180019e68  jz      short loc_180019E8E
0x180019e6a  test    byte ptr [rcx+1Ch], 40h
0x180019e6e  jz      short loc_180019E8E
0x180019e70  cmp     byte ptr [rcx+19h], 6
0x180019e74  jb      short loc_180019E8E
0x180019e76  mov     rcx, [rcx+10h]
0x180019e7a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019e81  mov     edx, 21Ah
0x180019e86  mov     r9d, ebx
0x180019e89  call    WPP_SF_d
0x180019e8e  mov     eax, ebx
0x180019e90  mov     rbx, [rsp+28h+arg_0]
0x180019e95  add     rsp, 20h
0x180019e99  pop     rsi
0x180019e9a  retn
```
