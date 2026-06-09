# CPinProgressDialog::_ExecuteHyperLink(ushort const *)

- ea: `0x180042794`
- end: `0x180042a20`
- name: `?_ExecuteHyperLink@CPinProgressDialog@@AEAAJPEBG@Z`
- size: `652`
- prototype: `int(CPinProgressDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042dc0`

## callees

- `0x18001101c`
- `0x180013d9c`
- `0x180042794`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004296b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004296b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800428f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004292e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800428f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004292e`

## pseudocode

```c
__int64 __fastcall CPinProgressDialog::_ExecuteHyperLink(CPinProgressDialog *this, const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  WCHAR *v4; // rcx
  const wchar_t *v5; // rax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int64 v13; // rax
  const wchar_t *v14; // rdi
  unsigned int v15; // ebx
  HRESULT v16; // eax
  int v17; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR lpString2[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+90h] [rbp-70h]
  __int128 v26; // [rsp+A0h] [rbp-60h]
  __int128 v27; // [rsp+B0h] [rbp-50h]
  __int128 v28; // [rsp+C0h] [rbp-40h]
  __int128 v29; // [rsp+D0h] [rbp-30h]
  _OWORD v30[2]; // [rsp+E0h] [rbp-20h]
  WCHAR String2[136]; // [rsp+100h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids, a2);
  }
  v3 = 2;
  v4 = String2;
  v5 = L"shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}\\::{BC48B32F-5910-47"
        "F5-8570-5074A8A5636A}";
  do
  {
    v6 = *((_OWORD *)v5 + 1);
    *(_OWORD *)v4 = *(_OWORD *)v5;
    v7 = *((_OWORD *)v5 + 2);
    *((_OWORD *)v4 + 1) = v6;
    v8 = *((_OWORD *)v5 + 3);
    *((_OWORD *)v4 + 2) = v7;
    v9 = *((_OWORD *)v5 + 4);
    *((_OWORD *)v4 + 3) = v8;
    v10 = *((_OWORD *)v5 + 5);
    *((_OWORD *)v4 + 4) = v9;
    v11 = *((_OWORD *)v5 + 6);
    *((_OWORD *)v4 + 5) = v10;
    v12 = *((_OWORD *)v5 + 7);
    v5 += 64;
    *((_OWORD *)v4 + 6) = v11;
    *((_OWORD *)v4 + 7) = v12;
    v4 += 64;
    --v3;
  }
  while ( v3 );
  v13 = *(_QWORD *)v5;
  *(_OWORD *)lpString2 = *(_OWORD *)L"shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  *(_QWORD *)v4 = v13;
  v22 = *(_OWORD *)L"8-A00A-44D7-9371-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v21 = *(_OWORD *)L"{26EE0668-A00A-44D7-9371-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v24 = *(_OWORD *)L"-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v23 = *(_OWORD *)L"4D7-9371-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v26 = *(_OWORD *)L"1\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v25 = *(_OWORD *)L"98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v28 = *(_OWORD *)L"E7-4E32-A8E8-8D23B85255BF}";
  v30[0] = *(_OWORD *)L"3B85255BF}";
  *(_QWORD *)((char *)v30 + 14) = *(_QWORD *)L"BF}";
  v27 = *(_OWORD *)L"3F5E5-7AE7-4E32-A8E8-8D23B85255BF}";
  v29 = *(_OWORD *)L"A8E8-8D23B85255BF}";
  if ( CompareStringW(0x7Fu, 1u, a2, -1, String2, -1) == 2 )
  {
    v14 = L"::{BC48B32F-5910-47F5-8570-5074A8A5636A}";
  }
  else
  {
    v15 = 0;
    if ( CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) != 2 )
      return v15;
    v14 = &lParam;
  }
  ppv = 0;
  v16 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv);
  v15 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
        (unsigned int)v16);
    }
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 24LL))(
            ppv,
            L"Microsoft.SyncCenter",
            v14,
            0);
    v15 = v17;
    if ( v17 < 0
      && WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids,
        (unsigned int)v17);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v15;
}

