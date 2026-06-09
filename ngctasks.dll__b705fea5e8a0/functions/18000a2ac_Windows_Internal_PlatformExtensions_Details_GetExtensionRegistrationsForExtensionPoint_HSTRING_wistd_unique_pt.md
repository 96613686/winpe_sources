# Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)

- ea: `0x18000a2ac`
- end: `0x18000a3b1`
- name: `?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180009b9c`

## callees

- `0x180006354`
- `0x180009340`
- `0x18000a2ac`
- `0x18000b06c`
- `0x18000cc34`
- `0x18000ef6c`

## string_xrefs

- `0x18000a328`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000a354`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(
        HSTRING a1,
        __int64 a2)
{
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *v4; // rax
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *v5; // rbx
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    a2,
    0);
  v4 = (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *)operator new(
                                                                                                    0x10u,
                                                                                                    (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection::`vftable';
    *(_QWORD *)v4 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable';
    *((_QWORD *)v4 + 1) = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    v7 = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(v5, a1);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v7,
        (int)v5);
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(
        (HKEY *)v5,
        1);
      return v8;
    }
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      a2,
      v5);
    return 0;
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      0);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a2ac  mov     [rsp+arg_0], rbx
0x18000a2b1  mov     [rsp+arg_8], rsi
0x18000a2b6  push    rdi
0x18000a2b7  sub     rsp, 30h
0x18000a2bb  mov     rsi, rdx
0x18000a2be  mov     rdi, rcx
0x18000a2c1  xor     edx, edx
0x18000a2c3  mov     rcx, rsi
0x18000a2c6  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18000a2cb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a2d2  mov     ecx, 10h; unsigned __int64
0x18000a2d7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a2dc  mov     rbx, rax
0x18000a2df  mov     [rsp+38h+arg_10], rax
0x18000a2e4  test    rax, rax
0x18000a2e7  jz      short loc_18000A30F
0x18000a2e9  lea     rax, ??_7ExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection::`vftable'
0x18000a2f0  mov     [rbx], rax
0x18000a2f3  lea     rax, ??_7ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`vftable'
0x18000a2fa  mov     [rbx], rax
0x18000a2fd  lea     rax, [rbx+8]
0x18000a301  mov     [rsp+38h+arg_18], rax
0x18000a306  mov     qword ptr [rax], 0
0x18000a30d  jmp     short loc_18000A311
0x18000a30f  xor     ebx, ebx
0x18000a311  mov     qword ptr [rsp+38h+var_18], rbx; int
0x18000a316  test    rbx, rbx
0x18000a319  jnz     short loc_18000A33B
0x18000a31b  mov     rcx, [rsp+38h]; this
0x18000a320  mov     ebx, 8007000Eh
0x18000a325  mov     r9d, ebx; char *
0x18000a328  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000a32f  mov     edx, 155h; void *
0x18000a334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a339  jmp     short loc_18000A396
0x18000a33b  mov     rdx, rdi; HSTRING
0x18000a33e  mov     rcx, rbx; this
0x18000a341  call    ?Initialize@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::Initialize(HSTRING__ *)
0x18000a346  mov     edi, eax
0x18000a348  test    eax, eax
0x18000a34a  jns     short loc_18000A380
0x18000a34c  mov     rcx, [rsp+38h]; this
0x18000a351  mov     r9d, eax; char *
0x18000a354  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000a35b  mov     edx, 156h; void *
0x18000a360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a365  nop
0x18000a366  mov     qword ptr [rsp+38h+var_18], 0
0x18000a36f  mov     edx, 1; unsigned int
0x18000a374  mov     rcx, rbx; this
0x18000a377  call    ??_GExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::`scalar deleting destructor'(uint)
0x18000a37c  mov     eax, edi
0x18000a37e  jmp     short loc_18000A3A1
0x18000a380  mov     qword ptr [rsp+38h+var_18], 0
0x18000a389  mov     rdx, rbx
0x18000a38c  mov     rcx, rsi
0x18000a38f  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x18000a394  xor     ebx, ebx
0x18000a396  mov     qword ptr [rsp+38h+var_18], 0
0x18000a39f  mov     eax, ebx
0x18000a3a1  mov     rbx, [rsp+38h+arg_0]
0x18000a3a6  mov     rsi, [rsp+38h+arg_8]
0x18000a3ab  add     rsp, 30h
0x18000a3af  pop     rdi
0x18000a3b0  retn
```
