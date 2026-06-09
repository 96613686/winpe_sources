# EventClassSaver::Save(void)

- ea: `0x1800481e0`
- end: `0x18004884b`
- name: `?Save@EventClassSaver@@UEAAJXZ`
- size: `1643`
- prototype: `__int64 __fastcall(EventClassSaver *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800481e0`
- `0x180049800`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048294`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048294`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180048337`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004861e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004878a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180048337`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004861e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004878a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004825d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004825d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800482a4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800482a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048255`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048246`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048230`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048230`
- `OLEAUT32!__imp_SysAllocString` at `0x180048345`
- `OLEAUT32!__imp_SysAllocString` at `0x1800483cd`
- `OLEAUT32!__imp_SysAllocString` at `0x18004845b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800484ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18004857d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004862c`
- `OLEAUT32!__imp_SysAllocString` at `0x180048798`
- `OLEAUT32!__imp_SysAllocString` at `0x180048345`
- `OLEAUT32!__imp_SysAllocString` at `0x1800483cd`
- `OLEAUT32!__imp_SysAllocString` at `0x18004845b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800484ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18004857d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004862c`
- `OLEAUT32!__imp_SysAllocString` at `0x180048798`
- `OLEAUT32!__imp_SysFreeString` at `0x180048381`
- `OLEAUT32!__imp_SysFreeString` at `0x18004840f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800484a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180048531`
- `OLEAUT32!__imp_SysFreeString` at `0x1800485c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180048661`
- `OLEAUT32!__imp_SysFreeString` at `0x1800487cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180048826`
- `OLEAUT32!__imp_SysFreeString` at `0x180056998`
- `OLEAUT32!__imp_SysFreeString` at `0x180048381`
- `OLEAUT32!__imp_SysFreeString` at `0x18004840f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800484a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180048531`
- `OLEAUT32!__imp_SysFreeString` at `0x1800485c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180048661`
- `OLEAUT32!__imp_SysFreeString` at `0x1800487cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180048826`
- `OLEAUT32!__imp_SysFreeString` at `0x180056998`

## pseudocode

