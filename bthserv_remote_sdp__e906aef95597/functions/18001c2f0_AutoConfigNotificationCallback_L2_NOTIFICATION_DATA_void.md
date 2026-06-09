# AutoConfigNotificationCallback(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x18001c2f0`
- end: `0x18001c711`
- name: `?AutoConfigNotificationCallback@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `1057`
- prototype: `void __stdcall(PWLAN_NOTIFICATION_DATA, PVOID)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x18001c2f0`
- `0x18001d754`
- `0x18001db00`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001c6a4`
- `wlanapi!WlanFreeMemory` at `0x18001c6a4`
- `wlanapi!WlanEnumInterfaces` at `0x18001c47b`
- `wlanapi!WlanEnumInterfaces` at `0x18001c47b`

## pseudocode

```c
void __fastcall AutoConfigNotificationCallback(PWLAN_NOTIFICATION_DATA a1, PVOID a2)
{
  PWLAN_INTERFACE_INFO_LIST v2; // r8
  _BYTE *v4; // rcx
  char v5; // bl
  bool v6; // dl
  int v7; // r8d
  _QWORD *v8; // r10
  bool v9; // cl
  int v10; // edx
  bool v11; // dl
  int v12; // edx
  int v13; // r8d
  _BYTE *v14; // rcx
  bool v15; // r10
  _UNKNOWN **v16; // r9
  int v17; // edx
  GUID *v18; // rdx
  bool v19; // al
  bool v20; // al
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  ppInterfaceList = 0;
  v4 = WPP_GLOBAL_Control;
  v5 = 1;
  v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = ppInterfaceList;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1->NotificationSource != 8 )
  {
    if ( a1->NotificationSource != 16 )
      goto LABEL_70;
    if ( a1->NotificationCode != 6 )
      goto LABEL_71;
    *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
    v8 = WPP_GLOBAL_Control;
    v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_70;
    v10 = *((unsigned __int8 *)pInterfaceGuid + 120);
LABEL_69:
    LOBYTE(v10) = v9;
    WPP_RECORDER_AND_TRACE_SF_sD(v8[2], v10, v7, v8[5]);
    goto LABEL_70;
  }
  switch ( a1->NotificationCode )
  {
    case 0xAu:
      *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
      v8 = WPP_GLOBAL_Control;
      v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        break;
      v10 = *((unsigned __int8 *)pInterfaceGuid + 120);
      goto LABEL_69;
    case 0xDu:
    case 0xEu:
      if ( WlanEnumInterfaces(*((HANDLE *)pInterfaceGuid + 12), 0, &ppInterfaceList) )
      {
        LOBYTE(v12) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
        *((_DWORD *)pInterfaceGuid + 28) = 0;
      }
      else
      {
        *((_DWORD *)pInterfaceGuid + 28) = ppInterfaceList->dwNumberOfItems;
        v14 = WPP_GLOBAL_Control;
        v15 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        v16 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
        if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = *((_DWORD *)pInterfaceGuid + 28);
          LOBYTE(v17) = v15;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
          v14 = WPP_GLOBAL_Control;
          v16 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
        }
        v18 = (GUID *)pInterfaceGuid;
        if ( *((_DWORD *)pInterfaceGuid + 28) == 1 )
        {
          v19 = v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 4u;
          if ( v19 || v16 != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_s(
              *((_QWORD *)v14 + 2),
              v19,
              v16 != &WPP_RECORDER_INITIALIZED,
              *((_QWORD *)v14 + 5));
            v18 = (GUID *)pInterfaceGuid;
          }
          *v18 = ppInterfaceList->InterfaceInfo[0].InterfaceGuid;
          *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
        }
        else
        {
          v20 = v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 4u;
          if ( v20 || v16 != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_s(
              *((_QWORD *)v14 + 2),
              v20,
              v16 != &WPP_RECORDER_INITIALIZED,
              *((_QWORD *)v14 + 5));
            v18 = (GUID *)pInterfaceGuid;
          }
          *v18 = 0;
          *((_BYTE *)pInterfaceGuid + 120) = 0;
        }
      }
      break;
    case 0x15u:
      *((_BYTE *)pInterfaceGuid + 120) = 0;
      v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      break;
    default:
      goto LABEL_71;
  }
LABEL_70:
  ProcessNotification();
  v2 = ppInterfaceList;
  v4 = WPP_GLOBAL_Control;
LABEL_71:
  if ( v2 )
  {
    WlanFreeMemory(v2);
    ppInterfaceList = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 4u )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v4 + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
}

```

## disassembly

