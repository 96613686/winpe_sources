# OneXCreateSupplicantPort

- ea: `0x180012cc0`
- end: `0x180012f84`
- name: `OneXCreateSupplicantPort`
- size: `708`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180004280`
- `0x180005440`
- `0x180010ae0`
- `0x180012cc0`
- `0x180012f90`
- `0x18001b53c`
- `0x18001fb58`
- `0x1800214f0`
- `0x18002d9a8`

## string_xrefs

- `0x180012d41`: `OneXCreateSupplicantPort`
- `0x180012ef7`: `OneXCreateSupplicantPort`

## pseudocode

```c
__int64 __fastcall OneXCreateSupplicantPort(int a1, __int64 a2, unsigned int a3, __int64 a4, _QWORD *a5, char a6)
{
  _QWORD *v10; // rcx
  unsigned int NewPort; // eax
  int v12; // r8d
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  _QWORD *v20; // rcx
  _DWORD v22[18]; // [rsp+30h] [rbp-48h] BYREF

  v22[0] = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
      WPP_SF_(v10[7], 30, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  }
  NewPort = IncThreadCountAndCheckInitialized("OneXCreateSupplicantPort", 215);
  v13 = NewPort;
  if ( NewPort )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_44;
    v15 = 31;
LABEL_11:
    v16 = NewPort;
LABEL_12:
    WPP_SF_d(v14[7], v15, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v16);
LABEL_43:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  if ( a1 != 1 )
  {
    v13 = 50;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_44;
    v15 = 32;
    goto LABEL_17;
  }
  if ( a5 && a4 && a3 )
  {
    if ( *(int *)(a2 + 8) >= 2 )
    {
      v13 = 87;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_47;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_44;
      v15 = 34;
LABEL_17:
      v16 = v13;
      goto LABEL_12;
    }
    if ( !(unsigned int)MSMIsMissingMandatoryCallback(a2 + 2088) )
    {
      NewPort = OneXValidateProfile(a3, a4, *(unsigned int *)(a2 + 8), v22);
      v13 = NewPort;
      if ( NewPort )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_47;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_44;
        v15 = 36;
      }
      else
      {
        NewPort = PortMgrCreateNewPort(v18, a3, a4, a2, a5);
        v13 = NewPort;
        if ( !NewPort )
        {
          if ( (a6 & 1) != 0 )
            *(_DWORD *)(*a5 + 24LL) |= 1u;
          goto LABEL_43;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_47;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_44;
        v15 = 37;
      }
      goto LABEL_11;
    }
    v13 = 127;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_44;
    v17 = 35;
LABEL_42:
    WPP_SF_(v14[7], v17, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
    goto LABEL_43;
  }
  v13 = 87;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_47;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v17 = 33;
    goto LABEL_42;
  }
LABEL_44:
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 17) & 0x400) != 0 )
    WPP_SF_sd(v14[7], 32, v12, (unsigned int)"OneXCreateSupplicantPort", 0);
