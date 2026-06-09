# RasProtocolStop

- ea: `0x18001d3f0`
- end: `0x18001d4f4`
- name: `RasProtocolStop`
- size: `260`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001d3f0`
- `0x180021000`
- `0x180021488`

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
0x18001d3f0  mov     [rsp+arg_0], rbx
0x18001d3f5  mov     [rsp+arg_8], rsi
0x18001d3fa  push    rdi
0x18001d3fb  sub     rsp, 20h
0x18001d3ff  mov     rbx, rcx
0x18001d402  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d409  lea     rsi, WPP_GLOBAL_Control
0x18001d410  mov     edi, 40h ; '@'
0x18001d415  cmp     rcx, rsi
0x18001d418  jz      short loc_18001D43E
0x18001d41a  test    [rcx+1Ch], dil
0x18001d41e  jz      short loc_18001D43E
0x18001d420  cmp     byte ptr [rcx+19h], 6
0x18001d424  jb      short loc_18001D43E
0x18001d426  mov     rcx, [rcx+10h]
0x18001d42a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d431  mov     edx, 1AEh
0x18001d436  mov     r9, rbx
0x18001d439  call    WPP_SF_q
0x18001d43e  mov     rcx, rbx
0x18001d441  call    ValidatePortHandle
0x18001d446  test    eax, eax
0x18001d448  jnz     short loc_18001D472
0x18001d44a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d451  mov     ebx, 259h
0x18001d456  cmp     rcx, rsi
0x18001d459  jz      loc_18001D4E2
0x18001d45f  test    [rcx+1Ch], dil
0x18001d463  jz      short loc_18001D4E2
0x18001d465  cmp     byte ptr [rcx+19h], 2
0x18001d469  jb      short loc_18001D4E2
0x18001d46b  mov     edx, 1AFh
0x18001d470  jmp     short loc_18001D4CF
0x18001d472  mov     rdx, rbx
0x18001d475  mov     ecx, edi
0x18001d477  call    SubmitLocalRequest
0x18001d47c  mov     ebx, eax
0x18001d47e  test    eax, eax
0x18001d480  jz      short loc_18001D4B2
0x18001d482  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d489  cmp     rcx, rsi
0x18001d48c  jz      short loc_18001D4E2
0x18001d48e  test    [rcx+1Ch], dil
0x18001d492  jz      short loc_18001D4B9
0x18001d494  cmp     byte ptr [rcx+19h], 2
0x18001d498  jb      short loc_18001D4B9
0x18001d49a  mov     rcx, [rcx+10h]
0x18001d49e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d4a5  mov     edx, 1B0h
0x18001d4aa  mov     r9d, eax
0x18001d4ad  call    WPP_SF_d
0x18001d4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4b9  cmp     rcx, rsi
0x18001d4bc  jz      short loc_18001D4E2
0x18001d4be  test    [rcx+1Ch], dil
0x18001d4c2  jz      short loc_18001D4E2
0x18001d4c4  cmp     byte ptr [rcx+19h], 6
0x18001d4c8  jb      short loc_18001D4E2
0x18001d4ca  mov     edx, 1B1h
0x18001d4cf  mov     rcx, [rcx+10h]
0x18001d4d3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d4da  mov     r9d, ebx
0x18001d4dd  call    WPP_SF_d
0x18001d4e2  mov     rsi, [rsp+28h+arg_8]
0x18001d4e7  mov     eax, ebx
0x18001d4e9  mov     rbx, [rsp+28h+arg_0]
0x18001d4ee  add     rsp, 20h
0x18001d4f2  pop     rdi
0x18001d4f3  retn
```
