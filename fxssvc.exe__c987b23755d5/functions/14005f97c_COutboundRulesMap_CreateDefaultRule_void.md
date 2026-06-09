# COutboundRulesMap::CreateDefaultRule(void)

- ea: `0x14005f97c`
- end: `0x14005fd22`
- name: `?CreateDefaultRule@COutboundRulesMap@@QEAAHXZ`
- size: `934`
- prototype: `__int64 __fastcall(COutboundRulesMap *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1400472a0`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x14002c3d4`
- `0x14002c54c`
- `0x14005f830`
- `0x14005f97c`
- `0x14005fd28`
- `0x1400601ec`
- `0x140060558`
- `0x1400606f0`
- `0x140060ed0`
- `0x140065df8`
- `0x14007dfa0`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005fccf`
- `ADVAPI32!RegCloseKey` at `0x14005fccf`
- `KERNEL32!GetLastError` at `0x14005f9fe`
- `KERNEL32!GetLastError` at `0x14005fa5c`
- `KERNEL32!GetLastError` at `0x14005f9fe`
- `KERNEL32!GetLastError` at `0x14005fa5c`
- `KERNEL32!SetLastError` at `0x14005fcdb`
- `KERNEL32!SetLastError` at `0x14005fcdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall COutboundRulesMap::CreateDefaultRule(COutboundRulesMap *this)
{
  COutboundRulesMap *v1; // r14
  unsigned int v2; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  HKEY v7; // r15
  DWORD v8; // eax
  DWORD v9; // esi
  unsigned int Status; // eax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  COutboundRulesMap *v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-C8h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-C0h] BYREF
  _WORD v17[8]; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A0h]
  __int64 v19; // [rsp+60h] [rbp-98h]
  void *Block[3]; // [rsp+78h] [rbp-80h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp-68h]
  void *v22[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v23; // [rsp+B0h] [rbp-48h]

  v1 = g_pRulesMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids);
  }
  v2 = 0;
  v16[0] = 0;
  v15 = 0;
  if ( COutboundRulesMap::FindRule(v1, (struct CDialingLocation *)v16) )
    return 1;
  LastError = GetLastError();
  if ( LastError != 7005 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 69;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, LastError);
    return 0;
  }
  v7 = (HKEY)OpenOutboundRuleKey(0, 0, 1);
  v16[1] = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 70;
    v5 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v23 = 7;
  v22[2] = 0;
  LOWORD(v22[0]) = 0;
  v21 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  std::wstring::assign(Block, (void *)L"<All devices>");
  v19 = 7;
  v18 = 0;
  v17[0] = 0;
  std::wstring::assign(v17);
  v8 = COutboundRoutingRule::Init(v22);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v8);
    }
    if ( v21 >= 8 )
      operator delete(Block[0]);
    goto LABEL_53;
  }
  if ( v21 >= 8 )
    operator delete(Block[0]);
  Status = COutboundRulesMap::AddRule(v1, (struct COutboundRoutingRule *)v22);
  v9 = Status;
  if ( Status )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 73;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, Status);
    }
  }
  else
  {
    v13 = COutboundRoutingRule::Save((COutboundRoutingRule *)v22, v7);
    v9 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v13);
      }
      COutboundRulesMap::DelRule(v14, (struct CDialingLocation *)v16);
      goto LABEL_53;
    }
    Status = COutboundRoutingRule::GetStatus((COutboundRoutingRule *)v22, (enum FAX_ENUM_RULE_STATUS *)&v15);
    if ( !Status )
    {
      if ( v15 && v15 != 3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v15);
        }
        FaxLog(1, 2, 2, 2147515716LL);
      }
      goto LABEL_53;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 75;
      goto LABEL_34;
    }
  }
LABEL_53:
  RegCloseKey(v7);
  if ( v9 )
    SetLastError(v9);
  else
    v2 = 1;
  if ( v23 >= 8 )
    operator delete(v22[0]);
  return v2;
}

```

## disassembly

