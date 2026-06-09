# Microsoft::HostGuardian::Client::HgServiceController::EncryptWithKeyProtector(HgBlob *,uint,HgBlob *,bool,HgBlob *,HgBlob *)

- ea: `0x18000d190`
- end: `0x18000d2dc`
- name: `?EncryptWithKeyProtector@HgServiceController@Client@HostGuardian@Microsoft@@QEAAXPEAUHgBlob@@I0_N00@Z`
- size: `332`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServiceController *this, struct HgBlob *, __int64, struct HgBlob *, bool, struct HgBlob *, struct HgBlob *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b020`

## callees

- `0x180008760`
- `0x18000cfcc`
- `0x18000d190`
- `0x180014114`
- `0x1800141f0`

## string_xrefs

- `0x18000d2b5`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000d2ca`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServiceController::EncryptWithKeyProtector(
        Microsoft::HostGuardian::Client::HgServiceController *this,
        struct HgBlob *a2,
        __int64 a3,
        struct HgBlob *a4,
        bool a5,
        struct HgBlob *a6,
        struct HgBlob *a7)
{
  bool v8; // bl
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  __int128 v13; // [rsp+48h] [rbp-21h] BYREF
  __int128 v14; // [rsp+58h] [rbp-11h] BYREF
  __int128 v15; // [rsp+68h] [rbp-1h] BYREF
  __int128 v16; // [rsp+78h] [rbp+Fh] BYREF
  __int128 *v17; // [rsp+88h] [rbp+1Fh]
  __int128 *v18; // [rsp+90h] [rbp+27h]
  Microsoft::HostGuardian::Client::HgServiceController *v19; // [rsp+98h] [rbp+2Fh]
  char v20; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+47h]

  v13 = 0;
  v14 = 0;
  v17 = &v13;
  v18 = &v14;
  v19 = this;
  v8 = 1;
  v20 = 1;
  v15 = *(_OWORD *)a4;
  v16 = *(_OWORD *)a2;
  v9 = Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector(this, &v16, a3, &v15);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)(unsigned int)v9,
      a5);
  if ( (_DWORD)v13 && *((_QWORD *)&v13 + 1) && (_DWORD)v14 )
    v8 = *((_QWORD *)&v14 + 1) == 0;
  if ( v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x8000FFFFLL,
      a5);
  v16 = v13;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(
    (__int64)retaddr,
    (unsigned int *)&v16,
    v10,
    (__int64)a6);
  v16 = v14;
  Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(v11, (unsigned int *)&v16, v12, (__int64)a7);
  if ( (_DWORD)v13 && *((_QWORD *)&v13 + 1) || (_DWORD)v14 && *((_QWORD *)&v14 + 1) )
  {
    Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(this, (struct HgBlob *)&v13);
    Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(this, (struct HgBlob *)&v14);
  }
}

