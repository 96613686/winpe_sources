# GetINetCfgLock

- ea: `0x18003f6bc`
- end: `0x18003fa78`
- name: `GetINetCfgLock`
- size: `956`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010520`
- `0x180044198`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e650`
- `0x18003f6bc`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f7d6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f798`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003f798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9cc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003fa2e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003fa2e`

## string_xrefs

- `0x18003f87a`: `rasmans.dll`

## pseudocode

```c
__int64 __fastcall GetINetCfgLock(LPVOID *a1, _QWORD *a2, unsigned int a3, _DWORD *a4)
{
  struct _LIST_ENTRY *v8; // rcx
  bool v9; // zf
  HRESULT v11; // eax
  unsigned int v12; // ebx
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+58h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 697, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a3);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = g_RasMobileCore == 0;
  ppv = 0;
  v17 = 0;
  pv = 0;
  *a1 = 0;
  *a2 = 0;
  *a4 = 0;
  if ( !v9 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 6u )
    {
      WPP_SF_d(v8[1].Flink, 698, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 1);
    }
    return 1;
  }
  v11 = CoInitializeEx(0, 4u);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( v11 != -2147417850 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_48;
      }
      v14 = 699;
LABEL_46:
      WPP_SF_d(v13[1].Flink, v14, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, (unsigned int)v11);
LABEL_47:
      v13 = WPP_GLOBAL_Control;
LABEL_48:
      if ( pv )
      {
        CoTaskMemFree(pv);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v13 = WPP_GLOBAL_Control;
        v17 = 0;
      }
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v13 = WPP_GLOBAL_Control;
        ppv = 0;
      }
      if ( *a4 )
      {
        CoUninitialize();
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v13[1].Blink) & 0x2000) != 0
        && BYTE1(v13[1].Blink) >= 6u )
      {
        WPP_SF_d(v13[1].Flink, 705, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v12);
      }
      return v12;
    }
  }
  else
  {
    *a4 = 1;
  }
  v11 = CoCreateInstance(&CLSID_CNetCfg, 0, 1u, &IID_INetCfg, &ppv);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    v14 = 700;
    goto LABEL_46;
  }
  v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_INetCfgLock, &v17);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    v14 = 701;
    goto LABEL_46;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, LPVOID *))(*(_QWORD *)v17 + 24LL))(
          v17,
          a3,
          L"rasmans.dll",
          &pv);
  v12 = v15;
  if ( v15 == 1 )
  {
    v12 = -2147180508;
    goto LABEL_27;
  }
  if ( v15 < 0 )
  {
LABEL_27:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_48;
    }
    WPP_SF_Sd(
      WPP_GLOBAL_Control[1].Flink,
      702,
      (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
      (_DWORD)pv,
      v12);
    goto LABEL_47;
  }
  if ( pv )
    CoTaskMemFree(pv);
  *a1 = ppv;
  *a2 = v17;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 703, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v16 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v16[1].Blink) & 0x2000) != 0
      && BYTE1(v16[1].Blink) >= 6u )
    {
      WPP_SF_d(v16[1].Flink, 704, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003f6bc  push    rbp
0x18003f6be  push    rbx
0x18003f6bf  push    rsi
0x18003f6c0  push    rdi
0x18003f6c1  push    r12
0x18003f6c3  push    r14
0x18003f6c5  push    r15
0x18003f6c7  mov     rbp, rsp
0x18003f6ca  sub     rsp, 30h
0x18003f6ce  mov     r12, r9
0x18003f6d1  mov     r15d, r8d
0x18003f6d4  mov     rsi, rdx
0x18003f6d7  mov     r14, rcx
0x18003f6da  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f6e1  lea     rax, WPP_GLOBAL_Control
0x18003f6e8  cmp     rcx, rax
0x18003f6eb  jz      short loc_18003F722
0x18003f6ed  test    dword ptr [rcx+1Ch], 2000h
0x18003f6f4  jz      short loc_18003F722
0x18003f6f6  cmp     byte ptr [rcx+19h], 6
0x18003f6fa  jb      short loc_18003F722
0x18003f6fc  mov     rcx, [rcx+10h]
0x18003f700  mov     r9d, r8d
0x18003f703  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f70a  mov     edx, 2B9h
0x18003f70f  call    WPP_SF_d
0x18003f714  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f71b  lea     rax, WPP_GLOBAL_Control
0x18003f722  cmp     cs:g_RasMobileCore, 0
0x18003f729  mov     [rbp+arg_8], 0
0x18003f731  mov     [rbp+arg_0], 0
0x18003f739  mov     [rbp+pv], 0
0x18003f741  mov     qword ptr [r14], 0
0x18003f748  mov     qword ptr [rsi], 0
0x18003f74f  mov     dword ptr [r12], 0
0x18003f757  jz      short loc_18003F791
0x18003f759  mov     edi, 1
0x18003f75e  cmp     rcx, rax
0x18003f761  jz      short loc_18003F78A
0x18003f763  test    dword ptr [rcx+1Ch], 2000h
0x18003f76a  jz      short loc_18003F78A
0x18003f76c  cmp     byte ptr [rcx+19h], 6
0x18003f770  jb      short loc_18003F78A
0x18003f772  mov     rcx, [rcx+10h]
0x18003f776  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f77d  mov     edx, 2BAh
0x18003f782  mov     r9d, edi
0x18003f785  call    WPP_SF_d
0x18003f78a  mov     eax, edi
0x18003f78c  jmp     loc_18003FA69
0x18003f791  mov     edx, 4; dwCoInit
0x18003f796  xor     ecx, ecx; pvReserved
0x18003f798  call    cs:__imp_CoInitializeEx
0x18003f79e  mov     ebx, eax
0x18003f7a0  mov     edi, 1
0x18003f7a5  test    eax, eax
0x18003f7a7  js      short loc_18003F7AF
0x18003f7a9  mov     [r12], edi
0x18003f7ad  jmp     short loc_18003F7BA
0x18003f7af  cmp     eax, 80010106h
0x18003f7b4  jnz     loc_18003F97F
0x18003f7ba  lea     rax, [rbp+arg_8]
0x18003f7be  mov     r8d, edi; dwClsContext
0x18003f7c1  lea     r9, IID_INetCfg; riid
0x18003f7c8  mov     [rsp+30h+ppv], rax; ppv
0x18003f7cd  xor     edx, edx; pUnkOuter
0x18003f7cf  lea     rcx, CLSID_CNetCfg; rclsid
0x18003f7d6  call    cs:__imp_CoCreateInstance
0x18003f7dc  mov     ebx, eax
0x18003f7de  test    eax, eax
0x18003f7e0  jns     short loc_18003F81A
0x18003f7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f7e9  lea     rdi, WPP_GLOBAL_Control
0x18003f7f0  cmp     rcx, rdi
0x18003f7f3  jz      loc_18003F9C0
0x18003f7f9  test    dword ptr [rcx+1Ch], 2000h
0x18003f800  jz      loc_18003F9C0
0x18003f806  cmp     byte ptr [rcx+19h], 2
0x18003f80a  jb      loc_18003F9C0
0x18003f810  mov     edx, 2BCh
0x18003f815  jmp     loc_18003F9A6
0x18003f81a  mov     rcx, [rbp+arg_8]
0x18003f81e  lea     r8, [rbp+arg_0]
0x18003f822  lea     rdx, IID_INetCfgLock
0x18003f829  mov     rax, [rcx]
0x18003f82c  mov     rax, [rax]
0x18003f82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f834  mov     ebx, eax
0x18003f836  test    eax, eax
0x18003f838  jns     short loc_18003F872
0x18003f83a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f841  lea     rdi, WPP_GLOBAL_Control
0x18003f848  cmp     rcx, rdi
0x18003f84b  jz      loc_18003F9C0
0x18003f851  test    dword ptr [rcx+1Ch], 2000h
0x18003f858  jz      loc_18003F9C0
0x18003f85e  cmp     byte ptr [rcx+19h], 2
0x18003f862  jb      loc_18003F9C0
0x18003f868  mov     edx, 2BDh
0x18003f86d  jmp     loc_18003F9A6
0x18003f872  mov     rcx, [rbp+arg_0]
0x18003f876  lea     r9, [rbp+pv]
0x18003f87a  lea     r8, aRasmansDll_2; "rasmans.dll"
0x18003f881  mov     edx, r15d
0x18003f884  mov     rax, [rcx]
0x18003f887  mov     rax, [rax+18h]
0x18003f88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f890  mov     ebx, eax
0x18003f892  cmp     eax, edi
0x18003f894  jnz     short loc_18003F89D
0x18003f896  mov     ebx, 8004A024h
0x18003f89b  jmp     short loc_18003F8A1
0x18003f89d  test    eax, eax
0x18003f89f  jns     short loc_18003F8F1
0x18003f8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8a8  lea     rdi, WPP_GLOBAL_Control
0x18003f8af  cmp     rcx, rdi
0x18003f8b2  jz      loc_18003F9C0
0x18003f8b8  test    dword ptr [rcx+1Ch], 2000h
0x18003f8bf  jz      loc_18003F9C0
0x18003f8c5  cmp     byte ptr [rcx+19h], 2
0x18003f8c9  jb      loc_18003F9C0
0x18003f8cf  mov     r9, [rbp+pv]
0x18003f8d3  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f8da  mov     rcx, [rcx+10h]
0x18003f8de  mov     edx, 2BEh
0x18003f8e3  mov     dword ptr [rsp+30h+ppv], ebx
0x18003f8e7  call    WPP_SF_Sd
0x18003f8ec  jmp     loc_18003F9B9
0x18003f8f1  mov     rcx, [rbp+pv]; pv
0x18003f8f5  test    rcx, rcx
0x18003f8f8  jz      short loc_18003F900
0x18003f8fa  call    cs:__imp_CoTaskMemFree
0x18003f900  mov     rax, [rbp+arg_8]
0x18003f904  mov     [r14], rax
0x18003f907  mov     rax, [rbp+arg_0]
0x18003f90b  mov     [rsi], rax
0x18003f90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f915  lea     rdi, WPP_GLOBAL_Control
0x18003f91c  cmp     rcx, rdi
0x18003f91f  jz      short loc_18003F978
0x18003f921  test    dword ptr [rcx+1Ch], 2000h
0x18003f928  jz      short loc_18003F94C
0x18003f92a  cmp     byte ptr [rcx+19h], 5
0x18003f92e  jb      short loc_18003F94C
0x18003f930  mov     rcx, [rcx+10h]
0x18003f934  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f93b  mov     edx, 2BFh
0x18003f940  call    WPP_SF_
0x18003f945  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f94c  cmp     rcx, rdi
0x18003f94f  jz      short loc_18003F978
0x18003f951  test    dword ptr [rcx+1Ch], 2000h
0x18003f958  jz      short loc_18003F978
0x18003f95a  cmp     byte ptr [rcx+19h], 6
0x18003f95e  jb      short loc_18003F978
0x18003f960  mov     rcx, [rcx+10h]
0x18003f964  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f96b  mov     edx, 2C0h
0x18003f970  xor     r9d, r9d
0x18003f973  call    WPP_SF_d
0x18003f978  xor     eax, eax
0x18003f97a  jmp     loc_18003FA69
0x18003f97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f986  lea     rdi, WPP_GLOBAL_Control
0x18003f98d  cmp     rcx, rdi
0x18003f990  jz      short loc_18003F9C0
0x18003f992  test    dword ptr [rcx+1Ch], 2000h
0x18003f999  jz      short loc_18003F9C0
0x18003f99b  cmp     byte ptr [rcx+19h], 2
0x18003f99f  jb      short loc_18003F9C0
0x18003f9a1  mov     edx, 2BBh
0x18003f9a6  mov     rcx, [rcx+10h]
0x18003f9aa  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003f9b1  mov     r9d, eax
0x18003f9b4  call    WPP_SF_d
0x18003f9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9c0  mov     rax, [rbp+pv]
0x18003f9c4  test    rax, rax
0x18003f9c7  jz      short loc_18003F9D9
0x18003f9c9  mov     rcx, rax; pv
0x18003f9cc  call    cs:__imp_CoTaskMemFree
0x18003f9d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9d9  mov     rdx, [rbp+arg_0]
0x18003f9dd  test    rdx, rdx
0x18003f9e0  jz      short loc_18003FA00
0x18003f9e2  mov     rax, [rdx]
0x18003f9e5  mov     rcx, rdx
0x18003f9e8  mov     rax, [rax+10h]
0x18003f9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9f8  mov     [rbp+arg_0], 0
0x18003fa00  mov     rdx, [rbp+arg_8]
0x18003fa04  test    rdx, rdx
0x18003fa07  jz      short loc_18003FA27
0x18003fa09  mov     rax, [rdx]
0x18003fa0c  mov     rcx, rdx
0x18003fa0f  mov     rax, [rax+10h]
0x18003fa13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa18  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa1f  mov     [rbp+arg_8], 0
0x18003fa27  cmp     dword ptr [r12], 0
0x18003fa2c  jz      short loc_18003FA3B
0x18003fa2e  call    cs:__imp_CoUninitialize
0x18003fa34  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa3b  cmp     rcx, rdi
0x18003fa3e  jz      short loc_18003FA67
0x18003fa40  test    dword ptr [rcx+1Ch], 2000h
0x18003fa47  jz      short loc_18003FA67
0x18003fa49  cmp     byte ptr [rcx+19h], 6
0x18003fa4d  jb      short loc_18003FA67
0x18003fa4f  mov     rcx, [rcx+10h]
0x18003fa53  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003fa5a  mov     edx, 2C1h
0x18003fa5f  mov     r9d, ebx
0x18003fa62  call    WPP_SF_d
0x18003fa67  mov     eax, ebx
0x18003fa69  add     rsp, 30h
0x18003fa6d  pop     r15
0x18003fa6f  pop     r14
0x18003fa71  pop     r12
0x18003fa73  pop     rdi
0x18003fa74  pop     rsi
0x18003fa75  pop     rbx
0x18003fa76  pop     rbp
0x18003fa77  retn
```
