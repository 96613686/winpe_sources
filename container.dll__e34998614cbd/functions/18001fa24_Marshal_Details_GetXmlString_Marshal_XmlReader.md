# Marshal::Details::GetXmlString(Marshal::XmlReader &)

- ea: `0x18001fa24`
- end: `0x18001fc25`
- name: `?GetXmlString@Details@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUXmlReader@2@@Z`
- size: `513`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `12`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180013ed4`
- `0x180013fa0`
- `0x180014088`
- `0x18001411c`
- `0x180014278`
- `0x180014378`
- `0x180014478`
- `0x180014578`
- `0x180014678`
- `0x180014778`
- `0x180014878`
- `0x18001492c`

## callees

- `0x180003620`
- `0x180003650`
- `0x18000cd50`
- `0x18001d754`
- `0x18001fa24`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x18001fbe5`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001fbfe`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18001fc13`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall Marshal::Details::GetXmlString(char *Src, _BYTE *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rdx
  void *v8; // r9
  char *v9; // rsi
  __int64 v10; // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  void *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rsi
  char *v18; // rbx
  int v19; // [rsp+20h] [rbp-20h]
  void *v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v22; // [rsp+78h] [rbp+38h] BYREF
  int v23; // [rsp+80h] [rbp+40h] BYREF
  void *Srca; // [rsp+88h] [rbp+48h] BYREF

  v23 = 0;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  v4 = *(_QWORD *)a2;
  if ( a2[48] )
  {
    Srca = 0;
    LODWORD(v22) = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, void **, __int64 *))(*(_QWORD *)v4 + 128LL))(v4, &Srca, &v22);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)v5,
        v19);
    v7 = (unsigned int)v22;
    v8 = Srca;
    if ( (unsigned __int64)(unsigned int)v22 > *((_QWORD *)Src + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        Src,
        (unsigned int)v22,
        v6,
        Srca);
    }
    else
    {
      if ( *((_QWORD *)Src + 3) <= 7u )
        v9 = Src;
      else
        v9 = *(char **)Src;
      *((_QWORD *)Src + 2) = (unsigned int)v22;
      v10 = 2 * v7;
      memmove_0(v9, v8, 2 * v7);
      *(_WORD *)&v9[v10] = 0;
    }
  }
  else if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 160LL))(v4) )
  {
    while ( 1 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)a2 + 48LL))(*(_QWORD *)a2, &v23);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
          (const char *)(unsigned int)v12,
          v19);
      if ( v23 == 15 || !v23 )
        break;
      if ( v23 != 8 )
      {
        if ( (unsigned int)(v23 - 3) > 1 )
        {
          LODWORD(Srca) = 15;
          throw (Marshal::UnmarshalError *)&Srca;
        }
        v20 = 0;
        LODWORD(v22) = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD, void **, __int64 *))(**(_QWORD **)a2 + 128LL))(
                *(_QWORD *)a2,
                &v20,
                &v22);
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x12E,
            (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
            (const char *)(unsigned int)v13,
            v19);
        v14 = (unsigned int)v22;
        v15 = v20;
        v16 = *((_QWORD *)Src + 2);
        if ( (unsigned int)v22 > (unsigned __int64)(*((_QWORD *)Src + 3) - v16) )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            Src,
            (unsigned int)v22);
        }
        else
        {
          v17 = v16 + (unsigned int)v22;
          *((_QWORD *)Src + 2) = v17;
          if ( *((_QWORD *)Src + 3) <= 7u )
            v18 = Src;
          else
            v18 = *(char **)Src;
          memmove_0(&v18[2 * v16], v15, 2 * v14);
          *(_WORD *)&v18[2 * v17] = 0;
        }
      }
    }
  }
  return Src;
}

