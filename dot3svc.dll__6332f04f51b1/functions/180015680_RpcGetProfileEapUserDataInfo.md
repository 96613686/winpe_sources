# RpcGetProfileEapUserDataInfo

- ea: `0x180015680`
- end: `0x180015947`
- name: `RpcGetProfileEapUserDataInfo`
- size: `711`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, int, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000c95c`
- `0x180014d14`
- `0x180015680`
- `0x18001fc54`
- `0x180020844`
- `0x180020da4`
- `0x180027da8`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800158ea`
- `MobileNetworking!RaQueryRpcClientToken` at `0x1800156f0`
- `MobileNetworking!RaQueryRpcClientToken` at `0x1800156f0`

## pseudocode

```c
__int64 __fastcall RpcGetProfileEapUserDataInfo(__int64 a1, struct _GUID *a2, int a3, unsigned int *a4)
{
  unsigned int RpcClientToken; // ebx
  const unsigned __int16 *v8; // rdx
  unsigned int Profile; // eax
  void *v10; // rdx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // r9
  __int64 *v16; // rdx
  unsigned int UserDataProperties; // eax
  unsigned int v19; // [rsp+30h] [rbp-28h] BYREF
  void *lpMem; // [rsp+38h] [rbp-20h] BYREF
  struct _PM_PROFILE *v21; // [rsp+40h] [rbp-18h] BYREF
  HANDLE hObject[2]; // [rsp+48h] [rbp-10h] BYREF

  hObject[0] = 0;
  v19 = 0;
  lpMem = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 89, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
  }
  RpcClientToken = RaQueryRpcClientToken(hObject);
  if ( RpcClientToken )
    goto LABEL_43;
  if ( !a4 || a3 )
  {
    RpcClientToken = 87;
    goto LABEL_40;
  }
  if ( !g_bRpcServerStarted )
  {
    RpcClientToken = 1722;
    goto LABEL_43;
  }
  if ( !(unsigned int)Dot3AcmIsAPIAllowed(a2) )
  {
    RpcClientToken = 50;
    goto LABEL_43;
  }
  Profile = PmGetProfile(a2, v8, &v21);
  RpcClientToken = Profile;
  if ( Profile )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_41;
    }
    v12 = 90;
    goto LABEL_17;
  }
  if ( a2 )
  {
    v13 = Dot3AcmQueryUserDataByGuid(a2, v10, &v19, (unsigned __int8 **)&lpMem);
    RpcClientToken = v13;
    if ( v13 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 91, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v13);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) == 0 )
        goto LABEL_41;
      v15 = 1839;
      v16 = QueryUserDataByGuidFailed;
LABEL_26:
      McTemplateU0qqq_EtwEventWriteTransfer(v11, v16, RpcClientToken, v15);
      goto LABEL_40;
    }
LABEL_32:
    UserDataProperties = AcmQueryUserDataProperties(
                           *((struct _DOT3_AC_PROFILE **)v21 + 69),
                           v14,
                           (unsigned __int8 *)lpMem,
                           a4);
    RpcClientToken = UserDataProperties;
    if ( !UserDataProperties )
      goto LABEL_40;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 93, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, UserDataProperties);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) == 0 )
      goto LABEL_41;
    v15 = 1860;
    v16 = QueryUserDataPropertiesFailed;
    goto LABEL_26;
  }
  Profile = Dot3AcmQueryMachineUserData(0, &v19, (unsigned __int8 **)&lpMem);
  RpcClientToken = Profile;
  if ( !Profile )
    goto LABEL_32;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || !BYTE1(WPP_GLOBAL_Control[1].Blink)
    || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
  {
    goto LABEL_41;
  }
  v12 = 92;
LABEL_17:
  WPP_SF_d(v11[1].Flink, v12, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, Profile);
LABEL_40:
  v11 = WPP_GLOBAL_Control;
LABEL_41:
  if ( !v21 )
    goto LABEL_44;
  LpFreeProfile(v21);
LABEL_43:
  v11 = WPP_GLOBAL_Control;
LABEL_44:
  if ( hObject[0] )
  {
    CloseHandle(hObject[0]);
    v11 = WPP_GLOBAL_Control;
  }
  if ( lpMem )
  {
    Dot3Free(lpMem);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v11[1].Blink) >= 4u && (BYTE4(v11[1].Blink) & 1) != 0 )
    WPP_SF_d(v11[1].Flink, 94, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, RpcClientToken);
  return RpcClientToken;
}

```

## disassembly

