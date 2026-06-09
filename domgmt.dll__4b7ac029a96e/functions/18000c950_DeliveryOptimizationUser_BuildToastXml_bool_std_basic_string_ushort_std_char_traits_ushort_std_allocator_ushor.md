# DeliveryOptimizationUser::_BuildToastXml(bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000c950`
- end: `0x18000cc23`
- name: `?_BuildToastXml@DeliveryOptimizationUser@@AEAAJ_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `723`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6b0`

## callees

- `0x180001ba0`
- `0x180005944`
- `0x180005964`
- `0x1800062f0`
- `0x180008d88`
- `0x180008ef4`
- `0x18000c06c`
- `0x18000c950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c9f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ca38`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c9f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ca38`

## string_xrefs

- `0x18000c97d`: `<toast launch="https://go.microsoft.com/fwlink/?LinkID=614833" activationType="protocol"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall DeliveryOptimizationUser::_BuildToastXml(__int64 a1, unsigned __int8 a2, __int64 a3)
{
  int v4; // ebx
  unsigned __int16 *v5; // rcx
  const wchar_t *v6; // rax
  __int64 v7; // rdi
  const char *v8; // r9
  __int64 result; // rax
  const char *v10; // r9
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int16 **v15; // rdi
  unsigned __int64 i; // rcx
  unsigned __int16 *v17; // rcx
  int v18; // eax
  unsigned int v19; // edi
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned __int16 **v22; // rax
  unsigned __int64 v23; // r8
  unsigned __int16 **v24; // rcx
  unsigned __int64 v25; // rdx
  unsigned __int16 **v26; // r9
  _WORD *v27; // rdi
  unsigned __int64 j; // rcx
  int v29; // [rsp+20h] [rbp-838h]
  unsigned __int16 *Src[2]; // [rsp+38h] [rbp-820h] BYREF
  unsigned __int64 v31; // [rsp+48h] [rbp-810h]
  unsigned __int64 v32; // [rsp+50h] [rbp-808h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-7F8h] BYREF
  unsigned __int16 v34[208]; // [rsp+270h] [rbp-5E8h] BYREF
  WCHAR v35[520]; // [rsp+410h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+0h]

  v4 = a2;
  v5 = v34;
  v6 = L"<toast launch=\"https://go.microsoft.com/fwlink/?LinkID=614833\" activationType=\"protocol\"><visual><binding tem"
        "plate=\"ToastGeneric\"><text id=\"1\">%s</text><text id=\"2\">%s</text></binding></visual></toast>";
  v7 = 3;
  do
  {
    *(_OWORD *)v5 = *(_OWORD *)v6;
    *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
    *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
    *((_OWORD *)v5 + 4) = *((_OWORD *)v6 + 4);
    *((_OWORD *)v5 + 5) = *((_OWORD *)v6 + 5);
    *((_OWORD *)v5 + 6) = *((_OWORD *)v6 + 6);
    *((_OWORD *)v5 + 7) = *((_OWORD *)v6 + 7);
    v5 += 64;
    v6 += 64;
    --v7;
  }
  while ( v7 );
  *(_OWORD *)v5 = *(_OWORD *)v6;
  *((_DWORD *)v5 + 4) = *((_DWORD *)v6 + 4);
  if ( !LoadStringW(g_hModule, 0x64u, Buffer, 260) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4E,
             (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
             v8);
  if ( !LoadStringW(g_hModule, v4 + 101, v35, 520) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x52,
             (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
             v10);
  *(_OWORD *)Src = 0;
  v31 = 0;
  v32 = 7;
  LOWORD(Src[0]) = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( Buffer[v12] );
  v13 = -1;
  do
    ++v13;
  while ( v35[v13] );
  try
  {
    v14 = v13 + v12 + 202;
    if ( v14 )
    {
      if ( v14 > 7 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(Src);
        goto LABEL_20;
      }
      v31 = v13 + v12 + 202;
      v15 = Src;
      for ( i = v31; i; --i )
      {
        *(_WORD *)v15 = 0;
        v15 = (unsigned __int16 **)((char *)v15 + 2);
      }
    }
    else
    {
      v31 = 0;
    }
    *((_WORD *)Src + v14) = 0;
LABEL_20:
    v17 = (unsigned __int16 *)Src;
    if ( v32 > 7 )
      v17 = Src[0];
    v18 = StringCchPrintfW(v17, v31 + 1, v34, Buffer, v35);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v22 = Src;
      if ( v32 > 7 )
        v22 = (unsigned __int16 **)Src[0];
      do
        ++v11;
      while ( *((_WORD *)v22 + v11) );
      v23 = v31;
      if ( v11 > v31 )
      {
        v25 = v11 - v31;
        if ( v11 - v31 > v32 - v31 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(Src);
        }
        else
        {
          v31 = v11;
          v26 = Src;
          if ( v32 > 7 )
            v26 = (unsigned __int16 **)Src[0];
          v27 = (_WORD *)v26 + v23;
          if ( v25 )
          {
            for ( j = v11 - v23; j; --j )
              *v27++ = 0;
          }
          *((_WORD *)v26 + v11) = 0;
        }
      }
      else
      {
        v31 = v11;
        v24 = Src;
        if ( v32 > 7 )
          v24 = (unsigned __int16 **)Src[0];
        *((_WORD *)v24 + v11) = 0;
      }
      std::wstring::operator=(a3, Src);
      std::wstring::~wstring((char **)Src);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
        (const char *)(unsigned int)v18,
        v29);
      std::wstring::~wstring((char **)Src);
      result = v19;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x5C, v20, v21);
  }
  return result;
}

