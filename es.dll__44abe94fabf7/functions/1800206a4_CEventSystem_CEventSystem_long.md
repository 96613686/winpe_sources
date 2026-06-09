# CEventSystem::CEventSystem(long &)

- ea: `0x1800206a4`
- end: `0x180020953`
- name: `??0CEventSystem@@QEAA@AEAJ@Z`
- size: `687`
- prototype: `CEventSystem *__fastcall(CEventSystem *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020620`

## callees

- `0x180003d54`
- `0x1800206a4`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020700`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180020787`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180020787`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180020863`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800208e4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180020863`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800208e4`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180020813`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180020898`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180020813`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180020898`

## string_xrefs

- `0x180020905`: `com\complus\src\events\Shared\StringFuncs.h`

## pseudocode

```c
CEventSystem *__fastcall CEventSystem::CEventSystem(CEventSystem *this, int *a2)
{
  _OWORD *v4; // rbx
  HRESULT ClassObject; // ebx
  HRESULT v7; // eax
  IUnknown *v8; // rcx
  HRESULT v9; // eax
  IUnknown *v10; // rcx
  IUnknown *ppv; // [rsp+70h] [rbp+30h] BYREF
  IUnknown *pProxy; // [rsp+80h] [rbp+40h] BYREF
  IUnknown *ppCopy; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)this = &CEventSystem::`vftable'{for `IEventSystem2'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 1) = &CEventSystem::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = &CEventSystem::`vftable'{for `IEventSystemInitialize'};
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_WORD *)this + 30) = 0;
  _InterlockedIncrement(&g_tier1ActiveObjects);
  v4 = CoTaskMemAlloc(0x4Eu);
  if ( !v4 )
    InternalError(L"com\\complus\\src\\events\\Shared\\StringFuncs.h", 0x13u, 0xC0001204, 0x10u);
  *v4 = *(_OWORD *)L"{26c409cc-ae86-11d1-b616-00805fc79216}";
  v4[1] = *(_OWORD *)L"c-ae86-11d1-b616-00805fc79216}";
  v4[2] = *(_OWORD *)L"1d1-b616-00805fc79216}";
  v4[3] = *(_OWORD *)L"-00805fc79216}";
  *(_OWORD *)((char *)v4 + 62) = *(_OWORD *)L"c79216}";
  *((_QWORD *)this + 4) = v4;
  if ( !v4 )
  {
    ClassObject = -2147024882;
    goto LABEL_6;
  }
  ppv = 0;
  pProxy = 0;
  ClassObject = CoGetClassObject(
                  &CLSID_CEventSystemTier2,
                  g_fRunningASService != 0 ? 1 : 4,
                  0,
                  &GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af,
                  (LPVOID *)&ppv);
  if ( ClassObject >= 0 )
  {
    if ( g_fRunningASService )
    {
LABEL_8:
      ClassObject = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, GUID *, IUnknown **))ppv->lpVtbl[1].Release)(
                      ppv,
                      L"{26c409cc-ae86-11d1-b616-00805fc79216}",
                      &IID_IEventSystemTier2,
                      &pProxy);
      ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
      ppv = 0;
      if ( ClassObject < 0 || g_fRunningASService )
        goto LABEL_5;
      ppCopy = 0;
      v7 = CoCopyProxy(pProxy, &ppCopy);
      ClassObject = v7;
      if ( v7 < 0 )
      {
        if ( v7 == -2147467262 )
        {
          ClassObject = 0;
          goto LABEL_5;
        }
      }
      else
      {
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        v8 = ppCopy;
        pProxy = ppCopy;
        ppCopy = 0;
        ClassObject = CoSetProxyBlanket(
                        v8,
                        0xFFFFFFFF,
                        0xFFFFFFFF,
                        (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                        0,
                        3u,
                        (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                        0x40u);
        if ( ClassObject >= 0 )
          goto LABEL_5;
      }
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      pProxy = 0;
      goto LABEL_5;
    }
    ppCopy = 0;
    v9 = CoCopyProxy(ppv, &ppCopy);
    ClassObject = v9;
    if ( v9 < 0 )
    {
      if ( v9 == -2147467262 )
        goto LABEL_8;
    }
    else
    {
      ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
      v10 = ppCopy;
      ppv = ppCopy;
      ppCopy = 0;
      ClassObject = CoSetProxyBlanket(
                      v10,
                      0xFFFFFFFF,
                      0xFFFFFFFF,
                      (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                      0,
                      2u,
                      (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                      0x800u);
      if ( ClassObject >= 0 )
        goto LABEL_8;
    }
    ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
  }
LABEL_5:
  *((_QWORD *)this + 3) = pProxy;
LABEL_6:
  *a2 = ClassObject;
  return this;
}

```

## disassembly

```asm
0x1800206a4  mov     [rsp-28h+arg_8], rbx
0x1800206a9  push    rbp
0x1800206aa  push    rsi
0x1800206ab  push    rdi
0x1800206ac  push    r12
0x1800206ae  push    r14
0x1800206b0  mov     rbp, rsp
0x1800206b3  sub     rsp, 40h
0x1800206b7  xor     r14d, r14d
0x1800206ba  lea     rax, ??_7CEventSystem@@6BIEventSystem2@@@; const CEventSystem::`vftable'{for `IEventSystem2'}
0x1800206c1  mov     [rcx], rax
0x1800206c4  mov     rsi, rdx
0x1800206c7  lea     rax, ??_7CEventSystem@@6BISupportErrorInfo@@@; const CEventSystem::`vftable'{for `ISupportErrorInfo'}
0x1800206ce  mov     [rcx+18h], r14
0x1800206d2  mov     [rcx+8], rax
0x1800206d6  mov     rdi, rcx
0x1800206d9  lea     rax, ??_7CEventSystem@@6BIEventSystemInitialize@@@; const CEventSystem::`vftable'{for `IEventSystemInitialize'}
0x1800206e0  mov     [rcx+20h], r14
0x1800206e4  mov     [rcx+10h], rax
0x1800206e8  mov     [rcx+30h], r14
0x1800206ec  mov     [rcx+38h], r14d
0x1800206f0  mov     [rcx+3Ch], r14w
0x1800206f5  lock inc cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x1800206fc  lea     ecx, [r14+4Eh]; cb
0x180020700  call    cs:__imp_CoTaskMemAlloc
0x180020706  mov     rbx, rax
0x180020709  test    rax, rax
0x18002070c  jz      loc_180020900
0x180020712  movaps  xmm0, xmmword ptr cs:a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x180020719  movups  xmmword ptr [rbx], xmm0
0x18002071c  movaps  xmm1, xmmword ptr cs:a26c409ccAe8611+10h; "c-ae86-11d1-b616-00805fc79216}"
0x180020723  movups  xmmword ptr [rbx+10h], xmm1
0x180020727  movaps  xmm0, xmmword ptr cs:a26c409ccAe8611+20h; "1d1-b616-00805fc79216}"
0x18002072e  movups  xmmword ptr [rbx+20h], xmm0
0x180020732  movaps  xmm1, xmmword ptr cs:a26c409ccAe8611+30h; "-00805fc79216}"
0x180020739  movups  xmmword ptr [rbx+30h], xmm1
0x18002073d  movups  xmm0, xmmword ptr cs:a26c409ccAe8611+3Eh; "c79216}"
0x180020744  movups  xmmword ptr [rbx+3Eh], xmm0
0x180020748  mov     [rdi+20h], rbx
0x18002074c  test    rbx, rbx
0x18002074f  jz      loc_1800208F6
0x180020755  mov     eax, cs:g_fRunningASService
0x18002075b  lea     r9, _GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af; riid
0x180020762  neg     eax
0x180020764  mov     [rbp+arg_0], r14
0x180020768  lea     rax, [rbp+arg_0]
0x18002076c  mov     [rbp+pProxy], r14
0x180020770  sbb     edx, edx
0x180020772  mov     [rsp+40h+ppv], rax; ppv
0x180020777  and     edx, 0FFFFFFFDh
0x18002077a  lea     rcx, CLSID_CEventSystemTier2; rclsid
0x180020781  add     edx, 4; dwClsContext
0x180020784  xor     r8d, r8d; pvReserved
0x180020787  call    cs:__imp_CoGetClassObject
0x18002078d  mov     ebx, eax
0x18002078f  test    eax, eax
0x180020791  jns     short loc_1800207B1
0x180020793  mov     rax, [rbp+pProxy]
0x180020797  mov     [rdi+18h], rax
0x18002079b  mov     [rsi], ebx
0x18002079d  mov     rax, rdi
0x1800207a0  mov     rbx, [rsp+40h+arg_8]
0x1800207a5  add     rsp, 40h
0x1800207a9  pop     r14
0x1800207ab  pop     r12
0x1800207ad  pop     rdi
0x1800207ae  pop     rsi
0x1800207af  pop     rbp
0x1800207b0  retn
0x1800207b1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800207b5  cmp     cs:g_fRunningASService, r14d
0x1800207bc  jz      loc_18002088C
0x1800207c2  mov     rcx, [rbp+arg_0]
0x1800207c6  lea     r9, [rbp+pProxy]
0x1800207ca  lea     r8, IID_IEventSystemTier2
0x1800207d1  lea     rdx, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x1800207d8  mov     rax, [rcx]
0x1800207db  mov     rax, [rax+28h]
0x1800207df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207e4  mov     rcx, [rbp+arg_0]
0x1800207e8  mov     ebx, eax
0x1800207ea  mov     rax, [rcx]
0x1800207ed  mov     rax, [rax+10h]
0x1800207f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207f6  mov     [rbp+arg_0], r14
0x1800207fa  test    ebx, ebx
0x1800207fc  js      short loc_180020793
0x1800207fe  cmp     cs:g_fRunningASService, r14d
0x180020805  jnz     short loc_180020793
0x180020807  mov     rcx, [rbp+pProxy]; pProxy
0x18002080b  lea     rdx, [rbp+ppCopy]; ppCopy
0x18002080f  mov     [rbp+ppCopy], r14
0x180020813  call    cs:__imp_CoCopyProxy
0x180020819  mov     ebx, eax
0x18002081b  test    eax, eax
0x18002081d  js      loc_180020940
0x180020823  mov     rcx, [rbp+pProxy]
0x180020827  mov     rax, [rcx]
0x18002082a  mov     rax, [rax+10h]
0x18002082e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020833  mov     rcx, [rbp+ppCopy]; pProxy
0x180020837  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x18002083b  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180020843  or      edx, r8d; dwAuthnSvc
0x180020846  mov     [rsp+40h+pAuthInfo], r12; pAuthInfo
0x18002084b  mov     r9, r12; pServerPrincName
0x18002084e  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180020856  mov     [rbp+pProxy], rcx
0x18002085a  mov     [rbp+ppCopy], r14
0x18002085e  mov     dword ptr [rsp+40h+ppv], r14d; dwAuthnLevel
0x180020863  call    cs:__imp_CoSetProxyBlanket
0x180020869  mov     ebx, eax
0x18002086b  test    eax, eax
0x18002086d  jns     loc_180020793
0x180020873  mov     rcx, [rbp+pProxy]
0x180020877  mov     rax, [rcx]
0x18002087a  mov     rax, [rax+10h]
0x18002087e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020883  mov     [rbp+pProxy], r14
0x180020887  jmp     loc_180020793
0x18002088c  mov     rcx, [rbp+arg_0]; pProxy
0x180020890  lea     rdx, [rbp+ppCopy]; ppCopy
0x180020894  mov     [rbp+ppCopy], r14
0x180020898  call    cs:__imp_CoCopyProxy
0x18002089e  mov     ebx, eax
0x1800208a0  test    eax, eax
0x1800208a2  js      short loc_180020920
0x1800208a4  mov     rcx, [rbp+arg_0]
0x1800208a8  mov     rax, [rcx]
0x1800208ab  mov     rax, [rax+10h]
0x1800208af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208b4  mov     rcx, [rbp+ppCopy]; pProxy
0x1800208b8  or      r8d, 0FFFFFFFFh; dwAuthzSvc
0x1800208bc  mov     [rsp+40h+dwCapabilities], 800h; dwCapabilities
0x1800208c4  or      edx, r8d; dwAuthnSvc
0x1800208c7  mov     [rsp+40h+pAuthInfo], r12; pAuthInfo
0x1800208cc  mov     r9, r12; pServerPrincName
0x1800208cf  mov     [rsp+40h+dwImpLevel], 2; dwImpLevel
0x1800208d7  mov     [rbp+arg_0], rcx
0x1800208db  mov     [rbp+ppCopy], r14
0x1800208df  mov     dword ptr [rsp+40h+ppv], r14d; dwAuthnLevel
0x1800208e4  call    cs:__imp_CoSetProxyBlanket
0x1800208ea  mov     ebx, eax
0x1800208ec  test    eax, eax
0x1800208ee  jns     loc_1800207C2
0x1800208f4  jmp     short loc_18002092B
0x1800208f6  mov     ebx, 8007000Eh
0x1800208fb  jmp     loc_18002079B
0x180020900  mov     edx, 13h; unsigned int
0x180020905  lea     rcx, aComComplusSrcE_1; "com\\complus\\src\\events\\Shared\\Stri"...
0x18002090c  mov     r8d, 0C0001204h; unsigned int
0x180020912  lea     r9d, [rdx-3]; unsigned __int16
0x180020916  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18002091b  jmp     loc_180020712
0x180020920  cmp     eax, 80004002h
0x180020925  jz      loc_1800207C2
0x18002092b  mov     rcx, [rbp+arg_0]
0x18002092f  mov     rax, [rcx]
0x180020932  mov     rax, [rax+10h]
0x180020936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002093b  jmp     loc_180020793
0x180020940  cmp     eax, 80004002h
0x180020945  jnz     loc_180020873
0x18002094b  mov     ebx, r14d
0x18002094e  jmp     loc_180020793
```
