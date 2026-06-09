# DaRpcFetchConnectedDevice

- ea: `0x140007dd0`
- end: `0x140008270`
- name: `DaRpcFetchConnectedDevice`
- size: `1184`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

## callees

- `0x140002c00`
- `0x140002c40`
- `0x140002fbc`
- `0x140004bd4`
- `0x1400076f4`
- `0x140007dd0`
- `0x140009b80`
- `0x140009e9c`
- `0x14000a0b0`
- `0x14000a154`
- `0x140018350`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140007fa2`
- `KERNEL32!EnterCriticalSection` at `0x14000806e`
- `KERNEL32!EnterCriticalSection` at `0x140007fa2`
- `KERNEL32!EnterCriticalSection` at `0x14000806e`
- `KERNEL32!LeaveCriticalSection` at `0x140008053`
- `KERNEL32!LeaveCriticalSection` at `0x1400081d5`
- `KERNEL32!LeaveCriticalSection` at `0x140008053`
- `KERNEL32!LeaveCriticalSection` at `0x1400081d5`
- `KERNEL32!GetTickCount64` at `0x140007ff1`
- `KERNEL32!GetTickCount64` at `0x1400080c0`
- `KERNEL32!GetTickCount64` at `0x140007ff1`
- `KERNEL32!GetTickCount64` at `0x1400080c0`
- `msvcrt!strcpy_s` at `0x140008043`
- `msvcrt!strcpy_s` at `0x140008043`
- `msvcrt!_wcsicmp` at `0x140007fd5`
- `msvcrt!_wcsicmp` at `0x1400080a1`
- `msvcrt!_wcsicmp` at `0x140007fd5`
- `msvcrt!_wcsicmp` at `0x1400080a1`
- `msvcrt!wcscpy_s` at `0x140008174`
- `msvcrt!wcscpy_s` at `0x140008174`
- `RPCRT4!RpcImpersonateClient` at `0x140007ed7`
- `RPCRT4!RpcImpersonateClient` at `0x140007ed7`

## pseudocode

```c
__int64 __fastcall DaRpcFetchConnectedDevice(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        wchar_t *a5,
        unsigned int *a6,
        _DWORD *a7,
        _DWORD *a8)
{
  rsize_t v9; // r12
  unsigned int v10; // eax
  int Luid; // eax
  __int64 v13; // rcx
  void *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // r14d
  HGLOBAL v17; // rbx
  const wchar_t *v18; // rcx
  ULONGLONG TickCount64; // rax
  ULONGLONG v20; // rdx
  __int64 v21; // r8
  const wchar_t *v22; // rcx
  ULONGLONG v23; // rax
  __int64 v24; // rax
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  struct _LUID DestinationLuid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v29; // [rsp+50h] [rbp-B0h]
  _DWORD *v30; // [rsp+58h] [rbp-A8h]
  _DWORD *v31; // [rsp+60h] [rbp-A0h]
  char v32[40]; // [rsp+68h] [rbp-98h] BYREF
  char Destination[272]; // [rsp+90h] [rbp-70h] BYREF

  v9 = a4;
  v29 = a6;
  v30 = a7;
  v31 = a8;
  DestinationLuid = 0;
  strcpy(v32, "DaRpcFetchConnectedDevice");
  if ( a2 && a3 && (!a4 || a5) && a6 && a7 && a8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, a3);
    *a6 = 0;
    if ( a5 && (_DWORD)v9 )
      *a5 = 0;
    v10 = RpcImpersonateClient(0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v10);
      return 5;
    }
    Luid = GetLuid(&DestinationLuid);
    if ( Luid < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
          (unsigned int)Luid);
      SafeRpcRevertToSelf(v14, 561);
      return 5;
    }
    v15 = SafeRpcRevertToSelf(v13, 568);
    v16 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
          (unsigned int)v32,
          v15);
      return v16;
    }
    RefreshConnectionCheckParameters();
    EnterCriticalSection(&DeviceListCS);
    v17 = pDeviceList;
    if ( !pDeviceList )
      goto LABEL_62;
    do
    {
      if ( DestinationLuid.LowPart == *(_DWORD *)v17 && DestinationLuid.HighPart == *((_DWORD *)v17 + 1) )
      {
        v18 = (const wchar_t *)*((_QWORD *)v17 + 4);
        if ( v18 )
        {
          if ( !_wcsicmp(v18, a3) )
            break;
        }
      }
      v17 = (HGLOBAL)*((_QWORD *)v17 + 8);
    }
    while ( v17 );
    if ( v17 )
    {
      TickCount64 = GetTickCount64();
      v21 = qword_140021B80;
      if ( *((_DWORD *)v17 + 4) )
        v21 = qword_140021B78;
      if ( *((_DWORD *)v17 + 3) == 2 )
        goto LABEL_50;
      v20 = v21 + *((_QWORD *)v17 + 3);
      if ( v20 > TickCount64 || *((_DWORD *)v17 + 5) && v21 )
        goto LABEL_50;
      strcpy_s(Destination, 0x105u, *((const char **)v17 + 7));
      ++*((_DWORD *)v17 + 5);
      LeaveCriticalSection(&DeviceListCS);
      CheckServerConnection((int)Destination);
      EnterCriticalSection(&DeviceListCS);
      v17 = pDeviceList;
      if ( pDeviceList )
      {
        do
        {
          if ( DestinationLuid.LowPart == *(_DWORD *)v17 && DestinationLuid.HighPart == *((_DWORD *)v17 + 1) )
          {
            v22 = (const wchar_t *)*((_QWORD *)v17 + 4);
            if ( v22 )
            {
              if ( !_wcsicmp(v22, a3) )
                break;
            }
          }
          v17 = (HGLOBAL)*((_QWORD *)v17 + 8);
        }
        while ( v17 );
        if ( v17 )
        {
          *((_DWORD *)v17 + 4) = 0;
          v23 = GetTickCount64();
          --*((_DWORD *)v17 + 5);
          *((_QWORD *)v17 + 3) = v23;
LABEL_50:
          v24 = -1;
          do
            ++v24;
          while ( *(_WORD *)(*((_QWORD *)v17 + 5) + 2 * v24) );
          v25 = v24 + 1;
          *v29 = v25;
          if ( (unsigned int)v9 >= v25 )
          {
            *v30 = *((_DWORD *)v17 + 3);
            *v31 = *((_DWORD *)v17 + 4);
            wcscpy_s(a5, v9, *((const wchar_t **)v17 + 5));
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, a5);
          }
          else
          {
            v16 = 234;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_DSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, 0, *((_QWORD *)v17 + 5), v9, v25);
          }
          goto LABEL_66;
        }
      }
      v16 = 2250;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v27 = 44;
