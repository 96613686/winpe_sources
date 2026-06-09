# Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::EncryptDataWithKeyProtector(_MI_Application &,HgBlob const &,uint,HgBlob const &,bool,HgBlob &,HgBlob &)

- ea: `0x1800092fc`
- end: `0x18000966a`
- name: `?EncryptDataWithKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@I1_NAEAU7@3@Z`
- size: `878`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this, struct _MI_Application *, const struct HgBlob *, __int64, const struct HgBlob *, union _MI_Value *, union _MI_Value *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x180001520`
- `0x1800029c8`
- `0x1800068ec`
- `0x1800092fc`
- `0x180009670`
- `0x1800096c4`
- `0x180009cfc`
- `0x180009f44`
- `0x18000a070`
- `0x18000a45c`
- `0x18000a550`
- `0x18000c010`

## string_xrefs

- `0x18000963b`: `Failed to create a new session. %d.`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::EncryptDataWithKeyProtector(
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this,
        struct _MI_Application *a2,
        const struct HgBlob *a3,
        __int64 a4,
        const struct HgBlob *a5,
        union _MI_Value *a6,
        union _MI_Value *a7)
{
  int v8; // r12d
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // r8d
  __int64 v13; // rbx
  struct HgBlob *v14; // r8
  struct HgBlob *v15; // rdx
  int v16; // edi
  struct HgBlob *v17; // r8
  struct HgBlob *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // r8d
  enum _MI_Result v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // r8d
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[40]; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+80h] [rbp-80h]
  const wchar_t *v31; // [rsp+88h] [rbp-78h]
  _OWORD *v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+A0h] [rbp-60h]
  const wchar_t *v35; // [rsp+A8h] [rbp-58h]
  bool *v36; // [rsp+B0h] [rbp-50h]
  int v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  const wchar_t *v39; // [rsp+C8h] [rbp-38h]
  __int64 v40; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v41; // [rsp+D8h] [rbp-28h]
  _QWORD v42[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v43; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v44; // [rsp+F9h] [rbp-7h]
  _BYTE v45[23]; // [rsp+109h] [rbp+9h] BYREF
  char v46; // [rsp+120h] [rbp+20h] BYREF
  __int128 v47; // [rsp+121h] [rbp+21h]
  _BYTE v48[23]; // [rsp+131h] [rbp+31h] BYREF
  _QWORD v49[5]; // [rsp+148h] [rbp+48h] BYREF
  bool v50; // [rsp+170h] [rbp+70h] BYREF
  __int128 v51; // [rsp+171h] [rbp+71h]
  _BYTE v52[23]; // [rsp+181h] [rbp+81h] BYREF
  _OWORD v53[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v54; // [rsp+1B8h] [rbp+B8h]
  _OWORD v55[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v56; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v8 = (int)a3;
  v40 = 0;
  v41 = 0;
  if ( !miApplication.ft )
  {
    v11 = 4;
LABEL_16:
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
      (wchar_t *)L"Failed to create a new session. %d.",
      (const wchar_t *)v11);
    v22 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
            (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v11,
            v21);
    v23 = wil::verify_hresult<long>(v22);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xB1, v24, (const char *)v23, v25);
  }
  v25 = 0;
  v11 = ((__int64 (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD))miApplication.ft->NewSession)(
          &miApplication,
          0,
          0,
          0);
  if ( v11 )
    goto LABEL_16;
  v42[1] = &v40;
  memset(&v28[1], 0, 32);
  *(_QWORD *)v28 = a2->reserved2;
  *(_DWORD *)&v28[8] = a2->reserved1;
  v53[0] = *(_OWORD *)v28;
  v53[1] = *(_OWORD *)&v28[16];
  v54 = 0;
  memset(&v28[1], 0, 32);
  *(_QWORD *)v28 = *(_QWORD *)(a4 + 8);
  *(_DWORD *)&v28[8] = *(_DWORD *)a4;
  v55[0] = *(_OWORD *)v28;
  v55[1] = *(_OWORD *)&v28[16];
  v56 = 0;
  *(_OWORD *)((char *)v49 + 1) = 0;
  memset((char *)&v49[2] + 1, 0, 23);
  LODWORD(v49[0]) = v8;
  v51 = 0;
  memset(v52, 0, sizeof(v52));
  v50 = (_BYTE)a5 != 0;
  *(_QWORD *)v28 = v53;
  *(_DWORD *)&v28[8] = 0x2000;
  *(_DWORD *)&v28[16] = 17;
  *(_QWORD *)&v28[24] = L"BaseKeyProtector";
  *(_QWORD *)&v28[32] = v49;
  v29 = 0x2000;
  v30 = 5;
  v31 = L"UniqueEncryptionIdentifier";
  v32 = v55;
  v33 = 0x2000;
  v34 = 17;
  v35 = L"PlainTextData";
  v36 = &v50;
  v37 = 0x2000;
  v38 = 0;
  v39 = L"RollKeyProtector";
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(&v27, v10, v28, 4);
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(
    (unsigned int)v42,
    (unsigned int)&v40,
    v12,
    (unsigned int)L"EncryptDataWithKeyProtector",
    0,
    v27);
  v46 = 0;
  v47 = 0;
  memset(v48, 0, sizeof(v48));
  v43 = 0;
  v44 = 0;
  memset(v45, 0, sizeof(v45));
  *(_QWORD *)v28 = &v46;
  *(_DWORD *)&v28[8] = 0;
  *(_DWORD *)&v28[16] = 17;
  *(_QWORD *)&v28[24] = L"EncryptedData";
  *(_QWORD *)&v28[32] = &v43;
  v29 = 0;
  v30 = 17;
  v31 = L"EgressKeyProtector";
  v13 = v42[0];
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(v42[0], v28, 2);
  v16 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
          (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v43,
          a6,
          v14);
  if ( v16 < 0
    || (v16 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
                (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)&v46,
                a7,
                v17),
        v16 < 0) )
  {
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
      (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a6,
      v15);
    Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
      (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a7,
      v18);
    v19 = wil::verify_hresult<long>((unsigned int)v16);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xE1, v20, (const char *)v19, v26);
  }
  if ( v13 && *(_QWORD *)v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v27 && *(_QWORD *)v27 )
    (*(void (**)(void))(*(_QWORD *)v27 + 16LL))();
  if ( *((_QWORD *)&v41 + 1) )
    (**((void (__fastcall ***)(__int64 *, _QWORD, _QWORD))&v41 + 1))(&v40, 0, 0);
}

```

