# RasSendProtocolResultToRasman

- ea: `0x18001e640`
- end: `0x18001e714`
- name: `RasSendProtocolResultToRasman`
- size: `212`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x18001e640`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasSendProtocolResultToRasman(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 427, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v4 = SubmitLocalRequest(0x52u, a1, a2);
  v5 = v4;
  if ( !v4 )
    goto LABEL_10;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 428, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v4);
LABEL_10:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 429, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001e640  mov     [rsp+arg_0], rbx
0x18001e645  mov     [rsp+arg_8], rbp
0x18001e64a  push    rdi
0x18001e64b  sub     rsp, 20h
0x18001e64f  mov     rdi, rdx
0x18001e652  mov     rbx, rcx
0x18001e655  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e65c  lea     rbp, WPP_GLOBAL_Control
0x18001e663  cmp     rcx, rbp
0x18001e666  jz      short loc_18001E68C
0x18001e668  test    byte ptr [rcx+1Ch], 40h
0x18001e66c  jz      short loc_18001E68C
0x18001e66e  cmp     byte ptr [rcx+19h], 6
0x18001e672  jb      short loc_18001E68C
0x18001e674  mov     rcx, [rcx+10h]
0x18001e678  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e67f  mov     edx, 1ABh
0x18001e684  mov     r9, rbx
0x18001e687  call    WPP_SF_q
0x18001e68c  mov     ecx, 52h ; 'R'
0x18001e691  mov     r8, rdi
0x18001e694  mov     rdx, rbx
0x18001e697  call    SubmitLocalRequest
0x18001e69c  mov     ebx, eax
0x18001e69e  test    eax, eax
0x18001e6a0  jz      short loc_18001E6D2
0x18001e6a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6a9  cmp     rcx, rbp
0x18001e6ac  jz      short loc_18001E702
0x18001e6ae  test    byte ptr [rcx+1Ch], 40h
0x18001e6b2  jz      short loc_18001E6D9
0x18001e6b4  cmp     byte ptr [rcx+19h], 2
0x18001e6b8  jb      short loc_18001E6D9
0x18001e6ba  mov     rcx, [rcx+10h]
0x18001e6be  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e6c5  mov     edx, 1ACh
0x18001e6ca  mov     r9d, eax
0x18001e6cd  call    WPP_SF_d
0x18001e6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6d9  cmp     rcx, rbp
0x18001e6dc  jz      short loc_18001E702
0x18001e6de  test    byte ptr [rcx+1Ch], 40h
0x18001e6e2  jz      short loc_18001E702
0x18001e6e4  cmp     byte ptr [rcx+19h], 6
0x18001e6e8  jb      short loc_18001E702
0x18001e6ea  mov     rcx, [rcx+10h]
0x18001e6ee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e6f5  mov     edx, 1ADh
0x18001e6fa  mov     r9d, ebx
0x18001e6fd  call    WPP_SF_d
0x18001e702  mov     rbp, [rsp+28h+arg_8]
0x18001e707  mov     eax, ebx
0x18001e709  mov     rbx, [rsp+28h+arg_0]
0x18001e70e  add     rsp, 20h
0x18001e712  pop     rdi
0x18001e713  retn
```
