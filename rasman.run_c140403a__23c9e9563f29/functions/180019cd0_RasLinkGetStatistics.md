# RasLinkGetStatistics

- ea: `0x180019cd0`
- end: `0x180019da2`
- name: `RasLinkGetStatistics`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002f80`
- `0x180019cd0`
- `0x180021000`
- `0x1800217a0`

## pseudocode

```c
__int64 __fastcall RasLinkGetStatistics(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 562, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a2);
  }
  v6 = SubmitLocalRequest(0x62u, a1, a2, a3);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 563, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 564, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180019cd0  push    rbx
0x180019cd2  push    rsi
0x180019cd3  push    rdi
0x180019cd4  push    r14
0x180019cd6  sub     rsp, 38h
0x180019cda  mov     rsi, r8
0x180019cdd  mov     ebx, edx
0x180019cdf  mov     rdi, rcx
0x180019ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ce9  lea     r14, WPP_GLOBAL_Control
0x180019cf0  cmp     rcx, r14
0x180019cf3  jz      short loc_180019D1D
0x180019cf5  test    byte ptr [rcx+1Ch], 40h
0x180019cf9  jz      short loc_180019D1D
0x180019cfb  cmp     byte ptr [rcx+19h], 6
0x180019cff  jb      short loc_180019D1D
0x180019d01  mov     rcx, [rcx+10h]
0x180019d05  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019d0c  mov     edx, 232h
0x180019d11  mov     [rsp+58h+var_38], ebx
0x180019d15  mov     r9, rdi
0x180019d18  call    WPP_SF_qd
0x180019d1d  mov     ecx, 62h ; 'b'
0x180019d22  mov     r9, rsi
0x180019d25  mov     r8d, ebx
0x180019d28  mov     rdx, rdi
0x180019d2b  call    SubmitLocalRequest
0x180019d30  mov     ebx, eax
0x180019d32  test    eax, eax
0x180019d34  jz      short loc_180019D66
0x180019d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d3d  cmp     rcx, r14
0x180019d40  jz      short loc_180019D96
0x180019d42  test    byte ptr [rcx+1Ch], 40h
0x180019d46  jz      short loc_180019D6D
0x180019d48  cmp     byte ptr [rcx+19h], 2
0x180019d4c  jb      short loc_180019D6D
0x180019d4e  mov     rcx, [rcx+10h]
0x180019d52  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019d59  mov     edx, 233h
0x180019d5e  mov     r9d, eax
0x180019d61  call    WPP_SF_d
0x180019d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d6d  cmp     rcx, r14
0x180019d70  jz      short loc_180019D96
0x180019d72  test    byte ptr [rcx+1Ch], 40h
0x180019d76  jz      short loc_180019D96
0x180019d78  cmp     byte ptr [rcx+19h], 6
0x180019d7c  jb      short loc_180019D96
0x180019d7e  mov     rcx, [rcx+10h]
0x180019d82  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019d89  mov     edx, 234h
0x180019d8e  mov     r9d, ebx
0x180019d91  call    WPP_SF_d
0x180019d96  mov     eax, ebx
0x180019d98  add     rsp, 38h
0x180019d9c  pop     r14
0x180019d9e  pop     rdi
0x180019d9f  pop     rsi
0x180019da0  pop     rbx
0x180019da1  retn
```
