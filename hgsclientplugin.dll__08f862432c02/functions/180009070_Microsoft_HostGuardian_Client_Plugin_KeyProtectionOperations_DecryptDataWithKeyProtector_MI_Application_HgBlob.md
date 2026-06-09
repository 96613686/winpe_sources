# Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector(_MI_Application &,HgBlob const &,HgBlob const &,HgBlob &)

- ea: `0x180009070`
- end: `0x1800092f4`
- name: `?DecryptDataWithKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@1AEAU7@@Z`
- size: `644`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this, struct _MI_Application *, const struct HgBlob *, const union _MI_Value *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007860`

## callees

- `0x180001520`
- `0x1800029c8`
- `0x1800068ec`
- `0x180009070`
- `0x1800096c4`
- `0x180009a84`
- `0x180009cfc`
- `0x180009f44`
- `0x18000a070`
- `0x18000a45c`
- `0x18000a550`
- `0x18000c010`

## string_xrefs

- `0x1800092c8`: `Failed to create a new session. %d.`
- `0x1800092af`: `servercommon\base\securehostingservice\common\service\plugin\keyprotectionoperations.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector(
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this,
        struct _MI_Application *a2,
        const struct HgBlob *a3,
        const union _MI_Value *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v9; // r8d
  __int64 v10; // rbx
  struct HgBlob *v11; // r8
  int v12; // eax
  enum _MI_Result v13; // edx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  _BYTE v19[40]; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int128 v25; // [rsp+90h] [rbp-70h]
  _QWORD v26[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v27; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v28; // [rsp+B1h] [rbp-4Fh]
  _BYTE v29[23]; // [rsp+C1h] [rbp-3Fh] BYREF
  _OWORD v30[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-8h]
  _OWORD v32[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v33; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v24 = 0;
  v25 = 0;
  if ( !miApplication.ft )
  {
    v8 = 4;
LABEL_15:
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
      (wchar_t *)L"Failed to create a new session. %d.",
      (const wchar_t *)v8);
    v14 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
            (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v8,
            v13);
    v15 = wil::verify_hresult<long>(v14);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xF7, v16, (const char *)v15, v17);
  }
  v17 = 0;
  v8 = ((__int64 (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD))miApplication.ft->NewSession)(
         &miApplication,
         0,
         0,
         0);
  if ( v8 )
    goto LABEL_15;
  v26[1] = &v24;
  memset(&v19[1], 0, 32);
  *(_QWORD *)v19 = a2->reserved2;
  *(_DWORD *)&v19[8] = a2->reserved1;
  v30[0] = *(_OWORD *)v19;
  v30[1] = *(_OWORD *)&v19[16];
  v31 = 0;
  memset(&v19[1], 0, 32);
  *(_QWORD *)v19 = *((_QWORD *)a3 + 1);
  *(_DWORD *)&v19[8] = *(_DWORD *)a3;
  v32[0] = *(_OWORD *)v19;
  v32[1] = *(_OWORD *)&v19[16];
  v33 = 0;
  *(_QWORD *)v19 = v30;
  *(_DWORD *)&v19[8] = 0;
  *(_DWORD *)&v19[16] = 17;
  *(_QWORD *)&v19[24] = L"BaseKeyProtector";
  *(_QWORD *)&v19[32] = v32;
  v20 = 0;
  v21 = 17;
  v22 = L"EncryptedData";
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(&v23, v7, v19, 2);
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(
    (unsigned int)v26,
    (unsigned int)&v24,
    v9,
    (unsigned int)L"DecryptDataWithKeyProtector",
    0,
    v23);
  v27 = 0;
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  *(_QWORD *)v19 = &v27;
  *(_DWORD *)&v19[8] = 0;
  *(_DWORD *)&v19[16] = 17;
  *(_QWORD *)&v19[24] = L"PlainTextData";
  v10 = v26[0];
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(v26[0], v19, 1);
  v12 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v27,
          a4,
          v11);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      279,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\keyprotectionoperations.cpp",
      (const char *)(unsigned int)v12,
      v18);
  if ( v10 && *(_QWORD *)v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v23 && *(_QWORD *)v23 )
    (*(void (**)(void))(*(_QWORD *)v23 + 16LL))();
  if ( *((_QWORD *)&v25 + 1) )
    (**((void (__fastcall ***)(__int64 *, _QWORD, _QWORD))&v25 + 1))(&v24, 0, 0);
}

