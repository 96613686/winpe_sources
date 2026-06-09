# DhcpInitNSIMediaSense

- ea: `0x1800147e4`
- end: `0x1800149e0`
- name: `DhcpInitNSIMediaSense`
- size: `508`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180023928`

## callees

- `0x1800147e4`
- `0x180014f80`
- `0x18001d826`
- `0x1800429cc`
- `0x18004c51c`
- `0x18004c5f8`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d4c0`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800148b4`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800148b4`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800148c2`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x1800148c2`
- `WINNSI!NsiConnectToServer` at `0x18001482e`
- `WINNSI!NsiConnectToServer` at `0x18001482e`
- `WINNSI!NsiRpcRegisterChangeNotificationEx` at `0x180014940`
- `WINNSI!NsiRpcRegisterChangeNotificationEx` at `0x180014940`

## pseudocode

```c
__int64 DhcpInitNSIMediaSense()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  NET_IF_COMPARTMENT_SCOPE v4; // edi
  unsigned int v5; // ebx
  int v6; // esi
  int v7; // r14d
  _BYTE v9[8]; // [rsp+30h] [rbp-50h] BYREF
  const NPI_MODULEID *v10; // [rsp+38h] [rbp-48h]
  int v11; // [rsp+40h] [rbp-40h]
  __int64 (__fastcall *v12)(); // [rsp+48h] [rbp-38h]
  char v13; // [rsp+50h] [rbp-30h]
  __int64 v14; // [rsp+58h] [rbp-28h]
  __int64 *v15; // [rsp+70h] [rbp-10h]
  UINT32 CompartmentScope; // [rsp+A0h] [rbp+20h] BYREF
  UINT32 CompartmentId; // [rsp+A8h] [rbp+28h] BYREF

  memset_0(v9, 0, 0x48u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 92, WPP_b85ebe6c12863f19dba418452b756303_Traceguids);
  v3 = NsiConnectToServer(0);
  qword_1800616F0 = v3;
  if ( ((v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_q(1025, 93, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v3);
    v4 = 0;
    v5 = 1722;
    v6 = 0;
    goto LABEL_23;
  }
  CompartmentId = 0;
  v7 = 0;
  CompartmentScope = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 18, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids);
  v5 = 0;
  if ( DhcpGlobalCompartmentAware )
  {
    GetCurrentThreadCompartmentScope(&CompartmentScope, &CompartmentId);
    v1 = 0xFFFFFFFFLL;
    if ( CompartmentScope == -1 )
    {
LABEL_13:
      v4 = CompartmentScope;
      v6 = v7;
      goto LABEL_15;
    }
    v5 = SetCurrentThreadCompartmentScope(0xFFFFFFFF);
    if ( !v5 )
    {
      v7 = 1;
      goto LABEL_13;
    }
  }
  v4 = 0;
  v6 = 0;
LABEL_15:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dlD(v1, v0, v2, CompartmentScope, v7, v5);
  if ( !v5 )
  {
    v10 = &NPI_MS_IPV4_MODULEID;
    v11 = 7;
    v12 = DhcpNSIMediaSenseCallback;
    v15 = &qword_1800616E8;
    v13 = 1;
    v14 = 0;
    v5 = NsiRpcRegisterChangeNotificationEx(qword_1800616F0, v9);
    if ( !v5 )
    {
      if ( ((qword_1800616E8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_26;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_q(1025, 94, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, qword_1800616E8);
      v5 = 1359;
    }
  }
LABEL_23:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 95, WPP_b85ebe6c12863f19dba418452b756303_Traceguids, v5);
  DhcpDeInitNSIMediaSense();
LABEL_26:
  if ( v6 )
    DhcpRevertThreadCompartmentScope(v4);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qqD();
  return v5;
}

```

## disassembly

