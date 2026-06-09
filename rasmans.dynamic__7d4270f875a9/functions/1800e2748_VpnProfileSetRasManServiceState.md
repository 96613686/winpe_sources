# VpnProfileSetRasManServiceState

- ea: `0x1800e2748`
- end: `0x1800e2adf`
- name: `VpnProfileSetRasManServiceState`
- size: `919`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800cea20`
- `0x1800d9a60`
- `0x1800e0e34`

## callees

- `0x180005bfc`
- `0x18000c37c`
- `0x1800d8014`
- `0x1800e2748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e27be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e28dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e27be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2823`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e28dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2a13`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e2a7e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e2a8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e2a7e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800e2a8d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e27aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e27aa`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e280f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e280f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800e2953`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800e2953`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e28cd`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e2a03`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e28cd`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800e2a03`

## pseudocode

```c
__int64 __fastcall VpnProfileSetRasManServiceState(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbp
  DWORD LastError; // eax
  int v8; // ebx
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  DWORD v13; // eax
  struct _LIST_ENTRY *v14; // rcx
  DWORD v15; // edi
  __int64 v16; // rdx
  DWORD v17; // eax
  DWORD v18; // eax
  unsigned int Info; // [rsp+98h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 971, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, a4);
  }
  Info = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 972;
LABEL_8:
      WPP_SF_d(v9[1].Flink, v10, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
LABEL_48:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v11 = OpenServiceW(v5, L"Rasman", 0xF01FFu);
  v12 = v11;
  if ( v11 )
  {
    v8 = 0;
    if ( (unsigned int)int_QueryServiceConfiguration(v11, &Info) )
    {
      if ( a1 )
      {
        if ( Info == 2 )
          goto LABEL_47;
        goto LABEL_19;
      }
      if ( Info == 3 )
        goto LABEL_47;
    }
    if ( !a1 )
    {
      if ( !ChangeServiceConfigW(v12, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        v18 = GetLastError();
        v14 = WPP_GLOBAL_Control;
        v15 = v18;
        if ( v18
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 978, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v18);
          v14 = WPP_GLOBAL_Control;
          v8 = v15;
        }
        else
        {
          v8 = v18;
          if ( !v18 )
            goto LABEL_47;
        }
        if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v14[1].Blink) & 1) == 0 )
          goto LABEL_47;
        v16 = 979;
LABEL_46:
        WPP_SF_d(v14[1].Flink, v16, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v15);
      }
LABEL_47:
      CloseServiceHandle(v12);
      CloseServiceHandle(v6);
      goto LABEL_48;
    }
LABEL_19:
    Info = 0;
    if ( !ChangeServiceConfigW(v12, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v13 = GetLastError();
      v14 = WPP_GLOBAL_Control;
      v15 = v13;
      if ( v13
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 974, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v13);
        v14 = WPP_GLOBAL_Control;
        v8 = v15;
        goto LABEL_25;
      }
      v8 = v13;
      if ( v13 )
      {
LABEL_25:
        if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v14[1].Blink) & 1) == 0 )
          goto LABEL_47;
        v16 = 975;
        goto LABEL_46;
      }
    }
    if ( !ChangeServiceConfig2W(v12, 3u, &Info) )
    {
      v17 = GetLastError();
      v14 = WPP_GLOBAL_Control;
      v15 = v17;
      if ( v17
        && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 976, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v17);
        v14 = WPP_GLOBAL_Control;
        v8 = v15;
        goto LABEL_34;
      }
      v8 = v17;
      if ( v17 )
      {
LABEL_34:
        if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v14[1].Blink) & 1) == 0 )
          goto LABEL_47;
        v16 = 977;
        goto LABEL_46;
      }
    }
    goto LABEL_47;
  }
  LastError = GetLastError();
  v8 = LastError;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v10 = 973;
    goto LABEL_8;
  }
