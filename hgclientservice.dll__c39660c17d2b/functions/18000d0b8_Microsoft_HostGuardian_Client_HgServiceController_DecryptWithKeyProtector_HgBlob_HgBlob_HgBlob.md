# Microsoft::HostGuardian::Client::HgServiceController::DecryptWithKeyProtector(HgBlob *,HgBlob *,HgBlob *)

- ea: `0x18000d0b8`
- end: `0x18000d189`
- name: `?DecryptWithKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXPEAUHgBlob@@00@Z`
- size: `209`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *__hidden this, struct HgBlob *, struct HgBlob *, struct HgBlob *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000af90`

## callees

- `0x180008760`
- `0x18000cfcc`
- `0x18000d0b8`
- `0x1800140ac`
- `0x1800141f0`

## string_xrefs

- `0x18000d162`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000d177`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::DecryptWithKeyProtector(
        Microsoft::HostGuardian::Client::HgServiceController *this,
        struct HgBlob *a2,
        struct HgBlob *a3,
        struct HgBlob *a4)
{
  bool v6; // bl
  int v7; // eax
  __int64 v8; // r8
  __int128 v9; // [rsp+20h] [rbp-58h] BYREF
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+40h] [rbp-38h] BYREF
  __int128 *v12; // [rsp+50h] [rbp-28h]
  Microsoft::HostGuardian::Client::HgServiceController *v13; // [rsp+58h] [rbp-20h]
  char v14; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v9 = 0;
  v12 = &v9;
  v13 = this;
  v6 = 1;
  v14 = 1;
  v10 = *(_OWORD *)a3;
  v11 = *(_OWORD *)a2;
  v7 = Microsoft::HostGuardian::Client::HgServicePlugin::DecryptWithKeyProtector(this, &v11, &v10, &v9);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)(unsigned int)v7,
      v9);
  if ( (_DWORD)v9 )
    v6 = *((_QWORD *)&v9 + 1) == 0;
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x8000FFFFLL,
      v9);
  v11 = v9;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(
    (__int64)retaddr,
    (unsigned int *)&v11,
    v8,
    (__int64)a4);
  if ( (_DWORD)v9 )
  {
    if ( *((_QWORD *)&v9 + 1) )
      Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(this, (struct HgBlob *)&v9);
  }
}

```

## disassembly

```asm
0x18000d0b8  push    rbp
0x18000d0ba  push    rbx
0x18000d0bb  push    rsi
0x18000d0bc  push    rdi
0x18000d0bd  mov     rbp, rsp
0x18000d0c0  sub     rsp, 78h
0x18000d0c4  mov     rsi, r9
0x18000d0c7  mov     rdi, rcx
0x18000d0ca  xorps   xmm0, xmm0
0x18000d0cd  movups  [rbp+var_58], xmm0
0x18000d0d1  lea     rax, [rbp+var_58]
0x18000d0d5  mov     [rbp+var_28], rax
0x18000d0d9  mov     [rbp+var_20], rcx
0x18000d0dd  mov     bl, 1
0x18000d0df  mov     [rbp+var_18], bl
0x18000d0e2  movups  xmm0, xmmword ptr [r8]
0x18000d0e6  movdqu  [rbp+var_48], xmm0
0x18000d0eb  movups  xmm1, xmmword ptr [rdx]
0x18000d0ee  movdqu  [rbp+var_38], xmm1
0x18000d0f3  lea     r9, [rbp+var_58]
0x18000d0f7  lea     r8, [rbp+var_48]
0x18000d0fb  lea     rdx, [rbp+var_38]
0x18000d0ff  call    ?DecryptWithKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@0PEAU5@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::DecryptWithKeyProtector(HgBlob,HgBlob,HgBlob *)
0x18000d104  mov     rcx, [rbp+20h]; this
0x18000d108  test    eax, eax
0x18000d10a  js      short loc_18000D174
0x18000d10c  cmp     dword ptr [rbp+var_58], 0
0x18000d110  jbe     short loc_18000D11B
0x18000d112  cmp     qword ptr [rbp+var_58+8], 0
0x18000d117  jz      short loc_18000D11B
0x18000d119  xor     bl, bl
0x18000d11b  mov     rcx, [rbp+20h]; this
0x18000d11f  test    bl, bl
0x18000d121  jnz     short loc_18000D15C
0x18000d123  movaps  xmm0, [rbp+var_58]
0x18000d127  movdqa  [rbp+var_38], xmm0
0x18000d12c  mov     r9, rsi
0x18000d12f  lea     rdx, [rbp+var_38]
0x18000d133  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000d138  nop
0x18000d139  cmp     dword ptr [rbp+var_58], 0
0x18000d13d  jbe     short loc_18000D153
0x18000d13f  cmp     qword ptr [rbp+var_58+8], 0
0x18000d144  jz      short loc_18000D153
0x18000d146  lea     rdx, [rbp+var_58]; struct HgBlob *
0x18000d14a  mov     rcx, rdi; this
0x18000d14d  call    ?FreeBlobData@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(HgBlob &)
0x18000d152  nop
0x18000d153  add     rsp, 78h
0x18000d157  pop     rdi
0x18000d158  pop     rsi
0x18000d159  pop     rbx
0x18000d15a  pop     rbp
0x18000d15b  retn
0x18000d15c  mov     r9d, 8000FFFFh; char *
0x18000d162  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d169  mov     edx, 156h; void *
0x18000d16e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d174  mov     r9d, eax; char *
0x18000d177  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d17e  mov     edx, 155h; void *
0x18000d183  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
