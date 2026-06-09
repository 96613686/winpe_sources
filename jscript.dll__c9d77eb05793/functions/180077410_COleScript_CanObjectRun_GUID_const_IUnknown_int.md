# COleScript::CanObjectRun(_GUID const &,IUnknown *,int)

- ea: `0x180077410`
- end: `0x180077558`
- name: `?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `328`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800513a8`

## callees

- `0x18004c72c`
- `0x180077410`
- `0x18007acd4`
- `0x18007afec`
- `0x18007dfb8`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007751c`
- `ole32!CoTaskMemFree` at `0x18007751c`

## pseudocode

```c
__int64 __fastcall COleScript::CanObjectRun(COleScript *this, const struct _GUID *a2, struct IUnknown *a3, int a4)
{
  COleScript *v8; // rcx
  COleScript *v10; // rcx
  struct IInternetHostSecurityManager *v11; // rdi
  struct _GUID v12; // xmm0
  int v13; // ebx
  unsigned int v14; // [rsp+40h] [rbp-40h] BYREF
  struct IInternetHostSecurityManager *v15; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+68h] [rbp-18h]
  BOOL v19; // [rsp+70h] [rbp-10h]
  int v20; // [rsp+74h] [rbp-Ch]

  if ( !(unsigned int)COleScript::InSafeMode(this, a2) )
    return 1;
  if ( (*((_BYTE *)this + 736) & 8) == 0 )
    return COleScript::IsObjectSafeForScripting(v8, a2, a3, a4);
  v15 = 0;
  if ( (int)COleScript::GetSiteHostSecurityManagerNoRef(this, &v15) < 0 )
    return 0;
  v11 = v15;
  if ( !(unsigned int)COleScript::VerifyHostSecurityManager(v10, v15, a2) )
    return 0;
  v12 = *a2;
  v20 = 0;
  pv = 0;
  v14 = 0;
  v17 = v12;
  v18 = a3;
  v19 = a4 != 0;
  if ( ((int (__fastcall *)(struct IInternetHostSecurityManager *, GUID *, LPVOID *, unsigned int *, struct _GUID *, int, _DWORD))v11->lpVtbl->QueryCustomPolicy)(
         v11,
         &GUID_CUSTOM_CONFIRMOBJECTSAFETY,
         &pv,
         &v14,
         &v17,
         32,
         0) < 0 )
    return 0;
  LOBYTE(v13) = 3;
  if ( pv )
  {
    if ( v14 >= 4 )
      v13 = *(_DWORD *)pv;
    CoTaskMemFree(pv);
  }
  return (v13 & 0xF) == 0;
}

```

## disassembly

```asm
0x180077410  push    rbp
0x180077412  push    rbx
0x180077413  push    rsi
0x180077414  push    rdi
0x180077415  push    r14
0x180077417  mov     rbp, rsp
0x18007741a  sub     rsp, 80h
0x180077421  mov     rax, cs:__security_cookie
0x180077428  xor     rax, rsp
0x18007742b  mov     [rbp+var_8], rax
0x18007742f  mov     r14d, r9d
0x180077432  mov     rsi, r8
0x180077435  mov     rbx, rdx
0x180077438  mov     rdi, rcx
0x18007743b  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180077440  test    eax, eax
0x180077442  jnz     short loc_18007744E
0x180077444  mov     eax, 1
0x180077449  jmp     loc_18007753E
0x18007744e  test    byte ptr [rdi+2E0h], 8
0x180077455  jz      loc_180077530
0x18007745b  lea     rdx, [rbp+var_38]; struct IInternetHostSecurityManager **
0x18007745f  mov     [rbp+var_38], 0
0x180077467  mov     rcx, rdi; this
0x18007746a  call    ?GetSiteHostSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetHostSecurityManager@@@Z; COleScript::GetSiteHostSecurityManagerNoRef(IInternetHostSecurityManager * *)
0x18007746f  test    eax, eax
0x180077471  js      loc_18007752C
0x180077477  mov     rdi, [rbp+var_38]
0x18007747b  mov     r8, rbx; struct _GUID *
0x18007747e  mov     rdx, rdi; struct IInternetHostSecurityManager *
0x180077481  call    ?VerifyHostSecurityManager@COleScript@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z; COleScript::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)
0x180077486  test    eax, eax
0x180077488  jz      loc_18007752C
0x18007748e  movups  xmm0, xmmword ptr [rbx]
0x180077491  xor     eax, eax
0x180077493  mov     qword ptr [rbp+var_28], 0
0x18007749b  mov     qword ptr [rbp+var_28+8], 0
0x1800774a3  lea     rcx, [rbp+var_28]
0x1800774a7  mov     [rbp+var_C], 0
0x1800774ae  lea     r9, [rbp+var_40]
0x1800774b2  mov     [rbp+pv], 0
0x1800774ba  lea     r8, [rbp+pv]
0x1800774be  mov     [rbp+var_40], 0
0x1800774c5  lea     rdx, GUID_CUSTOM_CONFIRMOBJECTSAFETY
0x1800774cc  movdqu  [rbp+var_28], xmm0
0x1800774d1  mov     [rbp+var_18], rsi
0x1800774d5  test    r14d, r14d
0x1800774d8  mov     [rsp+80h+var_50], 0
0x1800774e0  setnz   al
0x1800774e3  mov     [rsp+80h+var_58], 20h ; ' '
0x1800774eb  mov     [rbp+var_10], eax
0x1800774ee  mov     rax, [rdi]
0x1800774f1  mov     [rsp+80h+var_60], rcx
0x1800774f6  mov     rcx, rdi
0x1800774f9  mov     rax, [rax+28h]
0x1800774fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077502  test    eax, eax
0x180077504  js      short loc_18007752C
0x180077506  mov     rcx, [rbp+pv]; pv
0x18007750a  mov     ebx, 3
0x18007750f  test    rcx, rcx
0x180077512  jz      short loc_180077522
0x180077514  cmp     [rbp+var_40], 4
0x180077518  jb      short loc_18007751C
0x18007751a  mov     ebx, [rcx]
0x18007751c  call    cs:__imp_CoTaskMemFree
0x180077522  xor     eax, eax
0x180077524  test    bl, 0Fh
0x180077527  setz    al
0x18007752a  jmp     short loc_18007753E
0x18007752c  xor     eax, eax
0x18007752e  jmp     short loc_18007753E
0x180077530  mov     r9d, r14d; int
0x180077533  mov     r8, rsi; struct IUnknown *
0x180077536  mov     rdx, rbx; struct _GUID *
0x180077539  call    ?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)
0x18007753e  mov     rcx, [rbp+var_8]
0x180077542  xor     rcx, rsp; StackCookie
0x180077545  call    __security_check_cookie
0x18007754a  add     rsp, 80h
0x180077551  pop     r14
0x180077553  pop     rdi
0x180077554  pop     rsi
0x180077555  pop     rbx
0x180077556  pop     rbp
0x180077557  retn
```
