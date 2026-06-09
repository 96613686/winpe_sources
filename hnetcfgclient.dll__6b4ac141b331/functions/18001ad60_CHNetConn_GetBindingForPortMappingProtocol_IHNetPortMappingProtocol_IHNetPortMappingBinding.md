# CHNetConn::GetBindingForPortMappingProtocol(IHNetPortMappingProtocol *,IHNetPortMappingBinding * *)

- ea: `0x18001ad60`
- end: `0x18001b107`
- name: `?GetBindingForPortMappingProtocol@CHNetConn@@UEAAJPEAUIHNetPortMappingProtocol@@PEAPEAUIHNetPortMappingBinding@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CHNetConn *this, __int64 (__fastcall ***)(struct IHNetPortMappingProtocol *, GUID *, CHNetPortMappingBinding **), struct IHNetPortMappingBinding **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x1800100f4`
- `0x18001ad60`
- `0x180024bd8`
- `0x1800294f8`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001af6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001af6d`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetBindingForPortMappingProtocol(
        CHNetConn *this,
        __int64 (__fastcall ***a2)(struct IHNetPortMappingProtocol *, GUID *, CHNetPortMappingBinding **),
        struct IHNetPortMappingBinding **a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  __int64 (__fastcall **v11)(struct IHNetPortMappingProtocol *, GUID *, CHNetPortMappingBinding **); // rax
  int v12; // eax
  int PortMappingBindingInstance; // eax
  int v14; // eax
  CHNetPortMappingBinding *v15; // rdi
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-10h] BYREF
  struct IWbemClassObject *v21; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 v22; // [rsp+78h] [rbp+38h] BYREF
  CHNetPortMappingBinding *v23; // [rsp+88h] [rbp+48h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  bstrString = 0;
  v21 = 0;
  v22 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = -2147467261;
      if ( v6 == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)v6 + 28) & 8) == 0 || *((_BYTE *)v6 + 25) < 2u )
        goto LABEL_63;
      v8 = 160;
      goto LABEL_10;
    }
    *a3 = 0;
    v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IHNetPortMappingProtocol *, GUID *, CHNetPortMappingBinding **), unsigned __int16 *))(*a2)[7])(
            a2,
            &v22);
    v7 = v10;
    if ( v10 < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_63;
      v8 = 161;
LABEL_60:
      v9 = (unsigned int)v10;
      goto LABEL_61;
    }
    if ( !v10 )
    {
      v11 = *a2;
      v23 = 0;
      v10 = (*v11)((struct IHNetPortMappingProtocol *)a2, &GUID_3f1e85f9_a5b4_487e_b0a0_b137973be622, &v23);
      v7 = v10;
      if ( !v10 )
      {
        v12 = (*(__int64 (__fastcall **)(CHNetPortMappingBinding *, BSTR *))(*(_QWORD *)v23 + 24LL))(v23, &bstrString);
        v7 = v12;
        if ( v12 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            162,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v12);
        }
        (*(void (__fastcall **)(CHNetPortMappingBinding *))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v7 )
          goto LABEL_62;
        PortMappingBindingInstance = GetPortMappingBindingInstance(
                                       *((struct IWbemServices **)this + 8),
                                       *((unsigned __int16 **)this + 15),
                                       *((unsigned __int16 **)this + 9),
                                       bstrString,
                                       v22,
                                       &v21);
        v7 = PortMappingBindingInstance;
        if ( PortMappingBindingInstance < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            164,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)PortMappingBindingInstance);
        }
        SysFreeString(bstrString);
        if ( v7 )
          goto LABEL_62;
        v23 = 0;
        v14 = ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(&v23);
        v7 = v14;
        if ( v14 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              165,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)v14);
          }
          goto LABEL_54;
        }
        if ( v14 )
        {
LABEL_54:
          ((void (__fastcall *)(struct IWbemClassObject *))v21->lpVtbl->Release)(v21);
          goto LABEL_62;
        }
        v15 = v23;
        (*(void (__fastcall **)(CHNetPortMappingBinding *))(*(_QWORD *)v23 + 8LL))(v23);
        v16 = CHNetPortMappingBinding::Initialize(v15, *((struct IWbemServices **)this + 8), v21);
        v7 = v16;
        if ( v16 >= 0 )
        {
          if ( v16 )
            goto LABEL_53;
          v16 = (**(__int64 (__fastcall ***)(CHNetPortMappingBinding *, GUID *, struct IHNetPortMappingBinding **))v15)(
                  v15,
                  &GUID_85d18b80_3032_11d4_9348_00c04f8eeb71,
                  a3);
          v7 = v16;
          if ( v16 >= 0 )
            goto LABEL_53;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v18 = 167;
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_53;
          }
          v18 = 166;
        }
        WPP_SF_d(v17[2], v18, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)v16);
LABEL_53:
        (*(void (__fastcall **)(CHNetPortMappingBinding *))(*(_QWORD *)v15 + 16LL))(v15);
        goto LABEL_54;
      }
      if ( v10 < 0 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v7;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_63;
        v8 = 163;
        goto LABEL_60;
      }
    }
LABEL_62:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_63;
  }
  v7 = -2147024809;
  if ( v6 == &WPP_GLOBAL_Control )
    return v7;
  if ( (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v8 = 159;
LABEL_10:
    v9 = v7;
LABEL_61:
    WPP_SF_d(v6[2], v8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v9);
    goto LABEL_62;
  }
LABEL_63:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 168, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18001ad60  mov     [rsp-28h+arg_0], rbx
0x18001ad65  push    rbp
0x18001ad66  push    rsi
0x18001ad67  push    rdi
0x18001ad68  push    r13
0x18001ad6a  push    r14
0x18001ad6c  mov     rbp, rsp
0x18001ad6f  sub     rsp, 40h
0x18001ad73  mov     rsi, r8
0x18001ad76  mov     rdi, rdx
0x18001ad79  mov     r14, rcx
0x18001ad7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad83  lea     r13, WPP_GLOBAL_Control
0x18001ad8a  cmp     rcx, r13
0x18001ad8d  jz      short loc_18001ADB7
0x18001ad8f  test    byte ptr [rcx+1Ch], 8
0x18001ad93  jz      short loc_18001ADB7
0x18001ad95  cmp     byte ptr [rcx+19h], 6
0x18001ad99  jb      short loc_18001ADB7
0x18001ad9b  mov     rcx, [rcx+10h]
0x18001ad9f  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ada6  mov     edx, 9Eh
0x18001adab  call    WPP_SF_
0x18001adb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adb7  xor     eax, eax
0x18001adb9  mov     [rbp+bstrString], 0
0x18001adc1  mov     [rbp+var_8], 0
0x18001adc9  mov     [rbp+arg_8], ax
0x18001adcd  test    rdi, rdi
0x18001add0  jnz     short loc_18001AE01
0x18001add2  mov     ebx, 80070057h
0x18001add7  cmp     rcx, r13
0x18001adda  jz      loc_18001B0F4
0x18001ade0  test    byte ptr [rcx+1Ch], 8
0x18001ade4  jz      loc_18001B0CB
0x18001adea  cmp     byte ptr [rcx+19h], 2
0x18001adee  jb      loc_18001B0CB
0x18001adf4  mov     edx, 9Fh
0x18001adf9  mov     r9d, ebx
0x18001adfc  jmp     loc_18001B0B4
0x18001ae01  test    rsi, rsi
0x18001ae04  jnz     short loc_18001AE2F
0x18001ae06  mov     ebx, 80004003h
0x18001ae0b  cmp     rcx, r13
0x18001ae0e  jz      loc_18001B0F4
0x18001ae14  test    byte ptr [rcx+1Ch], 8
0x18001ae18  jz      loc_18001B0CB
0x18001ae1e  cmp     byte ptr [rcx+19h], 2
0x18001ae22  jb      loc_18001B0CB
0x18001ae28  mov     edx, 0A0h
0x18001ae2d  jmp     short loc_18001ADF9
0x18001ae2f  mov     [rsi], rax
0x18001ae32  lea     rdx, [rbp+arg_8]
0x18001ae36  mov     rax, [rdi]
0x18001ae39  mov     rcx, rdi
0x18001ae3c  mov     rax, [rax+38h]
0x18001ae40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae45  mov     ebx, eax
0x18001ae47  test    eax, eax
0x18001ae49  jns     short loc_18001AE79
0x18001ae4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae52  cmp     rcx, r13
0x18001ae55  jz      loc_18001B0F4
0x18001ae5b  test    byte ptr [rcx+1Ch], 8
0x18001ae5f  jz      loc_18001B0CB
0x18001ae65  cmp     byte ptr [rcx+19h], 2
0x18001ae69  jb      loc_18001B0CB
0x18001ae6f  mov     edx, 0A1h
0x18001ae74  jmp     loc_18001B0B1
0x18001ae79  jnz     loc_18001B0C4
0x18001ae7f  mov     rax, [rdi]
0x18001ae82  lea     r8, [rbp+arg_18]
0x18001ae86  lea     rdx, _GUID_3f1e85f9_a5b4_487e_b0a0_b137973be622
0x18001ae8d  mov     [rbp+arg_18], 0
0x18001ae95  mov     rcx, rdi
0x18001ae98  mov     rax, [rax]
0x18001ae9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aea0  mov     ebx, eax
0x18001aea2  test    eax, eax
0x18001aea4  jnz     loc_18001B092
0x18001aeaa  mov     rcx, [rbp+arg_18]
0x18001aeae  lea     rdx, [rbp+bstrString]
0x18001aeb2  mov     rax, [rcx]
0x18001aeb5  mov     rax, [rax+18h]
0x18001aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aebe  mov     ebx, eax
0x18001aec0  test    eax, eax
0x18001aec2  jns     short loc_18001AEF4
0x18001aec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aecb  cmp     rcx, r13
0x18001aece  jz      short loc_18001AEF4
0x18001aed0  test    byte ptr [rcx+1Ch], 8
0x18001aed4  jz      short loc_18001AEF4
0x18001aed6  cmp     byte ptr [rcx+19h], 2
0x18001aeda  jb      short loc_18001AEF4
0x18001aedc  mov     rcx, [rcx+10h]
0x18001aee0  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001aee7  mov     edx, 0A2h
0x18001aeec  mov     r9d, eax
0x18001aeef  call    WPP_SF_d
0x18001aef4  mov     rcx, [rbp+arg_18]
0x18001aef8  mov     rax, [rcx]
0x18001aefb  mov     rax, [rax+10h]
0x18001aeff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af04  test    ebx, ebx
0x18001af06  jnz     loc_18001B0C4
0x18001af0c  mov     r9, [rbp+bstrString]; unsigned __int16 *
0x18001af10  lea     rax, [rbp+var_8]
0x18001af14  mov     r8, [r14+48h]; unsigned __int16 *
0x18001af18  mov     rdx, [r14+78h]; unsigned __int16 *
0x18001af1c  mov     rcx, [r14+40h]; struct IWbemServices *
0x18001af20  mov     [rsp+40h+var_18], rax; struct IWbemClassObject **
0x18001af25  movzx   eax, [rbp+arg_8]
0x18001af29  mov     [rsp+40h+var_20], ax; unsigned __int16
0x18001af2e  call    ?GetPortMappingBindingInstance@@YAJPEAUIWbemServices@@PEAG11GPEAPEAUIWbemClassObject@@@Z; GetPortMappingBindingInstance(IWbemServices *,ushort *,ushort *,ushort *,ushort,IWbemClassObject * *)
0x18001af33  mov     ebx, eax
0x18001af35  test    eax, eax
0x18001af37  jns     short loc_18001AF69
0x18001af39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af40  cmp     rcx, r13
0x18001af43  jz      short loc_18001AF69
0x18001af45  test    byte ptr [rcx+1Ch], 8
0x18001af49  jz      short loc_18001AF69
0x18001af4b  cmp     byte ptr [rcx+19h], 2
0x18001af4f  jb      short loc_18001AF69
0x18001af51  mov     rcx, [rcx+10h]
0x18001af55  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001af5c  mov     edx, 0A4h
0x18001af61  mov     r9d, eax
0x18001af64  call    WPP_SF_d
0x18001af69  mov     rcx, [rbp+bstrString]; bstrString
0x18001af6d  call    cs:__imp_SysFreeString
0x18001af73  test    ebx, ebx
0x18001af75  jnz     loc_18001B0C4
0x18001af7b  lea     rcx, [rbp+arg_18]
0x18001af7f  mov     [rbp+arg_18], 0
0x18001af87  call    ?CreateInstance@?$CComObject@VCHNetPortMappingBinding@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNetPortMappingBinding>::CreateInstance(ATL::CComObject<CHNetPortMappingBinding> * *)
0x18001af8c  mov     ebx, eax
0x18001af8e  test    eax, eax
0x18001af90  jns     short loc_18001AFD3
0x18001af92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af99  cmp     rcx, r13
0x18001af9c  jz      loc_18001B080
0x18001afa2  test    byte ptr [rcx+1Ch], 8
0x18001afa6  jz      loc_18001B080
0x18001afac  cmp     byte ptr [rcx+19h], 2
0x18001afb0  jb      loc_18001B080
0x18001afb6  mov     rcx, [rcx+10h]
0x18001afba  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001afc1  mov     edx, 0A5h
0x18001afc6  mov     r9d, eax
0x18001afc9  call    WPP_SF_d
0x18001afce  jmp     loc_18001B080
0x18001afd3  jnz     loc_18001B080
0x18001afd9  mov     rdi, [rbp+arg_18]
0x18001afdd  mov     rcx, rdi
0x18001afe0  mov     rax, [rdi]
0x18001afe3  mov     rax, [rax+8]
0x18001afe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afec  mov     r8, [rbp+var_8]; struct IWbemClassObject *
0x18001aff0  mov     rcx, rdi; this
0x18001aff3  mov     rdx, [r14+40h]; struct IWbemServices *
0x18001aff7  call    ?Initialize@CHNetPortMappingBinding@@QEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@@Z; CHNetPortMappingBinding::Initialize(IWbemServices *,IWbemClassObject *)
0x18001affc  mov     ebx, eax
0x18001affe  test    eax, eax
0x18001b000  jns     short loc_18001B021
0x18001b002  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b009  cmp     rcx, r13
0x18001b00c  jz      short loc_18001B071
0x18001b00e  test    byte ptr [rcx+1Ch], 8
0x18001b012  jz      short loc_18001B071
0x18001b014  cmp     byte ptr [rcx+19h], 2
0x18001b018  jb      short loc_18001B071
0x18001b01a  mov     edx, 0A6h
0x18001b01f  jmp     short loc_18001B05E
0x18001b021  jnz     short loc_18001B071
0x18001b023  mov     rax, [rdi]
0x18001b026  lea     rdx, _GUID_85d18b80_3032_11d4_9348_00c04f8eeb71
0x18001b02d  mov     r8, rsi
0x18001b030  mov     rcx, rdi
0x18001b033  mov     rax, [rax]
0x18001b036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b03b  mov     ebx, eax
0x18001b03d  test    eax, eax
0x18001b03f  jns     short loc_18001B071
0x18001b041  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b048  cmp     rcx, r13
0x18001b04b  jz      short loc_18001B071
0x18001b04d  test    byte ptr [rcx+1Ch], 8
0x18001b051  jz      short loc_18001B071
0x18001b053  cmp     byte ptr [rcx+19h], 2
0x18001b057  jb      short loc_18001B071
0x18001b059  mov     edx, 0A7h
0x18001b05e  mov     rcx, [rcx+10h]
0x18001b062  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001b069  mov     r9d, eax
0x18001b06c  call    WPP_SF_d
0x18001b071  mov     rax, [rdi]
0x18001b074  mov     rcx, rdi
0x18001b077  mov     rax, [rax+10h]
0x18001b07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b080  mov     rcx, [rbp+var_8]
0x18001b084  mov     rax, [rcx]
0x18001b087  mov     rax, [rax+10h]
0x18001b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b090  jmp     short loc_18001B0C4
0x18001b092  jns     short loc_18001B0C4
0x18001b094  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b09b  cmp     rcx, r13
0x18001b09e  jz      short loc_18001B0F4
0x18001b0a0  test    byte ptr [rcx+1Ch], 8
0x18001b0a4  jz      short loc_18001B0CB
0x18001b0a6  cmp     byte ptr [rcx+19h], 2
0x18001b0aa  jb      short loc_18001B0CB
0x18001b0ac  mov     edx, 0A3h
0x18001b0b1  mov     r9d, eax
0x18001b0b4  mov     rcx, [rcx+10h]
0x18001b0b8  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001b0bf  call    WPP_SF_d
0x18001b0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0cb  cmp     rcx, r13
0x18001b0ce  jz      short loc_18001B0F4
0x18001b0d0  test    byte ptr [rcx+1Ch], 8
0x18001b0d4  jz      short loc_18001B0F4
0x18001b0d6  cmp     byte ptr [rcx+19h], 6
0x18001b0da  jb      short loc_18001B0F4
0x18001b0dc  mov     rcx, [rcx+10h]
0x18001b0e0  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001b0e7  mov     edx, 0A8h
0x18001b0ec  mov     r9d, ebx
0x18001b0ef  call    WPP_SF_d
0x18001b0f4  mov     eax, ebx
0x18001b0f6  mov     rbx, [rsp+40h+arg_0]
0x18001b0fb  add     rsp, 40h
0x18001b0ff  pop     r14
0x18001b101  pop     r13
0x18001b103  pop     rdi
0x18001b104  pop     rsi
0x18001b105  pop     rbp
0x18001b106  retn
```
