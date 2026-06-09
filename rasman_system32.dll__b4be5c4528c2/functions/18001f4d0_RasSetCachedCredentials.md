# RasSetCachedCredentials

- ea: `0x18001f4d0`
- end: `0x18001f59d`
- name: `RasSetCachedCredentials`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800030d0`
- `0x18001f4d0`
- `0x180021ae4`
- `0x180021b14`

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
0x18001f4d0  push    rbx
0x18001f4d2  push    rsi
0x18001f4d3  push    rdi
0x18001f4d4  push    r14
0x18001f4d6  sub     rsp, 28h
0x18001f4da  mov     rbx, r8
0x18001f4dd  mov     rdi, rdx
0x18001f4e0  mov     rsi, rcx
0x18001f4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4ea  lea     r14, WPP_GLOBAL_Control
0x18001f4f1  cmp     rcx, r14
0x18001f4f4  jz      short loc_18001F517
0x18001f4f6  test    byte ptr [rcx+1Ch], 40h
0x18001f4fa  jz      short loc_18001F517
0x18001f4fc  cmp     byte ptr [rcx+19h], 6
0x18001f500  jb      short loc_18001F517
0x18001f502  mov     rcx, [rcx+10h]
0x18001f506  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f50d  mov     edx, 116h
0x18001f512  call    WPP_SF_
0x18001f517  mov     ecx, 2Dh ; '-'
0x18001f51c  mov     r9, rbx
0x18001f51f  mov     r8, rdi
0x18001f522  mov     rdx, rsi
0x18001f525  call    SubmitLocalRequest
0x18001f52a  mov     ebx, eax
0x18001f52c  test    eax, eax
0x18001f52e  jz      short loc_18001F560
0x18001f530  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f537  cmp     rcx, r14
0x18001f53a  jz      short loc_18001F590
0x18001f53c  test    byte ptr [rcx+1Ch], 40h
0x18001f540  jz      short loc_18001F567
0x18001f542  cmp     byte ptr [rcx+19h], 2
0x18001f546  jb      short loc_18001F567
0x18001f548  mov     rcx, [rcx+10h]
0x18001f54c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f553  mov     edx, 117h
0x18001f558  mov     r9d, eax
0x18001f55b  call    WPP_SF_d
0x18001f560  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f567  cmp     rcx, r14
0x18001f56a  jz      short loc_18001F590
0x18001f56c  test    byte ptr [rcx+1Ch], 40h
0x18001f570  jz      short loc_18001F590
0x18001f572  cmp     byte ptr [rcx+19h], 6
0x18001f576  jb      short loc_18001F590
0x18001f578  mov     rcx, [rcx+10h]
0x18001f57c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f583  mov     edx, 118h
0x18001f588  mov     r9d, ebx
0x18001f58b  call    WPP_SF_d
0x18001f590  mov     eax, ebx
0x18001f592  add     rsp, 28h
0x18001f596  pop     r14
0x18001f598  pop     rdi
0x18001f599  pop     rsi
0x18001f59a  pop     rbx
0x18001f59b  retn
```
