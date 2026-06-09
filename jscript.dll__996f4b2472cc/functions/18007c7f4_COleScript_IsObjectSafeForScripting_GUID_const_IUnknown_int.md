# COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)

- ea: `0x18007c7f4`
- end: `0x18007c97d`
- name: `?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `393`
- prototype: `_BOOL8 __fastcall(COleScript *this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800789d4`

## callees

- `0x18007c7f4`
- `0x18007ee54`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18007c8b6`
- `ole32!CoCreateInstance` at `0x18007c8b6`

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
0x18007c7f4  mov     [rsp-18h+arg_0], rbx
0x18007c7f9  push    rbp
0x18007c7fa  push    rsi
0x18007c7fb  push    rdi
0x18007c7fc  mov     rbp, rsp
0x18007c7ff  sub     rsp, 70h
0x18007c803  mov     rax, cs:__security_cookie
0x18007c80a  xor     rax, rsp
0x18007c80d  mov     [rbp+var_10], rax
0x18007c811  mov     rax, [r8]
0x18007c814  mov     rcx, r8
0x18007c817  mov     rsi, rdx
0x18007c81a  mov     [rbp+var_30], 0
0x18007c822  lea     r8, [rbp+var_30]
0x18007c826  mov     edi, r9d
0x18007c829  lea     rdx, IID_IObjectSafety
0x18007c830  mov     rax, [rax]
0x18007c833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c838  mov     ebx, 1
0x18007c83d  test    eax, eax
0x18007c83f  js      short loc_18007C892
0x18007c841  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x18007c845  lea     r8, GUID_NULL; struct _GUID *
0x18007c84c  neg     edi
0x18007c84e  sbb     edi, edi
0x18007c850  and     edi, 2
0x18007c853  add     edi, ebx
0x18007c855  mov     r9d, edi; unsigned int
0x18007c858  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x18007c85c  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x18007c861  test    eax, eax
0x18007c863  jns     short loc_18007C882
0x18007c865  mov     rdx, [rbp+var_30]; struct IObjectSafety *
0x18007c869  lea     r8, IID_IDispatch; struct _GUID *
0x18007c870  mov     r9d, edi; unsigned int
0x18007c873  mov     dword ptr [rsp+70h+ppv], edi; unsigned int
0x18007c877  call    ?SetObjectSafety@COleScript@@IEAAJPEAUIObjectSafety@@AEBU_GUID@@KK@Z; COleScript::SetObjectSafety(IObjectSafety *,_GUID const &,ulong,ulong)
0x18007c87c  test    eax, eax
0x18007c87e  jns     short loc_18007C882
0x18007c880  xor     ebx, ebx
0x18007c882  mov     rcx, [rbp+var_30]
0x18007c886  mov     rax, [rcx]
0x18007c889  mov     rax, [rax+10h]
0x18007c88d  jmp     loc_18007C959
0x18007c892  lea     rax, [rbp+var_28]
0x18007c896  mov     [rbp+var_28], 0
0x18007c89e  lea     r9, IID_ICatInformation; riid
0x18007c8a5  mov     [rsp+70h+ppv], rax; ppv
0x18007c8aa  mov     r8d, ebx; dwClsContext
0x18007c8ad  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18007c8b4  xor     edx, edx; pUnkOuter
0x18007c8b6  call    cs:__imp_CoCreateInstance
0x18007c8bd  nop     dword ptr [rax+rax+00h]
0x18007c8c2  test    eax, eax
0x18007c8c4  jns     short loc_18007C8CD
0x18007c8c6  xor     eax, eax
0x18007c8c8  jmp     loc_18007C960
0x18007c8cd  movups  xmm0, xmmword ptr cs:CATID_SafeForScripting.Data1
0x18007c8d4  mov     rcx, [rbp+var_28]
0x18007c8d8  lea     r9, [rbp+var_20]
0x18007c8dc  mov     [rsp+70h+var_48], 0
0x18007c8e5  mov     r8d, ebx
0x18007c8e8  movdqu  [rbp+var_20], xmm0
0x18007c8ed  mov     rdx, rsi
0x18007c8f0  mov     dword ptr [rsp+70h+ppv], 0
0x18007c8f8  mov     rax, [rcx]
0x18007c8fb  mov     rax, [rax+30h]
0x18007c8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c904  test    eax, eax
0x18007c906  jnz     short loc_18007C94C
0x18007c908  test    edi, edi
0x18007c90a  jz      short loc_18007C94E
0x18007c90c  movups  xmm0, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x18007c913  mov     rcx, [rbp+var_28]
0x18007c917  lea     r9, [rbp+var_20]
0x18007c91b  mov     [rsp+70h+var_48], 0
0x18007c924  mov     r8d, ebx
0x18007c927  movdqu  [rbp+var_20], xmm0
0x18007c92c  mov     rdx, rsi
0x18007c92f  mov     dword ptr [rsp+70h+ppv], 0
0x18007c937  mov     rax, [rcx]
0x18007c93a  mov     rax, [rax+30h]
0x18007c93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c943  xor     ebx, ebx
0x18007c945  test    eax, eax
0x18007c947  setz    bl
0x18007c94a  jmp     short loc_18007C94E
0x18007c94c  xor     ebx, ebx
0x18007c94e  mov     rcx, [rbp+var_28]
0x18007c952  mov     rdx, [rcx]
0x18007c955  mov     rax, [rdx+10h]
0x18007c959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c95e  mov     eax, ebx
0x18007c960  mov     rcx, [rbp+var_10]
0x18007c964  xor     rcx, rsp; StackCookie
0x18007c967  call    __security_check_cookie
0x18007c96c  mov     rbx, [rsp+70h+arg_0]
0x18007c974  add     rsp, 70h
0x18007c978  pop     rdi
0x18007c979  pop     rsi
0x18007c97a  pop     rbp
0x18007c97b  retn
```
