# RasProtocolRetry

- ea: `0x18001cc10`
- end: `0x18001cd25`
- name: `RasProtocolRetry`
- size: `277`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001cc10`
- `0x180021000`
- `0x180021488`

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
0x18001cc10  push    rbx
0x18001cc12  push    rbp
0x18001cc13  push    rsi
0x18001cc14  push    rdi
0x18001cc15  push    r15
0x18001cc17  sub     rsp, 30h
0x18001cc1b  mov     rdi, r9
0x18001cc1e  mov     rsi, r8
0x18001cc21  mov     rbp, rdx
0x18001cc24  mov     rbx, rcx
0x18001cc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc2e  lea     r15, WPP_GLOBAL_Control
0x18001cc35  cmp     rcx, r15
0x18001cc38  jz      short loc_18001CC5E
0x18001cc3a  test    byte ptr [rcx+1Ch], 40h
0x18001cc3e  jz      short loc_18001CC5E
0x18001cc40  cmp     byte ptr [rcx+19h], 6
0x18001cc44  jb      short loc_18001CC5E
0x18001cc46  mov     rcx, [rcx+10h]
0x18001cc4a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cc51  mov     edx, 1BEh
0x18001cc56  mov     r9, rbx
0x18001cc59  call    WPP_SF_q
0x18001cc5e  mov     rcx, rbx
0x18001cc61  call    ValidatePortHandle
0x18001cc66  test    eax, eax
0x18001cc68  jnz     short loc_18001CC9A
0x18001cc6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc71  mov     ebx, 259h
0x18001cc76  cmp     rcx, r15
0x18001cc79  jz      loc_18001CD18
0x18001cc7f  test    byte ptr [rcx+1Ch], 40h
0x18001cc83  jz      loc_18001CD18
0x18001cc89  cmp     byte ptr [rcx+19h], 2
0x18001cc8d  jb      loc_18001CD18
0x18001cc93  mov     edx, 1BFh
0x18001cc98  jmp     short loc_18001CD05
0x18001cc9a  mov     ecx, 42h ; 'B'
0x18001cc9f  mov     [rsp+58h+var_38], rdi
0x18001cca4  mov     r9, rsi
0x18001cca7  mov     r8, rbp
0x18001ccaa  mov     rdx, rbx
0x18001ccad  call    SubmitLocalRequest
0x18001ccb2  mov     ebx, eax
0x18001ccb4  test    eax, eax
0x18001ccb6  jz      short loc_18001CCE8
0x18001ccb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccbf  cmp     rcx, r15
0x18001ccc2  jz      short loc_18001CD18
0x18001ccc4  test    byte ptr [rcx+1Ch], 40h
0x18001ccc8  jz      short loc_18001CCEF
0x18001ccca  cmp     byte ptr [rcx+19h], 2
0x18001ccce  jb      short loc_18001CCEF
0x18001ccd0  mov     rcx, [rcx+10h]
0x18001ccd4  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ccdb  mov     edx, 1C0h
0x18001cce0  mov     r9d, eax
0x18001cce3  call    WPP_SF_d
0x18001cce8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccef  cmp     rcx, r15
0x18001ccf2  jz      short loc_18001CD18
0x18001ccf4  test    byte ptr [rcx+1Ch], 40h
0x18001ccf8  jz      short loc_18001CD18
0x18001ccfa  cmp     byte ptr [rcx+19h], 6
0x18001ccfe  jb      short loc_18001CD18
0x18001cd00  mov     edx, 1C1h
0x18001cd05  mov     rcx, [rcx+10h]
0x18001cd09  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cd10  mov     r9d, ebx
0x18001cd13  call    WPP_SF_d
0x18001cd18  mov     eax, ebx
0x18001cd1a  add     rsp, 30h
0x18001cd1e  pop     r15
0x18001cd20  pop     rdi
0x18001cd21  pop     rsi
0x18001cd22  pop     rbp
0x18001cd23  pop     rbx
0x18001cd24  retn
```
