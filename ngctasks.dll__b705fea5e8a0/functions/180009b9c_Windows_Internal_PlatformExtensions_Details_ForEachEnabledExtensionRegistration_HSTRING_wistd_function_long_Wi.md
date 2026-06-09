# Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)

- ea: `0x180009b9c`
- end: `0x180009d35`
- name: `?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e750`

## callees

- `0x180009b9c`
- `0x18000a2ac`
- `0x18000cc34`
- `0x18000ef6c`
- `0x180022010`

## string_xrefs

- `0x180009bfc`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180009d08`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(
        HSTRING a1,
        __int64 a2)
{
  int ExtensionRegistrationsForExtensionPoint; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rsi
  unsigned __int64 i; // rbx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-40h]
  char v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v19; // [rsp+90h] [rbp+30h] BYREF
  char *v20; // [rsp+98h] [rbp+38h] BYREF

  v15 = 0;
  ExtensionRegistrationsForExtensionPoint = Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(a1);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 352;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)ExtensionRegistrationsForExtensionPoint,
      v12);
    goto LABEL_20;
  }
  v16 = 0;
  v6 = v15;
  ExtensionRegistrationsForExtensionPoint = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v15 + 8LL))(
                                              v15,
                                              &v16);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 355;
    goto LABEL_5;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v16 )
      goto LABEL_15;
    v14 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, i, &v14);
    if ( v8 < 0 )
      break;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      v13 = 0;
      v20 = &v13;
      v19 = 0;
      v17 = v14;
      v9 = *(_QWORD *)(a2 + 112);
      if ( !v9 )
        __fastfail(7u);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, char *, char **))(*(_QWORD *)v9 + 32LL))(v9, &v17, &v19, &v20);
      if ( v8 < 0 )
      {
        v11 = 389;
        goto LABEL_19;
      }
      if ( !v13 )
      {
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v14,
          0);
LABEL_15:
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v15,
          0);
        return 0;
      }
    }
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      &v14,
      0);
  }
  v11 = 365;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v8,
    v12);
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v14,
    0);
  v4 = v8;
LABEL_20:
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v15,
    0);
  return v4;
}

```

## disassembly

```asm
0x180009b9c  mov     [rsp-18h+arg_0], rbx
0x180009ba1  mov     [rsp-18h+arg_8], rsi
0x180009ba6  push    rbp
0x180009ba7  push    rdi
0x180009ba8  push    r14
0x180009baa  mov     rbp, rsp
0x180009bad  sub     rsp, 60h
0x180009bb1  mov     r14, rdx
0x180009bb4  mov     [rbp+var_20], 0
0x180009bbc  lea     rdx, [rbp+var_20]
0x180009bc0  call    ?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)
0x180009bc5  mov     ebx, eax
0x180009bc7  test    eax, eax
0x180009bc9  jns     short loc_180009BD2
0x180009bcb  mov     edx, 160h
0x180009bd0  jmp     short loc_180009BFC
0x180009bd2  mov     [rbp+var_18], 0
0x180009bda  mov     rsi, [rbp+var_20]
0x180009bde  mov     rax, [rsi]
0x180009be1  lea     rdx, [rbp+var_18]
0x180009be5  mov     rcx, rsi
0x180009be8  mov     rax, [rax+8]
0x180009bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf1  mov     ebx, eax
0x180009bf3  test    eax, eax
0x180009bf5  jns     short loc_180009C14
0x180009bf7  mov     edx, 163h; void *
0x180009bfc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009c03  mov     r9d, eax; char *
0x180009c06  mov     rcx, [rbp+18h]; this
0x180009c0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c0f  jmp     loc_180009D26
0x180009c14  xor     ebx, ebx
0x180009c16  cmp     rbx, [rbp+var_18]
0x180009c1a  jnb     loc_180009CD0
0x180009c20  mov     [rbp+var_28], 0
0x180009c28  mov     rax, [rsi]
0x180009c2b  lea     r8, [rbp+var_28]
0x180009c2f  mov     rdx, rbx
0x180009c32  mov     rcx, rsi
0x180009c35  mov     rax, [rax+10h]
0x180009c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3e  mov     edi, eax
0x180009c40  test    eax, eax
0x180009c42  js      loc_180009D00
0x180009c48  mov     rcx, [rbp+var_28]
0x180009c4c  mov     rax, [rcx]
0x180009c4f  mov     rax, [rax+8]
0x180009c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c58  test    al, al
0x180009c5a  jnz     short loc_180009CB1
0x180009c5c  mov     rcx, [rbp+var_28]
0x180009c60  mov     rax, [rcx]
0x180009c63  mov     rax, [rax+28h]
0x180009c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6c  mov     [rbp+var_30], 0
0x180009c70  lea     rax, [rbp+var_30]
0x180009c74  mov     [rbp+arg_18], rax
0x180009c78  mov     [rbp+arg_10], 0
0x180009c7c  mov     rax, [rbp+var_28]
0x180009c80  mov     [rbp+var_10], rax
0x180009c84  mov     rcx, [r14+70h]
0x180009c88  test    rcx, rcx
0x180009c8b  jz      short loc_180009CF9
0x180009c8d  mov     rax, [rcx]
0x180009c90  lea     r9, [rbp+arg_18]
0x180009c94  lea     r8, [rbp+arg_10]
0x180009c98  lea     rdx, [rbp+var_10]
0x180009c9c  mov     rax, [rax+20h]
0x180009ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca5  mov     edi, eax
0x180009ca7  test    eax, eax
0x180009ca9  js      short loc_180009CF2
0x180009cab  cmp     [rbp+var_30], 0
0x180009caf  jz      short loc_180009CC4
0x180009cb1  xor     edx, edx
0x180009cb3  lea     rcx, [rbp+var_28]
0x180009cb7  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009cbc  inc     rbx
0x180009cbf  jmp     loc_180009C16
0x180009cc4  xor     edx, edx
0x180009cc6  lea     rcx, [rbp+var_28]
0x180009cca  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009ccf  nop
0x180009cd0  xor     edx, edx
0x180009cd2  lea     rcx, [rbp+var_20]
0x180009cd6  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009cdb  xor     eax, eax
0x180009cdd  lea     r11, [rsp+60h+var_s0]
0x180009ce2  mov     rbx, [r11+20h]
0x180009ce6  mov     rsi, [r11+28h]
0x180009cea  mov     rsp, r11
0x180009ced  pop     r14
0x180009cef  pop     rdi
0x180009cf0  pop     rbp
0x180009cf1  retn
0x180009cf2  mov     edx, 185h
0x180009cf7  jmp     short loc_180009D05
0x180009cf9  mov     ecx, 7
0x180009cfe  int     29h; Win8: RtlFailFast(ecx)
0x180009d00  mov     edx, 16Dh; void *
0x180009d05  mov     r9d, edi; char *
0x180009d08  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009d0f  mov     rcx, [rbp+18h]; this
0x180009d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d18  nop
0x180009d19  xor     edx, edx
0x180009d1b  lea     rcx, [rbp+var_28]
0x180009d1f  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009d24  mov     ebx, edi
0x180009d26  xor     edx, edx
0x180009d28  lea     rcx, [rbp+var_20]
0x180009d2c  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009d31  mov     eax, ebx
0x180009d33  jmp     short loc_180009CDD
```
