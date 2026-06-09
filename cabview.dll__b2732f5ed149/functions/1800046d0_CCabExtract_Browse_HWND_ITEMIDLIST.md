# CCabExtract::Browse(HWND__ *,_ITEMIDLIST * *)

- ea: `0x1800046d0`
- end: `0x1800049b3`
- name: `?Browse@CCabExtract@@AEAAJPEAUHWND__@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `739`
- prototype: `__int64 __fastcall(CCabExtract *__hidden this, HWND, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000570c`

## callees

- `0x180002620`
- `0x1800046d0`
- `0x1800066dc`
- `0x180006794`
- `0x180008498`
- `0x180009ca0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047d6`

## pseudocode

```c
__int64 __fastcall CCabExtract::Browse(CCabExtract *this, HWND a2, struct _ITEMIDLIST **a3)
{
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  _QWORD v20[3]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v21[3]; // [rsp+48h] [rbp-38h] BYREF
  LPVOID v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-18h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *a3 = 0;
  memset(v21, 0, sizeof(v21));
  v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(v21, g_hinst, 69);
  v6 = v5;
  if ( v5 >= 0 )
  {
    memset(v20, 0, sizeof(v20));
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
           v20,
           g_hinst,
           70);
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"shell\\ext\\cabview\\cabitms.cpp",
        (const char *)(unsigned int)v7,
        ppv);
LABEL_5:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v20);
      goto LABEL_26;
    }
    v22 = 0;
    Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v22);
    v8 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 3u, &GUID_42f85136_db7e_439c_85f1_e4075d135fc8, &v22);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v22 + 136LL))(v22, v21[0]);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v22 + 144LL))(v22, v20[0]);
        v6 = v8;
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v22 + 72LL))(v22, 2144);
          v6 = v8;
          if ( v8 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, HWND))(*(_QWORD *)v22 + 24LL))(v22, a2);
            if ( v6 >= 0 )
            {
              v10 = v22;
              v23 = 0;
              v11 = *(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v22 + 160LL);
              Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v23);
              v12 = v11(v10, &v23);
              v6 = v12;
              if ( v12 >= 0 )
              {
                v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
                v24 = 0;
                v14 = **v23;
                Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v24);
                v15 = v14(v13, &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5, &v24);
                v6 = v15;
                if ( v15 >= 0 )
                {
                  v15 = (*(__int64 (__fastcall **)(__int64, struct _ITEMIDLIST **))(*(_QWORD *)v24 + 40LL))(v24, a3);
                  v6 = v15;
                  if ( v15 >= 0 )
                  {
                    Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v24);
                    Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v23);
                    Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v22);
                    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v20);
                    v6 = 0;
                    goto LABEL_26;
                  }
                  v16 = 864;
                }
                else
                {
                  v16 = 863;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v16,
                  (unsigned int)"shell\\ext\\cabview\\cabitms.cpp",
                  (const char *)(unsigned int)v15,
                  ppva);
                Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v24);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x35D,
                  (unsigned int)"shell\\ext\\cabview\\cabitms.cpp",
                  (const char *)(unsigned int)v12,
                  ppva);
              }
              Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v23);
            }
            goto LABEL_9;
          }
          v9 = 857;
        }
        else
        {
          v9 = 856;
        }
      }
      else
      {
        v9 = 855;
      }
    }
    else
    {
      v9 = 854;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\ext\\cabview\\cabitms.cpp",
      (const char *)(unsigned int)v8,
      ppva);
LABEL_9:
    Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(&v22);
    goto LABEL_5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x351,
    (unsigned int)"shell\\ext\\cabview\\cabitms.cpp",
    (const char *)(unsigned int)v5,
    ppv);
