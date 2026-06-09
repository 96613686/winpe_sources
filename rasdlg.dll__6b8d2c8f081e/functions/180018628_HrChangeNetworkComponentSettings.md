# HrChangeNetworkComponentSettings

- ea: `0x180018628`
- end: `0x1800188b8`
- name: `HrChangeNetworkComponentSettings`
- size: `656`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b048`
- `0x18002d480`

## callees

- `0x180018628`
- `0x180026eb0`
- `0x180040bc8`
- `0x180040e50`
- `0x180040ef8`
- `0x180048f0c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800186c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800186c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180018793`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180018793`

## pseudocode

```c
__int64 __fastcall HrChangeNetworkComponentSettings(HWND hWnd, __int64 a2, const WCHAR *a3, int a4)
{
  unsigned int v5; // r14d
  HRESULT v7; // eax
  LPCWSTR v8; // r15
  HRESULT v9; // edi
  __int64 v10; // rdx
  __int64 i; // rbx
  __int64 v12; // rsi
  HRESULT v13; // eax
  __int64 j; // rsi
  UINT v15; // edx
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpString1; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  HWND v21; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpString2; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  _QWORD v25[256]; // [rsp+80h] [rbp-80h] BYREF

  lpString2 = a3;
  v21 = hWnd;
  v5 = 1;
  lpString1 = 0;
  ppv = 0;
  v19 = 0;
  v7 = HrCreateAndInitializeINetCfg((unsigned int)&v19, (unsigned int)&lpString1, 1, a4, a2);
  v8 = lpString1;
  v9 = v7;
  if ( v7 )
  {
    v5 = 0;
    if ( v7 == -2147180507 )
    {
      v15 = 1586;
    }
    else
    {
      v15 = 1587;
      if ( v7 == -2147024891 )
        v15 = 1588;
    }
    MsgDlgUtil(hWnd, v15, 0, g_hinstDll, 0x169u);
  }
  else
  {
    v9 = CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, &ppv);
    if ( v9 >= 0 )
    {
      if ( a4 )
      {
        memset_0(v25, 0, sizeof(v25));
        v17 = 0;
        v9 = HrEnumComponentsForListView(v8, v10, v25, &v17);
        if ( v9 >= 0 && v17 <= 0x100 )
        {
          for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
          {
            v12 = v25[i];
            lpString1 = 0;
            if ( (*(int (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v12 + 48LL))(v12, &lpString1) >= 0
              && !lstrcmpW(lpString1, lpString2) )
            {
              if ( a4 == 1 )
                v13 = (*(__int64 (__fastcall **)(LPVOID, HWND, LPCWSTR, __int64))(*(_QWORD *)ppv + 24LL))(
                        ppv,
                        v21,
                        v8,
                        v12);
              else
                v13 = (*(__int64 (__fastcall **)(__int64, HWND, __int64))(*(_QWORD *)v12 + 112LL))(v12, v21, 2);
              v9 = v13;
              CoTaskMemFree((LPVOID)lpString1);
              break;
            }
            CoTaskMemFree((LPVOID)lpString1);
          }
          for ( j = 0; (unsigned int)j < v17; j = (unsigned int)(j + 1) )
          {
            ReleaseObj(v25[j]);
            v25[j] = 0;
          }
        }
      }
      else
      {
        v23 = 0;
        v24 = 0;
        LODWORD(v23) = 2;
        v9 = (*(__int64 (__fastcall **)(LPVOID, HWND, LPCWSTR, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, hWnd, v8, &v23);
      }
      if ( !v9 )
        v9 = (*(__int64 (__fastcall **)(LPCWSTR))(*(_QWORD *)v8 + 40LL))(v8);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    HrUninitializeAndReleaseINetCfg(v19, v8, v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018628  push    rbp
0x18001862a  push    rbx
0x18001862b  push    rsi
0x18001862c  push    rdi
0x18001862d  push    r13
0x18001862f  push    r14
0x180018631  push    r15
0x180018633  lea     rbp, [rsp-790h]
0x18001863b  sub     rsp, 890h
0x180018642  mov     rax, cs:__security_cookie
0x180018649  xor     rax, rsp
0x18001864c  mov     [rbp+7C0h+var_40], rax
0x180018653  mov     [rsp+8C0h+lpString2], r8
0x180018658  mov     rbx, rcx
0x18001865b  mov     [rsp+8C0h+var_870], rcx
0x180018660  mov     r14d, 1
0x180018666  mov     [rsp+8C0h+ppv], rdx
0x18001866b  lea     rcx, [rsp+8C0h+var_880]
0x180018670  mov     r8d, r14d
0x180018673  mov     [rsp+8C0h+lpString1], 0
0x18001867c  lea     rdx, [rsp+8C0h+lpString1]
0x180018681  mov     [rsp+8C0h+var_878], 0
0x18001868a  mov     r13d, r9d
0x18001868d  mov     [rsp+8C0h+var_880], 0
0x180018695  call    HrCreateAndInitializeINetCfg
0x18001869a  mov     r15, [rsp+8C0h+lpString1]
0x18001869f  mov     edi, eax
0x1800186a1  test    eax, eax
0x1800186a3  jnz     loc_18001882E
0x1800186a9  lea     rax, [rsp+8C0h+var_878]
0x1800186ae  mov     r8d, r14d; dwClsContext
0x1800186b1  lea     r9, IID_INetConnectionUiUtilities; riid
0x1800186b8  mov     [rsp+8C0h+ppv], rax; ppv
0x1800186bd  xor     edx, edx; pUnkOuter
0x1800186bf  lea     rcx, CLSID_NetConnectionUiUtilities; rclsid
0x1800186c6  call    cs:__imp_CoCreateInstance
0x1800186cc  mov     edi, eax
0x1800186ce  test    eax, eax
0x1800186d0  js      loc_18001886B
0x1800186d6  test    r13d, r13d
0x1800186d9  jnz     short loc_180018715
0x1800186db  mov     rcx, [rsp+8C0h+var_878]
0x1800186e0  lea     r9, [rsp+8C0h+var_860]
0x1800186e5  xor     eax, eax
0x1800186e7  xorps   xmm0, xmm0
0x1800186ea  movups  [rsp+8C0h+var_860], xmm0
0x1800186ef  mov     [rsp+8C0h+var_850], rax
0x1800186f4  mov     r8, r15
0x1800186f7  mov     dword ptr [rsp+8C0h+var_860], 2
0x1800186ff  mov     rdx, rbx
0x180018702  mov     rax, [rcx]
0x180018705  mov     rax, [rax+28h]
0x180018709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001870e  mov     edi, eax
0x180018710  jmp     loc_180018817
0x180018715  xor     edx, edx; Val
0x180018717  lea     rcx, [rbp+7C0h+var_840]; void *
0x18001871b  mov     r8d, 800h; Size
0x180018721  call    memset_0
0x180018726  lea     r9, [rsp+8C0h+var_890]
0x18001872b  mov     [rsp+8C0h+var_890], 0
0x180018733  lea     r8, [rbp+7C0h+var_840]
0x180018737  mov     rcx, r15
0x18001873a  call    HrEnumComponentsForListView
0x18001873f  mov     edi, eax
0x180018741  test    eax, eax
0x180018743  js      loc_180018817
0x180018749  cmp     [rsp+8C0h+var_890], 100h
0x180018751  ja      loc_180018817
0x180018757  xor     ebx, ebx
0x180018759  cmp     ebx, [rsp+8C0h+var_890]
0x18001875d  jnb     loc_1800187F3
0x180018763  mov     rsi, [rbp+rbx*8+7C0h+var_840]
0x180018768  lea     rdx, [rsp+8C0h+lpString1]
0x18001876d  mov     [rsp+8C0h+lpString1], 0
0x180018776  mov     rcx, rsi
0x180018779  mov     rax, [rsi]
0x18001877c  mov     rax, [rax+30h]
0x180018780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018785  test    eax, eax
0x180018787  js      short loc_18001879D
0x180018789  mov     rdx, [rsp+8C0h+lpString2]; lpString2
0x18001878e  mov     rcx, [rsp+8C0h+lpString1]; lpString1
0x180018793  call    cs:__imp_lstrcmpW
0x180018799  test    eax, eax
0x18001879b  jz      short loc_1800187AD
0x18001879d  mov     rcx, [rsp+8C0h+lpString1]; pv
0x1800187a2  call    cs:__imp_CoTaskMemFree
0x1800187a8  add     ebx, r14d
0x1800187ab  jmp     short loc_180018759
0x1800187ad  mov     rdx, [rsp+8C0h+var_870]
0x1800187b2  cmp     r13d, r14d
0x1800187b5  jnz     short loc_1800187D0
0x1800187b7  mov     rcx, [rsp+8C0h+var_878]
0x1800187bc  mov     r9, rsi
0x1800187bf  mov     r8, r15
0x1800187c2  mov     rax, [rcx]
0x1800187c5  mov     rax, [rax+18h]
0x1800187c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187ce  jmp     short loc_1800187E6
0x1800187d0  mov     rax, [rsi]
0x1800187d3  xor     r9d, r9d
0x1800187d6  mov     rcx, rsi
0x1800187d9  mov     rax, [rax+70h]
0x1800187dd  lea     r8d, [r9+2]
0x1800187e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e6  mov     rcx, [rsp+8C0h+lpString1]; pv
0x1800187eb  mov     edi, eax
0x1800187ed  call    cs:__imp_CoTaskMemFree
0x1800187f3  xor     esi, esi
0x1800187f5  cmp     [rsp+8C0h+var_890], esi
0x1800187f9  jbe     short loc_180018817
0x1800187fb  mov     rcx, [rbp+rsi*8+7C0h+var_840]
0x180018800  call    ReleaseObj
0x180018805  mov     [rbp+rsi*8+7C0h+var_840], 0
0x18001880e  add     esi, r14d
0x180018811  cmp     esi, [rsp+8C0h+var_890]
0x180018815  jb      short loc_1800187FB
0x180018817  test    edi, edi
0x180018819  jnz     short loc_18001886B
0x18001881b  mov     rax, [r15]
0x18001881e  mov     rcx, r15
0x180018821  mov     rax, [rax+28h]
0x180018825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001882a  mov     edi, eax
0x18001882c  jmp     short loc_18001886B
0x18001882e  xor     r14d, r14d
0x180018831  cmp     edi, 8004A025h
0x180018837  jnz     short loc_180018840
0x180018839  mov     edx, 632h
0x18001883e  jmp     short loc_180018851
0x180018840  mov     edx, 633h
0x180018845  cmp     edi, 80070005h
0x18001884b  lea     eax, [rdx+1]
0x18001884e  cmovz   edx, eax; uID
0x180018851  mov     r9, cs:g_hinstDll; hInstance
0x180018858  xor     r8d, r8d; Arguments
0x18001885b  mov     rcx, rbx; hWnd
0x18001885e  mov     dword ptr [rsp+8C0h+ppv], 169h; UINT
0x180018866  call    MsgDlgUtil
0x18001886b  mov     rcx, [rsp+8C0h+var_878]
0x180018870  test    rcx, rcx
0x180018873  jz      short loc_180018881
0x180018875  mov     rax, [rcx]
0x180018878  mov     rax, [rax+10h]
0x18001887c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018881  test    r15, r15
0x180018884  jz      short loc_180018895
0x180018886  mov     ecx, [rsp+8C0h+var_880]
0x18001888a  mov     r8d, r14d
0x18001888d  mov     rdx, r15
0x180018890  call    HrUninitializeAndReleaseINetCfg
0x180018895  mov     eax, edi
0x180018897  mov     rcx, [rbp+7C0h+var_40]
0x18001889e  xor     rcx, rsp; StackCookie
0x1800188a1  call    __security_check_cookie
0x1800188a6  add     rsp, 890h
0x1800188ad  pop     r15
0x1800188af  pop     r14
0x1800188b1  pop     r13
0x1800188b3  pop     rdi
0x1800188b4  pop     rsi
0x1800188b5  pop     rbx
0x1800188b6  pop     rbp
0x1800188b7  retn
```
