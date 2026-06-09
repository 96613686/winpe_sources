# COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)

- ea: `0x18007afec`
- end: `0x18007b16e`
- name: `?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `386`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180077410`

## callees

- `0x18007afec`
- `0x18007d530`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007b0ae`
- `ole32!CoCreateInstance` at `0x18007b0ae`

## pseudocode

```c
_BOOL8 __fastcall COleScript::IsObjectSafeForScripting(
        COleScript *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        int a4)
{
  struct IUnknownVtbl *lpVtbl; // rax
  COleScript *v7; // rcx
  BOOL v8; // ebx
  unsigned int v9; // edi
  COleScript *v10; // rcx
  void (*Release)(void); // rax
  struct IObjectSafety *v13; // [rsp+40h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  GUID v15; // [rsp+50h] [rbp-20h] BYREF

  lpVtbl = a3->lpVtbl;
  v13 = 0;
  v8 = 1;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IObjectSafety **))lpVtbl->QueryInterface)(
         a3,
         &IID_IObjectSafety,
         &v13) < 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatInformation, &ppv) < 0 )
      return 0;
    v15 = CATID_SafeForScripting;
    if ( (*(unsigned int (__fastcall **)(LPVOID, const struct _GUID *, __int64, GUID *, _DWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(
           ppv,
           a2,
           1,
           &v15,
           0,
           0) )
    {
      v8 = 0;
    }
    else if ( a4 )
    {
      v15 = CATID_SafeForInitializing;
      v8 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, GUID *, _DWORD, _QWORD))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a2,
             1,
             &v15,
             0,
             0) == 0;
    }
    Release = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
  }
  else
  {
    v9 = a4 != 0 ? 3 : 1;
    if ( (int)COleScript::SetObjectSafety(v7, v13, &GUID_NULL, v9, v9) < 0 )
      v8 = (int)COleScript::SetObjectSafety(v10, v13, &IID_IDispatch, v9, v9) >= 0;
    Release = (void (*)(void))v13->lpVtbl->Release;
  }
  Release();
  return v8;
}

```

## disassembly

```asm
0x18007afec  mov     [rsp-18h+arg_0], rbx
0x18007aff1  push    rbp
0x18007aff2  push    rsi
0x18007aff3  push    rdi
0x18007aff4  mov     rbp, rsp
0x18007aff7  sub     rsp, 70h
0x18007affb  mov     rax, cs:__security_cookie
0x18007b002  xor     rax, rsp
0x18007b005  mov     [rbp+var_10], rax
0x18007b009  mov     rax, [r8]
0x18007b00c  mov     rcx, r8
0x18007b00f  mov     rsi, rdx
0x18007b012  mov     [rbp+var_30], 0
0x18007b01a  lea     r8, [rbp+var_30]
0x18007b01e  mov     edi, r9d
0x18007b021  lea     rdx, IID_IObjectSafety
0x18007b028  mov     rax, [rax]
0x18007b02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b030  mov     ebx, 1
0x18007b035  test    eax, eax
0x18007b037  js      short loc_18007B08A
0x18007b039  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x18007b03d  lea     r8, GUID_NULL; struct _GUID *
0x18007b044  neg     edi
0x18007b046  sbb     edi, edi
0x18007b048  and     edi, 2
0x18007b04b  add     edi, ebx
0x18007b04d  mov     r9d, edi; unsigned int
0x18007b050  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x18007b054  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x18007b059  test    eax, eax
0x18007b05b  jns     short loc_18007B07A
0x18007b05d  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x18007b061  lea     r8, IID_IDispatch; struct _GUID *
0x18007b068  mov     r9d, edi; unsigned int
0x18007b06b  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x18007b06f  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x18007b074  test    eax, eax
0x18007b076  jns     short loc_18007B07A
0x18007b078  xor     ebx, ebx
0x18007b07a  mov     rcx, [rbp+var_30]
0x18007b07e  mov     rax, [rcx]
0x18007b081  mov     rax, [rax+10h]
0x18007b085  jmp     loc_18007B14B
0x18007b08a  lea     rax, [rbp+var_28]
0x18007b08e  mov     [rbp+var_28], 0
0x18007b096  lea     r9, IID_ICatInformation; riid
0x18007b09d  mov     [rsp+70h+ppv], rax; ppv
0x18007b0a2  mov     r8d, ebx; dwClsContext
0x18007b0a5  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007b0ac  xor     edx, edx; pUnkOuter
0x18007b0ae  call    cs:__imp_CoCreateInstance
0x18007b0b4  test    eax, eax
0x18007b0b6  jns     short loc_18007B0BF
0x18007b0b8  xor     eax, eax
0x18007b0ba  jmp     loc_18007B152
0x18007b0bf  movups  xmm0, xmmword ptr cs:CATID_SafeForScripting.Data1
0x18007b0c6  mov     rcx, [rbp+var_28]
0x18007b0ca  lea     r9, [rbp+var_20]
0x18007b0ce  mov     [rsp+70h+var_48], 0
0x18007b0d7  mov     r8d, ebx
0x18007b0da  movdqu  [rbp+var_20], xmm0
0x18007b0df  mov     rdx, rsi
0x18007b0e2  mov     dword ptr [rsp+70h+ppv], 0
0x18007b0ea  mov     rax, [rcx]
0x18007b0ed  mov     rax, [rax+30h]
0x18007b0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b0f6  test    eax, eax
0x18007b0f8  jnz     short loc_18007B13E
0x18007b0fa  test    edi, edi
0x18007b0fc  jz      short loc_18007B140
0x18007b0fe  movups  xmm0, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x18007b105  mov     rcx, [rbp+var_28]
0x18007b109  lea     r9, [rbp+var_20]
0x18007b10d  mov     [rsp+70h+var_48], 0
0x18007b116  mov     r8d, ebx
0x18007b119  movdqu  [rbp+var_20], xmm0
0x18007b11e  mov     rdx, rsi
0x18007b121  mov     dword ptr [rsp+70h+ppv], 0
0x18007b129  mov     rax, [rcx]
0x18007b12c  mov     rax, [rax+30h]
0x18007b130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b135  xor     ebx, ebx
0x18007b137  test    eax, eax
0x18007b139  setz    bl
0x18007b13c  jmp     short loc_18007B140
0x18007b13e  xor     ebx, ebx
0x18007b140  mov     rcx, [rbp+var_28]
0x18007b144  mov     rdx, [rcx]
0x18007b147  mov     rax, [rdx+10h]
0x18007b14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b150  mov     eax, ebx
0x18007b152  mov     rcx, [rbp+var_10]
0x18007b156  xor     rcx, rsp; StackCookie
0x18007b159  call    __security_check_cookie
0x18007b15e  mov     rbx, [rsp+70h+arg_0]
0x18007b166  add     rsp, 70h
0x18007b16a  pop     rdi
0x18007b16b  pop     rsi
0x18007b16c  pop     rbp
0x18007b16d  retn
```