## disassembly

```asm
0x1800092fc  push    rbp
0x1800092fe  push    rbx
0x1800092ff  push    rsi
0x180009300  push    rdi
0x180009301  push    r12
0x180009303  push    r14
0x180009305  push    r15
0x180009307  lea     rbp, [rsp-0F0h]
0x18000930f  sub     rsp, 1F0h
0x180009316  mov     rax, cs:__security_cookie
0x18000931d  xor     rax, rsp
0x180009320  mov     [rbp+120h+var_38], rax
0x180009327  mov     rdi, r9
0x18000932a  mov     r12d, r8d
0x18000932d  mov     r15, rdx
0x180009330  mov     r14, [rbp+120h+arg_28]
0x180009337  mov     rsi, [rbp+120h+arg_30]
0x18000933e  mov     [rbp+120h+var_150], 0
0x180009346  xorps   xmm0, xmm0
0x180009349  movdqu  [rbp+120h+var_148], xmm0
0x18000934e  mov     rax, cs:?miApplication@@3U_MI_Application@@A.ft; _MI_Application miApplication ...
0x180009355  test    rax, rax
0x180009358  jz      loc_180009634
0x18000935e  lea     rcx, [rbp+120h+var_150]
0x180009362  mov     [rsp+220h+var_1F0], rcx
0x180009367  mov     [rsp+220h+var_1F8], 0
0x180009370  mov     qword ptr [rsp+220h+var_200], 0; int
0x180009379  xor     r9d, r9d
0x18000937c  xor     r8d, r8d
0x18000937f  xor     edx, edx
0x180009381  lea     rcx, ?miApplication@@3U_MI_Application@@A; _MI_Application miApplication
0x180009388  mov     rax, [rax+8]
0x18000938c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009391  mov     ebx, eax
0x180009393  test    eax, eax
0x180009395  jnz     loc_180009639
0x18000939b  lea     rax, [rbp+120h+var_150]
0x18000939f  mov     [rbp+120h+var_130], rax
0x1800093a3  xorps   xmm0, xmm0
0x1800093a6  xor     ecx, ecx
0x1800093a8  movups  xmmword ptr [rsp+220h+var_1D0+1], xmm0
0x1800093ad  movups  [rsp+220h+var_1BF], xmm0
0x1800093b2  mov     rax, [r15+8]
0x1800093b6  mov     [rsp+50h], rax
0x1800093bb  mov     eax, [r15]
0x1800093be  mov     [rsp+220h+var_1C8], eax
0x1800093c2  movups  xmm0, xmmword ptr [rsp+50h]
0x1800093c7  movups  [rbp+120h+var_88], xmm0
0x1800093ce  movups  xmm1, xmmword ptr [rsp+60h]
0x1800093d3  movups  [rbp+120h+var_78], xmm1
0x1800093da  mov     [rbp+120h+var_68], rcx
0x1800093e1  xorps   xmm1, xmm1
0x1800093e4  movups  xmmword ptr [rsp+220h+var_1D0+1], xmm1
0x1800093e9  movups  [rsp+220h+var_1BF], xmm1
0x1800093ee  mov     rax, [rdi+8]
0x1800093f2  mov     [rsp+50h], rax
0x1800093f7  mov     eax, [rdi]
0x1800093f9  mov     [rsp+220h+var_1C8], eax
0x1800093fd  movups  xmm0, xmmword ptr [rsp+50h]
0x180009402  movups  [rbp+120h+var_60], xmm0
0x180009409  movups  xmm1, xmmword ptr [rsp+60h]
0x18000940e  movups  [rbp+120h+var_50], xmm1
0x180009415  mov     [rbp+120h+var_40], rcx
0x18000941c  xorps   xmm1, xmm1
0x18000941f  xor     eax, eax
0x180009421  movups  [rbp+120h+var_D7], xmm1
0x180009425  movups  xmmword ptr [rbp+120h+var_C7], xmm1
0x180009429  mov     qword ptr [rbp+120h+var_C7+0Fh], rax
0x18000942d  mov     [rbp+48h], r12d
0x180009431  xorps   xmm0, xmm0
0x180009434  movups  [rbp+120h+var_AF], xmm0
0x180009438  movups  xmmword ptr [rbp+120h+var_9F], xmm0
0x18000943f  mov     qword ptr [rbp+120h+var_9F+0Fh], rax
0x180009446  cmp     byte ptr [rbp+120h+arg_20], al
0x18000944c  setnz   [rbp+120h+var_B0]
0x180009450  lea     rax, [rbp+120h+var_88]
0x180009457  mov     [rsp+50h], rax
0x18000945c  mov     ecx, 2000h
0x180009461  mov     [rsp+220h+var_1C8], ecx
0x180009465  lea     edi, [rbx+11h]
0x180009468  mov     [rsp+60h], edi
0x18000946c  mov     rax, cs:off_18000D0B0; "BaseKeyProtector"
0x180009473  mov     qword ptr [rsp+220h+var_1BF+7], rax
0x180009478  lea     rax, [rbp+120h+var_D8]
0x18000947c  mov     qword ptr [rsp+220h+var_1BF+0Fh], rax
0x180009481  mov     [rsp+220h+var_1A8], ecx
0x180009485  mov     [rbp+120h+var_1A0], 5
0x18000948c  mov     rax, cs:off_18000D0A8; "UniqueEncryptionIdentifier"
0x180009493  mov     [rbp+120h+var_198], rax
0x180009497  lea     rax, [rbp+120h+var_60]
0x18000949e  mov     [rbp+120h+var_190], rax
0x1800094a2  mov     [rbp+120h+var_188], ecx
0x1800094a5  mov     [rbp+120h+var_180], edi
0x1800094a8  mov     rax, cs:off_18000D0A0; "PlainTextData"
0x1800094af  mov     [rbp+120h+var_178], rax
0x1800094b3  lea     rax, [rbp+120h+var_B0]
0x1800094b7  mov     [rbp+120h+var_170], rax
0x1800094bb  mov     [rbp+120h+var_168], ecx
0x1800094be  mov     [rbp+120h+var_160], ebx
0x1800094c1  mov     rax, cs:off_18000D090; "RollKeyProtector"
0x1800094c8  mov     [rbp+120h+var_158], rax
0x1800094cc  lea     r9d, [rbx+4]
0x1800094d0  lea     r8, [rsp+220h+var_1D0]
0x1800094d5  lea     rcx, [rsp+220h+var_1E0]
0x1800094da  call    ?SetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Application@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(_MI_Application &,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x1800094df  nop
0x1800094e0  mov     rax, [rsp+220h+var_1E0]
0x1800094e5  mov     [rsp+220h+var_1F8], rax
0x1800094ea  lea     r9, aEncryptdatawit; "EncryptDataWithKeyProtector"
0x1800094f1  lea     rdx, [rbp+120h+var_150]
0x1800094f5  lea     rcx, [rbp+120h+var_138]
0x1800094f9  call    ?InvokeStaticWmiMethod@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Session@@PEB_W11PEBU_MI_Instance@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod(_MI_Session &,wchar_t const *,wchar_t const *,wchar_t const *,_MI_Instance const *)
0x1800094fe  nop
0x1800094ff  mov     [rbp+120h+var_100], bl
0x180009502  xorps   xmm0, xmm0
0x180009505  xor     eax, eax
0x180009507  movups  [rbp+120h+var_FF], xmm0
0x18000950b  movups  xmmword ptr [rbp+120h+var_EF], xmm0
0x18000950f  mov     qword ptr [rbp+120h+var_EF+0Fh], rax
0x180009513  mov     [rbp+120h+var_128], al
0x180009516  movups  [rbp+120h+var_127], xmm0
0x18000951a  movups  xmmword ptr [rbp+120h+var_117], xmm0
0x18000951e  mov     qword ptr [rbp+120h+var_117+0Fh], rax
0x180009522  lea     rax, [rbp+120h+var_100]
0x180009526  mov     [rsp+220h+var_1D0], rax
0x18000952b  mov     [rsp+220h+var_1C8], ebx
0x18000952f  mov     [rsp+60h], edi
0x180009533  mov     rax, cs:off_18000D098; "EncryptedData"
0x18000953a  mov     qword ptr [rsp+220h+var_1BF+7], rax
0x18000953f  lea     rax, [rbp+120h+var_128]
0x180009543  mov     qword ptr [rsp+220h+var_1BF+0Fh], rax
0x180009548  mov     [rsp+220h+var_1A8], ebx
0x18000954c  mov     [rbp+120h+var_1A0], edi
0x18000954f  mov     rax, cs:off_18000D068; "EgressKeyProtector"
0x180009556  mov     [rbp+120h+var_198], rax
0x18000955a  lea     r8d, [rbx+2]
0x18000955e  lea     rdx, [rsp+220h+var_1D0]
0x180009563  mov     rbx, [rbp+120h+var_138]
0x180009567  mov     rcx, rbx
0x18000956a  call    ?GetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(_MI_Instance const *,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x18000956f  mov     rdx, r14; union _MI_Value *
0x180009572  lea     rcx, [rbp+120h+var_128]; this
0x180009576  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x18000957b  mov     edi, eax
0x18000957d  test    eax, eax
0x18000957f  js      loc_180009608
0x180009585  mov     rdx, rsi; union _MI_Value *
0x180009588  lea     rcx, [rbp+120h+var_100]; this
0x18000958c  call    ?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)
0x180009591  mov     edi, eax
0x180009593  test    eax, eax
0x180009595  js      short loc_180009608
0x180009597  test    rbx, rbx
0x18000959a  jz      short loc_1800095B1
0x18000959c  mov     rax, [rbx]
0x18000959f  test    rax, rax
0x1800095a2  jz      short loc_1800095B1
0x1800095a4  mov     rcx, rbx
0x1800095a7  mov     rax, [rax+10h]
0x1800095ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b0  nop
0x1800095b1  mov     rcx, [rsp+220h+var_1E0]
0x1800095b6  test    rcx, rcx
0x1800095b9  jz      short loc_1800095CD
0x1800095bb  mov     rax, [rcx]
0x1800095be  test    rax, rax
0x1800095c1  jz      short loc_1800095CD
0x1800095c3  mov     rax, [rax+10h]
0x1800095c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095cc  nop
0x1800095cd  mov     rax, qword ptr [rbp+120h+var_148+8]
0x1800095d1  test    rax, rax
0x1800095d4  jz      short loc_1800095E7
0x1800095d6  xor     r8d, r8d
0x1800095d9  xor     edx, edx
0x1800095db  lea     rcx, [rbp+120h+var_150]
0x1800095df  mov     rax, [rax]
0x1800095e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e7  mov     rcx, [rbp+120h+var_38]
0x1800095ee  xor     rcx, rsp; StackCookie
0x1800095f1  call    __security_check_cookie
0x1800095f6  add     rsp, 1F0h
0x1800095fd  pop     r15
0x1800095ff  pop     r14
0x180009601  pop     r12
0x180009603  pop     rdi
0x180009604  pop     rsi
0x180009605  pop     rbx
0x180009606  pop     rbp
0x180009607  retn
0x180009608  mov     rcx, r14; this
0x18000960b  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x180009610  mov     rcx, rsi; this
0x180009613  call    ?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)
0x180009618  mov     ecx, edi
0x18000961a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000961f  mov     r9d, eax; char *
0x180009622  mov     rcx, [rbp+128h]; this
0x180009629  mov     edx, 0E1h; void *
0x18000962e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009634  mov     ebx, 4
0x180009639  mov     edx, ebx; wchar_t *
0x18000963b  lea     rcx, aFailedToCreate; "Failed to create a new session. %d."
0x180009642  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x180009647  mov     ecx, ebx; this
0x180009649  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x18000964e  mov     ecx, eax
0x180009650  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180009655  mov     r9d, eax; char *
0x180009658  mov     rcx, [rbp+128h]; this
0x18000965f  mov     edx, 0B1h; void *
0x180009664  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
