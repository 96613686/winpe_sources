# CHNetConn::CreatePortMappingBindings(void)

- ea: `0x1800197b8`
- end: `0x180019b21`
- name: `?CreatePortMappingBindings@CHNetConn@@IEAAJXZ`
- size: `873`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a140`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x1800197b8`
- `0x1800294f8`
- `0x180029a74`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019822`
- `OLEAUT32!__imp_SysAllocString` at `0x180019822`
- `OLEAUT32!__imp_SysFreeString` at `0x18001989f`
- `OLEAUT32!__imp_SysFreeString` at `0x180019a1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001989f`
- `OLEAUT32!__imp_SysFreeString` at `0x180019a1d`

## string_xrefs

- `0x180019813`: `HNet_PortMappingProtocol`

## pseudocode

```c
__int64 __fastcall CHNetConn::CreatePortMappingBindings(CHNetConn *this)
{
  OLECHAR *v2; // rax
  OLECHAR *v3; // rsi
  __int64 v4; // rcx
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int WmiPathFromObject; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r8
  unsigned __int16 *v12; // rdx
  struct IWbemServices *v13; // rcx
  int PortMappingBindingInstance; // eax
  PVOID *v15; // rcx
  __int64 result; // rax
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  struct IWbemClassObject *v18; // [rsp+48h] [rbp-28h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  int v21; // [rsp+A8h] [rbp+38h] BYREF
  struct IWbemClassObject *v22; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v23 = 0;
  v22 = 0;
  v20 = 0;
  v19 = 0;
  v2 = SysAllocString(L"HNet_PortMappingProtocol");
  bstrString = v2;
  v3 = v2;
  if ( v2 )
  {
    v4 = *((_QWORD *)this + 8);
    v23 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64))(*(_QWORD *)v4 + 144LL))(v4, v2, 48);
    v6 = v5;
    if ( v5 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        248,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v5);
    }
    SysFreeString(v3);
    if ( v6 )
      goto LABEL_49;
    v21 = 0;
    while ( 1 )
    {
      v22 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v23 + 32LL))(
             v23,
             0xFFFFFFFFLL,
             1,
             &v22,
             &v21);
      v6 = v7;
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            250,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v7);
        }
LABEL_44:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_49:
        v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_50:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 && *((_BYTE *)v15 + 25) >= 6u )
          WPP_SF_d(v15[2], 254, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v6);
        goto LABEL_54;
      }
      if ( v21 != 1 )
        goto LABEL_44;
      WmiPathFromObject = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, __int128 *, _QWORD, _QWORD))v22->lpVtbl->Get)(
                            v22,
                            L"Port",
                            0,
                            &v19,
                            0,
                            0);
      v6 = WmiPathFromObject;
      if ( WmiPathFromObject < 0 )
        break;
      if ( !WmiPathFromObject )
      {
        WmiPathFromObject = GetWmiPathFromObject(v22, &bstrString);
        v6 = WmiPathFromObject;
        if ( WmiPathFromObject >= 0 )
        {
          if ( !WmiPathFromObject )
          {
            v11 = (unsigned __int16 *)*((_QWORD *)this + 9);
            v12 = (unsigned __int16 *)*((_QWORD *)this + 15);
            v13 = (struct IWbemServices *)*((_QWORD *)this + 8);
            v18 = 0;
            PortMappingBindingInstance = GetPortMappingBindingInstance(v13, v12, v11, bstrString, WORD4(v19), &v18);
            v6 = PortMappingBindingInstance;
            if ( PortMappingBindingInstance < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                253,
                WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                (unsigned int)PortMappingBindingInstance);
            }
            SysFreeString(bstrString);
            if ( v6 )
            {
              if ( (unsigned int)(v6 + 2147217406) <= 1 )
                v6 = 0;
            }
            else
            {
              ((void (__fastcall *)(struct IWbemClassObject *))v18->lpVtbl->Release)(v18);
            }
          }
          goto LABEL_37;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 252;
LABEL_26:
          WPP_SF_d(v9[2], v10, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)WmiPathFromObject);
        }
      }