LABEL_47:
  v19 = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)&qword_18003DD5C);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v19);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 17) & 0x800) != 0 )
      WPP_SF_D(v20[7], 38, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180012cc0  push    rbx
0x180012cc2  push    rbp
0x180012cc3  push    rsi
0x180012cc4  push    rdi
0x180012cc5  push    r12
0x180012cc7  push    r14
0x180012cc9  push    r15
0x180012ccb  sub     rsp, 40h
0x180012ccf  mov     rbp, r9
0x180012cd2  mov     [rsp+78h+var_48], 0
0x180012cda  mov     r14d, r8d
0x180012cdd  mov     rsi, rdx
0x180012ce0  mov     edi, ecx
0x180012ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ce9  lea     r15, WPP_GLOBAL_Control
0x180012cf0  lea     r12, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180012cf7  cmp     rcx, r15
0x180012cfa  jz      short loc_180012D3C
0x180012cfc  test    dword ptr [rcx+44h], 800h
0x180012d03  jz      short loc_180012D1D
0x180012d05  mov     rcx, [rcx+38h]
0x180012d09  mov     edx, 1Dh
0x180012d0e  mov     r8, r12
0x180012d11  call    WPP_SF_
0x180012d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d1d  cmp     rcx, r15
0x180012d20  jz      short loc_180012D3C
0x180012d22  test    dword ptr [rcx+44h], 100h
0x180012d29  jz      short loc_180012D3C
0x180012d2b  mov     rcx, [rcx+38h]
0x180012d2f  mov     edx, 1Eh
0x180012d34  mov     r8, r12
0x180012d37  call    WPP_SF_
0x180012d3c  mov     edx, 0D7h
0x180012d41  lea     rcx, aOnexcreatesupp_0; "OneXCreateSupplicantPort"
0x180012d48  call    IncThreadCountAndCheckInitialized
0x180012d4d  mov     ebx, eax
0x180012d4f  test    eax, eax
0x180012d51  jz      short loc_180012D86
0x180012d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d5a  cmp     rcx, r15
0x180012d5d  jz      loc_180012F10
0x180012d63  test    byte ptr [rcx+44h], 1
0x180012d67  jz      loc_180012EE5
0x180012d6d  mov     edx, 1Fh
0x180012d72  mov     r9d, eax
0x180012d75  mov     rcx, [rcx+38h]
0x180012d79  mov     r8, r12
0x180012d7c  call    WPP_SF_d
0x180012d81  jmp     loc_180012EDE
0x180012d86  cmp     edi, 1
0x180012d89  jz      short loc_180012DB2
0x180012d8b  mov     ebx, 32h ; '2'
0x180012d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d97  cmp     rcx, r15
0x180012d9a  jz      loc_180012F10
0x180012da0  test    byte ptr [rcx+44h], 1
0x180012da4  jz      loc_180012EE5
0x180012daa  lea     edx, [rbx-12h]
0x180012dad  mov     r9d, ebx
0x180012db0  jmp     short loc_180012D75
0x180012db2  mov     rdi, [rsp+78h+arg_20]
0x180012dba  test    rdi, rdi
0x180012dbd  jz      loc_180012EB8
0x180012dc3  test    rbp, rbp
0x180012dc6  jz      loc_180012EB8
0x180012dcc  test    r14d, r14d
0x180012dcf  jz      loc_180012EB8
0x180012dd5  cmp     dword ptr [rsi+8], 2
0x180012dd9  jl      short loc_180012DFF
0x180012ddb  mov     ebx, 57h ; 'W'
0x180012de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012de7  cmp     rcx, r15
0x180012dea  jz      loc_180012F10
0x180012df0  test    byte ptr [rcx+44h], 1
0x180012df4  jz      loc_180012EE5
0x180012dfa  lea     edx, [rbx-35h]
0x180012dfd  jmp     short loc_180012DAD
0x180012dff  lea     rcx, [rsi+828h]
0x180012e06  call    MSMIsMissingMandatoryCallback
0x180012e0b  test    eax, eax
0x180012e0d  jz      short loc_180012E36
0x180012e0f  mov     ebx, 7Fh
0x180012e14  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e1b  cmp     rcx, r15
0x180012e1e  jz      loc_180012F10
0x180012e24  test    byte ptr [rcx+44h], 1
0x180012e28  jz      loc_180012EE5
0x180012e2e  lea     edx, [rbx-5Ch]
0x180012e31  jmp     loc_180012ED2
0x180012e36  mov     r8d, [rsi+8]
0x180012e3a  lea     r9, [rsp+78h+var_48]
0x180012e3f  mov     rdx, rbp
0x180012e42  mov     ecx, r14d
0x180012e45  call    OneXValidateProfile
0x180012e4a  mov     ebx, eax
0x180012e4c  test    eax, eax
0x180012e4e  jz      short loc_180012E70
0x180012e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e57  cmp     rcx, r15
0x180012e5a  jz      loc_180012F10
0x180012e60  test    byte ptr [rcx+44h], 1
0x180012e64  jz      short loc_180012EE5
0x180012e66  mov     edx, 24h ; '$'
0x180012e6b  jmp     loc_180012D72
0x180012e70  mov     r9, rsi
0x180012e73  mov     [rsp+78h+var_58], rdi
0x180012e78  mov     r8, rbp
0x180012e7b  mov     edx, r14d
0x180012e7e  call    PortMgrCreateNewPort
0x180012e83  mov     ebx, eax
0x180012e85  test    eax, eax
0x180012e87  jz      short loc_180012EA5
0x180012e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e90  cmp     rcx, r15
0x180012e93  jz      short loc_180012F10
0x180012e95  test    byte ptr [rcx+44h], 1
0x180012e99  jz      short loc_180012EE5
0x180012e9b  mov     edx, 25h ; '%'
0x180012ea0  jmp     loc_180012D72
0x180012ea5  test    [rsp+78h+arg_28], 1
0x180012ead  jz      short loc_180012EDE
0x180012eaf  mov     rax, [rdi]
0x180012eb2  or      dword ptr [rax+18h], 1
0x180012eb6  jmp     short loc_180012EDE
0x180012eb8  mov     ebx, 57h ; 'W'
0x180012ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ec4  cmp     rcx, r15
0x180012ec7  jz      short loc_180012F10
0x180012ec9  test    byte ptr [rcx+44h], 1
0x180012ecd  jz      short loc_180012EE5
0x180012ecf  lea     edx, [rbx-36h]
0x180012ed2  mov     rcx, [rcx+38h]
0x180012ed6  mov     r8, r12
0x180012ed9  call    WPP_SF_
0x180012ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ee5  cmp     rcx, r15
0x180012ee8  jz      short loc_180012F10
0x180012eea  test    dword ptr [rcx+44h], 400h
0x180012ef1  jz      short loc_180012F10
0x180012ef3  mov     rcx, [rcx+38h]
0x180012ef7  lea     r9, aOnexcreatesupp_0; "OneXCreateSupplicantPort"
0x180012efe  mov     edx, 20h ; ' '
0x180012f03  mov     dword ptr [rsp+78h+var_58], 100h
0x180012f0b  call    WPP_SF_sd
0x180012f10  or      r9d, 0FFFFFFFFh
0x180012f14  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180012f1d  dec     r9d
0x180012f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f27  cmp     rcx, r15
0x180012f2a  jz      short loc_180012F73
0x180012f2c  test    dword ptr [rcx+44h], 400h
0x180012f33  jz      short loc_180012F51
0x180012f35  mov     rcx, [rcx+38h]
0x180012f39  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180012f40  mov     edx, 21h ; '!'
0x180012f45  call    WPP_SF_d
0x180012f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f51  cmp     rcx, r15
0x180012f54  jz      short loc_180012F73
0x180012f56  test    dword ptr [rcx+44h], 800h
0x180012f5d  jz      short loc_180012F73
0x180012f5f  mov     rcx, [rcx+38h]
0x180012f63  mov     edx, 26h ; '&'
0x180012f68  mov     r9d, ebx
0x180012f6b  mov     r8, r12
0x180012f6e  call    WPP_SF_D
0x180012f73  mov     eax, ebx
0x180012f75  add     rsp, 40h
0x180012f79  pop     r15
0x180012f7b  pop     r14
0x180012f7d  pop     r12
0x180012f7f  pop     rdi
0x180012f80  pop     rsi
0x180012f81  pop     rbp
0x180012f82  pop     rbx
0x180012f83  retn
```
