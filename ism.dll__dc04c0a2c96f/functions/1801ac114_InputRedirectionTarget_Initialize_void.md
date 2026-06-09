# InputRedirectionTarget::Initialize(void)

- ea: `0x1801ac114`
- end: `0x1801ac272`
- name: `?Initialize@InputRedirectionTarget@@IEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(InputRedirectionTarget *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801abebc`

## callees

- `0x180012b74`
- `0x180026be0`
- `0x18007dc50`
- `0x18008ead4`
- `0x1800f0990`
- `0x1801ac114`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x1801ac1c8`
- `CoreMessaging!CoreUICreate` at `0x1801ac1c8`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1801ac228`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x1801ac228`

## pseudocode

```c
__int64 __fastcall InputRedirectionTarget::Initialize(InputRedirectionTarget *this)
{
  __int128 v1; // xmm1
  __int64 v2; // rax
  _QWORD *v3; // r14
  __int128 v4; // xmm2
  __int64 v6; // xmm3_8
  int v7; // ebx
  __int64 v8; // rdx
  unsigned int v10; // eax
  unsigned int v11[4]; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v13; // [rsp+68h] [rbp-98h]
  __int128 v14; // [rsp+78h] [rbp-88h]
  __int128 v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+98h] [rbp-68h]
  __int128 v17; // [rsp+A0h] [rbp-60h]
  __int128 v18; // [rsp+B0h] [rbp-50h]
  __int128 v19; // [rsp+C0h] [rbp-40h]
  __int64 v20; // [rsp+D0h] [rbp-30h]
  __int128 v21; // [rsp+D8h] [rbp-28h]
  __int128 v22; // [rsp+E8h] [rbp-18h]
  __int128 v23; // [rsp+F8h] [rbp-8h]
  __int64 v24; // [rsp+108h] [rbp+8h]
  __int128 v25; // [rsp+110h] [rbp+10h]
  __int128 v26; // [rsp+120h] [rbp+20h]
  __int128 v27; // [rsp+130h] [rbp+30h]
  __int64 v28; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v1 = *(_OWORD *)((char *)this + 72);
  v2 = *((_QWORD *)this + 7);
  v3 = (_QWORD *)((char *)this + 32);
  v4 = *(_OWORD *)((char *)this + 88);
  v12 = 232;
  v6 = *((_QWORD *)this + 13);
  *(_QWORD *)&v11[2] = v2;
  *(_QWORD *)v11 = 3;
  v18 = v1;
  v17 = *(_OWORD *)v11;
  v25 = *(_OWORD *)v11;
  v21 = *(_OWORD *)v11;
  v13 = *(_OWORD *)v11;
  v19 = v4;
  v20 = v6;
  v26 = v1;
  v27 = v4;
  v28 = v6;
  v22 = v1;
  v23 = v4;
  v24 = v6;
  v14 = v1;
  v15 = v4;
  v16 = v6;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 32);
  v7 = CoreUICreate(v3);
  if ( v7 < 0 )
  {
    v8 = 56;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\inputredirection\\system"
                    "\\lib\\inputredirectiontarget.cpp",
      (const char *)(unsigned int)v7,
      3);
    return (unsigned int)v7;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)*v3 + 120LL))(
         *v3,
         (char *)this + 72,
         (char *)this + 40);
  if ( v7 < 0 )
  {
    v8 = 59;
    goto LABEL_3;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>::reset(
    (char *)this + 112,
    0);
  v10 = NtCreateCompositionInputSink(&v12, (char *)this + 112);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3D,
             (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\inputredirection\\"
                           "system\\lib\\inputredirectiontarget.cpp",
             (const char *)v10,
             3u);
  else
    return 0;
}

