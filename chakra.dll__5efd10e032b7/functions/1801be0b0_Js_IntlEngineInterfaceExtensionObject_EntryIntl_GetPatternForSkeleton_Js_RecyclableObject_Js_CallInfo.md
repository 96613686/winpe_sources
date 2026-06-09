# Js::IntlEngineInterfaceExtensionObject::EntryIntl_GetPatternForSkeleton(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1801be0b0`
- end: `0x1801be2fb`
- name: `?EntryIntl_GetPatternForSkeleton@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `587`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x1800a21a4`
- `0x1800a2a0c`
- `0x180189ef4`
- `0x1801bd8b4`
- `0x1801be0b0`
- `0x1801be304`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `icu!uloc_getBaseName` at `0x1801be1df`
- `icu!uloc_getBaseName` at `0x1801be1df`
- `icu!udatpg_open` at `0x1801be212`
- `icu!udatpg_open` at `0x1801be212`
- `icu!udatpg_close` at `0x1801be2a1`
- `icu!udatpg_close` at `0x1801be2a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_GetPatternForSkeleton(
        __int64 a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  ThreadContext **v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // rsi
  unsigned int v9; // ebx
  __int64 v10; // rax
  int BaseName; // eax
  __int64 v12; // rbx
  int v14; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v16; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v20[160]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v21[160]; // [rsp+118h] [rbp+10h] BYREF

  v19[2] = -2;
  v5 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v5[110], 0xC00u, (struct Js::ScriptContext *)v5, 0);
  v16 = 0;
  if ( (a2 & 0xFFFFFF) != 3 || !Js::JavascriptString::Is(a4) || !Js::JavascriptString::Is(*(void **)(v6 + 16)) )
    goto LABEL_6;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v18 = v7;
  v14 = 0;
  memset_0(v20, 0, 0x9Du);
  v9 = a4[6];
  v10 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a4 + 752LL))(a4);
  Js::LangtagToLocaleID_157__0(v10, v9, v20);
  memset_0(v21, 0, 0x9Du);
  BaseName = uloc_getBaseName(v20, v21, 157, &v14);
  if ( v14 == 7 )
    Js::Throw::OutOfMemory();
  if ( v14 > 0 || v14 == -124 || (unsigned int)(BaseName - 1) > 0x9B )
  {
LABEL_6:
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  v17 = udatpg_open(v21, &v14);
  if ( v14 == 7 )
    Js::Throw::OutOfMemory();
  if ( v14 > 0 || v14 == -124 )
  {
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x1801BE2FALL);
  }
  v16 = 0;
  v15 = 0;
  v19[0] = &v17;
  v19[1] = &v18;
  Js::EnsureBuffer__lambda_4c8349b5d09978f94966c98cc7e2b09f___(v19, *(_QWORD *)(v8 + 1008), &v16, &v15);
  v12 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v16, v15, v8);
  if ( v17 )
    udatpg_close();
  return v12;
}

```

## disassembly

