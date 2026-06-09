# RasSecurityDialogReceive

- ea: `0x18001e0b0`
- end: `0x18001e2d9`
- name: `RasSecurityDialogReceive`
- size: `553`
- prototype: `DWORD __stdcall(HPORT hPort, PBYTE pBuffer, PWORD pBufferLength, DWORD Timeout, HANDLE hEvent)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180011860`
- `0x18001ba70`
- `0x18001e0b0`
- `0x180021000`
- `0x180021990`
- `0x1800263ce`
- `0x180026400`

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
  Info = RasGetInfo(0, (__int64)hPort, (__int64)v16);
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
0x18001e0b0  push    rbx
0x18001e0b2  push    rbp
0x18001e0b3  push    rsi
0x18001e0b4  push    rdi
0x18001e0b5  push    r13
0x18001e0b7  push    r14
0x18001e0b9  push    r15
0x18001e0bb  sub     rsp, 3F0h
0x18001e0c2  mov     rax, cs:__security_cookie
0x18001e0c9  xor     rax, rsp
0x18001e0cc  mov     [rsp+428h+var_48], rax
0x18001e0d4  mov     r14, [rsp+428h+hEvent]
0x18001e0dc  mov     ebp, r9d
0x18001e0df  mov     rdi, r8
0x18001e0e2  mov     r15, rdx
0x18001e0e5  mov     rsi, rcx
0x18001e0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0ef  lea     r13, WPP_GLOBAL_Control
0x18001e0f6  cmp     rcx, r13
0x18001e0f9  jz      short loc_18001E122
0x18001e0fb  test    byte ptr [rcx+1Ch], 40h
0x18001e0ff  jz      short loc_18001E122
0x18001e101  cmp     byte ptr [rcx+19h], 6
0x18001e105  jb      short loc_18001E122
0x18001e107  mov     rcx, [rcx+10h]
0x18001e10b  mov     edx, 14Eh
0x18001e110  mov     [rsp+428h+var_400], r14
0x18001e115  mov     dword ptr [rsp+428h+var_408], r9d
0x18001e11a  mov     r9, rsi
0x18001e11d  call    WPP_SF_qdq
0x18001e122  xor     edx, edx; Val
0x18001e124  lea     rcx, [rsp+428h+var_3E8]; void *
0x18001e129  mov     r8d, 398h; Size
0x18001e12f  call    memset_0
0x18001e134  lea     r8, [rsp+428h+var_3E8]
0x18001e139  mov     rdx, rsi
0x18001e13c  xor     ecx, ecx
0x18001e13e  call    RasGetInfo
0x18001e143  mov     ebx, eax
0x18001e145  test    eax, eax
0x18001e147  jz      short loc_18001E1AB
0x18001e149  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e150  cmp     rcx, r13
0x18001e153  jz      loc_18001E2B5
0x18001e159  test    byte ptr [rcx+1Ch], 40h
0x18001e15d  jz      short loc_18001E184
0x18001e15f  cmp     byte ptr [rcx+19h], 2
0x18001e163  jb      short loc_18001E184
0x18001e165  mov     rcx, [rcx+10h]
0x18001e169  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e170  mov     edx, 14Fh
0x18001e175  mov     r9d, eax
0x18001e178  call    WPP_SF_d
0x18001e17d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e184  cmp     rcx, r13
0x18001e187  jz      loc_18001E2B5
0x18001e18d  test    byte ptr [rcx+1Ch], 40h
0x18001e191  jz      loc_18001E2B5
0x18001e197  cmp     byte ptr [rcx+19h], 6
0x18001e19b  jb      loc_18001E2B5
0x18001e1a1  mov     edx, 150h
0x18001e1a6  jmp     loc_18001E2A2
0x18001e1ab  cmp     [rsp+428h+var_3E4], 5
0x18001e1b0  jz      short loc_18001E219
0x18001e1b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1b9  mov     ebx, 26Bh
0x18001e1be  cmp     rcx, r13
0x18001e1c1  jz      loc_18001E2B5
0x18001e1c7  test    byte ptr [rcx+1Ch], 40h
0x18001e1cb  jz      short loc_18001E1F2
0x18001e1cd  cmp     byte ptr [rcx+19h], 2
0x18001e1d1  jb      short loc_18001E1F2
0x18001e1d3  mov     rcx, [rcx+10h]
0x18001e1d7  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e1de  mov     edx, 151h
0x18001e1e3  mov     r9d, ebx
0x18001e1e6  call    WPP_SF_d
0x18001e1eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1f2  cmp     rcx, r13
0x18001e1f5  jz      loc_18001E2B5
0x18001e1fb  test    byte ptr [rcx+1Ch], 40h
0x18001e1ff  jz      loc_18001E2B5
0x18001e205  cmp     byte ptr [rcx+19h], 6
0x18001e209  jb      loc_18001E2B5
0x18001e20f  mov     edx, 152h
0x18001e214  jmp     loc_18001E2A2
0x18001e219  test    rdi, rdi
0x18001e21c  jnz     short loc_18001E228
0x18001e21e  mov     eax, 80070057h
0x18001e223  jmp     loc_18001E2B7
0x18001e228  movzx   eax, word ptr [rdi]
0x18001e22b  lea     r8, [rsp+428h+var_3F8]
0x18001e230  mov     r9d, ebp
0x18001e233  mov     [rsp+428h+var_3F8], eax
0x18001e237  mov     rdx, r15
0x18001e23a  mov     [rsp+428h+var_408], r14
0x18001e23f  mov     rcx, rsi
0x18001e242  call    RasPortReceive
0x18001e247  mov     ebx, eax
0x18001e249  test    eax, eax
0x18001e24b  jz      short loc_18001E27D
0x18001e24d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e254  cmp     rcx, r13
0x18001e257  jz      short loc_18001E27D
0x18001e259  test    byte ptr [rcx+1Ch], 40h
0x18001e25d  jz      short loc_18001E27D
0x18001e25f  cmp     byte ptr [rcx+19h], 2
0x18001e263  jb      short loc_18001E27D
0x18001e265  mov     rcx, [rcx+10h]
0x18001e269  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e270  mov     edx, 153h
0x18001e275  mov     r9d, eax
0x18001e278  call    WPP_SF_d
0x18001e27d  movzx   eax, word ptr [rsp+428h+var_3F8]
0x18001e282  mov     [rdi], ax
0x18001e285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e28c  cmp     rcx, r13
0x18001e28f  jz      short loc_18001E2B5
0x18001e291  test    byte ptr [rcx+1Ch], 40h
0x18001e295  jz      short loc_18001E2B5
0x18001e297  cmp     byte ptr [rcx+19h], 6
0x18001e29b  jb      short loc_18001E2B5
0x18001e29d  mov     edx, 154h
0x18001e2a2  mov     rcx, [rcx+10h]
0x18001e2a6  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e2ad  mov     r9d, ebx
0x18001e2b0  call    WPP_SF_d
0x18001e2b5  mov     eax, ebx
0x18001e2b7  mov     rcx, [rsp+428h+var_48]
0x18001e2bf  xor     rcx, rsp; StackCookie
0x18001e2c2  call    __security_check_cookie
0x18001e2c7  add     rsp, 3F0h
0x18001e2ce  pop     r15
0x18001e2d0  pop     r14
0x18001e2d2  pop     r13
0x18001e2d4  pop     rdi
0x18001e2d5  pop     rsi
0x18001e2d6  pop     rbp
0x18001e2d7  pop     rbx
0x18001e2d8  retn
```
