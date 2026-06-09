# RasPortConnectComplete

- ea: `0x18001adf0`
- end: `0x18001af1a`
- name: `RasPortConnectComplete`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001adf0`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasPortConnectComplete(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v3 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      {
        v4 = 174;
LABEL_24:
        WPP_SF_d(v2[2], v4, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
        return v3;
      }
    }
    return v3;
  }
  v5 = SubmitLocalRequest(0xBu, a1);
  v3 = v5;
  if ( v5 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v4 = 176;
    goto LABEL_24;
  }
  return v3;
}

```

## disassembly

```asm
0x18001adf0  mov     [rsp+arg_0], rbx
0x18001adf5  mov     [rsp+arg_8], rbp
0x18001adfa  push    rsi
0x18001adfb  sub     rsp, 20h
0x18001adff  mov     rbx, rcx
0x18001ae02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae09  lea     rsi, WPP_GLOBAL_Control
0x18001ae10  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ae17  cmp     rcx, rsi
0x18001ae1a  jz      short loc_18001AE3C
0x18001ae1c  test    byte ptr [rcx+1Ch], 40h
0x18001ae20  jz      short loc_18001AE3C
0x18001ae22  cmp     byte ptr [rcx+19h], 6
0x18001ae26  jb      short loc_18001AE3C
0x18001ae28  mov     rcx, [rcx+10h]
0x18001ae2c  mov     edx, 0ACh
0x18001ae31  mov     r9, rbx
0x18001ae34  mov     r8, rbp
0x18001ae37  call    WPP_SF_q
0x18001ae3c  mov     rcx, rbx
0x18001ae3f  call    ValidatePortHandle
0x18001ae44  test    eax, eax
0x18001ae46  jnz     short loc_18001AE9C
0x18001ae48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae4f  mov     ebx, 259h
0x18001ae54  cmp     rcx, rsi
0x18001ae57  jz      loc_18001AF07
0x18001ae5d  test    byte ptr [rcx+1Ch], 40h
0x18001ae61  jz      short loc_18001AE84
0x18001ae63  cmp     byte ptr [rcx+19h], 2
0x18001ae67  jb      short loc_18001AE84
0x18001ae69  mov     rcx, [rcx+10h]
0x18001ae6d  mov     edx, 0ADh
0x18001ae72  mov     r9d, ebx
0x18001ae75  mov     r8, rbp
0x18001ae78  call    WPP_SF_d
0x18001ae7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae84  cmp     rcx, rsi
0x18001ae87  jz      short loc_18001AF07
0x18001ae89  test    byte ptr [rcx+1Ch], 40h
0x18001ae8d  jz      short loc_18001AF07
0x18001ae8f  cmp     byte ptr [rcx+19h], 6
0x18001ae93  jb      short loc_18001AF07
0x18001ae95  mov     edx, 0AEh
0x18001ae9a  jmp     short loc_18001AEF8
0x18001ae9c  mov     ecx, 0Bh
0x18001aea1  mov     rdx, rbx
0x18001aea4  call    SubmitLocalRequest
0x18001aea9  mov     ebx, eax
0x18001aeab  test    eax, eax
0x18001aead  jz      short loc_18001AEDB
0x18001aeaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aeb6  cmp     rcx, rsi
0x18001aeb9  jz      short loc_18001AF07
0x18001aebb  test    byte ptr [rcx+1Ch], 40h
0x18001aebf  jz      short loc_18001AEE2
0x18001aec1  cmp     byte ptr [rcx+19h], 2
0x18001aec5  jb      short loc_18001AEE2
0x18001aec7  mov     rcx, [rcx+10h]
0x18001aecb  mov     edx, 0AFh
0x18001aed0  mov     r9d, eax
0x18001aed3  mov     r8, rbp
0x18001aed6  call    WPP_SF_d
0x18001aedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aee2  cmp     rcx, rsi
0x18001aee5  jz      short loc_18001AF07
0x18001aee7  test    byte ptr [rcx+1Ch], 40h
0x18001aeeb  jz      short loc_18001AF07
0x18001aeed  cmp     byte ptr [rcx+19h], 6
0x18001aef1  jb      short loc_18001AF07
0x18001aef3  mov     edx, 0B0h
0x18001aef8  mov     rcx, [rcx+10h]
0x18001aefc  mov     r9d, ebx
0x18001aeff  mov     r8, rbp
0x18001af02  call    WPP_SF_d
0x18001af07  mov     rbp, [rsp+28h+arg_8]
0x18001af0c  mov     eax, ebx
0x18001af0e  mov     rbx, [rsp+28h+arg_0]
0x18001af13  add     rsp, 20h
0x18001af17  pop     rsi
0x18001af18  retn
```
