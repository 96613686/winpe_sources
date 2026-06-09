# RasProtocolRetry

- ea: `0x18001d650`
- end: `0x18001d766`
- name: `RasProtocolRetry`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001d650`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasProtocolRetry(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 446, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 447;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x42u, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 448, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 449;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001d650  push    rbx
0x18001d652  push    rbp
0x18001d653  push    rsi
0x18001d654  push    rdi
0x18001d655  push    r15
0x18001d657  sub     rsp, 30h
0x18001d65b  mov     rdi, r9
0x18001d65e  mov     rsi, r8
0x18001d661  mov     rbp, rdx
0x18001d664  mov     rbx, rcx
0x18001d667  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d66e  lea     r15, WPP_GLOBAL_Control
0x18001d675  cmp     rcx, r15
0x18001d678  jz      short loc_18001D69E
0x18001d67a  test    byte ptr [rcx+1Ch], 40h
0x18001d67e  jz      short loc_18001D69E
0x18001d680  cmp     byte ptr [rcx+19h], 6
0x18001d684  jb      short loc_18001D69E
0x18001d686  mov     rcx, [rcx+10h]
0x18001d68a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d691  mov     edx, 1BEh
0x18001d696  mov     r9, rbx
0x18001d699  call    WPP_SF_q
0x18001d69e  mov     rcx, rbx
0x18001d6a1  call    ValidatePortHandle
0x18001d6a6  test    eax, eax
0x18001d6a8  jnz     short loc_18001D6DA
0x18001d6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6b1  mov     ebx, 259h
0x18001d6b6  cmp     rcx, r15
0x18001d6b9  jz      loc_18001D758
0x18001d6bf  test    byte ptr [rcx+1Ch], 40h
0x18001d6c3  jz      loc_18001D758
0x18001d6c9  cmp     byte ptr [rcx+19h], 2
0x18001d6cd  jb      loc_18001D758
0x18001d6d3  mov     edx, 1BFh
0x18001d6d8  jmp     short loc_18001D745
0x18001d6da  mov     ecx, 42h ; 'B'
0x18001d6df  mov     [rsp+58h+var_38], rdi
0x18001d6e4  mov     r9, rsi
0x18001d6e7  mov     r8, rbp
0x18001d6ea  mov     rdx, rbx
0x18001d6ed  call    SubmitLocalRequest
0x18001d6f2  mov     ebx, eax
0x18001d6f4  test    eax, eax
0x18001d6f6  jz      short loc_18001D728
0x18001d6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6ff  cmp     rcx, r15
0x18001d702  jz      short loc_18001D758
0x18001d704  test    byte ptr [rcx+1Ch], 40h
0x18001d708  jz      short loc_18001D72F
0x18001d70a  cmp     byte ptr [rcx+19h], 2
0x18001d70e  jb      short loc_18001D72F
0x18001d710  mov     rcx, [rcx+10h]
0x18001d714  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d71b  mov     edx, 1C0h
0x18001d720  mov     r9d, eax
0x18001d723  call    WPP_SF_d
0x18001d728  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d72f  cmp     rcx, r15
0x18001d732  jz      short loc_18001D758
0x18001d734  test    byte ptr [rcx+1Ch], 40h
0x18001d738  jz      short loc_18001D758
0x18001d73a  cmp     byte ptr [rcx+19h], 6
0x18001d73e  jb      short loc_18001D758
0x18001d740  mov     edx, 1C1h
0x18001d745  mov     rcx, [rcx+10h]
0x18001d749  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d750  mov     r9d, ebx
0x18001d753  call    WPP_SF_d
0x18001d758  mov     eax, ebx
0x18001d75a  add     rsp, 30h
0x18001d75e  pop     r15
0x18001d760  pop     rdi
0x18001d761  pop     rsi
0x18001d762  pop     rbp
0x18001d763  pop     rbx
0x18001d764  retn
```
