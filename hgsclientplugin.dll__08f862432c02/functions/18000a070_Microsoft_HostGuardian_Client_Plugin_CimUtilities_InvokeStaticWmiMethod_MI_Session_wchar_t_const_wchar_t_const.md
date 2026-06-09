# Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(_MI_Session &,wchar_t const *,wchar_t const *,wchar_t const *,_MI_Instance const *)

- ea: `0x18000a070`
- end: `0x18000a37a`
- name: `?InvokeStaticWmiMethod@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Session@@PEB_W11PEBU_MI_Instance@@@Z`
- size: `778`
- prototype: `struct _MI_Operation **__fastcall(struct _MI_Operation **, __int64, __int64, Microsoft::HostGuardian::Client::Plugin::CimUtilities **, int, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`

## callees

- `0x180001520`
- `0x1800068ec`
- `0x180009a84`
- `0x180009e50`
- `0x180009f44`
- `0x18000a070`
- `0x18000a3a0`
- `0x18000c010`

## string_xrefs

- `0x18000a30b`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a320`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a338`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a350`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a368`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

## pseudocode

```c
struct _MI_Operation **__fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(
        struct _MI_Operation **a1,
        __int64 a2,
        __int64 a3,
        Microsoft::HostGuardian::Client::Plugin::CimUtilities **a4,
        int a5,
        __int64 a6)
{
  struct _MI_Operation **v6; // r14
  __int64 v7; // rax
  __int64 *v8; // rcx
  const struct _MI_Instance *v9; // rdx
  unsigned int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // esi
  __int64 *v13; // r8
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  char v17; // al
  unsigned int v18; // eax
  char v19; // dl
  enum _MI_Result v20; // edx
  unsigned int v21; // eax
  struct _MI_Operation *v22; // rdx
  __int64 v24; // [rsp+0h] [rbp-108h] BYREF
  unsigned int *v25; // [rsp+20h] [rbp-E8h]
  Microsoft::HostGuardian::Client::Plugin::CimUtilities **v26; // [rsp+28h] [rbp-E0h]
  __int64 v27; // [rsp+30h] [rbp-D8h]
  __int64 v28; // [rsp+38h] [rbp-D0h]
  __int64 v29; // [rsp+40h] [rbp-C8h]
  __int64 *v30; // [rsp+48h] [rbp-C0h]
  char v31[4]; // [rsp+60h] [rbp-A8h] BYREF
  int v32; // [rsp+64h] [rbp-A4h] BYREF
  int v33; // [rsp+68h] [rbp-A0h]
  wchar_t v34[4]; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v35; // [rsp+78h] [rbp-90h] BYREF
  Microsoft::HostGuardian::Client::Plugin::CimUtilities *v36; // [rsp+80h] [rbp-88h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, wchar_t *); // [rsp+88h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-78h] BYREF
  __int128 v39; // [rsp+98h] [rbp-70h]
  struct _MI_Operation **v40; // [rsp+B0h] [rbp-58h]
  __int64 *v41; // [rsp+B8h] [rbp-50h]
  unsigned __int64 v42[5]; // [rsp+C0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v6 = a1;
  v40 = a1;
  v32 = 0;
  v38 = 0;
  v39 = 0;
  if ( a2 )
  {
    v7 = *(_QWORD *)(a2 + 16);
    if ( v7 )
    {
      v30 = &v38;
      v29 = 0;
      v28 = a6;
      v27 = 0;
      v26 = a4;
      v25 = (unsigned int *)L"MSFT_HgsKeyProtectorOperations";
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, const wchar_t *))(v7 + 48))(
        a2,
        0,
        0,
        L"Root\\Microsoft\\Windows\\Hgs");
    }
  }
  v41 = &v38;
  v31[0] = 0;
  v8 = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  if ( *((_QWORD *)&v39 + 1) )
  {
    v26 = &v36;
    v25 = (unsigned int *)&v35;
    v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, wchar_t *), char *, int *))(*((_QWORD *)&v39 + 1) + 24LL))(
            &v38,
            &v37,
            v31,
            &v32);
    v33 = v10;
    v11 = v32;
    v12 = 4;
    if ( !v10 && !v32 )
      goto LABEL_21;
    v8 = v35;
  }
  else
  {
    v12 = 4;
    v11 = 4;
    v32 = 4;
    v10 = 4;
    v33 = 4;
  }
  v13 = &qword_18000DE68;
  if ( v8 )
    v13 = v8;
  if ( v10 )
    v11 = v10;
  Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
    (wchar_t *)L"Failed to get the output instance. Error code:%u. Message:%s",
    (const wchar_t *)v11,
    v13);
  v14 = 0;
  *(_DWORD *)v34 = 0;
  if ( !v36 )
    goto LABEL_17;
  try
  {
    Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetMessageIdFromCimError(v36, v9, (__int64)v42, v34);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, &v24, v15, v16);
    v12 = 4;
    v10 = v33;
    v6 = v40;
  }
  v14 = (const char *)*(unsigned int *)v34;
  if ( *(int *)v34 < 0 )
  {
    LOBYTE(v9) = 1;
    v17 = 1;
  }
  else
  {
LABEL_17:
    v17 = 0;
    LOBYTE(v9) = 1;
  }
  if ( v17 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      65,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      v14,
      (int)v25);
  v11 = v32;
  if ( !v10 )
  {
    if ( v32 )
    {
LABEL_22:
      v10 = v11;
      goto LABEL_23;
    }
LABEL_21:
    LOBYTE(v9) = 0;
    goto LABEL_22;
  }
LABEL_23:
  v18 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v10,
          (enum _MI_Result)v9);
  if ( v19 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      69,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)v18,
      (int)v25);
  if ( !v37 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      70,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)0x80070490LL,
      (int)v25);
  v20 = MI_RESULT_OK;
  *(_QWORD *)v34 = 0;
  if ( *v37 )
  {
    v12 = (**v37)(v37, v34);
    v20 = *(_DWORD *)v34;
  }
  v21 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v12,
          v20);
  if ( v12 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      81,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)v21,
      (int)v25);
  if ( !v22 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      82,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)0x80004003LL,
      (int)v25);
  *v6 = v22;
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(
    (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v38,
    v22);
  return v6;
}

```

