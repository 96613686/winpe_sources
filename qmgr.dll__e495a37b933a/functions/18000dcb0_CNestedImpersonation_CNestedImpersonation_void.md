# CNestedImpersonation::CNestedImpersonation(void)

- ea: `0x18000dcb0`
- end: `0x18000e365`
- name: `??0CNestedImpersonation@@QEAA@XZ`
- size: `1717`
- prototype: `CNestedImpersonation *__fastcall(CNestedImpersonation *__hidden this)`
- caller_count: `31`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009ac0`
- `0x180009e70`
- `0x18000a680`
- `0x18000d1f0`
- `0x180016ee0`
- `0x180027d18`
- `0x1800302e8`
- `0x180030480`
- `0x180059860`
- `0x18005a720`
- `0x180068880`
- `0x180076344`
- `0x18007d8d4`
- `0x18008a9a0`
- `0x18008abdc`
- `0x18008b030`
- `0x18008b230`
- `0x18008b6b0`
- `0x18008bd40`
- `0x18008c040`
- `0x18009651c`
- `0x180097c58`
- `0x1800a1930`
- `0x1800cbe68`
- `0x1800ce1a0`
- `0x1800d4390`
- `0x1800d46d0`
- `0x1800d5388`
- `0x1800d5794`
- `0x1800d691c`
- `0x1800d77ac`

## callees

- `0x18000dcb0`
- `0x18000e370`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dcda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dcda`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd96`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000de40`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000de40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e30a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e057`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e0f8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ddc5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000ddc5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000de2d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000de2d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000defe`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000defe`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
CNestedImpersonation *__fastcall CNestedImpersonation::CNestedImpersonation(CNestedImpersonation *this)
{
  _DWORD *v2; // rax
  volatile signed __int32 **v3; // rsi
  volatile signed __int32 *v4; // rax
  _DWORD *v5; // rax
  _DWORD *v6; // rax
  HRESULT v7; // eax
  volatile signed __int32 **v8; // rsi
  __int64 v9; // r8
  volatile signed __int32 *v10; // rax
  void *v12; // rcx
  volatile signed __int32 **v13; // rsi
  __int64 v14; // r8
  volatile signed __int32 *v15; // rax
  volatile signed __int32 **v16; // rsi
  __int64 v17; // r8
  volatile signed __int32 *v18; // rax
  void *v19; // rcx
  void *v20; // rcx
  char *v21; // rcx
  char *v22; // rcx
  void *v23; // rcx
  char *v24; // rcx
  char *v25; // rcx
  unsigned int LastError; // eax
  unsigned int v27; // eax
  void *v28[2]; // [rsp+20h] [rbp-2D8h] BYREF
  void **v29; // [rsp+30h] [rbp-2C8h] BYREF
  __int128 v30; // [rsp+38h] [rbp-2C0h]
  int v31; // [rsp+48h] [rbp-2B0h]
  int v32; // [rsp+4Ch] [rbp-2ACh]
  int v33; // [rsp+50h] [rbp-2A8h]
  void **v34; // [rsp+90h] [rbp-268h] BYREF
  __int128 v35; // [rsp+98h] [rbp-260h]
  int v36; // [rsp+A8h] [rbp-250h]
  int v37; // [rsp+ACh] [rbp-24Ch]
  int v38; // [rsp+B0h] [rbp-248h]
  void **v39; // [rsp+F0h] [rbp-208h] BYREF
  __int128 v40; // [rsp+F8h] [rbp-200h]
  int v41; // [rsp+108h] [rbp-1F0h]
  int v42; // [rsp+10Ch] [rbp-1ECh]
  int v43; // [rsp+110h] [rbp-1E8h]
  void **pExceptionObject; // [rsp+150h] [rbp-1A8h] BYREF
  __int128 v45; // [rsp+158h] [rbp-1A0h]
  HRESULT v46; // [rsp+168h] [rbp-190h]
  int v47; // [rsp+16Ch] [rbp-18Ch]
  int v48; // [rsp+170h] [rbp-188h]
  void **v49; // [rsp+1B0h] [rbp-148h] BYREF
  __int128 v50; // [rsp+1B8h] [rbp-140h]
  unsigned int v51; // [rsp+1C8h] [rbp-130h]
  int v52; // [rsp+1CCh] [rbp-12Ch]
  int v53; // [rsp+1D0h] [rbp-128h]
  void **v54; // [rsp+210h] [rbp-E8h] BYREF
  __int128 v55; // [rsp+218h] [rbp-E0h]
  unsigned int v56; // [rsp+228h] [rbp-D0h]
  int v57; // [rsp+22Ch] [rbp-CCh]
  int v58; // [rsp+230h] [rbp-C8h]

  v28[1] = this;
  v2 = HeapAlloc(hBitsHeap, 8u, 0x10u);
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v30 = 0;
    v29 = &ComError::`vftable';
    v31 = -2147024882;
    v32 = 0;
    v33 = 1;
    throw (ComError *)&v29;
  }
  *(_QWORD *)this = v2;
  v2[2] = 1;
  **(_QWORD **)this = 0;
  v3 = (volatile signed __int32 **)CopyThreadToken(v28);
  if ( **(_QWORD **)this != *(_QWORD *)*v3 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)this + 8LL), 0xFFFFFFFF) == 1 )
    {
      v21 = **(char ***)this;
      if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v21);
        **(_QWORD **)this = 0;
      }
      operator delete(*(void **)this, 0x10u);
      *(_QWORD *)this = 0;
    }
    v4 = *v3;
    *(_QWORD *)this = *v3;
    _InterlockedIncrement(v4 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[0] + 2, 0xFFFFFFFF) == 1 )
  {
    v12 = v28[0];
    if ( (unsigned __int64)(*(_QWORD *)v28[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v28[0]);
      *(_QWORD *)v28[0] = 0;
      v12 = v28[0];
    }
    operator delete(v12, 0x10u);
    v28[0] = 0;
  }
  *((_BYTE *)this + 8) = 0;
  v5 = HeapAlloc(hBitsHeap, 8u, 0x10u);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v35 = 0;
    v34 = &ComError::`vftable';
    v36 = -2147024882;
    v37 = 0;
    v38 = 1;
    throw (ComError *)&v34;
  }
  *((_QWORD *)this + 2) = v5;
  v5[2] = 1;
  **((_QWORD **)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v6 = HeapAlloc(hBitsHeap, 8u, 4u);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v40 = 0;
    v39 = &ComError::`vftable';
    v41 = -2147024882;
    v42 = 0;
    v43 = 1;
    throw (ComError *)&v39;
  }
  *v6 = 1;
  *((_QWORD *)this + 4) = v6;
  *((_QWORD *)this + 5) = 0;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 6) = &GenericStringHandle<unsigned short>::s_EmptyString;
  v7 = CoImpersonateClient();
  if ( v7 != -2147417833 )
  {
    if ( v7 )
    {
      v45 = 0;
      pExceptionObject = &ComError::`vftable';
      v46 = v7;
      v47 = 353;
      v48 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *((_BYTE *)this + 8) = 1;
    v8 = (volatile signed __int32 **)CopyThreadToken(v28);
    v9 = *((_QWORD *)this + 2);
    if ( *(_QWORD *)v9 != *(_QWORD *)*v8 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
      {
        v22 = (char *)**((_QWORD **)this + 2);
        if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(v22);
          **((_QWORD **)this + 2) = 0;
        }
        operator delete(*((void **)this + 2), 0x10u);
        *((_QWORD *)this + 2) = 0;
      }
      v10 = *v8;
      *((_QWORD *)this + 2) = *v8;
      _InterlockedIncrement(v10 + 2);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[0] + 2, 0xFFFFFFFF) == 1 )
    {
      v20 = v28[0];
      if ( (unsigned __int64)(*(_QWORD *)v28[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v28[0]);
        *(_QWORD *)v28[0] = 0;
        v20 = v28[0];
      }
      operator delete(v20, 0x10u);
    }
    CoRevertToSelf();
    *((_BYTE *)this + 8) = 0;
    if ( !SetThreadToken(0, **((HANDLE **)this + 2)) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v50 = 0;
      v49 = &ComError::`vftable';
      v51 = LastError;
      v52 = 320;
      v53 = 1;
      throw (ComError *)&v49;
    }
LABEL_15:
    *((_BYTE *)this + 8) = 1;
    return this;
  }
  v13 = (volatile signed __int32 **)CopyThreadToken(v28);
  v14 = *((_QWORD *)this + 2);
  if ( *(_QWORD *)v14 != *(_QWORD *)*v13 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 0xFFFFFFFF) == 1 )
    {
      v24 = (char *)**((_QWORD **)this + 2);
      if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v24);
        **((_QWORD **)this + 2) = 0;
      }
      operator delete(*((void **)this + 2), 0x10u);
      *((_QWORD *)this + 2) = 0;
    }
    v15 = *v13;
    *((_QWORD *)this + 2) = *v13;
    _InterlockedIncrement(v15 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[0] + 2, 0xFFFFFFFF) == 1 )
  {
    v23 = v28[0];
    if ( (unsigned __int64)(*(_QWORD *)v28[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v28[0]);
      *(_QWORD *)v28[0] = 0;
      v23 = v28[0];
    }
    operator delete(v23, 0x10u);
  }
  if ( **((_QWORD **)this + 2) )
    goto LABEL_15;
  if ( !ImpersonateSelf(SecurityImpersonation) )
  {
    if ( (int)GetLastError() > 0 )
      v27 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v27 = GetLastError();
    v55 = 0;
    v54 = &ComError::`vftable';
    v56 = v27;
    v57 = 343;
    v58 = 1;
    throw (ComError *)&v54;
  }
  *((_BYTE *)this + 8) = 1;
  v16 = (volatile signed __int32 **)CopyThreadToken(v28);
  v17 = *((_QWORD *)this + 2);
  if ( *(_QWORD *)v17 != *(_QWORD *)*v16 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
    {
      v25 = (char *)**((_QWORD **)this + 2);
      if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v25);
        **((_QWORD **)this + 2) = 0;
      }
      operator delete(*((void **)this + 2), 0x10u);
      *((_QWORD *)this + 2) = 0;
    }
    v18 = *v16;
    *((_QWORD *)this + 2) = *v16;
    _InterlockedIncrement(v18 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28[0] + 2, 0xFFFFFFFF) == 1 )
  {
    v19 = v28[0];
    if ( (unsigned __int64)(*(_QWORD *)v28[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v28[0]);
      *(_QWORD *)v28[0] = 0;
      v19 = v28[0];
    }
    operator delete(v19, 0x10u);
  }
  return this;
}

```

## disassembly

```asm
0x18000dcb0  push    rbx
0x18000dcb2  push    rsi
0x18000dcb3  push    rdi
0x18000dcb4  push    r14
0x18000dcb6  sub     rsp, 2D8h
0x18000dcbd  mov     rbx, rcx
0x18000dcc0  mov     [rsp+2F8h+var_2D0], rcx
0x18000dcc5  xor     r14d, r14d
0x18000dcc8  mov     edx, 8; dwFlags
0x18000dccd  mov     r8d, 10h; dwBytes
0x18000dcd3  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000dcda  call    cs:__imp_HeapAlloc
0x18000dce0  test    rax, rax
0x18000dce3  jz      loc_18000E11C
0x18000dce9  mov     [rbx], rax
0x18000dcec  mov     dword ptr [rax+8], 1
0x18000dcf3  mov     rax, [rbx]
0x18000dcf6  mov     [rax], r14
0x18000dcf9  lea     rcx, [rsp+2F8h+var_2D8]
0x18000dcfe  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000dd03  mov     rsi, rax
0x18000dd06  mov     r8, [rbx]
0x18000dd09  mov     rcx, [rax]
0x18000dd0c  mov     rdx, [rcx]
0x18000dd0f  mov     edi, 0FFFFFFFFh
0x18000dd14  cmp     [r8], rdx
0x18000dd17  jz      short loc_18000DD34
0x18000dd19  mov     ecx, edi
0x18000dd1b  lock xadd [r8+8], ecx
0x18000dd21  cmp     ecx, 1
0x18000dd24  jz      loc_18000E015
0x18000dd2a  mov     rax, [rsi]
0x18000dd2d  mov     [rbx], rax
0x18000dd30  lock inc dword ptr [rax+8]
0x18000dd34  mov     rcx, [rsp+2F8h+var_2D8]
0x18000dd39  mov     eax, edi
0x18000dd3b  lock xadd [rcx+8], eax
0x18000dd40  cmp     eax, 1
0x18000dd43  jz      loc_18000DE62
0x18000dd49  mov     byte ptr [rbx+8], 0
0x18000dd4d  mov     edx, 8; dwFlags
0x18000dd52  mov     r8d, 10h; dwBytes
0x18000dd58  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000dd5f  call    cs:__imp_HeapAlloc
0x18000dd65  test    rax, rax
0x18000dd68  jz      loc_18000E18B
0x18000dd6e  mov     [rbx+10h], rax
0x18000dd72  mov     dword ptr [rax+8], 1
0x18000dd79  mov     rax, [rbx+10h]
0x18000dd7d  mov     [rax], r14
0x18000dd80  mov     [rbx+18h], r14
0x18000dd84  mov     edx, 8; dwFlags
0x18000dd89  mov     r8d, 4; dwBytes
0x18000dd8f  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000dd96  call    cs:__imp_HeapAlloc
0x18000dd9c  test    rax, rax
0x18000dd9f  jz      loc_18000E20C
0x18000dda5  mov     dword ptr [rax], 1
0x18000ddab  mov     [rbx+20h], rax
0x18000ddaf  mov     [rbx+28h], r14
0x18000ddb3  lock inc cs:dword_180145058
0x18000ddba  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18000ddc1  mov     [rbx+30h], rax
0x18000ddc5  call    cs:__imp_CoImpersonateClient
0x18000ddcb  cmp     eax, 80010117h
0x18000ddd0  jz      loc_18000DE9E
0x18000ddd6  test    eax, eax
0x18000ddd8  jnz     loc_18000DFC9
0x18000ddde  mov     byte ptr [rbx+8], 1
0x18000dde2  lea     rcx, [rsp+2F8h+var_2D8]
0x18000dde7  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000ddec  mov     rsi, rax
0x18000ddef  mov     r8, [rbx+10h]
0x18000ddf3  mov     rcx, [rax]
0x18000ddf6  mov     rdx, [rcx]
0x18000ddf9  cmp     [r8], rdx
0x18000ddfc  jz      short loc_18000DE1A
0x18000ddfe  mov     ecx, edi
0x18000de00  lock xadd [r8+8], ecx
0x18000de06  cmp     ecx, 1
0x18000de09  jz      loc_18000E046
0x18000de0f  mov     rax, [rsi]
0x18000de12  mov     [rbx+10h], rax
0x18000de16  lock inc dword ptr [rax+8]
0x18000de1a  mov     rax, [rsp+2F8h+var_2D8]
0x18000de1f  lock xadd [rax+8], edi
0x18000de24  cmp     edi, 1
0x18000de27  jz      loc_18000DF92
0x18000de2d  call    cs:__imp_CoRevertToSelf
0x18000de33  mov     byte ptr [rbx+8], 0
0x18000de37  mov     rdx, [rbx+10h]
0x18000de3b  mov     rdx, [rdx]; Token
0x18000de3e  xor     ecx, ecx; Thread
0x18000de40  call    cs:__imp_SetThreadToken
0x18000de46  test    eax, eax
0x18000de48  jz      loc_18000E28D
0x18000de4e  mov     byte ptr [rbx+8], 1
0x18000de52  mov     rax, rbx
0x18000de55  add     rsp, 2D8h
0x18000de5c  pop     r14
0x18000de5e  pop     rdi
0x18000de5f  pop     rsi
0x18000de60  pop     rbx
0x18000de61  retn
0x18000de62  mov     rcx, [rsp+2F8h+var_2D8]
0x18000de67  mov     rdx, [rcx]
0x18000de6a  lea     rax, [rdx-1]
0x18000de6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000de72  ja      short loc_18000DE8A
0x18000de74  mov     rcx, rdx; hObject
0x18000de77  call    cs:__imp_CloseHandle
0x18000de7d  mov     rax, [rsp+2F8h+var_2D8]
0x18000de82  mov     [rax], r14
0x18000de85  mov     rcx, [rsp+2F8h+var_2D8]; void *
0x18000de8a  mov     edx, 10h; unsigned __int64
0x18000de8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000de94  mov     [rsp+2F8h+var_2D8], r14
0x18000de99  jmp     loc_18000DD49
0x18000de9e  lea     rcx, [rsp+2F8h+var_2D8]
0x18000dea3  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000dea8  mov     rsi, rax
0x18000deab  mov     r8, [rbx+10h]
0x18000deaf  mov     rcx, [rax]
0x18000deb2  mov     rdx, [rcx]
0x18000deb5  cmp     [r8], rdx
0x18000deb8  jz      short loc_18000DED6
0x18000deba  mov     ecx, edi
0x18000debc  lock xadd [r8+8], ecx
0x18000dec2  cmp     ecx, 1
0x18000dec5  jz      loc_18000E0B2
0x18000decb  mov     rax, [rsi]
0x18000dece  mov     [rbx+10h], rax
0x18000ded2  lock inc dword ptr [rax+8]
0x18000ded6  mov     rcx, [rsp+2F8h+var_2D8]
0x18000dedb  mov     eax, edi
0x18000dedd  lock xadd [rcx+8], eax
0x18000dee2  cmp     eax, 1
0x18000dee5  jz      loc_18000E07B
0x18000deeb  mov     rax, [rbx+10h]
0x18000deef  cmp     qword ptr [rax], 0
0x18000def3  jnz     loc_18000DE4E
0x18000def9  mov     ecx, 2; ImpersonationLevel
0x18000defe  call    cs:__imp_ImpersonateSelf
0x18000df04  test    eax, eax
0x18000df06  jz      loc_18000E2F8
0x18000df0c  mov     byte ptr [rbx+8], 1
0x18000df10  lea     rcx, [rsp+2F8h+var_2D8]
0x18000df15  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000df1a  mov     rsi, rax
0x18000df1d  mov     r8, [rbx+10h]
0x18000df21  mov     rcx, [rax]
0x18000df24  mov     rdx, [rcx]
0x18000df27  cmp     [r8], rdx
0x18000df2a  jz      short loc_18000DF48
0x18000df2c  mov     ecx, edi
0x18000df2e  lock xadd [r8+8], ecx
0x18000df34  cmp     ecx, 1
0x18000df37  jz      loc_18000E0E7
0x18000df3d  mov     rax, [rsi]
0x18000df40  mov     [rbx+10h], rax
0x18000df44  lock inc dword ptr [rax+8]
0x18000df48  mov     rax, [rsp+2F8h+var_2D8]
0x18000df4d  lock xadd [rax+8], edi
0x18000df52  cmp     edi, 1
0x18000df55  jnz     loc_18000DE52
0x18000df5b  mov     rcx, [rsp+2F8h+var_2D8]
0x18000df60  mov     rdx, [rcx]
0x18000df63  lea     rax, [rdx-1]
0x18000df67  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000df6b  ja      short loc_18000DF83
0x18000df6d  mov     rcx, rdx; hObject
0x18000df70  call    cs:__imp_CloseHandle
0x18000df76  mov     rax, [rsp+2F8h+var_2D8]
0x18000df7b  mov     [rax], r14
0x18000df7e  mov     rcx, [rsp+2F8h+var_2D8]; void *
0x18000df83  mov     edx, 10h; unsigned __int64
0x18000df88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df8d  jmp     loc_18000DE52
0x18000df92  mov     rcx, [rsp+2F8h+var_2D8]
0x18000df97  mov     rdx, [rcx]
0x18000df9a  lea     rax, [rdx-1]
0x18000df9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dfa2  ja      short loc_18000DFBA
0x18000dfa4  mov     rcx, rdx; hObject
0x18000dfa7  call    cs:__imp_CloseHandle
0x18000dfad  mov     rax, [rsp+2F8h+var_2D8]
0x18000dfb2  mov     [rax], r14
0x18000dfb5  mov     rcx, [rsp+2F8h+var_2D8]; void *
0x18000dfba  mov     edx, 10h; unsigned __int64
0x18000dfbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dfc4  jmp     loc_18000DE2D
0x18000dfc9  xorps   xmm0, xmm0
0x18000dfcc  movups  [rsp+2F8h+var_1A0], xmm0
0x18000dfd4  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000dfdb  mov     [rsp+2F8h+pExceptionObject], rcx
0x18000dfe3  mov     [rsp+2F8h+var_190], eax
0x18000dfea  mov     [rsp+2F8h+var_18C], 161h
0x18000dff5  mov     [rsp+2F8h+var_188], 1
0x18000e000  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000e007  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x18000e00f  call    _CxxThrowException_0
0x18000e015  mov     rcx, [rbx]
0x18000e018  mov     rcx, [rcx]; hObject
0x18000e01b  lea     rax, [rcx-1]
0x18000e01f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e023  ja      short loc_18000E031
0x18000e025  call    cs:__imp_CloseHandle
0x18000e02b  mov     rax, [rbx]
0x18000e02e  mov     [rax], r14
0x18000e031  mov     edx, 10h; unsigned __int64
0x18000e036  mov     rcx, [rbx]; void *
0x18000e039  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e03e  mov     [rbx], r14
0x18000e041  jmp     loc_18000DD2A
0x18000e046  mov     rax, [rbx+10h]
0x18000e04a  mov     rcx, [rax]; hObject
0x18000e04d  lea     rax, [rcx-1]
0x18000e051  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e055  ja      short loc_18000E064
0x18000e057  call    cs:__imp_CloseHandle
0x18000e05d  mov     rax, [rbx+10h]
0x18000e061  mov     [rax], r14
0x18000e064  mov     edx, 10h; unsigned __int64
0x18000e069  mov     rcx, [rbx+10h]; void *
0x18000e06d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e072  mov     [rbx+10h], r14
0x18000e076  jmp     loc_18000DE0F
0x18000e07b  mov     rcx, [rsp+2F8h+var_2D8]
0x18000e080  mov     rdx, [rcx]
0x18000e083  lea     rax, [rdx-1]
0x18000e087  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e08b  ja      short loc_18000E0A3
0x18000e08d  mov     rcx, rdx; hObject
0x18000e090  call    cs:__imp_CloseHandle
0x18000e096  mov     rax, [rsp+2F8h+var_2D8]
0x18000e09b  mov     [rax], r14
0x18000e09e  mov     rcx, [rsp+2F8h+var_2D8]; void *
0x18000e0a3  mov     edx, 10h; unsigned __int64
0x18000e0a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e0ad  jmp     loc_18000DEEB
0x18000e0b2  mov     rax, [rbx+10h]
0x18000e0b6  mov     rcx, [rax]; hObject
0x18000e0b9  lea     rax, [rcx-1]
0x18000e0bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e0c1  ja      short loc_18000E0D0
0x18000e0c3  call    cs:__imp_CloseHandle
0x18000e0c9  mov     rax, [rbx+10h]
0x18000e0cd  mov     [rax], r14
0x18000e0d0  mov     edx, 10h; unsigned __int64
0x18000e0d5  mov     rcx, [rbx+10h]; void *
0x18000e0d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e0de  mov     [rbx+10h], r14
0x18000e0e2  jmp     loc_18000DECB
0x18000e0e7  mov     rax, [rbx+10h]
0x18000e0eb  mov     rcx, [rax]; hObject
0x18000e0ee  lea     rax, [rcx-1]
0x18000e0f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e0f6  ja      short loc_18000E105
0x18000e0f8  call    cs:__imp_CloseHandle
0x18000e0fe  mov     rax, [rbx+10h]
0x18000e102  mov     [rax], r14
0x18000e105  mov     edx, 10h; unsigned __int64
0x18000e10a  mov     rcx, [rbx+10h]; void *
0x18000e10e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e113  mov     [rbx+10h], r14
0x18000e117  jmp     loc_18000DF3D
0x18000e11c  lea     rax, WPP_GLOBAL_Control
0x18000e123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e12a  cmp     rcx, rax
0x18000e12d  jz      short loc_18000E150
0x18000e12f  test    byte ptr [rcx+1Ch], 4
0x18000e133  jz      short loc_18000E150
0x18000e135  mov     edx, 0Ah
0x18000e13a  mov     r9d, 10h
0x18000e140  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000e147  mov     rcx, [rcx+10h]
0x18000e14b  call    WPP_SF_d
0x18000e150  xorps   xmm0, xmm0
0x18000e153  movups  [rsp+2F8h+var_2C0], xmm0
0x18000e158  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000e15f  mov     [rsp+2F8h+var_2C8], rcx
0x18000e164  mov     [rsp+2F8h+var_2B0], 8007000Eh
0x18000e16c  mov     [rsp+2F8h+var_2AC], r14d
0x18000e171  mov     [rsp+2F8h+var_2A8], 1
0x18000e179  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000e180  lea     rcx, [rsp+2F8h+var_2C8]; pExceptionObject
0x18000e185  call    _CxxThrowException_0
0x18000e18b  lea     rax, WPP_GLOBAL_Control
0x18000e192  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e199  cmp     rcx, rax
0x18000e19c  jz      short loc_18000E1BF
0x18000e19e  test    byte ptr [rcx+1Ch], 4
0x18000e1a2  jz      short loc_18000E1BF
0x18000e1a4  mov     edx, 0Ah
0x18000e1a9  mov     r9d, 10h
0x18000e1af  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000e1b6  mov     rcx, [rcx+10h]
0x18000e1ba  call    WPP_SF_d
0x18000e1bf  xorps   xmm0, xmm0
0x18000e1c2  movups  [rsp+2F8h+var_260], xmm0
  ... truncated ...
```
