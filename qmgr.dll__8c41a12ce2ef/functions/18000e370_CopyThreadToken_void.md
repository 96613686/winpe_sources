# CopyThreadToken(void)

- ea: `0x18000e370`
- end: `0x18000e5b5`
- name: `?CopyThreadToken@@YA?AVTokenHandle@@XZ`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b40`
- `0x18000c920`
- `0x18000db20`
- `0x18000dcb0`
- `0x18000e8f0`
- `0x18000f1c0`
- `0x18000f5f0`
- `0x1800118f0`
- `0x1800131f0`
- `0x180013ddc`
- `0x180019d90`
- `0x18003cac0`
- `0x18003f7d0`
- `0x180040240`
- `0x180050560`
- `0x1800548e4`
- `0x180054ea0`
- `0x1800a05d8`
- `0x1800de51c`

## callees

- `0x18000e370`
- `0x18009e9c8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e3d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e429`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e3d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e38a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e38a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e3a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e535`

## pseudocode

```c
_QWORD *__fastcall CopyThreadToken(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  _DWORD *v4; // rax
  _DWORD *v6; // rax
  signed int LastError; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-68h] BYREF
  __int128 v9; // [rsp+38h] [rbp-60h]
  int v10; // [rsp+48h] [rbp-50h]
  int v11; // [rsp+4Ch] [rbp-4Ch]
  int v12; // [rsp+50h] [rbp-48h]
  void *TokenHandle; // [rsp+A8h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    v3 = TokenHandle;
    v4 = HeapAlloc(hBitsHeap, 8u, 0x10u);
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v10 = -2147024882;
      v11 = 0;
      pExceptionObject = &ComError::`vftable';
      v12 = 1;
      v9 = 0;
      throw (ComError *)&pExceptionObject;
    }
    v4[2] = 1;
    *(_QWORD *)v4 = v3;
    *a1 = v4;
    return a1;
  }
  else
  {
    if ( GetLastError() != 1008 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids,
          (unsigned int)LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError;
      v11 = 1093;
      pExceptionObject = &ComError::`vftable';
      v12 = 1;
      v9 = 0;
      throw (ComError *)&pExceptionObject;
    }
    v6 = HeapAlloc(hBitsHeap, 8u, 0x10u);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v10 = -2147024882;
      v11 = 0;
      pExceptionObject = &ComError::`vftable';
      v12 = 1;
      v9 = 0;
      throw (ComError *)&pExceptionObject;
    }
    v6[2] = 1;
    *a1 = v6;
    *(_QWORD *)v6 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x18000e370  mov     [rsp+arg_10], rbx
0x18000e375  push    rsi
0x18000e376  sub     rsp, 90h
0x18000e37d  xor     esi, esi
0x18000e37f  mov     rbx, rcx
0x18000e382  mov     [rsp+98h+TokenHandle], rsi
0x18000e38a  call    cs:__imp_GetCurrentThread
0x18000e390  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18000e398  mov     edx, 2000000h; DesiredAccess
0x18000e39d  mov     rcx, rax; ThreadHandle
0x18000e3a0  mov     r8d, 1; OpenAsSelf
0x18000e3a6  call    cs:__imp_OpenThreadToken
0x18000e3ac  test    eax, eax
0x18000e3ae  jz      short loc_18000E406
0x18000e3b0  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000e3b7  mov     edx, 8; dwFlags
0x18000e3bc  mov     [rsp+98h+arg_0], rdi
0x18000e3c4  mov     r8d, 10h; dwBytes
0x18000e3ca  mov     rdi, [rsp+98h+TokenHandle]
0x18000e3d2  call    cs:__imp_HeapAlloc
0x18000e3d8  test    rax, rax
0x18000e3db  jz      short loc_18000E459
0x18000e3dd  mov     dword ptr [rax+8], 1
0x18000e3e4  mov     [rax], rdi
0x18000e3e7  mov     rdi, [rsp+98h+arg_0]
0x18000e3ef  mov     [rbx], rax
0x18000e3f2  mov     rax, rbx
0x18000e3f5  mov     rbx, [rsp+98h+arg_10]
0x18000e3fd  add     rsp, 90h
0x18000e404  pop     rsi
0x18000e405  retn
0x18000e406  call    cs:__imp_GetLastError
0x18000e40c  cmp     eax, 3F0h
0x18000e411  jnz     loc_18000E535
0x18000e417  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000e41e  mov     edx, 8; dwFlags
0x18000e423  mov     r8d, 10h; dwBytes
0x18000e429  call    cs:__imp_HeapAlloc
0x18000e42f  test    rax, rax
0x18000e432  jz      loc_18000E4C7
0x18000e438  mov     dword ptr [rax+8], 1
0x18000e43f  mov     [rbx], rax
0x18000e442  mov     [rax], rsi
0x18000e445  mov     rax, rbx
0x18000e448  mov     rbx, [rsp+98h+arg_10]
0x18000e450  add     rsp, 90h
0x18000e457  pop     rsi
0x18000e458  retn
0x18000e459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e460  lea     rax, WPP_GLOBAL_Control
0x18000e467  cmp     rcx, rax
0x18000e46a  jz      short loc_18000E48D
0x18000e46c  test    byte ptr [rcx+1Ch], 4
0x18000e470  jz      short loc_18000E48D
0x18000e472  mov     rcx, [rcx+10h]
0x18000e476  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000e47d  mov     edx, 0Ah
0x18000e482  mov     r9d, 10h
0x18000e488  call    WPP_SF_d
0x18000e48d  xorps   xmm0, xmm0
0x18000e490  mov     [rsp+98h+var_50], 8007000Eh
0x18000e498  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000e49f  mov     [rsp+98h+var_4C], esi
0x18000e4a3  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000e4aa  mov     [rsp+98h+pExceptionObject], rax
0x18000e4af  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e4b4  mov     [rsp+98h+var_48], 1
0x18000e4bc  movups  [rsp+98h+var_60], xmm0
0x18000e4c1  call    _CxxThrowException_0
0x18000e4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4ce  lea     rax, WPP_GLOBAL_Control
0x18000e4d5  cmp     rcx, rax
0x18000e4d8  jz      short loc_18000E4FB
0x18000e4da  test    byte ptr [rcx+1Ch], 4
0x18000e4de  jz      short loc_18000E4FB
0x18000e4e0  mov     rcx, [rcx+10h]
0x18000e4e4  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000e4eb  mov     edx, 0Ah
0x18000e4f0  mov     r9d, 10h
0x18000e4f6  call    WPP_SF_d
0x18000e4fb  xorps   xmm0, xmm0
0x18000e4fe  mov     [rsp+98h+var_50], 8007000Eh
0x18000e506  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000e50d  mov     [rsp+98h+var_4C], esi
0x18000e511  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000e518  mov     [rsp+98h+pExceptionObject], rax
0x18000e51d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e522  mov     [rsp+98h+var_48], 1
0x18000e52a  movups  [rsp+98h+var_60], xmm0
0x18000e52f  call    _CxxThrowException_0
0x18000e535  call    cs:__imp_GetLastError
0x18000e53b  mov     ebx, eax
0x18000e53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e544  lea     rax, WPP_GLOBAL_Control
0x18000e54b  cmp     rcx, rax
0x18000e54e  jz      short loc_18000E56E
0x18000e550  test    byte ptr [rcx+1Ch], 4
0x18000e554  jz      short loc_18000E56E
0x18000e556  mov     rcx, [rcx+10h]
0x18000e55a  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x18000e561  mov     edx, 26h ; '&'
0x18000e566  mov     r9d, ebx
0x18000e569  call    WPP_SF_d
0x18000e56e  test    ebx, ebx
0x18000e570  jle     short loc_18000E57B
0x18000e572  movzx   ebx, bx
0x18000e575  or      ebx, 80070000h
0x18000e57b  xorps   xmm0, xmm0
0x18000e57e  mov     [rsp+98h+var_50], ebx
0x18000e582  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000e589  mov     [rsp+98h+var_4C], 445h
0x18000e591  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000e598  mov     [rsp+98h+pExceptionObject], rax
0x18000e59d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000e5a2  mov     [rsp+98h+var_48], 1
0x18000e5aa  movups  [rsp+98h+var_60], xmm0
0x18000e5af  call    _CxxThrowException_0
```
