# CopyTokenSid(void *)

- ea: `0x180018d00`
- end: `0x18001902e`
- name: `?CopyTokenSid@@YAPEAXPEAX@Z`
- size: `814`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a680`
- `0x18000e790`
- `0x180016ee0`
- `0x180019040`
- `0x180027a48`
- `0x180059860`
- `0x18006ecfc`
- `0x180076344`
- `0x18007d8d4`
- `0x1800a0738`

## callees

- `0x180018d00`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018d58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018db1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018d58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fff`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018dcb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018dcb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018d9a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018d9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018d86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018d86`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CopyTokenSid(HANDLE TokenHandle)
{
  DWORD v2; // esi
  PSID *v3; // rax
  PSID *v4; // rbx
  PSID v5; // r14
  DWORD LengthSid; // esi
  void *v7; // rax
  void *v8; // rdi
  unsigned int LastError; // ecx
  unsigned int v11; // ecx
  DWORD v12; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-19h] BYREF
  __int128 v14; // [rsp+38h] [rbp-11h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  int v17; // [rsp+50h] [rbp+7h]
  DWORD TokenInformationLength; // [rsp+B8h] [rbp+6Fh] BYREF
  PSID *v19; // [rsp+C0h] [rbp+77h]

  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = LastError;
    v16 = 1044;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v2 = TokenInformationLength;
  v3 = (PSID *)HeapAlloc(hBitsHeap, 8u, TokenInformationLength);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v2);
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = -2147024882;
    v16 = 0;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v19 = v3;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
  {
    if ( (int)GetLastError() > 0 )
      v11 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v11 = GetLastError();
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = v11;
    v16 = 1059;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v5 = *v4;
  LengthSid = GetLengthSid(*v4);
  v7 = HeapAlloc(hBitsHeap, 8u, LengthSid);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, LengthSid);
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = -2147024882;
    v16 = 0;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  if ( !CopySid(LengthSid, v7, v5) )
  {
    if ( !HeapFree(hBitsHeap, 0, v8)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v8, v12);
    }
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = -2147024882;
    v16 = 907;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  operator delete(v4, 1u);
  return v8;
}

```

## disassembly

