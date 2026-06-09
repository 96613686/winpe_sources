# RasSecurityDialogSend

- ea: `0x18001e2e0`
- end: `0x18001e47e`
- name: `RasSecurityDialogSend`
- size: `414`
- prototype: `DWORD __stdcall(HPORT hPort, PBYTE pBuffer, WORD BufferLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180011860`
- `0x18001bfb0`
- `0x18001e2e0`
- `0x180021000`
- `0x180021488`
- `0x1800263ce`
- `0x180026400`

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
  Info = RasGetInfo(0, (__int64)hPort, (__int64)v12);
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
0x18001e2e0  push    rbx
0x18001e2e2  push    rsi
0x18001e2e3  push    rdi
0x18001e2e4  push    r14
0x18001e2e6  push    r15
0x18001e2e8  sub     rsp, 3D0h
0x18001e2ef  mov     rax, cs:__security_cookie
0x18001e2f6  xor     rax, rsp
0x18001e2f9  mov     [rsp+3F8h+var_38], rax
0x18001e301  movzx   esi, r8w
0x18001e305  mov     rdi, rdx
0x18001e308  mov     rbx, rcx
0x18001e30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e312  lea     r14, WPP_GLOBAL_Control
0x18001e319  lea     r15, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e320  cmp     rcx, r14
0x18001e323  jz      short loc_18001E345
0x18001e325  test    byte ptr [rcx+1Ch], 40h
0x18001e329  jz      short loc_18001E345
0x18001e32b  cmp     byte ptr [rcx+19h], 6
0x18001e32f  jb      short loc_18001E345
0x18001e331  mov     rcx, [rcx+10h]
0x18001e335  mov     edx, 148h
0x18001e33a  mov     r9, rbx
0x18001e33d  mov     r8, r15
0x18001e340  call    WPP_SF_q
0x18001e345  xor     edx, edx; Val
0x18001e347  lea     rcx, [rsp+3F8h+var_3D8]; void *
0x18001e34c  mov     r8d, 398h; Size
0x18001e352  call    memset_0
0x18001e357  lea     r8, [rsp+3F8h+var_3D8]
0x18001e35c  mov     rdx, rbx
0x18001e35f  xor     ecx, ecx
0x18001e361  call    RasGetInfo
0x18001e366  test    eax, eax
0x18001e368  jz      short loc_18001E396
0x18001e36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e371  cmp     rcx, r14
0x18001e374  jz      short loc_18001E39D
0x18001e376  test    byte ptr [rcx+1Ch], 40h
0x18001e37a  jz      short loc_18001E39D
0x18001e37c  cmp     byte ptr [rcx+19h], 2
0x18001e380  jb      short loc_18001E39D
0x18001e382  mov     rcx, [rcx+10h]
0x18001e386  mov     edx, 149h
0x18001e38b  mov     r9d, eax
0x18001e38e  mov     r8, r15
0x18001e391  call    WPP_SF_d
0x18001e396  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e39d  cmp     [rsp+3F8h+var_3D4], 5
0x18001e3a2  jz      short loc_18001E3F1
0x18001e3a4  mov     ebx, 26Bh
0x18001e3a9  cmp     rcx, r14
0x18001e3ac  jz      loc_18001E45D
0x18001e3b2  test    byte ptr [rcx+1Ch], 40h
0x18001e3b6  jz      short loc_18001E3D9
0x18001e3b8  cmp     byte ptr [rcx+19h], 2
0x18001e3bc  jb      short loc_18001E3D9
0x18001e3be  mov     rcx, [rcx+10h]
0x18001e3c2  mov     edx, 14Ah
0x18001e3c7  mov     r9d, ebx
0x18001e3ca  mov     r8, r15
0x18001e3cd  call    WPP_SF_d
0x18001e3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3d9  cmp     rcx, r14
0x18001e3dc  jz      short loc_18001E45D
0x18001e3de  test    byte ptr [rcx+1Ch], 40h
0x18001e3e2  jz      short loc_18001E45D
0x18001e3e4  cmp     byte ptr [rcx+19h], 6
0x18001e3e8  jb      short loc_18001E45D
0x18001e3ea  mov     edx, 14Bh
0x18001e3ef  jmp     short loc_18001E44E
0x18001e3f1  mov     r8d, esi
0x18001e3f4  mov     rdx, rdi
0x18001e3f7  mov     rcx, rbx
0x18001e3fa  call    RasPortSend
0x18001e3ff  mov     ebx, eax
0x18001e401  test    eax, eax
0x18001e403  jz      short loc_18001E431
0x18001e405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e40c  cmp     rcx, r14
0x18001e40f  jz      short loc_18001E45D
0x18001e411  test    byte ptr [rcx+1Ch], 40h
0x18001e415  jz      short loc_18001E438
0x18001e417  cmp     byte ptr [rcx+19h], 2
0x18001e41b  jb      short loc_18001E438
0x18001e41d  mov     rcx, [rcx+10h]
0x18001e421  mov     edx, 14Ch
0x18001e426  mov     r9d, eax
0x18001e429  mov     r8, r15
0x18001e42c  call    WPP_SF_d
0x18001e431  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e438  cmp     rcx, r14
0x18001e43b  jz      short loc_18001E45D
0x18001e43d  test    byte ptr [rcx+1Ch], 40h
0x18001e441  jz      short loc_18001E45D
0x18001e443  cmp     byte ptr [rcx+19h], 6
0x18001e447  jb      short loc_18001E45D
0x18001e449  mov     edx, 14Dh
0x18001e44e  mov     rcx, [rcx+10h]
0x18001e452  mov     r9d, ebx
0x18001e455  mov     r8, r15
0x18001e458  call    WPP_SF_d
0x18001e45d  mov     eax, ebx
0x18001e45f  mov     rcx, [rsp+3F8h+var_38]
0x18001e467  xor     rcx, rsp; StackCookie
0x18001e46a  call    __security_check_cookie
0x18001e46f  add     rsp, 3D0h
0x18001e476  pop     r15
0x18001e478  pop     r14
0x18001e47a  pop     rdi
0x18001e47b  pop     rsi
0x18001e47c  pop     rbx
0x18001e47d  retn
```