```

## disassembly

```asm
0x18001fa24  mov     [rsp-28h+arg_0], rcx
0x18001fa29  push    rbp
0x18001fa2a  push    rbx
0x18001fa2b  push    rsi
0x18001fa2c  push    rdi
0x18001fa2d  push    r14
0x18001fa2f  mov     rbp, rsp
0x18001fa32  sub     rsp, 40h
0x18001fa36  mov     r14, rdx
0x18001fa39  mov     rdi, rcx
0x18001fa3c  mov     [rbp+var_10], 0
0x18001fa43  mov     [rbp+arg_10], 0
0x18001fa4a  xorps   xmm0, xmm0
0x18001fa4d  movups  xmmword ptr [rcx], xmm0
0x18001fa50  mov     qword ptr [rcx+10h], 0
0x18001fa58  mov     qword ptr [rcx+18h], 7
0x18001fa60  xor     eax, eax
0x18001fa62  mov     [rcx], ax
0x18001fa65  mov     [rbp+var_10], 1
0x18001fa6c  mov     rcx, [rdx]
0x18001fa6f  cmp     [rdx+30h], al
0x18001fa72  jz      short loc_18001FAEB
0x18001fa74  mov     [rbp+Src], rax
0x18001fa78  mov     dword ptr [rbp+arg_8], eax
0x18001fa7b  mov     rax, [rcx]
0x18001fa7e  lea     r8, [rbp+arg_8]
0x18001fa82  lea     rdx, [rbp+Src]
0x18001fa86  mov     rax, [rax+80h]
0x18001fa8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa92  test    eax, eax
0x18001fa94  js      loc_18001FBF7
0x18001fa9a  mov     edx, dword ptr [rbp+arg_8]
0x18001fa9d  mov     r9, [rbp+Src]
0x18001faa1  cmp     rdx, [rdi+18h]
0x18001faa5  ja      short loc_18001FAE1
0x18001faa7  cmp     qword ptr [rdi+18h], 7
0x18001faac  jbe     short loc_18001FAB3
0x18001faae  mov     rsi, [rdi]
0x18001fab1  jmp     short loc_18001FAB6
0x18001fab3  mov     rsi, rdi
0x18001fab6  mov     [rdi+10h], rdx
0x18001faba  lea     rbx, [rdx+rdx]
0x18001fabe  mov     r8, rbx; Size
0x18001fac1  mov     rdx, r9; Src
0x18001fac4  mov     rcx, rsi; void *
0x18001fac7  call    memmove_0
0x18001facc  xor     eax, eax
0x18001face  mov     [rbx+rsi], ax
0x18001fad2  mov     rax, rdi
0x18001fad5  add     rsp, 40h
0x18001fad9  pop     r14
0x18001fadb  pop     rdi
0x18001fadc  pop     rsi
0x18001fadd  pop     rbx
0x18001fade  pop     rbp
0x18001fadf  retn
0x18001fae1  mov     rcx, rdi
0x18001fae4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001fae9  jmp     short loc_18001FAD2
0x18001faeb  mov     rax, [rcx]
0x18001faee  mov     rax, [rax+0A0h]
0x18001faf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fafa  test    eax, eax
0x18001fafc  jnz     short loc_18001FAD2
0x18001fafe  mov     rcx, [r14]
0x18001fb01  mov     rax, [rcx]
0x18001fb04  lea     rdx, [rbp+arg_10]
0x18001fb08  mov     rax, [rax+30h]
0x18001fb0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb11  mov     rcx, [rbp+28h]; this
0x18001fb15  test    eax, eax
0x18001fb17  js      loc_18001FBE2
0x18001fb1d  mov     eax, [rbp+arg_10]
0x18001fb20  cmp     eax, 0Fh
0x18001fb23  jz      short loc_18001FAD2
0x18001fb25  test    eax, eax
0x18001fb27  jz      short loc_18001FAD2
0x18001fb29  cmp     eax, 8
0x18001fb2c  jz      short loc_18001FAFE
0x18001fb2e  add     eax, 0FFFFFFFDh
0x18001fb31  cmp     eax, 1
0x18001fb34  ja      loc_18001FBCA
0x18001fb3a  mov     [rbp+var_8], 0
0x18001fb42  mov     dword ptr [rbp+arg_8], 0
0x18001fb49  mov     rcx, [r14]
0x18001fb4c  mov     rax, [rcx]
0x18001fb4f  lea     r8, [rbp+arg_8]
0x18001fb53  lea     rdx, [rbp+var_8]
0x18001fb57  mov     rax, [rax+80h]
0x18001fb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb63  mov     rcx, [rbp+28h]; this
0x18001fb67  test    eax, eax
0x18001fb69  js      loc_18001FC10
0x18001fb6f  mov     edx, dword ptr [rbp+arg_8]
0x18001fb72  mov     r9, [rbp+var_8]
0x18001fb76  mov     rcx, [rdi+10h]
0x18001fb7a  mov     rax, [rdi+18h]
0x18001fb7e  sub     rax, rcx
0x18001fb81  cmp     rdx, rax
0x18001fb84  ja      short loc_18001FBB8
0x18001fb86  lea     rsi, [rcx+rdx]
0x18001fb8a  mov     [rdi+10h], rsi
0x18001fb8e  cmp     qword ptr [rdi+18h], 7
0x18001fb93  jbe     short loc_18001FB9A
0x18001fb95  mov     rbx, [rdi]
0x18001fb98  jmp     short loc_18001FB9D
0x18001fb9a  mov     rbx, rdi
0x18001fb9d  lea     r8, [rdx+rdx]; Size
0x18001fba1  lea     rcx, [rbx+rcx*2]; void *
0x18001fba5  mov     rdx, r9; Src
0x18001fba8  call    memmove_0
0x18001fbad  xor     eax, eax
0x18001fbaf  mov     [rbx+rsi*2], ax
0x18001fbb3  jmp     loc_18001FAFE
0x18001fbb8  mov     qword ptr [rsp+40h+var_20], rdx; __int64
0x18001fbbd  mov     rcx, rdi; Src
0x18001fbc0  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001fbc5  jmp     loc_18001FAFE
0x18001fbca  mov     dword ptr [rbp+Src], 0Fh
0x18001fbd1  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x18001fbd8  lea     rcx, [rbp+Src]; pExceptionObject
0x18001fbdc  call    _CxxThrowException_0
0x18001fbe2  mov     r9d, eax; char *
0x18001fbe5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001fbec  mov     edx, 11Dh; void *
0x18001fbf1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fbf7  mov     rcx, [rbp+28h]; this
0x18001fbfb  mov     r9d, eax; char *
0x18001fbfe  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001fc05  mov     edx, 116h; void *
0x18001fc0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fc10  mov     r9d, eax; char *
0x18001fc13  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001fc1a  mov     edx, 12Eh; void *
0x18001fc1f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
