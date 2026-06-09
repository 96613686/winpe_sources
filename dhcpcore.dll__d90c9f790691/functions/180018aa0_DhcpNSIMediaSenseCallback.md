# DhcpNSIMediaSenseCallback

- ea: `0x180018aa0`
- end: `0x180018cce`
- name: `DhcpNSIMediaSenseCallback`
- size: `558`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180012c7c`
- `0x1800159d0`
- `0x180018aa0`
- `0x180019278`
- `0x1800218a4`
- `0x1800429cc`
- `0x180042b38`
- `0x18004a09c`
- `0x18004c5f8`
- `0x18004d1e0`
- `0x18004d4c0`
- `0x18004d958`
- `0x18004dd28`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x180018b6b`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x180018b6b`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180018b79`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180018b79`

## string_xrefs

- `0x180018af0`: `DeleteInstance`

## pseudocode

```c
void __fastcall DhcpNSIMediaSenseCallback(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v6; // rcx
  const char *v7; // rax
  int v8; // edi
  NTSTATUS v9; // ebx
  NET_IF_COMPARTMENT_SCOPE v10; // r15d
  int v11; // r12d
  int v12; // eax
  NET_LUID *v13; // rcx
  NET_LUID v14; // rax
  NTSTATUS v15; // eax
  UINT32 CompartmentId; // [rsp+30h] [rbp-10h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-8h] BYREF
  UINT32 CompartmentScope; // [rsp+88h] [rbp+48h] BYREF

  InterfaceLuid.Value = 0;
  v6 = a4;
  if ( a4 )
  {
    v6 = a4 - 1;
    if ( a4 == 1 )
    {
      v7 = "AddInstance";
    }
    else
    {
      v6 = a4 - 2;
      if ( a4 == 2 )
      {
        v7 = "DeleteInstance";
      }
      else if ( a4 == 3 )
      {
        v7 = "InitialNotification";
      }
      else
      {
        v7 = "Unknown";
      }
    }
  }
  else
  {
    v7 = "ParameterNotification";
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Js(v6, 88, (unsigned int)WPP_b85ebe6c12863f19dba418452b756303_Traceguids, InterfaceLuid.Value, (__int64)v7);
  CompartmentId = 0;
  v8 = 0;
  CompartmentScope = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 18, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids);
  v9 = 0;
  if ( DhcpGlobalCompartmentAware )
  {
    GetCurrentThreadCompartmentScope(&CompartmentScope, &CompartmentId);
    v6 = 0xFFFFFFFFLL;
    if ( CompartmentScope == -1 )
    {
LABEL_18:
      v10 = CompartmentScope;
      v11 = v8;
      goto LABEL_20;
    }
    v9 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
    if ( !v9 )
    {
      v8 = 1;
      goto LABEL_18;
    }
  }
  v10 = 0;
  v11 = 0;
LABEL_20:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dlD(v6, a2, a3, CompartmentScope, v8, v9);
  if ( !v9 )
  {
    if ( !a2 || (v12 = *(_DWORD *)(a2 + 8)) == 0 || (v13 = *(NET_LUID **)a2) == 0 || a4 == 3 )
    {
      v15 = DhcpEnumInterface();
      goto LABEL_40;
    }
    if ( v12 != 8 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_Dd(1025, 89, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, 8, *(_DWORD *)(a2 + 8));
      v9 = 87;
      goto LABEL_41;
    }
    v14.Value = v13->Value;
    InterfaceLuid.Value = v13->Value;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_q)(
        1028,
        90,
        WPP_b85ebe6c12863f19dba418452b756303_Traceguids,
        (NET_LUID)v14.Value);
      v14.Value = InterfaceLuid.Value;
    }
    if ( a4 != 2 && (unsigned int)((__int64 (__fastcall *)(_QWORD))IsInterfaceConnected)((NET_LUID)v14.Value) )
    {
      v15 = DhcpOnMediaConnected(&InterfaceLuid);
LABEL_40:
      v9 = v15;
      goto LABEL_41;
    }
    v9 = DhcpOnMediaDisconnected(&InterfaceLuid);
    if ( !v9 && a4 == 2 )
      TryDeleteDisconnectedContext(&InterfaceLuid);
  }
