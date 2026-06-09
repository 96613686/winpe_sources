# CMSVidVideoRenderer::SetVRConfig(void)

- ea: `0x180089360`
- end: `0x180089586`
- name: `?SetVRConfig@CMSVidVideoRenderer@@UEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(CMSVidVideoRenderer *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18008812c`
- `0x180089360`
- `0x1800f8010`

## import_xrefs

- `USER32!IsWindow` at `0x1800894f6`
- `USER32!IsWindow` at `0x1800894f6`
- `USER32!SystemParametersInfoW` at `0x18008939c`
- `USER32!SystemParametersInfoW` at `0x1800893b0`
- `USER32!SystemParametersInfoW` at `0x1800893c7`
- `USER32!SystemParametersInfoW` at `0x1800893db`
- `USER32!SystemParametersInfoW` at `0x18008939c`
- `USER32!SystemParametersInfoW` at `0x1800893b0`
- `USER32!SystemParametersInfoW` at `0x1800893c7`
- `USER32!SystemParametersInfoW` at `0x1800893db`

## pseudocode

```c
__int64 __fastcall CMSVidVideoRenderer::SetVRConfig(CMSVidVideoRenderer *this)
{
  __int64 v2; // rdx
  _QWORD *v3; // rsi
  __int64 v4; // rcx
  __int64 result; // rax
  _BOOL8 v6; // rdx
  int v7; // eax
  int v8; // ecx
  HWND v9; // rcx
  int v10; // ecx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  if ( !*((_QWORD *)this + 24) )
    return 0;
  if ( *((_BYTE *)this + 24) )
  {
    if ( *((_BYTE *)this + 92) )
    {
      if ( !*((_BYTE *)this + 73) )
      {
        SystemParametersInfoW(0x4Au, 0, (char *)this + 80, 0);
        SystemParametersInfoW(0x1024u, 0, (char *)this + 76, 0);
        *((_BYTE *)this + 73) = 1;
      }
      SystemParametersInfoW(0x1025u, 0, 0, 0);
      SystemParametersInfoW(0x4Bu, 0, 0, 3u);
    }
    v2 = 8;
    v3 = (_QWORD *)((char *)this + 200);
  }
  else
  {
    v3 = (_QWORD *)((char *)this + 200);
    v4 = *((_QWORD *)this + 25);
    if ( v4 )
    {
      result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 112LL))(v4, *((unsigned int *)this + 17));
      if ( (int)result < 0 )
        return result;
    }
    v2 = 1;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 24) + 48LL))(*((_QWORD *)this + 24), v2) < 0 )
    return 2147549183LL;
  if ( !*v3
    || (!*((_BYTE *)this + 24) ? (v6 = *((_BYTE *)this + 72) != 0) : (v6 = 0),
        result = (*(__int64 (__fastcall **)(_QWORD, _BOOL8))(*(_QWORD *)*v3 + 72LL))(*v3, v6),
        (int)result >= 0) )
  {
    if ( !*((_QWORD *)this + 32)
      || (result = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 24LL))(*((_QWORD *)this + 24)),
          (int)result >= 0) )
    {
      if ( this == (CMSVidVideoRenderer *)-32LL )
      {
        v11 = 0;
        v12 = 0;
        result = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(MEMORY[0xFFFFFFFFFFFFFFE0] + 256LL))(
                   -32,
                   &v11,
                   &v12);
        if ( (int)result < 0 )
          return result;
        v7 = v11;
        v8 = HIDWORD(v11);
        *((_QWORD *)this + 4) = 0;
        MEMORY[8] = v7;
        MEMORY[0xC] = v8;
      }
      result = (*(__int64 (__fastcall **)(CMSVidVideoRenderer *))(*(_QWORD *)this + 360LL))(this);
      if ( (int)result >= 0 )
      {
        v9 = (HWND)*((_QWORD *)this + 2);
        if ( v9 == HWND_MESSAGE|0x2LL
          || !IsWindow(v9)
          || !*v3
          || (result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 80LL))(*v3, *((_QWORD *)this + 2)),
              (int)result >= 0) )
        {
          if ( !*v3 )
            return ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(
                     0xC0040590,
                     &GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36,
                     -2147467259,
                     hInstance);
          v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 128LL))(*v3, *((unsigned int *)this + 16));
          if ( v10 < 0 )
          {
            result = 0;
            if ( v10 != -2147467263 )
              return (unsigned int)v10;
            return result;
          }
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180089360  mov     [rsp+arg_10], rbx
0x180089365  push    rbp
0x180089366  push    rsi
0x180089367  push    rdi
0x180089368  sub     rsp, 20h
0x18008936c  xor     ebp, ebp
0x18008936e  mov     rbx, rcx
0x180089371  cmp     [rcx+0C0h], rbp
0x180089378  jz      loc_180089577
0x18008937e  cmp     [rcx+18h], bpl
0x180089382  jz      short loc_1800893EF
0x180089384  cmp     [rcx+5Ch], bpl
0x180089388  jz      short loc_1800893E1
0x18008938a  cmp     [rcx+49h], bpl
0x18008938e  jnz     short loc_1800893BA
0x180089390  lea     r8, [rcx+50h]; pvParam
0x180089394  xor     r9d, r9d; fWinIni
0x180089397  lea     ecx, [rbp+4Ah]; uiAction
0x18008939a  xor     edx, edx; uiParam
0x18008939c  call    cs:__imp_SystemParametersInfoW
0x1800893a2  lea     r8, [rbx+4Ch]; pvParam
0x1800893a6  xor     r9d, r9d; fWinIni
0x1800893a9  xor     edx, edx; uiParam
0x1800893ab  mov     ecx, 1024h; uiAction
0x1800893b0  call    cs:__imp_SystemParametersInfoW
0x1800893b6  mov     byte ptr [rbx+49h], 1
0x1800893ba  xor     r9d, r9d; fWinIni
0x1800893bd  xor     r8d, r8d; pvParam
0x1800893c0  xor     edx, edx; uiParam
0x1800893c2  mov     ecx, 1025h; uiAction
0x1800893c7  call    cs:__imp_SystemParametersInfoW
0x1800893cd  xor     edx, edx; uiParam
0x1800893cf  mov     r9d, 3; fWinIni
0x1800893d5  xor     r8d, r8d; pvParam
0x1800893d8  lea     ecx, [rdx+4Bh]; uiAction
0x1800893db  call    cs:__imp_SystemParametersInfoW
0x1800893e1  mov     edx, 8
0x1800893e6  lea     rsi, [rbx+0C8h]
0x1800893ed  jmp     short loc_18008941A
0x1800893ef  lea     rsi, [rcx+0C8h]
0x1800893f6  mov     rcx, [rsi]
0x1800893f9  test    rcx, rcx
0x1800893fc  jz      short loc_180089415
0x1800893fe  mov     rax, [rcx]
0x180089401  mov     edx, [rbx+44h]
0x180089404  mov     rax, [rax+70h]
0x180089408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008940d  test    eax, eax
0x18008940f  js      loc_180089579
0x180089415  mov     edx, 1
0x18008941a  mov     rcx, [rbx+0C0h]
0x180089421  mov     rax, [rcx]
0x180089424  mov     rax, [rax+30h]
0x180089428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008942d  test    eax, eax
0x18008942f  jns     short loc_18008943B
0x180089431  mov     eax, 8000FFFFh
0x180089436  jmp     loc_180089579
0x18008943b  mov     rcx, [rsi]
0x18008943e  test    rcx, rcx
0x180089441  jz      short loc_180089463
0x180089443  mov     rax, [rcx]
0x180089446  mov     rax, [rax+48h]
0x18008944a  cmp     [rbx+18h], bpl
0x18008944e  jz      loc_180089549
0x180089454  xor     edx, edx
0x180089456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008945b  test    eax, eax
0x18008945d  js      loc_180089579
0x180089463  mov     rdx, [rbx+100h]
0x18008946a  test    rdx, rdx
0x18008946d  jz      short loc_18008948A
0x18008946f  mov     rcx, [rbx+0C0h]
0x180089476  mov     rax, [rcx]
0x180089479  mov     rax, [rax+18h]
0x18008947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089482  test    eax, eax
0x180089484  js      loc_180089579
0x18008948a  lea     rdi, [rbx+20h]
0x18008948e  test    rdi, rdi
0x180089491  jnz     short loc_1800894D2
0x180089493  mov     rax, [rbx]
0x180089496  lea     r8, [rsp+38h+arg_8]
0x18008949b  lea     rdx, [rsp+38h+arg_0]
0x1800894a0  mov     [rsp+38h+arg_0], rbp
0x1800894a5  mov     rcx, rbx
0x1800894a8  mov     [rsp+38h+arg_8], rbp
0x1800894ad  mov     rax, [rax+100h]
0x1800894b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894b9  test    eax, eax
0x1800894bb  js      loc_180089579
0x1800894c1  mov     eax, dword ptr [rsp+38h+arg_0]
0x1800894c5  mov     ecx, dword ptr [rsp+38h+arg_0+4]
0x1800894c9  mov     [rdi], rbp
0x1800894cc  mov     [rdi+8], eax
0x1800894cf  mov     [rdi+0Ch], ecx
0x1800894d2  mov     rax, [rbx]
0x1800894d5  mov     rcx, rbx
0x1800894d8  mov     rax, [rax+168h]
0x1800894df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894e4  test    eax, eax
0x1800894e6  js      loc_180089579
0x1800894ec  mov     rcx, [rbx+10h]; hWnd
0x1800894f0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800894f4  jz      short loc_18008951C
0x1800894f6  call    cs:__imp_IsWindow
0x1800894fc  test    eax, eax
0x1800894fe  jz      short loc_18008951C
0x180089500  mov     rcx, [rsi]
0x180089503  test    rcx, rcx
0x180089506  jz      short loc_18008951C
0x180089508  mov     rax, [rcx]
0x18008950b  mov     rdx, [rbx+10h]
0x18008950f  mov     rax, [rax+50h]
0x180089513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089518  test    eax, eax
0x18008951a  js      short loc_180089579
0x18008951c  mov     rcx, [rsi]
0x18008951f  test    rcx, rcx
0x180089522  jz      short loc_180089557
0x180089524  mov     rax, [rcx]
0x180089527  mov     edx, [rbx+40h]
0x18008952a  mov     rax, [rax+80h]
0x180089531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089536  mov     ecx, eax
0x180089538  test    eax, eax
0x18008953a  jns     short loc_180089577
0x18008953c  cmp     ecx, 80004001h
0x180089542  mov     eax, ebp
0x180089544  cmovnz  eax, ecx
0x180089547  jmp     short loc_180089579
0x180089549  cmp     [rbx+48h], bpl
0x18008954d  mov     edx, ebp
0x18008954f  setnz   dl
0x180089552  jmp     loc_180089456
0x180089557  mov     r9, cs:hInstance; HINSTANCE
0x18008955e  lea     rdx, _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36; struct _GUID *
0x180089565  mov     r8d, 80004005h; int
0x18008956b  mov     ecx, 0C0040590h; dwMessageId
0x180089570  call    ?Error@?$CComCoClass@VCMSVidVideoRenderer@@$1?_GUID_37b03543_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidVideoRenderer,&__s_GUID const _GUID_37b03543_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x180089575  jmp     short loc_180089579
0x180089577  xor     eax, eax
0x180089579  mov     rbx, [rsp+38h+arg_10]
0x18008957e  add     rsp, 20h
0x180089582  pop     rdi
0x180089583  pop     rsi
0x180089584  pop     rbp
0x180089585  retn
```
