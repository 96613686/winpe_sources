# ConnectionManager::HrEnsureRegisteredOrDeregisteredWithNsi(int)

- ea: `0x18001b570`
- end: `0x18001b75e`
- name: `?HrEnsureRegisteredOrDeregisteredWithNsi@ConnectionManager@@AEAAJH@Z`
- size: `494`
- prototype: `__int64 __fastcall(ConnectionManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ae98`
- `0x18001bb00`

## callees

- `0x1800052b4`
- `0x18000538c`
- `0x18001b570`
- `0x180032c3c`

## import_xrefs

- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18001b5f0`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18001b5f0`
- `WINNSI!NsiDisconnectFromServer` at `0x18001b72c`
- `WINNSI!NsiDisconnectFromServer` at `0x18001b72c`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x18001b6b8`
- `WINNSI!NsiRpcRegisterChangeNotification` at `0x18001b6b8`
- `WINNSI!NsiConnectToServer` at `0x18001b642`
- `WINNSI!NsiConnectToServer` at `0x18001b642`

## pseudocode

```c
__int64 __fastcall ConnectionManager::HrEnsureRegisteredOrDeregisteredWithNsi(ConnectionManager *this, int a2)
{
  PVOID v4; // rcx
  const wchar_t *v5; // r9
  _QWORD *v6; // rbx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // r9
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r9

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v5 = L"REGISTERED";
    if ( !a2 )
      v5 = L"DEREGISTERED";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v5);
  }
  v6 = (_QWORD *)((char *)this + 216);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 26) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    v11 = NsiConnectToServer(0);
    *((_QWORD *)this + 26) = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
          2147942406LL);
      LOWORD(v8) = 6;
      return (unsigned __int16)v8 | 0x80070000;
    }
    v12 = NsiRpcRegisterChangeNotification(v11, &NPI_MS_NDIS_MODULEID, 0, &OnInfoNotification, 0, 0, (char *)this + 216);
    v8 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        else
          v13 = (unsigned int)v12;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v13);
      }
      goto LABEL_32;
    }
    return 0;
  }
  if ( !*v6 || !*((_QWORD *)this + 26) )
    return 0;
  v7 = NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 26), &NPI_MS_NDIS_MODULEID, 0, *v6);
  v8 = v7;
  if ( v7 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( v7 > 0 )
      v9 = (unsigned __int16)v7 | 0x80070000;
    else
      v9 = (unsigned int)v7;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v9);
  }
  NsiDisconnectFromServer(*((_QWORD *)this + 26));
  *((_QWORD *)this + 26) = 0;
  if ( !v8 )
    return 0;