```asm
0x1800147e4  mov     [rsp-18h+arg_10], rbx
0x1800147e9  mov     [rsp-18h+arg_18], rsi
0x1800147ee  push    rbp
0x1800147ef  push    rdi
0x1800147f0  push    r14
0x1800147f2  mov     rbp, rsp
0x1800147f5  sub     rsp, 80h
0x1800147fc  xor     edx, edx; Val
0x1800147fe  lea     rcx, [rbp+var_50]; void *
0x180014802  lea     r8d, [rdx+48h]; Size
0x180014806  call    memset_0
0x18001480b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180014812  mov     ebx, 404h
0x180014817  jz      short loc_18001482C
0x180014819  mov     edx, 5Ch ; '\'
0x18001481e  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180014825  mov     ecx, ebx
0x180014827  call    WPP_SF_
0x18001482c  xor     ecx, ecx
0x18001482e  call    cs:__imp_NsiConnectToServer
0x180014834  mov     r9, rax
0x180014837  mov     cs:qword_1800616F0, rax
0x18001483e  inc     rax
0x180014841  test    rax, 0FFFFFFFFFFFFFFFEh
0x180014847  jnz     short loc_180014876
0x180014849  test    byte ptr cs:xmmword_1800616A0, 2
0x180014850  jz      short loc_180014868
0x180014852  mov     edx, 5Dh ; ']'
0x180014857  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x18001485e  mov     ecx, 401h
0x180014863  call    WPP_SF_q
0x180014868  xor     edi, edi
0x18001486a  mov     ebx, 6BAh
0x18001486f  xor     esi, esi
0x180014871  jmp     loc_180014982
0x180014876  mov     [rbp+CompartmentId], 0
0x18001487d  xor     r14d, r14d
0x180014880  mov     [rbp+CompartmentScope], 0
0x180014887  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001488e  jz      short loc_1800148A2
0x180014890  lea     edx, [r14+12h]
0x180014894  mov     ecx, ebx
0x180014896  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x18001489d  call    WPP_SF_
0x1800148a2  xor     ebx, ebx
0x1800148a4  cmp     cs:DhcpGlobalCompartmentAware, ebx
0x1800148aa  jz      short loc_1800148DA
0x1800148ac  lea     rdx, [rbp+CompartmentId]; CompartmentId
0x1800148b0  lea     rcx, [rbp+CompartmentScope]; CompartmentScope
0x1800148b4  call    cs:__imp_GetCurrentThreadCompartmentScope
0x1800148ba  or      ecx, 0FFFFFFFFh; CompartmentScope
0x1800148bd  cmp     [rbp+CompartmentScope], ecx
0x1800148c0  jz      short loc_1800148D2
0x1800148c2  call    cs:__imp_SetCurrentThreadCompartmentScope
0x1800148c8  mov     ebx, eax
0x1800148ca  test    eax, eax
0x1800148cc  jnz     short loc_1800148DA
0x1800148ce  lea     r14d, [rax+1]
0x1800148d2  mov     edi, [rbp+CompartmentScope]
0x1800148d5  mov     esi, r14d
0x1800148d8  jmp     short loc_1800148DE
0x1800148da  xor     edi, edi
0x1800148dc  xor     esi, esi
0x1800148de  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800148e5  jz      short loc_1800148F9
0x1800148e7  mov     r9d, [rbp+CompartmentScope]
0x1800148eb  mov     [rsp+80h+var_58], ebx
0x1800148ef  mov     [rsp+80h+var_60], r14d
0x1800148f4  call    WPP_SF_dlD
0x1800148f9  test    ebx, ebx
0x1800148fb  jnz     loc_180014982
0x180014901  mov     rcx, cs:qword_1800616F0
0x180014908  lea     rax, NPI_MS_IPV4_MODULEID
0x18001490f  mov     [rbp+var_48], rax
0x180014913  lea     rdx, [rbp+var_50]
0x180014917  lea     rax, DhcpNSIMediaSenseCallback
0x18001491e  mov     [rbp+var_40], 7
0x180014925  mov     [rbp+var_38], rax
0x180014929  lea     rax, qword_1800616E8
0x180014930  mov     [rbp+var_10], rax
0x180014934  mov     [rbp+var_30], 1
0x180014938  mov     [rbp+var_28], 0
0x180014940  call    cs:__imp_NsiRpcRegisterChangeNotificationEx
0x180014946  mov     ebx, eax
0x180014948  test    eax, eax
0x18001494a  jnz     short loc_180014982
0x18001494c  mov     r9, cs:qword_1800616E8
0x180014953  lea     rcx, [r9+1]
0x180014957  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001495e  jnz     short loc_1800149A9
0x180014960  test    byte ptr cs:xmmword_1800616A0, 2
0x180014967  jz      short loc_18001497D
0x180014969  lea     edx, [rax+5Eh]
0x18001496c  mov     ecx, 401h
0x180014971  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180014978  call    WPP_SF_q
0x18001497d  mov     ebx, 54Fh
0x180014982  test    byte ptr cs:xmmword_1800616A0, 2
0x180014989  jz      short loc_1800149A4
0x18001498b  mov     edx, 5Fh ; '_'
0x180014990  lea     r8, WPP_b85ebe6c12863f19dba418452b756303_Traceguids
0x180014997  mov     ecx, 401h
0x18001499c  mov     r9d, ebx
0x18001499f  call    WPP_SF_D
0x1800149a4  call    DhcpDeInitNSIMediaSense
0x1800149a9  test    esi, esi
0x1800149ab  jz      short loc_1800149B4
0x1800149ad  mov     ecx, edi; CompartmentScope
0x1800149af  call    DhcpRevertThreadCompartmentScope
0x1800149b4  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800149bb  jz      short loc_1800149C6
0x1800149bd  mov     [rsp+80h+var_58], ebx
0x1800149c1  call    WPP_SF_qqD
0x1800149c6  lea     r11, [rsp+80h+var_s0]
0x1800149ce  mov     eax, ebx
0x1800149d0  mov     rbx, [r11+30h]
0x1800149d4  mov     rsi, [r11+38h]
0x1800149d8  mov     rsp, r11
0x1800149db  pop     r14
0x1800149dd  pop     rdi
0x1800149de  pop     rbp
0x1800149df  retn
```
