# CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)

- ea: `0x1001c380`
- end: `0x1001c529`
- name: `?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z`
- size: `425`
- prototype: `static int __stdcall(int, int, const struct _GUID *, int)`
- caller_count: `147`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1000c0d0`
- `0x1000ce70`
- `0x1000cff0`
- `0x1000d150`
- `0x1000d5b0`
- `0x1000d6c0`
- `0x1000d7d0`
- `0x1000d8e0`
- `0x1000da40`
- `0x1000ddb0`
- `0x1000e140`
- `0x1000fcf0`
- `0x100107b0`
- `0x10010b50`
- `0x10010f80`
- `0x10011130`
- `0x10011260`
- `0x10011380`
- `0x10011530`
- `0x10011740`
- `0x100118b0`
- `0x10011d40`
- `0x10013890`
- `0x10014c10`
- `0x10014cd0`
- `0x10014d90`
- `0x100152a0`
- `0x100153e0`
- `0x100155d0`
- `0x100157a0`
- `0x10016690`
- `0x10017160`
- `0x100174a0`
- `0x10017580`
- `0x100176f0`
- `0x10019070`
- `0x1001a2a0`
- `0x1001a700`
- `0x1001a7b0`
- `0x1001a970`
- `0x1001af60`
- `0x1001bd60`
- `0x1001bdc0`
- `0x1001d7f0`
- `0x1001df20`
- `0x1001e350`
- `0x1001ebc0`
- `0x10025180`
- `0x10025b50`
- `0x10025bf0`

## callees

- `0x1000ed00`
- `0x1001c380`
- `0x1001c6d0`
- `0x1004d420`

## import_xrefs

- `OLEAUT32!__imp__VariantInit@4` at `0x1001c470`
- `OLEAUT32!__imp__VariantInit@4` at `0x1001c470`
- `OLEAUT32!__imp__GetErrorInfo@8` at `0x1001c3ed`
- `OLEAUT32!__imp__GetErrorInfo@8` at `0x1001c3ed`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001c4cf`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001c4cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1001c40c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1001c40c`

## pseudocode

```c
HRESULT __userpurge CExtError::SendHRtoOLEAuto@<eax>(
        int a1@<edx>,
        __int128 *a2,
        unsigned __int16 a3,
        const struct _GUID *a4,
        int a5)
{
  IErrorInfo *v7; // eax
  HRESULT Instance; // edi
  int v9; // edi
  unsigned int i; // esi
  __int128 v11; // xmm0
  struct tagDISPPARAMS *v12; // [esp+0h] [ebp-58h]
  int v13; // [esp+20h] [ebp-38h] BYREF
  IErrorInfo *pperrinfo; // [esp+24h] [ebp-34h] BYREF
  _DWORD v15[2]; // [esp+28h] [ebp-30h] BYREF
  GUID v16; // [esp+30h] [ebp-28h]
  __int128 v17; // [esp+40h] [ebp-18h]
  int v18; // [esp+50h] [ebp-8h]

  pperrinfo = 0;
  v13 = 0;
  if ( a1 == -2147024882 )
    return -2147467259;
  GetErrorInfo(0, &pperrinfo);
  v7 = pperrinfo;
  if ( pperrinfo
    || (Instance = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&pperrinfo),
        Instance >= 0)
    && (v7 = pperrinfo) != 0 )
  {
    ((void (__thiscall *)(HRESULT (__stdcall *)(IErrorInfo *, const IID *const, void **), IErrorInfo *, GUID *, int *))v7->lpVtbl->QueryInterface)(
      v7->lpVtbl->QueryInterface,
      v7,
      &IID_IErrorRecords,
      &v13);
    v9 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(*(_DWORD *)(*(_DWORD *)Sys + 12), Sys, 96);
    if ( v9 )
    {
      for ( i = 0; i < 6; ++i )
        VariantInit((VARIANTARG *)(v9 + 16 * i));
      v15[1] = a3;
      v16 = CLSID_JOLT;
      v11 = *a2;
      v15[0] = a1;
      v18 = 0;
      v17 = v11;
      Instance = (*(int (__thiscall **)(_DWORD, int, _DWORD *, int, _DWORD, _DWORD, _DWORD))(*(_DWORD *)v13 + 12))(
                   *(_DWORD *)(*(_DWORD *)v13 + 12),
                   v13,
                   v15,
                   0x10000000,
                   0,
                   0,
                   0);
      if ( Instance >= 0 )
        Instance = SetErrorInfo(0, pperrinfo);
    }
    else
    {
      Instance = -2147024882;
    }
  }
  CError::ClearDispParams(v12);
  if ( v13 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v13 + 8))(*(_DWORD *)(*(_DWORD *)v13 + 8), v13);
    v13 = 0;
  }
  if ( pperrinfo )
    ((void (__thiscall *)(ULONG (__stdcall *)(IErrorInfo *), IErrorInfo *))pperrinfo->lpVtbl->Release)(
      pperrinfo->lpVtbl->Release,
      pperrinfo);
  return Instance;
}