LABEL_37:
      ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
      if ( v6 < 0 || v21 != 1 )
        goto LABEL_44;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v10 = 251;
    goto LABEL_26;
  }
  v6 = -2147024882;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147942414LL);
      goto LABEL_49;
    }
    goto LABEL_50;
  }
LABEL_54:
  result = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return result;
}

```

## disassembly

```asm
0x1800197b8  push    rbp
0x1800197ba  push    rbx
0x1800197bb  push    rsi
0x1800197bc  push    r13
0x1800197be  push    r14
0x1800197c0  mov     rbp, rsp
0x1800197c3  sub     rsp, 70h
0x1800197c7  mov     r14, rcx
0x1800197ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197d1  lea     r13, WPP_GLOBAL_Control
0x1800197d8  cmp     rcx, r13
0x1800197db  jz      short loc_1800197FE
0x1800197dd  test    byte ptr [rcx+1Ch], 8
0x1800197e1  jz      short loc_1800197FE
0x1800197e3  cmp     byte ptr [rcx+19h], 6
0x1800197e7  jb      short loc_1800197FE
0x1800197e9  mov     rcx, [rcx+10h]
0x1800197ed  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x1800197f4  mov     edx, 0F7h
0x1800197f9  call    WPP_SF_
0x1800197fe  xorps   xmm0, xmm0
0x180019801  mov     [rbp+arg_18], 0
0x180019809  xor     eax, eax
0x18001980b  mov     [rbp+arg_10], 0
0x180019813  lea     rcx, ?c_wszHnetPortMappingProtocol@@3QBGB; "HNet_PortMappingProtocol"
0x18001981a  mov     [rbp+var_10], rax
0x18001981e  movups  [rbp+var_20], xmm0
0x180019822  call    cs:__imp_SysAllocString
0x180019828  mov     [rbp+bstrString], rax
0x18001982c  mov     rsi, rax
0x18001982f  test    rax, rax
0x180019832  jz      loc_180019AA9
0x180019838  mov     rcx, [r14+40h]
0x18001983c  lea     rdx, [rbp+arg_18]
0x180019840  mov     [rbp+arg_18], 0
0x180019848  xor     r9d, r9d
0x18001984b  mov     qword ptr [rsp+70h+var_50], rdx
0x180019850  mov     rdx, rsi
0x180019853  mov     rax, [rcx]
0x180019856  lea     r8d, [r9+30h]
0x18001985a  mov     rax, [rax+90h]
0x180019861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019866  mov     ebx, eax
0x180019868  test    eax, eax
0x18001986a  jns     short loc_18001989C
0x18001986c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019873  cmp     rcx, r13
0x180019876  jz      short loc_18001989C
0x180019878  test    byte ptr [rcx+1Ch], 8
0x18001987c  jz      short loc_18001989C
0x18001987e  cmp     byte ptr [rcx+19h], 2
0x180019882  jb      short loc_18001989C
0x180019884  mov     rcx, [rcx+10h]
0x180019888  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001988f  mov     edx, 0F8h
0x180019894  mov     r9d, eax
0x180019897  call    WPP_SF_d
0x18001989c  mov     rcx, rsi; bstrString
0x18001989f  call    cs:__imp_SysFreeString
0x1800198a5  test    ebx, ebx
0x1800198a7  jnz     loc_180019ADE
0x1800198ad  mov     [rbp+arg_8], ebx
0x1800198b0  lea     esi, [rbx+1]
0x1800198b3  mov     rcx, [rbp+arg_18]
0x1800198b7  lea     rdx, [rbp+arg_8]
0x1800198bb  mov     [rbp+arg_10], 0
0x1800198c3  lea     r9, [rbp+arg_10]
0x1800198c7  mov     qword ptr [rsp+70h+var_50], rdx
0x1800198cc  mov     r8d, esi
0x1800198cf  or      edx, 0FFFFFFFFh
0x1800198d2  mov     rax, [rcx]
0x1800198d5  mov     rax, [rax+20h]
0x1800198d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198de  mov     ebx, eax
0x1800198e0  test    eax, eax
0x1800198e2  js      loc_180019A67
0x1800198e8  mov     eax, [rbp+arg_8]
0x1800198eb  cmp     eax, esi
0x1800198ed  jnz     loc_180019A97
0x1800198f3  mov     rcx, [rbp+arg_10]
0x1800198f7  lea     r9, [rbp+var_20]
0x1800198fb  mov     [rsp+70h+var_48], 0
0x180019904  lea     rdx, ?c_wszPort@@3QBGB; "Port"
0x18001990b  xor     r8d, r8d
0x18001990e  mov     qword ptr [rsp+70h+var_50], 0
0x180019917  mov     rax, [rcx]
0x18001991a  mov     rax, [rax+20h]
0x18001991e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019923  mov     ebx, eax
0x180019925  test    eax, eax
0x180019927  jns     short loc_180019954
0x180019929  mov     rcx, cs:WPP_GLOBAL_Control
0x180019930  cmp     rcx, r13
0x180019933  jz      loc_180019A46
0x180019939  test    byte ptr [rcx+1Ch], 8
0x18001993d  jz      loc_180019A46
0x180019943  cmp     byte ptr [rcx+19h], 2
0x180019947  jb      loc_180019A46
0x18001994d  mov     edx, 0FBh
0x180019952  jmp     short loc_180019996
0x180019954  jnz     loc_180019A46
0x18001995a  mov     rcx, [rbp+arg_10]; struct IWbemClassObject *
0x18001995e  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180019962  call    ?GetWmiPathFromObject@@YAJPEAUIWbemClassObject@@PEAPEAG@Z; GetWmiPathFromObject(IWbemClassObject *,ushort * *)
0x180019967  mov     ebx, eax
0x180019969  test    eax, eax
0x18001996b  jns     short loc_1800199AE
0x18001996d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019974  cmp     rcx, r13
0x180019977  jz      loc_180019A46
0x18001997d  test    byte ptr [rcx+1Ch], 8
0x180019981  jz      loc_180019A46
0x180019987  cmp     byte ptr [rcx+19h], 2
0x18001998b  jb      loc_180019A46
0x180019991  mov     edx, 0FCh
0x180019996  mov     rcx, [rcx+10h]
0x18001999a  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x1800199a1  mov     r9d, eax
0x1800199a4  call    WPP_SF_d
0x1800199a9  jmp     loc_180019A46
0x1800199ae  jnz     loc_180019A46
0x1800199b4  mov     r9, [rbp+bstrString]; unsigned __int16 *
0x1800199b8  lea     rax, [rbp+var_28]
0x1800199bc  mov     r8, [r14+48h]; unsigned __int16 *
0x1800199c0  mov     rdx, [r14+78h]; unsigned __int16 *
0x1800199c4  mov     rcx, [r14+40h]; struct IWbemServices *
0x1800199c8  mov     [rsp+70h+var_48], rax; struct IWbemClassObject **
0x1800199cd  movzx   eax, word ptr [rbp+var_20+8]
0x1800199d1  mov     [rsp+70h+var_50], ax; unsigned __int16
0x1800199d6  mov     [rbp+var_28], 0
0x1800199de  call    ?GetPortMappingBindingInstance@@YAJPEAUIWbemServices@@PEAG11GPEAPEAUIWbemClassObject@@@Z; GetPortMappingBindingInstance(IWbemServices *,ushort *,ushort *,ushort *,ushort,IWbemClassObject * *)
0x1800199e3  mov     ebx, eax
0x1800199e5  test    eax, eax
0x1800199e7  jns     short loc_180019A19
0x1800199e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199f0  cmp     rcx, r13
0x1800199f3  jz      short loc_180019A19
0x1800199f5  test    byte ptr [rcx+1Ch], 8
0x1800199f9  jz      short loc_180019A19
0x1800199fb  cmp     byte ptr [rcx+19h], 2
0x1800199ff  jb      short loc_180019A19
0x180019a01  mov     rcx, [rcx+10h]
0x180019a05  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019a0c  mov     edx, 0FDh
0x180019a11  mov     r9d, eax
0x180019a14  call    WPP_SF_d
0x180019a19  mov     rcx, [rbp+bstrString]; bstrString
0x180019a1d  call    cs:__imp_SysFreeString
0x180019a23  test    ebx, ebx
0x180019a25  jnz     short loc_180019A39
0x180019a27  mov     rcx, [rbp+var_28]
0x180019a2b  mov     rax, [rcx]
0x180019a2e  mov     rax, [rax+10h]
0x180019a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a37  jmp     short loc_180019A46
0x180019a39  lea     ecx, [rbx+7FFBEFFEh]
0x180019a3f  xor     eax, eax
0x180019a41  cmp     ecx, esi
0x180019a43  cmovbe  ebx, eax
0x180019a46  mov     rcx, [rbp+arg_10]
0x180019a4a  mov     rax, [rcx]
0x180019a4d  mov     rax, [rax+10h]
0x180019a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a56  test    ebx, ebx
0x180019a58  js      short loc_180019A97
0x180019a5a  mov     eax, [rbp+arg_8]
0x180019a5d  cmp     eax, esi
0x180019a5f  jz      loc_1800198B3
0x180019a65  jmp     short loc_180019A97
0x180019a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a6e  cmp     rcx, r13
0x180019a71  jz      short loc_180019A97
0x180019a73  test    byte ptr [rcx+1Ch], 8
0x180019a77  jz      short loc_180019A97
0x180019a79  cmp     byte ptr [rcx+19h], 2
0x180019a7d  jb      short loc_180019A97
0x180019a7f  mov     rcx, [rcx+10h]
0x180019a83  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019a8a  mov     edx, 0FAh
0x180019a8f  mov     r9d, eax
0x180019a92  call    WPP_SF_d
0x180019a97  mov     rcx, [rbp+arg_18]
0x180019a9b  mov     rax, [rcx]
0x180019a9e  mov     rax, [rax+10h]
0x180019aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aa7  jmp     short loc_180019ADE
0x180019aa9  mov     ebx, 8007000Eh
0x180019aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ab5  cmp     rcx, r13
0x180019ab8  jz      short loc_180019B0E
0x180019aba  test    byte ptr [rcx+1Ch], 8
0x180019abe  jz      short loc_180019AE5
0x180019ac0  cmp     byte ptr [rcx+19h], 2
0x180019ac4  jb      short loc_180019AE5
0x180019ac6  mov     rcx, [rcx+10h]
0x180019aca  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019ad1  mov     edx, 0F9h
0x180019ad6  mov     r9d, ebx
0x180019ad9  call    WPP_SF_d
0x180019ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ae5  cmp     rcx, r13
0x180019ae8  jz      short loc_180019B0E
0x180019aea  test    byte ptr [rcx+1Ch], 8
0x180019aee  jz      short loc_180019B0E
0x180019af0  cmp     byte ptr [rcx+19h], 6
0x180019af4  jb      short loc_180019B0E
0x180019af6  mov     rcx, [rcx+10h]
0x180019afa  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x180019b01  mov     edx, 0FEh
0x180019b06  mov     r9d, ebx
0x180019b09  call    WPP_SF_d
0x180019b0e  xor     eax, eax
0x180019b10  test    ebx, ebx
0x180019b12  cmovs   eax, ebx
0x180019b15  add     rsp, 70h
0x180019b19  pop     r14
0x180019b1b  pop     r13
0x180019b1d  pop     rsi
0x180019b1e  pop     rbx
0x180019b1f  pop     rbp
0x180019b20  retn
```