LABEL_41:
  if ( v11 )
    DhcpRevertThreadCompartmentScope(v10);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qD)(
      1028,
      91,
      WPP_b85ebe6c12863f19dba418452b756303_Traceguids,
      (NET_LUID)InterfaceLuid.Value,
      v9);
}

```

## disassembly

```asm
0x180018aa0  mov     [rsp-28h+arg_0], rbx
0x180018aa5  mov     [rsp-28h+arg_8], rsi
0x180018aaa  push    rbp
0x180018aab  push    rdi
0x180018aac  push    r12
0x180018aae  push    r14
0x180018ab0  push    r15
0x180018ab2  mov     rbp, rsp
0x180018ab5  sub     rsp, 40h
0x180018ab9  mov     qword ptr [rbp+InterfaceLuid], 0
0x180018ac1  mov     esi, r9d
0x180018ac4  mov     r14, rdx
0x180018ac7  mov     ecx, r9d
0x180018aca  test    r9d, r9d
0x180018acd  jz      short loc_180018B02
0x180018acf  sub     ecx, 1
0x180018ad2  jz      short loc_180018AF9
0x180018ad4  sub     ecx, 1
0x180018ad7  jz      short loc_180018AF0
0x180018ad9  cmp     ecx, 1
0x180018adc  jz      short loc_180018AE7
0x180018ade  lea     rax, aUnknown; "Unknown"
0x180018ae5  jmp     short loc_180018B09
0x180018ae7  lea     rax, aInitialnotific; "InitialNotification"
0x180018aee  jmp     short loc_180018B09
0x180018af0  lea     rax, aDeleteinstance; "DeleteInstance"
0x180018af7  jmp     short loc_180018B09
0x180018af9  lea     rax, aAddinstance; "AddInstance"
0x180018b00  jmp     short loc_180018B09
0x180018b02  lea     rax, aParameternotif; "ParameterNotification"
0x180018b09  test    byte ptr cs:xmmword_1800616A0, 10h
0x180018b10  jz      short loc_180018B2C
0x180018b12  mov     r9, qword ptr [rbp+InterfaceLuid]
0x180018b16  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180018b1d  mov     edx, 58h ; 'X'
0x180018b22  mov     [rsp+40h+var_20], rax
0x180018b27  call    WPP_SF_Js
0x180018b2c  mov     [rbp+CompartmentId], 0
0x180018b33  xor     edi, edi
0x180018b35  mov     [rbp+CompartmentScope], 0
0x180018b3c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180018b43  jz      short loc_180018B59
0x180018b45  lea     edx, [rdi+12h]
0x180018b48  mov     ecx, 404h
0x180018b4d  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x180018b54  call    WPP_SF_
0x180018b59  xor     ebx, ebx
0x180018b5b  cmp     cs:DhcpGlobalCompartmentAware, ebx
0x180018b61  jz      short loc_180018B91
0x180018b63  lea     rdx, [rbp+CompartmentId]; CompartmentId
0x180018b67  lea     rcx, [rbp+CompartmentScope]; CompartmentScope
0x180018b6b  call    cs:__imp_GetCurrentThreadCompartmentScope
0x180018b71  or      ecx, 0FFFFFFFFh; CompartmentScope
0x180018b74  cmp     [rbp+CompartmentScope], ecx
0x180018b77  jz      short loc_180018B88
0x180018b79  call    cs:__imp_SetCurrentThreadCompartmentScope
0x180018b7f  mov     ebx, eax
0x180018b81  test    eax, eax
0x180018b83  jnz     short loc_180018B91
0x180018b85  lea     edi, [rax+1]
0x180018b88  mov     r15d, [rbp+CompartmentScope]
0x180018b8c  mov     r12d, edi
0x180018b8f  jmp     short loc_180018B97
0x180018b91  xor     r15d, r15d
0x180018b94  xor     r12d, r12d
0x180018b97  test    byte ptr cs:xmmword_1800616A0, 10h
0x180018b9e  jz      short loc_180018BB1
0x180018ba0  mov     r9d, [rbp+CompartmentScope]
0x180018ba4  mov     [rsp+40h+var_18], ebx
0x180018ba8  mov     dword ptr [rsp+40h+var_20], edi
0x180018bac  call    WPP_SF_dlD
0x180018bb1  test    ebx, ebx
0x180018bb3  jnz     loc_180018C83
0x180018bb9  test    r14, r14
0x180018bbc  jz      loc_180018C7C
0x180018bc2  mov     eax, [r14+8]
0x180018bc6  test    eax, eax
0x180018bc8  jz      loc_180018C7C
0x180018bce  mov     rcx, [r14]
0x180018bd1  test    rcx, rcx
0x180018bd4  jz      loc_180018C7C
0x180018bda  cmp     esi, 3
0x180018bdd  jz      loc_180018C7C
0x180018be3  lea     r9d, [rbx+8]
0x180018be7  cmp     eax, r9d
0x180018bea  jz      short loc_180018C14
0x180018bec  test    byte ptr cs:xmmword_1800616A0, 2
0x180018bf3  jz      short loc_180018C0D
0x180018bf5  lea     edx, [rbx+59h]
0x180018bf8  mov     dword ptr [rsp+40h+var_20], eax
0x180018bfc  mov     ecx, 401h
0x180018c01  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180018c08  call    WPP_SF_Dd
0x180018c0d  mov     ebx, 57h ; 'W'
0x180018c12  jmp     short loc_180018C83
0x180018c14  mov     rax, [rcx]
0x180018c17  mov     qword ptr [rbp+InterfaceLuid], rax
0x180018c1b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180018c22  jz      short loc_180018C41
0x180018c24  mov     edx, 5Ah ; 'Z'
0x180018c29  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180018c30  mov     ecx, 404h
0x180018c35  mov     r9, rax
0x180018c38  call    WPP_SF_q
0x180018c3d  mov     rax, qword ptr [rbp+InterfaceLuid]
0x180018c41  cmp     esi, 2
0x180018c44  jz      short loc_180018C5D
0x180018c46  mov     rcx, rax
0x180018c49  call    IsInterfaceConnected
0x180018c4e  test    eax, eax
0x180018c50  jz      short loc_180018C5D
0x180018c52  lea     rcx, [rbp+InterfaceLuid]; InterfaceLuid
0x180018c56  call    DhcpOnMediaConnected
0x180018c5b  jmp     short loc_180018C81
0x180018c5d  lea     rcx, [rbp+InterfaceLuid]; InterfaceLuid
0x180018c61  call    DhcpOnMediaDisconnected
0x180018c66  mov     ebx, eax
0x180018c68  test    eax, eax
0x180018c6a  jnz     short loc_180018C83
0x180018c6c  cmp     esi, 2
0x180018c6f  jnz     short loc_180018C83
0x180018c71  lea     rcx, [rbp+InterfaceLuid]
0x180018c75  call    TryDeleteDisconnectedContext
0x180018c7a  jmp     short loc_180018C83
0x180018c7c  call    DhcpEnumInterface
0x180018c81  mov     ebx, eax
0x180018c83  test    r12d, r12d
0x180018c86  jz      short loc_180018C90
0x180018c88  mov     ecx, r15d; CompartmentScope
0x180018c8b  call    DhcpRevertThreadCompartmentScope
0x180018c90  test    byte ptr cs:xmmword_1800616A0, 10h
0x180018c97  jz      short loc_180018CB7
0x180018c99  mov     r9, qword ptr [rbp+InterfaceLuid]
0x180018c9d  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180018ca4  mov     edx, 5Bh ; '['
0x180018ca9  mov     dword ptr [rsp+40h+var_20], ebx
0x180018cad  mov     ecx, 404h
0x180018cb2  call    WPP_SF_qD
0x180018cb7  mov     rbx, [rsp+40h+arg_0]
0x180018cbc  mov     rsi, [rsp+40h+arg_8]
0x180018cc1  add     rsp, 40h
0x180018cc5  pop     r15
0x180018cc7  pop     r14
0x180018cc9  pop     r12
0x180018ccb  pop     rdi
0x180018ccc  pop     rbp
0x180018ccd  retn
```