```asm
0x1801be0b0  mov     rax, rsp
0x1801be0b3  mov     [rax+10h], rdx
0x1801be0b7  mov     [rax+8], rcx
0x1801be0bb  mov     [rax+18h], r8
0x1801be0bf  mov     [rax+20h], r9
0x1801be0c3  push    rbp
0x1801be0c4  push    rbx
0x1801be0c5  push    rsi
0x1801be0c6  push    rdi
0x1801be0c7  lea     rbp, [rax-0E8h]
0x1801be0ce  sub     rsp, 1C8h
0x1801be0d5  mov     qword ptr [rsp+60h], 0FFFFFFFFFFFFFFFEh
0x1801be0de  mov     rax, cs:__security_cookie
0x1801be0e5  xor     rax, rsp
0x1801be0e8  mov     [rbp+0E0h+var_30], rax
0x1801be0ef  mov     rbx, [rbp+0E0h+arg_0]
0x1801be0f6  mov     rax, [rbx+8]
0x1801be0fa  mov     rcx, [rax+8]
0x1801be0fe  mov     rcx, [rcx+440h]
0x1801be105  xor     r9d, r9d; void *
0x1801be108  mov     r8, rcx; struct Js::ScriptContext *
0x1801be10b  mov     edx, 0C00h; unsigned __int64
0x1801be110  mov     rcx, [rcx+370h]; this
0x1801be117  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1801be11c  mov     [rsp+1E0h+var_1A8], 0
0x1801be125  lea     r8, [rbp+0E0h+arg_10]
0x1801be12c  mov     eax, [rbp+0E0h+arg_8]
0x1801be132  and     eax, 0FFFFFFh
0x1801be137  cmp     eax, 3
0x1801be13a  jnz     loc_1801BE1FE
0x1801be140  mov     rdi, [r8+8]
0x1801be144  mov     rcx, rdi; void *
0x1801be147  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801be14c  test    al, al
0x1801be14e  jz      loc_1801BE1FE
0x1801be154  mov     r8, [r8+10h]
0x1801be158  mov     rcx, r8; void *
0x1801be15b  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801be160  test    al, al
0x1801be162  jz      loc_1801BE1FE
0x1801be168  mov     rax, [rbx+8]
0x1801be16c  mov     rdx, [rax+8]
0x1801be170  mov     rsi, [rdx+440h]
0x1801be177  mov     [rsp+1E0h+var_198], r8
0x1801be17c  mov     dword ptr [rsp+1E0h+var_1B0], 0
0x1801be184  xor     edx, edx; Val
0x1801be186  mov     r8d, 9Dh; Size
0x1801be18c  lea     rcx, [rsp+1E0h+var_170]; void *
0x1801be191  call    memset_0
0x1801be196  mov     ebx, [rdi+18h]
0x1801be199  mov     rax, [rdi]
0x1801be19c  mov     rcx, rdi
0x1801be19f  mov     rax, [rax+2F0h]
0x1801be1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801be1ab  lea     r8, [rsp+1E0h+var_170]
0x1801be1b0  mov     edx, ebx
0x1801be1b2  mov     rcx, rax
0x1801be1b5  call    Js__LangtagToLocaleID_157__0
0x1801be1ba  xor     edx, edx; Val
0x1801be1bc  mov     r8d, 9Dh; Size
0x1801be1c2  lea     rcx, [rbp+0E0h+var_D0]; void *
0x1801be1c6  call    memset_0
0x1801be1cb  lea     r9, [rsp+1E0h+var_1B0]
0x1801be1d0  mov     r8d, 9Dh
0x1801be1d6  lea     rdx, [rbp+0E0h+var_D0]
0x1801be1da  lea     rcx, [rsp+1E0h+var_170]
0x1801be1df  call    cs:__imp_uloc_getBaseName
0x1801be1e6  nop     dword ptr [rax+rax+00h]
0x1801be1eb  mov     ecx, dword ptr [rsp+1E0h+var_1B0]
0x1801be1ef  cmp     ecx, 7
0x1801be1f2  jnz     loc_1801BE2CD
0x1801be1f8  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801be1fe  mov     ecx, 80004005h; int
0x1801be203  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x1801be208  int     3; Trap to Debugger
0x1801be209  lea     rdx, [rsp+1E0h+var_1B0]
0x1801be20e  lea     rcx, [rbp+0E0h+var_D0]
0x1801be212  call    cs:__imp_udatpg_open
0x1801be219  nop     dword ptr [rax+rax+00h]
0x1801be21e  mov     [rsp+1E0h+var_1A0], rax
0x1801be223  mov     eax, dword ptr [rsp+1E0h+var_1B0]
0x1801be227  cmp     eax, 7
0x1801be22a  jnz     short loc_1801BE232
0x1801be22c  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1801be232  test    eax, eax
0x1801be234  jg      loc_1801BE2F0
0x1801be23a  cmp     eax, 0FFFFFF84h
0x1801be23d  jz      loc_1801BE2F0
0x1801be243  mov     [rsp+1E0h+var_1A8], 0
0x1801be24c  mov     dword ptr [rsp+1E0h+var_1B0+4], 0
0x1801be254  lea     rax, [rsp+1E0h+var_1A0]
0x1801be259  mov     [rsp+1E0h+var_190], rax
0x1801be25e  lea     rax, [rsp+1E0h+var_198]
0x1801be263  mov     [rsp+1E0h+var_188], rax
0x1801be268  lea     r9, [rsp+1E0h+var_1B0+4]
0x1801be26d  lea     r8, [rsp+1E0h+var_1A8]
0x1801be272  mov     rdx, [rsi+3F0h]
0x1801be279  lea     rcx, [rsp+1E0h+var_190]
0x1801be27e  call    Js__EnsureBuffer__lambda_4c8349b5d09978f94966c98cc7e2b09f___
0x1801be283  mov     r8, rsi
0x1801be286  mov     edx, dword ptr [rsp+1E0h+var_1B0+4]
0x1801be28a  mov     rcx, [rsp+1E0h+var_1A8]
0x1801be28f  call    ??$NewWithBufferT@VLiteralString@Js@@$0A@@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(ushort const *,uint,Js::ScriptContext *)
0x1801be294  mov     rbx, rax
0x1801be297  mov     rcx, [rsp+1E0h+var_1A0]
0x1801be29c  test    rcx, rcx
0x1801be29f  jz      short loc_1801BE2AE
0x1801be2a1  call    cs:__imp_udatpg_close
0x1801be2a8  nop     dword ptr [rax+rax+00h]
0x1801be2ad  nop
0x1801be2ae  mov     rax, rbx
0x1801be2b1  mov     rcx, [rbp+0E0h+var_30]
0x1801be2b8  xor     rcx, rsp; StackCookie
0x1801be2bb  call    __security_check_cookie
0x1801be2c0  add     rsp, 1C8h
0x1801be2c7  pop     rdi
0x1801be2c8  pop     rsi
0x1801be2c9  pop     rbx
0x1801be2ca  pop     rbp
0x1801be2cb  retn
0x1801be2cd  test    ecx, ecx
0x1801be2cf  jg      loc_1801BE1FE
0x1801be2d5  cmp     ecx, 0FFFFFF84h
0x1801be2d8  jz      loc_1801BE1FE
0x1801be2de  dec     eax
0x1801be2e0  cmp     eax, 9Bh
0x1801be2e5  ja      loc_1801BE1FE
0x1801be2eb  jmp     loc_1801BE209
0x1801be2f0  mov     ecx, 80004005h; int
0x1801be2f5  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
