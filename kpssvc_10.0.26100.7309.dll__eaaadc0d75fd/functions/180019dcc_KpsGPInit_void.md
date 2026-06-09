# KpsGPInit(void)

- ea: `0x180019dcc`
- end: `0x18001a0b5`
- name: `?KpsGPInit@@YAKXZ`
- size: `745`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cf60`

## callees

- `0x180019a20`
- `0x180019dcc`
- `0x18001a1e0`
- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae38`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019f03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f1f`
- `ntdll!RtlInitializeCriticalSection` at `0x180019e27`
- `ntdll!RtlInitializeCriticalSection` at `0x180019e27`
- `ntdll!RtlDeleteCriticalSection` at `0x180019f66`
- `ntdll!RtlDeleteCriticalSection` at `0x180019f66`

## string_xrefs

- `0x180019e81`: `System\CurrentControlSet\Services\KPSSVC\Settings`

## pseudocode

```c
__int64 KpsGPInit(void)
{
  unsigned int v0; // eax
  unsigned int v1; // edi
  _QWORD *v2; // rbx
  unsigned int v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  _QWORD *v12; // rcx
  unsigned int v13; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int *v15; // [rsp+48h] [rbp-20h]
  int v16; // [rsp+50h] [rbp-18h]
  int v17; // [rsp+54h] [rbp-14h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
  v0 = RtlInitializeCriticalSection(&stru_18003A958);
  v1 = v0;
  if ( v0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v0);
LABEL_23:
    v2 = WPP_GLOBAL_Control;
LABEL_24:
    memset_0(&KpsGp, 0, 0x80u);
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 1) != 0 )
    {
      v17 = 0;
      v15 = &v13;
      v13 = v1;
      v16 = 4;
      McGenEventWrite_EventWriteTransfer(v9, GPInitFailure, v10, 2, v14);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v2 + 28) & 0x10) != 0 )
      {
        WPP_SF_D(v2[2], 60, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v1);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
        WPP_SF_D(v2[2], 61, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v1);
    }
    return v1;
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\KPSSVC\\Settings", 0, 0x20019u, &hKey);
  v1 = v3;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v5 = 55;
LABEL_16:
    WPP_SF_D(v4[2], v5, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, v3);