```

## disassembly

```asm
0x180009070  mov     [rsp-8+arg_0], rbx
0x180009075  mov     [rsp-8+arg_8], rsi
0x18000907a  push    rbp
0x18000907b  push    rdi
0x18000907c  push    r14
0x18000907e  lea     rbp, [rsp-30h]
0x180009083  sub     rsp, 130h
0x18000908a  mov     rax, cs:__security_cookie
0x180009091  xor     rax, rsp
0x180009094  mov     [rbp+40h+var_18], rax
0x180009098  mov     r14, r9
0x18000909b  mov     rdi, r8
0x18000909e  mov     rsi, rdx
0x1800090a1  mov     [rbp+40h+var_B8], 0
0x1800090a9  xorps   xmm0, xmm0
0x1800090ac  movdqu  [rbp+40h+var_B0], xmm0
0x1800090b1  mov     rax, cs:?miApplication@@3U_MI_Application@@A.ft; _MI_Application miApplication ...
0x1800090b8  test    rax, rax
0x1800090bb  jz      loc_1800092C1
0x1800090c1  lea     rcx, [rbp+40h+var_B8]
0x1800090c5  mov     [rsp+140h+var_110], rcx
0x1800090ca  mov     [rsp+140h+var_118], 0
0x1800090d3  mov     qword ptr [rsp+140h+var_120], 0; int
0x1800090dc  xor     r9d, r9d
0x1800090df  xor     r8d, r8d
0x1800090e2  xor     edx, edx
0x1800090e4  lea     rcx, ?miApplication@@3U_MI_Application@@A; _MI_Application miApplication
0x1800090eb  mov     rax, [rax+8]
0x1800090ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f4  mov     ebx, eax
0x1800090f6  test    eax, eax
0x1800090f8  jnz     loc_1800092C6
0x1800090fe  lea     rax, [rbp+40h+var_B8]
0x180009102  mov     [rbp+40h+var_98], rax
0x180009106  xorps   xmm0, xmm0
0x180009109  xor     ecx, ecx
0x18000910b  movups  [rsp+140h+var_100+1], xmm0
0x180009110  movups  [rsp+140h+var_EF], xmm0
0x180009115  mov     rax, [rsi+8]
0x180009119  mov     qword ptr [rsp+140h+var_100], rax
0x18000911e  mov     eax, [rsi]
0x180009120  mov     dword ptr [rsp+140h+var_100+8], eax
0x180009124  movups  xmm0, [rsp+140h+var_100]
0x180009129  movups  [rbp+40h+var_68], xmm0
0x18000912d  movups  xmm1, xmmword ptr [rsp+50h]
0x180009132  movups  [rbp+40h+var_58], xmm1
0x180009136  mov     [rbp+40h+var_48], rcx
0x18000913a  xorps   xmm1, xmm1
0x18000913d  movups  [rsp+140h+var_100+1], xmm1
0x180009142  movups  [rsp+140h+var_EF], xmm1
0x180009147  mov     rax, [rdi+8]
0x18000914b  mov     qword ptr [rsp+140h+var_100], rax
0x180009150  mov     eax, [rdi]
0x180009152  mov     dword ptr [rsp+140h+var_100+8], eax
0x180009156  movups  xmm0, [rsp+140h+var_100]
0x18000915b  movups  [rbp+40h+var_40], xmm0
0x18000915f  movups  xmm1, xmmword ptr [rsp+50h]
0x180009164  movups  [rbp+40h+var_30], xmm1
0x180009168  mov     [rbp+40h+var_20], rcx
0x18000916c  lea     rax, [rbp+40h+var_68]
0x180009170  mov     qword ptr [rsp+140h+var_100], rax
0x180009175  mov     dword ptr [rsp+140h+var_100+8], ecx
0x180009179  lea     ebx, [rcx+11h]
0x18000917c  mov     [rsp+50h], ebx
0x180009180  mov     rax, cs:off_18000D0B0; "BaseKeyProtector"
0x180009187  mov     qword ptr [rsp+140h+var_EF+7], rax
0x18000918c  lea     rax, [rbp+40h+var_40]
0x180009190  mov     qword ptr [rsp+140h+var_EF+0Fh], rax
0x180009195  mov     [rsp+140h+var_D8], ecx
0x180009199  mov     [rsp+140h+var_D0], ebx
0x18000919d  mov     rax, cs:off_18000D098; "EncryptedData"
0x1800091a4  mov     [rsp+140h+var_C8], rax
0x1800091a9  lea     r9d, [rcx+2]
0x1800091ad  lea     r8, [rsp+140h+var_100]
0x1800091b2  lea     rcx, [rbp+40h+var_C0]
0x1800091b6  call    ?SetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Application@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(_MI_Application &,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x1800091bb  nop
0x1800091bc  mov     rax, [rbp+40h+var_C0]
0x1800091c0  mov     [rsp+140h+var_118], rax
0x1800091c5  lea     r9, aDecryptdatawit; "DecryptDataWithKeyProtector"
0x1800091cc  lea     rdx, [rbp+40h+var_B8]
0x1800091d0  lea     rcx, [rbp+40h+var_A0]
0x1800091d4  call    ?InvokeStaticWmiMethod@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Session@@PEB_W11PEBU_MI_Instance@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(_MI_Session &,wchar_t const *,wchar_t const *,wchar_t const *,_MI_Instance const *)
0x1800091d9  nop
0x1800091da  mov     [rbp+40h+var_90], 0
0x1800091de  xorps   xmm0, xmm0
0x1800091e1  xor     eax, eax
0x1800091e3  movups  [rbp+40h+var_8F], xmm0
0x1800091e7  movups  xmmword ptr [rbp+40h+var_7F], xmm0
0x1800091eb  mov     qword ptr [rbp+40h+var_7F+0Fh], rax
0x1800091ef  lea     rax, [rbp+40h+var_90]
0x1800091f3  mov     qword ptr [rsp+140h+var_100], rax
0x1800091f8  mov     dword ptr [rsp+140h+var_100+8], 0
0x180009200  mov     [rsp+50h], ebx
0x180009204  mov     rax, cs:off_18000D0A0; "PlainTextData"
0x18000920b  mov     qword ptr [rsp+140h+var_EF+7], rax
0x180009210  lea     r8d, [rbx-10h]
0x180009214  lea     rdx, [rsp+140h+var_100]
0x180009219  mov     rbx, [rbp+40h+var_A0]
0x18000921d  mov     rcx, rbx
0x180009220  call    ?GetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(_MI_Instance const *,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x180009225  mov     rdx, r14; union _MI_Value *
0x180009228  lea     rcx, [rbp+40h+var_90]; this
0x18000922c  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x180009231  mov     rcx, [rbp+48h]; this
0x180009235  test    eax, eax
0x180009237  js      short loc_1800092AC
0x180009239  test    rbx, rbx
0x18000923c  jz      short loc_180009253
0x18000923e  mov     rax, [rbx]
0x180009241  test    rax, rax
0x180009244  jz      short loc_180009253
0x180009246  mov     rcx, rbx
0x180009249  mov     rax, [rax+10h]
0x18000924d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009252  nop
0x180009253  mov     rcx, [rbp+40h+var_C0]
0x180009257  test    rcx, rcx
0x18000925a  jz      short loc_18000926E
0x18000925c  mov     rax, [rcx]
0x18000925f  test    rax, rax
0x180009262  jz      short loc_18000926E
0x180009264  mov     rax, [rax+10h]
0x180009268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926d  nop
0x18000926e  mov     rax, qword ptr [rbp+40h+var_B0+8]
0x180009272  test    rax, rax
0x180009275  jz      short loc_180009288
0x180009277  xor     r8d, r8d
0x18000927a  xor     edx, edx
0x18000927c  lea     rcx, [rbp+40h+var_B8]
0x180009280  mov     rax, [rax]
0x180009283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009288  mov     rcx, [rbp+40h+var_18]
0x18000928c  xor     rcx, rsp; StackCookie
0x18000928f  call    __security_check_cookie
0x180009294  lea     r11, [rsp+140h+var_10]
0x18000929c  mov     rbx, [r11+20h]
0x1800092a0  mov     rsi, [r11+28h]
0x1800092a4  mov     rsp, r11
0x1800092a7  pop     r14
0x1800092a9  pop     rdi
0x1800092aa  pop     rbp
0x1800092ab  retn
0x1800092ac  mov     r9d, eax; char *
0x1800092af  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x1800092b6  mov     edx, 117h; void *
0x1800092bb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800092c1  mov     ebx, 4
0x1800092c6  mov     edx, ebx; wchar_t *
0x1800092c8  lea     rcx, aFailedToCreate; "Failed to create a new session. %d."
0x1800092cf  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x1800092d4  mov     ecx, ebx; this
0x1800092d6  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x1800092db  mov     ecx, eax
0x1800092dd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800092e2  mov     r9d, eax; char *
0x1800092e5  mov     rcx, [rbp+48h]; this
0x1800092e9  mov     edx, 0F7h; void *
0x1800092ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