```asm
0x14005f97c  push    rbx
0x14005f97e  push    rsi
0x14005f97f  push    r12
0x14005f981  push    r14
0x14005f983  push    r15
0x14005f985  sub     rsp, 0D0h
0x14005f98c  mov     rax, cs:__security_cookie
0x14005f993  xor     rax, rsp
0x14005f996  mov     [rsp+0F8h+var_30], rax
0x14005f99e  mov     r14, cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA; COutboundRulesMap * g_pRulesMap
0x14005f9a5  lea     r12, WPP_GLOBAL_Control
0x14005f9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f9b3  cmp     rcx, r12
0x14005f9b6  jz      short loc_14005F9D9
0x14005f9b8  test    byte ptr [rcx+1Ch], 4
0x14005f9bc  jz      short loc_14005F9D9
0x14005f9be  cmp     byte ptr [rcx+19h], 5
0x14005f9c2  jb      short loc_14005F9D9
0x14005f9c4  mov     edx, 44h ; 'D'
0x14005f9c9  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005f9d0  mov     rcx, [rcx+10h]
0x14005f9d4  call    WPP_SF_
0x14005f9d9  xor     ebx, ebx
0x14005f9db  mov     [rsp+0F8h+var_C0], rbx
0x14005f9e0  mov     [rsp+0F8h+var_C8], ebx
0x14005f9e4  lea     rdx, [rsp+0F8h+var_C0]; struct CDialingLocation *
0x14005f9e9  mov     rcx, r14; this
0x14005f9ec  call    ?FindRule@COutboundRulesMap@@QEAAPEAVCOutboundRoutingRule@@AEAVCDialingLocation@@@Z; COutboundRulesMap::FindRule(CDialingLocation &)
0x14005f9f1  test    rax, rax
0x14005f9f4  jz      short loc_14005F9FE
0x14005f9f6  lea     eax, [rbx+1]
0x14005f9f9  jmp     loc_14005FD02
0x14005f9fe  call    cs:__imp_GetLastError
0x14005fa04  cmp     eax, 1B5Dh
0x14005fa09  jz      short loc_14005FA2A
0x14005fa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fa12  cmp     rcx, r12
0x14005fa15  jz      short loc_14005FA80
0x14005fa17  test    byte ptr [rcx+1Ch], 4
0x14005fa1b  jz      short loc_14005FA80
0x14005fa1d  cmp     byte ptr [rcx+19h], 2
0x14005fa21  jb      short loc_14005FA80
0x14005fa23  mov     edx, 45h ; 'E'
0x14005fa28  jmp     short loc_14005FA6D
0x14005fa2a  xor     edx, edx
0x14005fa2c  xor     ecx, ecx
0x14005fa2e  lea     r8d, [rdx+1]
0x14005fa32  call    OpenOutboundRuleKey
0x14005fa37  mov     r15, rax
0x14005fa3a  mov     [rsp+0F8h+var_B8], rax
0x14005fa3f  test    rax, rax
0x14005fa42  jnz     short loc_14005FA87
0x14005fa44  mov     rax, cs:WPP_GLOBAL_Control
0x14005fa4b  cmp     rax, r12
0x14005fa4e  jz      short loc_14005FA80
0x14005fa50  test    byte ptr [rax+1Ch], 4
0x14005fa54  jz      short loc_14005FA80
0x14005fa56  cmp     byte ptr [rax+19h], 2
0x14005fa5a  jb      short loc_14005FA80
0x14005fa5c  call    cs:__imp_GetLastError
0x14005fa62  lea     edx, [r15+46h]
0x14005fa66  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fa6d  mov     r9d, eax
0x14005fa70  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fa77  mov     rcx, [rcx+10h]
0x14005fa7b  call    WPP_SF_d
0x14005fa80  xor     eax, eax
0x14005fa82  jmp     loc_14005FD02
0x14005fa87  mov     esi, 7
0x14005fa8c  mov     [rsp+0F8h+var_48], rsi
0x14005fa94  mov     [rsp+0F8h+var_50], rbx
0x14005fa9c  mov     word ptr [rsp+0F8h+var_60], bx
0x14005faa4  mov     [rsp+0F8h+var_68], rsi
0x14005faac  mov     [rsp+0F8h+var_70], rbx
0x14005fab4  mov     word ptr [rsp+0F8h+Block], bx
0x14005fab9  lea     rdx, aAllDevices; "<All devices>"
0x14005fac0  lea     rcx, [rsp+0F8h+Block]; void *
0x14005fac5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x14005faca  nop
0x14005facb  mov     [rsp+0F8h+var_98], rsi
0x14005fad0  mov     [rsp+0F8h+var_A0], rbx
0x14005fad5  mov     [rsp+0F8h+var_B0], bx
0x14005fada  or      r9, 0FFFFFFFFFFFFFFFFh
0x14005fade  xor     r8d, r8d
0x14005fae1  lea     rdx, [rsp+0F8h+Block]
0x14005fae6  lea     rcx, [rsp+0F8h+var_B0]; void *
0x14005faeb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14005faf0  lea     r8, [rsp+0F8h+var_B0]
0x14005faf5  mov     rdx, [rsp+0F8h+var_C0]
0x14005fafa  lea     rcx, [rsp+0F8h+var_60]; void *
0x14005fb02  call    ?Init@COutboundRoutingRule@@QEAAKVCDialingLocation@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; COutboundRoutingRule::Init(CDialingLocation,std::wstring)
0x14005fb07  mov     esi, eax
0x14005fb09  test    eax, eax
0x14005fb0b  jz      short loc_14005FB59
0x14005fb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb14  cmp     rcx, r12
0x14005fb17  jz      short loc_14005FB3E
0x14005fb19  test    byte ptr [rcx+1Ch], 4
0x14005fb1d  jz      short loc_14005FB3E
0x14005fb1f  cmp     byte ptr [rcx+19h], 2
0x14005fb23  jb      short loc_14005FB3E
0x14005fb25  mov     edx, 47h ; 'G'
0x14005fb2a  mov     r9d, eax
0x14005fb2d  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fb34  mov     rcx, [rcx+10h]
0x14005fb38  call    WPP_SF_d
0x14005fb3d  nop
0x14005fb3e  cmp     [rsp+0F8h+var_68], 8
0x14005fb47  jb      short loc_14005FB54
0x14005fb49  mov     rcx, [rsp+0F8h+Block]; Block
0x14005fb4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fb53  nop
0x14005fb54  jmp     loc_14005FCCC
0x14005fb59  cmp     [rsp+0F8h+var_68], 8
0x14005fb62  jb      short loc_14005FB6F
0x14005fb64  mov     rcx, [rsp+0F8h+Block]; Block
0x14005fb69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fb6e  nop
0x14005fb6f  lea     rdx, [rsp+0F8h+var_60]; struct COutboundRoutingRule *
0x14005fb77  mov     rcx, r14; this
0x14005fb7a  call    ?AddRule@COutboundRulesMap@@QEAAKAEAVCOutboundRoutingRule@@@Z; COutboundRulesMap::AddRule(COutboundRoutingRule &)
0x14005fb7f  mov     esi, eax
0x14005fb81  test    eax, eax
0x14005fb83  jz      short loc_14005FBC6
0x14005fb85  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fb8c  cmp     rcx, r12
0x14005fb8f  jz      loc_14005FCCC
0x14005fb95  test    byte ptr [rcx+1Ch], 4
0x14005fb99  jz      loc_14005FCCC
0x14005fb9f  cmp     byte ptr [rcx+19h], 2
0x14005fba3  jb      loc_14005FCCC
0x14005fba9  mov     edx, 49h ; 'I'
0x14005fbae  mov     r9d, eax
0x14005fbb1  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fbb8  mov     rcx, [rcx+10h]
0x14005fbbc  call    WPP_SF_d
0x14005fbc1  jmp     loc_14005FCCC
0x14005fbc6  mov     rdx, r15; HKEY
0x14005fbc9  lea     rcx, [rsp+0F8h+var_60]; this
0x14005fbd1  call    ?Save@COutboundRoutingRule@@QEBAKPEAUHKEY__@@@Z; COutboundRoutingRule::Save(HKEY__ *)
0x14005fbd6  mov     esi, eax
0x14005fbd8  test    eax, eax
0x14005fbda  jz      short loc_14005FC1B
0x14005fbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fbe3  cmp     rcx, r12
0x14005fbe6  jz      short loc_14005FC0C
0x14005fbe8  test    byte ptr [rcx+1Ch], 4
0x14005fbec  jz      short loc_14005FC0C
0x14005fbee  cmp     byte ptr [rcx+19h], 2
0x14005fbf2  jb      short loc_14005FC0C
0x14005fbf4  mov     edx, 4Ah ; 'J'
0x14005fbf9  mov     r9d, eax
0x14005fbfc  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fc03  mov     rcx, [rcx+10h]
0x14005fc07  call    WPP_SF_d
0x14005fc0c  lea     rdx, [rsp+0F8h+var_C0]; struct CDialingLocation *
0x14005fc11  call    ?DelRule@COutboundRulesMap@@QEAAKAEAVCDialingLocation@@@Z; COutboundRulesMap::DelRule(CDialingLocation &)
0x14005fc16  jmp     loc_14005FCCC
0x14005fc1b  lea     rdx, [rsp+0F8h+var_C8]; enum FAX_ENUM_RULE_STATUS *
0x14005fc20  lea     rcx, [rsp+0F8h+var_60]; this
0x14005fc28  call    ?GetStatus@COutboundRoutingRule@@QEBAKPEAW4FAX_ENUM_RULE_STATUS@@@Z; COutboundRoutingRule::GetStatus(FAX_ENUM_RULE_STATUS *)
0x14005fc2d  test    eax, eax
0x14005fc2f  jz      short loc_14005FC5B
0x14005fc31  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc38  cmp     rcx, r12
0x14005fc3b  jz      loc_14005FCCC
0x14005fc41  test    byte ptr [rcx+1Ch], 4
0x14005fc45  jz      loc_14005FCCC
0x14005fc4b  cmp     byte ptr [rcx+19h], 2
0x14005fc4f  jb      short loc_14005FCCC
0x14005fc51  mov     edx, 4Bh ; 'K'
0x14005fc56  jmp     loc_14005FBAE
0x14005fc5b  mov     r9d, [rsp+0F8h+var_C8]
0x14005fc60  test    r9d, r9d
0x14005fc63  jz      short loc_14005FCCC
0x14005fc65  cmp     r9d, 3
0x14005fc69  jz      short loc_14005FCCC
0x14005fc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc72  cmp     rcx, r12
0x14005fc75  jz      short loc_14005FC98
0x14005fc77  test    byte ptr [rcx+1Ch], 4
0x14005fc7b  jz      short loc_14005FC98
0x14005fc7d  cmp     byte ptr [rcx+19h], 5
0x14005fc81  jb      short loc_14005FC98
0x14005fc83  mov     edx, 4Ch ; 'L'
0x14005fc88  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14005fc8f  mov     rcx, [rcx+10h]
0x14005fc93  call    WPP_SF_d
0x14005fc98  lea     rax, asc_14008EF14; "*"
0x14005fc9f  mov     [rsp+0F8h+var_D0], rax
0x14005fca4  mov     [rsp+0F8h+var_D8], rax
0x14005fca9  mov     edx, 2
0x14005fcae  lea     ecx, [rdx-1]
0x14005fcb1  mov     r9d, 80007D44h
0x14005fcb7  mov     r8d, edx
0x14005fcba  call    FaxLog
0x14005fcbf  jmp     short loc_14005FCCC
0x14005fcc1  xor     ebx, ebx
0x14005fcc3  mov     esi, [rsp+0F8h+var_C8]
0x14005fcc7  mov     r15, [rsp+0F8h+var_B8]
0x14005fccc  mov     rcx, r15; hKey
0x14005fccf  call    cs:__imp_RegCloseKey
0x14005fcd5  test    esi, esi
0x14005fcd7  jz      short loc_14005FCE3
0x14005fcd9  mov     ecx, esi; dwErrCode
0x14005fcdb  call    cs:__imp_SetLastError
0x14005fce1  jmp     short loc_14005FCE8
0x14005fce3  mov     ebx, 1
0x14005fce8  cmp     [rsp+0F8h+var_48], 8
0x14005fcf1  jb      short loc_14005FD00
0x14005fcf3  mov     rcx, [rsp+0F8h+var_60]; Block
0x14005fcfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005fd00  mov     eax, ebx
0x14005fd02  mov     rcx, [rsp+0F8h+var_30]
0x14005fd0a  xor     rcx, rsp; StackCookie
0x14005fd0d  call    __security_check_cookie
0x14005fd12  add     rsp, 0D0h
0x14005fd19  pop     r15
0x14005fd1b  pop     r14
0x14005fd1d  pop     r12
0x14005fd1f  pop     rsi
0x14005fd20  pop     rbx
0x14005fd21  retn
```