```

## disassembly

```asm
0x1801ac114  mov     [rsp-8+arg_8], rbx
0x1801ac119  mov     [rsp-8+arg_10], rsi
0x1801ac11e  push    rbp
0x1801ac11f  push    rdi
0x1801ac120  push    r14
0x1801ac122  lea     rbp, [rsp-60h]
0x1801ac127  sub     rsp, 160h
0x1801ac12e  mov     rax, cs:__security_cookie
0x1801ac135  xor     rax, rsp
0x1801ac138  mov     [rbp+70h+var_20], rax
0x1801ac13c  movups  xmm1, xmmword ptr [rcx+48h]
0x1801ac140  mov     rax, [rcx+38h]
0x1801ac144  lea     r14, [rcx+20h]
0x1801ac148  movups  xmm2, xmmword ptr [rcx+58h]
0x1801ac14c  mov     rdi, rcx
0x1801ac14f  mov     [rsp+170h+var_110], 0E8h
0x1801ac158  movsd   xmm3, qword ptr [rcx+68h]
0x1801ac15d  xorps   xmm0, xmm0
0x1801ac160  movups  xmmword ptr [rsp+170h+var_150], xmm0
0x1801ac165  mov     qword ptr [rsp+170h+var_150+8], rax
0x1801ac16a  mov     rcx, r14
0x1801ac16d  mov     [rsp+170h+var_150], 3; unsigned int
0x1801ac175  movups  xmm0, xmmword ptr [rsp+170h+var_150]
0x1801ac17a  movaps  [rbp+70h+var_C0], xmm1
0x1801ac17e  movaps  [rbp+70h+var_D0], xmm0
0x1801ac182  movaps  [rbp+70h+var_60], xmm0
0x1801ac186  movups  [rbp+70h+var_98], xmm0
0x1801ac18a  movups  [rsp+170h+var_108], xmm0
0x1801ac18f  movaps  [rbp+70h+var_B0], xmm2
0x1801ac193  movsd   [rbp+70h+var_A0], xmm3
0x1801ac198  movaps  [rbp+70h+var_50], xmm1
0x1801ac19c  movaps  [rbp+70h+var_40], xmm2
0x1801ac1a0  movsd   [rbp+70h+var_30], xmm3
0x1801ac1a5  movups  [rbp+70h+var_88], xmm1
0x1801ac1a9  movups  [rbp+70h+var_78], xmm2
0x1801ac1ad  movsd   [rbp+70h+var_68], xmm3
0x1801ac1b2  movups  [rsp+170h+var_F8], xmm1
0x1801ac1b7  movups  [rbp+70h+var_E8], xmm2
0x1801ac1bb  movsd   [rbp+70h+var_D8], xmm3
0x1801ac1c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ac1c5  mov     rcx, r14
0x1801ac1c8  call    cs:__imp_CoreUICreate
0x1801ac1ce  mov     ebx, eax
0x1801ac1d0  test    eax, eax
0x1801ac1d2  jns     short loc_1801AC1F0
0x1801ac1d4  mov     edx, 38h ; '8'; void *
0x1801ac1d9  mov     rcx, [rbp+78h]; this
0x1801ac1dd  lea     r8, aOnecoreuapWind_204; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801ac1e4  mov     r9d, ebx; char *
0x1801ac1e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ac1ec  mov     eax, ebx
0x1801ac1ee  jmp     short loc_1801AC24E
0x1801ac1f0  mov     rcx, [r14]
0x1801ac1f3  lea     r8, [rdi+28h]
0x1801ac1f7  lea     rdx, [rdi+48h]
0x1801ac1fb  mov     rax, [rcx]
0x1801ac1fe  mov     rax, [rax+78h]
0x1801ac202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ac207  mov     ebx, eax
0x1801ac209  test    eax, eax
0x1801ac20b  jns     short loc_1801AC214
0x1801ac20d  mov     edx, 3Bh ; ';'
0x1801ac212  jmp     short loc_1801AC1D9
0x1801ac214  xor     edx, edx
0x1801ac216  lea     rcx, [rdi+70h]
0x1801ac21a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>::reset(void *)
0x1801ac21f  lea     rdx, [rdi+70h]
0x1801ac223  lea     rcx, [rsp+170h+var_110]
0x1801ac228  call    cs:__imp_NtCreateCompositionInputSink
0x1801ac22e  test    eax, eax
0x1801ac230  jz      short loc_1801AC24C
0x1801ac232  mov     rcx, [rbp+78h]; this
0x1801ac236  lea     r8, aOnecoreuapWind_204; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801ac23d  mov     r9d, eax; char *
0x1801ac240  mov     edx, 3Dh ; '='; void *
0x1801ac245  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801ac24a  jmp     short loc_1801AC24E
0x1801ac24c  xor     eax, eax
0x1801ac24e  mov     rcx, [rbp+70h+var_20]
0x1801ac252  xor     rcx, rsp; StackCookie
0x1801ac255  call    __security_check_cookie
0x1801ac25a  lea     r11, [rsp+170h+var_10]
0x1801ac262  mov     rbx, [r11+28h]
0x1801ac266  mov     rsi, [r11+30h]
0x1801ac26a  mov     rsp, r11
0x1801ac26d  pop     r14
0x1801ac26f  pop     rdi
0x1801ac270  pop     rbp
0x1801ac271  retn
```
