# _lambda_4f9cb091d726181fa859ce89134efc24_::operator()(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)

- ea: `0x180009138`
- end: `0x1800091d9`
- name: `??R_lambda_4f9cb091d726181fa859ce89134efc24_@@QEBA@PEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64 **, __int64, char, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800091e0`

## callees

- `0x180007550`
- `0x180009138`
- `0x18000cc34`
- `0x180022010`

## string_xrefs

- `0x180009176`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall _lambda_4f9cb091d726181fa859ce89134efc24_::operator()(__int64 **a1, __int64 a2, char a3, char *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char v10; // al
  __int64 *v11; // rcx
  char v12; // bl
  char v13; // cl
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, **a1, *a1[1]);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v11 = *a1;
    v12 = v10;
    v16 = v10;
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::EvaluatingRegistration<unsigned short * &,bool &>(
      v11,
      &v16);
    if ( v12 )
    {
      v13 = 0;
      *(_BYTE *)a1[3] = 1;
    }
    else
    {
      v13 = 1;
      ++*(_DWORD *)a1[4];
    }
    *a4 = v13;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v7,
      v14);
    return v8;
  }
}

```

## disassembly

```asm
0x180009138  mov     [rsp+arg_10], r8b
0x18000913d  push    rbx
0x18000913e  push    rsi
0x18000913f  push    rdi
0x180009140  push    r14
0x180009142  sub     rsp, 28h
0x180009146  mov     rax, [rdx]
0x180009149  mov     rsi, rdx
0x18000914c  mov     rdx, [rcx]
0x18000914f  mov     rdi, rcx
0x180009152  mov     r8, [rcx+8]
0x180009156  mov     r14, r9
0x180009159  mov     rcx, rsi
0x18000915c  mov     rax, [rax+20h]
0x180009160  mov     rdx, [rdx]
0x180009163  mov     r8, [r8]
0x180009166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916b  mov     ebx, eax
0x18000916d  test    eax, eax
0x18000916f  jns     short loc_18000918E
0x180009171  mov     rcx, [rsp+48h]; this
0x180009176  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000917d  mov     r9d, eax; char *
0x180009180  mov     edx, 1B7h; void *
0x180009185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000918a  mov     eax, ebx
0x18000918c  jmp     short loc_1800091CF
0x18000918e  mov     rax, [rsi]
0x180009191  mov     rcx, rsi
0x180009194  mov     rax, [rax+10h]
0x180009198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919d  mov     rcx, [rdi]
0x1800091a0  lea     rdx, [rsp+48h+arg_10]
0x1800091a5  mov     bl, al
0x1800091a7  mov     [rsp+48h+arg_10], al
0x1800091ab  call    ??$EvaluatingRegistration@AEAPEAGAEA_N@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAXAEAPEAGAEA_N@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::EvaluatingRegistration<ushort * &,bool &>(ushort * &,bool &)
0x1800091b0  test    bl, bl
0x1800091b2  jz      short loc_1800091BF
0x1800091b4  mov     rax, [rdi+18h]
0x1800091b8  xor     cl, cl
0x1800091ba  mov     byte ptr [rax], 1
0x1800091bd  jmp     short loc_1800091CA
0x1800091bf  mov     rax, [rdi+20h]
0x1800091c3  mov     ecx, 1
0x1800091c8  add     [rax], ecx
0x1800091ca  mov     [r14], cl
0x1800091cd  xor     eax, eax
0x1800091cf  add     rsp, 28h
0x1800091d3  pop     r14
0x1800091d5  pop     rdi
0x1800091d6  pop     rsi
0x1800091d7  pop     rbx
0x1800091d8  retn
```
