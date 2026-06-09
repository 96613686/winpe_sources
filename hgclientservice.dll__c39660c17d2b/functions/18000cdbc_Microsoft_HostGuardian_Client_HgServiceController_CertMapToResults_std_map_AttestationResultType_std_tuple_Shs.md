# Microsoft::HostGuardian::Client::HgServiceController::CertMapToResults(std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>>>,uint *,AttestationResult * *)

- ea: `0x18000cdbc`
- end: `0x18000cfc6`
- name: `?CertMapToResults@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@std@@PEAIPEAPEAUAttestationResult@@@Z`
- size: `522`
- prototype: `void __fastcall(__int64, void **, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d4d8`

## callees

- `0x180008760`
- `0x180008780`
- `0x18000b8b0`
- `0x18000bedc`
- `0x18000c45c`
- `0x18000cdbc`
- `0x18000cfcc`
- `0x18000d2e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce1e`

## string_xrefs

- `0x18000cf87`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cfa2`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000cfb4`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::CertMapToResults(
        __int64 a1,
        void **a2,
        unsigned int *a3,
        _QWORD *a4)
{
  char v8; // al
  _BYTE *v9; // rax
  const char *v10; // r9
  _BYTE *v11; // rdx
  __int64 i; // rcx
  int v13; // r13d
  __int64 v14; // rbx
  int v15; // r12d
  __int64 v16; // r8
  char v17; // al
  __int64 j; // rax
  unsigned int v19; // edx
  _BYTE *v20; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v21[2]; // [rsp+30h] [rbp-50h] BYREF
  char *v22; // [rsp+38h] [rbp-48h]
  char *v23; // [rsp+40h] [rbp-40h] BYREF
  char *v24; // [rsp+48h] [rbp-38h]
  __int64 v25; // [rsp+58h] [rbp-28h]
  unsigned int *v26; // [rsp+60h] [rbp-20h]
  _QWORD *v27; // [rsp+68h] [rbp-18h]
  char v28; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  unsigned int v30; // [rsp+D0h] [rbp+50h] BYREF

  if ( !a3 || !a4 || (v8 = 0, !a2[1]) )
    v8 = 1;
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x80070057LL,
      (int)v20);
  *a4 = 0;
  *a3 = 0;
  v30 = *((_DWORD *)a2 + 2);
  v9 = CoTaskMemAlloc(24LL * v30);
  v11 = v9;
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x17B,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v10);
  for ( i = 24LL * v30; i; --i )
    *v9++ = 0;
  v20 = v11;
  v25 = a1;
  v26 = &v30;
  v27 = &v20;
  v28 = 1;
  v13 = 0;
  v14 = *(_QWORD *)*a2;
  while ( !*(_BYTE *)(v14 + 25) )
  {
    v15 = *(_DWORD *)(v14 + 32);
    std::vector<unsigned char>::vector<unsigned char>(&v23, v14 + 48);
    if ( v24 != v23 || (v17 = 1, v23) )
      v17 = 0;
    if ( v17 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
        (const char *)0x8000FFFFLL,
        (int)v20);
    v21[0] = (_DWORD)v24 - (_DWORD)v23;
    v21[1] = 0;
    v22 = v23;
    Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v23, v21, v16, &v20[24 * v13 + 8]);
    *(_DWORD *)&v20[24 * v13++] = v15;
    std::vector<unsigned char>::~vector<unsigned char>(&v23);
    i = *(_QWORD *)(v14 + 16);
    if ( *(_BYTE *)(i + 25) )
    {
      for ( j = *(_QWORD *)(v14 + 8); !*(_BYTE *)(j + 25) && v14 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        v14 = j;
      v14 = j;
    }
    else
    {
      v14 = *(_QWORD *)(v14 + 16);
      for ( i = *(_QWORD *)i; !*(_BYTE *)(i + 25); i = *(_QWORD *)i )
        v14 = i;
    }
  }
  *a4 = v20;
  v19 = v30;
  *a3 = v30;
  v20 = 0;
  Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(
    (Microsoft::HostGuardian::Client::HgServiceController *)i,
    v19,
    0);
  std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(a2);
}

