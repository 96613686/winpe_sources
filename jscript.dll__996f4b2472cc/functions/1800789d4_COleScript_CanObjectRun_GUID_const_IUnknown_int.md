# COleScript::CanObjectRun(_GUID const &,IUnknown *,int)

- ea: `0x1800789d4`
- end: `0x180078b23`
- name: `?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800520c0`

## callees

- `0x18004d3ec`
- `0x1800789d4`
- `0x18007c4ac`
- `0x18007c7f4`
- `0x18007f918`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180078ae0`
- `ole32!CoTaskMemFree` at `0x180078ae0`

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
0x1800789d4  push    rbp
0x1800789d6  push    rbx
0x1800789d7  push    rsi
0x1800789d8  push    rdi
0x1800789d9  push    r14
0x1800789db  mov     rbp, rsp
0x1800789de  sub     rsp, 80h
0x1800789e5  mov     rax, cs:__security_cookie
0x1800789ec  xor     rax, rsp
0x1800789ef  mov     [rbp+var_8], rax
0x1800789f3  mov     r14d, r9d
0x1800789f6  mov     rsi, r8
0x1800789f9  mov     rbx, rdx
0x1800789fc  mov     rdi, rcx
0x1800789ff  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180078a04  test    eax, eax
0x180078a06  jnz     short loc_180078A12
0x180078a08  mov     eax, 1
0x180078a0d  jmp     loc_180078B08
0x180078a12  test    byte ptr [rdi+2E0h], 8
0x180078a19  jz      loc_180078AFA
0x180078a1f  lea     rdx, [rbp+var_38]; struct IInternetHostSecurityManager **
0x180078a23  mov     [rbp+var_38], 0
0x180078a2b  mov     rcx, rdi; this
0x180078a2e  call    ?GetSiteHostSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetHostSecurityManager@@@Z; COleScript::GetSiteHostSecurityManagerNoRef(IInternetHostSecurityManager * *)
0x180078a33  test    eax, eax
0x180078a35  js      loc_180078AF6
0x180078a3b  mov     rdi, [rbp+var_38]
0x180078a3f  mov     r8, rbx; struct _GUID *
0x180078a42  mov     rdx, rdi; struct IInternetHostSecurityManager *
0x180078a45  call    ?VerifyHostSecurityManager@COleScript@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z; COleScript::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)
0x180078a4a  test    eax, eax
0x180078a4c  jz      loc_180078AF6
0x180078a52  movups  xmm0, xmmword ptr [rbx]
0x180078a55  xor     eax, eax
0x180078a57  mov     qword ptr [rbp+var_28], 0
0x180078a5f  mov     qword ptr [rbp+var_28+8], 0
0x180078a67  lea     rcx, [rbp+var_28]
0x180078a6b  mov     [rbp+var_C], 0
0x180078a72  lea     r9, [rbp+var_40]
0x180078a76  mov     [rbp+pv], 0
0x180078a7e  lea     r8, [rbp+pv]
0x180078a82  mov     [rbp+var_40], 0
0x180078a89  lea     rdx, GUID_CUSTOM_CONFIRMOBJECTSAFETY
0x180078a90  movdqu  [rbp+var_28], xmm0
0x180078a95  mov     [rbp+var_18], rsi
0x180078a99  test    r14d, r14d
0x180078a9c  mov     [rsp+80h+var_50], 0
0x180078aa4  setnz   al
0x180078aa7  mov     [rsp+80h+var_58], 20h ; ' '
0x180078aaf  mov     [rbp+var_10], eax
0x180078ab2  mov     rax, [rdi]
0x180078ab5  mov     [rsp+80h+var_60], rcx
0x180078aba  mov     rcx, rdi
0x180078abd  mov     rax, [rax+28h]
0x180078ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ac6  test    eax, eax
0x180078ac8  js      short loc_180078AF6
0x180078aca  mov     rcx, [rbp+pv]; pv
0x180078ace  mov     ebx, 3
0x180078ad3  test    rcx, rcx
0x180078ad6  jz      short loc_180078AEC
0x180078ad8  cmp     [rbp+var_40], 4
0x180078adc  jb      short loc_180078AE0
0x180078ade  mov     ebx, [rcx]
0x180078ae0  call    cs:__imp_CoTaskMemFree
0x180078ae7  nop     dword ptr [rax+rax+00h]
0x180078aec  xor     eax, eax
0x180078aee  test    bl, 0Fh
0x180078af1  setz    al
0x180078af4  jmp     short loc_180078B08
0x180078af6  xor     eax, eax
0x180078af8  jmp     short loc_180078B08
0x180078afa  mov     r9d, r14d; int
0x180078afd  mov     r8, rsi; struct IUnknown *
0x180078b00  mov     rdx, rbx; struct _GUID *
0x180078b03  call    ?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)
0x180078b08  mov     rcx, [rbp+var_8]
0x180078b0c  xor     rcx, rsp; StackCookie
0x180078b0f  call    __security_check_cookie
0x180078b14  add     rsp, 80h
0x180078b1b  pop     r14
0x180078b1d  pop     rdi
0x180078b1e  pop     rsi
0x180078b1f  pop     rbx
0x180078b20  pop     rbp
0x180078b21  retn
```
