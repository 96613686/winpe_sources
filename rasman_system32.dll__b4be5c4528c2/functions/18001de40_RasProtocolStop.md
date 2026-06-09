# RasProtocolStop

- ea: `0x18001de40`
- end: `0x18001df45`
- name: `RasProtocolStop`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001de40`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasProtocolStop(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 430, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v3 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 431;
LABEL_20:
      WPP_SF_d(v2[2], v4, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
      return v3;
    }
    return v3;
  }
  v5 = SubmitLocalRequest(0x40u, a1);
  v3 = v5;
  if ( v5 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 432, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v4 = 433;
    goto LABEL_20;
  }
  return v3;
}

```

## disassembly

```asm
0x18001de40  mov     [rsp+arg_0], rbx
0x18001de45  mov     [rsp+arg_8], rsi
0x18001de4a  push    rdi
0x18001de4b  sub     rsp, 20h
0x18001de4f  mov     rbx, rcx
0x18001de52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de59  lea     rsi, WPP_GLOBAL_Control
0x18001de60  mov     edi, 40h ; '@'
0x18001de65  cmp     rcx, rsi
0x18001de68  jz      short loc_18001DE8E
0x18001de6a  test    [rcx+1Ch], dil
0x18001de6e  jz      short loc_18001DE8E
0x18001de70  cmp     byte ptr [rcx+19h], 6
0x18001de74  jb      short loc_18001DE8E
0x18001de76  mov     rcx, [rcx+10h]
0x18001de7a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001de81  mov     edx, 1AEh
0x18001de86  mov     r9, rbx
0x18001de89  call    WPP_SF_q
0x18001de8e  mov     rcx, rbx
0x18001de91  call    ValidatePortHandle
0x18001de96  test    eax, eax
0x18001de98  jnz     short loc_18001DEC2
0x18001de9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dea1  mov     ebx, 259h
0x18001dea6  cmp     rcx, rsi
0x18001dea9  jz      loc_18001DF32
0x18001deaf  test    [rcx+1Ch], dil
0x18001deb3  jz      short loc_18001DF32
0x18001deb5  cmp     byte ptr [rcx+19h], 2
0x18001deb9  jb      short loc_18001DF32
0x18001debb  mov     edx, 1AFh
0x18001dec0  jmp     short loc_18001DF1F
0x18001dec2  mov     rdx, rbx
0x18001dec5  mov     ecx, edi
0x18001dec7  call    SubmitLocalRequest
0x18001decc  mov     ebx, eax
0x18001dece  test    eax, eax
0x18001ded0  jz      short loc_18001DF02
0x18001ded2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ded9  cmp     rcx, rsi
0x18001dedc  jz      short loc_18001DF32
0x18001dede  test    [rcx+1Ch], dil
0x18001dee2  jz      short loc_18001DF09
0x18001dee4  cmp     byte ptr [rcx+19h], 2
0x18001dee8  jb      short loc_18001DF09
0x18001deea  mov     rcx, [rcx+10h]
0x18001deee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001def5  mov     edx, 1B0h
0x18001defa  mov     r9d, eax
0x18001defd  call    WPP_SF_d
0x18001df02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df09  cmp     rcx, rsi
0x18001df0c  jz      short loc_18001DF32
0x18001df0e  test    [rcx+1Ch], dil
0x18001df12  jz      short loc_18001DF32
0x18001df14  cmp     byte ptr [rcx+19h], 6
0x18001df18  jb      short loc_18001DF32
0x18001df1a  mov     edx, 1B1h
0x18001df1f  mov     rcx, [rcx+10h]
0x18001df23  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001df2a  mov     r9d, ebx
0x18001df2d  call    WPP_SF_d
0x18001df32  mov     rsi, [rsp+28h+arg_8]
0x18001df37  mov     eax, ebx
0x18001df39  mov     rbx, [rsp+28h+arg_0]
0x18001df3e  add     rsp, 20h
0x18001df42  pop     rdi
0x18001df43  retn
```
