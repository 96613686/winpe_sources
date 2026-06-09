# CCscWmiPinInfoObject::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x180021640`
- end: `0x1800219b7`
- name: `?_SetObjectProperties@CCscWmiPinInfoObject@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `887`
- prototype: `int(CCscWmiPinInfoObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180021640`
- `0x180022dc4`
- `0x180023170`
- `0x18002c010`

## string_xrefs

- `0x1800218d0`: `PinnedForComputer`

## pseudocode

```c
__int64 __fastcall CCscWmiPinInfoObject::_SetObjectProperties(
        CCscWmiPinInfoObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // r8d
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-10h] BYREF
  __int64 v19; // [rsp+28h] [rbp-8h] BYREF
  int v20; // [rsp+50h] [rbp+20h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v19 = 0;
  v7 = (**v6)(v6, &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b, &v19);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v20 = 0;
    v18 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 24LL))(v19, &v20);
    v8 = v9;
    if ( v9 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_29;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        26,
        WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)v9);
    }
    else
    {
      v8 = WmiProp_SetBooleanProperty(a4, L"Pinned", v20);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v19 + 32LL))(v19, &v20, &v18);
        if ( v8 >= 0 )
        {
          v10 = v20 ? (v18 != 0) + 1 : 0;
          v8 = WmiProp_SetUint32Property(a4, L"PinnedForUser", v10);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v19 + 40LL))(v19, &v20, &v18);
            if ( v8 < 0 )
            {
              v12 = WPP_GLOBAL_Control;
              goto LABEL_18;
            }
            if ( v20 )
              v11 = (v18 != 0) + 1;
            else
              v11 = 0;
            v8 = WmiProp_SetUint32Property(a4, L"PinnedForUserByPolicy", v11);
            goto LABEL_36;
          }
        }
        goto LABEL_32;
      }
    }
    v12 = WPP_GLOBAL_Control;
LABEL_29:
    if ( (_UNKNOWN *)v12 == &WPP_GLOBAL_Control )
      goto LABEL_48;
    if ( (*(_BYTE *)(v12 + 28) & 2) == 0 )
      goto LABEL_33;
    WPP_SF_d(*(_QWORD *)(v12 + 16), 27, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
LABEL_32:
    v12 = WPP_GLOBAL_Control;
LABEL_33:
    if ( (_UNKNOWN *)v12 == &WPP_GLOBAL_Control )
      goto LABEL_48;
    if ( (*(_BYTE *)(v12 + 28) & 2) == 0 )
    {
LABEL_37:
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v19 + 48LL))(v19, &v20, &v18);
        if ( v8 >= 0 )
        {
          if ( v20 )
            v15 = (v18 != 0) + 1;
          else
            v15 = 0;
          v8 = WmiProp_SetUint32Property(a4, L"PinnedForComputer", v15);
LABEL_21:
          if ( v8 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v19 + 56LL))(v19, &v20, &v18);
            v8 = v13;
            if ( v13 < 0 )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
              {
                WPP_SF_d(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  30,
                  WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
                  (unsigned int)v13);
              }
            }
            else
            {
              if ( v20 )
                v14 = (v18 != 0) + 1;
              else
                v14 = 0;
              v8 = WmiProp_SetUint32Property(a4, L"PinnedForFolderRedirection", v14);
            }
          }
          goto LABEL_48;
        }
        goto LABEL_48;
      }
LABEL_18:
      if ( (_UNKNOWN *)v12 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v12 + 28) & 2) != 0 )
          WPP_SF_d(*(_QWORD *)(v12 + 16), 29, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
        goto LABEL_21;
      }
LABEL_48:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_49:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_50;
    }
    WPP_SF_d(*(_QWORD *)(v12 + 16), 28, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
LABEL_36:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  if ( v7 != -2147467262 )
    goto LABEL_49;
  v16 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
    v16 = WPP_GLOBAL_Control;
  }
  v8 = -2147024846;
