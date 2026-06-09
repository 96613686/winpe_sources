# QueryUserContextToken(void *)

- ea: `0x180019d90`
- end: `0x18001a11e`
- name: `?QueryUserContextToken@@YA_KPEAX@Z`
- size: `910`
- prototype: `unsigned __int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180016ee0`
- `0x180019040`
- `0x180076344`
- `0x180082bcc`
- `0x18009d8a4`

## callees

- `0x18000e370`
- `0x180019d90`
- `0x180081600`
- `0x180090524`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800a44dc`
- `0x1800ab7fc`
- `0x1800baab8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019dcf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019dcf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180019f9c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a014`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180019f9c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019e89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ed1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a036`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019eed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180019eed`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180019f55`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180019f55`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall QueryUserContextToken(void *a1)
{
  unsigned __int64 v2; // rdx
  unsigned __int8 v3; // cl
  volatile signed __int32 *v4; // rax
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 **v6; // r14
  void *v7; // rcx
  unsigned int LastError; // ecx
  int v9; // esi
  __int64 v10; // rsi
  __int64 v12; // rcx
  CTelemetry *v13; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v15; // [rsp+28h] [rbp-58h]
  int v16; // [rsp+38h] [rbp-48h]
  int v17; // [rsp+3Ch] [rbp-44h]
  int v18; // [rsp+40h] [rbp-40h]
  void *v19; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v20; // [rsp+C0h] [rbp+40h] BYREF
  volatile signed __int32 *v21; // [rsp+C8h] [rbp+48h]

  v20 = 0;
  if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    if ( CTelemetry::IsEnabled(v3, v2) )
    {
      wil::details::static_lazy<CTelemetry>::get(v12, _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_);
      CTelemetry::UMgrApiNotAvailable_(v13, L"UMgrQueryUserContext");
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
    return 0;
  }
  v4 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = -2147024882;
    v17 = 0;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v21 = v4;
  *((_DWORD *)v4 + 2) = 1;
  *(_QWORD *)v4 = 0;
  v6 = (volatile signed __int32 **)CopyThreadToken(&v19);
  if ( *(_QWORD *)v5 != *(_QWORD *)*v6 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v5);
        *(_QWORD *)v5 = 0;
      }
      operator delete((void *)v5, 0x10u);
    }
    v5 = *v6;
    v21 = v5;
    _InterlockedIncrement(v5 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 2, 0xFFFFFFFF) == 1 )
  {
    v7 = v19;
    if ( (unsigned __int64)(*(_QWORD *)v19 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v19);
      *(_QWORD *)v19 = 0;
      v7 = v19;
    }
    operator delete(v7, 0x10u);
  }
  if ( !RevertToSelf() )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = LastError;
    v17 = 1348;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v9 = UMgrQueryUserContext(a1, &v20);
  if ( v9 < 0 )
  {
    if ( v9 != -2147023584 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids,
          (unsigned int)v9);
      v15 = 0;
      pExceptionObject = &ComError::`vftable';
      v16 = v9;
      v17 = 1366;
      v18 = 1;
      throw (ComError *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
    SetThreadToken(0, *(HANDLE *)v5);
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v5);
        *(_QWORD *)v5 = 0;
      }
      operator delete((void *)v5, 0x10u);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v20);
  v10 = v20;
  SetThreadToken(0, *(HANDLE *)v5);
  if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v5 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v5);
      *(_QWORD *)v5 = 0;
    }
    operator delete((void *)v5, 0x10u);
  }
  return v10;
}

