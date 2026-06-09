# DhcpEnumClasses

- ea: `0x18000d660`
- end: `0x18000d8d3`
- name: `DhcpEnumClasses`
- size: `627`
- prototype: `DWORD __stdcall(LPWSTR ServerIpAddress, DWORD ReservedMustBeZero, DHCP_RESUME_HANDLE *ResumeHandle, DWORD PreferredMaximum, LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray, DWORD *nRead, DWORD *nTotal)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000e8b0`

## callees

- `0x180002620`
- `0x180002c50`
- `0x180003080`
- `0x18000d660`
- `0x18000f4ec`
- `0x180010198`
- `0x180011ec4`
- `0x180012060`
- `0x180012850`
- `0x180012ad0`
- `0x180012b80`
- `0x180012d20`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180010d3e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010d3e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d723`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d773`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d7a5`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d723`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d773`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000d7a5`
- `WS2_32!__imp_ntohl` at `0x18000d81b`
- `WS2_32!__imp_ntohl` at `0x18000d86e`
- `WS2_32!__imp_ntohl` at `0x18000d81b`
- `WS2_32!__imp_ntohl` at `0x18000d86e`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
DWORD __stdcall DhcpEnumClasses(
        LPWSTR ServerIpAddress,
        DWORD ReservedMustBeZero,
        DHCP_RESUME_HANDLE *ResumeHandle,
        DWORD PreferredMaximum,
        LPDHCP_CLASS_INFO_ARRAY *ClassInfoArray,
        DWORD *nRead,
        DWORD *nTotal)
{
  __int64 v7; // r15
  __int64 v9; // rdi
  int v10; // ebx
  DWORD v11; // ebx
  int v12; // ecx
  LPWSTR CommandLineW; // rax
  int v14; // ecx
  char v15; // al
  LPWSTR v16; // rax
  int v17; // ecx
  u_long *v18; // r14
  u_long v19; // eax
  u_long v20; // ebx
  char v22; // [rsp+40h] [rbp-68h] BYREF
  DWORD v23; // [rsp+44h] [rbp-64h]
  __int64 v24; // [rsp+48h] [rbp-60h] BYREF
  __int128 v25; // [rsp+50h] [rbp-58h] BYREF
  _QWORD v26[9]; // [rsp+60h] [rbp-48h] BYREF

  v7 = *(_QWORD *)&PreferredMaximum;
  v9 = *(_QWORD *)&ReservedMustBeZero;
  v10 = (int)ServerIpAddress;
  memset(v26, 0, 32);
  v25 = 0;
  v22 = 77;
  v24 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_LSqq(
      (_DWORD)ServerIpAddress,
      ReservedMustBeZero,
      (_DWORD)ResumeHandle,
      (_DWORD)ServerIpAddress,
      ReservedMustBeZero,
      (char)ResumeHandle,
      PreferredMaximum);
  if ( !v9 || !ResumeHandle || v10 )
  {
    v11 = 87;
    goto LABEL_28;
  }
  if ( !v7 && *ResumeHandle )
  {
    v11 = 13;
    goto LABEL_28;
  }
  v22 = 77;
  LODWORD(v26[0]) = 1;
  v26[1] = &v22;
  v11 = DhcpAdapterNameToIfId(v9, &v24);
  if ( !v11 )
  {
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_SS(v14, 11, (unsigned int)WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids, v9, (__int64)CommandLineW);
    }
    v11 = RpcCliRequestParams(v12, (unsigned int)&v24, 0, 0, (__int64)v26, (__int64)&v25);
    v23 = v11;
    v15 = xmmword_18001E1E0;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v16 = GetCommandLineW();
      WPP_SF_DSS(v17, 12, (unsigned int)WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids, v11, v9, (__int64)v16);
      v15 = xmmword_18001E1E0;
    }
    if ( !v11 && (_DWORD)v25 )
    {
      if ( (unsigned int)v25 < 0xC )
      {
        if ( (v15 & 2) != 0 )
          WPP_SF_dd(1025, 13, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids, (unsigned int)v25, 12);
LABEL_20:
        v11 = 1359;
        goto LABEL_28;
      }
      v18 = (u_long *)*((_QWORD *)&v25 + 1);
      v19 = ntohl(*(_DWORD *)(*((_QWORD *)&v25 + 1) + 8LL));
      v20 = v19;
      if ( !v19 )
      {
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_(1025, 14, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids);
        goto LABEL_20;
      }
      if ( (unsigned int)v25 < (unsigned __int64)v19 + 12 )
      {
        if ( (xmmword_18001E1E0 & 2) != 0 )
          WPP_SF_dd(1025, 15, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids, (unsigned int)v25, v19 + 12);
        goto LABEL_20;
      }
      *v18 = ntohl(*v18);
      v11 = ConvertFromBufferToClassInfo(v18 + 3, v20, v7, ResumeHandle);
    }
  }