LABEL_65:
        WPP_SF_d(v26[2], v27, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, 2250);
      }
    }
    else
    {
LABEL_62:
      v16 = 2250;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v27 = 43;
        goto LABEL_65;
      }
    }
LABEL_66:
    LeaveCriticalSection(&DeviceListCS);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v16);
    return v16;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v32);
  return 87;
}

```

## disassembly

```asm
0x140007dd0  mov     [rsp-8+arg_0], rbx
0x140007dd5  push    rbp
0x140007dd6  push    rsi
0x140007dd7  push    rdi
0x140007dd8  push    r12
0x140007dda  push    r13
0x140007ddc  push    r14
0x140007dde  push    r15
0x140007de0  lea     rbp, [rsp-0B0h]
0x140007de8  sub     rsp, 1B0h
0x140007def  mov     rax, cs:__security_cookie
0x140007df6  xor     rax, rsp
0x140007df9  mov     [rbp+0E0h+var_40], rax
0x140007e00  movups  xmm0, xmmword ptr cs:aDarpcfetchconn; "DaRpcFetchConnectedDevice"
0x140007e07  mov     rbx, [rbp+0E0h+arg_28]
0x140007e0e  xor     r14d, r14d
0x140007e11  mov     rax, [rbp+0E0h+arg_30]
0x140007e18  mov     r13, r8
0x140007e1b  mov     rcx, [rbp+0E0h+arg_38]
0x140007e22  mov     r15, [rbp+0E0h+arg_20]
0x140007e29  mov     r12d, r9d
0x140007e2c  mov     [rsp+1E0h+var_190], rbx
0x140007e31  mov     [rsp+1E0h+var_188], rax
0x140007e36  mov     [rsp+1E0h+var_180], rcx
0x140007e3b  mov     qword ptr [rsp+1E0h+DestinationLuid.LowPart], r14
0x140007e40  mov     [rsp+1E0h+var_1A0], r14d
0x140007e45  movups  xmm1, xmmword ptr cs:aDarpcfetchconn+0Ah; "ConnectedDevice"
0x140007e4c  movups  xmmword ptr [rsp+1E0h+var_178], xmm0
0x140007e51  movups  xmmword ptr [rsp+1E0h+var_178+0Ah], xmm1
0x140007e56  test    edx, edx
0x140007e58  jz      loc_14000820E
0x140007e5e  test    r8, r8
0x140007e61  jz      loc_14000820E
0x140007e67  test    r9d, r9d
0x140007e6a  jz      short loc_140007E75
0x140007e6c  test    r15, r15
0x140007e6f  jz      loc_14000820E
0x140007e75  test    rbx, rbx
0x140007e78  jz      loc_14000820E
0x140007e7e  test    rax, rax
0x140007e81  jz      loc_14000820E
0x140007e87  test    rcx, rcx
0x140007e8a  jz      loc_14000820E
0x140007e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e97  lea     rdi, WPP_GLOBAL_Control
0x140007e9e  lea     rsi, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007ea5  cmp     rcx, rdi
0x140007ea8  jz      short loc_140007EC4
0x140007eaa  test    byte ptr [rcx+1Ch], 1
0x140007eae  jz      short loc_140007EC4
0x140007eb0  mov     rcx, [rcx+10h]
0x140007eb4  mov     edx, 27h ; '''
0x140007eb9  mov     r9, r13
0x140007ebc  mov     r8, rsi
0x140007ebf  call    WPP_SF_S
0x140007ec4  mov     [rbx], r14d
0x140007ec7  test    r15, r15
0x140007eca  jz      short loc_140007ED5
0x140007ecc  test    r12d, r12d
0x140007ecf  jz      short loc_140007ED5
0x140007ed1  mov     [r15], r14w
0x140007ed5  xor     ecx, ecx; BindingHandle
0x140007ed7  call    cs:__imp_RpcImpersonateClient
0x140007edd  test    eax, eax
0x140007edf  jz      short loc_140007F11
0x140007ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ee8  cmp     rcx, rdi
0x140007eeb  jz      short loc_140007F07
0x140007eed  test    byte ptr [rcx+1Ch], 2
0x140007ef1  jz      short loc_140007F07
0x140007ef3  mov     rcx, [rcx+10h]
0x140007ef7  mov     edx, 28h ; '('
0x140007efc  mov     r9d, eax
0x140007eff  mov     r8, rsi
0x140007f02  call    WPP_SF_d
0x140007f07  mov     eax, 5
0x140007f0c  jmp     loc_140008246
0x140007f11  lea     rcx, [rsp+1E0h+DestinationLuid]; DestinationLuid
0x140007f16  call    GetLuid
0x140007f1b  test    eax, eax
0x140007f1d  jns     short loc_140007F51
0x140007f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f26  cmp     rcx, rdi
0x140007f29  jz      short loc_140007F45
0x140007f2b  test    byte ptr [rcx+1Ch], 2
0x140007f2f  jz      short loc_140007F45
0x140007f31  mov     rcx, [rcx+10h]
0x140007f35  mov     edx, 29h ; ')'
0x140007f3a  mov     r9d, eax
0x140007f3d  mov     r8, rsi
0x140007f40  call    WPP_SF_d
0x140007f45  mov     edx, 231h
0x140007f4a  call    SafeRpcRevertToSelf
0x140007f4f  jmp     short loc_140007F07
0x140007f51  mov     edx, 238h
0x140007f56  call    SafeRpcRevertToSelf
0x140007f5b  mov     r14d, eax
0x140007f5e  test    eax, eax
0x140007f60  jz      short loc_140007F96
0x140007f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f69  cmp     rcx, rdi
0x140007f6c  jz      short loc_140007F8E
0x140007f6e  test    byte ptr [rcx+1Ch], 2
0x140007f72  jz      short loc_140007F8E
0x140007f74  mov     rcx, [rcx+10h]
0x140007f78  lea     r9, [rsp+1E0h+var_178]
0x140007f7d  mov     edx, 2Ah ; '*'
0x140007f82  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x140007f86  mov     r8, rsi
0x140007f89  call    WPP_SF_sd
0x140007f8e  mov     eax, r14d
0x140007f91  jmp     loc_140008246
0x140007f96  call    RefreshConnectionCheckParameters
0x140007f9b  lea     rcx, DeviceListCS; lpCriticalSection
0x140007fa2  call    cs:__imp_EnterCriticalSection
0x140007fa8  mov     rbx, cs:pDeviceList
0x140007faf  test    rbx, rbx
0x140007fb2  jz      loc_1400081A2
0x140007fb8  mov     eax, [rbx]
0x140007fba  cmp     [rsp+1E0h+DestinationLuid.LowPart], eax
0x140007fbe  jnz     short loc_140007FDF
0x140007fc0  mov     eax, [rbx+4]
0x140007fc3  cmp     [rsp+1E0h+DestinationLuid.HighPart], eax
0x140007fc7  jnz     short loc_140007FDF
0x140007fc9  mov     rcx, [rbx+20h]; String1
0x140007fcd  test    rcx, rcx
0x140007fd0  jz      short loc_140007FDF
0x140007fd2  mov     rdx, r13; String2
0x140007fd5  call    cs:__imp__wcsicmp
0x140007fdb  test    eax, eax
0x140007fdd  jz      short loc_140007FE8
0x140007fdf  mov     rbx, [rbx+40h]
0x140007fe3  test    rbx, rbx
0x140007fe6  jnz     short loc_140007FB8
0x140007fe8  test    rbx, rbx
0x140007feb  jz      loc_1400081A2
0x140007ff1  call    cs:__imp_GetTickCount64
0x140007ff7  mov     r8, cs:qword_140021B80
0x140007ffe  xor     r9d, r9d
0x140008001  cmp     [rbx+10h], r9d
0x140008005  cmovnz  r8, cs:qword_140021B78
0x14000800d  cmp     dword ptr [rbx+0Ch], 2
0x140008011  jz      loc_1400080D0
0x140008017  mov     rdx, [rbx+18h]
0x14000801b  add     rdx, r8
0x14000801e  cmp     rdx, rax
0x140008021  ja      loc_1400080D0
0x140008027  cmp     [rbx+14h], r9d
0x14000802b  jz      short loc_140008036
0x14000802d  test    r8, r8
0x140008030  jnz     loc_1400080D0
0x140008036  mov     r8, [rbx+38h]; Source
0x14000803a  lea     rcx, [rbp+0E0h+Destination]; Destination
0x14000803e  mov     edx, 105h; SizeInBytes
0x140008043  call    cs:__imp_strcpy_s
0x140008049  inc     dword ptr [rbx+14h]
0x14000804c  lea     rcx, DeviceListCS; lpCriticalSection
0x140008053  call    cs:__imp_LeaveCriticalSection
0x140008059  lea     rdx, [rsp+1E0h+var_1A0]
0x14000805e  lea     rcx, [rbp+0E0h+Destination]; int
0x140008062  call    CheckServerConnection
0x140008067  lea     rcx, DeviceListCS; lpCriticalSection
0x14000806e  call    cs:__imp_EnterCriticalSection
0x140008074  mov     rbx, cs:pDeviceList
0x14000807b  test    rbx, rbx
0x14000807e  jz      loc_140008130
0x140008084  mov     eax, [rbx]
0x140008086  cmp     [rsp+1E0h+DestinationLuid.LowPart], eax
0x14000808a  jnz     short loc_1400080AB
0x14000808c  mov     eax, [rbx+4]
0x14000808f  cmp     [rsp+1E0h+DestinationLuid.HighPart], eax
0x140008093  jnz     short loc_1400080AB
0x140008095  mov     rcx, [rbx+20h]; String1
0x140008099  test    rcx, rcx
0x14000809c  jz      short loc_1400080AB
0x14000809e  mov     rdx, r13; String2
0x1400080a1  call    cs:__imp__wcsicmp
0x1400080a7  test    eax, eax
0x1400080a9  jz      short loc_1400080B4
0x1400080ab  mov     rbx, [rbx+40h]
0x1400080af  test    rbx, rbx
0x1400080b2  jnz     short loc_140008084
0x1400080b4  test    rbx, rbx
0x1400080b7  jz      short loc_140008130
0x1400080b9  mov     eax, [rsp+1E0h+var_1A0]
0x1400080bd  mov     [rbx+10h], eax
0x1400080c0  call    cs:__imp_GetTickCount64
0x1400080c6  dec     dword ptr [rbx+14h]
0x1400080c9  mov     [rbx+18h], rax
0x1400080cd  xor     r9d, r9d
0x1400080d0  mov     rcx, [rbx+28h]
0x1400080d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400080d8  inc     rax
0x1400080db  cmp     [rcx+rax*2], r9w
0x1400080e0  jnz     short loc_1400080D8
0x1400080e2  mov     rcx, [rsp+1E0h+var_190]
0x1400080e7  inc     eax
0x1400080e9  mov     [rcx], eax
0x1400080eb  cmp     r12d, eax
0x1400080ee  jnb     short loc_140008156
0x1400080f0  mov     r14d, 0EAh
0x1400080f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080fd  cmp     rcx, rdi
0x140008100  jz      loc_1400081CE
0x140008106  test    byte ptr [rcx+1Ch], 2
0x14000810a  jz      loc_1400081CE
0x140008110  mov     rcx, [rcx+10h]
0x140008114  mov     [rsp+1E0h+var_1B0], eax
0x140008118  mov     rax, [rbx+28h]
0x14000811c  mov     [rsp+1E0h+var_1B8], r12d
0x140008121  mov     [rsp+1E0h+var_1C0], rax
0x140008126  call    WPP_SF_DSdd
0x14000812b  jmp     loc_1400081CE
0x140008130  mov     r9d, 8CAh
0x140008136  mov     r14d, r9d
0x140008139  mov     rcx, cs:WPP_GLOBAL_Control
0x140008140  cmp     rcx, rdi
0x140008143  jz      loc_1400081CE
0x140008149  test    byte ptr [rcx+1Ch], 2
0x14000814d  jz      short loc_1400081CE
0x14000814f  mov     edx, 2Ch ; ','
0x140008154  jmp     short loc_1400081C2
0x140008156  mov     eax, [rbx+0Ch]
0x140008159  mov     rdx, r12; SizeInWords
0x14000815c  mov     rcx, [rsp+1E0h+var_188]
0x140008161  mov     [rcx], eax
0x140008163  mov     rcx, [rsp+1E0h+var_180]
0x140008168  mov     eax, [rbx+10h]
0x14000816b  mov     [rcx], eax
0x14000816d  mov     rcx, r15; Destination
0x140008170  mov     r8, [rbx+28h]; Source
0x140008174  call    cs:__imp_wcscpy_s
0x14000817a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008181  cmp     rcx, rdi
0x140008184  jz      short loc_1400081CE
0x140008186  test    byte ptr [rcx+1Ch], 8
0x14000818a  jz      short loc_1400081CE
0x14000818c  mov     rcx, [rcx+10h]
0x140008190  mov     edx, 2Eh ; '.'
0x140008195  mov     r9, r15
0x140008198  mov     r8, rsi
0x14000819b  call    WPP_SF_S
0x1400081a0  jmp     short loc_1400081CE
0x1400081a2  mov     r9d, 8CAh
0x1400081a8  mov     r14d, r9d
0x1400081ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081b2  cmp     rcx, rdi
0x1400081b5  jz      short loc_1400081CE
0x1400081b7  test    byte ptr [rcx+1Ch], 2
0x1400081bb  jz      short loc_1400081CE
0x1400081bd  mov     edx, 2Bh ; '+'
0x1400081c2  mov     rcx, [rcx+10h]
0x1400081c6  mov     r8, rsi
0x1400081c9  call    WPP_SF_d
0x1400081ce  lea     rcx, DeviceListCS; lpCriticalSection
0x1400081d5  call    cs:__imp_LeaveCriticalSection
0x1400081db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081e2  cmp     rcx, rdi
0x1400081e5  jz      loc_140007F8E
0x1400081eb  test    byte ptr [rcx+1Ch], 2
0x1400081ef  jz      loc_140007F8E
0x1400081f5  mov     rcx, [rcx+10h]
0x1400081f9  mov     edx, 2Fh ; '/'
0x1400081fe  mov     r9d, r14d
0x140008201  mov     r8, rsi
0x140008204  call    WPP_SF_d
0x140008209  jmp     loc_140007F8E
0x14000820e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008215  lea     rdi, WPP_GLOBAL_Control
0x14000821c  cmp     rcx, rdi
0x14000821f  jz      short loc_140008241
0x140008221  test    byte ptr [rcx+1Ch], 2
0x140008225  jz      short loc_140008241
0x140008227  mov     rcx, [rcx+10h]
0x14000822b  lea     r9, [rsp+1E0h+var_178]
0x140008230  mov     edx, 26h ; '&'
0x140008235  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000823c  call    WPP_SF_s
0x140008241  mov     eax, 57h ; 'W'
0x140008246  mov     rcx, [rbp+0E0h+var_40]
0x14000824d  xor     rcx, rsp; StackCookie
0x140008250  call    __security_check_cookie
0x140008255  mov     rbx, [rsp+1E0h+arg_0]
0x14000825d  add     rsp, 1B0h
0x140008264  pop     r15
0x140008266  pop     r14
0x140008268  pop     r13
0x14000826a  pop     r12
0x14000826c  pop     rdi
0x14000826d  pop     rsi
0x14000826e  pop     rbp
0x14000826f  retn
```
