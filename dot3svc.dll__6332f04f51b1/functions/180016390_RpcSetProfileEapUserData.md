# RpcSetProfileEapUserData

- ea: `0x180016390`
- end: `0x18001678a`
- name: `RpcSetProfileEapUserData`
- size: `1018`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, __int128 *, char, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x180013bec`
- `0x180014d14`
- `0x180016390`
- `0x18001f180`
- `0x18001fc54`
- `0x1800213c4`
- `0x180021b40`
- `0x18003184c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001675d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001675d`
- `MobileNetworking!RaCheckRpcAllowed` at `0x180016412`
- `MobileNetworking!RaCheckRpcAllowed` at `0x180016412`
- `MobileNetworking!RaQueryRpcClientToken` at `0x18001646e`
- `MobileNetworking!RaQueryRpcClientToken` at `0x18001646e`

## pseudocode

```c
__int64 __fastcall RpcSetProfileEapUserData(
        __int64 a1,
        struct _GUID *a2,
        __int128 *a3,
        char a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  unsigned __int8 *v6; // rdi
  DWORD v7; // r13d
  int v11; // r14d
  unsigned int CanSaveUserData; // ebx
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  unsigned __int8 *v16; // r15
  __int128 *v17; // r13
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // r9
  HANDLE v20; // rdx
  HANDLE v21; // rcx
  __int128 v23; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+40h] BYREF
  __int128 *v25; // [rsp+A0h] [rbp+50h]
  SIZE_T dwBytes; // [rsp+A8h] [rbp+58h] BYREF

  v25 = a3;
  v6 = 0;
  hObject = 0;
  v7 = 0;
  LODWORD(dwBytes) = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 71, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, a1);
  }
  v11 = a4 & 1;
  if ( v11 )
  {
    CanSaveUserData = RaCheckRpcAllowed(qword_180052F20, 1);
    if ( CanSaveUserData )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v14 = 72;
LABEL_11:
        WPP_SF_d(v13[1].Flink, v14, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, CanSaveUserData);
        goto LABEL_67;
      }
      goto LABEL_67;
    }
LABEL_17:
    if ( !a1 || (v15 = a5, v16 = a6, a5) && !a6 )
    {
      CanSaveUserData = 87;
      goto LABEL_67;
    }
    if ( !g_bRpcServerStarted )
    {
      CanSaveUserData = 1722;
      goto LABEL_67;
    }
    if ( !(unsigned int)Dot3AcmIsAPIAllowed(a2) )
    {
      CanSaveUserData = 50;
      goto LABEL_67;
    }
    CanSaveUserData = Dot3AcmCanSaveUserData(a2, v15, v16, v11);
    if ( CanSaveUserData )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v14 = 74;
        goto LABEL_11;
      }
      goto LABEL_67;
    }
    if ( v15 )
    {
      v17 = v25;
      v23 = *v25;
      CanSaveUserData = OneXSetEapUserData(hObject, 0, &v23, v15, v16, 0, &dwBytes);
      if ( CanSaveUserData != 234 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 75, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, CanSaveUserData);
        }
        if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) == 0 )
          goto LABEL_67;
        v19 = 1476;
        goto LABEL_37;
      }
      v6 = (unsigned __int8 *)Dot3Alloc((unsigned int)dwBytes);
      if ( !v6 )
      {
        CanSaveUserData = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v14 = 76;
          goto LABEL_11;
        }
        goto LABEL_67;
      }
      v23 = *v17;
      CanSaveUserData = OneXSetEapUserData(hObject, 0, &v23, v15, v16, v6, &dwBytes);
      if ( CanSaveUserData )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 77, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, CanSaveUserData);
        }
        if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) == 0 )
          goto LABEL_67;
        v19 = 1492;
LABEL_37:
        McTemplateU0qqq_EtwEventWriteTransfer(v18, SetEapUserDataFailed, CanSaveUserData, v19);
        goto LABEL_67;
      }
      v7 = dwBytes;
      *(_DWORD *)&v6[*((unsigned int *)v6 + 4) + 20] |= v11 + 1;
    }
    if ( a2 )
    {
      v20 = hObject;
      if ( v11 )
        v20 = 0;
      CanSaveUserData = Dot3AcmSetUserDataByGuid(a2, v20, v7, v6);
      if ( CanSaveUserData )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v14 = 78;
          goto LABEL_11;
        }
      }
    }
    else
    {
      v21 = hObject;
      if ( v11 )
        v21 = 0;
      CanSaveUserData = Dot3AcmSetMachineUserData(v21, (const unsigned __int16 *)v7, v6);
      if ( CanSaveUserData )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v14 = 79;
          goto LABEL_11;
        }
      }
    }
    goto LABEL_67;
  }
  CanSaveUserData = RaQueryRpcClientToken(&hObject);
  if ( !CanSaveUserData )
    goto LABEL_17;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v14 = 73;
    goto LABEL_11;
  }
