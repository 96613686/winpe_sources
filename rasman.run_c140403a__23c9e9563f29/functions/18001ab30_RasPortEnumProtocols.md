# RasPortEnumProtocols

- ea: `0x18001ab30`
- end: `0x18001ac36`
- name: `RasPortEnumProtocols`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001ab30`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasPortEnumProtocols(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 289, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( (unsigned int)ValidatePortHandle(a1) )
  {
    v10 = SubmitLocalRequest(0x22u, a1, a2, a3);
    v6 = v10;
    if ( !v10 )
    {
LABEL_16:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v8 = 291;
    v9 = v10;
LABEL_15:
    WPP_SF_d(v7[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
    goto LABEL_16;
  }
  v6 = 601;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 290;
    v9 = 601;
    goto LABEL_15;
  }
LABEL_17:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 292, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001ab30  push    rbx
0x18001ab32  push    rsi
0x18001ab33  push    rdi
0x18001ab34  push    r14
0x18001ab36  sub     rsp, 28h
0x18001ab3a  mov     rdi, r8
0x18001ab3d  mov     rsi, rdx
0x18001ab40  mov     rbx, rcx
0x18001ab43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab4a  lea     r14, WPP_GLOBAL_Control
0x18001ab51  cmp     rcx, r14
0x18001ab54  jz      short loc_18001AB7A
0x18001ab56  test    byte ptr [rcx+1Ch], 40h
0x18001ab5a  jz      short loc_18001AB7A
0x18001ab5c  cmp     byte ptr [rcx+19h], 6
0x18001ab60  jb      short loc_18001AB7A
0x18001ab62  mov     rcx, [rcx+10h]
0x18001ab66  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ab6d  mov     edx, 121h
0x18001ab72  mov     r9, rbx
0x18001ab75  call    WPP_SF_q
0x18001ab7a  mov     rcx, rbx
0x18001ab7d  call    ValidatePortHandle
0x18001ab82  test    eax, eax
0x18001ab84  jnz     short loc_18001ABB1
0x18001ab86  mov     ebx, 259h
0x18001ab8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab92  cmp     rcx, r14
0x18001ab95  jz      loc_18001AC2A
0x18001ab9b  test    byte ptr [rcx+1Ch], 40h
0x18001ab9f  jz      short loc_18001AC01
0x18001aba1  cmp     byte ptr [rcx+19h], 2
0x18001aba5  jb      short loc_18001AC01
0x18001aba7  mov     edx, 122h
0x18001abac  mov     r9d, ebx
0x18001abaf  jmp     short loc_18001ABEA
0x18001abb1  mov     ecx, 22h ; '"'
0x18001abb6  mov     r9, rdi
0x18001abb9  mov     r8, rsi
0x18001abbc  mov     rdx, rbx
0x18001abbf  call    SubmitLocalRequest
0x18001abc4  mov     ebx, eax
0x18001abc6  test    eax, eax
0x18001abc8  jz      short loc_18001ABFA
0x18001abca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abd1  cmp     rcx, r14
0x18001abd4  jz      short loc_18001AC2A
0x18001abd6  test    byte ptr [rcx+1Ch], 40h
0x18001abda  jz      short loc_18001AC01
0x18001abdc  cmp     byte ptr [rcx+19h], 2
0x18001abe0  jb      short loc_18001AC01
0x18001abe2  mov     edx, 123h
0x18001abe7  mov     r9d, eax
0x18001abea  mov     rcx, [rcx+10h]
0x18001abee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001abf5  call    WPP_SF_d
0x18001abfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac01  cmp     rcx, r14
0x18001ac04  jz      short loc_18001AC2A
0x18001ac06  test    byte ptr [rcx+1Ch], 40h
0x18001ac0a  jz      short loc_18001AC2A
0x18001ac0c  cmp     byte ptr [rcx+19h], 6
0x18001ac10  jb      short loc_18001AC2A
0x18001ac12  mov     rcx, [rcx+10h]
0x18001ac16  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ac1d  mov     edx, 124h
0x18001ac22  mov     r9d, ebx
0x18001ac25  call    WPP_SF_d
0x18001ac2a  mov     eax, ebx
0x18001ac2c  add     rsp, 28h
0x18001ac30  pop     r14
0x18001ac32  pop     rdi
0x18001ac33  pop     rsi
0x18001ac34  pop     rbx
0x18001ac35  retn
```
