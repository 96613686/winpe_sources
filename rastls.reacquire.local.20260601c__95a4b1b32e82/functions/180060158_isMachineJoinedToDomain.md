# isMachineJoinedToDomain

- ea: `0x180060158`
- end: `0x1800602be`
- name: `isMachineJoinedToDomain`
- size: `358`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180006620`
- `0x18004de18`
- `0x180068250`
- `0x180068c68`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180039540`
- `0x180060158`

## import_xrefs

- `wkscli!NetGetJoinInformation` at `0x1800601d3`
- `wkscli!NetGetJoinInformation` at `0x1800601d3`
- `netutils!NetApiBufferFree` at `0x18006029f`
- `netutils!NetApiBufferFree` at `0x18006029f`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigForceNotDomainJoined` at `0x18006018e`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigForceNotDomainJoined` at `0x18006018e`

## pseudocode

```c
__int64 isMachineJoinedToDomain()
{
  unsigned int v1; // ebx
  DWORD JoinInformation; // eax
  struct _EAPTLS_CONTROL_BLOCK *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  __int64 v7; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v8; // rcx
  __int64 v9; // rdx
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR NameBuffer; // [rsp+38h] [rbp+10h] BYREF

  NameBuffer = 0;
  BufferType = NetSetupUnknownStatus;
  if ( (unsigned __int8)IsRasTlsExt_GetPinUserBlobPresent() )
  {
    if ( (unsigned int)RasTlsExt_GetConfigForceNotDomainJoined() )
      return 0;
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  }
  v1 = 1;
  JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
  if ( !JoinInformation )
  {
    v5 = (unsigned int)BufferType;
    switch ( BufferType )
    {
      case NetSetupUnknownStatus:
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_27;
        v7 = 57;
        goto LABEL_26;
      case NetSetupUnjoined:
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v9 = 58;
          goto LABEL_22;
        }
        break;
      case NetSetupWorkgroupName:
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v9 = 59;
LABEL_22:
          WPP_SF_(*((_QWORD *)v8 + 2), v9, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
        }
        break;
      case NetSetupDomainName:
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_27;
        v7 = 60;
LABEL_26:
        WPP_SF_(*((_QWORD *)v6 + 2), v7, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
        goto LABEL_27;
      default:
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_27;
        v4 = 61;
        goto LABEL_9;
    }
    v1 = 0;
    goto LABEL_27;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v4 = 56;
    v5 = JoinInformation;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v5);
  }
LABEL_27:
  NetApiBufferFree(NameBuffer);
  return v1;
}

```

## disassembly

```asm
0x180060158  mov     rax, rsp
0x18006015b  mov     [rax+18h], rbx
0x18006015f  mov     [rax+20h], rsi
0x180060163  push    rdi
0x180060164  sub     rsp, 20h
0x180060168  mov     qword ptr [rax+10h], 0
0x180060170  mov     dword ptr [rax+8], 0
0x180060177  call    IsRasTlsExt_GetPinUserBlobPresent
0x18006017c  lea     rsi, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x180060183  lea     rdi, WPP_GLOBAL_Control
0x18006018a  test    al, al
0x18006018c  jz      short loc_1800601A5
0x18006018e  call    cs:__imp_RasTlsExt_GetConfigForceNotDomainJoined
0x180060195  nop     dword ptr [rax+rax+00h]
0x18006019a  test    eax, eax
0x18006019c  jz      short loc_1800601C2
0x18006019e  xor     eax, eax
0x1800601a0  jmp     loc_1800602AD
0x1800601a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800601ac  cmp     rcx, rdi
0x1800601af  jz      short loc_1800601C2
0x1800601b1  mov     rcx, [rcx+10h]
0x1800601b5  mov     edx, 37h ; '7'
0x1800601ba  mov     r8, rsi
0x1800601bd  call    WPP_SF_
0x1800601c2  lea     r8, [rsp+28h+BufferType]; BufferType
0x1800601c7  xor     ecx, ecx; lpServer
0x1800601c9  lea     rdx, [rsp+28h+NameBuffer]; lpNameBuffer
0x1800601ce  mov     ebx, 1
0x1800601d3  call    cs:__imp_NetGetJoinInformation
0x1800601da  nop     dword ptr [rax+rax+00h]
0x1800601df  test    eax, eax
0x1800601e1  jz      short loc_18006020A
0x1800601e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800601ea  cmp     rcx, rdi
0x1800601ed  jz      loc_18006029A
0x1800601f3  lea     edx, [rbx+37h]
0x1800601f6  mov     r9d, eax
0x1800601f9  mov     rcx, [rcx+10h]
0x1800601fd  mov     r8, rsi
0x180060200  call    WPP_SF_d
0x180060205  jmp     loc_18006029A
0x18006020a  mov     r9d, [rsp+28h+BufferType]
0x18006020f  mov     ecx, r9d
0x180060212  test    r9d, r9d
0x180060215  jz      short loc_18006027D
0x180060217  sub     ecx, ebx
0x180060219  jz      short loc_18006025C
0x18006021b  sub     ecx, ebx
0x18006021d  jz      short loc_180060249
0x18006021f  cmp     ecx, ebx
0x180060221  jz      short loc_180060236
0x180060223  mov     rcx, cs:WPP_GLOBAL_Control
0x18006022a  cmp     rcx, rdi
0x18006022d  jz      short loc_18006029A
0x18006022f  mov     edx, 3Dh ; '='
0x180060234  jmp     short loc_1800601F9
0x180060236  mov     rcx, cs:WPP_GLOBAL_Control
0x18006023d  cmp     rcx, rdi
0x180060240  jz      short loc_18006029A
0x180060242  mov     edx, 3Ch ; '<'
0x180060247  jmp     short loc_18006028E
0x180060249  mov     rcx, cs:WPP_GLOBAL_Control
0x180060250  cmp     rcx, rdi
0x180060253  jz      short loc_180060279
0x180060255  mov     edx, 3Bh ; ';'
0x18006025a  jmp     short loc_18006026D
0x18006025c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060263  cmp     rcx, rdi
0x180060266  jz      short loc_180060279
0x180060268  mov     edx, 3Ah ; ':'
0x18006026d  mov     rcx, [rcx+10h]
0x180060271  mov     r8, rsi
0x180060274  call    WPP_SF_
0x180060279  xor     ebx, ebx
0x18006027b  jmp     short loc_18006029A
0x18006027d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060284  cmp     rcx, rdi
0x180060287  jz      short loc_18006029A
0x180060289  mov     edx, 39h ; '9'
0x18006028e  mov     rcx, [rcx+10h]
0x180060292  mov     r8, rsi
0x180060295  call    WPP_SF_
0x18006029a  mov     rcx, [rsp+28h+NameBuffer]; Buffer
0x18006029f  call    cs:__imp_NetApiBufferFree
0x1800602a6  nop     dword ptr [rax+rax+00h]
0x1800602ab  mov     eax, ebx
0x1800602ad  mov     rbx, [rsp+28h+arg_10]
0x1800602b2  mov     rsi, [rsp+28h+arg_18]
0x1800602b7  add     rsp, 20h
0x1800602bb  pop     rdi
0x1800602bc  retn
```
