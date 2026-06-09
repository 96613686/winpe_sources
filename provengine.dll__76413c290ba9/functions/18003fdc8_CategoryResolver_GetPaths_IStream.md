# CategoryResolver::GetPaths(IStream *)

- ea: `0x18003fdc8`
- end: `0x180040246`
- name: `?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAUIStream@@@Z`
- size: `1150`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18003fc9c`

## callees

- `0x1800071a4`
- `0x18000b030`
- `0x18000f56c`
- `0x18000f5f4`
- `0x180010ad8`
- `0x180021c5c`
- `0x180021cf4`
- `0x18003fb48`
- `0x18003fdc8`
- `0x180040338`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003fe80`
- `msvcrt!_wcsicmp` at `0x18003ff18`
- `msvcrt!_wcsicmp` at `0x18003ff36`
- `msvcrt!_wcsicmp` at `0x18003ff4b`
- `msvcrt!_wcsicmp` at `0x18003fe80`
- `msvcrt!_wcsicmp` at `0x18003ff18`
- `msvcrt!_wcsicmp` at `0x18003ff36`
- `msvcrt!_wcsicmp` at `0x18003ff4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040065`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040124`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040065`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040124`

## pseudocode

```c
_QWORD *__fastcall CategoryResolver::GetPaths(__int64 a1, _QWORD *a2, IUnknown *a3)
{
  int v4; // r13d
  void **v5; // r12
  int v6; // eax
  char v7; // r15
  void **v8; // rbx
  void **v9; // r14
  int v10; // eax
  int v11; // esi
  int v12; // eax
  const wchar_t *v13; // rdx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // r8
  __int64 v19; // rsi
  void *v20; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // [rsp+20h] [rbp-49h] BYREF
  void *ppvObject; // [rsp+28h] [rbp-41h] BYREF
  wchar_t *String2; // [rsp+30h] [rbp-39h] BYREF
  __int128 v27; // [rsp+38h] [rbp-31h] BYREF
  void **v28; // [rsp+48h] [rbp-21h]
  int v29; // [rsp+50h] [rbp-19h]
  int v30; // [rsp+54h] [rbp-15h]
  void *Src[2]; // [rsp+58h] [rbp-11h] BYREF
  void *v32[3]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v33; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Src[1] = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v4 = 1;
  v29 = 1;
  v27 = 0;
  v5 = 0;
  v28 = 0;
  v24 = 0;
  CreateReaderOnStream(&ppvObject, a3);
  while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v24) )
  {
    if ( v24 == 1 )
    {
      String2 = 0;
      v6 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &String2,
             0);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x20,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v6,
          v24);
      if ( _wcsicmp(L"wap-provisioningdoc", String2) )
      {
        v22 = wil::verify_hresult<long>(0x8000FFFF);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)v22,
          v24);
      }
      break;
    }
  }
  v7 = 0;
  v8 = (void **)*((_QWORD *)&v27 + 1);
  v9 = (void **)v27;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v24);
    if ( v10 )
      break;
    if ( v24 == 1 )
    {
      v11 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
      v30 = v11;
      String2 = 0;
      Src[0] = 0;
      v12 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
              ppvObject,
              &String2,
              0);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v12,
          v24);
      if ( _wcsicmp(L"characteristic", String2) )
      {
        if ( _wcsicmp(L"parm", String2) && _wcsicmp(L"noparm", String2) )
        {
          v23 = wil::verify_hresult<long>(0x8000FFFF);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x32,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
            (const char *)v23,
            v24);
        }
        v13 = L"name";
      }
      else
      {
        v13 = L"type";
      }
      v14 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
              ppvObject,
              v13,
              0);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v14,
          v24);
      v15 = (*(__int64 (__fastcall **)(void *, void **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(ppvObject, Src, 0);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
          (const char *)(unsigned int)v15,
          v24);
      v33 = 7;
      v32[2] = 0;
      LOWORD(v32[0]) = 0;
      if ( *(_WORD *)Src[0] )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)Src[0] + v16) );
      }
      else
      {
        v16 = 0;
      }
      std::wstring::assign(v32, (char *)Src[0], v16);
      v4 |= 4u;
      v29 = v4;
      if ( v32 >= v8 || v9 > v32 )
      {
        if ( v8 == v5 )
        {
          std::vector<std::wstring>::_Reserve(&v27);
          v5 = v28;
          v8 = (void **)*((_QWORD *)&v27 + 1);
          v9 = (void **)v27;
        }
        std::wstring::wstring(v8, v32);
      }
      else
      {
        v17 = (char *)v32 - (char *)v9;
        if ( v8 == v5 )
        {
          std::vector<std::wstring>::_Reserve(&v27);
          v5 = v28;
          v8 = (void **)*((_QWORD *)&v27 + 1);
          v9 = (void **)v27;
        }
        std::wstring::wstring(v8, (void **)((char *)v9 + (v17 & 0xFFFFFFFFFFFFFFE0uLL)));
        v11 = v30;
      }
      v8 += 4;
      *((_QWORD *)&v27 + 1) = v8;
      if ( v33 >= 8 )
        operator delete(v32[0]);
      v7 = 1;
      if ( v11 )
      {
LABEL_34:
        if ( v7 )
        {
          v7 = 0;
          v18 = a2[1];
          if ( (unsigned __int64)&v27 >= v18 || *a2 > (unsigned __int64)&v27 )
          {
            if ( v18 == a2[2] )
              std::vector<std::vector<std::wstring>>::_Reserve(a2);
            std::vector<std::wstring>::vector<std::wstring>(a2[1], &v27);
            a2[1] += 24LL;
          }
          else
          {
            v19 = ((__int64)&v27 - *a2) / 24;
            if ( v18 == a2[2] )
              std::vector<std::vector<std::wstring>>::_Reserve(a2);
            std::vector<std::wstring>::vector<std::wstring>(a2[1], *a2 + 24 * v19);
            a2[1] += 24LL;
          }
        }
        if ( v9 != v8 )
        {
          v8 -= 4;
          if ( (unsigned __int64)v8[3] >= 8 )
            operator delete(*v8);
          v8[3] = (void *)7;
          v8[2] = 0;
          *(_WORD *)v8 = 0;
          *((_QWORD *)&v27 + 1) = v8;
        }
      }
    }
    else if ( v24 == 15 )
    {
      goto LABEL_34;
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)(unsigned int)v10,
      v24);
  v20 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  std::vector<std::wstring>::_Tidy((__int64)&v27);
  return a2;
}

