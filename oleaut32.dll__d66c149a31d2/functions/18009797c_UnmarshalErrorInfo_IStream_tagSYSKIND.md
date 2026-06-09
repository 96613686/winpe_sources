# UnmarshalErrorInfo(IStream *,tagSYSKIND)

- ea: `0x18009797c`
- end: `0x180097c00`
- name: `?UnmarshalErrorInfo@@YAJPEAUIStream@@W4tagSYSKIND@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(struct IStream *, enum tagSYSKIND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180079d78`

## callees

- `0x180021dc0`
- `0x18004d900`
- `0x1800964a8`
- `0x18009797c`
- `0x18009c010`

## import_xrefs

- `combase!SetErrorInfo` at `0x180097a1b`
- `combase!SetErrorInfo` at `0x180097b88`
- `combase!SetErrorInfo` at `0x180097a1b`
- `combase!SetErrorInfo` at `0x180097b88`
- `combase!CreateErrorInfo` at `0x180097af0`
- `combase!CreateErrorInfo` at `0x180097af0`

## pseudocode

```c
__int64 __fastcall UnmarshalErrorInfo(struct IStream *a1, enum tagSYSKIND a2)
{
  __int64 v2; // rax
  unsigned __int16 *v3; // rsi
  __int64 (__fastcall *v5)(struct IStream *, int *, __int64, int *); // rax
  int v7; // ebx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(struct IStream *, unsigned int *, __int64, int *); // rax
  __int64 v11; // rax
  HRESULT v12; // eax
  int v13; // [rsp+30h] [rbp-50h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-40h] BYREF
  int v16; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-30h] BYREF
  BSTR v19; // [rsp+58h] [rbp-28h] BYREF
  IErrorInfo *perrinfo; // [rsp+60h] [rbp-20h] BYREF
  GUID v21; // [rsp+68h] [rbp-18h] BYREF

  v2 = *(_QWORD *)a1;
  v3 = 0;
  v16 = 0;
  v15 = 0;
  perrinfo = 0;
  v5 = *(__int64 (__fastcall **)(struct IStream *, int *, __int64, int *))(v2 + 24);
  pperrinfo = 0;
  bstrString = 0;
  v21 = 0;
  v19 = 0;
  v17 = 0;
  v13 = 0;
  v7 = v5(a1, &v16, 4, &v13);
  if ( v7 < 0 )
    goto LABEL_18;
  if ( v13 != 4 )
    goto LABEL_9;
  if ( !v16 )
  {
    SetErrorInfo(0, 0);
    return 0;
  }
  v9 = *(_QWORD *)a1;
  v15 = 0;
  v13 = 0;
  v10 = *(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64, int *))(v9 + 24);
  v21 = GUID_NULL;
  v7 = v10(a1, &v15, 4, &v13);
  if ( v7 >= 0 )
  {
    if ( v13 != 4 )
    {
LABEL_9:
      v7 = -2147287010;
      goto LABEL_18;
    }
    v11 = *(_QWORD *)a1;
    v13 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IStream *, GUID *, __int64, int *))(v11 + 24))(a1, &v21, 16, &v13);
    if ( v7 >= 0 )
    {
      if ( v13 == 16 )
      {
        v7 = BstrRead(a1, &bstrString, a2);
        if ( v7 >= 0 )
        {
          v7 = BstrRead(a1, &v19, a2);
          if ( v7 >= 0 )
          {
            v7 = BstrRead(a1, &v17, a2);
            if ( v7 < 0 )
            {
              v3 = v17;
            }
            else
            {
              v12 = CreateErrorInfo(&pperrinfo);
              v3 = v17;
              if ( !v12 )
              {
                ((void (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &v21);
                ((void (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetSource)(pperrinfo, bstrString);
                ((void (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v19);
                ((void (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetHelpFile)(
                  pperrinfo,
                  v3);
                ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, v15);
                if ( !((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                        pperrinfo,
                        &IID_IErrorInfo,
                        &perrinfo) )
                  SetErrorInfo(0, perrinfo);
              }
              v7 = 0;
            }
          }
        }
        goto LABEL_18;
      }
      goto LABEL_9;
    }
  }
LABEL_18:
  SysFreeString(bstrString);
  SysFreeString(v19);
  SysFreeString(v3);
  if ( pperrinfo )
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009797c  mov     [rsp-18h+arg_8], rbx
0x180097981  mov     [rsp-18h+arg_10], rsi
0x180097986  push    rbp
0x180097987  push    rdi
0x180097988  push    r14
0x18009798a  mov     rbp, rsp
0x18009798d  sub     rsp, 80h
0x180097994  mov     rax, cs:__security_cookie
0x18009799b  xor     rax, rsp
0x18009799e  mov     [rbp+var_8], rax
0x1800979a2  mov     rax, [rcx]
0x1800979a5  lea     r9, [rbp+var_50]
0x1800979a9  xor     esi, esi
0x1800979ab  mov     [rbp+var_3C], 0
0x1800979b2  mov     r14d, edx
0x1800979b5  mov     [rbp+var_40], 0
0x1800979bc  xorps   xmm0, xmm0
0x1800979bf  mov     [rbp+perrinfo], 0
0x1800979c7  mov     rax, [rax+18h]
0x1800979cb  lea     rdx, [rbp+var_3C]
0x1800979cf  lea     r8d, [rsi+4]
0x1800979d3  mov     [rbp+pperrinfo], 0
0x1800979db  mov     rdi, rcx
0x1800979de  mov     [rbp+bstrString], 0
0x1800979e6  movups  [rbp+var_18], xmm0
0x1800979ea  mov     [rbp+var_28], 0
0x1800979f2  mov     [rbp+var_38], rsi
0x1800979f6  mov     [rbp+var_50], esi
0x1800979f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800979fe  mov     ebx, eax
0x180097a00  test    eax, eax
0x180097a02  js      loc_180097B96
0x180097a08  cmp     [rbp+var_50], 4
0x180097a0c  jnz     loc_180097A97
0x180097a12  cmp     [rbp+var_3C], esi
0x180097a15  jnz     short loc_180097A28
0x180097a17  xor     edx, edx; perrinfo
0x180097a19  xor     ecx, ecx; dwReserved
0x180097a1b  call    cs:__imp_SetErrorInfo
0x180097a21  xor     eax, eax
0x180097a23  jmp     loc_180097BDC
0x180097a28  mov     rax, [rdi]
0x180097a2b  lea     r9, [rbp+var_50]
0x180097a2f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180097a36  mov     r8d, 4
0x180097a3c  mov     [rbp+var_40], esi
0x180097a3f  lea     rdx, [rbp+var_40]
0x180097a43  mov     [rbp+var_50], esi
0x180097a46  mov     rax, [rax+18h]
0x180097a4a  mov     rcx, rdi
0x180097a4d  movdqu  [rbp+var_18], xmm0
0x180097a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a57  mov     ebx, eax
0x180097a59  test    eax, eax
0x180097a5b  js      loc_180097B96
0x180097a61  cmp     [rbp+var_50], 4
0x180097a65  jnz     short loc_180097A97
0x180097a67  mov     rax, [rdi]
0x180097a6a  lea     r9, [rbp+var_50]
0x180097a6e  mov     r8d, 10h
0x180097a74  mov     [rbp+var_50], esi
0x180097a77  lea     rdx, [rbp+var_18]
0x180097a7b  mov     rcx, rdi
0x180097a7e  mov     rax, [rax+18h]
0x180097a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a87  mov     ebx, eax
0x180097a89  test    eax, eax
0x180097a8b  js      loc_180097B96
0x180097a91  cmp     [rbp+var_50], 10h
0x180097a95  jz      short loc_180097AA1
0x180097a97  mov     ebx, 8003001Eh
0x180097a9c  jmp     loc_180097B96
0x180097aa1  mov     r8d, r14d; enum tagSYSKIND
0x180097aa4  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180097aa8  mov     rcx, rdi; struct IStream *
0x180097aab  call    ?BstrRead@@YAJPEAUIStream@@PEAPEAGW4tagSYSKIND@@@Z; BstrRead(IStream *,ushort * *,tagSYSKIND)
0x180097ab0  mov     ebx, eax
0x180097ab2  test    eax, eax
0x180097ab4  js      loc_180097B96
0x180097aba  mov     r8d, r14d; enum tagSYSKIND
0x180097abd  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x180097ac1  mov     rcx, rdi; struct IStream *
0x180097ac4  call    ?BstrRead@@YAJPEAUIStream@@PEAPEAGW4tagSYSKIND@@@Z; BstrRead(IStream *,ushort * *,tagSYSKIND)
0x180097ac9  mov     ebx, eax
0x180097acb  test    eax, eax
0x180097acd  js      loc_180097B96
0x180097ad3  mov     r8d, r14d; enum tagSYSKIND
0x180097ad6  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x180097ada  mov     rcx, rdi; struct IStream *
0x180097add  call    ?BstrRead@@YAJPEAUIStream@@PEAPEAGW4tagSYSKIND@@@Z; BstrRead(IStream *,ushort * *,tagSYSKIND)
0x180097ae2  mov     ebx, eax
0x180097ae4  test    eax, eax
0x180097ae6  js      loc_180097B92
0x180097aec  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x180097af0  call    cs:__imp_CreateErrorInfo
0x180097af6  mov     rsi, [rbp+var_38]
0x180097afa  test    eax, eax
0x180097afc  jnz     loc_180097B8E
0x180097b02  mov     rcx, [rbp+pperrinfo]
0x180097b06  lea     rdx, [rbp+var_18]
0x180097b0a  mov     rax, [rcx]
0x180097b0d  mov     rax, [rax+18h]
0x180097b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b16  mov     rcx, [rbp+pperrinfo]
0x180097b1a  mov     rdx, [rbp+bstrString]
0x180097b1e  mov     rax, [rcx]
0x180097b21  mov     rax, [rax+20h]
0x180097b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b2a  mov     rcx, [rbp+pperrinfo]
0x180097b2e  mov     rdx, [rbp+var_28]
0x180097b32  mov     rax, [rcx]
0x180097b35  mov     rax, [rax+28h]
0x180097b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b3e  mov     rcx, [rbp+pperrinfo]
0x180097b42  mov     rdx, rsi
0x180097b45  mov     rax, [rcx]
0x180097b48  mov     rax, [rax+30h]
0x180097b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b51  mov     rcx, [rbp+pperrinfo]
0x180097b55  mov     edx, [rbp+var_40]
0x180097b58  mov     rax, [rcx]
0x180097b5b  mov     rax, [rax+38h]
0x180097b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b64  mov     rcx, [rbp+pperrinfo]
0x180097b68  lea     r8, [rbp+perrinfo]
0x180097b6c  lea     rdx, IID_IErrorInfo
0x180097b73  mov     rax, [rcx]
0x180097b76  mov     rax, [rax]
0x180097b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b7e  test    eax, eax
0x180097b80  jnz     short loc_180097B8E
0x180097b82  mov     rdx, [rbp+perrinfo]; perrinfo
0x180097b86  xor     ecx, ecx; dwReserved
0x180097b88  call    cs:__imp_SetErrorInfo
0x180097b8e  xor     ebx, ebx
0x180097b90  jmp     short loc_180097B96
0x180097b92  mov     rsi, [rbp+var_38]
0x180097b96  mov     rcx, [rbp+bstrString]; bstrString
0x180097b9a  call    SysFreeString
0x180097b9f  mov     rcx, [rbp+var_28]; bstrString
0x180097ba3  call    SysFreeString
0x180097ba8  mov     rcx, rsi; bstrString
0x180097bab  call    SysFreeString
0x180097bb0  mov     rcx, [rbp+pperrinfo]
0x180097bb4  test    rcx, rcx
0x180097bb7  jz      short loc_180097BC5
0x180097bb9  mov     rax, [rcx]
0x180097bbc  mov     rax, [rax+10h]
0x180097bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097bc5  mov     rcx, [rbp+perrinfo]
0x180097bc9  test    rcx, rcx
0x180097bcc  jz      short loc_180097BDA
0x180097bce  mov     rax, [rcx]
0x180097bd1  mov     rax, [rax+10h]
0x180097bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097bda  mov     eax, ebx
0x180097bdc  mov     rcx, [rbp+var_8]
0x180097be0  xor     rcx, rsp; StackCookie
0x180097be3  call    __security_check_cookie
0x180097be8  lea     r11, [rsp+80h+var_s0]
0x180097bf0  mov     rbx, [r11+28h]
0x180097bf4  mov     rsi, [r11+30h]
0x180097bf8  mov     rsp, r11
0x180097bfb  pop     r14
0x180097bfd  pop     rdi
0x180097bfe  pop     rbp
0x180097bff  retn
```
