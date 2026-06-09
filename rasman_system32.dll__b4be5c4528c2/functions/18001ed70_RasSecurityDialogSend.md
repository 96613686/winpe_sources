# RasSecurityDialogSend

- ea: `0x18001ed70`
- end: `0x18001ef0f`
- name: `RasSecurityDialogSend`
- size: `415`
- prototype: `DWORD __stdcall(HPORT hPort, PBYTE pBuffer, WORD BufferLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012050`
- `0x18001c9f0`
- `0x18001ed70`
- `0x180021b14`
- `0x180021fd4`
- `0x18002739e`
- `0x1800273d0`

## pseudocode

```c
DWORD __stdcall RasSecurityDialogSend(HPORT hPort, PBYTE pBuffer, WORD BufferLength)
{
  unsigned int v3; // esi
  unsigned int Info; // eax
  PVOID *v7; // rcx
  DWORD v8; // ebx
  __int64 v9; // rdx
  DWORD v10; // eax
  _BYTE v12[4]; // [rsp+20h] [rbp-3D8h] BYREF
  int v13; // [rsp+24h] [rbp-3D4h]

  v3 = BufferLength;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, hPort);
  }
  memset_0(v12, 0, 0x398u);
  Info = RasGetInfo(0, hPort, v12);
  if ( !Info )
    goto LABEL_10;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, Info);
LABEL_10:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != 5 )
  {
    v8 = 619;
    if ( v7 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      {
        WPP_SF_d(v7[2], 330, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 619);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      {
        v9 = 331;
LABEL_30:
        WPP_SF_d(v7[2], v9, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
        return v8;
      }
    }
    return v8;
  }
  v10 = RasPortSend(hPort, pBuffer, v3);
  v8 = v10;
  if ( v10 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_26;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 332, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
  {
    v9 = 333;
    goto LABEL_30;
  }
  return v8;
}

```

## disassembly

```asm
0x18001ed70  push    rbx
0x18001ed72  push    rsi
0x18001ed73  push    rdi
0x18001ed74  push    r14
0x18001ed76  push    r15
0x18001ed78  sub     rsp, 3D0h
0x18001ed7f  mov     rax, cs:__security_cookie
0x18001ed86  xor     rax, rsp
0x18001ed89  mov     [rsp+3F8h+var_38], rax
0x18001ed91  movzx   esi, r8w
0x18001ed95  mov     rdi, rdx
0x18001ed98  mov     rbx, rcx
0x18001ed9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eda2  lea     r14, WPP_GLOBAL_Control
0x18001eda9  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001edb0  cmp     rcx, r14
0x18001edb3  jz      short loc_18001EDD5
0x18001edb5  test    byte ptr [rcx+1Ch], 40h
0x18001edb9  jz      short loc_18001EDD5
0x18001edbb  cmp     byte ptr [rcx+19h], 6
0x18001edbf  jb      short loc_18001EDD5
0x18001edc1  mov     rcx, [rcx+10h]
0x18001edc5  mov     edx, 148h
0x18001edca  mov     r9, rbx
0x18001edcd  mov     r8, r15
0x18001edd0  call    WPP_SF_q
0x18001edd5  xor     edx, edx; Val
0x18001edd7  lea     rcx, [rsp+3F8h+var_3D8]; void *
0x18001eddc  mov     r8d, 398h; Size
0x18001ede2  call    memset_0
0x18001ede7  lea     r8, [rsp+3F8h+var_3D8]
0x18001edec  mov     rdx, rbx
0x18001edef  xor     ecx, ecx
0x18001edf1  call    RasGetInfo
0x18001edf6  test    eax, eax
0x18001edf8  jz      short loc_18001EE26
0x18001edfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee01  cmp     rcx, r14
0x18001ee04  jz      short loc_18001EE2D
0x18001ee06  test    byte ptr [rcx+1Ch], 40h
0x18001ee0a  jz      short loc_18001EE2D
0x18001ee0c  cmp     byte ptr [rcx+19h], 2
0x18001ee10  jb      short loc_18001EE2D
0x18001ee12  mov     rcx, [rcx+10h]
0x18001ee16  mov     edx, 149h
0x18001ee1b  mov     r9d, eax
0x18001ee1e  mov     r8, r15
0x18001ee21  call    WPP_SF_d
0x18001ee26  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee2d  cmp     [rsp+3F8h+var_3D4], 5
0x18001ee32  jz      short loc_18001EE81
0x18001ee34  mov     ebx, 26Bh
0x18001ee39  cmp     rcx, r14
0x18001ee3c  jz      loc_18001EEED
0x18001ee42  test    byte ptr [rcx+1Ch], 40h
0x18001ee46  jz      short loc_18001EE69
0x18001ee48  cmp     byte ptr [rcx+19h], 2
0x18001ee4c  jb      short loc_18001EE69
0x18001ee4e  mov     rcx, [rcx+10h]
0x18001ee52  mov     edx, 14Ah
0x18001ee57  mov     r9d, ebx
0x18001ee5a  mov     r8, r15
0x18001ee5d  call    WPP_SF_d
0x18001ee62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee69  cmp     rcx, r14
0x18001ee6c  jz      short loc_18001EEED
0x18001ee6e  test    byte ptr [rcx+1Ch], 40h
0x18001ee72  jz      short loc_18001EEED
0x18001ee74  cmp     byte ptr [rcx+19h], 6
0x18001ee78  jb      short loc_18001EEED
0x18001ee7a  mov     edx, 14Bh
0x18001ee7f  jmp     short loc_18001EEDE
0x18001ee81  mov     r8d, esi
0x18001ee84  mov     rdx, rdi
0x18001ee87  mov     rcx, rbx
0x18001ee8a  call    RasPortSend
0x18001ee8f  mov     ebx, eax
0x18001ee91  test    eax, eax
0x18001ee93  jz      short loc_18001EEC1
0x18001ee95  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee9c  cmp     rcx, r14
0x18001ee9f  jz      short loc_18001EEED
0x18001eea1  test    byte ptr [rcx+1Ch], 40h
0x18001eea5  jz      short loc_18001EEC8
0x18001eea7  cmp     byte ptr [rcx+19h], 2
0x18001eeab  jb      short loc_18001EEC8
0x18001eead  mov     rcx, [rcx+10h]
0x18001eeb1  mov     edx, 14Ch
0x18001eeb6  mov     r9d, eax
0x18001eeb9  mov     r8, r15
0x18001eebc  call    WPP_SF_d
0x18001eec1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eec8  cmp     rcx, r14
0x18001eecb  jz      short loc_18001EEED
0x18001eecd  test    byte ptr [rcx+1Ch], 40h
0x18001eed1  jz      short loc_18001EEED
0x18001eed3  cmp     byte ptr [rcx+19h], 6
0x18001eed7  jb      short loc_18001EEED
0x18001eed9  mov     edx, 14Dh
0x18001eede  mov     rcx, [rcx+10h]
0x18001eee2  mov     r9d, ebx
0x18001eee5  mov     r8, r15
0x18001eee8  call    WPP_SF_d
0x18001eeed  mov     eax, ebx
0x18001eeef  mov     rcx, [rsp+3F8h+var_38]
0x18001eef7  xor     rcx, rsp; StackCookie
0x18001eefa  call    __security_check_cookie
0x18001eeff  add     rsp, 3D0h
0x18001ef06  pop     r15
0x18001ef08  pop     r14
0x18001ef0a  pop     rdi
0x18001ef0b  pop     rsi
0x18001ef0c  pop     rbx
0x18001ef0d  retn
```
