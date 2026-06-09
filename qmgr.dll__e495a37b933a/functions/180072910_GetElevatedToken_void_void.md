# GetElevatedToken(void *,void * *)

- ea: `0x180072910`
- end: `0x180072c4a`
- name: `?GetElevatedToken@@YAXPEAXPEAPEAX@Z`
- size: `826`
- prototype: `void __fastcall(HANDLE TokenHandle, PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018880`

## callees

- `0x180072910`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b96`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180072a2d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180072a2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072954`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072b8c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072954`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180072b8c`

## pseudocode

```c
void __fastcall GetElevatedToken(HANDLE TokenHandle, PHANDLE phNewToken)
{
  DWORD LastError; // eax
  signed int v5; // ebx
  DWORD v6; // eax
  signed int v7; // ebx
  DWORD v8; // eax
  signed int v9; // ebx
  EVENT_LOG *v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // eax
  signed int v13; // ebx
  void *v14; // [rsp+30h] [rbp-29h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  __int128 v16; // [rsp+48h] [rbp-11h]
  signed int v17; // [rsp+58h] [rbp-1h]
  int v18; // [rsp+5Ch] [rbp+3h]
  int v19; // [rsp+60h] [rbp+7h]
  DWORD ReturnLength; // [rsp+C8h] [rbp+6Fh] BYREF
  int TokenInformation; // [rsp+D0h] [rbp+77h] BYREF
  int v22; // [rsp+D8h] [rbp+7Fh] BYREF

  *phNewToken = 0;
  ReturnLength = 0;
  v22 = 0;
  TokenInformation = 0;
  v14 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, LastError);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v17 = v5;
    v18 = 1537;
    pExceptionObject = &ComError::`vftable';
    v19 = 1;
    v16 = 0;
    throw (ComError *)&pExceptionObject;
  }
  if ( TokenInformation == 2 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
LABEL_12:
    if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenPrimary, phNewToken) )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v6);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v17 = v7;
      v18 = 1597;
      pExceptionObject = &ComError::`vftable';
      v19 = 1;
      v16 = 0;
      throw (ComError *)&pExceptionObject;
    }
    return;
  }
  if ( TokenInformation == 1 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenElevation, &v22, 4u, &ReturnLength) )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v8);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v17 = v9;
      v18 = 1565;
      pExceptionObject = &ComError::`vftable';
      v19 = 1;
      v16 = 0;
      throw (ComError *)&pExceptionObject;
    }
    if ( v22 )
      goto LABEL_12;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return;
    v11 = 56;
LABEL_41:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
    return;
  }
  if ( !GetTokenInformation(TokenHandle, TokenLinkedToken, &v14, 8u, &ReturnLength) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v12);
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v17 = v13;
    v18 = 1610;
    pExceptionObject = &ComError::`vftable';
    v19 = 1;
    v16 = 0;
    throw (ComError *)&pExceptionObject;
  }
  *phNewToken = v14;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 59;
    goto LABEL_41;
  }
}

```

## disassembly

