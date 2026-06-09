# IntfLoadProfile(_LAN_INTERFACE_CONTEXT *)

- ea: `0x180019690`
- end: `0x180019a54`
- name: `?IntfLoadProfile@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(struct _LAN_INTERFACE_CONTEXT *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180018d4c`
- `0x1800201f0`

## callees

- `0x1800030fc`
- `0x18000a7ec`
- `0x18000a9c0`
- `0x18000c4d4`
- `0x18000c85c`
- `0x18000d230`
- `0x180013264`
- `0x180019690`
- `0x18002489c`
- `0x18002491c`
- `0x180025480`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019896`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019896`
- `dot3msm!Dot3SetPortAuthenticationState` at `0x1800199cf`
- `dot3msm!Dot3SetPortAuthenticationState` at `0x1800199cf`
- `dot3msm!Dot3MsmCreateDefaultProfile` at `0x180019757`
- `dot3msm!Dot3MsmCreateDefaultProfile` at `0x180019757`
- `dot3msm!Dot3MsmFreeProfile` at `0x180019a34`
- `dot3msm!Dot3MsmFreeProfile` at `0x180019a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197db`

## pseudocode

```c
__int64 __fastcall IntfLoadProfile(struct _LAN_INTERFACE_CONTEXT *a1)
{
  struct _GUID *v1; // r15
  unsigned int v3; // eax
  unsigned int LastError; // ebx
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  struct _PM_PROFILE *v8; // rsi
  char *v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  void *v19; // rax
  unsigned int v20; // ecx
  __int64 v21; // rdx
  void *v22; // rcx
  unsigned int v23; // r8d
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  int v26; // edx
  int v27; // edx
  __int64 v28; // rdx
  GUID v29; // xmm0
  struct _L2_NOTIFICATION_DATA v31; // [rsp+20h] [rbp-30h] BYREF
  __int64 v32; // [rsp+90h] [rbp+40h] BYREF
  struct _PM_PROFILE *v33; // [rsp+98h] [rbp+48h] BYREF

  *((_DWORD *)a1 + 80) = 5;
  v1 = (struct _GUID *)((char *)a1 + 8);
  *((_QWORD *)a1 + 39) = 0;
  v32 = 0;
  v33 = 0;
  *(&v31.dwDataSize + 1) = 0;
  v31.InterfaceGuid = 0;
  v3 = PmEnumProfiles(
         (struct _GUID *)((char *)a1 + 8),
         (unsigned int (*)(struct _PM_PROFILE *, unsigned int, void *))ProfileCallBack,
         a1);
  LastError = v3;
  if ( v3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v6 = 153;
      v7 = v3;
LABEL_6:
      WPP_SF_d(v5[1].Flink, v6, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v7);
    }
  }
  else
  {
    v8 = (struct _PM_PROFILE *)*((_QWORD *)a1 + 39);
    if ( v8 )
    {
      v9 = (char *)*((_QWORD *)v8 + 69);
      v33 = (struct _PM_PROFILE *)*((_QWORD *)a1 + 39);
      if ( v9 )
        goto LABEL_31;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v6 = 154;
        v7 = 0;
        goto LABEL_6;
      }
    }
  }
  v10 = Dot3MsmCreateDefaultProfile(&v32);
  LastError = v10;
  if ( !v10 )
  {
    v9 = (char *)Dot3Alloc(0x20u, v11, v12);
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_61;
    }
    *(_DWORD *)v9 = 0;
    v18 = v32;
    *(_OWORD *)(v9 + 8) = *(_OWORD *)v32;
    *((_QWORD *)v9 + 3) = *(_QWORD *)(v18 + 16);
    v19 = Dot3Alloc(*(unsigned int *)(v32 + 8), v16, v17);
    *((_QWORD *)v9 + 3) = v19;
    if ( !v19 )
    {
LABEL_22:
      LastError = 14;
      goto LABEL_61;
    }
    memcpy_0(v19, *(const void **)(v32 + 16), *(unsigned int *)(v32 + 8));
    LastError = PmAllocateEmptyProfile(v20, &v33);
    if ( LastError )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_61;
      }
      v14 = 156;
      goto LABEL_28;
    }
    v8 = v33;
    if ( !v33 )
      goto LABEL_22;
    _o_wcscpy_s((char *)v33 + 24, 256, L"DEFAULT");
    *((_QWORD *)v8 + 69) = v9;
    LastError = PmSetProfile(v1, v21, v8);
    if ( LastError )
      goto LABEL_61;
LABEL_31:
    v22 = (void *)*((_QWORD *)a1 + 37);
    if ( v22 )
      LpFreeProfile(v22);
    v23 = *((_DWORD *)a1 + 80);
    v24 = (unsigned __int16 *)*((_QWORD *)a1 + 15);
    *((_DWORD *)a1 + 76) = v23;
    *((_QWORD *)a1 + 37) = v8;
    Dot3LogProfileChangeEvent(v1, v24, v23, (struct _DOT3_AC_PROFILE *)v9);
    v25 = *((_QWORD *)v9 + 3);
    if ( v25 )
      *((_DWORD *)v9 + 4) = *(_DWORD *)(v25 + 4);
    if ( *((_DWORD *)a1 + 76) != 1 )
    {
      if ( !*((_DWORD *)v9 + 3) || (v26 = 1, !*((_DWORD *)v9 + 2)) )
        v26 = 0;
      LastError = ChangeNdisControlState(v1, v26);
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_61;
        }
        v14 = 157;
        goto LABEL_28;
      }
      if ( !*((_DWORD *)v9 + 3) || (v27 = 0, !*((_DWORD *)v9 + 2)) )
        v27 = 1;
      LastError = ChangeNdisAuthState(v1, v27);
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_61;
        }
        v14 = 158;
        goto LABEL_28;
      }
      if ( !*((_DWORD *)v9 + 3) || (v28 = 1, !*((_DWORD *)v9 + 2)) )
        v28 = 0;
      LastError = Dot3SetPortAuthenticationState(*((_QWORD *)a1 + 41), v28, 0);
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_61;
        }
        v14 = 159;
LABEL_28:
        v15 = LastError;
        goto LABEL_14;
      }
    }
    v29 = *v1;
    v31.NotificationSource = 1;
    v31.NotificationCode = 11;
    v31.InterfaceGuid = v29;
    v31.pData = 0;
    v31.dwDataSize = 0;
    NhNotify(0, &v31);
    goto LABEL_61;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v14 = 155;
    v15 = v10;
LABEL_14:
    WPP_SF_d(v13[1].Flink, v14, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v15);
  }
LABEL_61:
  if ( v32 )
    Dot3MsmFreeProfile(v32);
  return LastError;
}

```