```asm
0x180015680  push    rbp
0x180015682  push    rbx
0x180015683  push    rsi
0x180015684  push    rdi
0x180015685  push    r13
0x180015687  push    r14
0x180015689  mov     rbp, rsp
0x18001568c  sub     rsp, 58h
0x180015690  mov     r14, r9
0x180015693  mov     [rbp+hObject], 0
0x18001569b  mov     esi, r8d
0x18001569e  mov     [rbp+var_28], 0
0x1800156a5  mov     rdi, rdx
0x1800156a8  mov     [rbp+lpMem], 0
0x1800156b0  mov     [rbp+var_18], 0
0x1800156b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156bf  lea     r13, WPP_GLOBAL_Control
0x1800156c6  cmp     rcx, r13
0x1800156c9  jz      short loc_1800156EC
0x1800156cb  cmp     byte ptr [rcx+19h], 4
0x1800156cf  jb      short loc_1800156EC
0x1800156d1  test    byte ptr [rcx+1Ch], 1
0x1800156d5  jz      short loc_1800156EC
0x1800156d7  mov     rcx, [rcx+10h]
0x1800156db  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800156e2  mov     edx, 59h ; 'Y'
0x1800156e7  call    WPP_SF_
0x1800156ec  lea     rcx, [rbp+hObject]
0x1800156f0  call    cs:__imp_RaQueryRpcClientToken
0x1800156f6  mov     ebx, eax
0x1800156f8  test    eax, eax
0x1800156fa  jnz     loc_1800158D7
0x180015700  test    r14, r14
0x180015703  jz      loc_1800158BA
0x180015709  test    esi, esi
0x18001570b  jnz     loc_1800158BA
0x180015711  cmp     cs:?g_bRpcServerStarted@@3EA, sil; uchar g_bRpcServerStarted
0x180015718  jnz     short loc_180015724
0x18001571a  mov     ebx, 6BAh
0x18001571f  jmp     loc_1800158D7
0x180015724  mov     rcx, rdi; struct _GUID *
0x180015727  call    ?Dot3AcmIsAPIAllowed@@YAHPEAU_GUID@@@Z; Dot3AcmIsAPIAllowed(_GUID *)
0x18001572c  test    eax, eax
0x18001572e  jnz     short loc_180015738
0x180015730  lea     ebx, [rax+32h]
0x180015733  jmp     loc_1800158D7
0x180015738  lea     r8, [rbp+var_18]; struct _PM_PROFILE **
0x18001573c  mov     rcx, rdi; struct _GUID *
0x18001573f  call    ?PmGetProfile@@YAKPEAU_GUID@@PEBGPEAPEAU_PM_PROFILE@@@Z; PmGetProfile(_GUID *,ushort const *,_PM_PROFILE * *)
0x180015744  mov     ebx, eax
0x180015746  test    eax, eax
0x180015748  jz      short loc_18001578B
0x18001574a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015751  cmp     rcx, r13
0x180015754  jz      loc_1800158C6
0x18001575a  cmp     byte ptr [rcx+19h], 1
0x18001575e  jb      loc_1800158C6
0x180015764  test    byte ptr [rcx+1Ch], 1
0x180015768  jz      loc_1800158C6
0x18001576e  mov     edx, 5Ah ; 'Z'
0x180015773  mov     rcx, [rcx+10h]
0x180015777  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001577e  mov     r9d, eax
0x180015781  call    WPP_SF_d
0x180015786  jmp     loc_1800158BF
0x18001578b  test    rdi, rdi
0x18001578e  jz      short loc_180015808
0x180015790  lea     r9, [rbp+lpMem]; unsigned __int8 **
0x180015794  mov     rcx, rdi; struct _GUID *
0x180015797  lea     r8, [rbp+var_28]; unsigned int *
0x18001579b  call    ?Dot3AcmQueryUserDataByGuid@@YAKPEBU_GUID@@PEAXPEAKPEAPEAE@Z; Dot3AcmQueryUserDataByGuid(_GUID const *,void *,ulong *,uchar * *)
0x1800157a0  mov     ebx, eax
0x1800157a2  test    eax, eax
0x1800157a4  jz      loc_18001584B
0x1800157aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157b1  cmp     rcx, r13
0x1800157b4  jz      short loc_1800157E1
0x1800157b6  cmp     byte ptr [rcx+19h], 1
0x1800157ba  jb      short loc_1800157E1
0x1800157bc  test    byte ptr [rcx+1Ch], 1
0x1800157c0  jz      short loc_1800157E1
0x1800157c2  mov     rcx, [rcx+10h]
0x1800157c6  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800157cd  mov     edx, 5Bh ; '['
0x1800157d2  mov     r9d, eax
0x1800157d5  call    WPP_SF_d
0x1800157da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157e1  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x1800157e8  jz      loc_1800158C6
0x1800157ee  mov     r9d, 72Fh
0x1800157f4  lea     rdx, QueryUserDataByGuidFailed
0x1800157fb  mov     r8d, ebx
0x1800157fe  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180015803  jmp     loc_1800158BF
0x180015808  lea     r8, [rbp+lpMem]; unsigned __int8 **
0x18001580c  xor     ecx, ecx; TokenHandle
0x18001580e  lea     rdx, [rbp+var_28]; unsigned int *
0x180015812  call    ?Dot3AcmQueryMachineUserData@@YAKPEAXPEAKPEAPEAE@Z; Dot3AcmQueryMachineUserData(void *,ulong *,uchar * *)
0x180015817  mov     ebx, eax
0x180015819  test    eax, eax
0x18001581b  jz      short loc_18001584B
0x18001581d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015824  cmp     rcx, r13
0x180015827  jz      loc_1800158C6
0x18001582d  cmp     byte ptr [rcx+19h], 1
0x180015831  jb      loc_1800158C6
0x180015837  test    byte ptr [rcx+1Ch], 1
0x18001583b  jz      loc_1800158C6
0x180015841  mov     edx, 5Ch ; '\'
0x180015846  jmp     loc_180015773
0x18001584b  mov     rcx, [rbp+var_18]
0x18001584f  mov     r9, r14; unsigned int *
0x180015852  mov     r8, [rbp+lpMem]; unsigned __int8 *
0x180015856  mov     rcx, [rcx+228h]; struct _DOT3_AC_PROFILE *
0x18001585d  call    ?AcmQueryUserDataProperties@@YAKPEAU_DOT3_AC_PROFILE@@KPEAEPEAK@Z; AcmQueryUserDataProperties(_DOT3_AC_PROFILE *,ulong,uchar *,ulong *)
0x180015862  mov     ebx, eax
0x180015864  test    eax, eax
0x180015866  jz      short loc_1800158BF
0x180015868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001586f  cmp     rcx, r13
0x180015872  jz      short loc_18001589F
0x180015874  cmp     byte ptr [rcx+19h], 1
0x180015878  jb      short loc_18001589F
0x18001587a  test    byte ptr [rcx+1Ch], 1
0x18001587e  jz      short loc_18001589F
0x180015880  mov     rcx, [rcx+10h]
0x180015884  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001588b  mov     edx, 5Dh ; ']'
0x180015890  mov     r9d, eax
0x180015893  call    WPP_SF_d
0x180015898  mov     rcx, cs:WPP_GLOBAL_Control
0x18001589f  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x1800158a6  jz      short loc_1800158C6
0x1800158a8  mov     r9d, 744h
0x1800158ae  lea     rdx, QueryUserDataPropertiesFailed
0x1800158b5  jmp     loc_1800157FB
0x1800158ba  mov     ebx, 57h ; 'W'
0x1800158bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158c6  mov     rax, [rbp+var_18]
0x1800158ca  test    rax, rax
0x1800158cd  jz      short loc_1800158DE
0x1800158cf  mov     rcx, rax; lpMem
0x1800158d2  call    LpFreeProfile
0x1800158d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158de  mov     rax, [rbp+hObject]
0x1800158e2  test    rax, rax
0x1800158e5  jz      short loc_1800158F7
0x1800158e7  mov     rcx, rax; hObject
0x1800158ea  call    cs:__imp_CloseHandle
0x1800158f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158f7  mov     rax, [rbp+lpMem]
0x1800158fb  test    rax, rax
0x1800158fe  jz      short loc_18001590F
0x180015900  mov     rcx, rax; lpMem
0x180015903  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180015908  mov     rcx, cs:WPP_GLOBAL_Control
0x18001590f  cmp     rcx, r13
0x180015912  jz      short loc_180015938
0x180015914  cmp     byte ptr [rcx+19h], 4
0x180015918  jb      short loc_180015938
0x18001591a  test    byte ptr [rcx+1Ch], 1
0x18001591e  jz      short loc_180015938
0x180015920  mov     rcx, [rcx+10h]
0x180015924  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001592b  mov     edx, 5Eh ; '^'
0x180015930  mov     r9d, ebx
0x180015933  call    WPP_SF_d
0x180015938  mov     eax, ebx
0x18001593a  add     rsp, 58h
0x18001593e  pop     r14
0x180015940  pop     r13
0x180015942  pop     rdi
0x180015943  pop     rsi
0x180015944  pop     rbx
0x180015945  pop     rbp
0x180015946  retn
```
