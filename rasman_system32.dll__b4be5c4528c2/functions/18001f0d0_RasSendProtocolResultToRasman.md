# RasSendProtocolResultToRasman

- ea: `0x18001f0d0`
- end: `0x18001f1a5`
- name: `RasSendProtocolResultToRasman`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x18001f0d0`
- `0x180021b14`
- `0x180021fd4`

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
0x18001f0d0  mov     [rsp+arg_0], rbx
0x18001f0d5  mov     [rsp+arg_8], rbp
0x18001f0da  push    rdi
0x18001f0db  sub     rsp, 20h
0x18001f0df  mov     rdi, rdx
0x18001f0e2  mov     rbx, rcx
0x18001f0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0ec  lea     rbp, WPP_GLOBAL_Control
0x18001f0f3  cmp     rcx, rbp
0x18001f0f6  jz      short loc_18001F11C
0x18001f0f8  test    byte ptr [rcx+1Ch], 40h
0x18001f0fc  jz      short loc_18001F11C
0x18001f0fe  cmp     byte ptr [rcx+19h], 6
0x18001f102  jb      short loc_18001F11C
0x18001f104  mov     rcx, [rcx+10h]
0x18001f108  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f10f  mov     edx, 1ABh
0x18001f114  mov     r9, rbx
0x18001f117  call    WPP_SF_q
0x18001f11c  mov     ecx, 52h ; 'R'
0x18001f121  mov     r8, rdi
0x18001f124  mov     rdx, rbx
0x18001f127  call    SubmitLocalRequest
0x18001f12c  mov     ebx, eax
0x18001f12e  test    eax, eax
0x18001f130  jz      short loc_18001F162
0x18001f132  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f139  cmp     rcx, rbp
0x18001f13c  jz      short loc_18001F192
0x18001f13e  test    byte ptr [rcx+1Ch], 40h
0x18001f142  jz      short loc_18001F169
0x18001f144  cmp     byte ptr [rcx+19h], 2
0x18001f148  jb      short loc_18001F169
0x18001f14a  mov     rcx, [rcx+10h]
0x18001f14e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f155  mov     edx, 1ACh
0x18001f15a  mov     r9d, eax
0x18001f15d  call    WPP_SF_d
0x18001f162  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f169  cmp     rcx, rbp
0x18001f16c  jz      short loc_18001F192
0x18001f16e  test    byte ptr [rcx+1Ch], 40h
0x18001f172  jz      short loc_18001F192
0x18001f174  cmp     byte ptr [rcx+19h], 6
0x18001f178  jb      short loc_18001F192
0x18001f17a  mov     rcx, [rcx+10h]
0x18001f17e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f185  mov     edx, 1ADh
0x18001f18a  mov     r9d, ebx
0x18001f18d  call    WPP_SF_d
0x18001f192  mov     rbp, [rsp+28h+arg_8]
0x18001f197  mov     eax, ebx
0x18001f199  mov     rbx, [rsp+28h+arg_0]
0x18001f19e  add     rsp, 20h
0x18001f1a2  pop     rdi
0x18001f1a3  retn
```
