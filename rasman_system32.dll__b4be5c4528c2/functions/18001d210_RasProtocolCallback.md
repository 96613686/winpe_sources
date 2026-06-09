# RasProtocolCallback

- ea: `0x18001d210`
- end: `0x18001d31d`
- name: `RasProtocolCallback`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001d210`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasProtocolCallback(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 434, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 435;
LABEL_20:
      WPP_SF_d(v4[2], v6, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = SubmitLocalRequest(0x45u, a1, a2);
  v5 = v7;
  if ( v7 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 436, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 437;
    goto LABEL_20;
  }
  return v5;
}

```

## disassembly

```asm
0x18001d210  mov     [rsp+arg_0], rbx
0x18001d215  mov     [rsp+arg_8], rbp
0x18001d21a  push    rdi
0x18001d21b  sub     rsp, 20h
0x18001d21f  mov     rdi, rdx
0x18001d222  mov     rbx, rcx
0x18001d225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d22c  lea     rbp, WPP_GLOBAL_Control
0x18001d233  cmp     rcx, rbp
0x18001d236  jz      short loc_18001D25C
0x18001d238  test    byte ptr [rcx+1Ch], 40h
0x18001d23c  jz      short loc_18001D25C
0x18001d23e  cmp     byte ptr [rcx+19h], 6
0x18001d242  jb      short loc_18001D25C
0x18001d244  mov     rcx, [rcx+10h]
0x18001d248  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d24f  mov     edx, 1B2h
0x18001d254  mov     r9, rbx
0x18001d257  call    WPP_SF_q
0x18001d25c  mov     rcx, rbx
0x18001d25f  call    ValidatePortHandle
0x18001d264  test    eax, eax
0x18001d266  jnz     short loc_18001D294
0x18001d268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d26f  mov     ebx, 259h
0x18001d274  cmp     rcx, rbp
0x18001d277  jz      loc_18001D30A
0x18001d27d  test    byte ptr [rcx+1Ch], 40h
0x18001d281  jz      loc_18001D30A
0x18001d287  cmp     byte ptr [rcx+19h], 2
0x18001d28b  jb      short loc_18001D30A
0x18001d28d  mov     edx, 1B3h
0x18001d292  jmp     short loc_18001D2F7
0x18001d294  mov     ecx, 45h ; 'E'
0x18001d299  mov     r8, rdi
0x18001d29c  mov     rdx, rbx
0x18001d29f  call    SubmitLocalRequest
0x18001d2a4  mov     ebx, eax
0x18001d2a6  test    eax, eax
0x18001d2a8  jz      short loc_18001D2DA
0x18001d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2b1  cmp     rcx, rbp
0x18001d2b4  jz      short loc_18001D30A
0x18001d2b6  test    byte ptr [rcx+1Ch], 40h
0x18001d2ba  jz      short loc_18001D2E1
0x18001d2bc  cmp     byte ptr [rcx+19h], 2
0x18001d2c0  jb      short loc_18001D2E1
0x18001d2c2  mov     rcx, [rcx+10h]
0x18001d2c6  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d2cd  mov     edx, 1B4h
0x18001d2d2  mov     r9d, eax
0x18001d2d5  call    WPP_SF_d
0x18001d2da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2e1  cmp     rcx, rbp
0x18001d2e4  jz      short loc_18001D30A
0x18001d2e6  test    byte ptr [rcx+1Ch], 40h
0x18001d2ea  jz      short loc_18001D30A
0x18001d2ec  cmp     byte ptr [rcx+19h], 6
0x18001d2f0  jb      short loc_18001D30A
0x18001d2f2  mov     edx, 1B5h
0x18001d2f7  mov     rcx, [rcx+10h]
0x18001d2fb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d302  mov     r9d, ebx
0x18001d305  call    WPP_SF_d
0x18001d30a  mov     rbp, [rsp+28h+arg_8]
0x18001d30f  mov     eax, ebx
0x18001d311  mov     rbx, [rsp+28h+arg_0]
0x18001d316  add     rsp, 20h
0x18001d31a  pop     rdi
0x18001d31b  retn
```
