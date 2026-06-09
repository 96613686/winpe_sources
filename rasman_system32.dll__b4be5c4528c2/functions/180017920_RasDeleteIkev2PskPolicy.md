# RasDeleteIkev2PskPolicy

- ea: `0x180017920`
- end: `0x1800179e5`
- name: `RasDeleteIkev2PskPolicy`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800030d0`
- `0x180017920`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasDeleteIkev2PskPolicy(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 703, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v2 = SubmitLocalRequest(0x8Eu, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 704, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 705, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180017920  mov     [rsp+arg_0], rbx
0x180017925  push    rsi
0x180017926  sub     rsp, 20h
0x18001792a  mov     rbx, rcx
0x18001792d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017934  lea     rsi, WPP_GLOBAL_Control
0x18001793b  cmp     rcx, rsi
0x18001793e  jz      short loc_180017964
0x180017940  test    byte ptr [rcx+1Ch], 40h
0x180017944  jz      short loc_180017964
0x180017946  cmp     byte ptr [rcx+19h], 6
0x18001794a  jb      short loc_180017964
0x18001794c  mov     rcx, [rcx+10h]
0x180017950  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180017957  mov     edx, 2BFh
0x18001795c  mov     r9, rbx
0x18001795f  call    WPP_SF_q
0x180017964  mov     ecx, 8Eh
0x180017969  mov     rdx, rbx
0x18001796c  call    SubmitLocalRequest
0x180017971  mov     ebx, eax
0x180017973  test    eax, eax
0x180017975  jz      short loc_1800179A7
0x180017977  mov     rcx, cs:WPP_GLOBAL_Control
0x18001797e  cmp     rcx, rsi
0x180017981  jz      short loc_1800179D7
0x180017983  test    byte ptr [rcx+1Ch], 40h
0x180017987  jz      short loc_1800179AE
0x180017989  cmp     byte ptr [rcx+19h], 2
0x18001798d  jb      short loc_1800179AE
0x18001798f  mov     rcx, [rcx+10h]
0x180017993  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001799a  mov     edx, 2C0h
0x18001799f  mov     r9d, eax
0x1800179a2  call    WPP_SF_d
0x1800179a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179ae  cmp     rcx, rsi
0x1800179b1  jz      short loc_1800179D7
0x1800179b3  test    byte ptr [rcx+1Ch], 40h
0x1800179b7  jz      short loc_1800179D7
0x1800179b9  cmp     byte ptr [rcx+19h], 6
0x1800179bd  jb      short loc_1800179D7
0x1800179bf  mov     rcx, [rcx+10h]
0x1800179c3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800179ca  mov     edx, 2C1h
0x1800179cf  mov     r9d, ebx
0x1800179d2  call    WPP_SF_d
0x1800179d7  mov     eax, ebx
0x1800179d9  mov     rbx, [rsp+28h+arg_0]
0x1800179de  add     rsp, 20h
0x1800179e2  pop     rsi
0x1800179e3  retn
```
