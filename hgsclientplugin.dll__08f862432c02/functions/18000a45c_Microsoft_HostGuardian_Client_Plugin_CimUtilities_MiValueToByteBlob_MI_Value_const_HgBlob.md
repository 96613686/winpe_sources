# Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(_MI_Value const &,HgBlob &)

- ea: `0x18000a45c`
- end: `0x18000a54a`
- name: `?MiValueToByteBlob@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJAEBT_MI_Value@@AEAUHgBlob@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::Plugin::CimUtilities *__hidden this, const union _MI_Value *, struct HgBlob *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`

## callees

- `0x180001f56`
- `0x180001f9e`
- `0x1800049f4`
- `0x1800082a8`
- `0x18000a45c`
- `0x18000a8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a4db`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a4db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a47f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a47f`

## string_xrefs

- `0x18000a4fd`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a52d`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::MiValueToByteBlob(
        Microsoft::HostGuardian::Client::Plugin::CimUtilities *this,
        const union _MI_Value *a2,
        struct HgBlob *a3)
{
  SIZE_T v5; // r14
  _BYTE *v6; // rax
  void *v7; // rbx
  _BYTE *i; // rcx
  MI_Uint32 v9; // eax
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-38h]
  char *v13; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*((_DWORD *)this + 2) || !*(_QWORD *)this )
    return 0;
  v5 = *((unsigned int *)this + 2);
  v6 = CoTaskMemAlloc(v5);
  v7 = v6;
  if ( v6 )
  {
    for ( i = &v6[v5]; v6 != i; ++v6 )
      *v6 = 0;
    v9 = *((_DWORD *)this + 2);
    if ( !v9 )
      goto LABEL_9;
    if ( *(_QWORD *)this )
    {
      memcpy_0(v7, *(const void **)this, v9);
      v9 = *((_DWORD *)this + 2);
LABEL_9:
      a2->uint32 = v9;
      *(&a2->uint64 + 1) = (MI_Uint64)v7;
      return 0;
    }
    memset_0(v7, 0, v9);
    *(_DWORD *)_o__errno(v11) = 22;
    invalid_parameter_noinfo();
    LODWORD(v13) = 22;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xCD,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)0x80004005LL,
      (int)"Failed to call memcpy_s. Error:%d",
      v13);
    CoTaskMemFree(v7);
    return 2147500037LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)0x8007000ELL,
      v12);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000a45c  push    rbx
0x18000a45e  push    rsi
0x18000a45f  push    rdi
0x18000a460  push    r14
0x18000a462  sub     rsp, 38h
0x18000a466  cmp     dword ptr [rcx+8], 0
0x18000a46a  mov     rsi, rdx
0x18000a46d  mov     rdi, rcx
0x18000a470  jz      short loc_18000A4CA
0x18000a472  cmp     qword ptr [rcx], 0
0x18000a476  jz      short loc_18000A4CA
0x18000a478  mov     r14d, [rcx+8]
0x18000a47c  mov     ecx, r14d; cb
0x18000a47f  call    cs:__imp_CoTaskMemAlloc
0x18000a485  mov     rbx, rax
0x18000a488  test    rax, rax
0x18000a48b  jz      loc_18000A528
0x18000a491  lea     rcx, [r14+rax]
0x18000a495  cmp     rax, rcx
0x18000a498  jz      short loc_18000A4A6
0x18000a49a  xor     edx, edx
0x18000a49c  mov     [rax], dl
0x18000a49e  inc     rax
0x18000a4a1  cmp     rax, rcx
0x18000a4a4  jnz     short loc_18000A49A
0x18000a4a6  mov     eax, [rdi+8]
0x18000a4a9  test    rax, rax
0x18000a4ac  jz      short loc_18000A4C4
0x18000a4ae  mov     rdx, [rdi]; Src
0x18000a4b1  mov     r8d, eax; Size
0x18000a4b4  mov     rcx, rbx; void *
0x18000a4b7  test    rdx, rdx
0x18000a4ba  jz      short loc_18000A4D6
0x18000a4bc  call    memcpy_0
0x18000a4c1  mov     eax, [rdi+8]
0x18000a4c4  mov     [rsi], eax
0x18000a4c6  mov     [rsi+8], rbx
0x18000a4ca  xor     eax, eax
0x18000a4cc  add     rsp, 38h
0x18000a4d0  pop     r14
0x18000a4d2  pop     rdi
0x18000a4d3  pop     rsi
0x18000a4d4  pop     rbx
0x18000a4d5  retn
0x18000a4d6  call    memset_0
0x18000a4db  call    cs:__imp__o__errno
0x18000a4e1  mov     edi, 16h
0x18000a4e6  mov     [rax], edi
0x18000a4e8  call    _invalid_parameter_noinfo
0x18000a4ed  mov     rcx, [rsp+58h]; this
0x18000a4f2  lea     rax, aFailedToCallMe; "Failed to call memcpy_s. Error:%d"
0x18000a4f9  mov     dword ptr [rsp+58h+var_30], edi; char *
0x18000a4fd  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a504  mov     edi, 80004005h
0x18000a509  mov     qword ptr [rsp+58h+var_38], rax; int
0x18000a50e  mov     r9d, edi; char *
0x18000a511  mov     edx, 0CDh; void *
0x18000a516  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a51b  mov     rcx, rbx; pv
0x18000a51e  call    cs:__imp_CoTaskMemFree
0x18000a524  mov     eax, edi
0x18000a526  jmp     short loc_18000A4CC
0x18000a528  mov     rcx, [rsp+58h]; this
0x18000a52d  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a534  mov     ebx, 8007000Eh
0x18000a539  mov     edx, 0CAh; void *
0x18000a53e  mov     r9d, ebx; char *
0x18000a541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a546  mov     eax, ebx
0x18000a548  jmp     short loc_18000A4CC
```
