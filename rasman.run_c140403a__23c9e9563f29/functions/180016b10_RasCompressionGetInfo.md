# RasCompressionGetInfo

- ea: `0x180016b10`
- end: `0x180016c1b`
- name: `RasCompressionGetInfo`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x180016b10`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasCompressionGetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 268;
LABEL_20:
      WPP_SF_d(v6[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
      return v7;
    }
    return v7;
  }
  v9 = SubmitLocalRequest(0x13u, a1, a2, a3);
  v7 = v9;
  if ( v9 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 270;
    goto LABEL_20;
  }
  return v7;
}

```

## disassembly

```asm
0x180016b10  push    rbx
0x180016b12  push    rsi
0x180016b13  push    rdi
0x180016b14  push    r14
0x180016b16  sub     rsp, 28h
0x180016b1a  mov     rdi, r8
0x180016b1d  mov     rsi, rdx
0x180016b20  mov     rbx, rcx
0x180016b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b2a  lea     r14, WPP_GLOBAL_Control
0x180016b31  cmp     rcx, r14
0x180016b34  jz      short loc_180016B5A
0x180016b36  test    byte ptr [rcx+1Ch], 40h
0x180016b3a  jz      short loc_180016B5A
0x180016b3c  cmp     byte ptr [rcx+19h], 6
0x180016b40  jb      short loc_180016B5A
0x180016b42  mov     rcx, [rcx+10h]
0x180016b46  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016b4d  mov     edx, 10Bh
0x180016b52  mov     r9, rbx
0x180016b55  call    WPP_SF_q
0x180016b5a  mov     rcx, rbx
0x180016b5d  call    ValidatePortHandle
0x180016b62  test    eax, eax
0x180016b64  jnz     short loc_180016B96
0x180016b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b6d  mov     ebx, 259h
0x180016b72  cmp     rcx, r14
0x180016b75  jz      loc_180016C0F
0x180016b7b  test    byte ptr [rcx+1Ch], 40h
0x180016b7f  jz      loc_180016C0F
0x180016b85  cmp     byte ptr [rcx+19h], 2
0x180016b89  jb      loc_180016C0F
0x180016b8f  mov     edx, 10Ch
0x180016b94  jmp     short loc_180016BFC
0x180016b96  mov     ecx, 13h
0x180016b9b  mov     r9, rdi
0x180016b9e  mov     r8, rsi
0x180016ba1  mov     rdx, rbx
0x180016ba4  call    SubmitLocalRequest
0x180016ba9  mov     ebx, eax
0x180016bab  test    eax, eax
0x180016bad  jz      short loc_180016BDF
0x180016baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bb6  cmp     rcx, r14
0x180016bb9  jz      short loc_180016C0F
0x180016bbb  test    byte ptr [rcx+1Ch], 40h
0x180016bbf  jz      short loc_180016BE6
0x180016bc1  cmp     byte ptr [rcx+19h], 2
0x180016bc5  jb      short loc_180016BE6
0x180016bc7  mov     rcx, [rcx+10h]
0x180016bcb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016bd2  mov     edx, 10Dh
0x180016bd7  mov     r9d, eax
0x180016bda  call    WPP_SF_d
0x180016bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016be6  cmp     rcx, r14
0x180016be9  jz      short loc_180016C0F
0x180016beb  test    byte ptr [rcx+1Ch], 40h
0x180016bef  jz      short loc_180016C0F
0x180016bf1  cmp     byte ptr [rcx+19h], 6
0x180016bf5  jb      short loc_180016C0F
0x180016bf7  mov     edx, 10Eh
0x180016bfc  mov     rcx, [rcx+10h]
0x180016c00  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016c07  mov     r9d, ebx
0x180016c0a  call    WPP_SF_d
0x180016c0f  mov     eax, ebx
0x180016c11  add     rsp, 28h
0x180016c15  pop     r14
0x180016c17  pop     rdi
0x180016c18  pop     rsi
0x180016c19  pop     rbx
0x180016c1a  retn
```
