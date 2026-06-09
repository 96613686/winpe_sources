# CMVEngine::HandleUiccLanguage(std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> const &)

- ea: `0x1800162f0`
- end: `0x180016548`
- name: `?HandleUiccLanguage@CMVEngine@@AEAAJAEBV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018e20`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x1800162f0`
- `0x18002ef84`
- `0x180033a08`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800163a0`
- `msvcrt!_wcsicmp` at `0x1800163dc`
- `msvcrt!_wcsicmp` at `0x180016418`
- `msvcrt!_wcsicmp` at `0x1800163a0`
- `msvcrt!_wcsicmp` at `0x1800163dc`
- `msvcrt!_wcsicmp` at `0x180016418`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMVEngine::HandleUiccLanguage(__int64 a1, __int64 *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rdi
  unsigned __int16 *v6; // rdx
  __int64 v7; // r9
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // r8
  __int64 v10; // rax
  __int64 v11; // rbx
  int v12; // edi
  __int64 v13; // rdx
  int v14; // eax
  int v15; // ecx
  _QWORD *v16; // rbx
  unsigned int v17; // esi
  _QWORD *v18; // rdi
  int v20; // eax
  int v21; // [rsp+20h] [rbp-29h]
  wchar_t *String2; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 *v23; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int16 *v24; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v26[32]; // [rsp+50h] [rbp+7h] BYREF
  wchar_t **p_String2; // [rsp+70h] [rbp+27h]
  __int64 v28; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v2 = *(_QWORD **)(a1 + 56);
  v4 = *(_QWORD **)(a1 + 64);
  while ( 1 )
  {
    v6 = 0;
    if ( v2 == v4 )
      break;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v2 + 64LL))(*v2, 0, 0);
    ++v2;
  }
  v7 = *a2;
  v8 = 0;
  v9 = 0;
  v10 = a2[1] - *a2;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( v10 >> 3 )
  {
    v11 = 0;
    while ( 1 )
    {
      String2 = 0;
      v12 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**(_QWORD **)(v7 + 8 * v11) + 40LL))(
              *(_QWORD *)(v7 + 8 * v11),
              &String2);
      if ( v12 < 0 )
        break;
      if ( _wcsicmp(L"mcc", String2) )
      {
        if ( _wcsicmp(L"iccid", String2) )
        {
          if ( !_wcsicmp(L"LANG", String2) )
          {
            v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)(*a2 + 8 * v11) + 48LL))(
                    *(_QWORD *)(*a2 + 8 * v11),
                    &v25);
            if ( v12 < 0 )
            {
              v13 = 1378;
              goto LABEL_22;
            }
          }
        }
        else
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)(*a2 + 8 * v11) + 48LL))(
                  *(_QWORD *)(*a2 + 8 * v11),
                  &v24);
          if ( v12 < 0 )
          {
            v13 = 1374;
            goto LABEL_22;
          }
        }
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)(*a2 + 8 * v11) + 48LL))(
                *(_QWORD *)(*a2 + 8 * v11),
                &v23);
        if ( v12 < 0 )
        {
          v13 = 1370;
          goto LABEL_22;
        }
      }
      v7 = *a2;
      if ( ++v11 >= (unsigned __int64)((a2[1] - *a2) >> 3) )
      {
        v8 = v23;
        v6 = v24;
        v9 = v25;
        goto LABEL_17;
      }
    }
    v13 = 1367;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)v12,
      v21);
    return (unsigned int)v12;
  }
  else
  {
LABEL_17:
    v14 = MvSetLanguageAndRegion(v8, v6, v9);
    v16 = *(_QWORD **)(a1 + 56);
    v17 = v14;
    v18 = *(_QWORD **)(a1 + 64);
    while ( v16 != v18 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v16 + 72LL))(*v16, v17, 0, 0);
      ++v16;
    }
    v20 = MvSetLanguageProvisioningComplete(v15);
    if ( (unsigned int)dword_18005A000 > 5 )
    {
      LODWORD(String2) = v20;
      v28 = 4;
      p_String2 = &String2;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F589, 0, 0, 3, v26);
    }
    if ( (v17 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x575,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
        (const char *)v17,
        v21);
    return v17;
  }
}