```

## disassembly

```asm
0x18000cdbc  mov     [rsp-38h+arg_0], rbx
0x18000cdc1  mov     [rsp-38h+arg_8], rdx
0x18000cdc6  push    rbp
0x18000cdc7  push    rsi
0x18000cdc8  push    rdi
0x18000cdc9  push    r12
0x18000cdcb  push    r13
0x18000cdcd  push    r14
0x18000cdcf  push    r15
0x18000cdd1  mov     rbp, rsp
0x18000cdd4  sub     rsp, 80h
0x18000cddb  mov     r14, r9
0x18000cdde  mov     r15, r8
0x18000cde1  mov     rsi, rdx
0x18000cde4  mov     rbx, rcx
0x18000cde7  xor     edi, edi
0x18000cde9  test    r8, r8
0x18000cdec  jz      short loc_18000CDFC
0x18000cdee  test    r9, r9
0x18000cdf1  jz      short loc_18000CDFC
0x18000cdf3  cmp     [rdx+8], rdi
0x18000cdf7  mov     al, dil
0x18000cdfa  jnz     short loc_18000CDFE
0x18000cdfc  mov     al, 1
0x18000cdfe  mov     rcx, [rbp+38h]; this
0x18000ce02  test    al, al
0x18000ce04  jnz     loc_18000CF9C
0x18000ce0a  mov     [r9], rdi
0x18000ce0d  mov     [r8], edi
0x18000ce10  mov     eax, [rdx+8]
0x18000ce13  mov     [rbp+arg_10], eax
0x18000ce16  lea     rcx, [rax+rax*2]
0x18000ce1a  shl     rcx, 3; cb
0x18000ce1e  call    cs:__imp_CoTaskMemAlloc
0x18000ce24  mov     rdx, rax
0x18000ce27  mov     rcx, [rbp+38h]; this
0x18000ce2b  test    rax, rax
0x18000ce2e  jz      loc_18000CFB4
0x18000ce34  mov     eax, [rbp+arg_10]
0x18000ce37  lea     rcx, [rax+rax*2]
0x18000ce3b  shl     rcx, 3
0x18000ce3f  mov     rax, rdx
0x18000ce42  test    rcx, rcx
0x18000ce45  jz      short loc_18000CE53
0x18000ce47  mov     [rax], dil
0x18000ce4a  inc     rax
0x18000ce4d  sub     rcx, 1; this
0x18000ce51  jnz     short loc_18000CE47
0x18000ce53  mov     [rbp+var_60], rdx
0x18000ce57  mov     [rbp+var_28], rbx
0x18000ce5b  lea     rax, [rbp+arg_10]
0x18000ce5f  mov     [rbp+var_20], rax
0x18000ce63  lea     rax, [rbp+var_60]
0x18000ce67  mov     [rbp+var_18], rax
0x18000ce6b  mov     [rbp+var_10], 1
0x18000ce6f  mov     r13d, edi
0x18000ce72  mov     rbx, [rsi]
0x18000ce75  mov     rbx, [rbx]
0x18000ce78  cmp     [rbx+19h], dil
0x18000ce7c  jnz     loc_18000CF44
0x18000ce82  mov     r12d, [rbx+20h]
0x18000ce86  lea     rdx, [rbx+30h]
0x18000ce8a  lea     rcx, [rbp+var_40]
0x18000ce8e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000ce93  nop
0x18000ce94  mov     rcx, [rbp+var_40]
0x18000ce98  mov     rdx, [rbp+var_38]
0x18000ce9c  sub     rdx, rcx
0x18000ce9f  jnz     short loc_18000CEA8
0x18000cea1  test    rcx, rcx
0x18000cea4  mov     al, 1
0x18000cea6  jz      short loc_18000CEAB
0x18000cea8  mov     al, dil
0x18000ceab  mov     r10, [rbp+38h]
0x18000ceaf  test    al, al
0x18000ceb1  jnz     loc_18000CF81
0x18000ceb7  movsxd  rax, r13d
0x18000ceba  lea     rdi, [rax+rax*2]
0x18000cebe  xor     eax, eax
0x18000cec0  mov     [rbp+var_50], edx
0x18000cec3  mov     [rbp+var_4C], eax
0x18000cec6  mov     [rbp+var_48], rcx
0x18000ceca  mov     r9, [rbp+var_60]
0x18000cece  add     r9, 8
0x18000ced2  lea     r9, [r9+rdi*8]
0x18000ced6  lea     rdx, [rbp+var_50]
0x18000ceda  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000cedf  mov     rax, [rbp+var_60]
0x18000cee3  mov     [rax+rdi*8], r12d
0x18000cee7  inc     r13d
0x18000ceea  lea     rcx, [rbp+var_40]
0x18000ceee  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000cef3  mov     rcx, [rbx+10h]
0x18000cef7  xor     edi, edi
0x18000cef9  cmp     [rcx+19h], dil
0x18000cefd  jz      short loc_18000CF20
0x18000ceff  mov     rax, [rbx+8]
0x18000cf03  jmp     short loc_18000CF12
0x18000cf05  cmp     rbx, [rax+10h]
0x18000cf09  jnz     short loc_18000CF18
0x18000cf0b  mov     rbx, rax
0x18000cf0e  mov     rax, [rax+8]
0x18000cf12  cmp     [rax+19h], dil
0x18000cf16  jz      short loc_18000CF05
0x18000cf18  mov     rbx, rax
0x18000cf1b  jmp     loc_18000CE78
0x18000cf20  mov     rbx, rcx
0x18000cf23  mov     rcx, [rcx]
0x18000cf26  cmp     [rcx+19h], dil
0x18000cf2a  jnz     loc_18000CE78
0x18000cf30  mov     rbx, rcx
0x18000cf33  mov     rax, [rcx]
0x18000cf36  mov     rcx, rax
0x18000cf39  cmp     [rax+19h], dil
0x18000cf3d  jz      short loc_18000CF30
0x18000cf3f  jmp     loc_18000CE78
0x18000cf44  mov     rax, [rbp+var_60]
0x18000cf48  mov     [r14], rax
0x18000cf4b  mov     edx, [rbp+arg_10]; unsigned int
0x18000cf4e  mov     [r15], edx
0x18000cf51  mov     [rbp+var_60], rdi
0x18000cf55  xor     r8d, r8d; struct AttestationResult *
0x18000cf58  call    ?FreeAttestationResults@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXIPEAUAttestationResult@@@Z; Microsoft::HostGuardian::Client::HgServiceController::FreeAttestationResults(uint,AttestationResult *)
0x18000cf5d  nop
0x18000cf5e  mov     rcx, rsi
0x18000cf61  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000cf66  mov     rbx, [rsp+80h+arg_0]
0x18000cf6e  add     rsp, 80h
0x18000cf75  pop     r15
0x18000cf77  pop     r14
0x18000cf79  pop     r13
0x18000cf7b  pop     r12
0x18000cf7d  pop     rdi
0x18000cf7e  pop     rsi
0x18000cf7f  pop     rbp
0x18000cf80  retn
0x18000cf81  mov     r9d, 8000FFFFh; char *
0x18000cf87  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cf8e  mov     edx, 18Ch; void *
0x18000cf93  mov     rcx, r10; this
0x18000cf96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cf9c  mov     r9d, 80070057h; char *
0x18000cfa2  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cfa9  mov     edx, 174h; void *
0x18000cfae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cfb4  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000cfbb  mov     edx, 17Bh; void *
0x18000cfc0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
