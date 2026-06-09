# RasSetCachedCredentials

- ea: `0x18001ea40`
- end: `0x18001eb0c`
- name: `RasSetCachedCredentials`
- size: `204`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002f80`
- `0x18001ea40`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasSetCachedCredentials(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v6 = SubmitLocalRequest(0x2Du, a1, a2, a3);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
LABEL_10:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 280, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001ea40  push    rbx
0x18001ea42  push    rsi
0x18001ea43  push    rdi
0x18001ea44  push    r14
0x18001ea46  sub     rsp, 28h
0x18001ea4a  mov     rbx, r8
0x18001ea4d  mov     rdi, rdx
0x18001ea50  mov     rsi, rcx
0x18001ea53  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea5a  lea     r14, WPP_GLOBAL_Control
0x18001ea61  cmp     rcx, r14
0x18001ea64  jz      short loc_18001EA87
0x18001ea66  test    byte ptr [rcx+1Ch], 40h
0x18001ea6a  jz      short loc_18001EA87
0x18001ea6c  cmp     byte ptr [rcx+19h], 6
0x18001ea70  jb      short loc_18001EA87
0x18001ea72  mov     rcx, [rcx+10h]
0x18001ea76  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ea7d  mov     edx, 116h
0x18001ea82  call    WPP_SF_
0x18001ea87  mov     ecx, 2Dh ; '-'
0x18001ea8c  mov     r9, rbx
0x18001ea8f  mov     r8, rdi
0x18001ea92  mov     rdx, rsi
0x18001ea95  call    SubmitLocalRequest
0x18001ea9a  mov     ebx, eax
0x18001ea9c  test    eax, eax
0x18001ea9e  jz      short loc_18001EAD0
0x18001eaa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaa7  cmp     rcx, r14
0x18001eaaa  jz      short loc_18001EB00
0x18001eaac  test    byte ptr [rcx+1Ch], 40h
0x18001eab0  jz      short loc_18001EAD7
0x18001eab2  cmp     byte ptr [rcx+19h], 2
0x18001eab6  jb      short loc_18001EAD7
0x18001eab8  mov     rcx, [rcx+10h]
0x18001eabc  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001eac3  mov     edx, 117h
0x18001eac8  mov     r9d, eax
0x18001eacb  call    WPP_SF_d
0x18001ead0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ead7  cmp     rcx, r14
0x18001eada  jz      short loc_18001EB00
0x18001eadc  test    byte ptr [rcx+1Ch], 40h
0x18001eae0  jz      short loc_18001EB00
0x18001eae2  cmp     byte ptr [rcx+19h], 6
0x18001eae6  jb      short loc_18001EB00
0x18001eae8  mov     rcx, [rcx+10h]
0x18001eaec  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001eaf3  mov     edx, 118h
0x18001eaf8  mov     r9d, ebx
0x18001eafb  call    WPP_SF_d
0x18001eb00  mov     eax, ebx
0x18001eb02  add     rsp, 28h
0x18001eb06  pop     r14
0x18001eb08  pop     rdi
0x18001eb09  pop     rsi
0x18001eb0a  pop     rbx
0x18001eb0b  retn
```