LABEL_50:
  if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_DWORD *)(v16 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v16 + 16), 32, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021640  mov     [rsp-18h+arg_8], rbx
0x180021645  mov     [rsp-18h+arg_10], rdi
0x18002164a  push    rbp
0x18002164b  push    r14
0x18002164d  push    r15
0x18002164f  mov     rbp, rsp
0x180021652  sub     rsp, 30h
0x180021656  mov     rdi, r9
0x180021659  mov     rbx, rcx
0x18002165c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021663  lea     r14, WPP_GLOBAL_Control
0x18002166a  lea     r15, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180021671  cmp     rcx, r14
0x180021674  jz      short loc_180021690
0x180021676  test    dword ptr [rcx+1Ch], 4000000h
0x18002167d  jz      short loc_180021690
0x18002167f  mov     rcx, [rcx+10h]
0x180021683  mov     edx, 19h
0x180021688  mov     r8, r15
0x18002168b  call    WPP_SF_
0x180021690  mov     rcx, [rbx+10h]
0x180021694  lea     r8, [rbp+var_8]
0x180021698  mov     [rbp+var_8], 0
0x1800216a0  lea     rdx, _GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b
0x1800216a7  mov     rax, [rcx]
0x1800216aa  mov     rax, [rax]
0x1800216ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216b2  mov     ebx, eax
0x1800216b4  test    eax, eax
0x1800216b6  js      loc_18002197C
0x1800216bc  mov     rcx, [rbp+var_8]
0x1800216c0  lea     rdx, [rbp+arg_0]
0x1800216c4  mov     [rbp+arg_0], 0
0x1800216cb  mov     [rbp+var_10], 0
0x1800216d2  mov     rax, [rcx]
0x1800216d5  mov     rax, [rax+18h]
0x1800216d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216de  mov     ebx, eax
0x1800216e0  test    eax, eax
0x1800216e2  js      loc_18002180C
0x1800216e8  mov     r8d, [rbp+arg_0]; int
0x1800216ec  lea     rdx, CSCWMI_STR_PROP_PINNED; "Pinned"
0x1800216f3  mov     rcx, rdi; struct IWbemClassObject *
0x1800216f6  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x1800216fb  mov     ebx, eax
0x1800216fd  test    eax, eax
0x1800216ff  js      loc_180021836
0x180021705  mov     rcx, [rbp+var_8]
0x180021709  lea     r8, [rbp+var_10]
0x18002170d  lea     rdx, [rbp+arg_0]
0x180021711  mov     rax, [rcx]
0x180021714  mov     rax, [rax+20h]
0x180021718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002171d  mov     ebx, eax
0x18002171f  test    eax, eax
0x180021721  js      loc_180021860
0x180021727  cmp     [rbp+arg_0], 0
0x18002172b  jnz     short loc_180021732
0x18002172d  xor     r8d, r8d
0x180021730  jmp     short loc_180021740
0x180021732  mov     eax, [rbp+var_10]
0x180021735  neg     eax
0x180021737  sbb     r8d, r8d
0x18002173a  neg     r8d
0x18002173d  inc     r8d; unsigned int
0x180021740  lea     rdx, CSCWMI_STR_PROP_PINNEDFORUSER; "PinnedForUser"
0x180021747  mov     rcx, rdi; struct IWbemClassObject *
0x18002174a  call    ?WmiProp_SetUint32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; WmiProp_SetUint32Property(IWbemClassObject *,ushort const *,ulong)
0x18002174f  mov     ebx, eax
0x180021751  test    eax, eax
0x180021753  js      loc_180021860
0x180021759  mov     rcx, [rbp+var_8]
0x18002175d  lea     r8, [rbp+var_10]
0x180021761  lea     rdx, [rbp+arg_0]
0x180021765  mov     rax, [rcx]
0x180021768  mov     rax, [rax+28h]
0x18002176c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021771  mov     ebx, eax
0x180021773  test    eax, eax
0x180021775  js      short loc_1800217A6
0x180021777  cmp     [rbp+arg_0], 0
0x18002177b  jnz     short loc_180021782
0x18002177d  xor     r8d, r8d
0x180021780  jmp     short loc_180021790
0x180021782  mov     eax, [rbp+var_10]
0x180021785  neg     eax
0x180021787  sbb     r8d, r8d
0x18002178a  neg     r8d
0x18002178d  inc     r8d; unsigned int
0x180021790  lea     rdx, CSCWMI_STR_PROP_PINNEDFORUSERBYPOLICY; "PinnedForUserByPolicy"
0x180021797  mov     rcx, rdi; struct IWbemClassObject *
0x18002179a  call    ?WmiProp_SetUint32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; WmiProp_SetUint32Property(IWbemClassObject *,ushort const *,ulong)
0x18002179f  mov     ebx, eax
0x1800217a1  jmp     loc_18002188A
0x1800217a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217ad  cmp     rcx, r14
0x1800217b0  jz      loc_18002192D
0x1800217b6  test    byte ptr [rcx+1Ch], 2
0x1800217ba  jz      short loc_1800217D0
0x1800217bc  mov     rcx, [rcx+10h]
0x1800217c0  mov     edx, 1Dh
0x1800217c5  mov     r9d, ebx
0x1800217c8  mov     r8, r15
0x1800217cb  call    WPP_SF_d
0x1800217d0  test    ebx, ebx
0x1800217d2  js      loc_18002192D
0x1800217d8  mov     rcx, [rbp+var_8]
0x1800217dc  lea     r8, [rbp+var_10]
0x1800217e0  lea     rdx, [rbp+arg_0]
0x1800217e4  mov     rax, [rcx]
0x1800217e7  mov     rax, [rax+38h]
0x1800217eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217f0  mov     ebx, eax
0x1800217f2  test    eax, eax
0x1800217f4  js      loc_180021907
0x1800217fa  cmp     [rbp+arg_0], 0
0x1800217fe  jnz     loc_1800218E6
0x180021804  xor     r8d, r8d
0x180021807  jmp     loc_1800218F4
0x18002180c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021813  cmp     rcx, r14
0x180021816  jz      loc_18002192D
0x18002181c  test    byte ptr [rcx+1Ch], 2
0x180021820  jz      short loc_18002183D
0x180021822  mov     rcx, [rcx+10h]
0x180021826  mov     edx, 1Ah
0x18002182b  mov     r9d, eax
0x18002182e  mov     r8, r15
0x180021831  call    WPP_SF_d
0x180021836  mov     rcx, cs:WPP_GLOBAL_Control
0x18002183d  cmp     rcx, r14
0x180021840  jz      loc_18002192D
0x180021846  test    byte ptr [rcx+1Ch], 2
0x18002184a  jz      short loc_180021867
0x18002184c  mov     rcx, [rcx+10h]
0x180021850  mov     edx, 1Bh
0x180021855  mov     r9d, ebx
0x180021858  mov     r8, r15
0x18002185b  call    WPP_SF_d
0x180021860  mov     rcx, cs:WPP_GLOBAL_Control
0x180021867  cmp     rcx, r14
0x18002186a  jz      loc_18002192D
0x180021870  test    byte ptr [rcx+1Ch], 2
0x180021874  jz      short loc_180021891
0x180021876  mov     rcx, [rcx+10h]
0x18002187a  mov     edx, 1Ch
0x18002187f  mov     r9d, ebx
0x180021882  mov     r8, r15
0x180021885  call    WPP_SF_d
0x18002188a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021891  test    ebx, ebx
0x180021893  js      loc_1800217AD
0x180021899  mov     rcx, [rbp+var_8]
0x18002189d  lea     r8, [rbp+var_10]
0x1800218a1  lea     rdx, [rbp+arg_0]
0x1800218a5  mov     rax, [rcx]
0x1800218a8  mov     rax, [rax+30h]
0x1800218ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218b1  mov     ebx, eax
0x1800218b3  test    eax, eax
0x1800218b5  js      short loc_18002192D
0x1800218b7  cmp     [rbp+arg_0], 0
0x1800218bb  jnz     short loc_1800218C2
0x1800218bd  xor     r8d, r8d
0x1800218c0  jmp     short loc_1800218D0
0x1800218c2  mov     eax, [rbp+var_10]
0x1800218c5  neg     eax
0x1800218c7  sbb     r8d, r8d
0x1800218ca  neg     r8d
0x1800218cd  inc     r8d; unsigned int
0x1800218d0  lea     rdx, CSCWMI_STR_PROP_PINNEDFORCOMPUTER; "PinnedForComputer"
0x1800218d7  mov     rcx, rdi; struct IWbemClassObject *
0x1800218da  call    ?WmiProp_SetUint32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; WmiProp_SetUint32Property(IWbemClassObject *,ushort const *,ulong)
0x1800218df  mov     ebx, eax
0x1800218e1  jmp     loc_1800217D0
0x1800218e6  mov     eax, [rbp+var_10]
0x1800218e9  neg     eax
0x1800218eb  sbb     r8d, r8d
0x1800218ee  neg     r8d
0x1800218f1  inc     r8d; unsigned int
0x1800218f4  lea     rdx, CSCWMI_STR_PROP_PINNEDFORFOLDERREDIR; "PinnedForFolderRedirection"
0x1800218fb  mov     rcx, rdi; struct IWbemClassObject *
0x1800218fe  call    ?WmiProp_SetUint32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; WmiProp_SetUint32Property(IWbemClassObject *,ushort const *,ulong)
0x180021903  mov     ebx, eax
0x180021905  jmp     short loc_18002192D
0x180021907  mov     rcx, cs:WPP_GLOBAL_Control
0x18002190e  cmp     rcx, r14
0x180021911  jz      short loc_18002192D
0x180021913  test    byte ptr [rcx+1Ch], 2
0x180021917  jz      short loc_18002192D
0x180021919  mov     rcx, [rcx+10h]
0x18002191d  mov     edx, 1Eh
0x180021922  mov     r9d, eax
0x180021925  mov     r8, r15
0x180021928  call    WPP_SF_d
0x18002192d  mov     rcx, [rbp+var_8]
0x180021931  mov     rax, [rcx]
0x180021934  mov     rax, [rax+10h]
0x180021938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002193d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021944  cmp     rcx, r14
0x180021947  jz      short loc_180021966
0x180021949  test    dword ptr [rcx+1Ch], 4000000h
0x180021950  jz      short loc_180021966
0x180021952  mov     rcx, [rcx+10h]
0x180021956  mov     edx, 20h ; ' '
0x18002195b  mov     r9d, ebx
0x18002195e  mov     r8, r15
0x180021961  call    WPP_SF_d
0x180021966  mov     rdi, [rsp+30h+arg_10]
0x18002196b  mov     eax, ebx
0x18002196d  mov     rbx, [rsp+30h+arg_8]
0x180021972  add     rsp, 30h
0x180021976  pop     r15
0x180021978  pop     r14
0x18002197a  pop     rbp
0x18002197b  retn
0x18002197c  cmp     eax, 80004002h
0x180021981  jnz     short loc_18002193D
0x180021983  mov     rcx, cs:WPP_GLOBAL_Control
0x18002198a  cmp     rcx, r14
0x18002198d  jz      short loc_1800219B0
0x18002198f  test    dword ptr [rcx+1Ch], 4000000h
0x180021996  jz      short loc_1800219B0
0x180021998  mov     rcx, [rcx+10h]
0x18002199c  mov     edx, 1Fh
0x1800219a1  mov     r8, r15
0x1800219a4  call    WPP_SF_
0x1800219a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219b0  mov     ebx, 80070032h
0x1800219b5  jmp     short loc_180021944
```