```

## disassembly

```asm
0x1800162f0  mov     [rsp-8+arg_0], rbx
0x1800162f5  mov     [rsp-8+arg_10], rsi
0x1800162fa  push    rbp
0x1800162fb  push    rdi
0x1800162fc  push    r14
0x1800162fe  lea     rbp, [rsp-47h]
0x180016303  sub     rsp, 90h
0x18001630a  mov     rax, cs:__security_cookie
0x180016311  xor     rax, rsp
0x180016314  mov     [rbp+57h+var_20], rax
0x180016318  mov     rbx, [rcx+38h]
0x18001631c  mov     rsi, rdx
0x18001631f  mov     rdi, [rcx+40h]
0x180016323  mov     r14, rcx
0x180016326  xor     edx, edx
0x180016328  cmp     rbx, rdi
0x18001632b  jz      short loc_180016345
0x18001632d  mov     rcx, [rbx]
0x180016330  xor     r8d, r8d
0x180016333  mov     rax, [rcx]
0x180016336  mov     rax, [rax+40h]
0x18001633a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001633f  add     rbx, 8
0x180016343  jmp     short loc_180016326
0x180016345  mov     r9, [rsi]
0x180016348  xor     ecx, ecx
0x18001634a  mov     rax, [rsi+8]
0x18001634e  xor     r8d, r8d
0x180016351  sub     rax, r9
0x180016354  mov     [rbp+57h+var_68], rcx
0x180016358  sar     rax, 3
0x18001635c  mov     [rbp+57h+var_60], rdx
0x180016360  mov     [rbp+57h+var_58], r8
0x180016364  test    rax, rax
0x180016367  jz      loc_180016465
0x18001636d  xor     ebx, ebx
0x18001636f  mov     [rbp+57h+String2], 0
0x180016377  lea     rdx, [rbp+57h+String2]
0x18001637b  mov     rcx, [r9+rbx*8]
0x18001637f  mov     rax, [rcx]
0x180016382  mov     rax, [rax+28h]
0x180016386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001638b  mov     edi, eax
0x18001638d  test    eax, eax
0x18001638f  js      loc_18001649D
0x180016395  mov     rdx, [rbp+57h+String2]; String2
0x180016399  lea     rcx, ?gc_wszMCC@@3QBGB; "mcc"
0x1800163a0  call    cs:__imp__wcsicmp
0x1800163a6  test    eax, eax
0x1800163a8  jnz     short loc_1800163D1
0x1800163aa  mov     rax, [rsi]
0x1800163ad  lea     rdx, [rbp+57h+var_68]
0x1800163b1  mov     rcx, [rax+rbx*8]
0x1800163b5  mov     rax, [rcx]
0x1800163b8  mov     rax, [rax+30h]
0x1800163bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c1  mov     edi, eax
0x1800163c3  test    eax, eax
0x1800163c5  jns     short loc_18001643F
0x1800163c7  mov     edx, 55Ah
0x1800163cc  jmp     loc_1800164A2
0x1800163d1  mov     rdx, [rbp+57h+String2]; String2
0x1800163d5  lea     rcx, ?gc_wszICCID@@3QBGB; "iccid"
0x1800163dc  call    cs:__imp__wcsicmp
0x1800163e2  test    eax, eax
0x1800163e4  jnz     short loc_18001640D
0x1800163e6  mov     rax, [rsi]
0x1800163e9  lea     rdx, [rbp+57h+var_60]
0x1800163ed  mov     rcx, [rax+rbx*8]
0x1800163f1  mov     rax, [rcx]
0x1800163f4  mov     rax, [rax+30h]
0x1800163f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fd  mov     edi, eax
0x1800163ff  test    eax, eax
0x180016401  jns     short loc_18001643F
0x180016403  mov     edx, 55Eh
0x180016408  jmp     loc_1800164A2
0x18001640d  mov     rdx, [rbp+57h+String2]; String2
0x180016411  lea     rcx, aLang; "LANG"
0x180016418  call    cs:__imp__wcsicmp
0x18001641e  test    eax, eax
0x180016420  jnz     short loc_18001643F
0x180016422  mov     rax, [rsi]
0x180016425  lea     rdx, [rbp+57h+var_58]
0x180016429  mov     rcx, [rax+rbx*8]
0x18001642d  mov     rax, [rcx]
0x180016430  mov     rax, [rax+30h]
0x180016434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016439  mov     edi, eax
0x18001643b  test    eax, eax
0x18001643d  js      short loc_180016496
0x18001643f  mov     r9, [rsi]
0x180016442  inc     rbx
0x180016445  mov     rax, [rsi+8]
0x180016449  sub     rax, r9
0x18001644c  sar     rax, 3
0x180016450  cmp     rbx, rax
0x180016453  jb      loc_18001636F
0x180016459  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x18001645d  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180016461  mov     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180016465  call    ?MvSetLanguageAndRegion@@YAJPEBG0PEAG@Z; MvSetLanguageAndRegion(ushort const *,ushort const *,ushort *)
0x18001646a  mov     rbx, [r14+38h]
0x18001646e  mov     esi, eax
0x180016470  mov     rdi, [r14+40h]
0x180016474  cmp     rbx, rdi
0x180016477  jz      short loc_1800164B9
0x180016479  mov     rcx, [rbx]
0x18001647c  xor     r9d, r9d
0x18001647f  xor     r8d, r8d
0x180016482  mov     rdx, [rcx]
0x180016485  mov     rax, [rdx+48h]
0x180016489  mov     edx, esi
0x18001648b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016490  add     rbx, 8
0x180016494  jmp     short loc_180016474
0x180016496  mov     edx, 562h
0x18001649b  jmp     short loc_1800164A2
0x18001649d  mov     edx, 557h; void *
0x1800164a2  mov     rcx, [rbp+5Fh]; this
0x1800164a6  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800164ad  mov     r9d, edi; char *
0x1800164b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164b5  mov     eax, edi
0x1800164b7  jmp     short loc_180016524
0x1800164b9  call    ?MvSetLanguageProvisioningComplete@@YAJH@Z; MvSetLanguageProvisioningComplete(int)
0x1800164be  mov     ecx, cs:dword_18005A000
0x1800164c4  cmp     ecx, 5
0x1800164c7  jbe     short loc_180016506
0x1800164c9  mov     dword ptr [rbp+57h+String2], eax
0x1800164cc  lea     rdx, byte_18004F589
0x1800164d3  lea     rax, [rbp+57h+String2]
0x1800164d7  mov     [rbp+57h+var_28], 4
0x1800164df  mov     [rbp+57h+var_30], rax
0x1800164e3  lea     rcx, dword_18005A000
0x1800164ea  lea     rax, [rbp+57h+var_50]
0x1800164ee  xor     r9d, r9d
0x1800164f1  mov     [rsp+0A0h+var_78], rax
0x1800164f6  xor     r8d, r8d
0x1800164f9  mov     [rsp+0A0h+var_80], 3; int
0x180016501  call    _tlgWriteTransfer_EventWriteTransfer
0x180016506  test    esi, esi
0x180016508  jns     short loc_180016522
0x18001650a  mov     rcx, [rbp+5Fh]; this
0x18001650e  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180016515  mov     r9d, esi; char *
0x180016518  mov     edx, 575h; void *
0x18001651d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016522  mov     eax, esi
0x180016524  mov     rcx, [rbp+57h+var_20]
0x180016528  xor     rcx, rsp; StackCookie
0x18001652b  call    __security_check_cookie
0x180016530  lea     r11, [rsp+0A0h+var_10]
0x180016538  mov     rbx, [r11+20h]
0x18001653c  mov     rsi, [r11+30h]
0x180016540  mov     rsp, r11
0x180016543  pop     r14
0x180016545  pop     rdi
0x180016546  pop     rbp
0x180016547  retn
```
