# Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(HgBlob,bool,HgBlob *)

- ea: `0x18000cfcc`
- end: `0x18000d0b0`
- name: `?CloneBlobForCOM@HgServiceController@Client@HostGuardian@Microsoft@@AEAAXUHgBlob@@_NPEAU5@@Z`
- size: `228`
- prototype: `bool __fastcall(__int64, unsigned int *, __int64, __int64)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ca70`
- `0x18000cdbc`
- `0x18000d0b8`
- `0x18000d190`
- `0x18000d348`
- `0x18000e100`

## callees

- `0x18000217a`
- `0x1800021f0`
- `0x180002e49`
- `0x180008760`
- `0x180008780`
- `0x18000cfcc`
- `0x18000e024`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d029`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cfed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cfed`

## string_xrefs

- `0x18000d05f`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000d081`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`
- `0x18000d09e`: `servercommon\base\securehostingservice\common\service\lib\hgservicecontroller.cpp`

## pseudocode

```c
bool __fastcall Microsoft::HostGuardian::Client::HgServiceController::CloneBlobForCOM(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4)
{
  SIZE_T v6; // rdi
  void *v7; // rax
  const char *v8; // r9
  void *v9; // rbx
  int v10; // esi
  const void *v11; // rdx
  bool result; // al
  int v13; // [rsp+20h] [rbp-48h]
  char *v14; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      (const char *)0x80004003LL,
      v13);
  v6 = *a2;
  v7 = CoTaskMemAlloc(v6);
  v9 = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2AB,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
      v8);
  if ( v6 )
  {
    v11 = (const void *)*((_QWORD *)a2 + 1);
    if ( !v11 )
    {
      memset_0(v7, 0, v6);
      v10 = 22;
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      goto LABEL_8;
    }
    memcpy_0(v7, v11, v6);
  }
  v10 = 0;
LABEL_8:
  LODWORD(v14) = v10;
  LOBYTE(v13) = v10 != 0;
  result = wil::details::in1diag3::Throw_HrIfMsg(
             retaddr,
             (void *)0x2AD,
             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservicecontroller.cpp",
             (const char *)0x80004005LL,
             v13,
             (bool)"Failed to call memcpy_s. Error:%d",
             v14);
  *(_DWORD *)a4 = v6;
  *(_QWORD *)(a4 + 8) = v9;
  return result;
}

```

## disassembly

```asm
0x18000cfcc  mov     [rsp+arg_0], rcx
0x18000cfd1  push    rbx
0x18000cfd2  push    rsi
0x18000cfd3  push    rdi
0x18000cfd4  push    r14
0x18000cfd6  sub     rsp, 48h
0x18000cfda  mov     r14, r9
0x18000cfdd  mov     rsi, rdx
0x18000cfe0  test    r9, r9
0x18000cfe3  jz      loc_18000D093
0x18000cfe9  mov     edi, [rdx]
0x18000cfeb  mov     ecx, edi; cb
0x18000cfed  call    cs:__imp_CoTaskMemAlloc
0x18000cff3  mov     rbx, rax
0x18000cff6  mov     [rsp+68h+arg_0], rax
0x18000cffb  mov     rcx, [rsp+68h]; this
0x18000d000  test    rax, rax
0x18000d003  jz      short loc_18000D081
0x18000d005  test    rdi, rdi
0x18000d008  jnz     short loc_18000D00E
0x18000d00a  xor     esi, esi
0x18000d00c  jmp     short loc_18000D03B
0x18000d00e  mov     rdx, [rsi+8]; Val
0x18000d012  mov     r8, rdi; Size
0x18000d015  mov     rcx, rbx; void *
0x18000d018  test    rdx, rdx
0x18000d01b  jz      short loc_18000D024
0x18000d01d  call    memcpy_0
0x18000d022  jmp     short loc_18000D00A
0x18000d024  call    memset_0
0x18000d029  call    cs:__imp__o__errno
0x18000d02f  mov     esi, 16h
0x18000d034  mov     [rax], esi
0x18000d036  call    _invalid_parameter_noinfo
0x18000d03b  test    esi, esi
0x18000d03d  setnz   al
0x18000d040  mov     rcx, [rsp+68h]; this
0x18000d045  mov     dword ptr [rsp+68h+var_38], esi; char *
0x18000d049  lea     rdx, aFailedToCallMe; "Failed to call memcpy_s. Error:%d"
0x18000d050  mov     qword ptr [rsp+68h+var_40], rdx; bool
0x18000d055  mov     byte ptr [rsp+68h+var_48], al; int
0x18000d059  mov     r9d, 80004005h; char *
0x18000d05f  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d066  mov     edx, 2ADh; void *
0x18000d06b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000d070  mov     [r14], edi
0x18000d073  mov     [r14+8], rbx
0x18000d077  add     rsp, 48h
0x18000d07b  pop     r14
0x18000d07d  pop     rdi
0x18000d07e  pop     rsi
0x18000d07f  pop     rbx
0x18000d080  retn
0x18000d081  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d088  mov     edx, 2ABh; void *
0x18000d08d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000d093  mov     rcx, [rsp+68h]; this
0x18000d098  mov     r9d, 80004003h; char *
0x18000d09e  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000d0a5  mov     edx, 2A4h; void *
0x18000d0aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
