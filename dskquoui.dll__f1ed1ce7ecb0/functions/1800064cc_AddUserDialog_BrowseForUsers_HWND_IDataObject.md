# AddUserDialog::BrowseForUsers(HWND__ *,IDataObject * *)

- ea: `0x1800064cc`
- end: `0x1800067ac`
- name: `?BrowseForUsers@AddUserDialog@@AEAAJPEAUHWND__@@PEAPEAUIDataObject@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(AddUserDialog *__hidden this, HWND, struct IDataObject **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d5f8`

## callees

- `0x180001510`
- `0x1800064cc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006529`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006529`

## pseudocode

```c
__int64 __fastcall AddUserDialog::BrowseForUsers(AddUserDialog *this, HWND a2, struct IDataObject **a3)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v8[7]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v9[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v10; // [rsp+90h] [rbp-70h]
  int v11; // [rsp+A0h] [rbp-60h]
  int v12; // [rsp+A8h] [rbp-58h]
  int v13; // [rsp+ACh] [rbp-54h]
  int v14; // [rsp+B0h] [rbp-50h]
  int v15; // [rsp+B4h] [rbp-4Ch]
  int v16; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v17; // [rsp+BCh] [rbp-44h]
  int v18; // [rsp+C4h] [rbp-3Ch]
  __int64 v19; // [rsp+C8h] [rbp-38h]
  __int64 v20; // [rsp+D0h] [rbp-30h]
  int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+E0h] [rbp-20h]
  int v23; // [rsp+E4h] [rbp-1Ch]
  int v24; // [rsp+E8h] [rbp-18h]
  int v25; // [rsp+ECh] [rbp-14h]
  int v26; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v27; // [rsp+F4h] [rbp-Ch]
  int v28; // [rsp+FCh] [rbp-4h]
  __int128 v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+110h] [rbp+10h]
  int v31; // [rsp+118h] [rbp+18h]
  int v32; // [rsp+11Ch] [rbp+1Ch]
  int v33; // [rsp+120h] [rbp+20h]
  int v34; // [rsp+124h] [rbp+24h]
  int v35; // [rsp+128h] [rbp+28h]
  unsigned __int64 v36; // [rsp+12Ch] [rbp+2Ch]
  int v37; // [rsp+134h] [rbp+34h]
  __int64 v38; // [rsp+138h] [rbp+38h]
  __int64 v39; // [rsp+140h] [rbp+40h]
  int v40; // [rsp+148h] [rbp+48h]
  int v41; // [rsp+150h] [rbp+50h]
  int v42; // [rsp+154h] [rbp+54h]
  int v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+15Ch] [rbp+5Ch]
  int v45; // [rsp+160h] [rbp+60h]
  unsigned __int64 v46; // [rsp+164h] [rbp+64h]
  int v47; // [rsp+16Ch] [rbp+6Ch]
  __int128 v48; // [rsp+170h] [rbp+70h]
  int v49; // [rsp+180h] [rbp+80h]
  int v50; // [rsp+188h] [rbp+88h]
  int v51; // [rsp+18Ch] [rbp+8Ch]
  int v52; // [rsp+190h] [rbp+90h]
  int v53; // [rsp+194h] [rbp+94h]
  int v54; // [rsp+198h] [rbp+98h]
  unsigned __int64 v55; // [rsp+19Ch] [rbp+9Ch]
  int v56; // [rsp+1A4h] [rbp+A4h]
  __int64 v57; // [rsp+1A8h] [rbp+A8h]
  __int64 v58; // [rsp+1B0h] [rbp+B0h]
  int v59; // [rsp+1B8h] [rbp+B8h]
  int v60; // [rsp+1C0h] [rbp+C0h]
  int v61; // [rsp+1C4h] [rbp+C4h]
  int v62; // [rsp+1C8h] [rbp+C8h]
  int v63; // [rsp+1CCh] [rbp+CCh]
  int v64; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v65; // [rsp+1D4h] [rbp+D4h]
  int v66; // [rsp+1DCh] [rbp+DCh]
  __int128 v67; // [rsp+1E0h] [rbp+E0h]
  int v68; // [rsp+1F0h] [rbp+F0h]
  int v69; // [rsp+1F8h] [rbp+F8h]
  int v70; // [rsp+1FCh] [rbp+FCh]
  int v71; // [rsp+200h] [rbp+100h]
  int v72; // [rsp+204h] [rbp+104h]
  int v73; // [rsp+208h] [rbp+108h]
  unsigned __int64 v74; // [rsp+20Ch] [rbp+10Ch]
  int v75; // [rsp+214h] [rbp+114h]
  __int64 v76; // [rsp+218h] [rbp+118h]
  __int64 v77; // [rsp+220h] [rbp+120h]
  int v78; // [rsp+228h] [rbp+128h]

  *a3 = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_DsObjectPicker, 0, 1u, &IID_IDsObjectPicker, &ppv);
  if ( v5 >= 0 )
  {
    v9[2] = 21;
    v9[1] = 2;
    v9[3] = 2;
    v9[0] = 56;
    v9[4] = 2;
    v9[5] = 2;
    v14 = 20;
    v23 = 8;
    v24 = 20;
    v33 = 20;
    v43 = 20;
    v52 = 20;
    v62 = 20;
    v9[6] = -2147483647;
    v9[7] = 0;
    v10 = 0;
    v11 = 0;
    v12 = 56;
    v13 = 4;
    v15 = 2;
    v16 = 2;
    v17 = 0x8000000100000002uLL;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 56;
    v25 = 2;
    v26 = 2;
    v27 = 0x8000000100000002uLL;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 56;
    v32 = 32;
    v34 = 2;
    v35 = 2;
    v36 = 0x8000000100000002uLL;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 56;
    v42 = 64;
    v44 = 2;
    v45 = 2;
    v46 = 0x8000000100000002uLL;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 56;
    v51 = 16;
    v53 = 2;
    v54 = 2;
    v55 = 0x8000000100000002uLL;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 56;
    v61 = 128;
    v63 = 2;
    v64 = 2;
    v65 = 0x8000000100000002uLL;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 56;
    v75 = 0;
    v71 = 20;
    v8[2] = 8;
    v8[3] = v9;
    v70 = 1;
    v72 = 2;
    v73 = 2;
    v74 = 0x8000000100000002uLL;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v8[0] = 48;
    v8[1] = 0;
    v8[4] = 1;
    v8[5] = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v8);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(LPVOID, HWND, struct IDataObject **))(*(_QWORD *)ppv + 32LL))(ppv, a2, a3);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800064cc  mov     [rsp-8+arg_0], rbx
