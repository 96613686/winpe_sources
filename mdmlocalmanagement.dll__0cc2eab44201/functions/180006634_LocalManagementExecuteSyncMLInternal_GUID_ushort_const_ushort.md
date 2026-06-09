# LocalManagementExecuteSyncMLInternal(_GUID &,ushort const *,ushort * *)

- ea: `0x180006634`
- end: `0x18000685f`
- name: `?LocalManagementExecuteSyncMLInternal@@YAJAEAU_GUID@@PEBGPEAPEAG@Z`
- size: `555`
- prototype: `__int64 __fastcall(GUID *rguid, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800058e0`

## callees

- `0x180001660`
- `0x180006000`
- `0x180006634`
- `0x180007010`

## import_xrefs

- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800066b2`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800066b2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800066d5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800066d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000676f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000676f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000681e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000681e`

## string_xrefs

- `0x18000671c`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LocalManagementExecuteSyncMLInternal(GUID *rguid, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HRESULT CurrentUserSid; // ebx
  unsigned int v7; // edx
  unsigned int v8; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v13; // [rsp+48h] [rbp-B8h]
  HLOCAL v14; // [rsp+58h] [rbp-A8h]
  _OWORD v15[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+80h] [rbp-80h]
  __int128 v17; // [rsp+90h] [rbp-70h] BYREF
  __int128 v18; // [rsp+A0h] [rbp-60h]
  const wchar_t **v19; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v20[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v21; // [rsp+C8h] [rbp-38h]
  __int128 v22; // [rsp+D8h] [rbp-28h]
  OLECHAR sz; // [rsp+F0h] [rbp-10h] BYREF
  char v24; // [rsp+F2h] [rbp-Eh] BYREF
  __int16 v25; // [rsp+13Ah] [rbp+3Ah]

  ppv = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  memset(v15, 0, sizeof(v15));
  v16 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  v22 = 0;
  hMem = 0;
  CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
  if ( CurrentUserSid >= 0 )
  {
    if ( StringFromGUID2(rguid, &sz, 39) )
    {
      v12 = L"OMADM::AccountID";
      if ( sz == 123 )
      {
        *(_QWORD *)&v13 = &v24;
        v25 = 0;
      }
      else
      {
        *(_QWORD *)&v13 = &sz;
      }
      *((_QWORD *)&v13 + 1) = L"OMADM::TargetedUserSID";
      v14 = hMem;
      *((_QWORD *)&v17 + 1) = L"Local_Management";
      HIDWORD(v18) = 2;
      v19 = &v12;
      CurrentUserSid = CoCreateInstance(
                         &GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8,
                         0,
                         1u,
                         &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
                         &ppv);
      if ( CurrentUserSid >= 0 )
      {
        CurrentUserSid = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, &v17, 40);
        if ( CurrentUserSid >= 0 )
        {
          DWORD2(v15[0]) = 1;
          *(_QWORD *)&v15[0] = a2;
          *(_QWORD *)((char *)v15 + 12) = 1;
          DWORD1(v16) = 0;
          CurrentUserSid = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, __int64))(*(_QWORD *)ppv + 32LL))(ppv, v15, 48);
          if ( CurrentUserSid >= 0 )
          {
            CurrentUserSid = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 **, __int64))(*(_QWORD *)ppv + 40LL))(
                               ppv,
                               v20,
                               48);
            if ( CurrentUserSid >= 0 )
              CurrentUserSid = AssembleOutputXML(v8, v7, v20[1], a3);
          }
        }
      }
    }
    else
    {
      CurrentUserSid = -2147418113;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180006634  push    rbp
0x180006636  push    rbx
0x180006637  push    rsi
0x180006638  push    rdi
0x180006639  push    r14
0x18000663b  lea     rbp, [rsp-50h]
0x180006640  sub     rsp, 150h
0x180006647  mov     rax, cs:__security_cookie
0x18000664e  xor     rax, rsp
0x180006651  mov     [rbp+70h+var_30], rax
0x180006655  mov     rsi, r8
0x180006658  mov     r14, rdx
0x18000665b  mov     rdi, rcx
0x18000665e  mov     [rsp+170h+var_140], 0
0x180006667  mov     [rsp+170h+var_130], 0
0x180006670  xorps   xmm0, xmm0
0x180006673  xor     eax, eax
0x180006675  movups  [rsp+170h+var_128], xmm0
0x18000667a  mov     [rsp+170h+var_118], rax
0x18000667f  xorps   xmm1, xmm1
0x180006682  movups  [rbp+70h+var_E0], xmm1
0x180006686  movups  [rbp+70h+var_D0], xmm1
0x18000668a  mov     [rbp+70h+var_C0], rax
0x18000668e  movups  [rsp+170h+var_110], xmm0
0x180006693  movups  [rsp+170h+var_100], xmm0
0x180006698  movups  [rbp+70h+var_F0], xmm0
0x18000669c  movups  xmmword ptr [rbp+70h+var_B8], xmm1
0x1800066a0  movups  [rbp+70h+var_A8], xmm1
0x1800066a4  movups  [rbp+70h+var_98], xmm1
0x1800066a8  mov     [rsp+170h+hMem], rax
0x1800066ad  lea     rcx, [rsp+170h+hMem]
0x1800066b2  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x1800066b9  nop     dword ptr [rax+rax+00h]
0x1800066be  mov     ebx, eax
0x1800066c0  test    eax, eax
0x1800066c2  js      loc_180006814
0x1800066c8  mov     r8d, 27h ; '''; cchMax
0x1800066ce  lea     rdx, [rbp+70h+sz]; lpsz
0x1800066d2  mov     rcx, rdi; rguid
0x1800066d5  call    cs:__imp_StringFromGUID2
0x1800066dc  nop     dword ptr [rax+rax+00h]
0x1800066e1  test    eax, eax
0x1800066e3  jnz     short loc_1800066EF
0x1800066e5  mov     ebx, 8000FFFFh
0x1800066ea  jmp     loc_180006814
0x1800066ef  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x1800066f6  mov     [rsp+170h+var_130], rax
0x1800066fb  cmp     [rbp+70h+sz], 7Bh ; '{'
0x180006700  jnz     short loc_180006713
0x180006702  lea     rax, [rbp+70h+var_7E]
0x180006706  mov     qword ptr [rsp+170h+var_128], rax
0x18000670b  xor     eax, eax
0x18000670d  mov     [rbp+70h+var_36], ax
0x180006711  jmp     short loc_18000671C
0x180006713  lea     rax, [rbp+70h+sz]
0x180006717  mov     qword ptr [rsp+170h+var_128], rax
0x18000671c  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180006723  mov     qword ptr [rsp+170h+var_128+8], rax
0x180006728  mov     rax, [rsp+170h+hMem]
0x18000672d  mov     [rsp+170h+var_118], rax
0x180006732  lea     rax, aLocalManagemen; "Local_Management"
0x180006739  mov     qword ptr [rbp+70h+var_E0+8], rax
0x18000673d  mov     dword ptr [rbp+70h+var_D0+0Ch], 2
0x180006744  lea     rax, [rsp+170h+var_130]
0x180006749  mov     [rbp+70h+var_C0], rax
0x18000674d  lea     rax, [rsp+170h+var_140]
0x180006752  mov     [rsp+170h+ppv], rax; ppv
0x180006757  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x18000675e  mov     edi, 1
0x180006763  mov     r8d, edi; dwClsContext
0x180006766  xor     edx, edx; pUnkOuter
0x180006768  lea     rcx, _GUID_e3784839_6bd5_4702_a7b0_59c7592fb7b8; rclsid
0x18000676f  call    cs:__imp_CoCreateInstance
0x180006776  nop     dword ptr [rax+rax+00h]
0x18000677b  mov     ebx, eax
0x18000677d  test    eax, eax
0x18000677f  js      loc_180006814
0x180006785  mov     rcx, [rsp+170h+var_140]
0x18000678a  mov     rax, [rcx]
0x18000678d  lea     r8d, [rdi+27h]
0x180006791  lea     rdx, [rbp+70h+var_E0]
0x180006795  mov     rax, [rax+18h]
0x180006799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000679e  mov     ebx, eax
0x1800067a0  test    eax, eax
0x1800067a2  js      short loc_180006814
0x1800067a4  mov     dword ptr [rsp+170h+var_110+8], edi
0x1800067a8  mov     qword ptr [rsp+170h+var_110], r14
0x1800067ad  mov     qword ptr [rsp+170h+var_110+0Ch], rdi
0x1800067b2  mov     dword ptr [rbp+70h+var_F0+4], 0
0x1800067b9  mov     rcx, [rsp+170h+var_140]
0x1800067be  mov     rax, [rcx]
0x1800067c1  mov     [rsp+170h+ppv], 0
0x1800067ca  xor     r9d, r9d
0x1800067cd  lea     edi, [r9+30h]
0x1800067d1  mov     r8d, edi
0x1800067d4  lea     rdx, [rsp+170h+var_110]
0x1800067d9  mov     rax, [rax+20h]
0x1800067dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e2  mov     ebx, eax
0x1800067e4  test    eax, eax
0x1800067e6  js      short loc_180006814
0x1800067e8  mov     rcx, [rsp+170h+var_140]
0x1800067ed  mov     rax, [rcx]
0x1800067f0  mov     r8d, edi
0x1800067f3  lea     rdx, [rbp+70h+var_B8]
0x1800067f7  mov     rax, [rax+28h]
0x1800067fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006800  mov     ebx, eax
0x180006802  test    eax, eax
0x180006804  js      short loc_180006814
0x180006806  mov     r9, rsi; unsigned __int16 **
0x180006809  mov     r8, [rbp+70h+var_B8+8]; unsigned __int16 *
0x18000680d  call    ?AssembleOutputXML@@YAJKKPEBGPEAPEAG@Z; AssembleOutputXML(ulong,ulong,ushort const *,ushort * *)
0x180006812  mov     ebx, eax
0x180006814  mov     rcx, [rsp+170h+hMem]; hMem
0x180006819  test    rcx, rcx
0x18000681c  jz      short loc_18000682B
0x18000681e  call    cs:__imp_LocalFree
0x180006825  nop     dword ptr [rax+rax+00h]
0x18000682a  nop
0x18000682b  mov     rcx, [rsp+170h+var_140]
0x180006830  test    rcx, rcx
0x180006833  jz      short loc_180006842
0x180006835  mov     rax, [rcx]
0x180006838  mov     rax, [rax+10h]
0x18000683c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006841  nop
0x180006842  mov     eax, ebx
0x180006844  mov     rcx, [rbp+70h+var_30]
0x180006848  xor     rcx, rsp; StackCookie
0x18000684b  call    __security_check_cookie
0x180006850  add     rsp, 150h
0x180006857  pop     r14
0x180006859  pop     rdi
0x18000685a  pop     rsi
0x18000685b  pop     rbx
0x18000685c  pop     rbp
0x18000685d  retn
```