```

## disassembly

```asm
0x180042794  push    rbp
0x180042796  push    rbx
0x180042797  push    rdi
0x180042798  push    r14
0x18004279a  lea     rbp, [rsp-128h]
0x1800427a2  sub     rsp, 228h
0x1800427a9  mov     rax, cs:__security_cookie
0x1800427b0  xor     rax, rsp
0x1800427b3  mov     [rbp+140h+var_30], rax
0x1800427ba  mov     rdi, rdx
0x1800427bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800427c4  lea     r14, WPP_GLOBAL_Control
0x1800427cb  cmp     rcx, r14
0x1800427ce  jz      short loc_1800427EE
0x1800427d0  test    byte ptr [rcx+1Ch], 40h
0x1800427d4  jz      short loc_1800427EE
0x1800427d6  mov     rcx, [rcx+10h]
0x1800427da  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800427e1  mov     edx, 1Dh
0x1800427e6  mov     r9, rdi
0x1800427e9  call    WPP_SF_S
0x1800427ee  mov     edx, 2
0x1800427f3  lea     rcx, [rbp+140h+String2]
0x1800427f7  lea     rax, aShell26ee0668A; "shell:::{26EE0668-A00A-44D7-9371-BEB064"...
0x1800427fe  lea     r8d, [rdx+7Eh]
0x180042802  movups  xmm0, xmmword ptr [rax]
0x180042805  movups  xmm1, xmmword ptr [rax+10h]
0x180042809  movups  xmmword ptr [rcx], xmm0
0x18004280c  movups  xmm0, xmmword ptr [rax+20h]
0x180042810  movups  xmmword ptr [rcx+10h], xmm1
0x180042814  movups  xmm1, xmmword ptr [rax+30h]
0x180042818  movups  xmmword ptr [rcx+20h], xmm0
0x18004281c  movups  xmm0, xmmword ptr [rax+40h]
0x180042820  movups  xmmword ptr [rcx+30h], xmm1
0x180042824  movups  xmm1, xmmword ptr [rax+50h]
0x180042828  movups  xmmword ptr [rcx+40h], xmm0
0x18004282c  movups  xmm0, xmmword ptr [rax+60h]
0x180042830  movups  xmmword ptr [rcx+50h], xmm1
0x180042834  movups  xmm1, xmmword ptr [rax+70h]
0x180042838  add     rax, r8
0x18004283b  movups  xmmword ptr [rcx+60h], xmm0
0x18004283f  movups  xmmword ptr [rcx+70h], xmm1
0x180042843  add     rcx, r8
0x180042846  sub     rdx, 1
0x18004284a  jnz     short loc_180042802
0x18004284c  mov     rax, [rax]
0x18004284f  or      r9d, 0FFFFFFFFh; cchCount1
0x180042853  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0; "shell:::{26EE0668-A00A-44D7-9371-BEB064"...
0x18004285a  mov     r8, rdi; lpString1
0x18004285d  movaps  xmm1, xmmword ptr cs:aShell26ee0668A_0+10h; "{26EE0668-A00A-44D7-9371-BEB064C98683}"...
0x180042864  movups  xmmword ptr [rsp+240h+var_200], xmm0
0x180042869  lea     edx, [r9+2]; dwCmpFlags
0x18004286d  mov     [rcx], rax
0x180042870  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0+20h; "8-A00A-44D7-9371-BEB064C98683}\\11\\::{"...
0x180042877  lea     ecx, [rdx+7Eh]; Locale
0x18004287a  mov     rax, qword ptr cs:aShell26ee0668A_0+0AEh; "BF}"
0x180042881  movups  [rsp+240h+var_1E0], xmm0
0x180042886  mov     [rsp+240h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004288e  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0+40h; "-BEB064C98683}\\11\\::{9C73F5E5-7AE7-4E"...
0x180042895  movups  [rsp+240h+var_1F0], xmm1
0x18004289a  movaps  xmm1, xmmword ptr cs:aShell26ee0668A_0+30h; "4D7-9371-BEB064C98683}\\11\\::{9C73F5E5"...
0x1800428a1  movups  [rbp+140h+var_1C0], xmm0
0x1800428a5  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0+60h; "1\\::{9C73F5E5-7AE7-4E32-A8E8-8D23B8525"...
0x1800428ac  movups  [rsp+240h+var_1D0], xmm1
0x1800428b1  movaps  xmm1, xmmword ptr cs:aShell26ee0668A_0+50h; "98683}\\11\\::{9C73F5E5-7AE7-4E32-A8E8-"...
0x1800428b8  movups  [rbp+140h+var_1A0], xmm0
0x1800428bc  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0+80h; "E7-4E32-A8E8-8D23B85255BF}"
0x1800428c3  movups  [rbp+140h+var_1B0], xmm1
0x1800428c7  movaps  xmm1, xmmword ptr cs:aShell26ee0668A_0+70h; "3F5E5-7AE7-4E32-A8E8-8D23B85255BF}"
0x1800428ce  movups  [rbp+140h+var_180], xmm0
0x1800428d2  movaps  xmm0, xmmword ptr cs:aShell26ee0668A_0+0A0h; "3B85255BF}"
0x1800428d9  movups  xmmword ptr [rbp+140h+var_160], xmm0
0x1800428dd  mov     qword ptr [rbp+140h+var_160+0Eh], rax
0x1800428e1  lea     rax, [rbp+140h+String2]
0x1800428e5  movups  [rbp+140h+var_190], xmm1
0x1800428e9  mov     [rsp+240h+lpString2], rax; lpString2
0x1800428ee  movaps  xmm1, xmmword ptr cs:aShell26ee0668A_0+90h; "A8E8-8D23B85255BF}"
0x1800428f5  movups  [rbp+140h+var_170], xmm1
0x1800428f9  call    cs:__imp_CompareStringW
0x1800428ff  cmp     eax, 2
0x180042902  jnz     short loc_18004290D
0x180042904  lea     rdi, aBc48b32f591047; "::{BC48B32F-5910-47F5-8570-5074A8A5636A"...
0x18004290b  jmp     short loc_180042944
0x18004290d  xor     ebx, ebx
0x18004290f  mov     [rsp+240h+cchCount2], 0FFFFFFFFh; cchCount2
0x180042917  lea     rax, [rsp+240h+var_200]
0x18004291c  or      r9d, 0FFFFFFFFh; cchCount1
0x180042920  mov     r8, rdi; lpString1
0x180042923  mov     [rsp+240h+lpString2], rax; lpString2
0x180042928  lea     edx, [rbx+1]; dwCmpFlags
0x18004292b  lea     ecx, [rbx+7Fh]; Locale
0x18004292e  call    cs:__imp_CompareStringW
0x180042934  cmp     eax, 2
0x180042937  jnz     loc_180042A02
0x18004293d  lea     rdi, lParam
0x180042944  xor     edx, edx; pUnkOuter
0x180042946  mov     [rsp+240h+ppv], 0
0x18004294f  lea     rax, [rsp+240h+ppv]
0x180042954  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18004295b  mov     [rsp+240h+lpString2], rax; ppv
0x180042960  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180042967  lea     r8d, [rdx+1]; dwClsContext
0x18004296b  call    cs:__imp_CoCreateInstance
0x180042971  mov     ebx, eax
0x180042973  test    eax, eax
0x180042975  js      short loc_1800429D8
0x180042977  mov     rcx, [rsp+240h+ppv]
0x18004297c  lea     rdx, aMicrosoftSyncc; "Microsoft.SyncCenter"
0x180042983  xor     r9d, r9d
0x180042986  mov     r8, rdi
0x180042989  mov     rax, [rcx]
0x18004298c  mov     rax, [rax+18h]
0x180042990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042995  mov     ebx, eax
0x180042997  test    eax, eax
0x180042999  jns     short loc_1800429C5
0x18004299b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429a2  cmp     rcx, r14
0x1800429a5  jz      short loc_1800429C5
0x1800429a7  test    byte ptr [rcx+1Ch], 2
0x1800429ab  jz      short loc_1800429C5
0x1800429ad  mov     rcx, [rcx+10h]
0x1800429b1  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800429b8  mov     edx, 1Eh
0x1800429bd  mov     r9d, eax
0x1800429c0  call    WPP_SF_d
0x1800429c5  mov     rcx, [rsp+240h+ppv]
0x1800429ca  mov     rax, [rcx]
0x1800429cd  mov     rax, [rax+10h]
0x1800429d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800429d6  jmp     short loc_180042A02
0x1800429d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429df  cmp     rcx, r14
0x1800429e2  jz      short loc_180042A02
0x1800429e4  test    byte ptr [rcx+1Ch], 2
0x1800429e8  jz      short loc_180042A02
0x1800429ea  mov     rcx, [rcx+10h]
0x1800429ee  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x1800429f5  mov     edx, 1Fh
0x1800429fa  mov     r9d, eax
0x1800429fd  call    WPP_SF_d
0x180042a02  mov     eax, ebx
0x180042a04  mov     rcx, [rbp+140h+var_30]
0x180042a0b  xor     rcx, rsp; StackCookie
0x180042a0e  call    __security_check_cookie
0x180042a13  add     rsp, 228h
0x180042a1a  pop     r14
0x180042a1c  pop     rdi
0x180042a1d  pop     rbx
0x180042a1e  pop     rbp
0x180042a1f  retn
```