```

## disassembly

```asm
0x18003fdc8  mov     [rsp-8+arg_0], rbx
0x18003fdcd  push    rbp
0x18003fdce  push    rsi
0x18003fdcf  push    rdi
0x18003fdd0  push    r12
0x18003fdd2  push    r13
0x18003fdd4  push    r14
0x18003fdd6  push    r15
0x18003fdd8  lea     rbp, [rsp-27h]
0x18003fddd  sub     rsp, 90h
0x18003fde4  mov     rax, cs:__security_cookie
0x18003fdeb  xor     rax, rsp
0x18003fdee  mov     [rbp+57h+var_38], rax
0x18003fdf2  mov     rdi, rdx
0x18003fdf5  mov     [rbp+57h+var_60], rdx
0x18003fdf9  xor     esi, esi
0x18003fdfb  mov     [rbp+57h+var_70], esi
0x18003fdfe  mov     [rdx], rsi
0x18003fe01  mov     [rdx+8], rsi
0x18003fe05  mov     [rdx+10h], rsi
0x18003fe09  lea     r13d, [rsi+1]
0x18003fe0d  mov     [rbp+57h+var_70], r13d
0x18003fe11  xorps   xmm0, xmm0
0x18003fe14  movdqu  [rbp+57h+var_88], xmm0
0x18003fe19  mov     r12d, esi
0x18003fe1c  mov     [rbp+57h+var_78], rsi
0x18003fe20  mov     [rbp+57h+var_A0], esi
0x18003fe23  mov     rdx, r8; pInputStream
0x18003fe26  lea     rcx, [rbp+57h+ppvObject]; ppvObject
0x18003fe2a  call    CreateReaderOnStream
0x18003fe2f  nop
0x18003fe30  mov     rcx, [rbp+57h+ppvObject]
0x18003fe34  mov     rax, [rcx]
0x18003fe37  lea     rdx, [rbp+57h+var_A0]
0x18003fe3b  mov     rax, [rax+30h]
0x18003fe3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe44  test    eax, eax
0x18003fe46  jnz     short loc_18003FE8E
0x18003fe48  cmp     [rbp+57h+var_A0], 1
0x18003fe4c  jnz     short loc_18003FE30
0x18003fe4e  mov     [rbp+57h+String2], rsi
0x18003fe52  mov     rcx, [rbp+57h+ppvObject]
0x18003fe56  mov     rax, [rcx]
0x18003fe59  xor     r8d, r8d
0x18003fe5c  lea     rdx, [rbp+57h+String2]
0x18003fe60  mov     rax, [rax+70h]
0x18003fe64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe69  mov     rcx, [rbp+5Fh]; this
0x18003fe6d  test    eax, eax
0x18003fe6f  js      loc_1800401CF
0x18003fe75  mov     rdx, [rbp+57h+String2]; String2
0x18003fe79  lea     rcx, aWapProvisionin; "wap-provisioningdoc"
0x18003fe80  call    cs:__imp__wcsicmp
0x18003fe86  test    eax, eax
0x18003fe88  jnz     loc_1800401AC
0x18003fe8e  mov     r15b, sil
0x18003fe91  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x18003fe95  mov     r14, qword ptr [rbp+57h+var_88]
0x18003fe99  mov     rcx, [rbp+57h+ppvObject]
0x18003fe9d  mov     rax, [rcx]
0x18003fea0  lea     rdx, [rbp+57h+var_A0]
0x18003fea4  mov     rax, [rax+30h]
0x18003fea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fead  test    eax, eax
0x18003feaf  jnz     loc_180040142
0x18003feb5  mov     ecx, [rbp+57h+var_A0]
0x18003feb8  sub     ecx, 1
0x18003febb  jz      short loc_18003FEC7
0x18003febd  cmp     ecx, 0Eh
0x18003fec0  jnz     short loc_18003FE99
0x18003fec2  jmp     loc_18004007B
0x18003fec7  mov     rcx, [rbp+57h+ppvObject]
0x18003fecb  mov     rax, [rcx]
0x18003fece  mov     rax, [rax+0A0h]
0x18003fed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feda  mov     esi, eax
0x18003fedc  mov     [rbp+57h+var_6C], eax
0x18003fedf  xor     r15d, r15d
0x18003fee2  mov     [rbp+57h+String2], r15
0x18003fee6  mov     [rbp+57h+Src], r15
0x18003feea  mov     rcx, [rbp+57h+ppvObject]
0x18003feee  mov     rax, [rcx]
0x18003fef1  xor     r8d, r8d
0x18003fef4  lea     rdx, [rbp+57h+String2]
0x18003fef8  mov     rax, [rax+70h]
0x18003fefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff01  mov     rcx, [rbp+5Fh]; this
0x18003ff05  test    eax, eax
0x18003ff07  js      loc_180040231
0x18003ff0d  mov     rdx, [rbp+57h+String2]; String2
0x18003ff11  lea     rcx, aCharacteristic; "characteristic"
0x18003ff18  call    cs:__imp__wcsicmp
0x18003ff1e  test    eax, eax
0x18003ff20  jnz     short loc_18003FF2B
0x18003ff22  lea     rdx, aType; "type"
0x18003ff29  jmp     short loc_18003FF60
0x18003ff2b  mov     rdx, [rbp+57h+String2]; String2
0x18003ff2f  lea     rcx, aParm; "parm"
0x18003ff36  call    cs:__imp__wcsicmp
0x18003ff3c  test    eax, eax
0x18003ff3e  jz      short loc_18003FF59
0x18003ff40  mov     rdx, [rbp+57h+String2]; String2
0x18003ff44  lea     rcx, aNoparm; "noparm"
0x18003ff4b  call    cs:__imp__wcsicmp
0x18003ff51  test    eax, eax
0x18003ff53  jnz     loc_1800401E4
0x18003ff59  lea     rdx, aName; "name"
0x18003ff60  mov     rcx, [rbp+57h+ppvObject]
0x18003ff64  mov     rax, [rcx]
0x18003ff67  xor     r8d, r8d
0x18003ff6a  mov     rax, [rax+50h]
0x18003ff6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff73  mov     rcx, [rbp+5Fh]; this
0x18003ff77  test    eax, eax
0x18003ff79  js      loc_18004021C
0x18003ff7f  mov     rcx, [rbp+57h+ppvObject]
0x18003ff83  mov     rax, [rcx]
0x18003ff86  xor     r8d, r8d
0x18003ff89  lea     rdx, [rbp+57h+Src]
0x18003ff8d  mov     rax, [rax+80h]
0x18003ff94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff99  mov     rcx, [rbp+5Fh]; this
0x18003ff9d  test    eax, eax
0x18003ff9f  js      loc_180040207
0x18003ffa5  mov     rdx, [rbp+57h+Src]; Src
0x18003ffa9  mov     [rbp+57h+var_40], 7
0x18003ffb1  mov     [rbp+57h+var_48], r15
0x18003ffb5  mov     word ptr [rbp+57h+var_58], r15w
0x18003ffba  cmp     [rdx], r15w
0x18003ffbe  jnz     short loc_18003FFC5
0x18003ffc0  mov     r8, r15
0x18003ffc3  jmp     short loc_18003FFD3
0x18003ffc5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ffc9  inc     r8
0x18003ffcc  cmp     [rdx+r8*2], r15w
0x18003ffd1  jnz     short loc_18003FFC9
0x18003ffd3  lea     rcx, [rbp+57h+var_58]; void *
0x18003ffd7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003ffdc  or      r13d, 4
0x18003ffe0  mov     [rbp+57h+var_70], r13d
0x18003ffe4  lea     rax, [rbp+57h+var_58]
0x18003ffe8  cmp     rax, rbx
0x18003ffeb  jnb     short loc_18004002C
0x18003ffed  lea     rax, [rbp+57h+var_58]
0x18003fff1  cmp     r14, rax
0x18003fff4  ja      short loc_18004002C
0x18003fff6  lea     rsi, [rbp+57h+var_58]
0x18003fffa  sub     rsi, r14
0x18003fffd  cmp     rbx, r12
0x180040000  jnz     short loc_180040017
0x180040002  lea     rcx, [rbp+57h+var_88]
0x180040006  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18004000b  mov     r12, [rbp+57h+var_78]
0x18004000f  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180040013  mov     r14, qword ptr [rbp+57h+var_88]
0x180040017  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18004001b  lea     rdx, [r14+rsi]
0x18004001f  mov     rcx, rbx
0x180040022  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180040027  mov     esi, [rbp+57h+var_6C]
0x18004002a  jmp     short loc_180040052
0x18004002c  cmp     rbx, r12
0x18004002f  jnz     short loc_180040046
0x180040031  lea     rcx, [rbp+57h+var_88]
0x180040035  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18004003a  mov     r12, [rbp+57h+var_78]
0x18004003e  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180040042  mov     r14, qword ptr [rbp+57h+var_88]
0x180040046  lea     rdx, [rbp+57h+var_58]
0x18004004a  mov     rcx, rbx
0x18004004d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180040052  add     rbx, 20h ; ' '
0x180040056  mov     qword ptr [rbp+57h+var_88+8], rbx
0x18004005a  cmp     [rbp+57h+var_40], 8
0x18004005f  jb      short loc_18004006B
0x180040061  mov     rcx, [rbp+57h+var_58]
0x180040065  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004006b  mov     r15b, 1
0x18004006e  test    esi, esi
0x180040070  mov     esi, 0
0x180040075  jz      loc_18003FE99
0x18004007b  test    r15b, r15b
0x18004007e  jz      loc_18004010D
0x180040084  mov     r15b, sil
0x180040087  mov     r8, [rdi+8]
0x18004008b  lea     rax, [rbp+57h+var_88]
0x18004008f  cmp     rax, r8
0x180040092  jnb     short loc_1800400ED
0x180040094  lea     rax, [rbp+57h+var_88]
0x180040098  cmp     [rdi], rax
0x18004009b  ja      short loc_1800400ED
0x18004009d  lea     rcx, [rbp+57h+var_88]
0x1800400a1  sub     rcx, [rdi]
0x1800400a4  mov     rax, 2AAAAAAAAAAAAAABh
0x1800400ae  imul    rcx
0x1800400b1  mov     rsi, rdx
0x1800400b4  sar     rsi, 2
0x1800400b8  mov     rax, rsi
0x1800400bb  shr     rax, 3Fh
0x1800400bf  add     rsi, rax
0x1800400c2  cmp     r8, [rdi+10h]
0x1800400c6  jnz     short loc_1800400D0
0x1800400c8  mov     rcx, rdi
0x1800400cb  call    ?_Reserve@?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::vector<std::wstring>>::_Reserve(unsigned __int64)
0x1800400d0  lea     rcx, [rsi+rsi*2]
0x1800400d4  mov     rax, [rdi]
0x1800400d7  lea     rdx, [rax+rcx*8]
0x1800400db  mov     rcx, [rdi+8]
0x1800400df  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800400e4  add     qword ptr [rdi+8], 18h
0x1800400e9  xor     esi, esi
0x1800400eb  jmp     short loc_18004010D
0x1800400ed  cmp     r8, [rdi+10h]
0x1800400f1  jnz     short loc_1800400FB
0x1800400f3  mov     rcx, rdi
0x1800400f6  call    ?_Reserve@?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::vector<std::wstring>>::_Reserve(unsigned __int64)
0x1800400fb  lea     rdx, [rbp+57h+var_88]
0x1800400ff  mov     rcx, [rdi+8]
0x180040103  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180040108  add     qword ptr [rdi+8], 18h
0x18004010d  cmp     r14, rbx
0x180040110  jz      loc_18003FE99
0x180040116  add     rbx, 0FFFFFFFFFFFFFFE0h
0x18004011a  cmp     qword ptr [rbx+18h], 8
0x18004011f  jb      short loc_18004012A
0x180040121  mov     rcx, [rbx]
0x180040124  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004012a  mov     qword ptr [rbx+18h], 7
0x180040132  mov     [rbx+10h], rsi
0x180040136  mov     [rbx], si
0x180040139  mov     qword ptr [rbp+57h+var_88+8], rbx
0x18004013d  jmp     loc_18003FE99
0x180040142  mov     rcx, [rbp+5Fh]; this
0x180040146  test    eax, eax
0x180040148  js      short loc_180040197
0x18004014a  mov     rcx, [rbp+57h+ppvObject]
0x18004014e  test    rcx, rcx
0x180040151  jz      short loc_180040164
0x180040153  mov     [rbp+57h+ppvObject], rsi
0x180040157  mov     rdx, [rcx]
0x18004015a  mov     rax, [rdx+10h]
0x18004015e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040163  nop
0x180040164  lea     rcx, [rbp+57h+var_88]
0x180040168  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004016d  mov     rax, rdi
0x180040170  mov     rcx, [rbp+57h+var_38]
0x180040174  xor     rcx, rsp; StackCookie
0x180040177  call    __security_check_cookie
0x18004017c  mov     rbx, [rsp+0C0h+arg_0]
0x180040184  add     rsp, 90h
0x18004018b  pop     r15
0x18004018d  pop     r14
0x18004018f  pop     r13
0x180040191  pop     r12
0x180040193  pop     rdi
0x180040194  pop     rsi
0x180040195  pop     rbp
0x180040196  retn
0x180040197  mov     r9d, eax; char *
0x18004019a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800401a1  mov     edx, 86h; void *
0x1800401a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800401ac  mov     ecx, 8000FFFFh
0x1800401b1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800401b6  mov     r9d, eax; char *
0x1800401b9  mov     rcx, [rbp+5Fh]; this
0x1800401bd  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800401c4  mov     edx, 5Dh ; ']'; void *
0x1800401c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800401cf  mov     r9d, eax; char *
0x1800401d2  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800401d9  mov     edx, 20h ; ' '; void *
0x1800401de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800401e4  mov     ecx, 8000FFFFh
0x1800401e9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800401ee  mov     r9d, eax; char *
0x1800401f1  mov     rcx, [rbp+5Fh]; this
0x1800401f5  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x1800401fc  mov     edx, 32h ; '2'; void *
0x180040201  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040207  mov     r9d, eax; char *
0x18004020a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180040211  mov     edx, 36h ; '6'; void *
0x180040216  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004021c  mov     r9d, eax; char *
0x18004021f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x180040226  mov     edx, 35h ; '5'; void *
0x18004022b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040231  mov     r9d, eax; char *
0x180040234  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18004023b  mov     edx, 27h ; '''; void *
0x180040240  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
