# DllRegisterServer

- ea: `0x18000a2e0`
- end: `0x18000a3d6`
- name: `DllRegisterServer`
- size: `246`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076f8`
- `0x180008dd0`
- `0x18000a2e0`
- `0x18000a45c`
- `0x18000a484`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a395`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000a395`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a327`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a327`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  char v0; // si
  HRESULT v1; // eax
  HRESULT v2; // ebx
  __int64 v3; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids);
  }
  v0 = 1;
  v1 = CoInitializeEx(0, 6u);
  v2 = v1;
  if ( v1 >= 0 || (v0 = 0, v1 == -2147417850) )
  {
    v3 = qword_18003BCA8;
    if ( qword_18003BCA8 )
    {
      while ( *(_QWORD *)v3 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
        if ( v2 < 0 )
          goto LABEL_14;
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 56))();
        v2 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v4, 1);
        if ( v2 < 0 )
          goto LABEL_14;
        v3 += 72;
      }
    }
    v2 = ATL::CAtlModuleT<ATL::CComModule>::RegisterServer();
LABEL_14:
    if ( v0 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids, (unsigned int)v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a2e0  push    rbx
0x18000a2e2  push    rbp
0x18000a2e3  push    rsi
0x18000a2e4  push    rdi
0x18000a2e5  sub     rsp, 28h
0x18000a2e9  lea     rbp, WPP_GLOBAL_Control
0x18000a2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2f7  cmp     rcx, rbp
0x18000a2fa  jz      short loc_18000A31D
0x18000a2fc  test    byte ptr [rcx+1Ch], 8
0x18000a300  jz      short loc_18000A31D
0x18000a302  cmp     byte ptr [rcx+19h], 6
0x18000a306  jb      short loc_18000A31D
0x18000a308  mov     edx, 12h
0x18000a30d  lea     r8, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids
0x18000a314  mov     rcx, [rcx+10h]
0x18000a318  call    WPP_SF_
0x18000a31d  mov     sil, 1
0x18000a320  mov     edx, 6; dwCoInit
0x18000a325  xor     ecx, ecx; pvReserved
0x18000a327  call    cs:__imp_CoInitializeEx
0x18000a32d  mov     ebx, eax
0x18000a32f  test    eax, eax
0x18000a331  jns     short loc_18000A33D
0x18000a333  xor     sil, sil
0x18000a336  cmp     eax, 80010106h
0x18000a33b  jnz     short loc_18000A39B
0x18000a33d  mov     rdi, cs:qword_18003BCA8
0x18000a344  test    rdi, rdi
0x18000a347  jz      short loc_18000A389
0x18000a349  jmp     short loc_18000A383
0x18000a34b  mov     ecx, 1
0x18000a350  mov     rax, [rdi+8]
0x18000a354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a359  mov     ebx, eax
0x18000a35b  test    eax, eax
0x18000a35d  js      short loc_18000A390
0x18000a35f  mov     rax, [rdi+38h]
0x18000a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a368  mov     r8d, 1; int
0x18000a36e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x18000a371  mov     rcx, [rdi]; rguid
0x18000a374  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18000a379  mov     ebx, eax
0x18000a37b  test    eax, eax
0x18000a37d  js      short loc_18000A390
0x18000a37f  add     rdi, 48h ; 'H'
0x18000a383  cmp     qword ptr [rdi], 0
0x18000a387  jnz     short loc_18000A34B
0x18000a389  call    ?RegisterServer@?$CAtlModuleT@VCComModule@ATL@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<ATL::CComModule>::RegisterServer(int,_GUID const *)
0x18000a38e  mov     ebx, eax
0x18000a390  test    sil, sil
0x18000a393  jz      short loc_18000A39B
0x18000a395  call    cs:__imp_CoUninitialize
0x18000a39b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3a2  cmp     rcx, rbp
0x18000a3a5  jz      short loc_18000A3CB
0x18000a3a7  test    byte ptr [rcx+1Ch], 8
0x18000a3ab  jz      short loc_18000A3CB
0x18000a3ad  cmp     byte ptr [rcx+19h], 6
0x18000a3b1  jb      short loc_18000A3CB
0x18000a3b3  mov     edx, 13h
0x18000a3b8  mov     r9d, ebx
0x18000a3bb  lea     r8, WPP_9c52d0f0b0473a65f63536fc845b93bf_Traceguids
0x18000a3c2  mov     rcx, [rcx+10h]
0x18000a3c6  call    WPP_SF_d
0x18000a3cb  mov     eax, ebx
0x18000a3cd  add     rsp, 28h
0x18000a3d1  pop     rdi
0x18000a3d2  pop     rsi
0x18000a3d3  pop     rbp
0x18000a3d4  pop     rbx
0x18000a3d5  retn
```