0x1800064d1  mov     [rsp-8+arg_18], rsi
0x1800064d6  push    rbp
0x1800064d7  push    rdi
0x1800064d8  push    r14
0x1800064da  lea     rbp, [rsp-140h]
0x1800064e2  sub     rsp, 240h
0x1800064e9  mov     rax, cs:__security_cookie
0x1800064f0  xor     rax, rsp
0x1800064f3  mov     [rbp+150h+var_20], rax
0x1800064fa  xor     r14d, r14d
0x1800064fd  lea     rax, [rsp+250h+var_220]
0x180006502  mov     rdi, r8
0x180006505  mov     [r8], r14
0x180006508  mov     rsi, rdx
0x18000650b  mov     [rsp+250h+var_220], r14
0x180006510  lea     r9, IID_IDsObjectPicker; riid
0x180006517  mov     [rsp+250h+ppv], rax; ppv
0x18000651c  lea     r8d, [r14+1]; dwClsContext
0x180006520  xor     edx, edx; pUnkOuter
0x180006522  lea     rcx, CLSID_DsObjectPicker; rclsid
0x180006529  call    cs:__imp_CoCreateInstance
0x18000652f  mov     ebx, eax
0x180006531  test    eax, eax
0x180006533  js      loc_180006783
0x180006539  lea     r10d, [r14+2]
0x18000653d  mov     [rsp+250h+var_1D8], 15h
0x180006545  xor     eax, eax
0x180006547  mov     [rsp+250h+var_1DC], r10d
0x18000654c  lea     r9d, [r14+38h]
0x180006550  mov     [rsp+250h+var_1D4], r10d
0x180006555  mov     r8d, 80000001h
0x18000655b  mov     [rsp+250h+var_1E0], r9d
0x180006560  xorps   xmm0, xmm0
0x180006563  mov     [rbp+150h+var_1D0], r10d
0x180006567  lea     ecx, [rax+14h]
0x18000656a  mov     [rbp+150h+var_1CC], r10d
0x18000656e  lea     edx, [rax+8]
0x180006571  mov     [rbp+150h+var_1A0], ecx
0x180006574  mov     [rbp+150h+var_16C], edx
0x180006577  mov     [rbp+150h+var_168], ecx
0x18000657a  mov     [rbp+150h+var_130], ecx
0x18000657d  mov     [rbp+150h+var_F8], ecx
0x180006580  mov     [rbp+150h+var_C0], ecx
0x180006586  mov     [rbp+150h+var_88], ecx
0x18000658c  mov     [rbp+150h+var_1C8], r8d
0x180006590  mov     [rbp+150h+var_1C4], eax
0x180006593  movdqa  [rbp+150h+var_1C0], xmm0
0x180006598  mov     [rbp+150h+var_1B0], r14d
0x18000659c  mov     [rbp+150h+var_1A8], r9d
0x1800065a0  mov     [rbp+150h+var_1A4], 4
0x1800065a7  mov     [rbp+150h+var_19C], r10d
0x1800065ab  mov     [rbp+150h+var_198], r10d
0x1800065af  mov     dword ptr [rbp+150h+var_194], r10d
0x1800065b3  mov     dword ptr [rbp+150h+var_194+4], r8d
0x1800065b7  mov     [rbp+150h+var_18C], eax
0x1800065ba  mov     [rbp+150h+var_188], r14
0x1800065be  mov     [rbp+150h+var_180], r14
0x1800065c2  mov     [rbp+150h+var_178], r14d
0x1800065c6  mov     [rbp+150h+var_170], r9d
0x1800065ca  mov     [rbp+150h+var_164], r10d
0x1800065ce  mov     [rbp+150h+var_160], r10d
0x1800065d2  mov     dword ptr [rbp+150h+var_15C], r10d
0x1800065d6  mov     dword ptr [rbp+150h+var_15C+4], r8d
0x1800065da  mov     [rbp+150h+var_154], eax
0x1800065dd  movdqa  [rbp+150h+var_150], xmm0
0x1800065e2  mov     [rbp+150h+var_140], r14d
0x1800065e6  mov     [rbp+150h+var_138], r9d
0x1800065ea  mov     [rbp+150h+var_134], 20h ; ' '
0x1800065f1  mov     [rbp+150h+var_12C], r10d
0x1800065f5  mov     [rbp+150h+var_128], r10d
0x1800065f9  mov     dword ptr [rbp+150h+var_124], r10d
0x1800065fd  mov     dword ptr [rbp+150h+var_124+4], r8d
0x180006601  mov     [rbp+150h+var_11C], eax
0x180006604  mov     [rbp+150h+var_118], r14
0x180006608  mov     [rbp+150h+var_110], r14
0x18000660c  mov     [rbp+150h+var_108], r14d
0x180006610  mov     [rbp+150h+var_100], r9d
0x180006614  mov     [rbp+150h+var_FC], 40h ; '@'
0x18000661b  mov     [rbp+150h+var_F4], r10d
0x18000661f  mov     [rbp+150h+var_F0], r10d
0x180006623  mov     dword ptr [rbp+150h+var_EC], r10d
0x180006627  mov     dword ptr [rbp+150h+var_EC+4], r8d
0x18000662b  mov     [rbp+150h+var_E4], eax
0x18000662e  movdqa  [rbp+150h+var_E0], xmm0
0x180006633  mov     [rbp+150h+var_D0], r14d
0x18000663a  mov     [rbp+150h+var_C8], r9d
0x180006641  mov     [rbp+150h+var_C4], 10h
0x18000664b  mov     [rbp+150h+var_BC], r10d
0x180006652  mov     [rbp+150h+var_B8], r10d
0x180006659  mov     dword ptr [rbp+150h+var_B4], r10d
0x180006660  mov     dword ptr [rbp+150h+var_B4+4], r8d
0x180006667  mov     [rbp+150h+var_AC], eax
0x18000666d  mov     [rbp+150h+var_A8], r14
0x180006674  mov     [rbp+150h+var_A0], r14
0x18000667b  mov     [rbp+150h+var_98], r14d
0x180006682  mov     [rbp+150h+var_90], r9d
0x180006689  mov     [rbp+150h+var_8C], 80h
0x180006693  mov     [rbp+150h+var_84], r10d
0x18000669a  mov     [rbp+150h+var_80], r10d
0x1800066a1  mov     dword ptr [rbp+150h+var_7C], r10d
0x1800066a8  mov     dword ptr [rbp+150h+var_7C+4], r8d
0x1800066af  mov     [rbp+150h+var_74], eax
0x1800066b5  movdqa  [rbp+150h+var_70], xmm0
0x1800066bd  mov     [rbp+150h+var_60], r14d
0x1800066c4  mov     [rbp+150h+var_58], r9d
0x1800066cb  mov     [rbp+150h+var_3C], eax
0x1800066d1  lea     rax, [rsp+250h+var_1E0]
0x1800066d6  mov     [rbp+150h+var_50], ecx
0x1800066dc  mov     rcx, [rsp+250h+var_220]
0x1800066e1  mov     [rsp+250h+var_208], rdx
0x1800066e6  lea     rdx, [rsp+250h+var_218]
0x1800066eb  mov     [rsp+250h+var_200], rax
0x1800066f0  mov     [rbp+150h+var_54], 1
0x1800066fa  mov     [rbp+150h+var_4C], r10d
0x180006701  mov     [rbp+150h+var_48], r10d
0x180006708  mov     dword ptr [rbp+150h+var_44], r10d
0x18000670f  mov     dword ptr [rbp+150h+var_44+4], r8d
0x180006716  mov     [rbp+150h+var_38], r14
0x18000671d  mov     [rbp+150h+var_30], r14
0x180006724  mov     [rbp+150h+var_28], r14d
0x18000672b  mov     [rsp+250h+var_218], 30h ; '0'
0x180006734  mov     [rsp+250h+var_210], r14
0x180006739  mov     [rsp+250h+var_1F8], 1
0x180006742  mov     [rsp+250h+var_1F0], r14
0x180006747  mov     rax, [rcx]
0x18000674a  mov     rax, [rax+18h]
0x18000674e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006753  mov     ebx, eax
0x180006755  test    eax, eax
0x180006757  js      short loc_180006772
0x180006759  mov     rcx, [rsp+250h+var_220]
0x18000675e  mov     r8, rdi
0x180006761  mov     rdx, rsi
0x180006764  mov     rax, [rcx]
0x180006767  mov     rax, [rax+20h]
0x18000676b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006770  mov     ebx, eax
0x180006772  mov     rcx, [rsp+250h+var_220]
0x180006777  mov     rax, [rcx]
0x18000677a  mov     rax, [rax+10h]
0x18000677e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006783  mov     eax, ebx
0x180006785  mov     rcx, [rbp+150h+var_20]
0x18000678c  xor     rcx, rsp; StackCookie
0x18000678f  call    __security_check_cookie
0x180006794  lea     r11, [rsp+250h+var_10]
0x18000679c  mov     rbx, [r11+20h]
0x1800067a0  mov     rsi, [r11+38h]
0x1800067a4  mov     rsp, r11
0x1800067a7  pop     r14
0x1800067a9  pop     rdi
0x1800067aa  pop     rbp
0x1800067ab  retn
```
