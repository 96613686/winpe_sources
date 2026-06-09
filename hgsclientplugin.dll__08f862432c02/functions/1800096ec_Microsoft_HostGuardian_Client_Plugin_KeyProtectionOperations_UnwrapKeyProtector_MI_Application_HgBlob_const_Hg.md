# Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::UnwrapKeyProtector(_MI_Application &,HgBlob const &,HgBlob &,HgBlob &,HgBlob &,HgBlob &)

- ea: `0x1800096ec`
- end: `0x180009a7e`
- name: `?UnwrapKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@AEAU7@222@Z`
- size: `914`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this, struct _MI_Application *, union _MI_Value *, struct HgBlob *, union _MI_Value *, union _MI_Value *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008320`

## callees

- `0x180001520`
- `0x1800029c8`
- `0x1800068ec`
- `0x180009670`
- `0x1800096c4`
- `0x1800096ec`
- `0x180009a84`
- `0x180009cfc`
- `0x180009f44`
- `0x18000a070`
- `0x18000a45c`
- `0x18000a550`
- `0x18000c010`

## string_xrefs

- `0x180009a3a`: `Failed to create a new session. %d.`
- `0x180009a6c`: `servercommon\base\securehostingservice\common\service\plugin\keyprotectionoperations.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::UnwrapKeyProtector(
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this,
        struct _MI_Application *a2,
        union _MI_Value *a3,
        struct HgBlob *a4,
        union _MI_Value *a5,
        union _MI_Value *a6)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int v11; // r8d
  __int64 v12; // rdi
  enum _MI_Result v13; // edx
  unsigned int v14; // eax
  struct HgBlob *v15; // r8
  char v16; // dl
  struct HgBlob *v17; // rdx
  int v18; // ebx
  struct HgBlob *v19; // r8
  struct HgBlob *v20; // r8
  struct HgBlob *v21; // r8
  struct HgBlob *v22; // rdx
  struct HgBlob *v23; // rdx
  struct HgBlob *v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // r8d
  enum _MI_Result v27; // edx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // r8d
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  Microsoft::HostGuardian::Client::Plugin::CimUtilities *v33[5]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+78h] [rbp-88h]
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  char *v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+A0h] [rbp-60h]
  const wchar_t *v41; // [rsp+A8h] [rbp-58h]
  char *v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h]
  const wchar_t *v45; // [rsp+C8h] [rbp-38h]
  char *v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+E0h] [rbp-20h]
  const wchar_t *v49; // [rsp+E8h] [rbp-18h]
  char *v50; // [rsp+F0h] [rbp-10h]
  int v51; // [rsp+F8h] [rbp-8h]
  int v52; // [rsp+100h] [rbp+0h]
  const wchar_t *v53; // [rsp+108h] [rbp+8h]
  __int64 *v54; // [rsp+110h] [rbp+10h]
  char v55; // [rsp+118h] [rbp+18h] BYREF
  __int128 v56; // [rsp+119h] [rbp+19h]
  _BYTE v57[23]; // [rsp+129h] [rbp+29h] BYREF
  char v58; // [rsp+140h] [rbp+40h] BYREF
  __int128 v59; // [rsp+141h] [rbp+41h]
  _BYTE v60[23]; // [rsp+151h] [rbp+51h] BYREF
  char v61; // [rsp+168h] [rbp+68h] BYREF
  __int128 v62; // [rsp+169h] [rbp+69h]
  _BYTE v63[23]; // [rsp+179h] [rbp+79h] BYREF
  char v64; // [rsp+190h] [rbp+90h] BYREF
  __int128 v65; // [rsp+191h] [rbp+91h]
  _BYTE v66[23]; // [rsp+1A1h] [rbp+A1h] BYREF
  _OWORD v67[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v68; // [rsp+1D8h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v35 = 0;
  v36 = 0;
  if ( !miApplication.ft )
  {
    v10 = 4;
LABEL_19:
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
      (wchar_t *)L"Failed to create a new session. %d.",
      (const wchar_t *)v10);
    v28 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
            (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v10,
            v27);
    v29 = wil::verify_hresult<long>(v28);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x21, v30, (const char *)v29, v31);
  }
  v31 = 0;
  v10 = ((__int64 (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD))miApplication.ft->NewSession)(
          &miApplication,
          0,
          0,
          0);
  if ( v10 )
    goto LABEL_19;
  v54 = &v35;
  memset((char *)v33 + 1, 0, 32);
  v33[0] = (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)a2->reserved2;
  LODWORD(v33[1]) = a2->reserved1;
  v67[0] = *(_OWORD *)v33;
  v67[1] = *(_OWORD *)&v33[2];
  v68 = 0;
  v33[0] = (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v67;
  LODWORD(v33[1]) = 0x2000;
  LODWORD(v33[2]) = 17;
  v33[3] = (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)L"IngressKeyProtector";
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(&v34, v9, v33, 1);
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(
    (unsigned int)&v37,
    (unsigned int)&v35,
    v11,
    (unsigned int)L"UnwrapKeyProtector",
    0,
    v34);
  memset(v33, 0, 17);
  v55 = 0;
  v56 = 0;
  memset(v57, 0, sizeof(v57));
  v58 = 0;
  v59 = 0;
  memset(v60, 0, sizeof(v60));
  v61 = 0;
  v62 = 0;
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  v65 = 0;
  memset(v66, 0, sizeof(v66));
  v38 = &v55;
  v39 = 0;
  v40 = 17;
  v41 = L"EncryptedTransferKey";
  v42 = &v58;
  v43 = 0;
  v44 = 17;
  v45 = L"EncryptedWrappingKey";
  v46 = &v61;
  v47 = 0;
  v48 = 17;
  v49 = L"EncryptedKeys";
  v50 = &v64;
  v51 = 0;
  v52 = 17;
  v53 = L"EgressKeyProtector";
  v12 = v37;
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(v37, &v38, 4);
  LOBYTE(v13) = LODWORD(v33[0]) != 0;
  v14 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)LODWORD(v33[0]),
          v13);
  if ( v16 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\keyprotectionoperations.cpp",
      (const char *)v14,
      v32);
  v18 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v55,
          a3,
          v15);
  if ( v18 < 0
    || (v18 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
                (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v58,
                (const union _MI_Value *)a4,
                v19),
        v18 < 0)
    || (v18 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
                (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v61,
                a5,
                v20),
        v18 < 0)
    || (v18 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
                (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v64,
                a6,
                v21),
        v18 < 0) )
  {
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
      (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a3,
      v17);
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(a4, v22);
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
      (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a5,
      v23);
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
      (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a6,
      v24);
    v25 = wil::verify_hresult<long>((unsigned int)v18);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x56, v26, (const char *)v25, v32);
  }
  if ( v12 && *(_QWORD *)v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v34 && *(_QWORD *)v34 )
    (*(void (**)(void))(*(_QWORD *)v34 + 16LL))();
  if ( *((_QWORD *)&v36 + 1) )
    (**((void (__fastcall ***)(__int64 *, _QWORD, _QWORD))&v36 + 1))(&v35, 0, 0);
}

