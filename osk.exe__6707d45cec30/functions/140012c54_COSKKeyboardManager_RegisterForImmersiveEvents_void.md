# COSKKeyboardManager::RegisterForImmersiveEvents(void)

- ea: `0x140012c54`
- end: `0x140012d69`
- name: `?RegisterForImmersiveEvents@COSKKeyboardManager@@AEAAJXZ`
- size: `277`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400118d0`

## callees

- `0x14000df20`
- `0x14000facc`
- `0x140012c54`
- `0x140013f04`
- `0x140027010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140012c9b`
- `ole32!CoCreateInstance` at `0x140012c9b`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::RegisterForImmersiveEvents(COSKKeyboardManager *this)
{
  unsigned int v1; // ebx
  _DWORD *v2; // r14
  struct IUnknown **v4; // rdi
  HRESULT Instance; // eax
  struct IUnknown *v6; // rdx
  PVOID *v7; // rcx
  __int64 v8; // rdx

  v1 = 0;
  v2 = (_DWORD *)((char *)this + 260);
  if ( *((_DWORD *)this + 65) )
    goto LABEL_14;
  v4 = (struct IUnknown **)((char *)this + 264);
  Instance = CoCreateInstance(
               &CLSID_AppVisibility,
               0,
               3u,
               &GUID_2246ea2d_caea_4444_a3c4_6de827e44313,
               (LPVOID *)this + 33);
  v1 = Instance;
  if ( Instance < 0 )
  {
    if ( Instance == -2147221164 )
    {
      v1 = 0;
      if ( *v4 )
        ATL::AtlComPtrAssign(v4, v6);
      goto LABEL_14;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v8 = 11;
    goto LABEL_13;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _DWORD *))(*v4)->lpVtbl[1].Release)(
               *v4,
               ((unsigned __int64)this + 8) & -(__int64)(this != 0),
               v2);
  v1 = Instance;
  if ( Instance >= 0 )
  {
LABEL_14:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 10;
LABEL_13:
    WPP_SF_d(v7[2], v8, &WPP_9329afad6021354e5db6dcc45420c377_Traceguids, (unsigned int)Instance);
    goto LABEL_14;
  }
LABEL_15:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_Dd(v7[2], 12, &WPP_9329afad6021354e5db6dcc45420c377_Traceguids, v1, *v2);
  return v1;
}

```

## disassembly

```asm
0x140012c54  push    rbx
0x140012c56  push    rbp
0x140012c57  push    rsi
0x140012c58  push    rdi
0x140012c59  push    r14
0x140012c5b  sub     rsp, 30h
0x140012c5f  xor     ebx, ebx
0x140012c61  lea     r14, [rcx+104h]
0x140012c68  lea     rbp, WPP_GLOBAL_Control
0x140012c6f  mov     rsi, rcx
0x140012c72  cmp     [r14], ebx
0x140012c75  jnz     loc_140012D2B
0x140012c7b  lea     rdi, [rcx+108h]
0x140012c82  xor     edx, edx; pUnkOuter
0x140012c84  lea     rcx, CLSID_AppVisibility; rclsid
0x140012c8b  mov     [rsp+58h+ppv], rdi; ppv
0x140012c90  lea     r9, _GUID_2246ea2d_caea_4444_a3c4_6de827e44313; riid
0x140012c97  lea     r8d, [rbx+3]; dwClsContext
0x140012c9b  call    cs:__imp_CoCreateInstance
0x140012ca1  mov     ebx, eax
0x140012ca3  test    eax, eax
0x140012ca5  js      short loc_140012CE9
0x140012ca7  mov     rcx, [rdi]
0x140012caa  lea     rax, [rsi+8]
0x140012cae  neg     rsi
0x140012cb1  mov     r8, r14
0x140012cb4  sbb     rdx, rdx
0x140012cb7  mov     r9, [rcx]
0x140012cba  and     rdx, rax
0x140012cbd  mov     rax, [r9+28h]
0x140012cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cc6  mov     ebx, eax
0x140012cc8  test    eax, eax
0x140012cca  jns     short loc_140012D2B
0x140012ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x140012cd3  cmp     rcx, rbp
0x140012cd6  jz      loc_140012D5C
0x140012cdc  test    byte ptr [rcx+1Ch], 1
0x140012ce0  jz      short loc_140012D32
0x140012ce2  mov     edx, 0Ah
0x140012ce7  jmp     short loc_140012D18
0x140012ce9  cmp     eax, 80040154h
0x140012cee  jnz     short loc_140012D01
0x140012cf0  xor     ebx, ebx
0x140012cf2  cmp     [rdi], rbx
0x140012cf5  jz      short loc_140012D2B
0x140012cf7  mov     rcx, rdi; struct IUnknown **
0x140012cfa  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140012cff  jmp     short loc_140012D2B
0x140012d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d08  cmp     rcx, rbp
0x140012d0b  jz      short loc_140012D5C
0x140012d0d  test    byte ptr [rcx+1Ch], 1
0x140012d11  jz      short loc_140012D32
0x140012d13  mov     edx, 0Bh
0x140012d18  mov     rcx, [rcx+10h]
0x140012d1c  lea     r8, WPP_9329afad6021354e5db6dcc45420c377_Traceguids
0x140012d23  mov     r9d, eax
0x140012d26  call    WPP_SF_d
0x140012d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d32  cmp     rcx, rbp
0x140012d35  jz      short loc_140012D5C
0x140012d37  test    byte ptr [rcx+1Ch], 10h
0x140012d3b  jz      short loc_140012D5C
0x140012d3d  mov     eax, [r14]
0x140012d40  lea     r8, WPP_9329afad6021354e5db6dcc45420c377_Traceguids
0x140012d47  mov     rcx, [rcx+10h]
0x140012d4b  mov     edx, 0Ch
0x140012d50  mov     r9d, ebx
0x140012d53  mov     dword ptr [rsp+58h+ppv], eax
0x140012d57  call    WPP_SF_Dd
0x140012d5c  mov     eax, ebx
0x140012d5e  add     rsp, 30h
0x140012d62  pop     r14
0x140012d64  pop     rdi
0x140012d65  pop     rsi
0x140012d66  pop     rbp
0x140012d67  pop     rbx
0x140012d68  retn
```
