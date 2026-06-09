# CHNetCfgMgr::ProhibitedByPolicy(ulong)

- ea: `0x180016b70`
- end: `0x180016c95`
- name: `?ProhibitedByPolicy@CHNetCfgMgr@@IEAAEK@Z`
- size: `293`
- prototype: `bool __fastcall(CHNetCfgMgr *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010be0`
- `0x180011030`

## callees

- `0x18000a484`
- `0x180016b70`
- `0x180018090`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016bcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016bcd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016bf3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016bf3`

## pseudocode

```c
bool __fastcall CHNetCfgMgr::ProhibitedByPolicy(CHNetCfgMgr *this, unsigned int a2)
{
  _QWORD *v4; // rbx
  int v5; // esi
  bool v6; // di
  HRESULT Instance; // eax
  __int64 v8; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, a2);
  }
  v4 = (_QWORD *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) )
    goto LABEL_13;
  v5 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( !*v4 )
  {
    Instance = CoCreateInstance(
                 &CLSID_NetConnectionUiUtilities,
                 0,
                 0x8005u,
                 &GUID_faedcf5e_31fe_11d1_aad2_00805fc1270e,
                 (LPVOID *)this + 13);
    v5 = Instance;
    if ( Instance < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        329,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)Instance);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v5 >= 0 )
LABEL_13:
    v6 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 48LL))(*v4, a2) == 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v8) = v6;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v8);
  }
  return v6;
}

```

## disassembly

```asm
0x180016b70  push    rbx
0x180016b72  push    rbp
0x180016b73  push    rsi
0x180016b74  push    rdi
0x180016b75  push    r12
0x180016b77  push    r14
0x180016b79  sub     rsp, 38h
0x180016b7d  mov     r14d, edx
0x180016b80  mov     rbp, rcx
0x180016b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b8a  lea     r12, WPP_GLOBAL_Control
0x180016b91  cmp     rcx, r12
0x180016b94  jz      short loc_180016BBA
0x180016b96  test    byte ptr [rcx+1Ch], 8
0x180016b9a  jz      short loc_180016BBA
0x180016b9c  cmp     byte ptr [rcx+19h], 6
0x180016ba0  jb      short loc_180016BBA
0x180016ba2  mov     rcx, [rcx+10h]
0x180016ba6  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180016bad  mov     edx, 148h
0x180016bb2  mov     r9d, r14d
0x180016bb5  call    WPP_SF_d
0x180016bba  lea     rbx, [rbp+68h]
0x180016bbe  cmp     qword ptr [rbx], 0
0x180016bc2  jnz     short loc_180016C3D
0x180016bc4  lea     rcx, [rbp+30h]; lpCriticalSection
0x180016bc8  xor     esi, esi
0x180016bca  xor     dil, dil
0x180016bcd  call    cs:__imp_EnterCriticalSection
0x180016bd3  cmp     [rbx], rsi
0x180016bd6  jnz     short loc_180016C2F
0x180016bd8  lea     r9, _GUID_faedcf5e_31fe_11d1_aad2_00805fc1270e; riid
0x180016bdf  mov     [rsp+68h+ppv], rbx; ppv
0x180016be4  xor     edx, edx; pUnkOuter
0x180016be6  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x180016bed  mov     r8d, 8005h; dwClsContext
0x180016bf3  call    cs:__imp_CoCreateInstance
0x180016bf9  mov     esi, eax
0x180016bfb  test    eax, eax
0x180016bfd  jns     short loc_180016C2F
0x180016bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c06  cmp     rcx, r12
0x180016c09  jz      short loc_180016C2F
0x180016c0b  test    byte ptr [rcx+1Ch], 8
0x180016c0f  jz      short loc_180016C2F
0x180016c11  cmp     byte ptr [rcx+19h], 2
0x180016c15  jb      short loc_180016C2F
0x180016c17  mov     rcx, [rcx+10h]
0x180016c1b  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180016c22  mov     edx, 149h
0x180016c27  mov     r9d, eax
0x180016c2a  call    WPP_SF_d
0x180016c2f  lea     rcx, [rbp+30h]; lpCriticalSection
0x180016c33  call    cs:__imp_LeaveCriticalSection
0x180016c39  test    esi, esi
0x180016c3b  js      short loc_180016C55
0x180016c3d  mov     rcx, [rbx]
0x180016c40  mov     edx, r14d
0x180016c43  mov     rax, [rcx]
0x180016c46  mov     rax, [rax+30h]
0x180016c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c4f  test    eax, eax
0x180016c51  setz    dil
0x180016c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c5c  cmp     rcx, r12
0x180016c5f  jz      short loc_180016C85
0x180016c61  test    byte ptr [rcx+1Ch], 8
0x180016c65  jz      short loc_180016C85
0x180016c67  cmp     byte ptr [rcx+19h], 6
0x180016c6b  jb      short loc_180016C85
0x180016c6d  mov     rcx, [rcx+10h]
0x180016c71  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180016c78  mov     edx, 14Ah
0x180016c7d  mov     r9b, dil
0x180016c80  call    WPP_SF_c
0x180016c85  mov     al, dil
0x180016c88  add     rsp, 38h
0x180016c8c  pop     r14
0x180016c8e  pop     r12
0x180016c90  pop     rdi
0x180016c91  pop     rsi
0x180016c92  pop     rbp
0x180016c93  pop     rbx
0x180016c94  retn
```