```asm
0x180018d00  mov     [rsp-8+arg_0], rbx
0x180018d05  mov     [rsp-8+arg_18], rsi
0x180018d0a  push    rbp
0x180018d0b  push    rdi
0x180018d0c  push    r14
0x180018d0e  lea     rbp, [rsp-47h]
0x180018d13  sub     rsp, 90h
0x180018d1a  mov     rdi, rcx
0x180018d1d  mov     [rbp+57h+TokenInformationLength], 0
0x180018d24  lea     rax, [rbp+57h+TokenInformationLength]
0x180018d28  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180018d2d  xor     r9d, r9d; TokenInformationLength
0x180018d30  xor     r8d, r8d; TokenInformation
0x180018d33  mov     edx, 1; TokenInformationClass
0x180018d38  call    cs:__imp_GetTokenInformation
0x180018d3e  test    eax, eax
0x180018d40  jz      loc_180018E4F
0x180018d46  mov     esi, [rbp+57h+TokenInformationLength]
0x180018d49  mov     r8d, esi; dwBytes
0x180018d4c  mov     edx, 8; dwFlags
0x180018d51  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180018d58  call    cs:__imp_HeapAlloc
0x180018d5e  mov     rbx, rax
0x180018d61  test    rax, rax
0x180018d64  jz      loc_180018EB5
0x180018d6a  mov     [rbp+57h+arg_10], rax
0x180018d6e  lea     rax, [rbp+57h+TokenInformationLength]
0x180018d72  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180018d77  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180018d7b  mov     r8, rbx; TokenInformation
0x180018d7e  mov     edx, 1; TokenInformationClass
0x180018d83  mov     rcx, rdi; TokenHandle
0x180018d86  call    cs:__imp_GetTokenInformation
0x180018d8c  test    eax, eax
0x180018d8e  jz      loc_180018F1E
0x180018d94  mov     r14, [rbx]
0x180018d97  mov     rcx, r14; pSid
0x180018d9a  call    cs:__imp_GetLengthSid
0x180018da0  mov     esi, eax
0x180018da2  mov     r8d, eax; dwBytes
0x180018da5  mov     edx, 8; dwFlags
0x180018daa  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180018db1  call    cs:__imp_HeapAlloc
0x180018db7  mov     rdi, rax
0x180018dba  test    rax, rax
0x180018dbd  jz      loc_180018F75
0x180018dc3  mov     r8, r14; pSourceSid
0x180018dc6  mov     rdx, rax; pDestinationSid
0x180018dc9  mov     ecx, esi; nDestinationSidLength
0x180018dcb  call    cs:__imp_CopySid
0x180018dd1  test    eax, eax
0x180018dd3  jz      short loc_180018DFD
0x180018dd5  mov     edx, 1; unsigned __int64
0x180018dda  mov     rcx, rbx; void *
0x180018ddd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018de2  mov     rax, rdi
0x180018de5  lea     r11, [rsp+0A0h+var_10]
0x180018ded  mov     rbx, [r11+20h]
0x180018df1  mov     rsi, [r11+38h]
0x180018df5  mov     rsp, r11
0x180018df8  pop     r14
0x180018dfa  pop     rdi
0x180018dfb  pop     rbp
0x180018dfc  retn
0x180018dfd  mov     r8, rdi; lpMem
0x180018e00  xor     edx, edx; dwFlags
0x180018e02  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180018e09  call    cs:__imp_HeapFree
0x180018e0f  test    eax, eax
0x180018e11  jz      loc_180018FDE
0x180018e17  xorps   xmm0, xmm0
0x180018e1a  movups  [rbp+57h+var_68], xmm0
0x180018e1e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018e25  mov     [rbp+57h+pExceptionObject], rax
0x180018e29  mov     [rbp+57h+var_58], 8007000Eh
0x180018e30  mov     [rbp+57h+var_54], 38Bh
0x180018e37  mov     [rbp+57h+var_50], 1
0x180018e3e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018e45  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018e49  call    _CxxThrowException_0
0x180018e4f  call    cs:__imp_GetLastError
0x180018e55  cmp     eax, 7Ah ; 'z'
0x180018e58  jz      loc_180018D46
0x180018e5e  call    cs:__imp_GetLastError
0x180018e64  test    eax, eax
0x180018e66  jg      short loc_180018E72
0x180018e68  call    cs:__imp_GetLastError
0x180018e6e  mov     ecx, eax
0x180018e70  jmp     short loc_180018E81
0x180018e72  call    cs:__imp_GetLastError
0x180018e78  movzx   ecx, ax
0x180018e7b  or      ecx, 80070000h
0x180018e81  xorps   xmm0, xmm0
0x180018e84  movups  [rbp+57h+var_68], xmm0
0x180018e88  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018e8f  mov     [rbp+57h+pExceptionObject], rax
0x180018e93  mov     [rbp+57h+var_58], ecx
0x180018e96  mov     [rbp+57h+var_54], 414h
0x180018e9d  mov     [rbp+57h+var_50], 1
0x180018ea4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018eab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018eaf  call    _CxxThrowException_0
0x180018eb5  lea     rax, WPP_GLOBAL_Control
0x180018ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ec3  cmp     rcx, rax
0x180018ec6  jz      short loc_180018EE6
0x180018ec8  test    byte ptr [rcx+1Ch], 4
0x180018ecc  jz      short loc_180018EE6
0x180018ece  mov     r9d, esi
0x180018ed1  mov     edx, 0Ah
0x180018ed6  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180018edd  mov     rcx, [rcx+10h]
0x180018ee1  call    WPP_SF_d
0x180018ee6  xorps   xmm0, xmm0
0x180018ee9  movups  [rbp+57h+var_68], xmm0
0x180018eed  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018ef4  mov     [rbp+57h+pExceptionObject], rax
0x180018ef8  mov     [rbp+57h+var_58], 8007000Eh
0x180018eff  mov     [rbp+57h+var_54], 0
0x180018f06  mov     [rbp+57h+var_50], 1
0x180018f0d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018f14  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018f18  call    _CxxThrowException_0
0x180018f1e  call    cs:__imp_GetLastError
0x180018f24  test    eax, eax
0x180018f26  jg      short loc_180018F32
0x180018f28  call    cs:__imp_GetLastError
0x180018f2e  mov     ecx, eax
0x180018f30  jmp     short loc_180018F41
0x180018f32  call    cs:__imp_GetLastError
0x180018f38  movzx   ecx, ax
0x180018f3b  or      ecx, 80070000h
0x180018f41  xorps   xmm0, xmm0
0x180018f44  movups  [rbp+57h+var_68], xmm0
0x180018f48  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018f4f  mov     [rbp+57h+pExceptionObject], rax
0x180018f53  mov     [rbp+57h+var_58], ecx
0x180018f56  mov     [rbp+57h+var_54], 423h
0x180018f5d  mov     [rbp+57h+var_50], 1
0x180018f64  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018f6b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018f6f  call    _CxxThrowException_0
0x180018f75  lea     rax, WPP_GLOBAL_Control
0x180018f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f83  cmp     rcx, rax
0x180018f86  jz      short loc_180018FA6
0x180018f88  test    byte ptr [rcx+1Ch], 4
0x180018f8c  jz      short loc_180018FA6
0x180018f8e  mov     edx, 0Ah
0x180018f93  mov     r9d, esi
0x180018f96  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180018f9d  mov     rcx, [rcx+10h]
0x180018fa1  call    WPP_SF_d
0x180018fa6  xorps   xmm0, xmm0
0x180018fa9  movups  [rbp+57h+var_68], xmm0
0x180018fad  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018fb4  mov     [rbp+57h+pExceptionObject], rax
0x180018fb8  mov     [rbp+57h+var_58], 8007000Eh
0x180018fbf  mov     [rbp+57h+var_54], 0
0x180018fc6  mov     [rbp+57h+var_50], 1
0x180018fcd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018fd4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018fd8  call    _CxxThrowException_0
0x180018fde  lea     rax, WPP_GLOBAL_Control
0x180018fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fec  cmp     rcx, rax
0x180018fef  jz      loc_180018E17
0x180018ff5  test    byte ptr [rcx+1Ch], 4
0x180018ff9  jz      loc_180018E17
0x180018fff  call    cs:__imp_GetLastError
0x180019005  mov     edx, 0Bh
0x18001900a  mov     dword ptr [rsp+0A0h+ReturnLength], eax
0x18001900e  mov     r9, rdi
0x180019011  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180019018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001901f  mov     rcx, [rcx+10h]
0x180019023  call    WPP_SF_qD
0x180019028  jmp     loc_180018E17
```
