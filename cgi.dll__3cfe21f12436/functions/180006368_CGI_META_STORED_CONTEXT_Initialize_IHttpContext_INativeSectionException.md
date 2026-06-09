# CGI_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180006368`
- end: `0x1800065bf`
- name: `?Initialize@CGI_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(CGI_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800065c8`

## callees

- `0x180006368`
- `0x180008010`

## string_xrefs

- `0x180006435`: `createCGIWithNewConsole`
- `0x180006462`: `createProcessAsUser`
- `0x180006521`: `accessPolicy`

## pseudocode

```c
__int64 __fastcall CGI_META_STORED_CONTEXT::Initialize(
        CGI_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // [rsp+40h] [rbp-10h] BYREF
  __int64 v14; // [rsp+48h] [rbp-8h] BYREF
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v14 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v13);
  if ( v10 < 0 )
    goto LABEL_9;
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v13 + 24LL))(
          v13,
          L"system.webServer/cgi",
          v8,
          &v15,
          a3,
          0);
  if ( v10 < 0 )
    goto LABEL_9;
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
          v15,
          L"createCGIWithNewConsole",
          (char *)this + 8,
          0,
          0);
  if ( v10 < 0 )
    goto LABEL_9;
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
          v15,
          L"createProcessAsUser",
          (char *)this + 12,
          0,
          0);
  if ( v10 < 0
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v15 + 80LL))(
                v15,
                L"timeout",
                &v14,
                0,
                0),
        v10 < 0)
    || (v11 = v15,
        *((_DWORD *)this + 4) = v14 / 10000000,
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11),
        v15 = 0,
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v13 + 24LL))(
                v13,
                L"system.webServer/handlers",
                v8,
                &v16,
                a3,
                0),
        v10 < 0)
    || (v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 48LL))(
                v16,
                L"accessPolicy",
                (char *)this + 20,
                0,
                0),
        v10 < 0) )
  {
LABEL_9:
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v16 = 0;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)v10;
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180006368  mov     [rsp-28h+arg_0], rbx
0x18000636d  push    rbp
0x18000636e  push    rsi
0x18000636f  push    rdi
0x180006370  push    r14
0x180006372  push    r15
0x180006374  mov     rbp, rsp
0x180006377  sub     rsp, 50h
0x18000637b  mov     rax, [rdx]
0x18000637e  xor     r15d, r15d
0x180006381  mov     rdi, rcx
0x180006384  mov     [rbp+var_10], r15
0x180006388  mov     rcx, rdx
0x18000638b  mov     [rbp+arg_8], r15
0x18000638f  mov     rsi, r8
0x180006392  mov     [rbp+arg_18], r15
0x180006396  mov     rax, [rax+0A0h]
0x18000639d  mov     [rbp+var_8], r15
0x1800063a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a6  mov     rdx, rax
0x1800063a9  mov     rcx, [rax]
0x1800063ac  mov     rax, [rcx]
0x1800063af  mov     rcx, rdx
0x1800063b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b7  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800063be  mov     r14, rax
0x1800063c1  mov     rdx, [rcx]
0x1800063c4  mov     rax, [rdx+38h]
0x1800063c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063cd  mov     r9, rax
0x1800063d0  lea     r8, [rbp+var_10]
0x1800063d4  lea     rdx, IID_INativeConfigurationSystem
0x1800063db  mov     rcx, [rax]
0x1800063de  mov     rax, [rcx]
0x1800063e1  mov     rcx, r9
0x1800063e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e9  mov     ebx, eax
0x1800063eb  test    eax, eax
0x1800063ed  js      loc_180006562
0x1800063f3  mov     rcx, [rbp+var_10]
0x1800063f7  lea     r9, [rbp+arg_8]
0x1800063fb  mov     [rsp+50h+var_28], r15
0x180006400  lea     rdx, aSystemWebserve_0; "system.webServer/cgi"
0x180006407  mov     r8, r14
0x18000640a  mov     [rsp+50h+var_30], rsi
0x18000640f  mov     rax, [rcx]
0x180006412  mov     rax, [rax+18h]
0x180006416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641b  mov     ebx, eax
0x18000641d  test    eax, eax
0x18000641f  js      loc_180006562
0x180006425  mov     rcx, [rbp+arg_8]
0x180006429  lea     r8, [rdi+8]
0x18000642d  xor     r9d, r9d
0x180006430  mov     [rsp+50h+var_30], r15
0x180006435  lea     rdx, aCreatecgiwithn; "createCGIWithNewConsole"
0x18000643c  mov     rax, [rcx]
0x18000643f  mov     rax, [rax+48h]
0x180006443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006448  mov     ebx, eax
0x18000644a  test    eax, eax
0x18000644c  js      loc_180006562
0x180006452  mov     rcx, [rbp+arg_8]
0x180006456  lea     r8, [rdi+0Ch]
0x18000645a  xor     r9d, r9d
0x18000645d  mov     [rsp+50h+var_30], r15
0x180006462  lea     rdx, aCreateprocessa; "createProcessAsUser"
0x180006469  mov     rax, [rcx]
0x18000646c  mov     rax, [rax+48h]
0x180006470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006475  mov     ebx, eax
0x180006477  test    eax, eax
0x180006479  js      loc_180006562
0x18000647f  mov     rcx, [rbp+arg_8]
0x180006483  lea     r8, [rbp+var_8]
0x180006487  xor     r9d, r9d
0x18000648a  mov     [rsp+50h+var_30], r15
0x18000648f  lea     rdx, aTimeout; "timeout"
0x180006496  mov     rax, [rcx]
0x180006499  mov     rax, [rax+50h]
0x18000649d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a2  mov     ebx, eax
0x1800064a4  test    eax, eax
0x1800064a6  js      loc_180006562
0x1800064ac  mov     rcx, [rbp+arg_8]
0x1800064b0  mov     rax, 0D6BF94D5E57A42BDh
0x1800064ba  imul    [rbp+var_8]
0x1800064be  add     rdx, [rbp+var_8]
0x1800064c2  sar     rdx, 17h
0x1800064c6  mov     rax, rdx
0x1800064c9  shr     rax, 3Fh
0x1800064cd  add     rdx, rax
0x1800064d0  mov     [rdi+10h], edx
0x1800064d3  mov     rax, [rcx]
0x1800064d6  mov     rax, [rax+10h]
0x1800064da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064df  mov     rcx, [rbp+var_10]
0x1800064e3  lea     r9, [rbp+arg_18]
0x1800064e7  mov     [rbp+arg_8], r15
0x1800064eb  lea     rdx, aSystemWebserve_1; "system.webServer/handlers"
0x1800064f2  mov     [rsp+50h+var_28], r15
0x1800064f7  mov     r8, r14
0x1800064fa  mov     [rsp+50h+var_30], rsi
0x1800064ff  mov     rax, [rcx]
0x180006502  mov     rax, [rax+18h]
0x180006506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650b  mov     ebx, eax
0x18000650d  test    eax, eax
0x18000650f  js      short loc_180006562
0x180006511  mov     rcx, [rbp+arg_18]
0x180006515  lea     r8, [rdi+14h]
0x180006519  xor     r9d, r9d
0x18000651c  mov     [rsp+50h+var_30], r15
0x180006521  lea     rdx, aAccesspolicy; "accessPolicy"
0x180006528  mov     rax, [rcx]
0x18000652b  mov     rax, [rax+30h]
0x18000652f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006534  mov     ebx, eax
0x180006536  test    eax, eax
0x180006538  js      short loc_180006562
0x18000653a  mov     rcx, [rbp+arg_18]
0x18000653e  mov     rax, [rcx]
0x180006541  mov     rax, [rax+10h]
0x180006545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654a  mov     rcx, [rbp+var_10]
0x18000654e  mov     [rbp+arg_18], r15
0x180006552  mov     rax, [rcx]
0x180006555  mov     rax, [rax+10h]
0x180006559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655e  xor     eax, eax
0x180006560  jmp     short loc_1800065AB
0x180006562  mov     rcx, [rbp+arg_18]
0x180006566  test    rcx, rcx
0x180006569  jz      short loc_18000657B
0x18000656b  mov     rax, [rcx]
0x18000656e  mov     rax, [rax+10h]
0x180006572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006577  mov     [rbp+arg_18], r15
0x18000657b  mov     rcx, [rbp+arg_8]
0x18000657f  test    rcx, rcx
0x180006582  jz      short loc_180006594
0x180006584  mov     rax, [rcx]
0x180006587  mov     rax, [rax+10h]
0x18000658b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006590  mov     [rbp+arg_8], r15
0x180006594  mov     rcx, [rbp+var_10]
0x180006598  test    rcx, rcx
0x18000659b  jz      short loc_1800065A9
0x18000659d  mov     rax, [rcx]
0x1800065a0  mov     rax, [rax+10h]
0x1800065a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a9  mov     eax, ebx
0x1800065ab  mov     rbx, [rsp+50h+arg_0]
0x1800065b3  add     rsp, 50h
0x1800065b7  pop     r15
0x1800065b9  pop     r14
0x1800065bb  pop     rdi
0x1800065bc  pop     rsi
0x1800065bd  pop     rbp
0x1800065be  retn
```
