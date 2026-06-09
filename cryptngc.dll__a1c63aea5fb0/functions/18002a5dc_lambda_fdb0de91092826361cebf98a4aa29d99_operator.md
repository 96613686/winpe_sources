# _lambda_fdb0de91092826361cebf98a4aa29d99_::operator()

- ea: `0x18002a5dc`
- end: `0x18002a872`
- name: `_lambda_fdb0de91092826361cebf98a4aa29d99_::operator()`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a5b4`

## callees

- `0x180006538`
- `0x180009510`
- `0x1800167f8`
- `0x180018430`
- `0x180019e94`
- `0x18001aaf8`
- `0x18001ae60`
- `0x18002a5dc`
- `0x18002b8c8`
- `0x180042a34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a84f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a84f`
- `ncrypt!NCryptSetProperty` at `0x18002a706`
- `ncrypt!NCryptSetProperty` at `0x18002a706`

## string_xrefs

- `0x18002a601`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18002a697`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18002a7fb`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_fdb0de91092826361cebf98a4aa29d99_::operator()(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  SECURITY_STATUS v5; // eax
  HWND v6; // r8
  int v7; // edi
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  const unsigned __int16 *v10; // r8
  int v11; // r9d
  BYTE *v12; // r8
  _BYTE *v13; // rcx
  int v14; // edx
  int v15; // r8d
  int v16; // ecx
  __int64 *v17; // r9
  int v18; // eax
  __int64 v19; // r9
  bool v20; // zf
  unsigned int *v21; // r8
  __int64 *v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  HLOCAL v25; // rcx
  _QWORD **v26; // rax
  HLOCAL v27; // rdx
  HLOCAL v28; // rcx
  DWORD dwFlags; // [rsp+20h] [rbp-40h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-40h]
  _QWORD v31[2]; // [rsp+40h] [rbp-20h] BYREF
  char v32; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  NCRYPT_HANDLE hObject; // [rsp+88h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+30h] BYREF

  v2 = *(_QWORD **)a1;
  if ( !*v2 )
  {
    v3 = 1732;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !**(_QWORD **)(a1 + 8) )
  {
    v3 = 1733;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 16) )
  {
    v3 = 1734;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 24) )
  {
    v3 = 1735;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    v3 = 1736;
    goto LABEL_3;
  }
  hObject = 0;
  v5 = NgcOpenUserIdKey(*v2, &hObject);
  v7 = v5;
  if ( v5 >= 0 )
  {
    v5 = NgcUtils::SetNCryptWindowHandle((NgcUtils *)hObject, **(_QWORD **)(a1 + 40), v6);
    v7 = v5;
    if ( v5 >= 0 )
    {
      v5 = NgcUtils::SetNgcAuthTicket((NgcUtils *)hObject, **(_QWORD **)(a1 + 48), v9);
      v7 = v5;
      if ( v5 >= 0 )
      {
        v5 = NgcUtils::SetNCryptUiPolicy((NgcUtils *)hObject, **(_QWORD **)(a1 + 56), v10);
        v7 = v5;
        if ( v5 >= 0 )
        {
          v12 = **(BYTE ***)(a1 + 64);
          if ( !v12 || (v5 = NCryptSetProperty(hObject, L"NgcUICancellationId", v12, 0x10u, 0), v7 = v5, v5 >= 0) )
          {
            v13 = *(_BYTE **)(a1 + 72);
            if ( (*v13 & 1) != 0 )
            {
              v5 = NgcUtils::SetNCryptBoolProperty(
                     (NgcUtils *)hObject,
                     (unsigned __int64)L"NgcDisplayAltCredOption",
                     (const unsigned __int16 *)1,
                     v11);
              v7 = v5;
              if ( v5 < 0 )
              {
                v8 = 1770;
                goto LABEL_16;
              }
              v13 = *(_BYTE **)(a1 + 72);
            }
            if ( **(_QWORD **)(a1 + 48) || (v14 = 0, **(_BYTE **)(a1 + 80)) )
              v14 = 64;
            v15 = *(_DWORD *)v13;
            v16 = v14 | ((*(_DWORD *)v13 & 0x10000) != 0 ? 0x10000 : 2);
            if ( (v15 & 0x20000) != 0 )
              v16 |= 0x20000u;
            v17 = *(__int64 **)(a1 + 88);
            v31[0] = &hMem;
            hMem = 0;
            v18 = v16 | 0x40000;
            v19 = *v17;
            v20 = (v15 & 0x40000) == 0;
            v21 = *(unsigned int **)(a1 + 16);
            v22 = *(__int64 **)(a1 + 8);
            if ( v20 )
              v18 = v16;
            v31[1] = 0;
            v23 = *v21;
            v24 = *v22;
            v32 = 1;
            dwFlagsa = v18;
            v7 = SignWithUserIdKeyHandle(hObject, v24, v23, v19);
            wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v31);
            if ( v7 >= 0 )
            {
              v26 = *(_QWORD ***)(a1 + 24);
              v27 = hMem;
              hMem = 0;
              **v26 = v27;
              ***(_DWORD ***)(a1 + 32) = 0;
              v28 = hMem;
              hMem = 0;
              if ( v28 )
                LocalFree(v28);
              v7 = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x70F,
                (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                (const char *)(unsigned int)v7,
                dwFlagsa);
              v25 = hMem;
              hMem = 0;
              if ( v25 )
                LocalFree(v25);
            }
            goto LABEL_41;
          }
          v8 = 1762;
        }
        else
        {
          v8 = 1753;
        }
      }
      else
      {
        v8 = 1749;
      }
    }
    else
    {
      v8 = 1745;
    }
  }
  else
  {
    v8 = 1741;
  }
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
    (const char *)(unsigned int)v5,
    dwFlags);
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a5dc  mov     [rsp-18h+arg_18], rbx
0x18002a5e1  push    rbp
0x18002a5e2  push    rsi
0x18002a5e3  push    rdi
0x18002a5e4  mov     rbp, rsp
0x18002a5e7  sub     rsp, 60h
0x18002a5eb  mov     rbx, rcx
0x18002a5ee  xor     esi, esi
0x18002a5f0  mov     rcx, [rcx]
0x18002a5f3  cmp     [rcx], rsi
0x18002a5f6  jnz     short loc_18002A61C
0x18002a5f8  mov     edx, 6C4h; void *
0x18002a5fd  mov     rcx, [rbp+18h]; this
0x18002a601  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002a608  mov     ebx, 80090027h
0x18002a60d  mov     r9d, ebx; char *
0x18002a610  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a615  mov     eax, ebx
0x18002a617  jmp     loc_18002A862
0x18002a61c  mov     rax, [rbx+8]
0x18002a620  cmp     [rax], rsi
0x18002a623  jnz     short loc_18002A62C
0x18002a625  mov     edx, 6C5h
0x18002a62a  jmp     short loc_18002A5FD
0x18002a62c  mov     rax, [rbx+10h]
0x18002a630  cmp     [rax], esi
0x18002a632  jnz     short loc_18002A63B
0x18002a634  mov     edx, 6C6h
0x18002a639  jmp     short loc_18002A5FD
0x18002a63b  mov     rax, [rbx+18h]
0x18002a63f  cmp     [rax], rsi
0x18002a642  jnz     short loc_18002A64B
0x18002a644  mov     edx, 6C7h
0x18002a649  jmp     short loc_18002A5FD
0x18002a64b  mov     rax, [rbx+20h]
0x18002a64f  cmp     [rax], rsi
0x18002a652  jnz     short loc_18002A65B
0x18002a654  mov     edx, 6C8h
0x18002a659  jmp     short loc_18002A5FD
0x18002a65b  mov     [rbp+hObject], rsi
0x18002a65f  lea     rdx, [rbp+hObject]
0x18002a663  mov     rcx, [rcx]
0x18002a666  call    NgcOpenUserIdKey
0x18002a66b  mov     edi, eax
0x18002a66d  test    eax, eax
0x18002a66f  jns     short loc_18002A678
0x18002a671  mov     edx, 6CDh
0x18002a676  jmp     short loc_18002A693
0x18002a678  mov     rdx, [rbx+28h]
0x18002a67c  mov     rcx, [rbp+hObject]; this
0x18002a680  mov     rdx, [rdx]; unsigned __int64
0x18002a683  call    ?SetNCryptWindowHandle@NgcUtils@@YAJ_KPEAUHWND__@@@Z; NgcUtils::SetNCryptWindowHandle(unsigned __int64,HWND__ *)
0x18002a688  mov     edi, eax
0x18002a68a  test    eax, eax
0x18002a68c  jns     short loc_18002A6AB
0x18002a68e  mov     edx, 6D1h; void *
0x18002a693  mov     rcx, [rbp+18h]; this
0x18002a697  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002a69e  mov     r9d, eax; char *
0x18002a6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a6a6  jmp     loc_18002A857
0x18002a6ab  mov     rdx, [rbx+30h]
0x18002a6af  mov     rcx, [rbp+hObject]; this
0x18002a6b3  mov     rdx, [rdx]; unsigned __int64
0x18002a6b6  call    ?SetNgcAuthTicket@NgcUtils@@YAJ_K0@Z; NgcUtils::SetNgcAuthTicket(unsigned __int64,unsigned __int64)
0x18002a6bb  mov     edi, eax
0x18002a6bd  test    eax, eax
0x18002a6bf  jns     short loc_18002A6C8
0x18002a6c1  mov     edx, 6D5h
0x18002a6c6  jmp     short loc_18002A693
0x18002a6c8  mov     rdx, [rbx+38h]
0x18002a6cc  mov     rcx, [rbp+hObject]; this
0x18002a6d0  mov     rdx, [rdx]; unsigned __int64
0x18002a6d3  call    ?SetNCryptUiPolicy@NgcUtils@@YAJ_KPEBG@Z; NgcUtils::SetNCryptUiPolicy(unsigned __int64,ushort const *)
0x18002a6d8  mov     edi, eax
0x18002a6da  test    eax, eax
0x18002a6dc  jns     short loc_18002A6E5
0x18002a6de  mov     edx, 6D9h
0x18002a6e3  jmp     short loc_18002A693
0x18002a6e5  mov     rax, [rbx+40h]
0x18002a6e9  mov     r8, [rax]; pbInput
0x18002a6ec  test    r8, r8
0x18002a6ef  jz      short loc_18002A71C
0x18002a6f1  mov     rcx, [rbp+hObject]; hObject
0x18002a6f5  lea     rdx, aNgcuicancellat; "NgcUICancellationId"
0x18002a6fc  mov     r9d, 10h; cbInput
0x18002a702  mov     [rsp+60h+dwFlags], esi; dwFlags
0x18002a706  call    cs:__imp_NCryptSetProperty
0x18002a70c  mov     edi, eax
0x18002a70e  test    eax, eax
0x18002a710  jns     short loc_18002A71C
0x18002a712  mov     edx, 6E2h
0x18002a717  jmp     loc_18002A693
0x18002a71c  mov     rcx, [rbx+48h]
0x18002a720  test    byte ptr [rcx], 1
0x18002a723  jz      short loc_18002A74F
0x18002a725  mov     rcx, [rbp+hObject]; this
0x18002a729  lea     rdx, aNgcdisplayaltc; "NgcDisplayAltCredOption"
0x18002a730  mov     r8d, 1; unsigned __int16 *
0x18002a736  call    ?SetNCryptBoolProperty@NgcUtils@@YAJ_KPEBGH@Z; NgcUtils::SetNCryptBoolProperty(unsigned __int64,ushort const *,int)
0x18002a73b  mov     edi, eax
0x18002a73d  test    eax, eax
0x18002a73f  jns     short loc_18002A74B
0x18002a741  mov     edx, 6EAh
0x18002a746  jmp     loc_18002A693
0x18002a74b  mov     rcx, [rbx+48h]
0x18002a74f  mov     rax, [rbx+30h]
0x18002a753  cmp     [rax], rsi
0x18002a756  jnz     short loc_18002A763
0x18002a758  mov     rax, [rbx+50h]
0x18002a75c  mov     edx, esi
0x18002a75e  cmp     [rax], sil
0x18002a761  jz      short loc_18002A768
0x18002a763  mov     edx, 40h ; '@'
0x18002a768  mov     r8d, [rcx]
0x18002a76b  mov     eax, r8d
0x18002a76e  and     eax, 10000h
0x18002a773  neg     eax
0x18002a775  mov     eax, 20000h
0x18002a77a  sbb     ecx, ecx
0x18002a77c  and     ecx, 0FFFEh
0x18002a782  add     ecx, 2
0x18002a785  or      ecx, edx
0x18002a787  test    eax, r8d
0x18002a78a  jz      short loc_18002A78E
0x18002a78c  or      ecx, eax
0x18002a78e  mov     r9, [rbx+58h]
0x18002a792  lea     rax, [rbp+hMem]
0x18002a796  mov     [rbp+var_20], rax
0x18002a79a  mov     edx, 40000h
0x18002a79f  mov     eax, ecx
0x18002a7a1  mov     [rbp+hMem], rsi
0x18002a7a5  or      eax, edx
0x18002a7a7  mov     [rbp+arg_0], esi
0x18002a7aa  mov     r9, [r9]
0x18002a7ad  test    edx, r8d
0x18002a7b0  mov     r8, [rbx+10h]
0x18002a7b4  mov     rdx, [rbx+8]
0x18002a7b8  cmovz   eax, ecx
0x18002a7bb  lea     rcx, [rbp+arg_0]
0x18002a7bf  mov     [rbp+var_18], rsi
0x18002a7c3  mov     [rsp+60h+var_30], rcx
0x18002a7c8  lea     rcx, [rbp+var_18]
0x18002a7cc  mov     r8d, [r8]
0x18002a7cf  mov     rdx, [rdx]
0x18002a7d2  mov     [rsp+60h+var_38], rcx
0x18002a7d7  mov     rcx, [rbp+hObject]
0x18002a7db  mov     [rbp+var_10], 1
0x18002a7df  mov     [rsp+60h+dwFlags], eax; int
0x18002a7e3  call    SignWithUserIdKeyHandle
0x18002a7e8  lea     rcx, [rbp+var_20]
0x18002a7ec  mov     edi, eax
0x18002a7ee  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002a7f3  test    edi, edi
0x18002a7f5  jns     short loc_18002A824
0x18002a7f7  mov     rcx, [rbp+18h]; this
0x18002a7fb  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002a802  mov     r9d, edi; char *
0x18002a805  mov     edx, 70Fh; void *
0x18002a80a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a80f  mov     rcx, [rbp+hMem]; hMem
0x18002a813  mov     [rbp+hMem], rsi
0x18002a817  test    rcx, rcx
0x18002a81a  jz      short loc_18002A857
0x18002a81c  call    cs:__imp_LocalFree
0x18002a822  jmp     short loc_18002A857
0x18002a824  mov     rax, [rbx+18h]
0x18002a828  mov     rdx, [rbp+hMem]
0x18002a82c  mov     [rbp+hMem], rsi
0x18002a830  mov     rcx, [rax]
0x18002a833  mov     [rcx], rdx
0x18002a836  mov     rax, [rbx+20h]
0x18002a83a  mov     rcx, [rax]
0x18002a83d  mov     eax, [rbp+arg_0]
0x18002a840  mov     [rcx], eax
0x18002a842  mov     rcx, [rbp+hMem]; hMem
0x18002a846  mov     [rbp+hMem], rsi
0x18002a84a  test    rcx, rcx
0x18002a84d  jz      short loc_18002A855
0x18002a84f  call    cs:__imp_LocalFree
0x18002a855  mov     edi, esi
0x18002a857  lea     rcx, [rbp+hObject]
0x18002a85b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18002a860  mov     eax, edi
0x18002a862  mov     rbx, [rsp+60h+arg_18]
0x18002a86a  add     rsp, 60h
0x18002a86e  pop     rdi
0x18002a86f  pop     rsi
0x18002a870  pop     rbp
0x18002a871  retn
```
