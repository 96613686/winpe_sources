# RasPortEnumProtocols

- ea: `0x18001b550`
- end: `0x18001b657`
- name: `RasPortEnumProtocols`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001b550`
- `0x180021b14`
- `0x180021fd4`

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
0x18001b550  push    rbx
0x18001b552  push    rsi
0x18001b553  push    rdi
0x18001b554  push    r14
0x18001b556  sub     rsp, 28h
0x18001b55a  mov     rdi, r8
0x18001b55d  mov     rsi, rdx
0x18001b560  mov     rbx, rcx
0x18001b563  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b56a  lea     r14, WPP_GLOBAL_Control
0x18001b571  cmp     rcx, r14
0x18001b574  jz      short loc_18001B59A
0x18001b576  test    byte ptr [rcx+1Ch], 40h
0x18001b57a  jz      short loc_18001B59A
0x18001b57c  cmp     byte ptr [rcx+19h], 6
0x18001b580  jb      short loc_18001B59A
0x18001b582  mov     rcx, [rcx+10h]
0x18001b586  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b58d  mov     edx, 121h
0x18001b592  mov     r9, rbx
0x18001b595  call    WPP_SF_q
0x18001b59a  mov     rcx, rbx
0x18001b59d  call    ValidatePortHandle
0x18001b5a2  test    eax, eax
0x18001b5a4  jnz     short loc_18001B5D1
0x18001b5a6  mov     ebx, 259h
0x18001b5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5b2  cmp     rcx, r14
0x18001b5b5  jz      loc_18001B64A
0x18001b5bb  test    byte ptr [rcx+1Ch], 40h
0x18001b5bf  jz      short loc_18001B621
0x18001b5c1  cmp     byte ptr [rcx+19h], 2
0x18001b5c5  jb      short loc_18001B621
0x18001b5c7  mov     edx, 122h
0x18001b5cc  mov     r9d, ebx
0x18001b5cf  jmp     short loc_18001B60A
0x18001b5d1  mov     ecx, 22h ; '"'
0x18001b5d6  mov     r9, rdi
0x18001b5d9  mov     r8, rsi
0x18001b5dc  mov     rdx, rbx
0x18001b5df  call    SubmitLocalRequest
0x18001b5e4  mov     ebx, eax
0x18001b5e6  test    eax, eax
0x18001b5e8  jz      short loc_18001B61A
0x18001b5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5f1  cmp     rcx, r14
0x18001b5f4  jz      short loc_18001B64A
0x18001b5f6  test    byte ptr [rcx+1Ch], 40h
0x18001b5fa  jz      short loc_18001B621
0x18001b5fc  cmp     byte ptr [rcx+19h], 2
0x18001b600  jb      short loc_18001B621
0x18001b602  mov     edx, 123h
0x18001b607  mov     r9d, eax
0x18001b60a  mov     rcx, [rcx+10h]
0x18001b60e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b615  call    WPP_SF_d
0x18001b61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b621  cmp     rcx, r14
0x18001b624  jz      short loc_18001B64A
0x18001b626  test    byte ptr [rcx+1Ch], 40h
0x18001b62a  jz      short loc_18001B64A
0x18001b62c  cmp     byte ptr [rcx+19h], 6
0x18001b630  jb      short loc_18001B64A
0x18001b632  mov     rcx, [rcx+10h]
0x18001b636  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b63d  mov     edx, 124h
0x18001b642  mov     r9d, ebx
0x18001b645  call    WPP_SF_d
0x18001b64a  mov     eax, ebx
0x18001b64c  add     rsp, 28h
0x18001b650  pop     r14
0x18001b652  pop     rdi
0x18001b653  pop     rsi
0x18001b654  pop     rbx
0x18001b655  retn
```