LABEL_28:
  DhcpMidlUserFree((char *)&v25 + 8);
  LODWORD(v25) = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 16, (unsigned int)WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids, v9, v11);
  return v11;
}

```

## disassembly

```asm
0x18000d660  mov     rax, rsp
0x18000d663  mov     [rax+20h], r9
0x18000d667  mov     [rax+18h], r8
0x18000d66b  mov     [rax+10h], rdx
0x18000d66f  push    rbx
0x18000d670  push    rsi
0x18000d671  push    rdi
0x18000d672  push    r14
0x18000d674  push    r15
0x18000d676  sub     rsp, 80h
0x18000d67d  mov     r15, r9
0x18000d680  mov     rsi, r8
0x18000d683  mov     rdi, rdx
0x18000d686  mov     ebx, ecx
0x18000d688  xorps   xmm0, xmm0
0x18000d68b  movups  xmmword ptr [rax-48h], xmm0
0x18000d68f  movups  xmmword ptr [rax-38h], xmm0
0x18000d693  movups  xmmword ptr [rax-58h], xmm0
0x18000d697  mov     byte ptr [rax-68h], 4Dh ; 'M'
0x18000d69b  mov     qword ptr [rax-60h], 0
0x18000d6a3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d6aa  jz      short loc_18000D6C1
0x18000d6ac  mov     [rax-78h], r9
0x18000d6b0  mov     [rax-80h], r8
0x18000d6b4  mov     [rsp+0A8h+var_88], rdx
0x18000d6b9  mov     r9d, ecx
0x18000d6bc  call    WPP_SF_LSqq
0x18000d6c1  test    rdi, rdi
0x18000d6c4  jnz     short loc_18000D6D0
0x18000d6c6  mov     ebx, 57h ; 'W'
0x18000d6cb  jmp     loc_18000D88A
0x18000d6d0  test    rsi, rsi
0x18000d6d3  jz      short loc_18000D6C6
0x18000d6d5  test    ebx, ebx
0x18000d6d7  jnz     short loc_18000D6C6
0x18000d6d9  test    r15, r15
0x18000d6dc  jnz     short loc_18000D6EC
0x18000d6de  cmp     [rsi], r15d
0x18000d6e1  jz      short loc_18000D6EC
0x18000d6e3  lea     ebx, [r15+0Dh]
0x18000d6e7  jmp     loc_18000D88A
0x18000d6ec  mov     [rsp+0A8h+var_68], 4Dh ; 'M'
0x18000d6f1  mov     [rsp+0A8h+var_48], 1
0x18000d6f9  lea     rax, [rsp+0A8h+var_68]
0x18000d6fe  mov     [rsp+0A8h+var_40], rax
0x18000d703  lea     rdx, [rsp+0A8h+var_60]
0x18000d708  mov     rcx, rdi
0x18000d70b  call    DhcpAdapterNameToIfId
0x18000d710  mov     ebx, eax
0x18000d712  test    eax, eax
0x18000d714  jnz     loc_18000D88A
0x18000d71a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d721  jz      short loc_18000D741
0x18000d723  call    cs:__imp_GetCommandLineW
0x18000d729  lea     edx, [rbx+0Bh]
0x18000d72c  mov     [rsp+0A8h+var_88], rax
0x18000d731  mov     r9, rdi
0x18000d734  lea     r8, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids
0x18000d73b  call    WPP_SF_SS
0x18000d740  nop
0x18000d741  lea     rax, [rsp+0A8h+var_58]
0x18000d746  mov     [rsp+0A8h+var_80], rax
0x18000d74b  lea     rax, [rsp+0A8h+var_48]
0x18000d750  mov     [rsp+0A8h+var_88], rax
0x18000d755  xor     r9d, r9d
0x18000d758  xor     r8d, r8d
0x18000d75b  lea     rdx, [rsp+0A8h+var_60]
0x18000d760  call    RpcCliRequestParams
0x18000d765  mov     ebx, eax
0x18000d767  mov     [rsp+0A8h+var_64], eax
0x18000d76b  jmp     short loc_18000D79B
0x18000d76d  mov     ebx, eax
0x18000d76f  mov     [rsp+0A8h+var_64], eax
0x18000d773  call    cs:__imp_GetCommandLineW
0x18000d779  mov     rdx, rax
0x18000d77c  mov     ecx, ebx
0x18000d77e  call    TraceRpcException
0x18000d783  mov     r15, [rsp+0A8h+arg_18]
0x18000d78b  mov     rsi, [rsp+0A8h+arg_10]
0x18000d793  mov     rdi, [rsp+0A8h+arg_8]
0x18000d79b  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000d7a1  test    al, 10h
0x18000d7a3  jz      short loc_18000D7CF
0x18000d7a5  call    cs:__imp_GetCommandLineW
0x18000d7ab  mov     edx, 0Ch
0x18000d7b0  mov     [rsp+0A8h+var_80], rax
0x18000d7b5  mov     [rsp+0A8h+var_88], rdi
0x18000d7ba  mov     r9d, ebx
0x18000d7bd  lea     r8, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids
0x18000d7c4  call    WPP_SF_DSS
0x18000d7c9  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000d7cf  test    ebx, ebx
0x18000d7d1  jnz     loc_18000D88A
0x18000d7d7  mov     r9d, [rsp+0A8h+var_58]
0x18000d7dc  test    r9d, r9d
0x18000d7df  jz      loc_18000D88A
0x18000d7e5  cmp     r9d, 0Ch
0x18000d7e9  jnb     short loc_18000D812
0x18000d7eb  test    al, 2
0x18000d7ed  jz      short loc_18000D80B
0x18000d7ef  lea     edx, [rbx+0Dh]
0x18000d7f2  mov     dword ptr [rsp+0A8h+var_88], 0Ch
0x18000d7fa  mov     ecx, 401h
0x18000d7ff  lea     r8, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids
0x18000d806  call    WPP_SF_dd
0x18000d80b  mov     ebx, 54Fh
0x18000d810  jmp     short loc_18000D88A
0x18000d812  mov     r14, [rsp+0A8h+var_50]
0x18000d817  mov     ecx, [r14+8]; netlong
0x18000d81b  call    cs:__imp_ntohl
0x18000d821  mov     ebx, eax
0x18000d823  test    eax, eax
0x18000d825  jnz     short loc_18000D846
0x18000d827  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000d82e  jz      short loc_18000D80B
0x18000d830  lea     edx, [rax+0Eh]
0x18000d833  mov     ecx, 401h
0x18000d838  lea     r8, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids
0x18000d83f  call    WPP_SF_
0x18000d844  jmp     short loc_18000D80B
0x18000d846  lea     rcx, [rbx+0Ch]
0x18000d84a  mov     r9d, [rsp+0A8h+var_58]
0x18000d84f  cmp     r9, rcx
0x18000d852  jnb     short loc_18000D86B
0x18000d854  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000d85b  jz      short loc_18000D80B
0x18000d85d  lea     eax, [rbx+0Ch]
0x18000d860  mov     edx, 0Fh
0x18000d865  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000d869  jmp     short loc_18000D7FA
0x18000d86b  mov     ecx, [r14]; netlong
0x18000d86e  call    cs:__imp_ntohl
0x18000d874  mov     [r14], eax
0x18000d877  lea     rcx, [r14+0Ch]
0x18000d87b  mov     r9, rsi
0x18000d87e  mov     r8, r15
0x18000d881  mov     edx, ebx
0x18000d883  call    ConvertFromBufferToClassInfo
0x18000d888  mov     ebx, eax
0x18000d88a  lea     rcx, [rsp+0A8h+var_50]
0x18000d88f  call    DhcpMidlUserFree
0x18000d894  mov     [rsp+0A8h+var_58], 0
0x18000d89c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000d8a3  jz      short loc_18000D8C2
0x18000d8a5  mov     edx, 10h
0x18000d8aa  mov     ecx, 404h
0x18000d8af  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000d8b3  mov     r9, rdi
0x18000d8b6  lea     r8, WPP_4a365f51140635eba2bc11e964f4e84a_Traceguids
0x18000d8bd  call    WPP_SF_SD
0x18000d8c2  mov     eax, ebx
0x18000d8c4  add     rsp, 80h
0x18000d8cb  pop     r15
0x18000d8cd  pop     r14
0x18000d8cf  pop     rdi
0x18000d8d0  pop     rsi
0x18000d8d1  pop     rbx
0x18000d8d2  retn
0x180010d30  push    rbp
0x180010d32  sub     rsp, 40h
0x180010d36  mov     rbp, rdx
0x180010d39  mov     rcx, [rcx]
0x180010d3c  mov     ecx, [rcx]; ExceptionCode
0x180010d3e  call    cs:__imp_I_RpcExceptionFilter
0x180010d44  nop
0x180010d45  add     rsp, 40h
0x180010d49  pop     rbp
0x180010d4a  retn
```