```

## disassembly

```asm
0x180019d90  mov     [rsp-28h+arg_0], rbx
0x180019d95  push    rbp
0x180019d96  push    rsi
0x180019d97  push    rdi
0x180019d98  push    r14
0x180019d9a  push    r15
0x180019d9c  mov     rbp, rsp
0x180019d9f  sub     rsp, 80h
0x180019da6  mov     rsi, rcx
0x180019da9  xor     r15d, r15d
0x180019dac  mov     [rbp+arg_10], r15
0x180019db0  call    IsUMgrEnumerateSessionUsersPresent
0x180019db5  test    al, al
0x180019db7  jz      loc_18001A0B6
0x180019dbd  mov     edx, 8; dwFlags
0x180019dc2  mov     r8d, 10h; dwBytes
0x180019dc8  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180019dcf  call    cs:__imp_HeapAlloc
0x180019dd5  mov     rbx, rax
0x180019dd8  test    rax, rax
0x180019ddb  jnz     short loc_180019E46
0x180019ddd  lea     rax, WPP_GLOBAL_Control
0x180019de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180019deb  cmp     rcx, rax
0x180019dee  jz      short loc_180019E11
0x180019df0  test    byte ptr [rcx+1Ch], 4
0x180019df4  jz      short loc_180019E11
0x180019df6  mov     edx, 0Ah
0x180019dfb  mov     r9d, 10h
0x180019e01  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180019e08  mov     rcx, [rcx+10h]
0x180019e0c  call    WPP_SF_d
0x180019e11  xorps   xmm0, xmm0
0x180019e14  movups  [rbp+var_58], xmm0
0x180019e18  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180019e1f  mov     [rbp+pExceptionObject], rax
0x180019e23  mov     [rbp+var_48], 8007000Eh
0x180019e2a  mov     [rbp+var_44], r15d
0x180019e2e  mov     [rbp+var_40], 1
0x180019e35  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180019e3c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019e40  call    _CxxThrowException_0
0x180019e46  mov     [rbp+arg_18], rbx
0x180019e4a  mov     dword ptr [rax+8], 1
0x180019e51  mov     [rax], r15
0x180019e54  lea     rcx, [rbp+arg_8]
0x180019e58  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x180019e5d  mov     r14, rax
0x180019e60  mov     rcx, [rax]
0x180019e63  mov     rdx, [rcx]
0x180019e66  mov     edi, 0FFFFFFFFh
0x180019e6b  cmp     [rbx], rdx
0x180019e6e  jz      short loc_180019EAA
0x180019e70  mov     ecx, edi
0x180019e72  lock xadd [rbx+8], ecx
0x180019e77  cmp     ecx, 1
0x180019e7a  jnz     short loc_180019E9F
0x180019e7c  mov     rcx, [rbx]; hObject
0x180019e7f  lea     rdx, [rcx-1]
0x180019e83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019e87  ja      short loc_180019E92
0x180019e89  call    cs:__imp_CloseHandle
0x180019e8f  mov     [rbx], r15
0x180019e92  mov     edx, 10h; unsigned __int64
0x180019e97  mov     rcx, rbx; void *
0x180019e9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019e9f  mov     rbx, [r14]
0x180019ea2  mov     [rbp+arg_18], rbx
0x180019ea6  lock inc dword ptr [rbx+8]
0x180019eaa  mov     r14, rbx
0x180019ead  mov     rcx, [rbp+arg_8]
0x180019eb1  mov     eax, edi
0x180019eb3  lock xadd [rcx+8], eax
0x180019eb8  cmp     eax, 1
0x180019ebb  jnz     short loc_180019EED
0x180019ebd  mov     rcx, [rbp+arg_8]
0x180019ec1  mov     rdx, [rcx]
0x180019ec4  lea     rax, [rdx-1]
0x180019ec8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019ecc  ja      short loc_180019EE2
0x180019ece  mov     rcx, rdx; hObject
0x180019ed1  call    cs:__imp_CloseHandle
0x180019ed7  mov     rax, [rbp+arg_8]
0x180019edb  mov     [rax], r15
0x180019ede  mov     rcx, [rbp+arg_8]; void *
0x180019ee2  mov     edx, 10h; unsigned __int64
0x180019ee7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019eec  nop
0x180019eed  call    cs:__imp_RevertToSelf
0x180019ef3  test    eax, eax
0x180019ef5  jnz     short loc_180019F4E
0x180019ef7  call    cs:__imp_GetLastError
0x180019efd  test    eax, eax
0x180019eff  jg      short loc_180019F0B
0x180019f01  call    cs:__imp_GetLastError
0x180019f07  mov     ecx, eax
0x180019f09  jmp     short loc_180019F1A
0x180019f0b  call    cs:__imp_GetLastError
0x180019f11  movzx   ecx, ax
0x180019f14  or      ecx, 80070000h
0x180019f1a  xorps   xmm0, xmm0
0x180019f1d  movups  [rbp+var_58], xmm0
0x180019f21  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180019f28  mov     [rbp+pExceptionObject], rax
0x180019f2c  mov     [rbp+var_48], ecx
0x180019f2f  mov     [rbp+var_44], 544h
0x180019f36  mov     [rbp+var_40], 1
0x180019f3d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180019f44  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019f48  call    _CxxThrowException_0
0x180019f4e  lea     rdx, [rbp+arg_10]
0x180019f52  mov     rcx, rsi
0x180019f55  call    cs:__imp_UMgrQueryUserContext
0x180019f5b  mov     esi, eax
0x180019f5d  test    eax, eax
0x180019f5f  js      short loc_180019FD8
0x180019f61  lea     rax, WPP_GLOBAL_Control
0x180019f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f6f  cmp     rcx, rax
0x180019f72  jz      short loc_180019F93
0x180019f74  test    byte ptr [rcx+1Ch], 1
0x180019f78  jz      short loc_180019F93
0x180019f7a  mov     edx, 2Dh ; '-'
0x180019f7f  mov     r9, [rbp+arg_10]
0x180019f83  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180019f8a  mov     rcx, [rcx+10h]
0x180019f8e  call    WPP_SF_q
0x180019f93  mov     rsi, [rbp+arg_10]
0x180019f97  mov     rdx, [rbx]; Token
0x180019f9a  xor     ecx, ecx; Thread
0x180019f9c  call    cs:__imp_SetThreadToken
0x180019fa2  lock xadd [r14+8], edi
0x180019fa8  cmp     edi, 1
0x180019fab  jnz     short loc_180019FD0
0x180019fad  mov     rcx, [r14]; hObject
0x180019fb0  lea     rdx, [rcx-1]
0x180019fb4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019fb8  ja      short loc_180019FC3
0x180019fba  call    cs:__imp_CloseHandle
0x180019fc0  mov     [r14], r15
0x180019fc3  mov     edx, 10h; unsigned __int64
0x180019fc8  mov     rcx, r14; void *
0x180019fcb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019fd0  mov     rax, rsi
0x180019fd3  jmp     loc_18001A107
0x180019fd8  cmp     esi, 80070520h
0x180019fde  jnz     short loc_18001A051
0x180019fe0  lea     rax, WPP_GLOBAL_Control
0x180019fe7  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fee  cmp     rcx, rax
0x180019ff1  jz      short loc_18001A00F
0x180019ff3  test    byte ptr [rcx+1Ch], 1
0x180019ff7  jz      short loc_18001A00F
0x180019ff9  mov     edx, 2Eh ; '.'
0x180019ffe  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18001a005  mov     rcx, [rcx+10h]
0x18001a009  call    WPP_SF_
0x18001a00e  nop
0x18001a00f  mov     rdx, [rbx]; Token
0x18001a012  xor     ecx, ecx; Thread
0x18001a014  call    cs:__imp_SetThreadToken
0x18001a01a  lock xadd [r14+8], edi
0x18001a020  cmp     edi, 1
0x18001a023  jnz     loc_18001A105
0x18001a029  mov     rcx, [r14]; hObject
0x18001a02c  lea     rax, [rcx-1]
0x18001a030  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a034  ja      short loc_18001A03F
0x18001a036  call    cs:__imp_CloseHandle
0x18001a03c  mov     [r14], r15
0x18001a03f  mov     edx, 10h; unsigned __int64
0x18001a044  mov     rcx, r14; void *
0x18001a047  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a04c  jmp     loc_18001A105
0x18001a051  lea     rax, WPP_GLOBAL_Control
0x18001a058  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a05f  cmp     rcx, rax
0x18001a062  jz      short loc_18001A082
0x18001a064  test    byte ptr [rcx+1Ch], 4
0x18001a068  jz      short loc_18001A082
0x18001a06a  mov     edx, 2Fh ; '/'
0x18001a06f  mov     r9d, esi
0x18001a072  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18001a079  mov     rcx, [rcx+10h]
0x18001a07d  call    WPP_SF_d
0x18001a082  xorps   xmm0, xmm0
0x18001a085  movups  [rbp+var_58], xmm0
0x18001a089  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001a090  mov     [rbp+pExceptionObject], rax
0x18001a094  mov     [rbp+var_48], esi
0x18001a097  mov     [rbp+var_44], 556h
0x18001a09e  mov     [rbp+var_40], 1
0x18001a0a5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001a0ac  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a0b0  call    _CxxThrowException_0
0x18001a0b6  call    ?IsEnabled@CTelemetry@@SA_NE_K@Z; CTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001a0bb  test    al, al
0x18001a0bd  jz      short loc_18001A0D7
0x18001a0bf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_@@CA@XZ; _lambda_522be0d8c7a8171f2eb2c3a9bc6a1151_::_lambda_invoker_cdecl_(void)
0x18001a0c6  call    ?get@?$static_lazy@VCTelemetry@@@details@wil@@QEAAPEAVCTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CTelemetry>::get(void (*)(void))
0x18001a0cb  lea     rdx, aUmgrqueryuserc_0; "UMgrQueryUserContext"
0x18001a0d2  call    ?UMgrApiNotAvailable_@CTelemetry@@QEAAXPEBG@Z; CTelemetry::UMgrApiNotAvailable_(ushort const *)
0x18001a0d7  lea     rax, WPP_GLOBAL_Control
0x18001a0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0e5  cmp     rcx, rax
0x18001a0e8  jz      short loc_18001A105
0x18001a0ea  test    byte ptr [rcx+1Ch], 2
0x18001a0ee  jz      short loc_18001A105
0x18001a0f0  mov     edx, 30h ; '0'
0x18001a0f5  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18001a0fc  mov     rcx, [rcx+10h]
0x18001a100  call    WPP_SF_
0x18001a105  xor     eax, eax
0x18001a107  mov     rbx, [rsp+80h+arg_0]
0x18001a10f  add     rsp, 80h
0x18001a116  pop     r15
0x18001a118  pop     r14
0x18001a11a  pop     rdi
0x18001a11b  pop     rsi
0x18001a11c  pop     rbp
0x18001a11d  retn
```
