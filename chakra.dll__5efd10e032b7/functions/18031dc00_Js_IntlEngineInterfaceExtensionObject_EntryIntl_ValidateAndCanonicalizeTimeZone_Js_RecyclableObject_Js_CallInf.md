# Js::IntlEngineInterfaceExtensionObject::EntryIntl_ValidateAndCanonicalizeTimeZone(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x18031dc00`
- end: `0x18031dea3`
- name: `?EntryIntl_ValidateAndCanonicalizeTimeZone@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800a2a0c`
- `0x1800a3d24`
- `0x18017f5d4`
- `0x180189ef4`
- `0x18031dc00`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18031ddb0`
- `msvcrt!_wcsicmp` at `0x18031ddb0`
- `icu!uenum_count` at `0x18031dcec`
- `icu!uenum_count` at `0x18031dcec`
- `icu!ucal_openTimeZoneIDEnumeration` at `0x18031dcd0`
- `icu!ucal_openTimeZoneIDEnumeration` at `0x18031dcd0`
- `icu!uenum_unext` at `0x18031dd5a`
- `icu!uenum_unext` at `0x18031dd5a`
- `icu!ucal_getCanonicalTimeZoneID` at `0x18031dde9`
- `icu!ucal_getCanonicalTimeZoneID` at `0x18031dde9`
- `icu!uenum_close` at `0x18031de33`
- `icu!uenum_close` at `0x18031de7e`
- `icu!uenum_close` at `0x18031de33`
- `icu!uenum_close` at `0x18031de7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_ValidateAndCanonicalizeTimeZone(
        __int64 a1,
        int a2,
        __int64 a3,
        void *a4)
{
  ThreadContext **v5; // r8
  __int64 v6; // r8
  __int64 v7; // r13
  __int64 v8; // rbx
  int v9; // r15d
  unsigned int v10; // esi
  int v11; // r14d
  __int64 v12; // rdi
  const wchar_t *v13; // r12
  const wchar_t *v14; // rax
  __int64 v15; // rdi
  int v17; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+3Ch] [rbp-CCh] BYREF
  struct Js::JavascriptString *v19; // [rsp+40h] [rbp-C8h]
  __int64 v20; // [rsp+48h] [rbp-C0h]
  __int64 v21; // [rsp+50h] [rbp-B8h]
  _WORD v22[104]; // [rsp+58h] [rbp-B0h] BYREF

  v20 = -2;
  v5 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v5[110], 0xC00u, (struct Js::ScriptContext *)v5, 0);
  v19 = 0;
  if ( (a2 & 0xFFFFFF) != 2 || !Js::JavascriptString::Is(a4) )
  {
LABEL_32:
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x18031DEA2LL);
  }
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v19 = Js::JavascriptString::FromVar(*(void **)(v6 + 8));
  v17 = 0;
  v8 = ucal_openTimeZoneIDEnumeration(0, 0, 0, &v17);
  v21 = v8;
  v9 = uenum_count(v8, &v17);
  if ( v17 == 7 )
    Js::Throw::OutOfMemory();
  if ( v17 > 0 || v17 == -124 || v9 <= 0 )
  {
    Js::Throw::FatalInternalError(-2147467259);
    goto LABEL_32;
  }
  v10 = 0;
  memset_0(v22, 0, 0xC8u);
  v11 = 0;
  v12 = -1;
  while ( v11 < v9 )
  {
    v18 = -1;
    v13 = (const wchar_t *)uenum_unext(v8, &v18, &v17);
    if ( v17 == 7 )
      goto LABEL_14;
    if ( v17 > 0 || v17 == -124 )
      goto LABEL_16;
    if ( !v18 )
      goto LABEL_14;
    if ( v18 <= 0 )
      goto LABEL_16;
    v14 = (const wchar_t *)(*(__int64 (__fastcall **)(struct Js::JavascriptString *))(*(_QWORD *)v19 + 752LL))(v19);
    if ( !_wcsicmp(v13, v14) )
    {
      ucal_getCanonicalTimeZoneID(v13, (unsigned int)v18, v22, 100, 0, &v17);
      if ( v17 == 7 )
LABEL_14:
        Js::Throw::OutOfMemory();
      if ( v17 > 0 || v17 == -124 )
      {
LABEL_16:
        Js::Throw::FatalInternalError(-2147467259);
        __debugbreak();
      }
      do
        ++v12;
      while ( v22[v12] );
      v10 = v12;
      break;
    }
    ++v11;
  }
  if ( v10 )
  {
    v15 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(v22, v10, v7);
    if ( v8 )
      uenum_close(v8);
  }
  else
  {
    v15 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 1000LL);
    if ( v8 )
      uenum_close(v8);
  }
  return v15;
}