```asm
0x180072910  mov     [rsp-8+arg_0], rbx
0x180072915  push    rbp
0x180072916  push    rsi
0x180072917  push    rdi
0x180072918  lea     rbp, [rsp-47h]
0x18007291d  sub     rsp, 0A0h
0x180072924  xor     eax, eax
0x180072926  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18007292a  mov     [rdx], rax
0x18007292d  mov     rdi, rdx
0x180072930  mov     [rbp+57h+arg_8], eax
0x180072933  mov     r9d, 4; TokenInformationLength
0x180072939  mov     [rbp+57h+arg_18], eax
0x18007293c  mov     edx, 12h; TokenInformationClass
0x180072941  mov     [rbp+57h+TokenInformation], eax
0x180072944  mov     rbx, rcx
0x180072947  mov     [rbp+57h+var_80], rax
0x18007294b  lea     rax, [rbp+57h+arg_8]
0x18007294f  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180072954  call    cs:__imp_GetTokenInformation
0x18007295a  test    eax, eax
0x18007295c  jnz     short loc_1800729D8
0x18007295e  call    cs:__imp_GetLastError
0x180072964  mov     ebx, eax
0x180072966  mov     rcx, cs:WPP_GLOBAL_Control
0x18007296d  lea     rsi, WPP_GLOBAL_Control
0x180072974  cmp     rcx, rsi
0x180072977  jz      short loc_180072997
0x180072979  test    byte ptr [rcx+1Ch], 4
0x18007297d  jz      short loc_180072997
0x18007297f  mov     rcx, [rcx+10h]
0x180072983  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18007298a  mov     edx, 35h ; '5'
0x18007298f  mov     r9d, eax
0x180072992  call    WPP_SF_d
0x180072997  test    ebx, ebx
0x180072999  jle     short loc_1800729A4
0x18007299b  movzx   ebx, bx
0x18007299e  or      ebx, 80070000h
0x1800729a4  xorps   xmm0, xmm0
0x1800729a7  mov     [rbp+57h+var_58], ebx
0x1800729aa  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800729b1  mov     [rbp+57h+var_54], 601h
0x1800729b8  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800729bf  mov     [rbp+57h+pExceptionObject], rax
0x1800729c3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800729c7  mov     [rbp+57h+var_50], 1
0x1800729ce  movups  [rbp+57h+var_68], xmm0
0x1800729d2  call    _CxxThrowException_0
0x1800729d8  mov     eax, [rbp+57h+TokenInformation]
0x1800729db  lea     rsi, WPP_GLOBAL_Control
0x1800729e2  cmp     eax, 2
0x1800729e5  jnz     loc_180072AAE
0x1800729eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800729f2  cmp     rcx, rsi
0x1800729f5  jz      short loc_180072A12
0x1800729f7  test    byte ptr [rcx+1Ch], 1
0x1800729fb  jz      short loc_180072A12
0x1800729fd  mov     rcx, [rcx+10h]
0x180072a01  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180072a08  mov     edx, 36h ; '6'
0x180072a0d  call    WPP_SF_
0x180072a12  mov     [rsp+0B0h+phNewToken], rdi; phNewToken
0x180072a17  mov     r9d, 2; ImpersonationLevel
0x180072a1d  xor     r8d, r8d; lpTokenAttributes
0x180072a20  mov     dword ptr [rsp+0B0h+ReturnLength], 1; TokenType
0x180072a28  xor     edx, edx; dwDesiredAccess
0x180072a2a  mov     rcx, rbx; hExistingToken
0x180072a2d  call    cs:__imp_DuplicateTokenEx
0x180072a33  test    eax, eax
0x180072a35  jnz     loc_180072C37
0x180072a3b  call    cs:__imp_GetLastError
0x180072a41  mov     ebx, eax
0x180072a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180072a4a  cmp     rcx, rsi
0x180072a4d  jz      short loc_180072A6D
0x180072a4f  test    byte ptr [rcx+1Ch], 4
0x180072a53  jz      short loc_180072A6D
0x180072a55  mov     rcx, [rcx+10h]
0x180072a59  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180072a60  mov     edx, 39h ; '9'
0x180072a65  mov     r9d, eax
0x180072a68  call    WPP_SF_d
0x180072a6d  test    ebx, ebx
0x180072a6f  jle     short loc_180072A7A
0x180072a71  movzx   ebx, bx
0x180072a74  or      ebx, 80070000h
0x180072a7a  xorps   xmm0, xmm0
0x180072a7d  mov     [rbp+57h+var_58], ebx
0x180072a80  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180072a87  mov     [rbp+57h+var_54], 63Dh
0x180072a8e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180072a95  mov     [rbp+57h+pExceptionObject], rax
0x180072a99  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180072a9d  mov     [rbp+57h+var_50], 1
0x180072aa4  movups  [rbp+57h+var_68], xmm0
0x180072aa8  call    _CxxThrowException_0
0x180072aae  cmp     eax, 1
0x180072ab1  mov     rcx, rbx; TokenHandle
0x180072ab4  lea     rax, [rbp+57h+arg_8]
0x180072ab8  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180072abd  jnz     loc_180072B7D
0x180072ac3  mov     r9d, 4; TokenInformationLength
0x180072ac9  lea     r8, [rbp+57h+arg_18]; TokenInformation
0x180072acd  mov     edx, 14h; TokenInformationClass
0x180072ad2  call    cs:__imp_GetTokenInformation
0x180072ad8  test    eax, eax
0x180072ada  jnz     short loc_180072B4F
0x180072adc  call    cs:__imp_GetLastError
0x180072ae2  mov     ebx, eax
0x180072ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180072aeb  cmp     rcx, rsi
0x180072aee  jz      short loc_180072B0E
0x180072af0  test    byte ptr [rcx+1Ch], 4
0x180072af4  jz      short loc_180072B0E
0x180072af6  mov     rcx, [rcx+10h]
0x180072afa  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180072b01  mov     edx, 37h ; '7'
0x180072b06  mov     r9d, eax
0x180072b09  call    WPP_SF_d
0x180072b0e  test    ebx, ebx
0x180072b10  jle     short loc_180072B1B
0x180072b12  movzx   ebx, bx
0x180072b15  or      ebx, 80070000h
0x180072b1b  xorps   xmm0, xmm0
0x180072b1e  mov     [rbp+57h+var_58], ebx
0x180072b21  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180072b28  mov     [rbp+57h+var_54], 61Dh
0x180072b2f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180072b36  mov     [rbp+57h+pExceptionObject], rax
0x180072b3a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180072b3e  mov     [rbp+57h+var_50], 1
0x180072b45  movups  [rbp+57h+var_68], xmm0
0x180072b49  call    _CxxThrowException_0
0x180072b4f  cmp     [rbp+57h+arg_18], 0
0x180072b53  jnz     loc_180072A12
0x180072b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180072b60  cmp     rcx, rsi
0x180072b63  jz      loc_180072C37
0x180072b69  test    byte ptr [rcx+1Ch], 1
0x180072b6d  jz      loc_180072C37
0x180072b73  mov     edx, 38h ; '8'
0x180072b78  jmp     loc_180072C27
0x180072b7d  mov     r9d, 8; TokenInformationLength
0x180072b83  lea     r8, [rbp+57h+var_80]; TokenInformation
0x180072b87  mov     edx, 13h; TokenInformationClass
0x180072b8c  call    cs:__imp_GetTokenInformation
0x180072b92  test    eax, eax
0x180072b94  jnz     short loc_180072C09
0x180072b96  call    cs:__imp_GetLastError
0x180072b9c  mov     ebx, eax
0x180072b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ba5  cmp     rcx, rsi
0x180072ba8  jz      short loc_180072BC8
0x180072baa  test    byte ptr [rcx+1Ch], 4
0x180072bae  jz      short loc_180072BC8
0x180072bb0  mov     rcx, [rcx+10h]
0x180072bb4  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180072bbb  mov     edx, 3Ah ; ':'
0x180072bc0  mov     r9d, eax
0x180072bc3  call    WPP_SF_d
0x180072bc8  test    ebx, ebx
0x180072bca  jle     short loc_180072BD5
0x180072bcc  movzx   ebx, bx
0x180072bcf  or      ebx, 80070000h
0x180072bd5  xorps   xmm0, xmm0
0x180072bd8  mov     [rbp+57h+var_58], ebx
0x180072bdb  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180072be2  mov     [rbp+57h+var_54], 64Ah
0x180072be9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180072bf0  mov     [rbp+57h+pExceptionObject], rax
0x180072bf4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180072bf8  mov     [rbp+57h+var_50], 1
0x180072bff  movups  [rbp+57h+var_68], xmm0
0x180072c03  call    _CxxThrowException_0
0x180072c09  mov     rax, [rbp+57h+var_80]
0x180072c0d  mov     [rdi], rax
0x180072c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c17  cmp     rcx, rsi
0x180072c1a  jz      short loc_180072C37
0x180072c1c  test    byte ptr [rcx+1Ch], 1
0x180072c20  jz      short loc_180072C37
0x180072c22  mov     edx, 3Bh ; ';'
0x180072c27  mov     rcx, [rcx+10h]
0x180072c2b  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180072c32  call    WPP_SF_
0x180072c37  mov     rbx, [rsp+0B0h+arg_0]
0x180072c3f  add     rsp, 0A0h
0x180072c46  pop     rdi
0x180072c47  pop     rsi
0x180072c48  pop     rbp
0x180072c49  retn
```