```asm
0x18001c2f0  mov     [rsp+arg_8], rbx
0x18001c2f5  mov     [rsp+arg_10], rdi
0x18001c2fa  push    r12
0x18001c2fc  push    r14
0x18001c2fe  push    r15
0x18001c300  sub     rsp, 50h
0x18001c304  xor     r8d, r8d
0x18001c307  mov     rdi, rcx
0x18001c30a  mov     [rsp+68h+ppInterfaceList], r8
0x18001c30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c316  lea     r14, WPP_GLOBAL_Control
0x18001c31d  lea     ebx, [r8+1]
0x18001c321  cmp     rcx, r14
0x18001c324  jz      short loc_18001C330
0x18001c326  cmp     byte ptr [rcx+19h], 4
0x18001c32a  jb      short loc_18001C330
0x18001c32c  mov     dl, bl
0x18001c32e  jmp     short loc_18001C332
0x18001c330  xor     dl, dl
0x18001c332  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c339  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c340  lea     r12, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001c347  setnz   al
0x18001c34a  test    dl, dl
0x18001c34c  jnz     short loc_18001C352
0x18001c34e  test    al, al
0x18001c350  jz      short loc_18001C37A
0x18001c352  mov     r9, [rcx+28h]
0x18001c356  mov     r8b, al
0x18001c359  mov     rcx, [rcx+10h]
0x18001c35d  mov     [rsp+68h+var_30], r12
0x18001c362  mov     [rsp+68h+var_38], 21h ; '!'
0x18001c369  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c36e  mov     r8, [rsp+68h+ppInterfaceList]
0x18001c373  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c37a  cmp     dword ptr [rdi], 8
0x18001c37d  jz      short loc_18001C3F2
0x18001c37f  cmp     dword ptr [rdi], 10h
0x18001c382  jnz     loc_18001C68B
0x18001c388  cmp     dword ptr [rdi+4], 6
0x18001c38c  jnz     loc_18001C69C
0x18001c392  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001c397  mov     rcx, cs:pInterfaceGuid
0x18001c39e  mov     [rcx+78h], al
0x18001c3a1  mov     r10, cs:WPP_GLOBAL_Control
0x18001c3a8  cmp     r10, r14
0x18001c3ab  jz      short loc_18001C3B8
0x18001c3ad  cmp     byte ptr [r10+19h], 4
0x18001c3b2  jb      short loc_18001C3B8
0x18001c3b4  mov     cl, bl
0x18001c3b6  jmp     short loc_18001C3BA
0x18001c3b8  xor     cl, cl
0x18001c3ba  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c3c1  setnz   r8b
0x18001c3c5  test    cl, cl
0x18001c3c7  jnz     short loc_18001C3D2
0x18001c3c9  test    r8b, r8b
0x18001c3cc  jz      loc_18001C68B
0x18001c3d2  mov     rax, cs:pInterfaceGuid
0x18001c3d9  movzx   edx, byte ptr [rax+78h]
0x18001c3dd  mov     [rsp+68h+var_20], edx
0x18001c3e1  mov     [rsp+68h+var_30], r12
0x18001c3e6  mov     [rsp+68h+var_38], 28h ; '('
0x18001c3ed  jmp     loc_18001C67C
0x18001c3f2  mov     edx, [rdi+4]
0x18001c3f5  sub     edx, 0Ah
0x18001c3f8  jz      loc_18001C625
0x18001c3fe  sub     edx, 3
0x18001c401  jz      short loc_18001C469
0x18001c403  sub     edx, ebx
0x18001c405  jz      short loc_18001C469
0x18001c407  cmp     edx, 7
0x18001c40a  jnz     loc_18001C69C
0x18001c410  mov     rax, cs:pInterfaceGuid
0x18001c417  mov     byte ptr [rax+78h], 0
0x18001c41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c422  cmp     rcx, r14
0x18001c425  jz      short loc_18001C431
0x18001c427  cmp     byte ptr [rcx+19h], 4
0x18001c42b  jb      short loc_18001C431
0x18001c42d  mov     dl, bl
0x18001c42f  jmp     short loc_18001C433
0x18001c431  xor     dl, dl
0x18001c433  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c43a  setnz   r8b
0x18001c43e  test    dl, dl
0x18001c440  jnz     short loc_18001C44B
0x18001c442  test    r8b, r8b
0x18001c445  jz      loc_18001C68B
0x18001c44b  mov     r9, [rcx+28h]
0x18001c44f  mov     rcx, [rcx+10h]
0x18001c453  mov     [rsp+68h+var_30], r12
0x18001c458  mov     [rsp+68h+var_38], 23h ; '#'
0x18001c45f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c464  jmp     loc_18001C68B
0x18001c469  mov     rcx, cs:pInterfaceGuid
0x18001c470  lea     r8, [rsp+68h+ppInterfaceList]; ppInterfaceList
0x18001c475  xor     edx, edx; pReserved
0x18001c477  mov     rcx, [rcx+60h]; hClientHandle
0x18001c47b  call    cs:__imp_WlanEnumInterfaces
0x18001c482  nop     dword ptr [rax+rax+00h]
0x18001c487  test    eax, eax
0x18001c489  jz      short loc_18001C4E4
0x18001c48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c492  cmp     rcx, r14
0x18001c495  jz      short loc_18001C4A1
0x18001c497  cmp     byte ptr [rcx+19h], 3
0x18001c49b  jb      short loc_18001C4A1
0x18001c49d  mov     dl, bl
0x18001c49f  jmp     short loc_18001C4A3
0x18001c4a1  xor     dl, dl
0x18001c4a3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c4aa  setnz   r8b
0x18001c4ae  test    dl, dl
0x18001c4b0  jnz     short loc_18001C4B7
0x18001c4b2  test    r8b, r8b
0x18001c4b5  jz      short loc_18001C4D4
0x18001c4b7  mov     r9, [rcx+28h]
0x18001c4bb  mov     rcx, [rcx+10h]
0x18001c4bf  mov     [rsp+68h+var_20], eax
0x18001c4c3  mov     [rsp+68h+var_30], r12
0x18001c4c8  mov     [rsp+68h+var_38], 24h ; '$'
0x18001c4cf  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001c4d4  mov     rax, cs:pInterfaceGuid
0x18001c4db  and     dword ptr [rax+70h], 0
0x18001c4df  jmp     loc_18001C68B
0x18001c4e4  mov     rax, [rsp+68h+ppInterfaceList]
0x18001c4e9  mov     ecx, [rax]
0x18001c4eb  mov     rax, cs:pInterfaceGuid
0x18001c4f2  mov     [rax+70h], ecx
0x18001c4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4fc  cmp     rcx, r14
0x18001c4ff  jz      short loc_18001C50C
0x18001c501  cmp     byte ptr [rcx+19h], 4
0x18001c505  jb      short loc_18001C50C
0x18001c507  mov     r10b, bl
0x18001c50a  jmp     short loc_18001C50F
0x18001c50c  xor     r10b, r10b
0x18001c50f  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18001c516  cmp     r9, r15
0x18001c519  setnz   r8b
0x18001c51d  test    r10b, r10b
0x18001c520  jnz     short loc_18001C527
0x18001c522  test    r8b, r8b
0x18001c525  jz      short loc_18001C55F
0x18001c527  mov     rax, cs:pInterfaceGuid
0x18001c52e  mov     r9, [rcx+28h]
0x18001c532  mov     rcx, [rcx+10h]
0x18001c536  mov     edx, [rax+70h]
0x18001c539  mov     [rsp+68h+var_20], edx
0x18001c53d  mov     dl, r10b
0x18001c540  mov     [rsp+68h+var_30], r12
0x18001c545  mov     [rsp+68h+var_38], 25h ; '%'
0x18001c54c  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001c551  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c558  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18001c55f  mov     rdx, cs:pInterfaceGuid
0x18001c566  cmp     [rdx+70h], ebx
0x18001c569  jnz     short loc_18001C5CF
0x18001c56b  cmp     rcx, r14
0x18001c56e  jz      short loc_18001C57A
0x18001c570  cmp     byte ptr [rcx+19h], 4
0x18001c574  jb      short loc_18001C57A
0x18001c576  mov     al, bl
0x18001c578  jmp     short loc_18001C57C
0x18001c57a  xor     al, al
0x18001c57c  cmp     r9, r15
0x18001c57f  setnz   r8b
0x18001c583  test    al, al
0x18001c585  jnz     short loc_18001C58C
0x18001c587  test    r8b, r8b
0x18001c58a  jz      short loc_18001C5AE
0x18001c58c  mov     r9, [rcx+28h]
0x18001c590  mov     dl, al
0x18001c592  mov     rcx, [rcx+10h]
0x18001c596  mov     [rsp+68h+var_30], r12
0x18001c59b  mov     [rsp+68h+var_38], 26h ; '&'
0x18001c5a2  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c5a7  mov     rdx, cs:pInterfaceGuid
0x18001c5ae  mov     rax, [rsp+68h+ppInterfaceList]
0x18001c5b3  movups  xmm0, xmmword ptr [rax+8]
0x18001c5b7  movdqu  xmmword ptr [rdx], xmm0
0x18001c5bb  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001c5c0  mov     rcx, cs:pInterfaceGuid
0x18001c5c7  mov     [rcx+78h], al
0x18001c5ca  jmp     loc_18001C68B
0x18001c5cf  cmp     rcx, r14
0x18001c5d2  jz      short loc_18001C5DE
0x18001c5d4  cmp     byte ptr [rcx+19h], 4
0x18001c5d8  jb      short loc_18001C5DE
0x18001c5da  mov     al, bl
0x18001c5dc  jmp     short loc_18001C5E0
0x18001c5de  xor     al, al
0x18001c5e0  cmp     r9, r15
0x18001c5e3  setnz   r8b
0x18001c5e7  test    al, al
0x18001c5e9  jnz     short loc_18001C5F0
0x18001c5eb  test    r8b, r8b
0x18001c5ee  jz      short loc_18001C612
0x18001c5f0  mov     r9, [rcx+28h]
0x18001c5f4  mov     dl, al
0x18001c5f6  mov     rcx, [rcx+10h]
0x18001c5fa  mov     [rsp+68h+var_30], r12
0x18001c5ff  mov     [rsp+68h+var_38], 27h ; '''
0x18001c606  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c60b  mov     rdx, cs:pInterfaceGuid
0x18001c612  xorps   xmm0, xmm0
0x18001c615  movups  xmmword ptr [rdx], xmm0
0x18001c618  mov     rax, cs:pInterfaceGuid
0x18001c61f  mov     byte ptr [rax+78h], 0
0x18001c623  jmp     short loc_18001C68B
0x18001c625  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001c62a  mov     rcx, cs:pInterfaceGuid
0x18001c631  mov     [rcx+78h], al
0x18001c634  mov     r10, cs:WPP_GLOBAL_Control
0x18001c63b  cmp     r10, r14
0x18001c63e  jz      short loc_18001C64B
0x18001c640  cmp     byte ptr [r10+19h], 4
0x18001c645  jb      short loc_18001C64B
0x18001c647  mov     cl, bl
0x18001c649  jmp     short loc_18001C64D
0x18001c64b  xor     cl, cl
0x18001c64d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c654  setnz   r8b
0x18001c658  test    cl, cl
0x18001c65a  jnz     short loc_18001C661
0x18001c65c  test    r8b, r8b
0x18001c65f  jz      short loc_18001C68B
0x18001c661  mov     rax, cs:pInterfaceGuid
0x18001c668  movzx   edx, byte ptr [rax+78h]
0x18001c66c  mov     [rsp+68h+var_20], edx
0x18001c670  mov     [rsp+68h+var_30], r12
0x18001c675  mov     [rsp+68h+var_38], 22h ; '"'
0x18001c67c  mov     r9, [r10+28h]
0x18001c680  mov     dl, cl
0x18001c682  mov     rcx, [r10+10h]
0x18001c686  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001c68b  call    ?ProcessNotification@@YAXXZ; ProcessNotification(void)
0x18001c690  mov     r8, [rsp+68h+ppInterfaceList]
0x18001c695  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c69c  test    r8, r8
0x18001c69f  jz      short loc_18001C6BD
0x18001c6a1  mov     rcx, r8; pMemory
0x18001c6a4  call    cs:__imp_WlanFreeMemory
0x18001c6ab  nop     dword ptr [rax+rax+00h]
0x18001c6b0  and     [rsp+68h+ppInterfaceList], 0
0x18001c6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6bd  cmp     rcx, r14
0x18001c6c0  jz      short loc_18001C6C8
0x18001c6c2  cmp     byte ptr [rcx+19h], 4
0x18001c6c6  jnb     short loc_18001C6CA
0x18001c6c8  xor     bl, bl
0x18001c6ca  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c6d1  setnz   r8b
0x18001c6d5  test    bl, bl
0x18001c6d7  jnz     short loc_18001C6DE
0x18001c6d9  test    r8b, r8b
0x18001c6dc  jz      short loc_18001C6F9
0x18001c6de  mov     r9, [rcx+28h]
0x18001c6e2  mov     dl, bl
0x18001c6e4  mov     rcx, [rcx+10h]
0x18001c6e8  mov     [rsp+68h+var_30], r12
0x18001c6ed  mov     [rsp+68h+var_38], 29h ; ')'
0x18001c6f4  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c6f9  lea     r11, [rsp+68h+var_18]
0x18001c6fe  mov     rbx, [r11+28h]
0x18001c702  mov     rdi, [r11+30h]
0x18001c706  mov     rsp, r11
0x18001c709  pop     r15
0x18001c70b  pop     r14
0x18001c70d  pop     r12
0x18001c70f  retn
```