LABEL_32:
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001b570  push    rbx
0x18001b572  push    rsi
0x18001b573  push    rdi
0x18001b574  push    r15
0x18001b576  sub     rsp, 48h
0x18001b57a  mov     esi, edx
0x18001b57c  mov     rdi, rcx
0x18001b57f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b586  lea     r15, WPP_GLOBAL_Control
0x18001b58d  cmp     rcx, r15
0x18001b590  jz      short loc_18001B5C1
0x18001b592  test    byte ptr [rcx+1Ch], 8
0x18001b596  jz      short loc_18001B5C1
0x18001b598  mov     rcx, [rcx+10h]
0x18001b59c  lea     rax, aDeregistered; "DEREGISTERED"
0x18001b5a3  test    edx, edx
0x18001b5a5  lea     r9, aRegistered; "REGISTERED"
0x18001b5ac  mov     edx, 22h ; '"'
0x18001b5b1  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b5b8  cmovz   r9, rax
0x18001b5bc  call    WPP_SF_S
0x18001b5c1  lea     rbx, [rdi+0D8h]
0x18001b5c8  test    esi, esi
0x18001b5ca  jnz     short loc_18001B631
0x18001b5cc  cmp     qword ptr [rbx], 0
0x18001b5d0  jz      short loc_18001B62A
0x18001b5d2  cmp     qword ptr [rdi+0D0h], 0
0x18001b5da  jz      short loc_18001B62A
0x18001b5dc  mov     rcx, [rdi+0D0h]
0x18001b5e3  mov     r9, [rbx]
0x18001b5e6  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001b5ed  xor     r8d, r8d
0x18001b5f0  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18001b5f6  mov     ebx, eax
0x18001b5f8  test    eax, eax
0x18001b5fa  jz      loc_18001B725
0x18001b600  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b607  cmp     rcx, r15
0x18001b60a  jz      loc_18001B725
0x18001b610  test    byte ptr [rcx+1Ch], 8
0x18001b614  jz      loc_18001B725
0x18001b61a  test    eax, eax
0x18001b61c  jg      loc_18001B705
0x18001b622  mov     r9d, eax
0x18001b625  jmp     loc_18001B710
0x18001b62a  xor     eax, eax
0x18001b62c  jmp     loc_18001B754
0x18001b631  cmp     qword ptr [rdi+0D0h], 0
0x18001b639  jz      short loc_18001B640
0x18001b63b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b640  xor     ecx, ecx
0x18001b642  call    cs:__imp_NsiConnectToServer
0x18001b648  mov     [rdi+0D0h], rax
0x18001b64f  test    rax, rax
0x18001b652  jnz     short loc_18001B689
0x18001b654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b65b  cmp     rcx, r15
0x18001b65e  jz      short loc_18001B67F
0x18001b660  test    byte ptr [rcx+1Ch], 8
0x18001b664  jz      short loc_18001B67F
0x18001b666  mov     rcx, [rcx+10h]
0x18001b66a  lea     edx, [rax+23h]
0x18001b66d  mov     r9d, 80070006h
0x18001b673  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b67a  call    WPP_SF_d
0x18001b67f  mov     ebx, 6
0x18001b684  jmp     loc_18001B745
0x18001b689  mov     rcx, rax
0x18001b68c  test    esi, esi
0x18001b68e  jz      loc_18001B5E3
0x18001b694  mov     [rsp+68h+var_38], rbx
0x18001b699  lea     r9, ?OnInfoNotification@@YAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z; OnInfoNotification(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)
0x18001b6a0  mov     [rsp+68h+var_40], 0
0x18001b6a9  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001b6b0  xor     r8d, r8d
0x18001b6b3  mov     [rsp+68h+var_48], 0
0x18001b6b8  call    cs:__imp_NsiRpcRegisterChangeNotification
0x18001b6be  mov     ebx, eax
0x18001b6c0  test    eax, eax
0x18001b6c2  jz      loc_18001B750
0x18001b6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6cf  cmp     rcx, r15
0x18001b6d2  jz      short loc_18001B741
0x18001b6d4  test    byte ptr [rcx+1Ch], 8
0x18001b6d8  jz      short loc_18001B741
0x18001b6da  test    eax, eax
0x18001b6dc  jg      short loc_18001B6E3
0x18001b6de  mov     r9d, eax
0x18001b6e1  jmp     short loc_18001B6EE
0x18001b6e3  movzx   r9d, ax
0x18001b6e7  or      r9d, 80070000h
0x18001b6ee  mov     rcx, [rcx+10h]
0x18001b6f2  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b6f9  mov     edx, 24h ; '$'
0x18001b6fe  call    WPP_SF_d
0x18001b703  jmp     short loc_18001B741
0x18001b705  movzx   r9d, bx
0x18001b709  or      r9d, 80070000h
0x18001b710  mov     rcx, [rcx+10h]
0x18001b714  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001b71b  mov     edx, 25h ; '%'
0x18001b720  call    WPP_SF_d
0x18001b725  mov     rcx, [rdi+0D0h]
0x18001b72c  call    cs:__imp_NsiDisconnectFromServer
0x18001b732  mov     qword ptr [rdi+0D0h], 0
0x18001b73d  test    ebx, ebx
0x18001b73f  jz      short loc_18001B750
0x18001b741  test    ebx, ebx
0x18001b743  jle     short loc_18001B752
0x18001b745  movzx   ebx, bx
0x18001b748  or      ebx, 80070000h
0x18001b74e  jmp     short loc_18001B752
0x18001b750  xor     ebx, ebx
0x18001b752  mov     eax, ebx
0x18001b754  add     rsp, 48h
0x18001b758  pop     r15
0x18001b75a  pop     rdi
0x18001b75b  pop     rsi
0x18001b75c  pop     rbx
0x18001b75d  retn
```