LABEL_26:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800046d0  mov     [rsp-18h+arg_0], rbx
0x1800046d5  push    rbp
0x1800046d6  push    rsi
0x1800046d7  push    rdi
0x1800046d8  mov     rbp, rsp
0x1800046db  sub     rsp, 80h
0x1800046e2  mov     rax, cs:__security_cookie
0x1800046e9  xor     rax, rsp
0x1800046ec  mov     [rbp+var_8], rax
0x1800046f0  mov     rsi, r8
0x1800046f3  mov     qword ptr [r8], 0
0x1800046fa  mov     rdi, rdx
0x1800046fd  mov     [rbp+var_38], 0
0x180004705  mov     rdx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18000470c  lea     rcx, [rbp+var_38]
0x180004710  mov     r8d, 45h ; 'E'
0x180004716  mov     [rbp+var_30], 0
0x18000471e  mov     [rbp+var_28], 0
0x180004726  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18000472b  mov     ebx, eax
0x18000472d  test    eax, eax
0x18000472f  jns     short loc_18000474E
0x180004731  mov     rcx, [rbp+18h]; this
0x180004735  lea     r8, aShellExtCabvie; "shell\\ext\\cabview\\cabitms.cpp"
0x18000473c  mov     r9d, eax; char *
0x18000473f  mov     edx, 351h; void *
0x180004744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004749  jmp     loc_180004989
0x18000474e  mov     rdx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180004755  lea     rcx, [rbp+var_50]
0x180004759  mov     r8d, 46h ; 'F'
0x18000475f  mov     [rbp+var_50], 0
0x180004767  mov     [rbp+var_48], 0
0x18000476f  mov     [rbp+var_40], 0
0x180004777  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x18000477c  mov     ebx, eax
0x18000477e  test    eax, eax
0x180004780  jns     short loc_1800047A8
0x180004782  mov     rcx, [rbp+18h]; this
0x180004786  lea     r8, aShellExtCabvie; "shell\\ext\\cabview\\cabitms.cpp"
0x18000478d  mov     r9d, eax; char *
0x180004790  mov     edx, 353h; void *
0x180004795  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000479a  lea     rcx, [rbp+var_50]
0x18000479e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800047a3  jmp     loc_180004989
0x1800047a8  lea     rcx, [rbp+var_20]
0x1800047ac  mov     [rbp+var_20], 0
0x1800047b4  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x1800047b9  xor     edx, edx; pUnkOuter
0x1800047bb  lea     rax, [rbp+var_20]
0x1800047bf  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x1800047c6  mov     qword ptr [rsp+80h+ppv], rax; int
0x1800047cb  lea     rcx, CLSID_FileOpenDialog; rclsid
0x1800047d2  lea     r8d, [rdx+3]; dwClsContext
0x1800047d6  call    cs:__imp_CoCreateInstance
0x1800047dc  mov     ebx, eax
0x1800047de  test    eax, eax
0x1800047e0  jns     short loc_180004805
0x1800047e2  mov     edx, 356h; void *
0x1800047e7  mov     rcx, [rbp+18h]; this
0x1800047eb  lea     r8, aShellExtCabvie; "shell\\ext\\cabview\\cabitms.cpp"
0x1800047f2  mov     r9d, eax; char *
0x1800047f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047fa  lea     rcx, [rbp+var_20]
0x1800047fe  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x180004803  jmp     short loc_18000479A
0x180004805  mov     rcx, [rbp+var_20]
0x180004809  mov     rdx, [rbp+var_38]
0x18000480d  mov     rax, [rcx]
0x180004810  mov     rax, [rax+88h]
0x180004817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481c  mov     ebx, eax
0x18000481e  test    eax, eax
0x180004820  jns     short loc_180004829
0x180004822  mov     edx, 357h
0x180004827  jmp     short loc_1800047E7
0x180004829  mov     rcx, [rbp+var_20]
0x18000482d  mov     rdx, [rbp+var_50]
0x180004831  mov     rax, [rcx]
0x180004834  mov     rax, [rax+90h]
0x18000483b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004840  mov     ebx, eax
0x180004842  test    eax, eax
0x180004844  jns     short loc_18000484D
0x180004846  mov     edx, 358h
0x18000484b  jmp     short loc_1800047E7
0x18000484d  mov     rcx, [rbp+var_20]
0x180004851  mov     edx, 860h
0x180004856  mov     rax, [rcx]
0x180004859  mov     rax, [rax+48h]
0x18000485d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004862  mov     ebx, eax
0x180004864  test    eax, eax
0x180004866  jns     short loc_180004872
0x180004868  mov     edx, 359h
0x18000486d  jmp     loc_1800047E7
0x180004872  mov     rcx, [rbp+var_20]
0x180004876  mov     rdx, rdi
0x180004879  mov     rax, [rcx]
0x18000487c  mov     rax, [rax+18h]
0x180004880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004885  mov     ebx, eax
0x180004887  test    eax, eax
0x180004889  js      loc_1800047FA
0x18000488f  mov     rdi, [rbp+var_20]
0x180004893  lea     rcx, [rbp+var_18]
0x180004897  mov     [rbp+var_18], 0
0x18000489f  mov     rax, [rdi]
0x1800048a2  mov     rbx, [rax+0A0h]
0x1800048a9  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x1800048ae  lea     rdx, [rbp+var_18]
0x1800048b2  mov     rcx, rdi
0x1800048b5  mov     rax, rbx
0x1800048b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048bd  mov     ebx, eax
0x1800048bf  test    eax, eax
0x1800048c1  jns     short loc_1800048E9
0x1800048c3  mov     rcx, [rbp+18h]; this
0x1800048c7  lea     r8, aShellExtCabvie; "shell\\ext\\cabview\\cabitms.cpp"
0x1800048ce  mov     r9d, eax; char *
0x1800048d1  mov     edx, 35Dh; void *
0x1800048d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800048db  lea     rcx, [rbp+var_18]
0x1800048df  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x1800048e4  jmp     loc_1800047FA
0x1800048e9  mov     rbx, [rbp+var_18]
0x1800048ed  lea     rcx, [rbp+var_10]
0x1800048f1  mov     [rbp+var_10], 0
0x1800048f9  mov     rax, [rbx]
0x1800048fc  mov     rdi, [rax]
0x1800048ff  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x180004904  lea     r8, [rbp+var_10]
0x180004908  mov     rcx, rbx
0x18000490b  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x180004912  mov     rax, rdi
0x180004915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000491a  mov     ebx, eax
0x18000491c  test    eax, eax
0x18000491e  jns     short loc_180004943
0x180004920  mov     edx, 35Fh; void *
0x180004925  mov     rcx, [rbp+18h]; this
0x180004929  lea     r8, aShellExtCabvie; "shell\\ext\\cabview\\cabitms.cpp"
0x180004930  mov     r9d, eax; char *
0x180004933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004938  lea     rcx, [rbp+var_10]
0x18000493c  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x180004941  jmp     short loc_1800048DB
0x180004943  mov     rcx, [rbp+var_10]
0x180004947  mov     rdx, rsi
0x18000494a  mov     rax, [rcx]
0x18000494d  mov     rax, [rax+28h]
0x180004951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004956  mov     ebx, eax
0x180004958  test    eax, eax
0x18000495a  jns     short loc_180004963
0x18000495c  mov     edx, 360h
0x180004961  jmp     short loc_180004925
0x180004963  lea     rcx, [rbp+var_10]
0x180004967  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x18000496c  lea     rcx, [rbp+var_18]
0x180004970  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x180004975  lea     rcx, [rbp+var_20]
0x180004979  call    ?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)
0x18000497e  lea     rcx, [rbp+var_50]
0x180004982  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180004987  xor     ebx, ebx
0x180004989  lea     rcx, [rbp+var_38]
0x18000498d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180004992  mov     eax, ebx
0x180004994  mov     rcx, [rbp+var_8]
0x180004998  xor     rcx, rsp; StackCookie
0x18000499b  call    __security_check_cookie
0x1800049a0  mov     rbx, [rsp+80h+arg_0]
0x1800049a8  add     rsp, 80h
0x1800049af  pop     rdi
0x1800049b0  pop     rsi
0x1800049b1  pop     rbp
0x1800049b2  retn
```
