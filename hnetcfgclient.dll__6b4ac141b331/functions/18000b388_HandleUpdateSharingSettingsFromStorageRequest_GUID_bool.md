# HandleUpdateSharingSettingsFromStorageRequest(_GUID,bool)

- ea: `0x18000b388`
- end: `0x18000b561`
- name: `?HandleUpdateSharingSettingsFromStorageRequest@@YAJU_GUID@@_N@Z`
- size: `473`
- prototype: `__int64 __fastcall(GUID *InterfaceGuid, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000ac50`

## callees

- `0x18000a484`
- `0x18000b388`
- `0x18000b664`
- `0x18000c0f0`
- `0x18000c280`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18000b441`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18000b441`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18000b3e0`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18000b3e0`
- `IpNatHlpClient!IpNatHlpUpdateSharingSettingsFromStorage` at `0x18000b4f1`
- `IpNatHlpClient!IpNatHlpUpdateSharingSettingsFromStorage` at `0x18000b4f1`

## pseudocode

```c
__int64 __fastcall HandleUpdateSharingSettingsFromStorageRequest(GUID *InterfaceGuid, __int64 a2, __int64 a3)
{
  char v3; // di
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  NTSTATUS v10; // eax
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int updated; // eax
  ULONG InterfaceIndex; // [rsp+30h] [rbp-38h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF__guid_c(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, InterfaceGuid, (_BYTE)a2);
  }
  InterfaceLuid.Value = 0;
  InterfaceIndex = -1;
  v5 = ConvertInterfaceGuidToLuid(InterfaceGuid, &InterfaceLuid);
  v6 = v5;
  if ( !v5 )
  {
    v10 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
        goto LABEL_40;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      v8 = 28;
      goto LABEL_13;
    }
    if ( v3 )
    {
      v11 = RegSetPublicIndex(InterfaceIndex);
      if ( v11 >= 0 )
        goto LABEL_34;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v13 = 29;
    }
    else
    {
      v11 = RegSetPrivateIndex(InterfaceIndex);
      if ( v11 >= 0 )
        goto LABEL_34;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v13 = 30;
    }
    WPP_SF_d(v12[2], v13, &WPP_f1a7b644f74231a09fdd825cfe4599b4_Traceguids, (unsigned int)v11);
LABEL_34:
    updated = IpNatHlpUpdateSharingSettingsFromStorage();
    v6 = updated;
    if ( updated >= 0 )
    {
LABEL_40:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_41;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_41;
    v8 = 31;
    v9 = (unsigned int)updated;
LABEL_39:
    WPP_SF_d(v7[2], v8, &WPP_f1a7b644f74231a09fdd825cfe4599b4_Traceguids, v9);
    goto LABEL_40;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_40;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 27;
LABEL_13:
    v9 = v6;
    goto LABEL_39;
  }
LABEL_41:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 32, &WPP_f1a7b644f74231a09fdd825cfe4599b4_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000b388  push    rbx
0x18000b38a  push    rbp
0x18000b38b  push    rdi
0x18000b38c  push    r14
0x18000b38e  sub     rsp, 48h
0x18000b392  mov     dil, dl
0x18000b395  mov     rbx, rcx
0x18000b398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b39f  lea     rbp, WPP_GLOBAL_Control
0x18000b3a6  cmp     rcx, rbp
0x18000b3a9  jz      short loc_18000B3C7
0x18000b3ab  test    byte ptr [rcx+1Ch], 8
0x18000b3af  jz      short loc_18000B3C7
0x18000b3b1  cmp     byte ptr [rcx+19h], 6
0x18000b3b5  jb      short loc_18000B3C7
0x18000b3b7  mov     rcx, [rcx+10h]
0x18000b3bb  mov     r9, rbx
0x18000b3be  mov     [rsp+68h+var_48], dl
0x18000b3c2  call    WPP_SF__guid_c
0x18000b3c7  lea     rdx, [rsp+68h+InterfaceLuid]; InterfaceLuid
0x18000b3cc  mov     qword ptr [rsp+68h+InterfaceLuid], 0
0x18000b3d5  mov     rcx, rbx; InterfaceGuid
0x18000b3d8  mov     [rsp+68h+InterfaceIndex], 0FFFFFFFFh
0x18000b3e0  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18000b3e6  lea     r14, WPP_f1a7b644f74231a09fdd825cfe4599b4_Traceguids
0x18000b3ed  mov     ebx, eax
0x18000b3ef  test    eax, eax
0x18000b3f1  jz      short loc_18000B437
0x18000b3f3  jle     short loc_18000B3FE
0x18000b3f5  movzx   ebx, ax
0x18000b3f8  or      ebx, 80070000h
0x18000b3fe  test    ebx, ebx
0x18000b400  jns     loc_18000B529
0x18000b406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b40d  cmp     rcx, rbp
0x18000b410  jz      loc_18000B555
0x18000b416  test    byte ptr [rcx+1Ch], 8
0x18000b41a  jz      loc_18000B530
0x18000b420  cmp     byte ptr [rcx+19h], 2
0x18000b424  jb      loc_18000B530
0x18000b42a  mov     edx, 1Bh
0x18000b42f  mov     r9d, ebx
0x18000b432  jmp     loc_18000B51D
0x18000b437  lea     rdx, [rsp+68h+InterfaceIndex]; InterfaceIndex
0x18000b43c  lea     rcx, [rsp+68h+InterfaceLuid]; InterfaceLuid
0x18000b441  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18000b447  mov     ebx, eax
0x18000b449  test    eax, eax
0x18000b44b  jz      short loc_18000B48B
0x18000b44d  jle     short loc_18000B458
0x18000b44f  movzx   ebx, ax
0x18000b452  or      ebx, 80070000h
0x18000b458  test    ebx, ebx
0x18000b45a  jns     loc_18000B529
0x18000b460  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b467  cmp     rcx, rbp
0x18000b46a  jz      loc_18000B555
0x18000b470  test    byte ptr [rcx+1Ch], 8
0x18000b474  jz      loc_18000B530
0x18000b47a  cmp     byte ptr [rcx+19h], 2
0x18000b47e  jb      loc_18000B530
0x18000b484  mov     edx, 1Ch
0x18000b489  jmp     short loc_18000B42F
0x18000b48b  mov     ecx, [rsp+68h+InterfaceIndex]; unsigned int
0x18000b48f  test    dil, dil
0x18000b492  jz      short loc_18000B4BC
0x18000b494  call    ?RegSetPublicIndex@@YAJK@Z; RegSetPublicIndex(ulong)
0x18000b499  test    eax, eax
0x18000b49b  jns     short loc_18000B4F1
0x18000b49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4a4  cmp     rcx, rbp
0x18000b4a7  jz      short loc_18000B4F1
0x18000b4a9  test    byte ptr [rcx+1Ch], 8
0x18000b4ad  jz      short loc_18000B4F1
0x18000b4af  cmp     byte ptr [rcx+19h], 2
0x18000b4b3  jb      short loc_18000B4F1
0x18000b4b5  mov     edx, 1Dh
0x18000b4ba  jmp     short loc_18000B4E2
0x18000b4bc  call    ?RegSetPrivateIndex@@YAJK@Z; RegSetPrivateIndex(ulong)
0x18000b4c1  test    eax, eax
0x18000b4c3  jns     short loc_18000B4F1
0x18000b4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4cc  cmp     rcx, rbp
0x18000b4cf  jz      short loc_18000B4F1
0x18000b4d1  test    byte ptr [rcx+1Ch], 8
0x18000b4d5  jz      short loc_18000B4F1
0x18000b4d7  cmp     byte ptr [rcx+19h], 2
0x18000b4db  jb      short loc_18000B4F1
0x18000b4dd  mov     edx, 1Eh
0x18000b4e2  mov     rcx, [rcx+10h]
0x18000b4e6  mov     r9d, eax
0x18000b4e9  mov     r8, r14
0x18000b4ec  call    WPP_SF_d
0x18000b4f1  call    cs:__imp_IpNatHlpUpdateSharingSettingsFromStorage
0x18000b4f7  mov     ebx, eax
0x18000b4f9  test    eax, eax
0x18000b4fb  jns     short loc_18000B529
0x18000b4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b504  cmp     rcx, rbp
0x18000b507  jz      short loc_18000B555
0x18000b509  test    byte ptr [rcx+1Ch], 8
0x18000b50d  jz      short loc_18000B530
0x18000b50f  cmp     byte ptr [rcx+19h], 2
0x18000b513  jb      short loc_18000B530
0x18000b515  mov     edx, 1Fh
0x18000b51a  mov     r9d, eax
0x18000b51d  mov     rcx, [rcx+10h]
0x18000b521  mov     r8, r14
0x18000b524  call    WPP_SF_d
0x18000b529  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b530  cmp     rcx, rbp
0x18000b533  jz      short loc_18000B555
0x18000b535  test    byte ptr [rcx+1Ch], 8
0x18000b539  jz      short loc_18000B555
0x18000b53b  cmp     byte ptr [rcx+19h], 6
0x18000b53f  jb      short loc_18000B555
0x18000b541  mov     rcx, [rcx+10h]
0x18000b545  mov     edx, 20h ; ' '
0x18000b54a  mov     r9d, ebx
0x18000b54d  mov     r8, r14
0x18000b550  call    WPP_SF_d
0x18000b555  mov     eax, ebx
0x18000b557  add     rsp, 48h
0x18000b55b  pop     r14
0x18000b55d  pop     rdi
0x18000b55e  pop     rbp
0x18000b55f  pop     rbx
0x18000b560  retn
```
