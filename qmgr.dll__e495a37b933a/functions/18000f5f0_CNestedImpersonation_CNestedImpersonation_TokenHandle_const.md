# CNestedImpersonation::CNestedImpersonation(TokenHandle const &)

- ea: `0x18000f5f0`
- end: `0x18000f8a6`
- name: `??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z`
- size: `694`
- prototype: `CNestedImpersonation *__fastcall(CNestedImpersonation *__hidden this, const struct TokenHandle *)`
- caller_count: `30`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800084a0`
- `0x18000bca0`
- `0x18000c920`
- `0x18001a6fc`
- `0x18001e96c`
- `0x18002ac74`
- `0x18003b140`
- `0x1800507a0`
- `0x1800523e8`
- `0x1800590e0`
- `0x180061000`
- `0x180062f88`
- `0x18006e460`
- `0x18008b9cc`
- `0x18008c480`
- `0x18009ea08`
- `0x1800a03b4`
- `0x1800bf570`
- `0x1800bf8d8`
- `0x1800c0c7c`
- `0x1800c365c`
- `0x1800ccef8`
- `0x1800dd8b0`
- `0x1800ddbe4`
- `0x1800ecbf0`
- `0x1800ecf00`
- `0x1800ed0a0`
- `0x1800ed91c`
- `0x1800edb70`
- `0x1800ee198`

## callees

- `0x18000e370`
- `0x18000f5f0`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f626`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f6b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f626`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f6b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f787`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f766`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f766`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f6f2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f6f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
CNestedImpersonation *__fastcall CNestedImpersonation::CNestedImpersonation(
        CNestedImpersonation *this,
        const struct TokenHandle *a2)
{
  _DWORD *v4; // rax
  volatile signed __int32 **v5; // rsi
  volatile signed __int32 *v6; // rax
  __int64 v7; // rax
  _DWORD *v8; // rax
  void *v10; // rcx
  char *v11; // rcx
  signed int LastError; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v14; // [rsp+28h] [rbp-58h]
  int v15; // [rsp+38h] [rbp-48h]
  int v16; // [rsp+3Ch] [rbp-44h]
  int v17; // [rsp+40h] [rbp-40h]
  void *v18; // [rsp+C0h] [rbp+40h] BYREF

  v4 = HeapAlloc(hBitsHeap, 8u, 0x10u);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = -2147024882;
    v16 = 0;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *(_QWORD *)this = v4;
  v4[2] = 1;
  **(_QWORD **)this = 0;
  v5 = (volatile signed __int32 **)CopyThreadToken(&v18);
  if ( **(_QWORD **)this != *(_QWORD *)*v5 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)this + 8LL), 0xFFFFFFFF) == 1 )
    {
      v11 = **(char ***)this;
      if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v11);
        **(_QWORD **)this = 0;
      }
      operator delete(*(void **)this, 0x10u);
      *(_QWORD *)this = 0;
    }
    v6 = *v5;
    *(_QWORD *)this = *v5;
    _InterlockedIncrement(v6 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 2, 0xFFFFFFFF) == 1 )
  {
    v10 = v18;
    if ( (unsigned __int64)(*(_QWORD *)v18 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v18);
      *(_QWORD *)v18 = 0;
      v10 = v18;
    }
    operator delete(v10, 0x10u);
    v18 = 0;
  }
  *((_BYTE *)this + 8) = 0;
  v7 = *(_QWORD *)a2;
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  *((_QWORD *)this + 3) = 0;
  v8 = HeapAlloc(hBitsHeap, 8u, 4u);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = -2147024882;
    v16 = 0;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *v8 = 1;
  *((_QWORD *)this + 4) = v8;
  *((_QWORD *)this + 5) = 0;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)this + 6) = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !*((_BYTE *)this + 8) )
  {
    if ( !ImpersonateLoggedOnUser(**((HANDLE **)this + 2)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = 0;
      pExceptionObject = &ComError::`vftable';
      v15 = LastError;
      v16 = 0;
      v17 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *((_BYTE *)this + 8) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x18000f5f0  mov     [rsp-28h+arg_8], rbx
0x18000f5f5  mov     [rsp-28h+arg_0], rcx
0x18000f5fa  push    rbp
0x18000f5fb  push    rsi
0x18000f5fc  push    rdi
0x18000f5fd  push    r14
0x18000f5ff  push    r15
0x18000f601  mov     rbp, rsp
0x18000f604  sub     rsp, 80h
0x18000f60b  mov     r14, rdx
0x18000f60e  mov     rdi, rcx
0x18000f611  xor     r15d, r15d
0x18000f614  mov     edx, 8; dwFlags
0x18000f619  mov     r8d, 10h; dwBytes
0x18000f61f  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000f626  call    cs:__imp_HeapAlloc
0x18000f62c  test    rax, rax
0x18000f62f  jz      loc_18000F7C6
0x18000f635  mov     [rdi], rax
0x18000f638  mov     dword ptr [rax+8], 1
0x18000f63f  mov     rax, [rdi]
0x18000f642  mov     [rax], r15
0x18000f645  lea     rcx, [rbp+arg_10]
0x18000f649  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000f64e  mov     rsi, rax
0x18000f651  mov     r8, [rdi]
0x18000f654  mov     rcx, [rax]
0x18000f657  mov     rdx, [rcx]
0x18000f65a  mov     ebx, 0FFFFFFFFh
0x18000f65f  cmp     [r8], rdx
0x18000f662  jz      short loc_18000F67F
0x18000f664  mov     ecx, ebx
0x18000f666  lock xadd [r8+8], ecx
0x18000f66c  cmp     ecx, 1
0x18000f66f  jz      loc_18000F756
0x18000f675  mov     rax, [rsi]
0x18000f678  mov     [rdi], rax
0x18000f67b  lock inc dword ptr [rax+8]
0x18000f67f  mov     rax, [rbp+arg_10]
0x18000f683  lock xadd [rax+8], ebx
0x18000f688  cmp     ebx, 1
0x18000f68b  jz      loc_18000F71E
0x18000f691  mov     byte ptr [rdi+8], 0
0x18000f695  mov     rax, [r14]
0x18000f698  mov     [rdi+10h], rax
0x18000f69c  lock inc dword ptr [rax+8]
0x18000f6a0  mov     [rdi+18h], r15
0x18000f6a4  mov     edx, 8; dwFlags
0x18000f6a9  mov     r8d, 4; dwBytes
0x18000f6af  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000f6b6  call    cs:__imp_HeapAlloc
0x18000f6bc  test    rax, rax
0x18000f6bf  jz      loc_18000F82F
0x18000f6c5  mov     dword ptr [rax], 1
0x18000f6cb  mov     [rdi+20h], rax
0x18000f6cf  mov     [rdi+28h], r15
0x18000f6d3  lock inc cs:dword_180145058
0x18000f6da  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18000f6e1  mov     [rdi+30h], rax
0x18000f6e5  cmp     byte ptr [rdi+8], 0
0x18000f6e9  jnz     short loc_18000F704
0x18000f6eb  mov     rcx, [rdi+10h]
0x18000f6ef  mov     rcx, [rcx]; hToken
0x18000f6f2  call    cs:__imp_ImpersonateLoggedOnUser
0x18000f6f8  test    eax, eax
0x18000f6fa  jz      loc_18000F787
0x18000f700  mov     byte ptr [rdi+8], 1
0x18000f704  mov     rax, rdi
0x18000f707  mov     rbx, [rsp+80h+arg_8]
0x18000f70f  add     rsp, 80h
0x18000f716  pop     r15
0x18000f718  pop     r14
0x18000f71a  pop     rdi
0x18000f71b  pop     rsi
0x18000f71c  pop     rbp
0x18000f71d  retn
0x18000f71e  mov     rcx, [rbp+arg_10]
0x18000f722  mov     rdx, [rcx]
0x18000f725  lea     rax, [rdx-1]
0x18000f729  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f72d  ja      short loc_18000F743
0x18000f72f  mov     rcx, rdx; hObject
0x18000f732  call    cs:__imp_CloseHandle
0x18000f738  mov     rax, [rbp+arg_10]
0x18000f73c  mov     [rax], r15
0x18000f73f  mov     rcx, [rbp+arg_10]; void *
0x18000f743  mov     edx, 10h; unsigned __int64
0x18000f748  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f74d  mov     [rbp+arg_10], r15
0x18000f751  jmp     loc_18000F691
0x18000f756  mov     rcx, [rdi]
0x18000f759  mov     rcx, [rcx]; hObject
0x18000f75c  lea     rax, [rcx-1]
0x18000f760  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f764  ja      short loc_18000F772
0x18000f766  call    cs:__imp_CloseHandle
0x18000f76c  mov     rax, [rdi]
0x18000f76f  mov     [rax], r15
0x18000f772  mov     edx, 10h; unsigned __int64
0x18000f777  mov     rcx, [rdi]; void *
0x18000f77a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f77f  mov     [rdi], r15
0x18000f782  jmp     loc_18000F675
0x18000f787  call    cs:__imp_GetLastError
0x18000f78d  test    eax, eax
0x18000f78f  jg      loc_18000F898
0x18000f795  xorps   xmm0, xmm0
0x18000f798  movups  [rbp+var_58], xmm0
0x18000f79c  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f7a3  mov     [rbp+pExceptionObject], rcx
0x18000f7a7  mov     [rbp+var_48], eax
0x18000f7aa  mov     [rbp+var_44], r15d
0x18000f7ae  mov     [rbp+var_40], 1
0x18000f7b5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f7bc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f7c0  call    _CxxThrowException_0
0x18000f7c6  lea     rax, WPP_GLOBAL_Control
0x18000f7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7d4  cmp     rcx, rax
0x18000f7d7  jz      short loc_18000F7FA
0x18000f7d9  test    byte ptr [rcx+1Ch], 4
0x18000f7dd  jz      short loc_18000F7FA
0x18000f7df  mov     edx, 0Ah
0x18000f7e4  mov     r9d, 10h
0x18000f7ea  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000f7f1  mov     rcx, [rcx+10h]
0x18000f7f5  call    WPP_SF_d
0x18000f7fa  xorps   xmm0, xmm0
0x18000f7fd  movups  [rbp+var_58], xmm0
0x18000f801  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f808  mov     [rbp+pExceptionObject], rcx
0x18000f80c  mov     [rbp+var_48], 8007000Eh
0x18000f813  mov     [rbp+var_44], r15d
0x18000f817  mov     [rbp+var_40], 1
0x18000f81e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f825  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f829  call    _CxxThrowException_0
0x18000f82f  lea     rax, WPP_GLOBAL_Control
0x18000f836  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f83d  cmp     rcx, rax
0x18000f840  jz      short loc_18000F863
0x18000f842  test    byte ptr [rcx+1Ch], 4
0x18000f846  jz      short loc_18000F863
0x18000f848  mov     edx, 0Ah
0x18000f84d  mov     r9d, 4
0x18000f853  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000f85a  mov     rcx, [rcx+10h]
0x18000f85e  call    WPP_SF_d
0x18000f863  xorps   xmm0, xmm0
0x18000f866  movups  [rbp+var_58], xmm0
0x18000f86a  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f871  mov     [rbp+pExceptionObject], rcx
0x18000f875  mov     [rbp+var_48], 8007000Eh
0x18000f87c  mov     [rbp+var_44], r15d
0x18000f880  mov     [rbp+var_40], 1
0x18000f887  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f88e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000f892  call    _CxxThrowException_0
0x18000f898  movzx   eax, ax
0x18000f89b  or      eax, 80070000h
0x18000f8a0  jmp     loc_18000F795
```
