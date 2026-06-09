# COfflineFilesCache::IsPathCacheable(ushort const *,int *,tagOFFLINEFILES_CACHING_MODE *)

- ea: `0x180008070`
- end: `0x1800081db`
- name: `?IsPathCacheable@COfflineFilesCache@@UEAAJPEBGPEAHPEAW4tagOFFLINEFILES_CACHING_MODE@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(COfflineFilesCache *__hidden this, const unsigned __int16 *, int *, enum tagOFFLINEFILES_CACHING_MODE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008070`
- `0x18000f5a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000810d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000810d`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::IsPathCacheable(
        COfflineFilesCache *this,
        const unsigned __int16 *a2,
        int *a3,
        enum tagOFFLINEFILES_CACHING_MODE *a4)
{
  _QWORD *v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // rax
  unsigned int v10; // edi
  __int64 result; // rax
  _QWORD v12[5]; // [rsp+30h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && a3 && a4 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 5);
    v8 = -2147467262;
    v12[0] = 0;
    v9 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v7;
    if ( !v9 )
      v9 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v7[1];
    if ( !v9 )
    {
      v10 = *((_DWORD *)this + 12);
      if ( v10 )
      {
        ppv = 0;
        v8 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, _QWORD *))(*(_QWORD *)ppv + 40LL))(
                 ppv,
                 v10,
                 &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
                 v12);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *, enum tagOFFLINEFILES_CACHING_MODE *))(*(_QWORD *)v12[0] + 224LL))(
                 v12[0],
                 a2,
                 a3,
                 a4);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
        }
      }
    }
    result = 0;
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008070  push    rbp
0x180008072  push    rsi
0x180008073  push    r14
0x180008075  sub     rsp, 40h
0x180008079  mov     rsi, r9
0x18000807c  mov     rbp, r8
0x18000807f  mov     r14, rdx
0x180008082  test    rdx, rdx
0x180008085  jz      loc_18000819F
0x18000808b  test    r8, r8
0x18000808e  jz      loc_18000819F
0x180008094  test    r9, r9
0x180008097  jz      loc_18000819F
0x18000809d  mov     rdx, [rcx+28h]
0x1800080a1  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x1800080a8  mov     [rsp+58h+arg_0], rbx
0x1800080ad  mov     ebx, 80004002h
0x1800080b2  mov     [rsp+58h+arg_18], r15
0x1800080b7  xor     r15d, r15d
0x1800080ba  mov     [rsp+58h+var_28], r15
0x1800080bf  sub     rax, [rdx]
0x1800080c2  jnz     short loc_1800080CF
0x1800080c4  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x1800080cb  sub     rax, [rdx+8]
0x1800080cf  test    rax, rax
0x1800080d2  jnz     loc_180008184
0x1800080d8  mov     [rsp+58h+arg_10], rdi
0x1800080dd  mov     edi, [rcx+30h]
0x1800080e0  test    edi, edi
0x1800080e2  jz      loc_18000817F
0x1800080e8  lea     rax, [rsp+58h+arg_8]
0x1800080ed  mov     [rsp+58h+arg_8], r15
0x1800080f2  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800080f9  mov     [rsp+58h+ppv], rax; ppv
0x1800080fe  xor     edx, edx; pUnkOuter
0x180008100  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008107  mov     r8d, 1; dwClsContext
0x18000810d  call    cs:__imp_CoCreateInstance
0x180008113  mov     ebx, eax
0x180008115  test    eax, eax
0x180008117  js      short loc_18000814B
0x180008119  mov     rcx, [rsp+58h+arg_8]
0x18000811e  lea     r9, [rsp+58h+var_28]
0x180008123  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x18000812a  mov     edx, edi
0x18000812c  mov     rax, [rcx]
0x18000812f  mov     rax, [rax+28h]
0x180008133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008138  mov     rcx, [rsp+58h+arg_8]
0x18000813d  mov     ebx, eax
0x18000813f  mov     rax, [rcx]
0x180008142  mov     rax, [rax+10h]
0x180008146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814b  test    ebx, ebx
0x18000814d  js      short loc_18000817F
0x18000814f  mov     rcx, [rsp+58h+var_28]
0x180008154  mov     r9, rsi
0x180008157  mov     r8, rbp
0x18000815a  mov     rdx, r14
0x18000815d  mov     rax, [rcx]
0x180008160  mov     rax, [rax+0E0h]
0x180008167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000816c  mov     rcx, [rsp+58h+var_28]
0x180008171  mov     ebx, eax
0x180008173  mov     rax, [rcx]
0x180008176  mov     rax, [rax+10h]
0x18000817a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000817f  mov     rdi, [rsp+58h+arg_10]
0x180008184  test    ebx, ebx
0x180008186  mov     eax, r15d
0x180008189  mov     r15, [rsp+58h+arg_18]
0x18000818e  cmovs   eax, ebx
0x180008191  mov     rbx, [rsp+58h+arg_0]
0x180008196  add     rsp, 40h
0x18000819a  pop     r14
0x18000819c  pop     rsi
0x18000819d  pop     rbp
0x18000819e  retn
0x18000819f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081a6  lea     rax, WPP_GLOBAL_Control
0x1800081ad  cmp     rcx, rax
0x1800081b0  jz      short loc_1800081CD
0x1800081b2  test    byte ptr [rcx+1Ch], 2
0x1800081b6  jz      short loc_1800081CD
0x1800081b8  mov     rcx, [rcx+10h]
0x1800081bc  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x1800081c3  mov     edx, 2Ah ; '*'
0x1800081c8  call    WPP_SF_
0x1800081cd  mov     eax, 80004003h
0x1800081d2  add     rsp, 40h
0x1800081d6  pop     r14
0x1800081d8  pop     rsi
0x1800081d9  pop     rbp
0x1800081da  retn
```
