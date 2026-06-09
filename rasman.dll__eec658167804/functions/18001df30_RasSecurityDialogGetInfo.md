# RasSecurityDialogGetInfo

- ea: `0x18001df30`
- end: `0x18001e09e`
- name: `RasSecurityDialogGetInfo`
- size: `366`
- prototype: `DWORD __stdcall(HPORT hPort, RAS_SECURITY_INFO *pBuffer)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180011860`
- `0x18001df30`
- `0x180021000`
- `0x180021488`
- `0x1800263ce`
- `0x180026400`

## pseudocode

```c
DWORD __stdcall RasSecurityDialogGetInfo(HPORT hPort, RAS_SECURITY_INFO *pBuffer)
{
  DWORD Info; // eax
  DWORD v5; // ebx
  PVOID *v6; // rcx
  CHAR v8; // al
  __int128 v9; // xmm1
  _BYTE v10[12]; // [rsp+20h] [rbp-3B8h] BYREF
  DWORD v11; // [rsp+2Ch] [rbp-3ACh]
  __int128 v12; // [rsp+44h] [rbp-394h]
  __int128 v13; // [rsp+54h] [rbp-384h]
  CHAR v14; // [rsp+64h] [rbp-374h]
  DWORD v15; // [rsp+174h] [rbp-264h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, hPort);
  }
  memset_0(v10, 0, 0x398u);
  Info = RasGetInfo(0, (__int64)hPort, (__int64)v10);
  v5 = Info;
  if ( Info )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 342, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, Info);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 343, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
    }
    return v5;
  }
  else
  {
    v8 = v14;
    v9 = v13;
    *(_OWORD *)pBuffer->DeviceName = v12;
    *(_OWORD *)&pBuffer->DeviceName[16] = v9;
    pBuffer->DeviceName[32] = v8;
    pBuffer->BytesReceived = v15;
    pBuffer->LastError = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 0);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001df30  mov     [rsp+arg_10], rbx
0x18001df35  mov     [rsp+arg_18], rdi
0x18001df3a  push    r15
0x18001df3c  sub     rsp, 3D0h
0x18001df43  mov     rax, cs:__security_cookie
0x18001df4a  xor     rax, rsp
0x18001df4d  mov     [rsp+3D8h+var_18], rax
0x18001df55  mov     rdi, rdx
0x18001df58  mov     rbx, rcx
0x18001df5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df62  lea     r15, WPP_GLOBAL_Control
0x18001df69  cmp     rcx, r15
0x18001df6c  jz      short loc_18001DF92
0x18001df6e  test    byte ptr [rcx+1Ch], 40h
0x18001df72  jz      short loc_18001DF92
0x18001df74  cmp     byte ptr [rcx+19h], 6
0x18001df78  jb      short loc_18001DF92
0x18001df7a  mov     rcx, [rcx+10h]
0x18001df7e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001df85  mov     edx, 155h
0x18001df8a  mov     r9, rbx
0x18001df8d  call    WPP_SF_q
0x18001df92  xor     edx, edx; Val
0x18001df94  lea     rcx, [rsp+3D8h+var_3B8]; void *
0x18001df99  mov     r8d, 398h; Size
0x18001df9f  call    memset_0
0x18001dfa4  lea     r8, [rsp+3D8h+var_3B8]
0x18001dfa9  mov     rdx, rbx
0x18001dfac  xor     ecx, ecx
0x18001dfae  call    RasGetInfo
0x18001dfb3  mov     ebx, eax
0x18001dfb5  test    eax, eax
0x18001dfb7  jz      short loc_18001E01D
0x18001dfb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfc0  cmp     rcx, r15
0x18001dfc3  jz      short loc_18001E019
0x18001dfc5  test    byte ptr [rcx+1Ch], 40h
0x18001dfc9  jz      short loc_18001DFF0
0x18001dfcb  cmp     byte ptr [rcx+19h], 2
0x18001dfcf  jb      short loc_18001DFF0
0x18001dfd1  mov     rcx, [rcx+10h]
0x18001dfd5  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dfdc  mov     edx, 156h
0x18001dfe1  mov     r9d, eax
0x18001dfe4  call    WPP_SF_d
0x18001dfe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff0  cmp     rcx, r15
0x18001dff3  jz      short loc_18001E019
0x18001dff5  test    byte ptr [rcx+1Ch], 40h
0x18001dff9  jz      short loc_18001E019
0x18001dffb  cmp     byte ptr [rcx+19h], 6
0x18001dfff  jb      short loc_18001E019
0x18001e001  mov     rcx, [rcx+10h]
0x18001e005  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e00c  mov     edx, 157h
0x18001e011  mov     r9d, ebx
0x18001e014  call    WPP_SF_d
0x18001e019  mov     eax, ebx
0x18001e01b  jmp     short loc_18001E078
0x18001e01d  mov     al, [rsp+3D8h+var_374]
0x18001e021  movups  xmm0, [rsp+3D8h+var_394]
0x18001e026  movups  xmm1, [rsp+3D8h+var_384]
0x18001e02b  movups  xmmword ptr [rdi+8], xmm0
0x18001e02f  movups  xmmword ptr [rdi+18h], xmm1
0x18001e033  mov     [rdi+28h], al
0x18001e036  mov     eax, [rsp+3D8h+var_264]
0x18001e03d  mov     [rdi+4], eax
0x18001e040  mov     eax, [rsp+3D8h+var_3AC]
0x18001e044  mov     [rdi], eax
0x18001e046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e04d  cmp     rcx, r15
0x18001e050  jz      short loc_18001E076
0x18001e052  test    byte ptr [rcx+1Ch], 40h
0x18001e056  jz      short loc_18001E076
0x18001e058  cmp     byte ptr [rcx+19h], 6
0x18001e05c  jb      short loc_18001E076
0x18001e05e  mov     rcx, [rcx+10h]
0x18001e062  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e069  mov     edx, 158h
0x18001e06e  xor     r9d, r9d
0x18001e071  call    WPP_SF_d
0x18001e076  xor     eax, eax
0x18001e078  mov     rcx, [rsp+3D8h+var_18]
0x18001e080  xor     rcx, rsp; StackCookie
0x18001e083  call    __security_check_cookie
0x18001e088  lea     r11, [rsp+3D8h+var_8]
0x18001e090  mov     rbx, [r11+20h]
0x18001e094  mov     rdi, [r11+28h]
0x18001e098  mov     rsp, r11
0x18001e09b  pop     r15
0x18001e09d  retn
```