```

## disassembly

```asm
0x18031dc00  mov     rax, rsp
0x18031dc03  mov     [rax+10h], rdx
0x18031dc07  mov     [rax+8], rcx
0x18031dc0b  mov     [rax+18h], r8
0x18031dc0f  mov     [rax+20h], r9
0x18031dc13  push    rbp
0x18031dc14  push    rbx
0x18031dc15  push    rsi
0x18031dc16  push    rdi
0x18031dc17  push    r12
0x18031dc19  push    r13
0x18031dc1b  push    r14
0x18031dc1d  push    r15
0x18031dc1f  lea     rbp, [rax-78h]
0x18031dc23  sub     rsp, 138h
0x18031dc2a  mov     [rsp+170h+var_130], 0FFFFFFFFFFFFFFFEh
0x18031dc33  mov     rax, cs:__security_cookie
0x18031dc3a  xor     rax, rsp
0x18031dc3d  mov     [rbp+70h+var_50], rax
0x18031dc41  mov     rbx, [rbp+70h+arg_0]
0x18031dc48  mov     rax, [rbx+8]
0x18031dc4c  mov     rcx, [rax+8]
0x18031dc50  mov     rcx, [rcx+440h]
0x18031dc57  xor     r9d, r9d; void *
0x18031dc5a  mov     r8, rcx; struct Js::ScriptContext *
0x18031dc5d  mov     edx, 0C00h; unsigned __int64
0x18031dc62  mov     rcx, [rcx+370h]; this
0x18031dc69  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x18031dc6e  xor     r12d, r12d
0x18031dc71  mov     [rsp+170h+var_138], r12
0x18031dc76  lea     r8, [rbp+70h+arg_10]
0x18031dc7d  mov     eax, [rbp+70h+arg_8]
0x18031dc83  and     eax, 0FFFFFFh
0x18031dc88  cmp     eax, 2
0x18031dc8b  jnz     loc_18031DE98
0x18031dc91  mov     rcx, [r8+8]; void *
0x18031dc95  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x18031dc9a  test    al, al
0x18031dc9c  jz      loc_18031DE98
0x18031dca2  mov     rax, [rbx+8]
0x18031dca6  mov     rdx, [rax+8]
0x18031dcaa  mov     r13, [rdx+440h]
0x18031dcb1  mov     rcx, [r8+8]; void *
0x18031dcb5  call    ?FromVar@JavascriptString@Js@@SAPEAV12@PEAX@Z; Js::JavascriptString::FromVar(void *)
0x18031dcba  mov     [rsp+170h+var_138], rax
0x18031dcbf  mov     dword ptr [rsp+170h+var_140], r12d
0x18031dcc4  lea     r9, [rsp+170h+var_140]
0x18031dcc9  xor     r8d, r8d
0x18031dccc  xor     edx, edx
0x18031dcce  xor     ecx, ecx
0x18031dcd0  call    cs:__imp_ucal_openTimeZoneIDEnumeration
0x18031dcd7  nop     dword ptr [rax+rax+00h]
0x18031dcdc  mov     rbx, rax
0x18031dcdf  mov     [rsp+170h+var_128], rax
0x18031dce4  lea     rdx, [rsp+170h+var_140]
0x18031dce9  mov     rcx, rax
0x18031dcec  call    cs:__imp_uenum_count
0x18031dcf3  nop     dword ptr [rax+rax+00h]
0x18031dcf8  mov     r15d, eax
0x18031dcfb  mov     ecx, dword ptr [rsp+170h+var_140]
0x18031dcff  cmp     ecx, 7
0x18031dd02  jnz     short loc_18031DD0A
0x18031dd04  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18031dd0a  test    ecx, ecx
0x18031dd0c  jg      loc_18031DE8D
0x18031dd12  cmp     ecx, 0FFFFFF84h
0x18031dd15  jz      loc_18031DE8D
0x18031dd1b  test    r15d, r15d
0x18031dd1e  jle     loc_18031DE8D
0x18031dd24  mov     esi, r12d
0x18031dd27  xor     edx, edx; Val
0x18031dd29  mov     r8d, 0C8h; Size
0x18031dd2f  lea     rcx, [rsp+170h+var_120]; void *
0x18031dd34  call    memset_0
0x18031dd39  mov     r14d, r12d
0x18031dd3c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18031dd40  cmp     r14d, r15d
0x18031dd43  jge     loc_18031DE1C
0x18031dd49  mov     dword ptr [rsp+170h+var_140+4], edi
0x18031dd4d  lea     r8, [rsp+170h+var_140]
0x18031dd52  lea     rdx, [rsp+170h+var_140+4]
0x18031dd57  mov     rcx, rbx
0x18031dd5a  call    cs:__imp_uenum_unext
0x18031dd61  nop     dword ptr [rax+rax+00h]
0x18031dd66  mov     r12, rax
0x18031dd69  mov     ecx, dword ptr [rsp+170h+var_140]
0x18031dd6d  cmp     ecx, 7
0x18031dd70  jz      short loc_18031DD83
0x18031dd72  test    ecx, ecx
0x18031dd74  jg      short loc_18031DD8B
0x18031dd76  cmp     ecx, 0FFFFFF84h
0x18031dd79  jz      short loc_18031DD8B
0x18031dd7b  mov     ecx, dword ptr [rsp+170h+var_140+4]
0x18031dd7f  test    ecx, ecx
0x18031dd81  jnz     short loc_18031DD89
0x18031dd83  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18031dd89  jg      short loc_18031DD96
0x18031dd8b  mov     ecx, 80004005h; int
0x18031dd90  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18031dd95  int     3; Trap to Debugger
0x18031dd96  mov     rcx, [rsp+170h+var_138]
0x18031dd9b  mov     rax, [rcx]
0x18031dd9e  mov     rax, [rax+2F0h]
0x18031dda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031ddaa  mov     rdx, rax; String2
0x18031ddad  mov     rcx, r12; String1
0x18031ddb0  call    cs:__imp__wcsicmp
0x18031ddb7  nop     dword ptr [rax+rax+00h]
0x18031ddbc  test    eax, eax
0x18031ddbe  jz      short loc_18031DDC8
0x18031ddc0  inc     r14d
0x18031ddc3  jmp     loc_18031DD40
0x18031ddc8  lea     rax, [rsp+170h+var_140]
0x18031ddcd  mov     qword ptr [rsp+170h+var_148], rax
0x18031ddd2  mov     [rsp+170h+var_150], rsi
0x18031ddd7  mov     r9d, 64h ; 'd'
0x18031dddd  lea     r8, [rsp+170h+var_120]
0x18031dde2  mov     edx, dword ptr [rsp+170h+var_140+4]
0x18031dde6  mov     rcx, r12
0x18031dde9  call    cs:__imp_ucal_getCanonicalTimeZoneID
0x18031ddf0  nop     dword ptr [rax+rax+00h]
0x18031ddf5  mov     eax, dword ptr [rsp+170h+var_140]
0x18031ddf9  cmp     eax, 7
0x18031ddfc  jz      short loc_18031DD83
0x18031ddfe  xor     r12d, r12d
0x18031de01  test    eax, eax
0x18031de03  jg      short loc_18031DD8B
0x18031de05  cmp     eax, 0FFFFFF84h
0x18031de08  jz      short loc_18031DD8B
0x18031de0a  lea     rax, [rsp+170h+var_120]
0x18031de0f  inc     rdi
0x18031de12  cmp     [rax+rdi*2], r12w
0x18031de17  jnz     short loc_18031DE0F
0x18031de19  mov     rsi, rdi
0x18031de1c  test    esi, esi
0x18031de1e  jnz     short loc_18031DE64
0x18031de20  mov     rax, [r13+8]
0x18031de24  mov     rdi, [rax+3E8h]
0x18031de2b  test    rbx, rbx
0x18031de2e  jz      short loc_18031DE40
0x18031de30  mov     rcx, rbx
0x18031de33  call    cs:__imp_uenum_close
0x18031de3a  nop     dword ptr [rax+rax+00h]
0x18031de3f  nop
0x18031de40  mov     rax, rdi
0x18031de43  mov     rcx, [rbp+70h+var_50]
0x18031de47  xor     rcx, rsp; StackCookie
0x18031de4a  call    __security_check_cookie
0x18031de4f  add     rsp, 138h
0x18031de56  pop     r15
0x18031de58  pop     r14
0x18031de5a  pop     r13
0x18031de5c  pop     r12
0x18031de5e  pop     rdi
0x18031de5f  pop     rsi
0x18031de60  pop     rbx
0x18031de61  pop     rbp
0x18031de62  retn
0x18031de64  mov     r8, r13
0x18031de67  mov     edx, esi
0x18031de69  lea     rcx, [rsp+170h+var_120]
0x18031de6e  call    ??$NewWithBufferT@VLiteralString@Js@@$00@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(ushort const *,uint,Js::ScriptContext *)
0x18031de73  mov     rdi, rax
0x18031de76  test    rbx, rbx
0x18031de79  jz      short loc_18031DE8B
0x18031de7b  mov     rcx, rbx
0x18031de7e  call    cs:__imp_uenum_close
0x18031de85  nop     dword ptr [rax+rax+00h]
0x18031de8a  nop
0x18031de8b  jmp     short loc_18031DE40
0x18031de8d  mov     ecx, 80004005h; int
0x18031de92  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18031de97  nop
0x18031de98  mov     ecx, 80004005h; int
0x18031de9d  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
