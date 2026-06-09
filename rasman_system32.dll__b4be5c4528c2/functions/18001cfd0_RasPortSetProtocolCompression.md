# RasPortSetProtocolCompression

- ea: `0x18001cfd0`
- end: `0x18001d0e9`
- name: `RasPortSetProtocolCompression`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001cfd0`
- `0x180021b14`
- `0x180022320`

## pseudocode

```c
__int64 __fastcall RasPortSetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 321;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x2Bu, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 323;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001cfd0  push    rbx
0x18001cfd2  push    rbp
0x18001cfd3  push    rsi
0x18001cfd4  push    rdi
0x18001cfd5  push    r15
0x18001cfd7  sub     rsp, 30h
0x18001cfdb  mov     rsi, r9
0x18001cfde  mov     rbp, r8
0x18001cfe1  mov     edi, edx
0x18001cfe3  mov     rbx, rcx
0x18001cfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfed  lea     r15, WPP_GLOBAL_Control
0x18001cff4  cmp     rcx, r15
0x18001cff7  jz      short loc_18001D021
0x18001cff9  test    byte ptr [rcx+1Ch], 40h
0x18001cffd  jz      short loc_18001D021
0x18001cfff  cmp     byte ptr [rcx+19h], 6
0x18001d003  jb      short loc_18001D021
0x18001d005  mov     rcx, [rcx+10h]
0x18001d009  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d010  mov     edx, 140h
0x18001d015  mov     dword ptr [rsp+58h+var_38], edi
0x18001d019  mov     r9, rbx
0x18001d01c  call    WPP_SF_qd
0x18001d021  mov     rcx, rbx
0x18001d024  call    ValidatePortHandle
0x18001d029  test    eax, eax
0x18001d02b  jnz     short loc_18001D05D
0x18001d02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d034  mov     ebx, 259h
0x18001d039  cmp     rcx, r15
0x18001d03c  jz      loc_18001D0DB
0x18001d042  test    byte ptr [rcx+1Ch], 40h
0x18001d046  jz      loc_18001D0DB
0x18001d04c  cmp     byte ptr [rcx+19h], 2
0x18001d050  jb      loc_18001D0DB
0x18001d056  mov     edx, 141h
0x18001d05b  jmp     short loc_18001D0C8
0x18001d05d  mov     ecx, 2Bh ; '+'
0x18001d062  mov     [rsp+58h+var_38], rsi
0x18001d067  mov     r9, rbp
0x18001d06a  mov     r8d, edi
0x18001d06d  mov     rdx, rbx
0x18001d070  call    SubmitLocalRequest
0x18001d075  mov     ebx, eax
0x18001d077  test    eax, eax
0x18001d079  jz      short loc_18001D0AB
0x18001d07b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d082  cmp     rcx, r15
0x18001d085  jz      short loc_18001D0DB
0x18001d087  test    byte ptr [rcx+1Ch], 40h
0x18001d08b  jz      short loc_18001D0B2
0x18001d08d  cmp     byte ptr [rcx+19h], 2
0x18001d091  jb      short loc_18001D0B2
0x18001d093  mov     rcx, [rcx+10h]
0x18001d097  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d09e  mov     edx, 142h
0x18001d0a3  mov     r9d, eax
0x18001d0a6  call    WPP_SF_d
0x18001d0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0b2  cmp     rcx, r15
0x18001d0b5  jz      short loc_18001D0DB
0x18001d0b7  test    byte ptr [rcx+1Ch], 40h
0x18001d0bb  jz      short loc_18001D0DB
0x18001d0bd  cmp     byte ptr [rcx+19h], 6
0x18001d0c1  jb      short loc_18001D0DB
0x18001d0c3  mov     edx, 143h
0x18001d0c8  mov     rcx, [rcx+10h]
0x18001d0cc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d0d3  mov     r9d, ebx
0x18001d0d6  call    WPP_SF_d
0x18001d0db  mov     eax, ebx
0x18001d0dd  add     rsp, 30h
0x18001d0e1  pop     r15
0x18001d0e3  pop     rdi
0x18001d0e4  pop     rsi
0x18001d0e5  pop     rbp
0x18001d0e6  pop     rbx
0x18001d0e7  retn
```
