# Microsoft::HostGuardian::Client::HgServiceController::IssueCertificate(unsigned __int64,HgBlob *,HgBlob *,HgBlob *,HgBlob *,HgBlob *)

- ea: `0x18000d348`
- end: `0x18000d4d1`
- name: `?IssueCertificate@HgServiceController@Client@HostGuardian@Microsoft@@QEAAX_KPEAUHgBlob@@1111@Z`
- size: `393`
- prototype: `void __fastcall(RTL_SRWLOCK *this, unsigned __int64, struct HgBlob *, struct HgBlob *, struct HgBlob *, struct HgBlob *, struct HgBlob *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000abf0`

## callees

- `0x180008760`
- `0x18000cfcc`
- `0x18000d348`
- `0x18000dab8`
- `0x1800136a4`
- `0x180013714`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d488`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d4a5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d488`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d4a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d435`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d435`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d472`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d472`

## string_xrefs

- `0x18000d4bf`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::IssueCertificate(
        RTL_SRWLOCK *this,
        unsigned __int64 a2,
        struct HgBlob *a3,
        struct HgBlob *a4,
        struct HgBlob *a5,
        struct HgBlob *a6,
        struct HgBlob *a7)
{
  Microsoft::HostGuardian::Client::VsmCaAgent *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  _QWORD *Ptr; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // [rsp+20h] [rbp-91h]
  void *Block[2]; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int8 *v19[2]; // [rsp+70h] [rbp-41h] BYREF
  __int128 v20; // [rsp+80h] [rbp-31h] BYREF
  __int128 *v21; // [rsp+90h] [rbp-21h]
  char v22; // [rsp+98h] [rbp-19h]
  __int128 v23; // [rsp+A0h] [rbp-11h] BYREF
  void **v24; // [rsp+B0h] [rbp-1h]
  unsigned __int8 **v25; // [rsp+B8h] [rbp+7h]
  char v26; // [rsp+C0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]

  *(_OWORD *)Block = 0;
  *(_OWORD *)v19 = 0;
  v24 = Block;
  v25 = v19;
  v26 = 1;
  v11 = Microsoft::HostGuardian::Client::VsmCaAgent::Instance();
  Microsoft::HostGuardian::Client::VsmCaAgent::IssueCertificateInternal(
    v11,
    a2,
    *(_DWORD *)a3,
    *((unsigned __int8 **)a3 + 1),
    *(_DWORD *)a4,
    *((unsigned __int8 **)a4 + 1),
    *(_DWORD *)a5,
    *((unsigned __int8 **)a5 + 1),
    (unsigned int *)Block,
    (unsigned __int8 **)&Block[1],
    (unsigned int *)v19,
    &v19[1]);
  v20 = *(_OWORD *)Block;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v12, (unsigned int *)&v20, v13, (__int64)a7);
  if ( !a6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x80004003LL,
      v17);
  Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert((Microsoft::HostGuardian::Client::HgServiceController *)this);
  v20 = 0;
  v21 = &v20;
  v22 = 1;
  AcquireSRWLockShared(this + 19);
  Ptr = this[18].Ptr;
  *((_QWORD *)&v20 + 1) = Ptr[1];
  LODWORD(v20) = *((_DWORD *)Ptr + 4);
  v23 = v20;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v15, (unsigned int *)&v23, v16, (__int64)a6);
  if ( this != (RTL_SRWLOCK *)-152LL )
    ReleaseSRWLockShared(this + 19);
  if ( LODWORD(Block[0]) && Block[1] )
  {
    free(Block[1]);
    *(_OWORD *)Block = 0;
  }
  if ( LODWORD(v19[0]) )
  {
    if ( v19[1] )
      free(v19[1]);
  }
}

