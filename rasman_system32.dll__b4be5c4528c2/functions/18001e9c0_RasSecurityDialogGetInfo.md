# RasSecurityDialogGetInfo

- ea: `0x18001e9c0`
- end: `0x18001eb2f`
- name: `RasSecurityDialogGetInfo`
- size: `367`
- prototype: `DWORD __stdcall(HPORT hPort, RAS_SECURITY_INFO *pBuffer)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012050`
- `0x18001e9c0`
- `0x180021b14`
- `0x180021fd4`
- `0x18002739e`
- `0x1800273d0`

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
  Info = RasGetInfo(0, hPort, v10);
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
0x18001e9c0  mov     [rsp+arg_10], rbx
0x18001e9c5  mov     [rsp+arg_18], rdi
0x18001e9ca  push    r15
0x18001e9cc  sub     rsp, 3D0h
0x18001e9d3  mov     rax, cs:__security_cookie
0x18001e9da  xor     rax, rsp
0x18001e9dd  mov     [rsp+3D8h+var_18], rax
0x18001e9e5  mov     rdi, rdx
0x18001e9e8  mov     rbx, rcx
0x18001e9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f2  lea     r15, WPP_GLOBAL_Control
0x18001e9f9  cmp     rcx, r15
0x18001e9fc  jz      short loc_18001EA22
0x18001e9fe  test    byte ptr [rcx+1Ch], 40h
0x18001ea02  jz      short loc_18001EA22
0x18001ea04  cmp     byte ptr [rcx+19h], 6
0x18001ea08  jb      short loc_18001EA22
0x18001ea0a  mov     rcx, [rcx+10h]
0x18001ea0e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ea15  mov     edx, 155h
0x18001ea1a  mov     r9, rbx
0x18001ea1d  call    WPP_SF_q
0x18001ea22  xor     edx, edx; Val
0x18001ea24  lea     rcx, [rsp+3D8h+var_3B8]; void *
0x18001ea29  mov     r8d, 398h; Size
0x18001ea2f  call    memset_0
0x18001ea34  lea     r8, [rsp+3D8h+var_3B8]
0x18001ea39  mov     rdx, rbx
0x18001ea3c  xor     ecx, ecx
0x18001ea3e  call    RasGetInfo
0x18001ea43  mov     ebx, eax
0x18001ea45  test    eax, eax
0x18001ea47  jz      short loc_18001EAAD
0x18001ea49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea50  cmp     rcx, r15
0x18001ea53  jz      short loc_18001EAA9
0x18001ea55  test    byte ptr [rcx+1Ch], 40h
0x18001ea59  jz      short loc_18001EA80
0x18001ea5b  cmp     byte ptr [rcx+19h], 2
0x18001ea5f  jb      short loc_18001EA80
0x18001ea61  mov     rcx, [rcx+10h]
0x18001ea65  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ea6c  mov     edx, 156h
0x18001ea71  mov     r9d, eax
0x18001ea74  call    WPP_SF_d
0x18001ea79  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea80  cmp     rcx, r15
0x18001ea83  jz      short loc_18001EAA9
0x18001ea85  test    byte ptr [rcx+1Ch], 40h
0x18001ea89  jz      short loc_18001EAA9
0x18001ea8b  cmp     byte ptr [rcx+19h], 6
0x18001ea8f  jb      short loc_18001EAA9
0x18001ea91  mov     rcx, [rcx+10h]
0x18001ea95  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ea9c  mov     edx, 157h
0x18001eaa1  mov     r9d, ebx
0x18001eaa4  call    WPP_SF_d
0x18001eaa9  mov     eax, ebx
0x18001eaab  jmp     short loc_18001EB08
0x18001eaad  mov     al, [rsp+3D8h+var_374]
0x18001eab1  movups  xmm0, [rsp+3D8h+var_394]
0x18001eab6  movups  xmm1, [rsp+3D8h+var_384]
0x18001eabb  movups  xmmword ptr [rdi+8], xmm0
0x18001eabf  movups  xmmword ptr [rdi+18h], xmm1
0x18001eac3  mov     [rdi+28h], al
0x18001eac6  mov     eax, [rsp+3D8h+var_264]
0x18001eacd  mov     [rdi+4], eax
0x18001ead0  mov     eax, [rsp+3D8h+var_3AC]
0x18001ead4  mov     [rdi], eax
0x18001ead6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eadd  cmp     rcx, r15
0x18001eae0  jz      short loc_18001EB06
0x18001eae2  test    byte ptr [rcx+1Ch], 40h
0x18001eae6  jz      short loc_18001EB06
0x18001eae8  cmp     byte ptr [rcx+19h], 6
0x18001eaec  jb      short loc_18001EB06
0x18001eaee  mov     rcx, [rcx+10h]
0x18001eaf2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001eaf9  mov     edx, 158h
0x18001eafe  xor     r9d, r9d
0x18001eb01  call    WPP_SF_d
0x18001eb06  xor     eax, eax
0x18001eb08  mov     rcx, [rsp+3D8h+var_18]
0x18001eb10  xor     rcx, rsp; StackCookie
0x18001eb13  call    __security_check_cookie
0x18001eb18  lea     r11, [rsp+3D8h+var_8]
0x18001eb20  mov     rbx, [r11+20h]
0x18001eb24  mov     rdi, [r11+28h]
0x18001eb28  mov     rsp, r11
0x18001eb2b  pop     r15
0x18001eb2d  retn
```
