# RasGetProtocolInfo

- ea: `0x180019f90`
- end: `0x18001a0b3`
- name: `RasGetProtocolInfo`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x180019f90`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasGetProtocolInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax

  v4 = a1;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 625, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v4);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( v5 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      {
        WPP_SF_d(v5[2], 626, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 2147942487LL);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        v7 = 627;
LABEL_24:
        WPP_SF_d(v5[2], v7, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
        return v6;
      }
    }
    return v6;
  }
  v8 = SubmitLocalRequest(0x72u, a2, a3, v4);
  v6 = v8;
  if ( v8 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 628, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
  {
    v7 = 629;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x180019f90  mov     [rsp+arg_0], rbx
0x180019f95  mov     [rsp+arg_8], rbp
0x180019f9a  push    rsi
0x180019f9b  sub     rsp, 20h
0x180019f9f  mov     rbx, rdx
0x180019fa2  mov     r9, rcx
0x180019fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fac  lea     rsi, WPP_GLOBAL_Control
0x180019fb3  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019fba  cmp     rcx, rsi
0x180019fbd  jz      short loc_180019FE3
0x180019fbf  test    byte ptr [rcx+1Ch], 40h
0x180019fc3  jz      short loc_180019FE3
0x180019fc5  cmp     byte ptr [rcx+19h], 6
0x180019fc9  jb      short loc_180019FE3
0x180019fcb  mov     rcx, [rcx+10h]
0x180019fcf  mov     edx, 271h
0x180019fd4  mov     r8, rbp
0x180019fd7  call    WPP_SF_q
0x180019fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fe3  test    rbx, rbx
0x180019fe6  jnz     short loc_18001A035
0x180019fe8  mov     ebx, 80070057h
0x180019fed  cmp     rcx, rsi
0x180019ff0  jz      loc_18001A0A0
0x180019ff6  test    byte ptr [rcx+1Ch], 40h
0x180019ffa  jz      short loc_18001A01D
0x180019ffc  cmp     byte ptr [rcx+19h], 2
0x18001a000  jb      short loc_18001A01D
0x18001a002  mov     rcx, [rcx+10h]
0x18001a006  mov     edx, 272h
0x18001a00b  mov     r9d, ebx
0x18001a00e  mov     r8, rbp
0x18001a011  call    WPP_SF_d
0x18001a016  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a01d  cmp     rcx, rsi
0x18001a020  jz      short loc_18001A0A0
0x18001a022  test    byte ptr [rcx+1Ch], 40h
0x18001a026  jz      short loc_18001A0A0
0x18001a028  cmp     byte ptr [rcx+19h], 6
0x18001a02c  jb      short loc_18001A0A0
0x18001a02e  mov     edx, 273h
0x18001a033  jmp     short loc_18001A091
0x18001a035  mov     ecx, 72h ; 'r'
0x18001a03a  mov     rdx, rbx
0x18001a03d  call    SubmitLocalRequest
0x18001a042  mov     ebx, eax
0x18001a044  test    eax, eax
0x18001a046  jz      short loc_18001A074
0x18001a048  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a04f  cmp     rcx, rsi
0x18001a052  jz      short loc_18001A0A0
0x18001a054  test    byte ptr [rcx+1Ch], 40h
0x18001a058  jz      short loc_18001A07B
0x18001a05a  cmp     byte ptr [rcx+19h], 2
0x18001a05e  jb      short loc_18001A07B
0x18001a060  mov     rcx, [rcx+10h]
0x18001a064  mov     edx, 274h
0x18001a069  mov     r9d, eax
0x18001a06c  mov     r8, rbp
0x18001a06f  call    WPP_SF_d
0x18001a074  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a07b  cmp     rcx, rsi
0x18001a07e  jz      short loc_18001A0A0
0x18001a080  test    byte ptr [rcx+1Ch], 40h
0x18001a084  jz      short loc_18001A0A0
0x18001a086  cmp     byte ptr [rcx+19h], 6
0x18001a08a  jb      short loc_18001A0A0
0x18001a08c  mov     edx, 275h
0x18001a091  mov     rcx, [rcx+10h]
0x18001a095  mov     r9d, ebx
0x18001a098  mov     r8, rbp
0x18001a09b  call    WPP_SF_d
0x18001a0a0  mov     rbp, [rsp+28h+arg_8]
0x18001a0a5  mov     eax, ebx
0x18001a0a7  mov     rbx, [rsp+28h+arg_0]
0x18001a0ac  add     rsp, 20h
0x18001a0b0  pop     rsi
0x18001a0b1  retn
```