```

## disassembly

```asm
0x18000d348  push    rbp
0x18000d34a  push    rbx
0x18000d34b  push    rsi
0x18000d34c  push    rdi
0x18000d34d  push    r14
0x18000d34f  lea     rbp, [rsp-1Fh]
0x18000d354  sub     rsp, 0D0h
0x18000d35b  mov     rbx, r9
0x18000d35e  mov     rdi, r8
0x18000d361  mov     rsi, rdx
0x18000d364  mov     r14, rcx
0x18000d367  xorps   xmm0, xmm0
0x18000d36a  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x18000d36e  xorps   xmm1, xmm1
0x18000d371  movups  xmmword ptr [rbp+3Fh+var_80], xmm1
0x18000d375  lea     rax, [rbp+3Fh+Block]
0x18000d379  mov     [rbp+3Fh+var_40], rax
0x18000d37d  lea     rax, [rbp+3Fh+var_80]
0x18000d381  mov     [rbp+3Fh+var_38], rax
0x18000d385  mov     [rbp+3Fh+var_30], 1
0x18000d389  call    ?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
0x18000d38e  mov     r10, rax
0x18000d391  lea     rax, [rbp+3Fh+var_80+8]
0x18000d395  mov     [rsp+0F0h+var_98], rax; unsigned __int8 **
0x18000d39a  lea     rax, [rbp+3Fh+var_80]
0x18000d39e  mov     [rsp+0F0h+var_A0], rax; unsigned int *
0x18000d3a3  lea     rax, [rbp+3Fh+Block+8]
0x18000d3a7  mov     [rsp+0F0h+var_A8], rax; unsigned __int8 **
0x18000d3ac  lea     rax, [rbp+3Fh+Block]
0x18000d3b0  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x18000d3b5  mov     rdx, [rbp+3Fh+arg_20]
0x18000d3b9  mov     rcx, [rdx+8]
0x18000d3bd  mov     [rsp+0F0h+var_B8], rcx; unsigned __int8 *
0x18000d3c2  mov     ecx, [rdx]
0x18000d3c4  mov     [rsp+0F0h+var_C0], ecx; unsigned int
0x18000d3c8  mov     rcx, [rbx+8]
0x18000d3cc  mov     [rsp+0F0h+var_C8], rcx; unsigned __int8 *
0x18000d3d1  mov     eax, [rbx]
0x18000d3d3  mov     [rsp+0F0h+var_D0], eax; int
0x18000d3d7  mov     r9, [rdi+8]; unsigned __int8 *
0x18000d3db  mov     r8d, [rdi]; unsigned int
0x18000d3de  mov     rdx, rsi; unsigned __int64
0x18000d3e1  mov     rcx, r10; this
0x18000d3e4  call    ?IssueCertificateInternal@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAX_KIPEAEI1I1PEAIPEAPEAE23@Z; Microsoft::HostGuardian::Client::VsmCaAgent::IssueCertificateInternal(unsigned __int64,uint,uchar *,uint,uchar *,uint,uchar *,uint *,uchar * *,uint *,uchar * *)
0x18000d3e9  movaps  xmm0, xmmword ptr [rbp+3Fh+Block]
0x18000d3ed  movdqa  [rbp+3Fh+var_70], xmm0
0x18000d3f2  mov     r9, [rbp+3Fh+arg_30]
0x18000d3f6  lea     rdx, [rbp+3Fh+var_70]
0x18000d3fa  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000d3ff  mov     rcx, [rbp+47h]; this
0x18000d403  mov     rdi, [rbp+3Fh+arg_28]
0x18000d407  test    rdi, rdi
0x18000d40a  jz      loc_18000D4B9
0x18000d410  mov     rcx, r14; this
0x18000d413  call    ?RequestAndStoreCAIntermediateCert@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::HgServiceController::RequestAndStoreCAIntermediateCert(void)
0x18000d418  xorps   xmm0, xmm0
0x18000d41b  movups  [rbp+3Fh+var_70], xmm0
0x18000d41f  lea     rax, [rbp+3Fh+var_70]
0x18000d423  mov     [rbp+3Fh+var_60], rax
0x18000d427  mov     [rbp+3Fh+var_58], 1
0x18000d42b  lea     rbx, [r14+98h]
0x18000d432  mov     rcx, rbx; SRWLock
0x18000d435  call    cs:__imp_AcquireSRWLockShared
0x18000d43b  mov     [rbp+3Fh+arg_20], rbx
0x18000d43f  mov     rdx, [r14+90h]
0x18000d446  mov     rax, [rdx+8]
0x18000d44a  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x18000d44e  mov     eax, [rdx+10h]
0x18000d451  mov     dword ptr [rbp+3Fh+var_70], eax
0x18000d454  movaps  xmm0, [rbp+3Fh+var_70]
0x18000d458  movdqa  [rbp+3Fh+var_50], xmm0
0x18000d45d  mov     r9, rdi
0x18000d460  lea     rdx, [rbp+3Fh+var_50]
0x18000d464  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000d469  nop
0x18000d46a  test    rbx, rbx
0x18000d46d  jz      short loc_18000D479
0x18000d46f  mov     rcx, rbx; SRWLock
0x18000d472  call    cs:__imp_ReleaseSRWLockShared
0x18000d478  nop
0x18000d479  cmp     dword ptr [rbp+3Fh+Block], 0
0x18000d47d  jbe     short loc_18000D496
0x18000d47f  mov     rcx, [rbp+3Fh+Block+8]; Block
0x18000d483  test    rcx, rcx
0x18000d486  jz      short loc_18000D496
0x18000d488  call    cs:__imp_free
0x18000d48e  xorps   xmm0, xmm0
0x18000d491  movdqa  xmmword ptr [rbp+3Fh+Block], xmm0
0x18000d496  cmp     dword ptr [rbp+3Fh+var_80], 0
0x18000d49a  jbe     short loc_18000D4AB
0x18000d49c  mov     rcx, [rbp+3Fh+var_80+8]; Block
0x18000d4a0  test    rcx, rcx
0x18000d4a3  jz      short loc_18000D4AB
0x18000d4a5  call    cs:__imp_free
0x18000d4ab  add     rsp, 0D0h
0x18000d4b2  pop     r14
0x18000d4b4  pop     rdi
0x18000d4b5  pop     rsi
0x18000d4b6  pop     rbx
0x18000d4b7  pop     rbp
0x18000d4b8  retn
0x18000d4b9  mov     r9d, 80004003h; char *
0x18000d4bf  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d4c6  mov     edx, 2B5h; void *
0x18000d4cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
