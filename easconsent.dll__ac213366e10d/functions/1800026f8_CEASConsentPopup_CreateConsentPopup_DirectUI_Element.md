# CEASConsentPopup::_CreateConsentPopup(DirectUI::Element * *)

- ea: `0x1800026f8`
- end: `0x180002943`
- name: `?_CreateConsentPopup@CEASConsentPopup@@AEAAJPEAPEAVElement@DirectUI@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(CEASConsentPopup *__hidden this, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002020`

## callees

- `0x180001bc8`
- `0x1800026f8`
- `0x180003100`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800027db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800027db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002751`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002751`

## pseudocode

```c
__int64 __fastcall CEASConsentPopup::_CreateConsentPopup(CEASConsentPopup *this, struct DirectUI::Element **a2)
{
  HRESULT v4; // ebx
  LPVOID v5; // rbx
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  __int64 (__fastcall *v8)(LPVOID, char *); // r14
  __int64 v9; // r14
  CEASConsentPopup *v10; // rsi
  __int64 v11; // rcx
  LPVOID v12; // rcx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  CEASConsentPopup *v16; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 131073);
    if ( v4 >= 0 )
    {
      v5 = ppv;
      v6 = (_QWORD *)((char *)this + 32);
      v7 = *((_QWORD *)this + 4);
      v8 = *(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)ppv + 80LL);
      if ( v7 )
      {
        *v6 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v4 = v8(v5, (char *)this + 32);
      if ( v4 >= 0 )
      {
        if ( LoadStringW((HINSTANCE)0x180000000LL, 0x2712u, Buffer, 256) > 0 )
          (*(void (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v6 + 32LL))(*v6, Buffer);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v6 + 352LL))(*v6, *a2);
        if ( v4 >= 0 )
        {
          *a2 = 0;
          v16 = this;
          v14 = 10003;
          v4 = -2147024882;
          Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(v17, &v14, &v16);
          v9 = v17[0];
          if ( v17[0] )
          {
            v17[0] = this;
            v14 = 10004;
            Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(&v16, &v14, v17);
            v10 = v16;
            if ( v16 )
            {
              v11 = *v6;
              v17[0] = v16;
              v17[1] = v9;
              v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v11 + 64LL))(v11, 2, v17);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v6 + 88LL))(*v6, 0);
                if ( v4 >= 0 )
                  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v6 + 120LL))(*v6, 1);
              }
              if ( v10 )
                (*(void (__fastcall **)(CEASConsentPopup *))(*(_QWORD *)v10 + 16LL))(v10);
            }
            if ( v9 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          }
        }
      }
    }
  }
  v12 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800026f8  mov     [rsp-8+arg_10], rbx
0x1800026fd  push    rbp
0x1800026fe  push    rsi
0x1800026ff  push    rdi
0x180002700  push    r14
0x180002702  push    r15
0x180002704  lea     rbp, [rsp-170h]
0x18000270c  sub     rsp, 270h
0x180002713  mov     rax, cs:__security_cookie
0x18000271a  xor     rax, rsp
0x18000271d  mov     [rbp+190h+var_30], rax
0x180002724  mov     r15, rdx
0x180002727  mov     [rsp+290h+var_258], 0
0x180002730  xor     edx, edx; pUnkOuter
0x180002732  lea     rax, [rsp+290h+var_258]
0x180002737  mov     rsi, rcx
0x18000273a  mov     [rsp+290h+ppv], rax; ppv
0x18000273f  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x180002746  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x18000274d  lea     r8d, [rdx+1]; dwClsContext
0x180002751  call    cs:__imp_CoCreateInstance
0x180002757  mov     ebx, eax
0x180002759  test    eax, eax
0x18000275b  js      loc_1800028FC
0x180002761  mov     rcx, [rsp+290h+var_258]
0x180002766  mov     edx, 20001h
0x18000276b  mov     rax, [rcx]
0x18000276e  mov     rax, [rax+18h]
0x180002772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002777  mov     ebx, eax
0x180002779  test    eax, eax
0x18000277b  js      loc_1800028FC
0x180002781  mov     rbx, [rsp+290h+var_258]
0x180002786  lea     rdi, [rsi+20h]
0x18000278a  mov     rcx, [rdi]
0x18000278d  mov     rax, [rbx]
0x180002790  mov     r14, [rax+50h]
0x180002794  test    rcx, rcx
0x180002797  jz      short loc_1800027AC
0x180002799  mov     qword ptr [rdi], 0
0x1800027a0  mov     rdx, [rcx]
0x1800027a3  mov     rax, [rdx+10h]
0x1800027a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ac  mov     rdx, rdi
0x1800027af  mov     rcx, rbx
0x1800027b2  mov     rax, r14
0x1800027b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ba  mov     ebx, eax
0x1800027bc  test    eax, eax
0x1800027be  js      loc_1800028FC
0x1800027c4  mov     r9d, 100h; cchBufferMax
0x1800027ca  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x1800027cf  mov     edx, 2712h; uID
0x1800027d4  lea     rcx, cs:180000000h; hInstance
0x1800027db  call    cs:__imp_LoadStringW
0x1800027e1  test    eax, eax
0x1800027e3  jle     short loc_1800027F9
0x1800027e5  mov     rcx, [rdi]
0x1800027e8  lea     rdx, [rsp+290h+Buffer]
0x1800027ed  mov     rax, [rcx]
0x1800027f0  mov     rax, [rax+20h]
0x1800027f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f9  mov     rcx, [rdi]
0x1800027fc  mov     rdx, [r15]
0x1800027ff  mov     rax, [rcx]
0x180002802  mov     rax, [rax+160h]
0x180002809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280e  mov     ebx, eax
0x180002810  test    eax, eax
0x180002812  js      loc_1800028FC
0x180002818  lea     r8, [rsp+290h+var_250]
0x18000281d  mov     qword ptr [r15], 0
0x180002824  lea     rdx, [rsp+290h+var_260]
0x180002829  mov     [rsp+290h+var_250], rsi
0x18000282e  lea     rcx, [rsp+290h+var_248]
0x180002833  mov     [rsp+290h+var_260], 2713h
0x18000283b  mov     ebx, 8007000Eh
0x180002840  call    ??$Make@VCPopupCommand@@HPEAVCEASConsentPopup@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPopupCommand@@@12@$$QEAH$$QEAPEAVCEASConsentPopup@@@Z; Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(int &&,CEASConsentPopup * &&)
0x180002845  mov     r14, [rsp+290h+var_248]
0x18000284a  test    r14, r14
0x18000284d  jz      loc_1800028FC
0x180002853  lea     r8, [rsp+290h+var_248]
0x180002858  mov     [rsp+290h+var_248], rsi
0x18000285d  lea     rdx, [rsp+290h+var_260]
0x180002862  mov     [rsp+290h+var_260], 2714h
0x18000286a  lea     rcx, [rsp+290h+var_250]
0x18000286f  call    ??$Make@VCPopupCommand@@HPEAVCEASConsentPopup@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPopupCommand@@@12@$$QEAH$$QEAPEAVCEASConsentPopup@@@Z; Microsoft::WRL::Details::Make<CPopupCommand,int,CEASConsentPopup *>(int &&,CEASConsentPopup * &&)
0x180002874  mov     rsi, [rsp+290h+var_250]
0x180002879  test    rsi, rsi
0x18000287c  jz      short loc_1800028E8
0x18000287e  mov     rcx, [rdi]
0x180002881  lea     r8, [rsp+290h+var_248]
0x180002886  mov     [rsp+290h+var_248], rsi
0x18000288b  mov     edx, 2
0x180002890  mov     [rsp+290h+var_240], r14
0x180002895  mov     rax, [rcx]
0x180002898  mov     rax, [rax+40h]
0x18000289c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a1  mov     ebx, eax
0x1800028a3  test    eax, eax
0x1800028a5  js      short loc_1800028D4
0x1800028a7  mov     rcx, [rdi]
0x1800028aa  xor     edx, edx
0x1800028ac  mov     rax, [rcx]
0x1800028af  mov     rax, [rax+58h]
0x1800028b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b8  mov     ebx, eax
0x1800028ba  test    eax, eax
0x1800028bc  js      short loc_1800028D4
0x1800028be  mov     rcx, [rdi]
0x1800028c1  mov     edx, 1
0x1800028c6  mov     rax, [rcx]
0x1800028c9  mov     rax, [rax+78h]
0x1800028cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d2  mov     ebx, eax
0x1800028d4  test    rsi, rsi
0x1800028d7  jz      short loc_1800028E8
0x1800028d9  mov     rax, [rsi]
0x1800028dc  mov     rcx, rsi
0x1800028df  mov     rax, [rax+10h]
0x1800028e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e8  test    r14, r14
0x1800028eb  jz      short loc_1800028FC
0x1800028ed  mov     rax, [r14]
0x1800028f0  mov     rcx, r14
0x1800028f3  mov     rax, [rax+10h]
0x1800028f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fc  mov     rcx, [rsp+290h+var_258]
0x180002901  test    rcx, rcx
0x180002904  jz      short loc_18000291B
0x180002906  mov     [rsp+290h+var_258], 0
0x18000290f  mov     rax, [rcx]
0x180002912  mov     rax, [rax+10h]
0x180002916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291b  mov     eax, ebx
0x18000291d  mov     rcx, [rbp+190h+var_30]
0x180002924  xor     rcx, rsp; StackCookie
0x180002927  call    __security_check_cookie
0x18000292c  mov     rbx, [rsp+290h+arg_10]
0x180002934  add     rsp, 270h
0x18000293b  pop     r15
0x18000293d  pop     r14
0x18000293f  pop     rdi
0x180002940  pop     rsi
0x180002941  pop     rbp
0x180002942  retn
```
