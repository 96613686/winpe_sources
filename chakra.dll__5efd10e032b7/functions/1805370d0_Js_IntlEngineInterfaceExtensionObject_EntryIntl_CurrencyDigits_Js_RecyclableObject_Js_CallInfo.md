# Js::IntlEngineInterfaceExtensionObject::EntryIntl_CurrencyDigits(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1805370d0`
- end: `0x18053722b`
- name: `?EntryIntl_CurrencyDigits@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800a2a0c`
- `0x180189ef4`
- `0x1803bcf80`
- `0x1803c4080`
- `0x180536c54`
- `0x1805370d0`
- `0x1805cd010`

## import_xrefs

- `icu!unum_open` at `0x18053718d`
- `icu!unum_open` at `0x18053718d`
- `icu!unum_setTextAttribute` at `0x1805371b9`
- `icu!unum_setTextAttribute` at `0x1805371b9`
- `icu!unum_getAttribute` at `0x1805371e5`
- `icu!unum_getAttribute` at `0x1805371e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_CurrencyDigits(
        __int64 a1,
        int a2,
        __int64 a3,
        void *a4)
{
  ThreadContext **v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rbx
  int v10; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v11[6]; // [rsp+38h] [rbp-30h] BYREF

  v11[1] = -2;
  v4 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v4[110], 0xC00u, (struct Js::ScriptContext *)v4, 0);
  v11[0] = 0;
  if ( (a2 & 0xFFFFFF) != 2 || !Js::JavascriptString::Is(a4) )
  {
LABEL_9:
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x18053722ALL);
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 752LL))(v5);
  v10 = 0;
  v7 = unum_open(2, 0, 0, 0, 0, &v10);
  v11[0] = v7;
  unum_setTextAttribute(v7, 5, v6, 0xFFFFFFFFLL, &v10);
  if ( v10 == 7 )
    Js::Throw::OutOfMemory();
  if ( v10 > 0 || v10 == -124 )
  {
    Js::Throw::FatalInternalError(-2147467259);
    goto LABEL_9;
  }
  v8 = (unsigned int)unum_getAttribute(v7, 8) | 0x1000000000000LL;
  PlatformAgnostic::ICUHelpers::ScopedICUObject<void * *,&void unum_close(void * *)>::~ScopedICUObject<void * *,&void unum_close(void * *)>(v11);
  return v8;
}

```

## disassembly

```asm
0x1805370d0  mov     rax, rsp
0x1805370d3  mov     [rax+10h], rdx
0x1805370d7  mov     [rax+8], rcx
0x1805370db  mov     [rax+18h], r8
0x1805370df  mov     [rax+20h], r9
0x1805370e3  push    rbx
0x1805370e4  push    rdi
0x1805370e5  sub     rsp, 58h
0x1805370e9  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1805370f1  mov     rax, [rax+8]
0x1805370f5  mov     rcx, [rax+8]
0x1805370f9  mov     rax, [rcx+8]
0x1805370fd  mov     rcx, [rax+440h]
0x180537104  xor     r9d, r9d; void *
0x180537107  mov     r8, rcx; struct Js::ScriptContext *
0x18053710a  mov     edx, 0C00h; unsigned __int64
0x18053710f  mov     rcx, [rcx+370h]; this
0x180537116  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x18053711b  mov     [rsp+68h+var_30], 0
0x180537124  lea     rdx, [rsp+68h+arg_10]
0x18053712c  mov     eax, [rsp+68h+arg_8]
0x180537130  and     eax, 0FFFFFFh
0x180537135  cmp     eax, 2
0x180537138  jnz     loc_180537220
0x18053713e  mov     rdx, [rdx+8]
0x180537142  mov     rcx, rdx; void *
0x180537145  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x18053714a  test    al, al
0x18053714c  jz      loc_180537220
0x180537152  mov     rax, [rdx]
0x180537155  mov     rcx, rdx
0x180537158  mov     rax, [rax+2F0h]
0x18053715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180537164  mov     rdi, rax
0x180537167  mov     [rsp+68h+var_38], 0
0x18053716f  lea     rax, [rsp+68h+var_38]
0x180537174  mov     [rsp+68h+var_40], rax
0x180537179  mov     [rsp+68h+var_48], 0
0x180537182  xor     r9d, r9d
0x180537185  xor     r8d, r8d
0x180537188  xor     edx, edx
0x18053718a  lea     ecx, [rdx+2]
0x18053718d  call    cs:__imp_unum_open
0x180537194  nop     dword ptr [rax+rax+00h]
0x180537199  mov     rbx, rax
0x18053719c  mov     [rsp+68h+var_30], rax
0x1805371a1  lea     rax, [rsp+68h+var_38]
0x1805371a6  mov     [rsp+68h+var_48], rax
0x1805371ab  or      r9d, 0FFFFFFFFh
0x1805371af  mov     r8, rdi
0x1805371b2  lea     edx, [r9+6]
0x1805371b6  mov     rcx, rbx
0x1805371b9  call    cs:__imp_unum_setTextAttribute
0x1805371c0  nop     dword ptr [rax+rax+00h]
0x1805371c5  mov     eax, [rsp+68h+var_38]
0x1805371c9  cmp     eax, 7
0x1805371cc  jnz     short loc_1805371D4
0x1805371ce  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1805371d4  test    eax, eax
0x1805371d6  jg      short loc_180537215
0x1805371d8  cmp     eax, 0FFFFFF84h
0x1805371db  jz      short loc_180537215
0x1805371dd  mov     edx, 8
0x1805371e2  mov     rcx, rbx
0x1805371e5  call    cs:__imp_unum_getAttribute
0x1805371ec  nop     dword ptr [rax+rax+00h]
0x1805371f1  mov     ebx, eax
0x1805371f3  mov     rax, 1000000000000h
0x1805371fd  or      rbx, rax
0x180537200  lea     rcx, [rsp+68h+var_30]
0x180537205  call    ??1?$ScopedICUObject@PEAPEAX$1?unum_close@@YAXPEAPEAX@Z@ICUHelpers@PlatformAgnostic@@QEAA@XZ; PlatformAgnostic::ICUHelpers::ScopedICUObject<void * *,&unum_close(void * *)>::~ScopedICUObject<void * *,&unum_close(void * *)>(void)
0x18053720a  mov     rax, rbx
0x18053720d  add     rsp, 58h
0x180537211  pop     rdi
0x180537212  pop     rbx
0x180537213  retn
0x180537215  mov     ecx, 80004005h; int
0x18053721a  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18053721f  nop
0x180537220  mov     ecx, 80004005h; int
0x180537225  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
