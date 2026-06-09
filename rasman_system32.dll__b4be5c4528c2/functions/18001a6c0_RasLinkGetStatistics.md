# RasLinkGetStatistics

- ea: `0x18001a6c0`
- end: `0x18001a793`
- name: `RasLinkGetStatistics`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800030d0`
- `0x18001a6c0`
- `0x180021b14`
- `0x180022320`

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
0x18001a6c0  push    rbx
0x18001a6c2  push    rsi
0x18001a6c3  push    rdi
0x18001a6c4  push    r14
0x18001a6c6  sub     rsp, 38h
0x18001a6ca  mov     rsi, r8
0x18001a6cd  mov     ebx, edx
0x18001a6cf  mov     rdi, rcx
0x18001a6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d9  lea     r14, WPP_GLOBAL_Control
0x18001a6e0  cmp     rcx, r14
0x18001a6e3  jz      short loc_18001A70D
0x18001a6e5  test    byte ptr [rcx+1Ch], 40h
0x18001a6e9  jz      short loc_18001A70D
0x18001a6eb  cmp     byte ptr [rcx+19h], 6
0x18001a6ef  jb      short loc_18001A70D
0x18001a6f1  mov     rcx, [rcx+10h]
0x18001a6f5  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a6fc  mov     edx, 232h
0x18001a701  mov     [rsp+58h+var_38], ebx
0x18001a705  mov     r9, rdi
0x18001a708  call    WPP_SF_qd
0x18001a70d  mov     ecx, 62h ; 'b'
0x18001a712  mov     r9, rsi
0x18001a715  mov     r8d, ebx
0x18001a718  mov     rdx, rdi
0x18001a71b  call    SubmitLocalRequest
0x18001a720  mov     ebx, eax
0x18001a722  test    eax, eax
0x18001a724  jz      short loc_18001A756
0x18001a726  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a72d  cmp     rcx, r14
0x18001a730  jz      short loc_18001A786
0x18001a732  test    byte ptr [rcx+1Ch], 40h
0x18001a736  jz      short loc_18001A75D
0x18001a738  cmp     byte ptr [rcx+19h], 2
0x18001a73c  jb      short loc_18001A75D
0x18001a73e  mov     rcx, [rcx+10h]
0x18001a742  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a749  mov     edx, 233h
0x18001a74e  mov     r9d, eax
0x18001a751  call    WPP_SF_d
0x18001a756  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a75d  cmp     rcx, r14
0x18001a760  jz      short loc_18001A786
0x18001a762  test    byte ptr [rcx+1Ch], 40h
0x18001a766  jz      short loc_18001A786
0x18001a768  cmp     byte ptr [rcx+19h], 6
0x18001a76c  jb      short loc_18001A786
0x18001a76e  mov     rcx, [rcx+10h]
0x18001a772  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a779  mov     edx, 234h
0x18001a77e  mov     r9d, ebx
0x18001a781  call    WPP_SF_d
0x18001a786  mov     eax, ebx
0x18001a788  add     rsp, 38h
0x18001a78c  pop     r14
0x18001a78e  pop     rdi
0x18001a78f  pop     rsi
0x18001a790  pop     rbx
0x18001a791  retn
```
