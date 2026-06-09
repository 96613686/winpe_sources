# isMachineJoinedToDomain

- ea: `0x18005caf4`
- end: `0x18005cc47`
- name: `isMachineJoinedToDomain`
- size: `339`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800060f0`
- `0x18004b518`
- `0x180064740`
- `0x1800650c0`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180036930`
- `0x18005caf4`

## import_xrefs

- `wkscli!NetGetJoinInformation` at `0x18005cb69`
- `wkscli!NetGetJoinInformation` at `0x18005cb69`
- `netutils!NetApiBufferFree` at `0x18005cc2f`
- `netutils!NetApiBufferFree` at `0x18005cc2f`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigForceNotDomainJoined` at `0x18005cb2a`
- `ext-ms-win-rastlsext-eap-l1-1-0!RasTlsExt_GetConfigForceNotDomainJoined` at `0x18005cb2a`

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
0x18005caf4  mov     rax, rsp
0x18005caf7  mov     [rax+18h], rbx
0x18005cafb  mov     [rax+20h], rsi
0x18005caff  push    rdi
0x18005cb00  sub     rsp, 20h
0x18005cb04  mov     qword ptr [rax+10h], 0
0x18005cb0c  mov     dword ptr [rax+8], 0
0x18005cb13  call    IsRasTlsExt_GetPinUserBlobPresent
0x18005cb18  lea     rsi, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005cb1f  lea     rdi, WPP_GLOBAL_Control
0x18005cb26  test    al, al
0x18005cb28  jz      short loc_18005CB3B
0x18005cb2a  call    cs:__imp_RasTlsExt_GetConfigForceNotDomainJoined
0x18005cb30  test    eax, eax
0x18005cb32  jz      short loc_18005CB58
0x18005cb34  xor     eax, eax
0x18005cb36  jmp     loc_18005CC37
0x18005cb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb42  cmp     rcx, rdi
0x18005cb45  jz      short loc_18005CB58
0x18005cb47  mov     rcx, [rcx+10h]
0x18005cb4b  mov     edx, 37h ; '7'
0x18005cb50  mov     r8, rsi
0x18005cb53  call    WPP_SF_
0x18005cb58  lea     r8, [rsp+28h+BufferType]; BufferType
0x18005cb5d  xor     ecx, ecx; lpServer
0x18005cb5f  lea     rdx, [rsp+28h+NameBuffer]; lpNameBuffer
0x18005cb64  mov     ebx, 1
0x18005cb69  call    cs:__imp_NetGetJoinInformation
0x18005cb6f  test    eax, eax
0x18005cb71  jz      short loc_18005CB9A
0x18005cb73  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb7a  cmp     rcx, rdi
0x18005cb7d  jz      loc_18005CC2A
0x18005cb83  lea     edx, [rbx+37h]
0x18005cb86  mov     r9d, eax
0x18005cb89  mov     rcx, [rcx+10h]
0x18005cb8d  mov     r8, rsi
0x18005cb90  call    WPP_SF_d
0x18005cb95  jmp     loc_18005CC2A
0x18005cb9a  mov     r9d, [rsp+28h+BufferType]
0x18005cb9f  mov     ecx, r9d
0x18005cba2  test    r9d, r9d
0x18005cba5  jz      short loc_18005CC0D
0x18005cba7  sub     ecx, ebx
0x18005cba9  jz      short loc_18005CBEC
0x18005cbab  sub     ecx, ebx
0x18005cbad  jz      short loc_18005CBD9
0x18005cbaf  cmp     ecx, ebx
0x18005cbb1  jz      short loc_18005CBC6
0x18005cbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cbba  cmp     rcx, rdi
0x18005cbbd  jz      short loc_18005CC2A
0x18005cbbf  mov     edx, 3Dh ; '='
0x18005cbc4  jmp     short loc_18005CB89
0x18005cbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cbcd  cmp     rcx, rdi
0x18005cbd0  jz      short loc_18005CC2A
0x18005cbd2  mov     edx, 3Ch ; '<'
0x18005cbd7  jmp     short loc_18005CC1E
0x18005cbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cbe0  cmp     rcx, rdi
0x18005cbe3  jz      short loc_18005CC09
0x18005cbe5  mov     edx, 3Bh ; ';'
0x18005cbea  jmp     short loc_18005CBFD
0x18005cbec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cbf3  cmp     rcx, rdi
0x18005cbf6  jz      short loc_18005CC09
0x18005cbf8  mov     edx, 3Ah ; ':'
0x18005cbfd  mov     rcx, [rcx+10h]
0x18005cc01  mov     r8, rsi
0x18005cc04  call    WPP_SF_
0x18005cc09  xor     ebx, ebx
0x18005cc0b  jmp     short loc_18005CC2A
0x18005cc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc14  cmp     rcx, rdi
0x18005cc17  jz      short loc_18005CC2A
0x18005cc19  mov     edx, 39h ; '9'
0x18005cc1e  mov     rcx, [rcx+10h]
0x18005cc22  mov     r8, rsi
0x18005cc25  call    WPP_SF_
0x18005cc2a  mov     rcx, [rsp+28h+NameBuffer]; Buffer
0x18005cc2f  call    cs:__imp_NetApiBufferFree
0x18005cc35  mov     eax, ebx
0x18005cc37  mov     rbx, [rsp+28h+arg_10]
0x18005cc3c  mov     rsi, [rsp+28h+arg_18]
0x18005cc41  add     rsp, 20h
0x18005cc45  pop     rdi
0x18005cc46  retn
```
