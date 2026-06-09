# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800b7fa8`
- end: `0x1800b8158`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b8500`

## callees

- `0x1800a5fc8`
- `0x1800a7558`
- `0x1800b7fa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b80a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b80a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b8100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b80bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b811c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b80bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b811c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b8051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b8051`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800b806f`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800b806f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rsi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r14
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // rdi
  int v12; // ebx
  unsigned int v13; // ebp
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // esi
  DWORD LastError; // eax
  DWORD v19; // eax

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 )
  {
    if ( v10 )
    {
      v12 = 0;
      v13 = 0;
      if ( (_DWORD)v5 )
      {
        while ( v12 >= 0 )
        {
          v14 = -1;
          v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
          v15 = *(const WCHAR **)(a2 + 8LL * v13);
          do
            ++v14;
          while ( v15[v14] );
          String = WindowsCreateString(v15, v14, &v11[v13++]);
          v12 = String;
          if ( v13 >= (unsigned int)v5 )
          {
            if ( String < 0 )
              break;
            goto LABEL_14;
          }
        }
      }
      else
      {
LABEL_14:
        v12 = RoRegisterActivationFactories(v11, v8, (unsigned int)v5, a3);
      }
      for ( i = 0; i < v13; ++i )
        WindowsDeleteString(v11[i]);
    }
    else
    {
      v12 = -2147024882;
    }
    if ( !HeapFree(hBitsHeap, 0, v8)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v8, LastError);
    }
  }
  else
  {
    v12 = -2147024882;
  }
  if ( v11
    && !HeapFree(hBitsHeap, 0, v11)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v19 = GetLastError();
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v11, v19);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b7fa8  push    rbx
0x1800b7faa  push    rbp
0x1800b7fab  push    rsi
0x1800b7fac  push    rdi
0x1800b7fad  push    r12
0x1800b7faf  push    r13
0x1800b7fb1  push    r14
0x1800b7fb3  push    r15
0x1800b7fb5  sub     rsp, 38h
0x1800b7fb9  mov     r15, rdx
0x1800b7fbc  mov     esi, r9d
0x1800b7fbf  mov     edi, 8
0x1800b7fc4  mov     r12, r8
0x1800b7fc7  mov     eax, edi
0x1800b7fc9  mul     rsi
0x1800b7fcc  lea     rbp, [rdi-9]
0x1800b7fd0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b7fd7  cmovb   rax, rbp
0x1800b7fdb  mov     rcx, rax; unsigned __int64
0x1800b7fde  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b7fe3  mov     r14, rax
0x1800b7fe6  mov     eax, edi
0x1800b7fe8  mul     rsi
0x1800b7feb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b7ff2  cmovb   rax, rbp
0x1800b7ff6  mov     rcx, rax; unsigned __int64
0x1800b7ff9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b7ffe  xor     r13d, r13d
0x1800b8001  lea     rbp, WPP_GLOBAL_Control
0x1800b8008  mov     rdi, rax
0x1800b800b  test    r14, r14
0x1800b800e  jz      loc_1800B80EA
0x1800b8014  test    rax, rax
0x1800b8017  jnz     short loc_1800B8020
0x1800b8019  mov     ebx, 8007000Eh
0x1800b801e  jmp     short loc_1800B8097
0x1800b8020  mov     ebx, r13d
0x1800b8023  mov     ebp, r13d
0x1800b8026  test    esi, esi
0x1800b8028  jz      short loc_1800B8063
0x1800b802a  test    ebx, ebx
0x1800b802c  js      short loc_1800B8077
0x1800b802e  mov     eax, ebp
0x1800b8030  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x1800b8037  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b803b  mov     [r14+rax*8], rcx
0x1800b803f  mov     rcx, [r15+rax*8]; sourceString
0x1800b8043  inc     rdx; length
0x1800b8046  cmp     [rcx+rdx*2], r13w
0x1800b804b  jnz     short loc_1800B8043
0x1800b804d  lea     r8, [rdi+rax*8]; string
0x1800b8051  call    cs:__imp_WindowsCreateString
0x1800b8057  inc     ebp
0x1800b8059  mov     ebx, eax
0x1800b805b  cmp     ebp, esi
0x1800b805d  jb      short loc_1800B802A
0x1800b805f  test    eax, eax
0x1800b8061  js      short loc_1800B8077
0x1800b8063  mov     r9, r12
0x1800b8066  mov     r8d, esi
0x1800b8069  mov     rdx, r14
0x1800b806c  mov     rcx, rdi
0x1800b806f  call    cs:__imp_RoRegisterActivationFactories
0x1800b8075  mov     ebx, eax
0x1800b8077  mov     esi, r13d
0x1800b807a  test    ebp, ebp
0x1800b807c  jz      short loc_1800B8090
0x1800b807e  mov     ecx, esi
0x1800b8080  mov     rcx, [rdi+rcx*8]; string
0x1800b8084  call    cs:__imp_WindowsDeleteString
0x1800b808a  inc     esi
0x1800b808c  cmp     esi, ebp
0x1800b808e  jb      short loc_1800B807E
0x1800b8090  lea     rbp, WPP_GLOBAL_Control
0x1800b8097  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800b809e  mov     r8, r14; lpMem
0x1800b80a1  xor     edx, edx; dwFlags
0x1800b80a3  call    cs:__imp_HeapFree
0x1800b80a9  test    eax, eax
0x1800b80ab  jnz     short loc_1800B80EF
0x1800b80ad  mov     rax, cs:WPP_GLOBAL_Control
0x1800b80b4  cmp     rax, rbp
0x1800b80b7  jz      short loc_1800B80EF
0x1800b80b9  test    byte ptr [rax+1Ch], 4
0x1800b80bd  jz      short loc_1800B80EF
0x1800b80bf  call    cs:__imp_GetLastError
0x1800b80c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b80cc  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800b80d3  mov     edx, 0Bh
0x1800b80d8  mov     [rsp+78h+var_58], eax
0x1800b80dc  mov     r9, r14
0x1800b80df  mov     rcx, [rcx+10h]
0x1800b80e3  call    WPP_SF_qD
0x1800b80e8  jmp     short loc_1800B80EF
0x1800b80ea  mov     ebx, 8007000Eh
0x1800b80ef  test    rdi, rdi
0x1800b80f2  jz      short loc_1800B8145
0x1800b80f4  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800b80fb  mov     r8, rdi; lpMem
0x1800b80fe  xor     edx, edx; dwFlags
0x1800b8100  call    cs:__imp_HeapFree
0x1800b8106  test    eax, eax
0x1800b8108  jnz     short loc_1800B8145
0x1800b810a  mov     rax, cs:WPP_GLOBAL_Control
0x1800b8111  cmp     rax, rbp
0x1800b8114  jz      short loc_1800B8145
0x1800b8116  test    byte ptr [rax+1Ch], 4
0x1800b811a  jz      short loc_1800B8145
0x1800b811c  call    cs:__imp_GetLastError
0x1800b8122  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8129  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800b8130  mov     edx, 0Bh
0x1800b8135  mov     [rsp+78h+var_58], eax
0x1800b8139  mov     r9, rdi
0x1800b813c  mov     rcx, [rcx+10h]
0x1800b8140  call    WPP_SF_qD
0x1800b8145  mov     eax, ebx
0x1800b8147  add     rsp, 38h
0x1800b814b  pop     r15
0x1800b814d  pop     r14
0x1800b814f  pop     r13
0x1800b8151  pop     r12
0x1800b8153  pop     rdi
0x1800b8154  pop     rsi
0x1800b8155  pop     rbp
0x1800b8156  pop     rbx
0x1800b8157  retn
```
