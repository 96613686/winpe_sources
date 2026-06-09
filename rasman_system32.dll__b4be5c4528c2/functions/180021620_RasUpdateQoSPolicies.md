# RasUpdateQoSPolicies

- ea: `0x180021620`
- end: `0x1800216e2`
- name: `RasUpdateQoSPolicies`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800030d0`
- `0x180021620`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
__int64 __fastcall RasUpdateQoSPolicies(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 730, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v2 = SubmitLocalRequest(0x98u, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 731, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 732, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180021620  mov     [rsp+arg_0], rbx
0x180021625  push    rsi
0x180021626  sub     rsp, 20h
0x18002162a  mov     rbx, rcx
0x18002162d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021634  lea     rsi, WPP_GLOBAL_Control
0x18002163b  cmp     rcx, rsi
0x18002163e  jz      short loc_180021661
0x180021640  test    byte ptr [rcx+1Ch], 40h
0x180021644  jz      short loc_180021661
0x180021646  cmp     byte ptr [rcx+19h], 6
0x18002164a  jb      short loc_180021661
0x18002164c  mov     rcx, [rcx+10h]
0x180021650  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021657  mov     edx, 2DAh
0x18002165c  call    WPP_SF_
0x180021661  mov     ecx, 98h
0x180021666  mov     rdx, rbx
0x180021669  call    SubmitLocalRequest
0x18002166e  mov     ebx, eax
0x180021670  test    eax, eax
0x180021672  jz      short loc_1800216A4
0x180021674  mov     rcx, cs:WPP_GLOBAL_Control
0x18002167b  cmp     rcx, rsi
0x18002167e  jz      short loc_1800216D4
0x180021680  test    byte ptr [rcx+1Ch], 40h
0x180021684  jz      short loc_1800216AB
0x180021686  cmp     byte ptr [rcx+19h], 2
0x18002168a  jb      short loc_1800216AB
0x18002168c  mov     rcx, [rcx+10h]
0x180021690  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021697  mov     edx, 2DBh
0x18002169c  mov     r9d, eax
0x18002169f  call    WPP_SF_d
0x1800216a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216ab  cmp     rcx, rsi
0x1800216ae  jz      short loc_1800216D4
0x1800216b0  test    byte ptr [rcx+1Ch], 40h
0x1800216b4  jz      short loc_1800216D4
0x1800216b6  cmp     byte ptr [rcx+19h], 6
0x1800216ba  jb      short loc_1800216D4
0x1800216bc  mov     rcx, [rcx+10h]
0x1800216c0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800216c7  mov     edx, 2DCh
0x1800216cc  mov     r9d, ebx
0x1800216cf  call    WPP_SF_d
0x1800216d4  mov     eax, ebx
0x1800216d6  mov     rbx, [rsp+28h+arg_0]
0x1800216db  add     rsp, 20h
0x1800216df  pop     rsi
0x1800216e0  retn
```
