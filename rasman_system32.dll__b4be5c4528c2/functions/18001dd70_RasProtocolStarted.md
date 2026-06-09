# RasProtocolStarted

- ea: `0x18001dd70`
- end: `0x18001de32`
- name: `RasProtocolStarted`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x18001dd70`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
__int64 __fastcall RasProtocolStarted(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 539, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v2 = SubmitLocalRequest(0x5Au, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 540, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 541, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001dd70  mov     [rsp+arg_0], rbx
0x18001dd75  push    rsi
0x18001dd76  sub     rsp, 20h
0x18001dd7a  mov     rbx, rcx
0x18001dd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd84  lea     rsi, WPP_GLOBAL_Control
0x18001dd8b  cmp     rcx, rsi
0x18001dd8e  jz      short loc_18001DDB1
0x18001dd90  test    byte ptr [rcx+1Ch], 40h
0x18001dd94  jz      short loc_18001DDB1
0x18001dd96  cmp     byte ptr [rcx+19h], 6
0x18001dd9a  jb      short loc_18001DDB1
0x18001dd9c  mov     rcx, [rcx+10h]
0x18001dda0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dda7  mov     edx, 21Bh
0x18001ddac  call    WPP_SF_
0x18001ddb1  mov     ecx, 5Ah ; 'Z'
0x18001ddb6  mov     rdx, rbx
0x18001ddb9  call    SubmitLocalRequest
0x18001ddbe  mov     ebx, eax
0x18001ddc0  test    eax, eax
0x18001ddc2  jz      short loc_18001DDF4
0x18001ddc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddcb  cmp     rcx, rsi
0x18001ddce  jz      short loc_18001DE24
0x18001ddd0  test    byte ptr [rcx+1Ch], 40h
0x18001ddd4  jz      short loc_18001DDFB
0x18001ddd6  cmp     byte ptr [rcx+19h], 2
0x18001ddda  jb      short loc_18001DDFB
0x18001dddc  mov     rcx, [rcx+10h]
0x18001dde0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dde7  mov     edx, 21Ch
0x18001ddec  mov     r9d, eax
0x18001ddef  call    WPP_SF_d
0x18001ddf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddfb  cmp     rcx, rsi
0x18001ddfe  jz      short loc_18001DE24
0x18001de00  test    byte ptr [rcx+1Ch], 40h
0x18001de04  jz      short loc_18001DE24
0x18001de06  cmp     byte ptr [rcx+19h], 6
0x18001de0a  jb      short loc_18001DE24
0x18001de0c  mov     rcx, [rcx+10h]
0x18001de10  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001de17  mov     edx, 21Dh
0x18001de1c  mov     r9d, ebx
0x18001de1f  call    WPP_SF_d
0x18001de24  mov     eax, ebx
0x18001de26  mov     rbx, [rsp+28h+arg_0]
0x18001de2b  add     rsp, 20h
0x18001de2f  pop     rsi
0x18001de30  retn
```