```

## disassembly

```asm
0x18000d190  mov     r11, rsp
0x18000d193  mov     [r11+8], rbx
0x18000d197  mov     [r11+10h], rdi
0x18000d19b  push    rbp
0x18000d19c  lea     rbp, [r11-47h]
0x18000d1a0  sub     rsp, 0A0h
0x18000d1a7  mov     rdi, rcx
0x18000d1aa  xorps   xmm0, xmm0
0x18000d1ad  movups  [rbp+3Fh+var_60], xmm0
0x18000d1b1  xorps   xmm1, xmm1
0x18000d1b4  movups  [rbp+3Fh+var_50], xmm1
0x18000d1b8  lea     rax, [rbp+3Fh+var_60]
0x18000d1bc  mov     [rbp+3Fh+var_20], rax
0x18000d1c0  lea     rax, [rbp+3Fh+var_50]
0x18000d1c4  mov     [rbp+3Fh+var_18], rax
0x18000d1c8  mov     [rbp+3Fh+var_10], rcx
0x18000d1cc  mov     bl, 1
0x18000d1ce  mov     [rbp+3Fh+var_8], bl
0x18000d1d1  movups  xmm0, xmmword ptr [r9]
0x18000d1d5  movdqu  [rbp+3Fh+var_40], xmm0
0x18000d1da  movups  xmm1, xmmword ptr [rdx]
0x18000d1dd  movdqu  [rbp+3Fh+var_30], xmm1
0x18000d1e2  movzx   eax, [rbp+3Fh+arg_20]
0x18000d1e6  lea     rcx, [rbp+3Fh+var_50]
0x18000d1ea  mov     [r11-78h], rcx
0x18000d1ee  lea     rcx, [rbp+3Fh+var_60]
0x18000d1f2  mov     [r11-80h], rcx
0x18000d1f6  mov     [rsp+0A0h+var_80], eax; int
0x18000d1fa  lea     r9, [rbp+3Fh+var_40]
0x18000d1fe  lea     rdx, [rbp+3Fh+var_30]
0x18000d202  mov     rcx, rdi
0x18000d205  call    ?EncryptWithKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@I0HPEAU5@1@Z; Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector(HgBlob,uint,HgBlob,int,HgBlob *,HgBlob *)
0x18000d20a  mov     rcx, [rbp+47h]; this
0x18000d20e  test    eax, eax
0x18000d210  js      loc_18000D2C7
0x18000d216  cmp     dword ptr [rbp+3Fh+var_60], 0
0x18000d21a  jbe     short loc_18000D232
0x18000d21c  cmp     qword ptr [rbp+3Fh+var_60+8], 0
0x18000d221  jz      short loc_18000D232
0x18000d223  cmp     dword ptr [rbp+3Fh+var_50], 0
0x18000d227  jbe     short loc_18000D232
0x18000d229  cmp     qword ptr [rbp+3Fh+var_50+8], 0
0x18000d22e  jz      short loc_18000D232
0x18000d230  xor     bl, bl
0x18000d232  mov     rcx, [rbp+47h]; this
0x18000d236  test    bl, bl
0x18000d238  jnz     short loc_18000D2AF
0x18000d23a  movaps  xmm0, [rbp+3Fh+var_60]
0x18000d23e  movdqa  [rbp+3Fh+var_30], xmm0
0x18000d243  mov     r9, [rbp+3Fh+arg_28]
0x18000d247  lea     rdx, [rbp+3Fh+var_30]
0x18000d24b  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000d250  movaps  xmm0, [rbp+3Fh+var_50]
0x18000d254  movdqa  [rbp+3Fh+var_30], xmm0
0x18000d259  mov     r9, [rbp+3Fh+arg_30]
0x18000d25d  lea     rdx, [rbp+3Fh+var_30]
0x18000d261  call    ?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z; Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)
0x18000d266  nop
0x18000d267  cmp     dword ptr [rbp+3Fh+var_60], 0
0x18000d26b  jbe     short loc_18000D274
0x18000d26d  cmp     qword ptr [rbp+3Fh+var_60+8], 0
0x18000d272  jnz     short loc_18000D281
0x18000d274  cmp     dword ptr [rbp+3Fh+var_50], 0
0x18000d278  jbe     short loc_18000D29A
0x18000d27a  cmp     qword ptr [rbp+3Fh+var_50+8], 0
0x18000d27f  jz      short loc_18000D29A
0x18000d281  lea     rdx, [rbp+3Fh+var_60]; struct HgBlob *
0x18000d285  mov     rcx, rdi; this
0x18000d288  call    ?FreeBlobData@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(HgBlob &)
0x18000d28d  lea     rdx, [rbp+3Fh+var_50]; struct HgBlob *
0x18000d291  mov     rcx, rdi; this
0x18000d294  call    ?FreeBlobData@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJAEAUHgBlob@@@Z; Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(HgBlob &)
0x18000d299  nop
0x18000d29a  lea     r11, [rsp+0A0h+var_s0]
0x18000d2a2  mov     rbx, [r11+10h]
0x18000d2a6  mov     rdi, [r11+18h]
0x18000d2aa  mov     rsp, r11
0x18000d2ad  pop     rbp
0x18000d2ae  retn
0x18000d2af  mov     r9d, 8000FFFFh; char *
0x18000d2b5  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d2bc  mov     edx, 13Dh; void *
0x18000d2c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d2c7  mov     r9d, eax; char *
0x18000d2ca  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d2d1  mov     edx, 13Ch; void *
0x18000d2d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