LABEL_49:
  if ( v8 < 0 && v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 8) != 0 )
    WPP_SF_d(v9[1].Flink, 980, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800e2748  mov     [rsp+arg_0], rbx
0x1800e274d  mov     [rsp+arg_10], rbp
0x1800e2752  push    rsi
0x1800e2753  push    rdi
0x1800e2754  push    r13
0x1800e2756  push    r14
0x1800e2758  push    r15
0x1800e275a  sub     rsp, 60h
0x1800e275e  mov     edi, ecx
0x1800e2760  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2767  lea     r15, WPP_GLOBAL_Control
0x1800e276e  xor     r14d, r14d
0x1800e2771  lea     r13, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800e2778  cmp     rcx, r15
0x1800e277b  jz      short loc_1800E279A
0x1800e277d  test    byte ptr [rcx+1Ch], 8
0x1800e2781  jz      short loc_1800E279A
0x1800e2783  mov     rcx, [rcx+10h]
0x1800e2787  test    edi, edi
0x1800e2789  mov     edx, 3CBh
0x1800e278e  mov     r8, r13
0x1800e2791  setnz   r9b
0x1800e2795  call    WPP_SF_c
0x1800e279a  xor     edx, edx; lpDatabaseName
0x1800e279c  mov     [rsp+88h+Info], r14d
0x1800e27a4  xor     ecx, ecx; lpMachineName
0x1800e27a6  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800e27aa  call    cs:__imp_OpenSCManagerW
0x1800e27b1  nop     dword ptr [rax+rax+00h]
0x1800e27b6  mov     rbp, rax
0x1800e27b9  test    rax, rax
0x1800e27bc  jnz     short loc_1800E27FF
0x1800e27be  call    cs:__imp_GetLastError
0x1800e27c5  nop     dword ptr [rax+rax+00h]
0x1800e27ca  mov     ebx, eax
0x1800e27cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e27d3  cmp     rcx, r15
0x1800e27d6  jz      loc_1800E2AA0
0x1800e27dc  test    byte ptr [rcx+1Ch], 1
0x1800e27e0  jz      loc_1800E2AA0
0x1800e27e6  mov     edx, 3CCh
0x1800e27eb  mov     rcx, [rcx+10h]
0x1800e27ef  mov     r9d, eax
0x1800e27f2  mov     r8, r13
0x1800e27f5  call    WPP_SF_d
0x1800e27fa  jmp     loc_1800E2A99
0x1800e27ff  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800e2805  lea     rdx, aRasman_2; "Rasman"
0x1800e280c  mov     rcx, rbp; hSCManager
0x1800e280f  call    cs:__imp_OpenServiceW
0x1800e2816  nop     dword ptr [rax+rax+00h]
0x1800e281b  mov     rsi, rax
0x1800e281e  test    rax, rax
0x1800e2821  jnz     short loc_1800E2852
0x1800e2823  call    cs:__imp_GetLastError
0x1800e282a  nop     dword ptr [rax+rax+00h]
0x1800e282f  mov     ebx, eax
0x1800e2831  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2838  cmp     rcx, r15
0x1800e283b  jz      loc_1800E2AA0
0x1800e2841  test    byte ptr [rcx+1Ch], 1
0x1800e2845  jz      loc_1800E2AA0
0x1800e284b  mov     edx, 3CDh
0x1800e2850  jmp     short loc_1800E27EB
0x1800e2852  lea     rdx, [rsp+88h+Info]; unsigned int *
0x1800e285a  mov     rcx, rsi; hService
0x1800e285d  mov     ebx, r14d
0x1800e2860  call    ?int_QueryServiceConfiguration@@YAHQEAUSC_HANDLE__@@PEAK@Z; int_QueryServiceConfiguration(SC_HANDLE__ * const,ulong *)
0x1800e2865  mov     r8d, 2; dwStartType
0x1800e286b  test    eax, eax
0x1800e286d  jz      short loc_1800E2891
0x1800e286f  test    edi, edi
0x1800e2871  jz      short loc_1800E2883
0x1800e2873  cmp     [rsp+88h+Info], r8d
0x1800e287b  jz      loc_1800E2A7B
0x1800e2881  jmp     short loc_1800E2899
0x1800e2883  cmp     [rsp+88h+Info], 3
0x1800e288b  jz      loc_1800E2A7B
0x1800e2891  test    edi, edi
0x1800e2893  jz      loc_1800E29D1
0x1800e2899  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x1800e289e  or      edx, 0FFFFFFFFh; dwServiceType
0x1800e28a1  mov     [rsp+88h+lpPassword], r14; lpPassword
0x1800e28a6  mov     r9d, edx; dwErrorControl
0x1800e28a9  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x1800e28ae  mov     rcx, rsi; hService
0x1800e28b1  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x1800e28b6  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x1800e28bb  mov     [rsp+88h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1800e28c0  mov     [rsp+88h+lpBinaryPathName], r14; lpBinaryPathName
0x1800e28c5  mov     [rsp+88h+Info], r14d
0x1800e28cd  call    cs:__imp_ChangeServiceConfigW
0x1800e28d4  nop     dword ptr [rax+rax+00h]
0x1800e28d9  test    eax, eax
0x1800e28db  jnz     short loc_1800E2943
0x1800e28dd  call    cs:__imp_GetLastError
0x1800e28e4  nop     dword ptr [rax+rax+00h]
0x1800e28e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e28f0  mov     edi, eax
0x1800e28f2  test    eax, eax
0x1800e28f4  jz      short loc_1800E2920
0x1800e28f6  cmp     rcx, r15
0x1800e28f9  jz      short loc_1800E2920
0x1800e28fb  test    byte ptr [rcx+1Ch], 1
0x1800e28ff  jz      short loc_1800E2920
0x1800e2901  mov     rcx, [rcx+10h]
0x1800e2905  mov     edx, 3CEh
0x1800e290a  mov     r9d, eax
0x1800e290d  mov     r8, r13
0x1800e2910  call    WPP_SF_d
0x1800e2915  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e291c  mov     ebx, edi
0x1800e291e  jmp     short loc_1800E2926
0x1800e2920  mov     ebx, edi
0x1800e2922  test    edi, edi
0x1800e2924  jz      short loc_1800E2943
0x1800e2926  cmp     rcx, r15
0x1800e2929  jz      loc_1800E2A7B
0x1800e292f  test    byte ptr [rcx+1Ch], 1
0x1800e2933  jz      loc_1800E2A7B
0x1800e2939  mov     edx, 3CFh
0x1800e293e  jmp     loc_1800E2A6C
0x1800e2943  lea     r8, [rsp+88h+Info]; lpInfo
0x1800e294b  mov     edx, 3; dwInfoLevel
0x1800e2950  mov     rcx, rsi; hService
0x1800e2953  call    cs:__imp_ChangeServiceConfig2W
0x1800e295a  nop     dword ptr [rax+rax+00h]
0x1800e295f  test    eax, eax
0x1800e2961  jnz     loc_1800E2A7B
0x1800e2967  call    cs:__imp_GetLastError
0x1800e296e  nop     dword ptr [rax+rax+00h]
0x1800e2973  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e297a  mov     edi, eax
0x1800e297c  test    eax, eax
0x1800e297e  jz      short loc_1800E29AA
0x1800e2980  cmp     rcx, r15
0x1800e2983  jz      short loc_1800E29AA
0x1800e2985  test    byte ptr [rcx+1Ch], 1
0x1800e2989  jz      short loc_1800E29AA
0x1800e298b  mov     rcx, [rcx+10h]
0x1800e298f  mov     edx, 3D0h
0x1800e2994  mov     r9d, eax
0x1800e2997  mov     r8, r13
0x1800e299a  call    WPP_SF_d
0x1800e299f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e29a6  mov     ebx, edi
0x1800e29a8  jmp     short loc_1800E29B4
0x1800e29aa  mov     ebx, edi
0x1800e29ac  test    edi, edi
0x1800e29ae  jz      loc_1800E2A7B
0x1800e29b4  cmp     rcx, r15
0x1800e29b7  jz      loc_1800E2A7B
0x1800e29bd  test    byte ptr [rcx+1Ch], 1
0x1800e29c1  jz      loc_1800E2A7B
0x1800e29c7  mov     edx, 3D1h
0x1800e29cc  jmp     loc_1800E2A6C
0x1800e29d1  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x1800e29d6  or      edx, 0FFFFFFFFh; dwServiceType
0x1800e29d9  mov     [rsp+88h+lpPassword], r14; lpPassword
0x1800e29de  mov     r9d, edx; dwErrorControl
0x1800e29e1  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x1800e29e6  mov     r8d, 3; dwStartType
0x1800e29ec  mov     [rsp+88h+lpDependencies], r14; lpDependencies
0x1800e29f1  mov     rcx, rsi; hService
0x1800e29f4  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x1800e29f9  mov     [rsp+88h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1800e29fe  mov     [rsp+88h+lpBinaryPathName], r14; lpBinaryPathName
0x1800e2a03  call    cs:__imp_ChangeServiceConfigW
0x1800e2a0a  nop     dword ptr [rax+rax+00h]
0x1800e2a0f  test    eax, eax
0x1800e2a11  jnz     short loc_1800E2A7B
0x1800e2a13  call    cs:__imp_GetLastError
0x1800e2a1a  nop     dword ptr [rax+rax+00h]
0x1800e2a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2a26  mov     edi, eax
0x1800e2a28  test    eax, eax
0x1800e2a2a  jz      short loc_1800E2A56
0x1800e2a2c  cmp     rcx, r15
0x1800e2a2f  jz      short loc_1800E2A56
0x1800e2a31  test    byte ptr [rcx+1Ch], 1
0x1800e2a35  jz      short loc_1800E2A56
0x1800e2a37  mov     rcx, [rcx+10h]
0x1800e2a3b  mov     edx, 3D2h
0x1800e2a40  mov     r9d, eax
0x1800e2a43  mov     r8, r13
0x1800e2a46  call    WPP_SF_d
0x1800e2a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2a52  mov     ebx, edi
0x1800e2a54  jmp     short loc_1800E2A5C
0x1800e2a56  mov     ebx, edi
0x1800e2a58  test    edi, edi
0x1800e2a5a  jz      short loc_1800E2A7B
0x1800e2a5c  cmp     rcx, r15
0x1800e2a5f  jz      short loc_1800E2A7B
0x1800e2a61  test    byte ptr [rcx+1Ch], 1
0x1800e2a65  jz      short loc_1800E2A7B
0x1800e2a67  mov     edx, 3D3h
0x1800e2a6c  mov     rcx, [rcx+10h]
0x1800e2a70  mov     r9d, edi
0x1800e2a73  mov     r8, r13
0x1800e2a76  call    WPP_SF_d
0x1800e2a7b  mov     rcx, rsi; hSCObject
0x1800e2a7e  call    cs:__imp_CloseServiceHandle
0x1800e2a85  nop     dword ptr [rax+rax+00h]
0x1800e2a8a  mov     rcx, rbp; hSCObject
0x1800e2a8d  call    cs:__imp_CloseServiceHandle
0x1800e2a94  nop     dword ptr [rax+rax+00h]
0x1800e2a99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2aa0  test    ebx, ebx
0x1800e2aa2  jns     short loc_1800E2AC3
0x1800e2aa4  cmp     rcx, r15
0x1800e2aa7  jz      short loc_1800E2AC3
0x1800e2aa9  test    byte ptr [rcx+1Ch], 8
0x1800e2aad  jz      short loc_1800E2AC3
0x1800e2aaf  mov     rcx, [rcx+10h]
0x1800e2ab3  mov     edx, 3D4h
0x1800e2ab8  mov     r9d, ebx
0x1800e2abb  mov     r8, r13
0x1800e2abe  call    WPP_SF_d
0x1800e2ac3  lea     r11, [rsp+88h+var_28]
0x1800e2ac8  mov     eax, ebx
0x1800e2aca  mov     rbx, [r11+30h]
0x1800e2ace  mov     rbp, [r11+40h]
0x1800e2ad2  mov     rsp, r11
0x1800e2ad5  pop     r15
0x1800e2ad7  pop     r14
0x1800e2ad9  pop     r13
0x1800e2adb  pop     rdi
0x1800e2adc  pop     rsi
0x1800e2add  retn
```