## disassembly

```asm
0x18000a070  mov     r11, rsp
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r14
0x18000a077  sub     rsp, 0F0h
0x18000a07e  mov     rax, cs:__security_cookie
0x18000a085  xor     rax, rsp
0x18000a088  mov     [rsp+108h+var_20], rax
0x18000a090  mov     r10, rdx
0x18000a093  mov     r14, rcx
0x18000a096  mov     [rsp+108h+var_58], rcx
0x18000a09e  mov     rcx, [rsp+108h+arg_28]
0x18000a0a6  mov     [rsp+108h+var_A4], 0
0x18000a0ae  mov     qword ptr [r11-78h], 0
0x18000a0b6  xorps   xmm0, xmm0
0x18000a0b9  movdqu  xmmword ptr [r11-70h], xmm0
0x18000a0bf  test    rdx, rdx
0x18000a0c2  jz      short loc_18000A116
0x18000a0c4  mov     rax, [rdx+10h]
0x18000a0c8  test    rax, rax
0x18000a0cb  jz      short loc_18000A116
0x18000a0cd  lea     rdx, [r11-78h]
0x18000a0d1  mov     [rsp+108h+var_C0], rdx
0x18000a0d6  mov     [rsp+108h+var_C8], 0
0x18000a0df  mov     [rsp+108h+var_D0], rcx
0x18000a0e4  mov     [rsp+108h+var_D8], 0
0x18000a0ed  mov     [rsp+108h+var_E0], r9
0x18000a0f2  lea     rcx, aMsftHgskeyprot; "MSFT_HgsKeyProtectorOperations"
0x18000a0f9  mov     [rsp+108h+var_E8], rcx; int
0x18000a0fe  lea     r9, aRootMicrosoftW; "Root\\Microsoft\\Windows\\Hgs"
0x18000a105  xor     r8d, r8d
0x18000a108  xor     edx, edx
0x18000a10a  mov     rcx, r10
0x18000a10d  mov     rax, [rax+30h]
0x18000a111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a116  lea     rax, [rsp+108h+var_78]
0x18000a11e  mov     [rsp+108h+var_50], rax
0x18000a126  mov     [rsp+108h+var_A8], 0
0x18000a12b  xor     ecx, ecx
0x18000a12d  mov     [rsp+108h+var_90], rcx
0x18000a132  mov     [rsp+108h+var_80], rcx
0x18000a13a  mov     [rsp+108h+var_88], rcx
0x18000a142  mov     rax, [rsp+108h+var_68]
0x18000a14a  test    rax, rax
0x18000a14d  jz      short loc_18000A1AB
0x18000a14f  lea     rcx, [rsp+108h+var_88]
0x18000a157  mov     [rsp+108h+var_E0], rcx
0x18000a15c  lea     rcx, [rsp+108h+var_90]
0x18000a161  mov     [rsp+108h+var_E8], rcx
0x18000a166  lea     r9, [rsp+108h+var_A4]
0x18000a16b  lea     r8, [rsp+108h+var_A8]
0x18000a170  lea     rdx, [rsp+108h+var_80]
0x18000a178  lea     rcx, [rsp+108h+var_78]
0x18000a180  mov     rax, [rax+18h]
0x18000a184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a189  mov     edi, eax
0x18000a18b  mov     [rsp+108h+var_A0], eax
0x18000a18f  test    eax, eax
0x18000a191  mov     eax, [rsp+108h+var_A4]
0x18000a195  mov     esi, 4
0x18000a19a  jnz     short loc_18000A1A4
0x18000a19c  test    eax, eax
0x18000a19e  jz      loc_18000A248
0x18000a1a4  mov     rcx, [rsp+108h+var_90]
0x18000a1a9  jmp     short loc_18000A1BC
0x18000a1ab  mov     esi, 4
0x18000a1b0  mov     eax, esi
0x18000a1b2  mov     [rsp+108h+var_A4], eax
0x18000a1b6  mov     edi, esi
0x18000a1b8  mov     [rsp+108h+var_A0], esi
0x18000a1bc  lea     r8, qword_18000DE68
0x18000a1c3  test    rcx, rcx
0x18000a1c6  cmovnz  r8, rcx
0x18000a1ca  test    edi, edi
0x18000a1cc  cmovnz  eax, edi
0x18000a1cf  mov     edx, eax; wchar_t *
0x18000a1d1  lea     rcx, aFailedToGetThe; "Failed to get the output instance. Erro"...
0x18000a1d8  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x18000a1dd  xor     r9d, r9d; char *
0x18000a1e0  mov     dword ptr [rsp+108h+var_98], r9d
0x18000a1e5  mov     rcx, [rsp+108h+var_88]; this
0x18000a1ed  test    rcx, rcx
0x18000a1f0  jz      short loc_18000A228
0x18000a1f2  lea     r9, [rsp+108h+var_98]; wchar_t *
0x18000a1f7  lea     r8, [rsp+108h+var_48]; unsigned __int64
0x18000a1ff  call    ?GetMessageIdFromCimError@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@_KPEA_WAEAI@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetMessageIdFromCimError(_MI_Instance const *,unsigned __int64,wchar_t *,uint &)
0x18000a204  nop
0x18000a205  jmp     short loc_18000A218
0x18000a207  mov     esi, 4
0x18000a20c  mov     edi, [rsp+108h+var_A0]
0x18000a210  mov     r14, [rsp+108h+var_58]
0x18000a218  mov     r9d, dword ptr [rsp+108h+var_98]
0x18000a21d  test    r9d, r9d
0x18000a220  jns     short loc_18000A228
0x18000a222  mov     dl, 1
0x18000a224  mov     al, dl
0x18000a226  jmp     short loc_18000A22C
0x18000a228  xor     al, al
0x18000a22a  mov     dl, 1; enum _MI_Result
0x18000a22c  mov     rcx, [rsp+108h]; this
0x18000a234  test    al, al
0x18000a236  jnz     loc_18000A30B
0x18000a23c  mov     eax, [rsp+108h+var_A4]
0x18000a240  test    edi, edi
0x18000a242  jnz     short loc_18000A252
0x18000a244  test    eax, eax
0x18000a246  jnz     short loc_18000A24C
0x18000a248  xor     dl, dl
0x18000a24a  jmp     short loc_18000A250
0x18000a24c  test    edi, edi
0x18000a24e  jnz     short loc_18000A252
0x18000a250  mov     edi, eax
0x18000a252  mov     ecx, edi; this
0x18000a254  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x18000a259  mov     rcx, [rsp+108h]; this
0x18000a261  test    dl, dl
0x18000a263  jnz     loc_18000A31D
0x18000a269  mov     rcx, [rsp+108h+var_80]
0x18000a271  test    rcx, rcx
0x18000a274  setz    al
0x18000a277  mov     r10, [rsp+108h]
0x18000a27f  test    al, al
0x18000a281  jnz     loc_18000A332
0x18000a287  xor     edx, edx
0x18000a289  mov     qword ptr [rsp+108h+var_98], rdx
0x18000a28e  test    rcx, rcx
0x18000a291  jz      short loc_18000A2AF
0x18000a293  mov     rax, [rcx]
0x18000a296  test    rax, rax
0x18000a299  jz      short loc_18000A2AF
0x18000a29b  lea     rdx, [rsp+108h+var_98]
0x18000a2a0  mov     rax, [rax]
0x18000a2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a8  mov     esi, eax
0x18000a2aa  mov     rdx, qword ptr [rsp+108h+var_98]; enum _MI_Result
0x18000a2af  mov     ecx, esi; this
0x18000a2b1  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x18000a2b6  mov     rcx, [rsp+108h]; this
0x18000a2be  test    esi, esi
0x18000a2c0  jnz     loc_18000A34D
0x18000a2c6  test    rdx, rdx
0x18000a2c9  setz    al
0x18000a2cc  mov     rcx, [rsp+108h]; this
0x18000a2d4  test    al, al
0x18000a2d6  jnz     loc_18000A362
0x18000a2dc  mov     [r14], rdx
0x18000a2df  lea     rcx, [rsp+108h+var_78]; this
0x18000a2e7  call    ?MI_Operation_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW4_MI_Result@@PEAU_MI_Operation@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *)
0x18000a2ec  mov     rax, r14
0x18000a2ef  mov     rcx, [rsp+108h+var_20]
0x18000a2f7  xor     rcx, rsp; StackCookie
0x18000a2fa  call    __security_check_cookie
0x18000a2ff  add     rsp, 0F0h
0x18000a306  pop     r14
0x18000a308  pop     rdi
0x18000a309  pop     rsi
0x18000a30a  retn
0x18000a30b  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a312  mov     edx, 41h ; 'A'; void *
0x18000a317  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a31d  mov     r9d, eax; char *
0x18000a320  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a327  mov     edx, 45h ; 'E'; void *
0x18000a32c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a332  mov     r9d, 80070490h; char *
0x18000a338  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a33f  mov     edx, 46h ; 'F'; void *
0x18000a344  mov     rcx, r10; this
0x18000a347  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a34d  mov     r9d, eax; char *
0x18000a350  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a357  mov     edx, 51h ; 'Q'; void *
0x18000a35c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a362  mov     r9d, 80004003h; char *
0x18000a368  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a36f  mov     edx, 52h ; 'R'; void *
0x18000a374  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