LABEL_22:
    RtlDeleteCriticalSection(&stru_18003A958);
    goto LABEL_23;
  }
  v3 = KpsGPRead();
  v1 = v3;
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v5 = 56;
    goto LABEL_16;
  }
  hObject = CreateEventW(0, 0, 0, 0);
  if ( !hObject )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_55dedb296c8337923463e18711d485b4_Traceguids, LastError);
    KpsFreeUrlPrefixList((struct _KPS_URL_PREFIX_LIST *)&xmmword_18003A998);
    goto LABEL_22;
  }
  KpsGp = 1;
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, GPInitSuccess, v7, 1, v14);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x20) != 0 )
      WPP_SF_(v12[2], 59, &WPP_55dedb296c8337923463e18711d485b4_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180019dcc  mov     [rsp+arg_0], rbx
0x180019dd1  mov     [rsp+arg_8], rbp
0x180019dd6  mov     [rsp+arg_10], rsi
0x180019ddb  push    rdi
0x180019ddc  sub     rsp, 60h
0x180019de0  mov     rax, cs:__security_cookie
0x180019de7  xor     rax, rsp
0x180019dea  mov     [rsp+68h+var_10], rax
0x180019def  mov     rcx, cs:WPP_GLOBAL_Control
0x180019df6  lea     rsi, WPP_GLOBAL_Control
0x180019dfd  lea     rbp, WPP_55dedb296c8337923463e18711d485b4_Traceguids
0x180019e04  cmp     rcx, rsi
0x180019e07  jz      short loc_180019E20
0x180019e09  test    byte ptr [rcx+1Ch], 20h
0x180019e0d  jz      short loc_180019E20
0x180019e0f  mov     rcx, [rcx+10h]
0x180019e13  mov     edx, 35h ; '5'
0x180019e18  mov     r8, rbp
0x180019e1b  call    WPP_SF_
0x180019e20  lea     rcx, stru_18003A958; CriticalSection
0x180019e27  call    cs:__imp_RtlInitializeCriticalSection
0x180019e2e  nop     dword ptr [rax+rax+00h]
0x180019e33  mov     edi, eax
0x180019e35  test    eax, eax
0x180019e37  jz      short loc_180019E6C
0x180019e39  mov     rbx, cs:WPP_GLOBAL_Control
0x180019e40  cmp     rbx, rsi
0x180019e43  jz      loc_180019F79
0x180019e49  test    byte ptr [rbx+1Ch], 1
0x180019e4d  jz      loc_180019F79
0x180019e53  mov     rcx, [rbx+10h]
0x180019e57  mov     edx, 36h ; '6'
0x180019e5c  mov     r9d, eax
0x180019e5f  mov     r8, rbp
0x180019e62  call    WPP_SF_D
0x180019e67  jmp     loc_180019F72
0x180019e6c  lea     rax, hKey
0x180019e73  mov     r9d, 20019h; samDesired
0x180019e79  xor     r8d, r8d; ulOptions
0x180019e7c  mov     [rsp+68h+phkResult], rax; phkResult
0x180019e81  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\KP"...
0x180019e88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019e8f  call    cs:__imp_RegOpenKeyExW
0x180019e96  nop     dword ptr [rax+rax+00h]
0x180019e9b  mov     edi, eax
0x180019e9d  test    eax, eax
0x180019e9f  jz      short loc_180019EC2
0x180019ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ea8  cmp     rcx, rsi
0x180019eab  jz      loc_180019F5F
0x180019eb1  test    byte ptr [rcx+1Ch], 1
0x180019eb5  jz      loc_180019F5F
0x180019ebb  mov     edx, 37h ; '7'
0x180019ec0  jmp     short loc_180019EE8
0x180019ec2  call    ?KpsGPRead@@YAKXZ; KpsGPRead(void)
0x180019ec7  mov     edi, eax
0x180019ec9  test    eax, eax
0x180019ecb  jz      short loc_180019EF9
0x180019ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ed4  cmp     rcx, rsi
0x180019ed7  jz      loc_180019F5F
0x180019edd  test    byte ptr [rcx+1Ch], 1
0x180019ee1  jz      short loc_180019F5F
0x180019ee3  mov     edx, 38h ; '8'
0x180019ee8  mov     rcx, [rcx+10h]
0x180019eec  mov     r9d, eax
0x180019eef  mov     r8, rbp
0x180019ef2  call    WPP_SF_D
0x180019ef7  jmp     short loc_180019F5F
0x180019ef9  xor     r9d, r9d; lpName
0x180019efc  xor     r8d, r8d; bInitialState
0x180019eff  xor     edx, edx; bManualReset
0x180019f01  xor     ecx, ecx; lpEventAttributes
0x180019f03  call    cs:__imp_CreateEventW
0x180019f0a  nop     dword ptr [rax+rax+00h]
0x180019f0f  mov     cs:hObject, rax
0x180019f16  test    rax, rax
0x180019f19  jnz     loc_18001A01D
0x180019f1f  call    cs:__imp_GetLastError
0x180019f26  nop     dword ptr [rax+rax+00h]
0x180019f2b  mov     edi, eax
0x180019f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f34  cmp     rcx, rsi
0x180019f37  jz      short loc_180019F53
0x180019f39  test    byte ptr [rcx+1Ch], 1
0x180019f3d  jz      short loc_180019F53
0x180019f3f  mov     rcx, [rcx+10h]
0x180019f43  mov     edx, 39h ; '9'
0x180019f48  mov     r9d, eax
0x180019f4b  mov     r8, rbp
0x180019f4e  call    WPP_SF_D
0x180019f53  lea     rcx, xmmword_18003A998; struct _KPS_URL_PREFIX_LIST *
0x180019f5a  call    ?KpsFreeUrlPrefixList@@YAXPEAU_KPS_URL_PREFIX_LIST@@@Z; KpsFreeUrlPrefixList(_KPS_URL_PREFIX_LIST *)
0x180019f5f  lea     rcx, stru_18003A958; CriticalSection
0x180019f66  call    cs:__imp_RtlDeleteCriticalSection
0x180019f6d  nop     dword ptr [rax+rax+00h]
0x180019f72  mov     rbx, cs:WPP_GLOBAL_Control
0x180019f79  xor     edx, edx; Val
0x180019f7b  lea     rcx, ?KpsGp@@3U_KPS_GP@@A; void *
0x180019f82  mov     r8d, 80h; Size
0x180019f88  call    memset_0
0x180019f8d  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 1
0x180019f94  jz      short loc_180019FD4
0x180019f96  and     [rsp+68h+var_14], 0
0x180019f9b  lea     rax, [rsp+68h+var_38]
0x180019fa0  mov     [rsp+68h+var_20], rax
0x180019fa5  lea     rdx, GPInitFailure
0x180019fac  lea     rax, [rsp+68h+var_30]
0x180019fb1  mov     [rsp+68h+var_38], edi
0x180019fb5  mov     r9d, 2
0x180019fbb  mov     [rsp+68h+phkResult], rax
0x180019fc0  mov     [rsp+68h+var_18], 4
0x180019fc8  call    McGenEventWrite_EventWriteTransfer
0x180019fcd  mov     rbx, cs:WPP_GLOBAL_Control
0x180019fd4  cmp     rbx, rsi
0x180019fd7  jz      short loc_18001A019
0x180019fd9  test    byte ptr [rbx+1Ch], 10h
0x180019fdd  jz      short loc_180019FFA
0x180019fdf  mov     rcx, [rbx+10h]
0x180019fe3  mov     edx, 3Ch ; '<'
0x180019fe8  mov     r9d, edi
0x180019feb  mov     r8, rbp
0x180019fee  call    WPP_SF_D
0x180019ff3  mov     rbx, cs:WPP_GLOBAL_Control
0x180019ffa  cmp     rbx, rsi
0x180019ffd  jz      short loc_18001A019
0x180019fff  test    byte ptr [rbx+1Ch], 20h
0x18001a003  jz      short loc_18001A019
0x18001a005  mov     rcx, [rbx+10h]
0x18001a009  mov     edx, 3Dh ; '='
0x18001a00e  mov     r9d, edi
0x18001a011  mov     r8, rbp
0x18001a014  call    WPP_SF_D
0x18001a019  mov     eax, edi
0x18001a01b  jmp     short loc_18001A091
0x18001a01d  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 8
0x18001a024  mov     cs:?KpsGp@@3U_KPS_GP@@A, 1; _KPS_GP KpsGp
0x18001a02b  jz      short loc_18001A049
0x18001a02d  lea     rax, [rsp+68h+var_30]
0x18001a032  mov     r9d, 1
0x18001a038  lea     rdx, GPInitSuccess
0x18001a03f  mov     [rsp+68h+phkResult], rax
0x18001a044  call    McGenEventWrite_EventWriteTransfer
0x18001a049  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a050  cmp     rcx, rsi
0x18001a053  jz      short loc_18001A08F
0x18001a055  test    byte ptr [rcx+1Ch], 10h
0x18001a059  jz      short loc_18001A073
0x18001a05b  mov     rcx, [rcx+10h]
0x18001a05f  mov     edx, 3Ah ; ':'
0x18001a064  mov     r8, rbp
0x18001a067  call    WPP_SF_
0x18001a06c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a073  cmp     rcx, rsi
0x18001a076  jz      short loc_18001A08F
0x18001a078  test    byte ptr [rcx+1Ch], 20h
0x18001a07c  jz      short loc_18001A08F
0x18001a07e  mov     rcx, [rcx+10h]
0x18001a082  mov     edx, 3Bh ; ';'
0x18001a087  mov     r8, rbp
0x18001a08a  call    WPP_SF_
0x18001a08f  xor     eax, eax
0x18001a091  mov     rcx, [rsp+68h+var_10]
0x18001a096  xor     rcx, rsp; StackCookie
0x18001a099  call    __security_check_cookie
0x18001a09e  lea     r11, [rsp+68h+var_8]
0x18001a0a3  mov     rbx, [r11+10h]
0x18001a0a7  mov     rbp, [r11+18h]
0x18001a0ab  mov     rsi, [r11+20h]
0x18001a0af  mov     rsp, r11
0x18001a0b2  pop     rdi
0x18001a0b3  retn
```