```

## disassembly

```asm
0x18000c950  push    rbx
0x18000c952  push    rsi
0x18000c953  push    rdi
0x18000c954  push    r14
0x18000c956  sub     rsp, 838h
0x18000c95d  mov     rax, cs:__security_cookie
0x18000c964  xor     rax, rsp
0x18000c967  mov     [rsp+858h+var_38], rax
0x18000c96f  mov     rsi, r8
0x18000c972  movzx   ebx, dl
0x18000c975  lea     rcx, [rsp+858h+var_5E8]
0x18000c97d  lea     rax, aToastLaunchHtt; "<toast launch=\"https://go.microsoft.co"...
0x18000c984  mov     edi, 3
0x18000c989  lea     edx, [rdi+7Dh]
0x18000c98c  movups  xmm0, xmmword ptr [rax]
0x18000c98f  movups  xmmword ptr [rcx], xmm0
0x18000c992  movups  xmm1, xmmword ptr [rax+10h]
0x18000c996  movups  xmmword ptr [rcx+10h], xmm1
0x18000c99a  movups  xmm0, xmmword ptr [rax+20h]
0x18000c99e  movups  xmmword ptr [rcx+20h], xmm0
0x18000c9a2  movups  xmm1, xmmword ptr [rax+30h]
0x18000c9a6  movups  xmmword ptr [rcx+30h], xmm1
0x18000c9aa  movups  xmm0, xmmword ptr [rax+40h]
0x18000c9ae  movups  xmmword ptr [rcx+40h], xmm0
0x18000c9b2  movups  xmm1, xmmword ptr [rax+50h]
0x18000c9b6  movups  xmmword ptr [rcx+50h], xmm1
0x18000c9ba  movups  xmm0, xmmword ptr [rax+60h]
0x18000c9be  movups  xmmword ptr [rcx+60h], xmm0
0x18000c9c2  movups  xmm1, xmmword ptr [rax+70h]
0x18000c9c6  movups  xmmword ptr [rcx+70h], xmm1
0x18000c9ca  add     rcx, rdx
0x18000c9cd  add     rax, rdx
0x18000c9d0  sub     rdi, 1
0x18000c9d4  jnz     short loc_18000C98C
0x18000c9d6  movups  xmm0, xmmword ptr [rax]
0x18000c9d9  movups  xmmword ptr [rcx], xmm0
0x18000c9dc  mov     eax, [rax+10h]
0x18000c9df  mov     [rcx+10h], eax
0x18000c9e2  mov     r9d, 104h; cchBufferMax
0x18000c9e8  lea     r8, [rsp+858h+Buffer]; lpBuffer
0x18000c9ed  lea     edx, [rdi+64h]; uID
0x18000c9f0  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c9f7  call    cs:__imp_LoadStringW
0x18000c9fd  xor     r14d, r14d
0x18000ca00  test    eax, eax
0x18000ca02  jnz     short loc_18000CA20
0x18000ca04  mov     rcx, [rsp+858h]; this
0x18000ca0c  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000ca13  lea     edx, [rdi+4Eh]; void *
0x18000ca16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ca1b  jmp     loc_18000CC05
0x18000ca20  lea     edx, [rbx+65h]; uID
0x18000ca23  mov     r9d, 208h; cchBufferMax
0x18000ca29  lea     r8, [rsp+858h+var_448]; lpBuffer
0x18000ca31  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000ca38  call    cs:__imp_LoadStringW
0x18000ca3e  test    eax, eax
0x18000ca40  jnz     short loc_18000CA5E
0x18000ca42  mov     rcx, [rsp+858h]; this
0x18000ca4a  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000ca51  lea     edx, [rax+52h]; void *
0x18000ca54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ca59  jmp     loc_18000CC05
0x18000ca5e  xorps   xmm0, xmm0
0x18000ca61  movups  xmmword ptr [rsp+858h+Src], xmm0
0x18000ca66  mov     [rsp+858h+var_810], r14
0x18000ca6b  mov     [rsp+858h+var_808], 7
0x18000ca74  mov     word ptr [rsp+858h+Src], r14w
0x18000ca7a  lea     rcx, [rsp+858h+Buffer]
0x18000ca7f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ca83  mov     rax, rbx
0x18000ca86  inc     rax
0x18000ca89  cmp     [rcx+rax*2], r14w
0x18000ca8e  jnz     short loc_18000CA86
0x18000ca90  lea     rdx, [rsp+858h+var_448]
0x18000ca98  mov     rcx, rbx
0x18000ca9b  inc     rcx
0x18000ca9e  cmp     [rdx+rcx*2], r14w
0x18000caa3  jnz     short loc_18000CA9B
0x18000caa5  lea     rdx, [rax+0CAh]
0x18000caac  add     rdx, rcx
0x18000caaf  jnz     short loc_18000CAB8
0x18000cab1  mov     [rsp+858h+var_810], rdx
0x18000cab6  jmp     short loc_18000CAD2
0x18000cab8  cmp     rdx, 7
0x18000cabc  ja      short loc_18000CADA
0x18000cabe  mov     [rsp+858h+var_810], rdx
0x18000cac3  lea     rdi, [rsp+858h+Src]
0x18000cac8  movzx   eax, r14w
0x18000cacc  mov     rcx, rdx
0x18000cacf  rep stosw
0x18000cad2  mov     word ptr [rsp+rdx*2+858h+Src], r14w
0x18000cad8  jmp     short loc_18000CAE7
0x18000cada  mov     r9, rdx
0x18000cadd  lea     rcx, [rsp+858h+Src]; Src
0x18000cae2  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000cae7  mov     rdx, [rsp+858h+var_810]
0x18000caec  lea     rcx, [rsp+858h+Src]
0x18000caf1  cmp     [rsp+858h+var_808], 7
0x18000caf7  cmova   rcx, [rsp+858h+Src]; unsigned __int16 *
0x18000cafd  inc     rdx; unsigned __int64
0x18000cb00  lea     rax, [rsp+858h+var_448]
0x18000cb08  mov     qword ptr [rsp+858h+var_838], rax; int
0x18000cb0d  lea     r9, [rsp+858h+Buffer]
0x18000cb12  lea     r8, [rsp+858h+var_5E8]; unsigned __int16 *
0x18000cb1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cb1f  mov     edi, eax
0x18000cb21  test    eax, eax
0x18000cb23  jns     short loc_18000CB53
0x18000cb25  mov     rcx, [rsp+858h]; this
0x18000cb2d  mov     r9d, eax; char *
0x18000cb30  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000cb37  mov     edx, 57h ; 'W'; void *
0x18000cb3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb41  nop
0x18000cb42  lea     rcx, [rsp+858h+Src]
0x18000cb47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cb4c  mov     eax, edi
0x18000cb4e  jmp     loc_18000CC05
0x18000cb53  mov     rdi, [rsp+858h+var_808]
0x18000cb58  lea     rax, [rsp+858h+Src]
0x18000cb5d  mov     r10, [rsp+858h+Src]
0x18000cb62  cmp     rdi, 7
0x18000cb66  cmova   rax, r10
0x18000cb6a  inc     rbx
0x18000cb6d  cmp     [rax+rbx*2], r14w
0x18000cb72  jnz     short loc_18000CB6A
0x18000cb74  mov     r8, [rsp+858h+var_810]
0x18000cb79  cmp     rbx, r8
0x18000cb7c  ja      short loc_18000CB97
0x18000cb7e  mov     [rsp+858h+var_810], rbx
0x18000cb83  lea     rcx, [rsp+858h+Src]
0x18000cb88  cmp     rdi, 7
0x18000cb8c  cmova   rcx, r10
0x18000cb90  mov     [rcx+rbx*2], r14w
0x18000cb95  jmp     short loc_18000CBE5
0x18000cb97  mov     rdx, rbx
0x18000cb9a  sub     rdx, r8
0x18000cb9d  mov     rax, rdi
0x18000cba0  sub     rax, r8
0x18000cba3  cmp     rdx, rax
0x18000cba6  ja      short loc_18000CBD8
0x18000cba8  mov     [rsp+858h+var_810], rbx
0x18000cbad  lea     r9, [rsp+858h+Src]
0x18000cbb2  cmp     rdi, 7
0x18000cbb6  cmova   r9, r10
0x18000cbba  lea     rdi, [r9+r8*2]
0x18000cbbe  test    rdx, rdx
0x18000cbc1  jz      short loc_18000CBCD
0x18000cbc3  movzx   eax, r14w
0x18000cbc7  mov     rcx, rdx
0x18000cbca  rep stosw
0x18000cbcd  lea     rcx, [rdx+r8]
0x18000cbd1  mov     [r9+rcx*2], r14w
0x18000cbd6  jmp     short loc_18000CBE5
0x18000cbd8  mov     r9, rdx
0x18000cbdb  lea     rcx, [rsp+858h+Src]; Src
0x18000cbe0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000cbe5  lea     rdx, [rsp+858h+Src]
0x18000cbea  mov     rcx, rsi
0x18000cbed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000cbf2  nop
0x18000cbf3  lea     rcx, [rsp+858h+Src]
0x18000cbf8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbfd  xor     eax, eax
0x18000cbff  jmp     short loc_18000CC05
0x18000cc01  mov     eax, [rsp+858h+var_828]
0x18000cc05  mov     rcx, [rsp+858h+var_38]
0x18000cc0d  xor     rcx, rsp; StackCookie
0x18000cc10  call    __security_check_cookie
0x18000cc15  add     rsp, 838h
0x18000cc1c  pop     r14
0x18000cc1e  pop     rdi
0x18000cc1f  pop     rsi
0x18000cc20  pop     rbx
0x18000cc21  retn
```
