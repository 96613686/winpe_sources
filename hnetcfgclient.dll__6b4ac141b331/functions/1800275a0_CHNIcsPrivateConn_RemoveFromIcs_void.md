# CHNIcsPrivateConn::RemoveFromIcs(void)

- ea: `0x1800275a0`
- end: `0x18002784d`
- name: `?RemoveFromIcs@CHNIcsPrivateConn@@UEAAJXZ`
- size: `685`
- prototype: `__int64 __fastcall(CHNIcsPrivateConn *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001b1e8`
- `0x18001e7f0`
- `0x18001e954`
- `0x18001ee3c`
- `0x180021458`
- `0x1800275a0`
- `0x18002a61c`
- `0x18002ad0c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800277fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800277fd`

## pseudocode

```c
__int64 __fastcall CHNIcsPrivateConn::RemoveFromIcs(CHNIcsPrivateConn *this)
{
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  int ConnectionPropertiesObject; // eax
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  unsigned __int16 *v12; // rdx
  struct IWbemServices *v13; // rcx
  int updated; // eax
  struct _GUID v16; // [rsp+30h] [rbp-28h] BYREF
  struct IWbemClassObject *v17; // [rsp+60h] [rbp+8h] BYREF
  struct _GUID *v18; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2d99a37c167230046a8df7b771a1270b_Traceguids);
  }
  v17 = 0;
  if ( !CHNetConn::ProhibitedByPolicy((CHNIcsPrivateConn *)((char *)this - 152), 0x32u) )
  {
    ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject(
                                   (CHNIcsPrivateConn *)((char *)this - 152),
                                   &v17);
    v2 = ConnectionPropertiesObject;
    if ( ConnectionPropertiesObject < 0 )
    {
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_45;
      v4 = 12;
      v5 = (unsigned int)ConnectionPropertiesObject;
      goto LABEL_10;
    }
    if ( ConnectionPropertiesObject )
      goto LABEL_44;
    v7 = SetBooleanValue(v17, L"IsIcsPrivate", 0);
    v2 = v7;
    if ( v7 >= 0 )
    {
      if ( !v7 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64))(**((_QWORD **)this - 11) + 112LL))(
               *((_QWORD *)this - 11),
               v17,
               1);
        v2 = v7;
        if ( v7 >= 0 )
        {
          if ( !v7 )
            CHNetConn::UpdateNetman((CHNIcsPrivateConn *)((char *)this - 152));
          goto LABEL_31;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 14;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 13;
LABEL_28:
        WPP_SF_d(v8[2], v9, WPP_2d99a37c167230046a8df7b771a1270b_Traceguids, (unsigned int)v7);
      }
    }
LABEL_31:
    ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v17);
    if ( !v2 )
    {
      v10 = *((_QWORD *)this - 19);
      v18 = 0;
      v11 = (*(__int64 (__fastcall **)(char *, struct _GUID **))(v10 + 32))((char *)this - 152, &v18);
      if ( v11 >= 0 )
      {
        v12 = (unsigned __int16 *)*((_QWORD *)this - 4);
        v13 = (struct IWbemServices *)*((_QWORD *)this - 11);
        v16 = *v18;
        updated = UpdateSharedAccessServicePerSettings(v13, v12, &v16, 0);
        if ( updated < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_2d99a37c167230046a8df7b771a1270b_Traceguids,
            (unsigned int)updated);
        }
        CHNetConn::RefreshNetConnectionsUI((CHNIcsPrivateConn *)((char *)this - 152), 0);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_2d99a37c167230046a8df7b771a1270b_Traceguids,
          (unsigned int)v11);
      }
      Sleep(0x5DCu);
      CHNetConn::RestoreIpConfiguration((CHNIcsPrivateConn *)((char *)this - 152));
    }
    goto LABEL_44;
  }
  v2 = -2147024891;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = 11;
    v5 = 2147942405LL;
LABEL_10:
    WPP_SF_d(v3[2], v4, WPP_2d99a37c167230046a8df7b771a1270b_Traceguids, v5);
LABEL_44:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_45:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 && *((_BYTE *)v3 + 25) >= 6u )
    WPP_SF_d(v3[2], 17, WPP_2d99a37c167230046a8df7b771a1270b_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800275a0  mov     [rsp+arg_10], rbx
0x1800275a5  mov     [rsp+arg_18], rsi
0x1800275aa  push    rdi
0x1800275ab  push    r12
0x1800275ad  push    r15
0x1800275af  sub     rsp, 40h
0x1800275b3  mov     rsi, rcx
0x1800275b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275bd  lea     r15, WPP_GLOBAL_Control
0x1800275c4  lea     r12, WPP_2d99a37c167230046a8df7b771a1270b_Traceguids
0x1800275cb  cmp     rcx, r15
0x1800275ce  jz      short loc_1800275ED
0x1800275d0  test    byte ptr [rcx+1Ch], 8
0x1800275d4  jz      short loc_1800275ED
0x1800275d6  cmp     byte ptr [rcx+19h], 6
0x1800275da  jb      short loc_1800275ED
0x1800275dc  mov     rcx, [rcx+10h]
0x1800275e0  mov     edx, 0Ah
0x1800275e5  mov     r8, r12
0x1800275e8  call    WPP_SF_
0x1800275ed  lea     rdi, [rsi-98h]
0x1800275f4  mov     [rsp+58h+arg_0], 0
0x1800275fd  mov     rcx, rdi; this
0x180027600  mov     edx, 32h ; '2'; unsigned int
0x180027605  call    ?ProhibitedByPolicy@CHNetConn@@IEAAEK@Z; CHNetConn::ProhibitedByPolicy(ulong)
0x18002760a  test    al, al
0x18002760c  jz      short loc_180027650
0x18002760e  mov     ebx, 80070005h
0x180027613  mov     rcx, cs:WPP_GLOBAL_Control
0x18002761a  cmp     rcx, r15
0x18002761d  jz      loc_180027837
0x180027623  test    byte ptr [rcx+1Ch], 8
0x180027627  jz      loc_180027812
0x18002762d  cmp     byte ptr [rcx+19h], 2
0x180027631  jb      loc_180027812
0x180027637  mov     edx, 0Bh
0x18002763c  mov     r9d, ebx
0x18002763f  mov     rcx, [rcx+10h]
0x180027643  mov     r8, r12
0x180027646  call    WPP_SF_d
0x18002764b  jmp     loc_18002780B
0x180027650  lea     rdx, [rsp+58h+arg_0]; struct IWbemClassObject **
0x180027655  mov     rcx, rdi; this
0x180027658  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x18002765d  mov     ebx, eax
0x18002765f  test    eax, eax
0x180027661  jns     short loc_180027691
0x180027663  mov     rcx, cs:WPP_GLOBAL_Control
0x18002766a  cmp     rcx, r15
0x18002766d  jz      loc_180027837
0x180027673  test    byte ptr [rcx+1Ch], 8
0x180027677  jz      loc_180027812
0x18002767d  cmp     byte ptr [rcx+19h], 2
0x180027681  jb      loc_180027812
0x180027687  mov     edx, 0Ch
0x18002768c  mov     r9d, eax
0x18002768f  jmp     short loc_18002763F
0x180027691  jnz     loc_18002780B
0x180027697  mov     rcx, [rsp+58h+arg_0]; struct IWbemClassObject *
0x18002769c  lea     rdx, ?c_wszIsIcsPrivate@@3QBGB; "IsIcsPrivate"
0x1800276a3  xor     r8d, r8d; unsigned __int8
0x1800276a6  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x1800276ab  mov     ebx, eax
0x1800276ad  test    eax, eax
0x1800276af  jns     short loc_1800276D0
0x1800276b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276b8  cmp     rcx, r15
0x1800276bb  jz      short loc_180027735
0x1800276bd  test    byte ptr [rcx+1Ch], 8
0x1800276c1  jz      short loc_180027735
0x1800276c3  cmp     byte ptr [rcx+19h], 2
0x1800276c7  jb      short loc_180027735
0x1800276c9  mov     edx, 0Dh
0x1800276ce  jmp     short loc_18002771A
0x1800276d0  jnz     short loc_180027735
0x1800276d2  mov     rcx, [rsi-58h]
0x1800276d6  xor     r9d, r9d
0x1800276d9  mov     rdx, [rsp+58h+arg_0]
0x1800276de  mov     [rsp+58h+var_38], 0
0x1800276e7  mov     rax, [rcx]
0x1800276ea  lea     r8d, [r9+1]
0x1800276ee  mov     rax, [rax+70h]
0x1800276f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276f7  mov     ebx, eax
0x1800276f9  test    eax, eax
0x1800276fb  jns     short loc_18002772B
0x1800276fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180027704  cmp     rcx, r15
0x180027707  jz      short loc_180027735
0x180027709  test    byte ptr [rcx+1Ch], 8
0x18002770d  jz      short loc_180027735
0x18002770f  cmp     byte ptr [rcx+19h], 2
0x180027713  jb      short loc_180027735
0x180027715  mov     edx, 0Eh
0x18002771a  mov     rcx, [rcx+10h]
0x18002771e  mov     r9d, eax
0x180027721  mov     r8, r12
0x180027724  call    WPP_SF_d
0x180027729  jmp     short loc_180027735
0x18002772b  jnz     short loc_180027735
0x18002772d  mov     rcx, rdi; this
0x180027730  call    ?UpdateNetman@CHNetConn@@IEAAJXZ; CHNetConn::UpdateNetman(void)
0x180027735  mov     rcx, [rsp+58h+arg_0]
0x18002773a  mov     rax, [rcx]
0x18002773d  mov     rax, [rax+10h]
0x180027741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027746  test    ebx, ebx
0x180027748  jnz     loc_18002780B
0x18002774e  mov     rax, [rdi]
0x180027751  lea     rdx, [rsp+58h+arg_8]
0x180027756  mov     rcx, rdi
0x180027759  mov     [rsp+58h+arg_8], 0
0x180027762  mov     rax, [rax+20h]
0x180027766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776b  test    eax, eax
0x18002776d  jns     short loc_18002779B
0x18002776f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027776  cmp     rcx, r15
0x180027779  jz      short loc_1800277F8
0x18002777b  test    byte ptr [rcx+1Ch], 8
0x18002777f  jz      short loc_1800277F8
0x180027781  cmp     byte ptr [rcx+19h], 2
0x180027785  jb      short loc_1800277F8
0x180027787  mov     rcx, [rcx+10h]
0x18002778b  lea     edx, [rbx+0Fh]
0x18002778e  mov     r9d, eax
0x180027791  mov     r8, r12
0x180027794  call    WPP_SF_d
0x180027799  jmp     short loc_1800277F8
0x18002779b  mov     rax, [rsp+58h+arg_8]
0x1800277a0  lea     r8, [rsp+58h+var_28]; struct _GUID
0x1800277a5  mov     rdx, [rsi-20h]; unsigned __int16 *
0x1800277a9  xor     r9d, r9d; bool
0x1800277ac  mov     rcx, [rsi-58h]; struct IWbemServices *
0x1800277b0  movups  xmm0, xmmword ptr [rax]
0x1800277b3  movdqu  xmmword ptr [rsp+58h+var_28.Data1], xmm0
0x1800277b9  call    ?UpdateSharedAccessServicePerSettings@@YAJPEAUIWbemServices@@PEAGU_GUID@@_N@Z; UpdateSharedAccessServicePerSettings(IWbemServices *,ushort *,_GUID,bool)
0x1800277be  test    eax, eax
0x1800277c0  jns     short loc_1800277EE
0x1800277c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277c9  cmp     rcx, r15
0x1800277cc  jz      short loc_1800277EE
0x1800277ce  test    byte ptr [rcx+1Ch], 8
0x1800277d2  jz      short loc_1800277EE
0x1800277d4  cmp     byte ptr [rcx+19h], 2
0x1800277d8  jb      short loc_1800277EE
0x1800277da  mov     rcx, [rcx+10h]
0x1800277de  mov     edx, 10h
0x1800277e3  mov     r9d, eax
0x1800277e6  mov     r8, r12
0x1800277e9  call    WPP_SF_d
0x1800277ee  xor     edx, edx; int
0x1800277f0  mov     rcx, rdi; this
0x1800277f3  call    ?RefreshNetConnectionsUI@CHNetConn@@IEAAJH@Z; CHNetConn::RefreshNetConnectionsUI(int)
0x1800277f8  mov     ecx, 5DCh; dwMilliseconds
0x1800277fd  call    cs:__imp_Sleep
0x180027803  mov     rcx, rdi; this
0x180027806  call    ?RestoreIpConfiguration@CHNetConn@@IEAAJXZ; CHNetConn::RestoreIpConfiguration(void)
0x18002780b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027812  cmp     rcx, r15
0x180027815  jz      short loc_180027837
0x180027817  test    byte ptr [rcx+1Ch], 8
0x18002781b  jz      short loc_180027837
0x18002781d  cmp     byte ptr [rcx+19h], 6
0x180027821  jb      short loc_180027837
0x180027823  mov     rcx, [rcx+10h]
0x180027827  mov     edx, 11h
0x18002782c  mov     r9d, ebx
0x18002782f  mov     r8, r12
0x180027832  call    WPP_SF_d
0x180027837  mov     rsi, [rsp+58h+arg_18]
0x18002783c  mov     eax, ebx
0x18002783e  mov     rbx, [rsp+58h+arg_10]
0x180027843  add     rsp, 40h
0x180027847  pop     r15
0x180027849  pop     r12
0x18002784b  pop     rdi
0x18002784c  retn
```