```c
__int64 __fastcall EventClassSaver::Save(EventClassSaver *this)
{
  int v2; // edi
  HANDLE CurrentThread; // rax
  HRESULT Instance; // ebx
  int v5; // eax
  BSTR v6; // rax
  OLECHAR *v7; // rbx
  OLECHAR *v8; // rbx
  OLECHAR *v9; // rbx
  OLECHAR *v10; // rbx
  OLECHAR *v11; // rbx
  BSTR v12; // rax
  OLECHAR *v13; // rbx
  BSTR v14; // rax
  OLECHAR *v15; // rdi
  int v17; // [rsp+44h] [rbp-C4h] BYREF
  BSTR v18; // [rsp+48h] [rbp-C0h]
  struct IUnknown *ppv; // [rsp+50h] [rbp-B8h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-B0h]
  GUID *rguid; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int *v23; // [rsp+70h] [rbp-98h]
  void *TokenHandle; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  v17 = 0;
  rguid = 0;
  v18 = 0;
  ppv = 0;
  v22 = 0;
  psz = 0;
  v23 = 0;
  TokenHandle = 0;
  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    CloseHandle(TokenHandle);
  }
  else
  {
    Instance = CoImpersonateClient();
    if ( Instance < 0 )
      goto LABEL_46;
    v2 = 1;
  }
  Instance = CoCreateInstance(&CLSID_CEventClass, 0, 0x17u, &IID_IEventClass2, (LPVOID *)&ppv);
  if ( v2 )
    CoRevertToSelf();
  if ( Instance >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
           ppv,
           &IID_IEventClass3,
           &v22);
    Instance = v5;
    if ( v5 >= 0 || v5 == -2147467262 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD, _QWORD, GUID **))(**((_QWORD **)this + 2)
                                                                                           + 152LL))(
                   *((_QWORD *)this + 2),
                   0,
                   &v17,
                   0,
                   0,
                   &rguid);
      if ( Instance >= 0 )
      {
        StringFromGUID2(rguid, sz, 39);
        v6 = SysAllocString(sz);
        v7 = v6;
        v18 = v6;
        if ( !v6 )
        {
LABEL_12:
          Instance = -2147024882;
          goto LABEL_46;
        }
        ((void (__fastcall *)(struct IUnknown *, BSTR))ppv->lpVtbl[2].Release)(ppv, v6);
        SysFreeString(v7);
        v18 = 0;
        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                     *((_QWORD *)this + 2),
                     1,
                     &v17);
        if ( Instance >= 0 )
        {
          v8 = SysAllocString(psz);
          v18 = v8;
          if ( !v8 && psz && *psz )
            goto LABEL_12;
          ((void (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[3].AddRef)(ppv, v8);
          SysFreeString(v8);
          v18 = 0;
          Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                       *((_QWORD *)this + 2),
                       2,
                       &v17);
          if ( Instance >= 0 )
          {
            v9 = SysAllocString(psz);
            v18 = v9;
            if ( !v9 && psz && *psz )
              goto LABEL_12;
            ((void (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[5].AddRef)(ppv, v9);
            SysFreeString(v9);
            v18 = 0;
            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                         *((_QWORD *)this + 2),
                         3,
                         &v17);
            if ( Instance >= 0 )
            {
              v10 = SysAllocString(psz);
              v18 = v10;
              if ( !v10 && psz && *psz )
                goto LABEL_12;
              ((void (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[6].Release)(ppv, v10);
              SysFreeString(v10);
              v18 = 0;
              Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                           *((_QWORD *)this + 2),
                           4,
                           &v17);
              if ( Instance >= 0 )
              {
                v11 = SysAllocString(psz);
                v18 = v11;
                if ( !v11 && psz && *psz )
                  goto LABEL_12;
                ((void (__fastcall *)(struct IUnknown *, OLECHAR *))ppv->lpVtbl[7].AddRef)(ppv, v11);
                SysFreeString(v11);
                v18 = 0;
                Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                             *((_QWORD *)this + 2),
                             5,
                             &v17);
                if ( Instance >= 0 )
                {
                  if ( rguid )
                  {
                    StringFromGUID2(rguid, sz, 39);
                    v12 = SysAllocString(sz);
                    v13 = v12;
                    v18 = v12;
                    if ( !v12 )
                      goto LABEL_12;
                    ((void (__fastcall *)(struct IUnknown *, BSTR))ppv->lpVtbl[8].QueryInterface)(ppv, v12);
                    SysFreeString(v13);
                    v18 = 0;
                  }
                  Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                               *((_QWORD *)this + 2),
                               6,
                               &v17);
                  if ( Instance >= 0 )
                  {
                    if ( v23 )
                      ((void (__fastcall *)(struct IUnknown *, _QWORD))ppv->lpVtbl[8].Release)(ppv, *v23);
                    Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                                 *((_QWORD *)this + 2),
                                 7,
                                 &v17);
                    if ( Instance >= 0 )
                    {
                      if ( v23 )
                        Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))ppv->lpVtbl[9].AddRef)(ppv, *v23);
                      if ( v22 )
                      {
                        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)this + 2) + 152LL))(
                                     *((_QWORD *)this + 2),
                                     8,
                                     &v17);
                        if ( Instance < 0 )
                          goto LABEL_46;
                        if ( rguid )
                        {
                          StringFromGUID2(rguid, sz, 39);
                          v14 = SysAllocString(sz);
                          v15 = v14;
                          v18 = v14;
                          if ( !v14 )
                            goto LABEL_12;
                          Instance = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v22 + 240LL))(v22, v14);
                          SysFreeString(v15);
                          v18 = 0;
                        }
                      }
                      if ( Instance >= 0 )
                        Instance = Saver::Store(this, L"EventSystem.EventClass", ppv);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_46:
  if ( ppv )
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  SysFreeString(0);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800481e0  push    rbx
0x1800481e2  push    rsi
0x1800481e3  push    rdi
0x1800481e4  push    r14
0x1800481e6  sub     rsp, 0E8h
0x1800481ed  mov     rax, cs:__security_cookie
0x1800481f4  xor     rax, rsp
0x1800481f7  mov     [rsp+108h+var_38], rax
0x1800481ff  mov     rsi, rcx
0x180048202  xor     r14d, r14d
0x180048205  mov     [rsp+108h+var_C4], r14d
0x18004820a  mov     [rsp+108h+rguid], r14
0x18004820f  mov     [rsp+108h+var_C0], r14
0x180048214  mov     [rsp+108h+var_B8], r14
0x180048219  mov     [rsp+108h+var_A0], r14
0x18004821e  mov     [rsp+108h+psz], r14
0x180048223  mov     [rsp+108h+var_98], r14
0x180048228  mov     [rsp+108h+TokenHandle], r14
0x18004822d  mov     edi, r14d
0x180048230  call    cs:__imp_GetCurrentThread
0x180048236  mov     rcx, rax; ThreadHandle
0x180048239  lea     r9, [rsp+108h+TokenHandle]; TokenHandle
0x18004823e  lea     edx, [r14+8]; DesiredAccess
0x180048242  lea     r8d, [r14+1]; OpenAsSelf
0x180048246  call    cs:__imp_OpenThreadToken
0x18004824c  test    eax, eax
0x18004824e  jz      short loc_18004825D
0x180048250  mov     rcx, [rsp+108h+TokenHandle]; hObject
0x180048255  call    cs:__imp_CloseHandle
0x18004825b  jmp     short loc_180048276
0x18004825d  call    cs:__imp_CoImpersonateClient
0x180048263  mov     ebx, eax
0x180048265  mov     [rsp+108h+var_C8], eax
0x180048269  test    eax, eax
0x18004826b  js      loc_1800487F8
0x180048271  mov     edi, 1
0x180048276  lea     rax, [rsp+108h+var_B8]
0x18004827b  mov     [rsp+108h+ppv], rax; ppv
0x180048280  lea     r9, IID_IEventClass2; riid
0x180048287  xor     edx, edx; pUnkOuter
0x180048289  lea     r8d, [rdx+17h]; dwClsContext
0x18004828d  lea     rcx, CLSID_CEventClass; rclsid
0x180048294  call    cs:__imp_CoCreateInstance
0x18004829a  mov     ebx, eax
0x18004829c  mov     [rsp+108h+var_C8], eax
0x1800482a0  test    edi, edi
0x1800482a2  jz      short loc_1800482AA
0x1800482a4  call    cs:__imp_CoRevertToSelf
0x1800482aa  test    ebx, ebx
0x1800482ac  js      loc_1800487F8
0x1800482b2  mov     rcx, [rsp+108h+var_B8]
0x1800482b7  mov     rax, [rcx]
0x1800482ba  lea     r8, [rsp+108h+var_A0]
0x1800482bf  lea     rdx, IID_IEventClass3
0x1800482c6  mov     rax, [rax]
0x1800482c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482ce  mov     ebx, eax
0x1800482d0  mov     [rsp+108h+var_C8], eax
0x1800482d4  test    eax, eax
0x1800482d6  jns     short loc_1800482E8
0x1800482d8  cmp     eax, 80004002h
0x1800482dd  jnz     loc_1800487F8
0x1800482e3  mov     [rsp+108h+var_C8], r14d
0x1800482e8  mov     rcx, [rsi+10h]
0x1800482ec  mov     rax, [rcx]
0x1800482ef  lea     rdx, [rsp+108h+rguid]
0x1800482f4  mov     [rsp+108h+var_E0], rdx
0x1800482f9  mov     [rsp+108h+ppv], r14
0x1800482fe  xor     r9d, r9d
0x180048301  lea     r8, [rsp+108h+var_C4]
0x180048306  xor     edx, edx
0x180048308  mov     rax, [rax+98h]
0x18004830f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048314  mov     ebx, eax
0x180048316  mov     [rsp+108h+var_C8], eax
0x18004831a  test    eax, eax
0x18004831c  js      loc_1800487F8
0x180048322  mov     edi, 27h ; '''
0x180048327  mov     r8d, edi; cchMax
0x18004832a  lea     rdx, [rsp+108h+sz]; lpsz
0x180048332  mov     rcx, [rsp+108h+rguid]; rguid
0x180048337  call    cs:__imp_StringFromGUID2
0x18004833d  lea     rcx, [rsp+108h+sz]; psz
0x180048345  call    cs:__imp_SysAllocString
0x18004834b  mov     rbx, rax
0x18004834e  mov     [rsp+108h+var_C0], rax
0x180048353  test    rax, rax
0x180048356  jnz     short loc_180048366
0x180048358  mov     ebx, 8007000Eh
0x18004835d  mov     [rsp+108h+var_C8], ebx
0x180048361  jmp     loc_1800487F8
0x180048366  mov     rcx, [rsp+108h+var_B8]
0x18004836b  mov     rax, [rcx]
0x18004836e  mov     rdx, rbx
0x180048371  mov     rax, [rax+40h]
0x180048375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004837a  mov     [rsp+108h+var_C8], eax
0x18004837e  mov     rcx, rbx; bstrString
0x180048381  call    cs:__imp_SysFreeString
0x180048387  mov     [rsp+108h+var_C0], r14
0x18004838c  mov     rcx, [rsi+10h]
0x180048390  mov     rax, [rcx]
0x180048393  lea     r8, [rsp+108h+psz]
0x180048398  mov     [rsp+108h+var_E0], r8
0x18004839d  mov     [rsp+108h+ppv], r14
0x1800483a2  xor     r9d, r9d
0x1800483a5  lea     r8, [rsp+108h+var_C4]
0x1800483aa  lea     edx, [r9+1]
0x1800483ae  mov     rax, [rax+98h]
0x1800483b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ba  mov     ebx, eax
0x1800483bc  mov     [rsp+108h+var_C8], eax
0x1800483c0  test    eax, eax
0x1800483c2  js      loc_1800487F8
0x1800483c8  mov     rcx, [rsp+108h+psz]; psz
0x1800483cd  call    cs:__imp_SysAllocString
0x1800483d3  mov     rbx, rax
0x1800483d6  mov     [rsp+108h+var_C0], rax
0x1800483db  test    rax, rax
0x1800483de  jnz     short loc_1800483F4
0x1800483e0  mov     rax, [rsp+108h+psz]
0x1800483e5  test    rax, rax
0x1800483e8  jz      short loc_1800483F4
0x1800483ea  cmp     [rax], r14w
0x1800483ee  jnz     loc_180048358
0x1800483f4  mov     rcx, [rsp+108h+var_B8]
0x1800483f9  mov     rax, [rcx]
0x1800483fc  mov     rdx, rbx
0x1800483ff  mov     rax, [rax+50h]
0x180048403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048408  mov     [rsp+108h+var_C8], eax
0x18004840c  mov     rcx, rbx; bstrString
0x18004840f  call    cs:__imp_SysFreeString
0x180048415  mov     [rsp+108h+var_C0], r14
0x18004841a  mov     rcx, [rsi+10h]
0x18004841e  mov     rax, [rcx]
0x180048421  lea     rdx, [rsp+108h+psz]
0x180048426  mov     [rsp+108h+var_E0], rdx
0x18004842b  mov     [rsp+108h+ppv], r14
0x180048430  xor     r9d, r9d
0x180048433  lea     r8, [rsp+108h+var_C4]
0x180048438  lea     edx, [r9+2]
0x18004843c  mov     rax, [rax+98h]
0x180048443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048448  mov     ebx, eax
0x18004844a  mov     [rsp+108h+var_C8], eax
0x18004844e  test    eax, eax
0x180048450  js      loc_1800487F8
0x180048456  mov     rcx, [rsp+108h+psz]; psz
0x18004845b  call    cs:__imp_SysAllocString
0x180048461  mov     rbx, rax
0x180048464  mov     [rsp+108h+var_C0], rax
0x180048469  test    rax, rax
0x18004846c  jnz     short loc_180048482
0x18004846e  mov     rax, [rsp+108h+psz]
0x180048473  test    rax, rax
0x180048476  jz      short loc_180048482
0x180048478  cmp     [rax], r14w
0x18004847c  jnz     loc_180048358
0x180048482  mov     rcx, [rsp+108h+var_B8]
0x180048487  mov     rax, [rcx]
0x18004848a  mov     rdx, rbx
0x18004848d  mov     rax, [rax+80h]
0x180048494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048499  mov     [rsp+108h+var_C8], eax
0x18004849d  mov     rcx, rbx; bstrString
0x1800484a0  call    cs:__imp_SysFreeString
0x1800484a6  mov     [rsp+108h+var_C0], r14
0x1800484ab  mov     rcx, [rsi+10h]
0x1800484af  mov     rax, [rcx]
0x1800484b2  lea     rdx, [rsp+108h+psz]
0x1800484b7  mov     [rsp+108h+var_E0], rdx
0x1800484bc  mov     [rsp+108h+ppv], r14
0x1800484c1  xor     r9d, r9d
0x1800484c4  lea     r8, [rsp+108h+var_C4]
0x1800484c9  lea     edx, [r9+3]
0x1800484cd  mov     rax, [rax+98h]
0x1800484d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484d9  mov     ebx, eax
0x1800484db  mov     [rsp+108h+var_C8], eax
0x1800484df  test    eax, eax
0x1800484e1  js      loc_1800487F8
0x1800484e7  mov     rcx, [rsp+108h+psz]; psz
0x1800484ec  call    cs:__imp_SysAllocString
0x1800484f2  mov     rbx, rax
0x1800484f5  mov     [rsp+108h+var_C0], rax
0x1800484fa  test    rax, rax
0x1800484fd  jnz     short loc_180048513
0x1800484ff  mov     rax, [rsp+108h+psz]
0x180048504  test    rax, rax
0x180048507  jz      short loc_180048513
0x180048509  cmp     [rax], r14w
0x18004850d  jnz     loc_180048358
0x180048513  mov     rcx, [rsp+108h+var_B8]
0x180048518  mov     rax, [rcx]
0x18004851b  mov     rdx, rbx
0x18004851e  mov     rax, [rax+0A0h]
0x180048525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004852a  mov     [rsp+108h+var_C8], eax
0x18004852e  mov     rcx, rbx; bstrString
0x180048531  call    cs:__imp_SysFreeString
0x180048537  mov     [rsp+108h+var_C0], r14
0x18004853c  mov     rcx, [rsi+10h]
0x180048540  mov     rax, [rcx]
0x180048543  lea     rdx, [rsp+108h+psz]
0x180048548  mov     [rsp+108h+var_E0], rdx
0x18004854d  mov     [rsp+108h+ppv], r14
0x180048552  xor     r9d, r9d
0x180048555  lea     r8, [rsp+108h+var_C4]
0x18004855a  lea     edx, [r9+4]
0x18004855e  mov     rax, [rax+98h]
0x180048565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004856a  mov     ebx, eax
0x18004856c  mov     [rsp+108h+var_C8], eax
0x180048570  test    eax, eax
0x180048572  js      loc_1800487F8
0x180048578  mov     rcx, [rsp+108h+psz]; psz
0x18004857d  call    cs:__imp_SysAllocString
0x180048583  mov     rbx, rax
0x180048586  mov     [rsp+108h+var_C0], rax
0x18004858b  test    rax, rax
0x18004858e  jnz     short loc_1800485A4
0x180048590  mov     rax, [rsp+108h+psz]
0x180048595  test    rax, rax
0x180048598  jz      short loc_1800485A4
0x18004859a  cmp     [rax], r14w
0x18004859e  jnz     loc_180048358
0x1800485a4  mov     rcx, [rsp+108h+var_B8]
0x1800485a9  mov     rax, [rcx]
0x1800485ac  mov     rdx, rbx
0x1800485af  mov     rax, [rax+0B0h]
0x1800485b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485bb  mov     [rsp+108h+var_C8], eax
0x1800485bf  mov     rcx, rbx; bstrString
0x1800485c2  call    cs:__imp_SysFreeString
0x1800485c8  mov     [rsp+108h+var_C0], r14
0x1800485cd  mov     rcx, [rsi+10h]
0x1800485d1  mov     rax, [rcx]
0x1800485d4  lea     rdx, [rsp+108h+rguid]
0x1800485d9  mov     [rsp+108h+var_E0], rdx
0x1800485de  mov     [rsp+108h+ppv], r14
0x1800485e3  xor     r9d, r9d
0x1800485e6  lea     r8, [rsp+108h+var_C4]
0x1800485eb  lea     edx, [r9+5]
0x1800485ef  mov     rax, [rax+98h]
0x1800485f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485fb  mov     ebx, eax
0x1800485fd  mov     [rsp+108h+var_C8], eax
0x180048601  test    eax, eax
0x180048603  js      loc_1800487F8
0x180048609  mov     rcx, [rsp+108h+rguid]; rguid
0x18004860e  test    rcx, rcx
0x180048611  jz      short loc_18004866C
0x180048613  mov     r8d, edi; cchMax
0x180048616  lea     rdx, [rsp+108h+sz]; lpsz
0x18004861e  call    cs:__imp_StringFromGUID2
0x180048624  lea     rcx, [rsp+108h+sz]; psz
0x18004862c  call    cs:__imp_SysAllocString
0x180048632  mov     rbx, rax
0x180048635  mov     [rsp+108h+var_C0], rax
0x18004863a  test    rax, rax
0x18004863d  jz      loc_180048358
0x180048643  mov     rcx, [rsp+108h+var_B8]
0x180048648  mov     rax, [rcx]
0x18004864b  mov     rdx, rbx
0x18004864e  mov     rax, [rax+0C0h]
0x180048655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004865a  mov     [rsp+108h+var_C8], eax
0x18004865e  mov     rcx, rbx; bstrString
0x180048661  call    cs:__imp_SysFreeString
0x180048667  mov     [rsp+108h+var_C0], r14
0x18004866c  mov     rcx, [rsi+10h]
0x180048670  mov     rax, [rcx]
0x180048673  lea     rdx, [rsp+108h+var_98]
0x180048678  mov     [rsp+108h+var_E0], rdx
0x18004867d  mov     [rsp+108h+ppv], r14
0x180048682  xor     r9d, r9d
0x180048685  lea     r8, [rsp+108h+var_C4]
0x18004868a  lea     edx, [r9+6]
0x18004868e  mov     rax, [rax+98h]
0x180048695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004869a  mov     ebx, eax
0x18004869c  mov     [rsp+108h+var_C8], eax
0x1800486a0  test    eax, eax
0x1800486a2  js      loc_1800487F8
0x1800486a8  mov     rdx, [rsp+108h+var_98]
0x1800486ad  test    rdx, rdx
0x1800486b0  jz      short loc_1800486CC
0x1800486b2  mov     rcx, [rsp+108h+var_B8]
0x1800486b7  mov     rax, [rcx]
0x1800486ba  mov     edx, [rdx]
0x1800486bc  mov     rax, [rax+0D0h]
0x1800486c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486c8  mov     [rsp+108h+var_C8], eax
0x1800486cc  mov     rcx, [rsi+10h]
0x1800486d0  mov     rax, [rcx]
0x1800486d3  lea     rdx, [rsp+108h+var_98]
0x1800486d8  mov     [rsp+108h+var_E0], rdx
0x1800486dd  mov     [rsp+108h+ppv], r14
0x1800486e2  xor     r9d, r9d
  ... truncated ...
```