```

## disassembly

```asm
0x1800096ec  mov     [rsp-8+arg_0], rbx
0x1800096f1  push    rbp
0x1800096f2  push    rsi
0x1800096f3  push    rdi
0x1800096f4  push    r12
0x1800096f6  push    r13
0x1800096f8  push    r14
0x1800096fa  push    r15
0x1800096fc  lea     rbp, [rsp-0F0h]
0x180009704  sub     rsp, 1F0h
0x18000970b  mov     rax, cs:__security_cookie
0x180009712  xor     rax, rsp
0x180009715  mov     [rbp+120h+var_40], rax
0x18000971c  mov     r14, r9
0x18000971f  mov     rsi, r8
0x180009722  mov     rdi, rdx
0x180009725  mov     r15, [rbp+120h+arg_20]
0x18000972c  mov     r12, [rbp+120h+arg_28]
0x180009733  xor     r13d, r13d
0x180009736  mov     [rsp+220h+var_1B0], r13
0x18000973b  xorps   xmm0, xmm0
0x18000973e  movdqu  [rsp+220h+var_1A8], xmm0
0x180009744  mov     rax, cs:?miApplication@@3U_MI_Application@@A.ft; _MI_Application miApplication ...
0x18000974b  test    rax, rax
0x18000974e  jz      loc_180009A33
0x180009754  lea     rcx, [rsp+220h+var_1B0]
0x180009759  mov     [rsp+220h+var_1F0], rcx
0x18000975e  mov     [rsp+220h+var_1F8], r13
0x180009763  mov     qword ptr [rsp+220h+var_200], r13; int
0x180009768  xor     r9d, r9d
0x18000976b  xor     r8d, r8d
0x18000976e  xor     edx, edx
0x180009770  lea     rcx, ?miApplication@@3U_MI_Application@@A; _MI_Application miApplication
0x180009777  mov     rax, [rax+8]
0x18000977b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009780  mov     ebx, eax
0x180009782  test    eax, eax
0x180009784  jnz     loc_180009A38
0x18000978a  lea     rax, [rsp+220h+var_1B0]
0x18000978f  mov     [rbp+120h+var_110], rax
0x180009793  xorps   xmm0, xmm0
0x180009796  xor     ecx, ecx
0x180009798  movups  xmmword ptr [rsp+220h+var_1E0+1], xmm0
0x18000979d  movups  [rsp+220h+var_1CF], xmm0
0x1800097a2  mov     rax, [rdi+8]
0x1800097a6  mov     [rsp+40h], rax
0x1800097ab  mov     eax, [rdi]
0x1800097ad  mov     [rsp+48h], eax
0x1800097b1  movups  xmm0, xmmword ptr [rsp+40h]
0x1800097b6  movups  [rbp+120h+var_68], xmm0
0x1800097bd  movups  xmm1, xmmword ptr [rsp+50h]
0x1800097c2  movups  [rbp+120h+var_58], xmm1
0x1800097c9  mov     [rbp+120h+var_48], rcx
0x1800097d0  lea     rax, [rbp+120h+var_68]
0x1800097d7  mov     [rsp+40h], rax
0x1800097dc  mov     dword ptr [rsp+48h], 2000h
0x1800097e4  lea     ebx, [rcx+11h]
0x1800097e7  mov     [rsp+50h], ebx
0x1800097eb  mov     rax, cs:off_18000D088; "IngressKeyProtector"
0x1800097f2  mov     qword ptr [rsp+220h+var_1CF+7], rax
0x1800097f7  lea     r9d, [r13+1]
0x1800097fb  lea     r8, [rsp+220h+var_1E0]
0x180009800  lea     rcx, [rsp+220h+var_1B8]
0x180009805  call    ?SetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Application@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(_MI_Application &,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x18000980a  nop
0x18000980b  mov     rax, [rsp+220h+var_1B8]
0x180009810  mov     [rsp+220h+var_1F8], rax
0x180009815  lea     r9, aUnwrapkeyprote; "UnwrapKeyProtector"
0x18000981c  lea     rdx, [rsp+220h+var_1B0]
0x180009821  lea     rcx, [rbp+120h+var_198]
0x180009825  call    ?InvokeStaticWmiMethod@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Session@@PEB_W11PEBU_MI_Instance@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(_MI_Session &,wchar_t const *,wchar_t const *,wchar_t const *,_MI_Instance const *)
0x18000982a  nop
0x18000982b  mov     byte ptr [rsp+220h+var_1E0], r13b
0x180009830  xorps   xmm0, xmm0
0x180009833  xor     eax, eax
0x180009835  movups  xmmword ptr [rsp+220h+var_1E0+1], xmm0
0x18000983a  mov     [rbp+120h+var_108], r13b
0x18000983e  movups  [rbp+120h+var_107], xmm0
0x180009842  movups  xmmword ptr [rbp+120h+var_F7], xmm0
0x180009846  mov     qword ptr [rbp+120h+var_F7+0Fh], rax
0x18000984a  mov     [rbp+120h+var_E0], r13b
0x18000984e  movups  [rbp+120h+var_DF], xmm0
0x180009852  movups  xmmword ptr [rbp+120h+var_CF], xmm0
0x180009856  mov     qword ptr [rbp+120h+var_CF+0Fh], rax
0x18000985a  mov     [rbp+120h+var_B8], r13b
0x18000985e  movups  [rbp+120h+var_B7], xmm0
0x180009862  movups  xmmword ptr [rbp+120h+var_A7], xmm0
0x180009866  mov     qword ptr [rbp+120h+var_A7+0Fh], rax
0x18000986d  mov     [rbp+120h+var_90], r13b
0x180009874  movups  [rbp+120h+var_8F], xmm0
0x18000987b  movups  xmmword ptr [rbp+120h+var_7F], xmm0
0x180009882  mov     qword ptr [rbp+120h+var_7F+0Fh], rax
0x180009889  lea     rax, [rbp+120h+var_108]
0x18000988d  mov     [rbp+120h+var_190], rax
0x180009891  mov     [rbp+120h+var_188], r13d
0x180009895  mov     [rbp+120h+var_180], ebx
0x180009898  mov     rax, cs:off_18000D080; "EncryptedTransferKey"
0x18000989f  mov     [rbp+120h+var_178], rax
0x1800098a3  lea     rax, [rbp+120h+var_E0]
0x1800098a7  mov     [rbp+120h+var_170], rax
0x1800098ab  mov     [rbp+120h+var_168], r13d
0x1800098af  mov     [rbp+120h+var_160], ebx
0x1800098b2  mov     rax, cs:off_18000D078; "EncryptedWrappingKey"
0x1800098b9  mov     [rbp+120h+var_158], rax
0x1800098bd  lea     rax, [rbp+120h+var_B8]
0x1800098c1  mov     [rbp+120h+var_150], rax
0x1800098c5  mov     [rbp+120h+var_148], r13d
0x1800098c9  mov     [rbp+120h+var_140], ebx
0x1800098cc  mov     rax, cs:off_18000D070; "EncryptedKeys"
0x1800098d3  mov     [rbp+120h+var_138], rax
0x1800098d7  lea     rax, [rbp+120h+var_90]
0x1800098de  mov     [rbp+120h+var_130], rax
0x1800098e2  mov     [rbp+120h+var_128], r13d
0x1800098e6  mov     [rbp+120h+var_120], ebx
0x1800098e9  mov     rax, cs:off_18000D068; "EgressKeyProtector"
0x1800098f0  mov     [rbp+120h+var_118], rax
0x1800098f4  lea     r8d, [r13+4]
0x1800098f8  lea     rdx, [rbp+120h+var_190]
0x1800098fc  mov     rdi, [rbp+120h+var_198]
0x180009900  mov     rcx, rdi
0x180009903  call    ?GetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(_MI_Instance const *,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x180009908  mov     ecx, dword ptr [rsp+220h+var_1E0]; this
0x18000990c  test    ecx, ecx
0x18000990e  setnz   dl; enum _MI_Result
0x180009911  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x180009916  mov     rcx, [rbp+128h]; this
0x18000991d  test    dl, dl
0x18000991f  jnz     loc_180009A69
0x180009925  mov     rdx, rsi; union _MI_Value *
0x180009928  lea     rcx, [rbp+120h+var_108]; this
0x18000992c  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x180009931  mov     ebx, eax
0x180009933  test    eax, eax
0x180009935  js      loc_1800099F7
0x18000993b  mov     rdx, r14; union _MI_Value *
0x18000993e  lea     rcx, [rbp+120h+var_E0]; this
0x180009942  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x180009947  mov     ebx, eax
0x180009949  test    eax, eax
0x18000994b  js      loc_1800099F7
0x180009951  mov     rdx, r15; union _MI_Value *
0x180009954  lea     rcx, [rbp+120h+var_B8]; this
0x180009958  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x18000995d  mov     ebx, eax
0x18000995f  test    eax, eax
0x180009961  js      loc_1800099F7
0x180009967  mov     rdx, r12; union _MI_Value *
0x18000996a  lea     rcx, [rbp+120h+var_90]; this
0x180009971  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x180009976  mov     ebx, eax
0x180009978  test    eax, eax
0x18000997a  js      short loc_1800099F7
0x18000997c  test    rdi, rdi
0x18000997f  jz      short loc_180009996
0x180009981  mov     rax, [rdi]
0x180009984  test    rax, rax
0x180009987  jz      short loc_180009996
0x180009989  mov     rcx, rdi
0x18000998c  mov     rax, [rax+10h]
0x180009990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009995  nop
0x180009996  mov     rcx, [rsp+220h+var_1B8]
0x18000999b  test    rcx, rcx
0x18000999e  jz      short loc_1800099B2
0x1800099a0  mov     rax, [rcx]
0x1800099a3  test    rax, rax
0x1800099a6  jz      short loc_1800099B2
0x1800099a8  mov     rax, [rax+10h]
0x1800099ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099b1  nop
0x1800099b2  mov     rax, qword ptr [rbp+120h+var_1A8+8]
0x1800099b6  test    rax, rax
0x1800099b9  jz      short loc_1800099CD
0x1800099bb  xor     r8d, r8d
0x1800099be  xor     edx, edx
0x1800099c0  lea     rcx, [rsp+220h+var_1B0]
0x1800099c5  mov     rax, [rax]
0x1800099c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cd  mov     rcx, [rbp+120h+var_40]
0x1800099d4  xor     rcx, rsp; StackCookie
0x1800099d7  call    __security_check_cookie
0x1800099dc  mov     rbx, [rsp+220h+arg_0]
0x1800099e4  add     rsp, 1F0h
0x1800099eb  pop     r15
0x1800099ed  pop     r14
0x1800099ef  pop     r13
0x1800099f1  pop     r12
0x1800099f3  pop     rdi
0x1800099f4  pop     rsi
0x1800099f5  pop     rbp
0x1800099f6  retn
0x1800099f7  mov     rcx, rsi; this
0x1800099fa  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x1800099ff  mov     rcx, r14; this
0x180009a02  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x180009a07  mov     rcx, r15; this
0x180009a0a  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x180009a0f  mov     rcx, r12; this
0x180009a12  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x180009a17  mov     ecx, ebx
0x180009a19  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180009a1e  mov     r9d, eax; char *
0x180009a21  mov     rcx, [rbp+128h]; this
0x180009a28  mov     edx, 56h ; 'V'; void *
0x180009a2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009a33  mov     ebx, 4
0x180009a38  mov     edx, ebx; wchar_t *
0x180009a3a  lea     rcx, aFailedToCreate; "Failed to create a new session. %d."
0x180009a41  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x180009a46  mov     ecx, ebx; this
0x180009a48  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x180009a4d  mov     ecx, eax
0x180009a4f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180009a54  mov     r9d, eax; char *
0x180009a57  mov     rcx, [rbp+128h]; this
0x180009a5e  mov     edx, 21h ; '!'; void *
0x180009a63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009a69  mov     r9d, eax; char *
0x180009a6c  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180009a73  mov     edx, 4Ah ; 'J'; void *
0x180009a78  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