LABEL_67:
  if ( hObject )
    CloseHandle(hObject);
  if ( v6 )
    Dot3Free(v6);
  return CanSaveUserData;
}

```

## disassembly

```asm
0x180016390  mov     [rsp-38h+arg_8], rbx
0x180016395  mov     [rsp-38h+arg_10], r8
0x18001639a  push    rbp
0x18001639b  push    rsi
0x18001639c  push    rdi
0x18001639d  push    r12
0x18001639f  push    r13
0x1800163a1  push    r14
0x1800163a3  push    r15
0x1800163a5  mov     rbp, rsp
0x1800163a8  sub     rsp, 50h
0x1800163ac  xor     edi, edi
0x1800163ae  mov     [rbp+hObject], 0
0x1800163b6  xor     r13d, r13d
0x1800163b9  mov     r14d, r9d
0x1800163bc  mov     dword ptr [rbp+dwBytes], r13d
0x1800163c0  mov     r12, rdx
0x1800163c3  mov     rsi, rcx
0x1800163c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163cd  lea     rax, WPP_GLOBAL_Control
0x1800163d4  lea     r15d, [rdi+1]
0x1800163d8  cmp     rcx, rax
0x1800163db  jz      short loc_1800163FF
0x1800163dd  cmp     byte ptr [rcx+19h], 4
0x1800163e1  jb      short loc_1800163FF
0x1800163e3  test    [rcx+1Ch], r15b
0x1800163e7  jz      short loc_1800163FF
0x1800163e9  mov     rcx, [rcx+10h]
0x1800163ed  lea     edx, [rdi+47h]
0x1800163f0  mov     r9, rsi
0x1800163f3  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800163fa  call    WPP_SF_q
0x1800163ff  and     r14d, r15d
0x180016402  jz      short loc_18001646A
0x180016404  lea     r8, [rbp+hObject]
0x180016408  mov     edx, r15d
0x18001640b  lea     rcx, qword_180052F20
0x180016412  call    cs:__imp_RaCheckRpcAllowed
0x180016418  mov     ebx, eax
0x18001641a  test    eax, eax
0x18001641c  jz      loc_1800164AC
0x180016422  mov     rcx, cs:WPP_GLOBAL_Control
0x180016429  lea     rax, WPP_GLOBAL_Control
0x180016430  cmp     rcx, rax
0x180016433  jz      loc_180016754
0x180016439  cmp     [rcx+19h], r15b
0x18001643d  jb      loc_180016754
0x180016443  test    [rcx+1Ch], r15b
0x180016447  jz      loc_180016754
0x18001644d  mov     edx, 48h ; 'H'
0x180016452  mov     rcx, [rcx+10h]
0x180016456  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001645d  mov     r9d, ebx
0x180016460  call    WPP_SF_d
0x180016465  jmp     loc_180016754
0x18001646a  lea     rcx, [rbp+hObject]
0x18001646e  call    cs:__imp_RaQueryRpcClientToken
0x180016474  mov     ebx, eax
0x180016476  test    eax, eax
0x180016478  jz      short loc_1800164AC
0x18001647a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016481  lea     rax, WPP_GLOBAL_Control
0x180016488  cmp     rcx, rax
0x18001648b  jz      loc_180016754
0x180016491  cmp     [rcx+19h], r15b
0x180016495  jb      loc_180016754
0x18001649b  test    [rcx+1Ch], r15b
0x18001649f  jz      loc_180016754
0x1800164a5  mov     edx, 49h ; 'I'
0x1800164aa  jmp     short loc_180016452
0x1800164ac  test    rsi, rsi
0x1800164af  jz      loc_18001674F
0x1800164b5  mov     esi, [rbp+arg_20]
0x1800164b8  mov     r15, [rbp+arg_28]
0x1800164bc  test    esi, esi
0x1800164be  jz      short loc_1800164C9
0x1800164c0  test    r15, r15
0x1800164c3  jz      loc_18001674F
0x1800164c9  cmp     cs:?g_bRpcServerStarted@@3EA, dil; uchar g_bRpcServerStarted
0x1800164d0  jnz     short loc_1800164DC
0x1800164d2  mov     ebx, 6BAh
0x1800164d7  jmp     loc_180016754
0x1800164dc  mov     rcx, r12; struct _GUID *
0x1800164df  call    ?Dot3AcmIsAPIAllowed@@YAHPEAU_GUID@@@Z; Dot3AcmIsAPIAllowed(_GUID *)
0x1800164e4  test    eax, eax
0x1800164e6  jnz     short loc_1800164F0
0x1800164e8  lea     ebx, [rax+32h]
0x1800164eb  jmp     loc_180016754
0x1800164f0  mov     r9d, r14d; int
0x1800164f3  mov     r8, r15; unsigned __int8 *
0x1800164f6  mov     edx, esi; unsigned int
0x1800164f8  mov     rcx, r12; struct _GUID *
0x1800164fb  call    ?Dot3AcmCanSaveUserData@@YAKPEBU_GUID@@KQEAEH@Z; Dot3AcmCanSaveUserData(_GUID const *,ulong,uchar * const,int)
0x180016500  mov     ebx, eax
0x180016502  test    eax, eax
0x180016504  jz      short loc_18001653B
0x180016506  mov     rcx, cs:WPP_GLOBAL_Control
0x18001650d  lea     rax, WPP_GLOBAL_Control
0x180016514  cmp     rcx, rax
0x180016517  jz      loc_180016754
0x18001651d  cmp     byte ptr [rcx+19h], 1
0x180016521  jb      loc_180016754
0x180016527  test    byte ptr [rcx+1Ch], 1
0x18001652b  jz      loc_180016754
0x180016531  mov     edx, 4Ah ; 'J'
0x180016536  jmp     loc_180016452
0x18001653b  test    esi, esi
0x18001653d  jz      loc_1800166BB
0x180016543  mov     r13, [rbp+arg_10]
0x180016547  lea     rax, [rbp+dwBytes]
0x18001654b  mov     rcx, [rbp+hObject]
0x18001654f  lea     r8, [rbp+var_10]
0x180016553  mov     [rsp+50h+var_20], rax
0x180016558  mov     r9d, esi
0x18001655b  mov     [rsp+50h+var_28], rdi
0x180016560  xor     edx, edx
0x180016562  movups  xmm0, xmmword ptr [r13+0]
0x180016567  mov     [rsp+50h+var_30], r15
0x18001656c  movdqu  [rbp+var_10], xmm0
0x180016571  call    OneXSetEapUserData
0x180016576  mov     ebx, eax
0x180016578  cmp     eax, 0EAh
0x18001657d  jz      short loc_1800165DD
0x18001657f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016586  lea     rax, WPP_GLOBAL_Control
0x18001658d  cmp     rcx, rax
0x180016590  jz      short loc_1800165B6
0x180016592  cmp     byte ptr [rcx+19h], 1
0x180016596  jb      short loc_1800165B6
0x180016598  test    byte ptr [rcx+1Ch], 1
0x18001659c  jz      short loc_1800165B6
0x18001659e  mov     rcx, [rcx+10h]
0x1800165a2  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800165a9  mov     edx, 4Bh ; 'K'
0x1800165ae  mov     r9d, ebx
0x1800165b1  call    WPP_SF_d
0x1800165b6  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x1800165bd  jz      loc_180016754
0x1800165c3  mov     r9d, 5C4h
0x1800165c9  mov     r8d, ebx
0x1800165cc  lea     rdx, SetEapUserDataFailed
0x1800165d3  call    McTemplateU0qqq_EtwEventWriteTransfer
0x1800165d8  jmp     loc_180016754
0x1800165dd  mov     ecx, dword ptr [rbp+dwBytes]; dwBytes
0x1800165e0  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x1800165e5  mov     rdi, rax
0x1800165e8  test    rax, rax
0x1800165eb  jnz     short loc_180016628
0x1800165ed  call    cs:__imp_GetLastError
0x1800165f3  mov     ebx, eax
0x1800165f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165fc  lea     rax, WPP_GLOBAL_Control
0x180016603  cmp     rcx, rax
0x180016606  jz      loc_180016754
0x18001660c  cmp     byte ptr [rcx+19h], 1
0x180016610  jb      loc_180016754
0x180016616  test    byte ptr [rcx+1Ch], 1
0x18001661a  jz      loc_180016754
0x180016620  lea     edx, [rdi+4Ch]
0x180016623  jmp     loc_180016452
0x180016628  movups  xmm0, xmmword ptr [r13+0]
0x18001662d  mov     rcx, [rbp+hObject]
0x180016631  lea     rax, [rbp+dwBytes]
0x180016635  mov     [rsp+50h+var_20], rax
0x18001663a  lea     r8, [rbp+var_10]
0x18001663e  mov     [rsp+50h+var_28], rdi
0x180016643  mov     r9d, esi
0x180016646  xor     edx, edx
0x180016648  mov     [rsp+50h+var_30], r15
0x18001664d  movdqu  [rbp+var_10], xmm0
0x180016652  call    OneXSetEapUserData
0x180016657  mov     ebx, eax
0x180016659  test    eax, eax
0x18001665b  jz      short loc_1800166AC
0x18001665d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016664  lea     rax, WPP_GLOBAL_Control
0x18001666b  cmp     rcx, rax
0x18001666e  jz      short loc_180016694
0x180016670  cmp     byte ptr [rcx+19h], 1
0x180016674  jb      short loc_180016694
0x180016676  test    byte ptr [rcx+1Ch], 1
0x18001667a  jz      short loc_180016694
0x18001667c  mov     rcx, [rcx+10h]
0x180016680  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180016687  mov     edx, 4Dh ; 'M'
0x18001668c  mov     r9d, ebx
0x18001668f  call    WPP_SF_d
0x180016694  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x18001669b  jz      loc_180016754
0x1800166a1  mov     r9d, 5D4h
0x1800166a7  jmp     loc_1800165C9
0x1800166ac  mov     ecx, [rdi+10h]
0x1800166af  lea     eax, [r14+1]
0x1800166b3  mov     r13d, dword ptr [rbp+dwBytes]
0x1800166b7  or      [rcx+rdi+14h], eax
0x1800166bb  xor     eax, eax
0x1800166bd  test    r12, r12
0x1800166c0  jz      short loc_18001670A
0x1800166c2  mov     rdx, [rbp+hObject]
0x1800166c6  test    r14d, r14d
0x1800166c9  mov     r9, rdi; unsigned __int8 *
0x1800166cc  mov     r8d, r13d; unsigned int
0x1800166cf  cmovnz  rdx, rax; TokenHandle
0x1800166d3  mov     rcx, r12; struct _GUID *
0x1800166d6  call    ?Dot3AcmSetUserDataByGuid@@YAKPEBU_GUID@@PEAXKPEAE@Z; Dot3AcmSetUserDataByGuid(_GUID const *,void *,ulong,uchar *)
0x1800166db  mov     ebx, eax
0x1800166dd  test    eax, eax
0x1800166df  jz      short loc_180016754
0x1800166e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166e8  lea     rax, WPP_GLOBAL_Control
0x1800166ef  cmp     rcx, rax
0x1800166f2  jz      short loc_180016754
0x1800166f4  cmp     byte ptr [rcx+19h], 1
0x1800166f8  jb      short loc_180016754
0x1800166fa  test    byte ptr [rcx+1Ch], 1
0x1800166fe  jz      short loc_180016754
0x180016700  mov     edx, 4Eh ; 'N'
0x180016705  jmp     loc_180016452
0x18001670a  mov     rcx, [rbp+hObject]
0x18001670e  test    r14d, r14d
0x180016711  mov     r8, rdi; unsigned __int8 *
0x180016714  mov     edx, r13d; unsigned int
0x180016717  cmovnz  rcx, rax; TokenHandle
0x18001671b  call    ?Dot3AcmSetMachineUserData@@YAKPEAXKPEAE@Z; Dot3AcmSetMachineUserData(void *,ulong,uchar *)
0x180016720  mov     ebx, eax
0x180016722  test    eax, eax
0x180016724  jz      short loc_180016754
0x180016726  mov     rcx, cs:WPP_GLOBAL_Control
0x18001672d  lea     rax, WPP_GLOBAL_Control
0x180016734  cmp     rcx, rax
0x180016737  jz      short loc_180016754
0x180016739  cmp     byte ptr [rcx+19h], 1
0x18001673d  jb      short loc_180016754
0x18001673f  test    byte ptr [rcx+1Ch], 1
0x180016743  jz      short loc_180016754
0x180016745  mov     edx, 4Fh ; 'O'
0x18001674a  jmp     loc_180016452
0x18001674f  mov     ebx, 57h ; 'W'
0x180016754  mov     rcx, [rbp+hObject]; hObject
0x180016758  test    rcx, rcx
0x18001675b  jz      short loc_180016763
0x18001675d  call    cs:__imp_CloseHandle
0x180016763  test    rdi, rdi
0x180016766  jz      short loc_180016770
0x180016768  mov     rcx, rdi; lpMem
0x18001676b  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180016770  mov     eax, ebx
0x180016772  mov     rbx, [rsp+50h+arg_8]
0x18001677a  add     rsp, 50h
0x18001677e  pop     r15
0x180016780  pop     r14
0x180016782  pop     r13
0x180016784  pop     r12
0x180016786  pop     rdi
0x180016787  pop     rsi
0x180016788  pop     rbp
0x180016789  retn
```
