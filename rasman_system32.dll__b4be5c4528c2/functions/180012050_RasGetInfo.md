# RasGetInfo

- ea: `0x180012050`
- end: `0x1800121ae`
- name: `RasGetInfo`
- size: `350`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e9c0`
- `0x18001eb40`
- `0x18001ed70`

## callees

- `0x180011f80`
- `0x180012050`
- `0x1800121b4`
- `0x180012330`
- `0x180021b14`
- `0x1800225a0`

## pseudocode

```c
__int64 __fastcall RasGetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  USHORT v9; // dx
  int v10; // r9d

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, a3, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a2) )
  {
    v7 = 601;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_6;
      v9 = 234;
LABEL_19:
      v10 = v7;
LABEL_28:
      WPP_SF_d((TRACEHANDLE)v8[2], v9, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
      goto LABEL_5;
    }
    return v7;
  }
  if ( !(unsigned int)ValidateConnectionHandle(a1) )
  {
    v7 = -2147024809;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_6;
      v9 = 235;
      goto LABEL_19;
    }
    return v7;
  }
  result = SubmitRequest(a1, 0x16u, a2, a3);
  v7 = result;
  if ( !(_DWORD)result )
  {
LABEL_5:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 236;
      v10 = result;
      goto LABEL_28;
    }
LABEL_6:
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      WPP_SF_d((TRACEHANDLE)v8[2], 0xEDu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180012050  push    rbx
0x180012052  push    rbp
0x180012053  push    rsi
0x180012054  push    rdi
0x180012055  sub     rsp, 38h
0x180012059  mov     rsi, r8
0x18001205c  mov     rbx, rdx
0x18001205f  mov     rdi, rcx
0x180012062  mov     rcx, cs:WPP_GLOBAL_Control
0x180012069  lea     rbp, WPP_GLOBAL_Control
0x180012070  cmp     rcx, rbp
0x180012073  jnz     short loc_1800120CA
0x180012075  mov     rcx, rbx
0x180012078  call    ValidatePortHandle
0x18001207d  test    eax, eax
0x18001207f  jz      loc_180012114
0x180012085  mov     rcx, rdi
0x180012088  call    ValidateConnectionHandle
0x18001208d  test    eax, eax
0x18001208f  jz      loc_180012142
0x180012095  mov     edx, 16h
0x18001209a  mov     r9, rsi
0x18001209d  mov     r8, rbx
0x1800120a0  mov     rcx, rdi
0x1800120a3  call    SubmitRequest
0x1800120a8  mov     ebx, eax
0x1800120aa  test    eax, eax
0x1800120ac  jnz     loc_18001216D
0x1800120b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120b9  cmp     rcx, rbp
0x1800120bc  jnz     short loc_1800120EE
0x1800120be  mov     eax, ebx
0x1800120c0  add     rsp, 38h
0x1800120c4  pop     rdi
0x1800120c5  pop     rsi
0x1800120c6  pop     rbp
0x1800120c7  pop     rbx
0x1800120c8  retn
0x1800120ca  test    byte ptr [rcx+1Ch], 40h
0x1800120ce  jz      short loc_180012075
0x1800120d0  cmp     byte ptr [rcx+19h], 6
0x1800120d4  jb      short loc_180012075
0x1800120d6  mov     rcx, [rcx+10h]
0x1800120da  mov     edx, 0E9h
0x1800120df  mov     r9, rdi
0x1800120e2  mov     [rsp+58h+var_38], rbx
0x1800120e7  call    WPP_SF_qq
0x1800120ec  jmp     short loc_180012075
0x1800120ee  test    byte ptr [rcx+1Ch], 40h
0x1800120f2  jz      short loc_1800120BE
0x1800120f4  cmp     byte ptr [rcx+19h], 6
0x1800120f8  jb      short loc_1800120BE
0x1800120fa  mov     rcx, [rcx+10h]
0x1800120fe  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180012105  mov     edx, 0EDh
0x18001210a  mov     r9d, ebx
0x18001210d  call    WPP_SF_d
0x180012112  jmp     short loc_1800120BE
0x180012114  mov     ebx, 259h
0x180012119  mov     rcx, cs:WPP_GLOBAL_Control
0x180012120  cmp     rcx, rbp
0x180012123  jz      short loc_1800120BE
0x180012125  test    byte ptr [rcx+1Ch], 40h
0x180012129  jz      short loc_1800120B9
0x18001212b  cmp     byte ptr [rcx+19h], 2
0x18001212f  jb      short loc_1800120B9
0x180012131  mov     edx, 0EAh
0x180012136  jmp     short loc_18001213D
0x180012138  mov     edx, 0EBh
0x18001213d  mov     r9d, ebx
0x180012140  jmp     short loc_180012199
0x180012142  mov     ebx, 80070057h
0x180012147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001214e  cmp     rcx, rbp
0x180012151  jz      loc_1800120BE
0x180012157  test    byte ptr [rcx+1Ch], 40h
0x18001215b  jz      loc_1800120B9
0x180012161  cmp     byte ptr [rcx+19h], 2
0x180012165  jb      loc_1800120B9
0x18001216b  jmp     short loc_180012138
0x18001216d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012174  cmp     rcx, rbp
0x180012177  jz      loc_1800120C0
0x18001217d  test    byte ptr [rcx+1Ch], 40h
0x180012181  jz      loc_1800120B9
0x180012187  cmp     byte ptr [rcx+19h], 2
0x18001218b  jb      loc_1800120B9
0x180012191  mov     edx, 0ECh
0x180012196  mov     r9d, eax
0x180012199  mov     rcx, [rcx+10h]
0x18001219d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800121a4  call    WPP_SF_d
0x1800121a9  jmp     loc_1800120B2
```