```

## disassembly

```asm
0x1001c380  mov     edi, edi
0x1001c382  push    ebp
0x1001c383  mov     ebp, esp
0x1001c385  sub     esp, 4Ch
0x1001c388  mov     eax, ___security_cookie
0x1001c38d  xor     eax, ebp
0x1001c38f  mov     [ebp+var_4], eax
0x1001c392  mov     eax, [ebp+arg_0]
0x1001c395  push    ebx
0x1001c396  mov     ebx, edx
0x1001c398  mov     [ebp+var_3C], eax
0x1001c39b  mov     [ebp+pperrinfo], 0
0x1001c3a2  mov     [ebp+var_38], 0
0x1001c3a9  mov     [ebp+var_44], 6
0x1001c3b0  mov     [ebp+var_48], 0
0x1001c3b7  mov     [ebp+var_40], 0
0x1001c3be  mov     [ebp+var_4C], 0
0x1001c3c5  push    esi
0x1001c3c6  push    edi; struct tagDISPPARAMS *
0x1001c3c7  cmp     ebx, 8007000Eh
0x1001c3cd  jnz     short loc_1001C3E7
0x1001c3cf  mov     eax, 80004005h
0x1001c3d4  pop     edi
0x1001c3d5  pop     esi
0x1001c3d6  pop     ebx
0x1001c3d7  mov     ecx, [ebp+var_4]
0x1001c3da  xor     ecx, ebp; StackCookie
0x1001c3dc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c3e1  mov     esp, ebp
0x1001c3e3  pop     ebp
0x1001c3e4  retn    8
0x1001c3e7  lea     eax, [ebp+pperrinfo]
0x1001c3ea  push    eax; pperrinfo
0x1001c3eb  push    0; dwReserved
0x1001c3ed  call    ds:__imp__GetErrorInfo@8; GetErrorInfo(x,x)
0x1001c3f3  mov     eax, [ebp+pperrinfo]
0x1001c3f6  test    eax, eax
0x1001c3f8  jnz     short loc_1001C427
0x1001c3fa  lea     eax, [ebp+pperrinfo]
0x1001c3fd  push    eax; ppv
0x1001c3fe  push    offset _IID_IErrorInfo; riid
0x1001c403  push    1; dwClsContext
0x1001c405  push    0; pUnkOuter
0x1001c407  push    offset ?CLSID_EXTENDEDERRORINFO@@3U_GUID@@B; rclsid
0x1001c40c  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1001c412  mov     edi, eax
0x1001c414  test    edi, edi
0x1001c416  js      loc_1001C4D7
0x1001c41c  mov     eax, [ebp+pperrinfo]
0x1001c41f  test    eax, eax
0x1001c421  jz      loc_1001C4D7
0x1001c427  mov     esi, [eax]
0x1001c429  lea     ecx, [ebp+var_38]
0x1001c42c  push    ecx
0x1001c42d  push    offset _IID_IErrorRecords
0x1001c432  push    eax
0x1001c433  mov     esi, [esi]
0x1001c435  mov     ecx, esi
0x1001c437  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c43d  call    esi
0x1001c43f  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1001c444  push    60h ; '`'
0x1001c446  push    eax
0x1001c447  mov     ecx, [eax]
0x1001c449  mov     esi, [ecx+0Ch]
0x1001c44c  mov     ecx, esi
0x1001c44e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c454  call    esi
0x1001c456  mov     edi, eax
0x1001c458  mov     [ebp+var_4C], edi
0x1001c45b  test    edi, edi
0x1001c45d  jnz     short loc_1001C466
0x1001c45f  mov     edi, 8007000Eh
0x1001c464  jmp     short loc_1001C4D7
0x1001c466  xor     esi, esi
0x1001c468  mov     eax, esi
0x1001c46a  shl     eax, 4
0x1001c46d  add     eax, edi
0x1001c46f  push    eax; pvarg
0x1001c470  call    ds:__imp__VariantInit@4; VariantInit(x)
0x1001c476  inc     esi
0x1001c477  cmp     esi, 6
0x1001c47a  jb      short loc_1001C468
0x1001c47c  movzx   eax, word ptr [ebp+arg_4]
0x1001c480  movups  xmm0, xmmword ptr ds:?CLSID_JOLT@@3U_GUID@@B.Data1; _GUID const CLSID_JOLT ...
0x1001c487  mov     ecx, [ebp+var_38]
0x1001c48a  mov     [ebp+var_2C], eax
0x1001c48d  mov     eax, [ebp+var_3C]
0x1001c490  movups  [ebp+var_28], xmm0
0x1001c494  push    0
0x1001c496  push    0
0x1001c498  movups  xmm0, xmmword ptr [eax]
0x1001c49b  mov     [ebp+var_30], ebx
0x1001c49e  mov     [ebp+var_8], 0
0x1001c4a5  movups  [ebp+var_18], xmm0
0x1001c4a9  mov     eax, [ecx]
0x1001c4ab  push    0
0x1001c4ad  push    10000000h
0x1001c4b2  mov     esi, [eax+0Ch]
0x1001c4b5  lea     eax, [ebp+var_30]
0x1001c4b8  push    eax
0x1001c4b9  push    ecx
0x1001c4ba  mov     ecx, esi
0x1001c4bc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c4c2  call    esi
0x1001c4c4  mov     edi, eax
0x1001c4c6  test    edi, edi
0x1001c4c8  js      short loc_1001C4D7
0x1001c4ca  push    [ebp+pperrinfo]; perrinfo
0x1001c4cd  push    0; dwReserved
0x1001c4cf  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001c4d5  mov     edi, eax
0x1001c4d7  lea     ecx, [ebp+var_4C]
0x1001c4da  call    ?ClearDispParams@CError@@SGXPAUtagDISPPARAMS@@@Z; CError::ClearDispParams(tagDISPPARAMS *)
0x1001c4df  mov     ecx, [ebp+var_38]
0x1001c4e2  test    ecx, ecx
0x1001c4e4  jz      short loc_1001C4FD
0x1001c4e6  mov     eax, [ecx]
0x1001c4e8  push    ecx
0x1001c4e9  mov     esi, [eax+8]
0x1001c4ec  mov     ecx, esi
0x1001c4ee  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c4f4  call    esi
0x1001c4f6  mov     [ebp+var_38], 0
0x1001c4fd  mov     ecx, [ebp+pperrinfo]
0x1001c500  test    ecx, ecx
0x1001c502  jz      short loc_1001C514
0x1001c504  mov     eax, [ecx]
0x1001c506  push    ecx
0x1001c507  mov     esi, [eax+8]
0x1001c50a  mov     ecx, esi
0x1001c50c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c512  call    esi
0x1001c514  mov     ecx, [ebp+var_4]
0x1001c517  mov     eax, edi
0x1001c519  pop     edi
0x1001c51a  pop     esi
0x1001c51b  xor     ecx, ebp; StackCookie
0x1001c51d  pop     ebx
0x1001c51e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c523  mov     esp, ebp
0x1001c525  pop     ebp
0x1001c526  retn    8
```
