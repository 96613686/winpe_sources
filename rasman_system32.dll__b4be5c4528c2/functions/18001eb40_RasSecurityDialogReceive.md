# RasSecurityDialogReceive

- ea: `0x18001eb40`
- end: `0x18001ed6a`
- name: `RasSecurityDialogReceive`
- size: `554`
- prototype: `DWORD __stdcall(HPORT hPort, PBYTE pBuffer, PWORD pBufferLength, DWORD Timeout, HANDLE hEvent)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012050`
- `0x18001c4a0`
- `0x18001eb40`
- `0x180021b14`
- `0x180022534`
- `0x18002739e`
- `0x1800273d0`

## pseudocode

```c
DWORD __stdcall RasSecurityDialogReceive(HPORT hPort, PBYTE pBuffer, PWORD pBufferLength, DWORD Timeout, HANDLE hEvent)
{
  DWORD Info; // eax
  DWORD v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  DWORD v14; // eax
  _DWORD v15[4]; // [rsp+30h] [rbp-3F8h] BYREF
  _BYTE v16[4]; // [rsp+40h] [rbp-3E8h] BYREF
  int v17; // [rsp+44h] [rbp-3E4h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qdq(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, pBufferLength, hPort, Timeout, hEvent);
  }
  memset_0(v16, 0, 0x398u);
  Info = RasGetInfo(0, hPort, v16);
  v10 = Info;
  if ( Info )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 335, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, Info);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 0x40) == 0 || *((_BYTE *)v11 + 25) < 6u )
      return v10;
    v12 = 336;
    goto LABEL_34;
  }
  if ( v17 != 5 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 619;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v10;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 619);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 0x40) == 0 || *((_BYTE *)v11 + 25) < 6u )
      return v10;
    v12 = 338;
    goto LABEL_34;
  }
  if ( !pBufferLength )
    return -2147024809;
  v15[0] = *pBufferLength;
  v14 = RasPortReceive((__int64)hPort, (__int64)pBuffer, (__int64)v15, Timeout, (__int64)hEvent);
  v10 = v14;
  if ( v14
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
  }
  *pBufferLength = v15[0];
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = 340;
LABEL_34:
    WPP_SF_d(v11[2], v12, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18001eb40  push    rbx
0x18001eb42  push    rbp
0x18001eb43  push    rsi
0x18001eb44  push    rdi
0x18001eb45  push    r13
0x18001eb47  push    r14
0x18001eb49  push    r15
0x18001eb4b  sub     rsp, 3F0h
0x18001eb52  mov     rax, cs:__security_cookie
0x18001eb59  xor     rax, rsp
0x18001eb5c  mov     [rsp+428h+var_48], rax
0x18001eb64  mov     r14, [rsp+428h+hEvent]
0x18001eb6c  mov     ebp, r9d
0x18001eb6f  mov     rdi, r8
0x18001eb72  mov     r15, rdx
0x18001eb75  mov     rsi, rcx
0x18001eb78  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb7f  lea     r13, WPP_GLOBAL_Control
0x18001eb86  cmp     rcx, r13
0x18001eb89  jz      short loc_18001EBB2
0x18001eb8b  test    byte ptr [rcx+1Ch], 40h
0x18001eb8f  jz      short loc_18001EBB2
0x18001eb91  cmp     byte ptr [rcx+19h], 6
0x18001eb95  jb      short loc_18001EBB2
0x18001eb97  mov     rcx, [rcx+10h]
0x18001eb9b  mov     edx, 14Eh
0x18001eba0  mov     [rsp+428h+var_400], r14
0x18001eba5  mov     dword ptr [rsp+428h+var_408], r9d
0x18001ebaa  mov     r9, rsi
0x18001ebad  call    WPP_SF_qdq
0x18001ebb2  xor     edx, edx; Val
0x18001ebb4  lea     rcx, [rsp+428h+var_3E8]; void *
0x18001ebb9  mov     r8d, 398h; Size
0x18001ebbf  call    memset_0
0x18001ebc4  lea     r8, [rsp+428h+var_3E8]
0x18001ebc9  mov     rdx, rsi
0x18001ebcc  xor     ecx, ecx
0x18001ebce  call    RasGetInfo
0x18001ebd3  mov     ebx, eax
0x18001ebd5  test    eax, eax
0x18001ebd7  jz      short loc_18001EC3B
0x18001ebd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebe0  cmp     rcx, r13
0x18001ebe3  jz      loc_18001ED45
0x18001ebe9  test    byte ptr [rcx+1Ch], 40h
0x18001ebed  jz      short loc_18001EC14
0x18001ebef  cmp     byte ptr [rcx+19h], 2
0x18001ebf3  jb      short loc_18001EC14
0x18001ebf5  mov     rcx, [rcx+10h]
0x18001ebf9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ec00  mov     edx, 14Fh
0x18001ec05  mov     r9d, eax
0x18001ec08  call    WPP_SF_d
0x18001ec0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec14  cmp     rcx, r13
0x18001ec17  jz      loc_18001ED45
0x18001ec1d  test    byte ptr [rcx+1Ch], 40h
0x18001ec21  jz      loc_18001ED45
0x18001ec27  cmp     byte ptr [rcx+19h], 6
0x18001ec2b  jb      loc_18001ED45
0x18001ec31  mov     edx, 150h
0x18001ec36  jmp     loc_18001ED32
0x18001ec3b  cmp     [rsp+428h+var_3E4], 5
0x18001ec40  jz      short loc_18001ECA9
0x18001ec42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec49  mov     ebx, 26Bh
0x18001ec4e  cmp     rcx, r13
0x18001ec51  jz      loc_18001ED45
0x18001ec57  test    byte ptr [rcx+1Ch], 40h
0x18001ec5b  jz      short loc_18001EC82
0x18001ec5d  cmp     byte ptr [rcx+19h], 2
0x18001ec61  jb      short loc_18001EC82
0x18001ec63  mov     rcx, [rcx+10h]
0x18001ec67  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ec6e  mov     edx, 151h
0x18001ec73  mov     r9d, ebx
0x18001ec76  call    WPP_SF_d
0x18001ec7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec82  cmp     rcx, r13
0x18001ec85  jz      loc_18001ED45
0x18001ec8b  test    byte ptr [rcx+1Ch], 40h
0x18001ec8f  jz      loc_18001ED45
0x18001ec95  cmp     byte ptr [rcx+19h], 6
0x18001ec99  jb      loc_18001ED45
0x18001ec9f  mov     edx, 152h
0x18001eca4  jmp     loc_18001ED32
0x18001eca9  test    rdi, rdi
0x18001ecac  jnz     short loc_18001ECB8
0x18001ecae  mov     eax, 80070057h
0x18001ecb3  jmp     loc_18001ED47
0x18001ecb8  movzx   eax, word ptr [rdi]
0x18001ecbb  lea     r8, [rsp+428h+var_3F8]
0x18001ecc0  mov     r9d, ebp
0x18001ecc3  mov     [rsp+428h+var_3F8], eax
0x18001ecc7  mov     rdx, r15
0x18001ecca  mov     [rsp+428h+var_408], r14
0x18001eccf  mov     rcx, rsi
0x18001ecd2  call    RasPortReceive
0x18001ecd7  mov     ebx, eax
0x18001ecd9  test    eax, eax
0x18001ecdb  jz      short loc_18001ED0D
0x18001ecdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ece4  cmp     rcx, r13
0x18001ece7  jz      short loc_18001ED0D
0x18001ece9  test    byte ptr [rcx+1Ch], 40h
0x18001eced  jz      short loc_18001ED0D
0x18001ecef  cmp     byte ptr [rcx+19h], 2
0x18001ecf3  jb      short loc_18001ED0D
0x18001ecf5  mov     rcx, [rcx+10h]
0x18001ecf9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ed00  mov     edx, 153h
0x18001ed05  mov     r9d, eax
0x18001ed08  call    WPP_SF_d
0x18001ed0d  movzx   eax, word ptr [rsp+428h+var_3F8]
0x18001ed12  mov     [rdi], ax
0x18001ed15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed1c  cmp     rcx, r13
0x18001ed1f  jz      short loc_18001ED45
0x18001ed21  test    byte ptr [rcx+1Ch], 40h
0x18001ed25  jz      short loc_18001ED45
0x18001ed27  cmp     byte ptr [rcx+19h], 6
0x18001ed2b  jb      short loc_18001ED45
0x18001ed2d  mov     edx, 154h
0x18001ed32  mov     rcx, [rcx+10h]
0x18001ed36  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ed3d  mov     r9d, ebx
0x18001ed40  call    WPP_SF_d
0x18001ed45  mov     eax, ebx
0x18001ed47  mov     rcx, [rsp+428h+var_48]
0x18001ed4f  xor     rcx, rsp; StackCookie
0x18001ed52  call    __security_check_cookie
0x18001ed57  add     rsp, 3F0h
0x18001ed5e  pop     r15
0x18001ed60  pop     r14
0x18001ed62  pop     r13
0x18001ed64  pop     rdi
0x18001ed65  pop     rsi
0x18001ed66  pop     rbp
0x18001ed67  pop     rbx
0x18001ed68  retn
```
