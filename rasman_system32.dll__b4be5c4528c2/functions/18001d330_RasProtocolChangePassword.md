# RasProtocolChangePassword

- ea: `0x18001d330`
- end: `0x18001d446`
- name: `RasProtocolChangePassword`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001d330`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasProtocolChangePassword(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 438, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 439;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x44u, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 440, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 441;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001d330  push    rbx
0x18001d332  push    rbp
0x18001d333  push    rsi
0x18001d334  push    rdi
0x18001d335  push    r15
0x18001d337  sub     rsp, 30h
0x18001d33b  mov     rdi, r9
0x18001d33e  mov     rsi, r8
0x18001d341  mov     rbp, rdx
0x18001d344  mov     rbx, rcx
0x18001d347  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d34e  lea     r15, WPP_GLOBAL_Control
0x18001d355  cmp     rcx, r15
0x18001d358  jz      short loc_18001D37E
0x18001d35a  test    byte ptr [rcx+1Ch], 40h
0x18001d35e  jz      short loc_18001D37E
0x18001d360  cmp     byte ptr [rcx+19h], 6
0x18001d364  jb      short loc_18001D37E
0x18001d366  mov     rcx, [rcx+10h]
0x18001d36a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d371  mov     edx, 1B6h
0x18001d376  mov     r9, rbx
0x18001d379  call    WPP_SF_q
0x18001d37e  mov     rcx, rbx
0x18001d381  call    ValidatePortHandle
0x18001d386  test    eax, eax
0x18001d388  jnz     short loc_18001D3BA
0x18001d38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d391  mov     ebx, 259h
0x18001d396  cmp     rcx, r15
0x18001d399  jz      loc_18001D438
0x18001d39f  test    byte ptr [rcx+1Ch], 40h
0x18001d3a3  jz      loc_18001D438
0x18001d3a9  cmp     byte ptr [rcx+19h], 2
0x18001d3ad  jb      loc_18001D438
0x18001d3b3  mov     edx, 1B7h
0x18001d3b8  jmp     short loc_18001D425
0x18001d3ba  mov     ecx, 44h ; 'D'
0x18001d3bf  mov     [rsp+58h+var_38], rdi
0x18001d3c4  mov     r9, rsi
0x18001d3c7  mov     r8, rbp
0x18001d3ca  mov     rdx, rbx
0x18001d3cd  call    SubmitLocalRequest
0x18001d3d2  mov     ebx, eax
0x18001d3d4  test    eax, eax
0x18001d3d6  jz      short loc_18001D408
0x18001d3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3df  cmp     rcx, r15
0x18001d3e2  jz      short loc_18001D438
0x18001d3e4  test    byte ptr [rcx+1Ch], 40h
0x18001d3e8  jz      short loc_18001D40F
0x18001d3ea  cmp     byte ptr [rcx+19h], 2
0x18001d3ee  jb      short loc_18001D40F
0x18001d3f0  mov     rcx, [rcx+10h]
0x18001d3f4  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d3fb  mov     edx, 1B8h
0x18001d400  mov     r9d, eax
0x18001d403  call    WPP_SF_d
0x18001d408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d40f  cmp     rcx, r15
0x18001d412  jz      short loc_18001D438
0x18001d414  test    byte ptr [rcx+1Ch], 40h
0x18001d418  jz      short loc_18001D438
0x18001d41a  cmp     byte ptr [rcx+19h], 6
0x18001d41e  jb      short loc_18001D438
0x18001d420  mov     edx, 1B9h
0x18001d425  mov     rcx, [rcx+10h]
0x18001d429  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d430  mov     r9d, ebx
0x18001d433  call    WPP_SF_d
0x18001d438  mov     eax, ebx
0x18001d43a  add     rsp, 30h
0x18001d43e  pop     r15
0x18001d440  pop     rdi
0x18001d441  pop     rsi
0x18001d442  pop     rbp
0x18001d443  pop     rbx
0x18001d444  retn
```