## disassembly

```asm
0x180019690  mov     [rsp-38h+arg_10], rbx
0x180019695  push    rbp
0x180019696  push    rsi
0x180019697  push    rdi
0x180019698  push    r12
0x18001969a  push    r13
0x18001969c  push    r14
0x18001969e  push    r15
0x1800196a0  mov     rbp, rsp
0x1800196a3  sub     rsp, 50h
0x1800196a7  xor     r12d, r12d
0x1800196aa  mov     dword ptr [rcx+140h], 5
0x1800196b4  lea     r15, [rcx+8]
0x1800196b8  mov     [rcx+138h], r12
0x1800196bf  mov     r14, rcx
0x1800196c2  mov     [rbp+arg_0], r12
0x1800196c6  xorps   xmm0, xmm0
0x1800196c9  mov     [rbp+arg_8], r12
0x1800196cd  mov     r8, rcx; void *
0x1800196d0  mov     dword ptr [rbp+var_30+1Ch], r12d
0x1800196d4  mov     rcx, r15; struct _GUID *
0x1800196d7  lea     rdx, ?ProfileCallBack@@YAKPEAU_PM_PROFILE@@KPEAX@Z; unsigned int (*)(struct _PM_PROFILE *, unsigned int, void *)
0x1800196de  movdqu  xmmword ptr [rbp+var_30.InterfaceGuid.Data1], xmm0
0x1800196e3  call    ?PmEnumProfiles@@YAKPEAU_GUID@@P6AKPEAU_PM_PROFILE@@KPEAX@Z2@Z; PmEnumProfiles(_GUID *,ulong (*)(_PM_PROFILE *,ulong,void *),void *)
0x1800196e8  lea     rdi, WPP_GLOBAL_Control
0x1800196ef  mov     ebx, eax
0x1800196f1  lea     r13d, [r12+1]
0x1800196f6  test    eax, eax
0x1800196f8  jz      short loc_18001972C
0x1800196fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019701  cmp     rcx, rdi
0x180019704  jz      short loc_180019753
0x180019706  cmp     byte ptr [rcx+19h], 2
0x18001970a  jb      short loc_180019753
0x18001970c  test    [rcx+1Ch], r13b
0x180019710  jz      short loc_180019753
0x180019712  mov     edx, 99h
0x180019717  mov     r9d, eax
0x18001971a  mov     rcx, [rcx+10h]
0x18001971e  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180019725  call    WPP_SF_d
0x18001972a  jmp     short loc_180019753
0x18001972c  mov     rsi, [r14+138h]
0x180019733  test    rsi, rsi
0x180019736  jz      short loc_1800197A4
0x180019738  mov     rdi, [rsi+228h]
0x18001973f  mov     [rbp+arg_8], rsi
0x180019743  test    rdi, rdi
0x180019746  jnz     loc_1800198B8
0x18001974c  lea     rdi, WPP_GLOBAL_Control
0x180019753  lea     rcx, [rbp+arg_0]
0x180019757  call    cs:__imp_Dot3MsmCreateDefaultProfile
0x18001975d  mov     ebx, eax
0x18001975f  test    eax, eax
0x180019761  jz      short loc_1800197C9
0x180019763  mov     rcx, cs:WPP_GLOBAL_Control
0x18001976a  cmp     rcx, rdi
0x18001976d  jz      loc_180019A2B
0x180019773  cmp     [rcx+19h], r13b
0x180019777  jb      loc_180019A2B
0x18001977d  test    [rcx+1Ch], r13b
0x180019781  jz      loc_180019A2B
0x180019787  mov     edx, 9Bh
0x18001978c  mov     r9d, eax
0x18001978f  mov     rcx, [rcx+10h]
0x180019793  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001979a  call    WPP_SF_d
0x18001979f  jmp     loc_180019A2B
0x1800197a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197ab  cmp     rcx, rdi
0x1800197ae  jz      short loc_180019753
0x1800197b0  cmp     byte ptr [rcx+19h], 2
0x1800197b4  jb      short loc_180019753
0x1800197b6  test    [rcx+1Ch], r13b
0x1800197ba  jz      short loc_180019753
0x1800197bc  mov     edx, 9Ah
0x1800197c1  xor     r9d, r9d
0x1800197c4  jmp     loc_18001971A
0x1800197c9  mov     ecx, 20h ; ' '; dwBytes
0x1800197ce  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x1800197d3  mov     rdi, rax
0x1800197d6  test    rax, rax
0x1800197d9  jnz     short loc_1800197EB
0x1800197db  call    cs:__imp_GetLastError
0x1800197e1  mov     ebx, eax
0x1800197e3  test    eax, eax
0x1800197e5  jnz     loc_180019A2B
0x1800197eb  mov     [rdi], r12d
0x1800197ee  mov     rcx, [rbp+arg_0]
0x1800197f2  movups  xmm0, xmmword ptr [rcx]
0x1800197f5  movups  xmmword ptr [rdi+8], xmm0
0x1800197f9  movsd   xmm1, qword ptr [rcx+10h]
0x1800197fe  movsd   qword ptr [rdi+18h], xmm1
0x180019803  mov     rax, [rbp+arg_0]
0x180019807  mov     ecx, [rax+8]; dwBytes
0x18001980a  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001980f  mov     [rdi+18h], rax
0x180019813  test    rax, rax
0x180019816  jnz     short loc_180019822
0x180019818  mov     ebx, 0Eh
0x18001981d  jmp     loc_180019A2B
0x180019822  mov     rdx, [rbp+arg_0]
0x180019826  mov     rcx, rax; void *
0x180019829  mov     r8d, [rdx+8]; Size
0x18001982d  mov     rdx, [rdx+10h]; Src
0x180019831  call    memcpy_0
0x180019836  lea     rdx, [rbp+arg_8]; struct _PM_PROFILE **
0x18001983a  call    ?PmAllocateEmptyProfile@@YAKKPEAPEAU_PM_PROFILE@@@Z; PmAllocateEmptyProfile(ulong,_PM_PROFILE * *)
0x18001983f  mov     ebx, eax
0x180019841  test    eax, eax
0x180019843  jz      short loc_18001987D
0x180019845  mov     rcx, cs:WPP_GLOBAL_Control
0x18001984c  lea     rax, WPP_GLOBAL_Control
0x180019853  cmp     rcx, rax
0x180019856  jz      loc_180019A2B
0x18001985c  cmp     [rcx+19h], r13b
0x180019860  jb      loc_180019A2B
0x180019866  test    [rcx+1Ch], r13b
0x18001986a  jz      loc_180019A2B
0x180019870  mov     edx, 9Ch
0x180019875  mov     r9d, ebx
0x180019878  jmp     loc_18001978F
0x18001987d  mov     rsi, [rbp+arg_8]
0x180019881  test    rsi, rsi
0x180019884  jz      short loc_180019818
0x180019886  lea     rcx, [rsi+18h]
0x18001988a  mov     edx, 100h
0x18001988f  lea     r8, aDefault; "DEFAULT"
0x180019896  call    cs:__imp__o_wcscpy_s
0x18001989c  mov     r8, rsi; struct _PM_PROFILE *
0x18001989f  mov     [rsi+228h], rdi
0x1800198a6  mov     rcx, r15; struct _GUID *
0x1800198a9  call    ?PmSetProfile@@YAKPEAU_GUID@@KPEAU_PM_PROFILE@@H@Z; PmSetProfile(_GUID *,ulong,_PM_PROFILE *,int)
0x1800198ae  mov     ebx, eax
0x1800198b0  test    eax, eax
0x1800198b2  jnz     loc_180019A2B
0x1800198b8  mov     rcx, [r14+128h]; lpMem
0x1800198bf  test    rcx, rcx
0x1800198c2  jz      short loc_1800198C9
0x1800198c4  call    LpFreeProfile
0x1800198c9  mov     r8d, [r14+140h]; unsigned int
0x1800198d0  mov     r9, rdi; struct _DOT3_AC_PROFILE *
0x1800198d3  mov     rdx, [r14+78h]; unsigned __int16 *
0x1800198d7  mov     rcx, r15; struct _GUID *
0x1800198da  mov     [r14+130h], r8d
0x1800198e1  mov     [r14+128h], rsi
0x1800198e8  call    ?Dot3LogProfileChangeEvent@@YAKPEAU_GUID@@PEAGKPEAU_DOT3_AC_PROFILE@@@Z; Dot3LogProfileChangeEvent(_GUID *,ushort *,ulong,_DOT3_AC_PROFILE *)
0x1800198ed  mov     rax, [rdi+18h]
0x1800198f1  test    rax, rax
0x1800198f4  jz      short loc_1800198FC
0x1800198f6  mov     eax, [rax+4]
0x1800198f9  mov     [rdi+10h], eax
0x1800198fc  cmp     [r14+130h], r13d
0x180019903  jz      loc_180019A04
0x180019909  cmp     [rdi+0Ch], r12d
0x18001990d  jz      short loc_180019918
0x18001990f  mov     edx, r13d
0x180019912  cmp     [rdi+8], r12d
0x180019916  jnz     short loc_18001991B
0x180019918  mov     edx, r12d; int
0x18001991b  mov     rcx, r15; struct _GUID *
0x18001991e  call    ?ChangeNdisControlState@@YAKPEAU_GUID@@H@Z; ChangeNdisControlState(_GUID *,int)
0x180019923  mov     ebx, eax
0x180019925  test    eax, eax
0x180019927  jz      short loc_18001995E
0x180019929  mov     rcx, cs:WPP_GLOBAL_Control
0x180019930  lea     rax, WPP_GLOBAL_Control
0x180019937  cmp     rcx, rax
0x18001993a  jz      loc_180019A2B
0x180019940  cmp     [rcx+19h], r13b
0x180019944  jb      loc_180019A2B
0x18001994a  test    [rcx+1Ch], r13b
0x18001994e  jz      loc_180019A2B
0x180019954  mov     edx, 9Dh
0x180019959  jmp     loc_180019875
0x18001995e  cmp     [rdi+0Ch], r12d
0x180019962  jz      short loc_18001996D
0x180019964  mov     edx, r12d
0x180019967  cmp     [rdi+8], r12d
0x18001996b  jnz     short loc_180019970
0x18001996d  mov     edx, r13d; int
0x180019970  mov     rcx, r15; struct _GUID *
0x180019973  call    ?ChangeNdisAuthState@@YAKPEAU_GUID@@H@Z; ChangeNdisAuthState(_GUID *,int)
0x180019978  mov     ebx, eax
0x18001997a  test    eax, eax
0x18001997c  jz      short loc_1800199B3
0x18001997e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019985  lea     rax, WPP_GLOBAL_Control
0x18001998c  cmp     rcx, rax
0x18001998f  jz      loc_180019A2B
0x180019995  cmp     [rcx+19h], r13b
0x180019999  jb      loc_180019A2B
0x18001999f  test    [rcx+1Ch], r13b
0x1800199a3  jz      loc_180019A2B
0x1800199a9  mov     edx, 9Eh
0x1800199ae  jmp     loc_180019875
0x1800199b3  cmp     [rdi+0Ch], r12d
0x1800199b7  jz      short loc_1800199C2
0x1800199b9  mov     edx, r13d
0x1800199bc  cmp     [rdi+8], r12d
0x1800199c0  jnz     short loc_1800199C5
0x1800199c2  mov     edx, r12d
0x1800199c5  mov     rcx, [r14+148h]
0x1800199cc  xor     r8d, r8d
0x1800199cf  call    cs:__imp_Dot3SetPortAuthenticationState
0x1800199d5  mov     ebx, eax
0x1800199d7  test    eax, eax
0x1800199d9  jz      short loc_180019A04
0x1800199db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199e2  lea     rax, WPP_GLOBAL_Control
0x1800199e9  cmp     rcx, rax
0x1800199ec  jz      short loc_180019A2B
0x1800199ee  cmp     [rcx+19h], r13b
0x1800199f2  jb      short loc_180019A2B
0x1800199f4  test    [rcx+1Ch], r13b
0x1800199f8  jz      short loc_180019A2B
0x1800199fa  mov     edx, 9Fh
0x1800199ff  jmp     loc_180019875
0x180019a04  movups  xmm0, xmmword ptr [r15]
0x180019a08  lea     rdx, [rbp+var_30]; struct _L2_NOTIFICATION_DATA *
0x180019a0c  mov     [rbp+var_30.NotificationSource], r13d
0x180019a10  xor     ecx, ecx; void *
0x180019a12  mov     [rbp+var_30.NotificationCode], 0Bh
0x180019a19  movdqu  xmmword ptr [rbp+var_30.InterfaceGuid.Data1], xmm0
0x180019a1e  mov     [rbp+var_30.pData], r12
0x180019a22  mov     [rbp+var_30.dwDataSize], r12d
0x180019a26  call    ?NhNotify@@YAKPEAXPEAU_L2_NOTIFICATION_DATA@@@Z; NhNotify(void *,_L2_NOTIFICATION_DATA *)
0x180019a2b  mov     rcx, [rbp+arg_0]
0x180019a2f  test    rcx, rcx
0x180019a32  jz      short loc_180019A3A
0x180019a34  call    cs:__imp_Dot3MsmFreeProfile
0x180019a3a  mov     eax, ebx
0x180019a3c  mov     rbx, [rsp+50h+arg_10]
0x180019a44  add     rsp, 50h
0x180019a48  pop     r15
0x180019a4a  pop     r14
0x180019a4c  pop     r13
0x180019a4e  pop     r12
0x180019a50  pop     rdi
0x180019a51  pop     rsi
0x180019a52  pop     rbp
0x180019a53  retn
```
