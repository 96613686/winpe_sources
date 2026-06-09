# CRemoteTask::RuntimeClassInitialize(Windows::Internal::IComPoolTask *)

- ea: `0x180032428`
- end: `0x180032547`
- name: `?RuntimeClassInitialize@CRemoteTask@@QEAAJPEAUIComPoolTask@Internal@Windows@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CRemoteTask *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030c60`

## callees

- `0x180001710`
- `0x18000c548`
- `0x18000f668`
- `0x180031dd0`
- `0x180032428`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800324fd`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800324fd`

## string_xrefs

- `0x18003248b`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteTask::RuntimeClassInitialize(CRemoteTask *this, struct Windows::Internal::IComPoolTask *a2)
{
  int *v3; // rax
  __int64 v4; // rcx
  int AgileReference; // ebx
  __int64 v6; // rdx
  __int64 *v8; // rbx
  __int64 v9; // rdi
  int v10[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v12; // [rsp+50h] [rbp+20h] BYREF
  struct Windows::Internal::IComPoolTask *v13; // [rsp+58h] [rbp+28h] BYREF
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF

  v13 = a2;
  v3 = (int *)Microsoft::WRL::Details::Make<CRemoteReleaseStub,Windows::Internal::IComPoolTask * &>(
                &v12,
                (__int64 *)&v13);
  v4 = 0;
  if ( v10 != v3 )
  {
    v4 = *(_QWORD *)v3;
    *(_QWORD *)v3 = 0;
  }
  *(_QWORD *)v10 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v4;
  Microsoft::WRL::ComPtr<CRemoteReleaseStub>::InternalRelease(v10);
  Microsoft::WRL::ComPtr<CRemoteReleaseStub>::InternalRelease(&v12);
  if ( !*((_QWORD *)this + 3) )
  {
    AgileReference = -2147024882;
    v6 = 1592;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)AgileReference,
      v10[0]);
    return (unsigned int)AgileReference;
  }
  v8 = (__int64 *)((char *)this + 16);
  v14 = 0;
  v12 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v14);
  v9 = (*((_QWORD *)this + 3) + 16LL) & -(__int64)(*((_QWORD *)this + 3) != 0);
  if ( v9 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v8);
    AgileReference = RoGetAgileReference(0, &GUID_00000000_0000_0000_c000_000000000046, v9, v8);
    if ( AgileReference < 0 )
    {
      v6 = 1593;
      goto LABEL_5;
    }
  }
  else
  {
    v14 = 0;
    v12 = *v8;
    *v8 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180032428  mov     [rsp-18h+arg_8], rdx
0x18003242d  push    rbp
0x18003242e  push    rbx
0x18003242f  push    rdi
0x180032430  mov     rbp, rsp
0x180032433  sub     rsp, 30h
0x180032437  mov     rdi, rcx
0x18003243a  lea     rdx, [rbp+arg_8]
0x18003243e  lea     rcx, [rbp+arg_0]
0x180032442  call    ??$Make@VCRemoteReleaseStub@@AEAPEAUIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCRemoteReleaseStub@@@12@AEAPEAUIComPoolTask@Internal@Windows@@@Z; Microsoft::WRL::Details::Make<CRemoteReleaseStub,Windows::Internal::IComPoolTask * &>(Windows::Internal::IComPoolTask * &)
0x180032447  xor     ecx, ecx
0x180032449  lea     rdx, [rbp+var_10]
0x18003244d  cmp     rdx, rax
0x180032450  jz      short loc_18003245C
0x180032452  mov     rcx, [rax]
0x180032455  mov     qword ptr [rax], 0
0x18003245c  mov     rax, [rdi+18h]
0x180032460  mov     qword ptr [rbp+var_10], rax
0x180032464  mov     [rdi+18h], rcx
0x180032468  lea     rcx, [rbp+var_10]
0x18003246c  call    ?InternalRelease@?$ComPtr@VCRemoteReleaseStub@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CRemoteReleaseStub>::InternalRelease(void)
0x180032471  lea     rcx, [rbp+arg_0]
0x180032475  call    ?InternalRelease@?$ComPtr@VCRemoteReleaseStub@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CRemoteReleaseStub>::InternalRelease(void)
0x18003247a  cmp     qword ptr [rdi+18h], 0
0x18003247f  jnz     short loc_1800324A5
0x180032481  mov     ebx, 8007000Eh
0x180032486  mov     edx, 638h; void *
0x18003248b  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180032492  mov     r9d, ebx; char *
0x180032495  mov     rcx, [rbp+18h]; this
0x180032499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003249e  mov     eax, ebx
0x1800324a0  jmp     loc_18003253F
0x1800324a5  lea     rbx, [rdi+10h]
0x1800324a9  mov     [rbp+arg_10], 0
0x1800324b1  mov     rax, [rbx]
0x1800324b4  mov     [rbp+arg_0], rax
0x1800324b8  mov     qword ptr [rbx], 0
0x1800324bf  lea     rcx, [rbp+arg_0]
0x1800324c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800324c8  nop
0x1800324c9  lea     rcx, [rbp+arg_10]
0x1800324cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800324d2  nop
0x1800324d3  mov     rax, [rdi+18h]
0x1800324d7  lea     rcx, [rax+10h]
0x1800324db  neg     rax
0x1800324de  sbb     rdi, rdi
0x1800324e1  and     rdi, rcx
0x1800324e4  jz      short loc_180032513
0x1800324e6  mov     rcx, rbx
0x1800324e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800324ee  mov     r9, rbx
0x1800324f1  mov     r8, rdi
0x1800324f4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800324fb  xor     ecx, ecx
0x1800324fd  call    cs:__imp_RoGetAgileReference
0x180032503  mov     ebx, eax
0x180032505  test    eax, eax
0x180032507  jns     short loc_18003253D
0x180032509  mov     edx, 639h
0x18003250e  jmp     loc_18003248B
0x180032513  mov     [rbp+arg_10], 0
0x18003251b  mov     rax, [rbx]
0x18003251e  mov     [rbp+arg_0], rax
0x180032522  mov     qword ptr [rbx], 0
0x180032529  lea     rcx, [rbp+arg_0]
0x18003252d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180032532  nop
0x180032533  lea     rcx, [rbp+arg_10]
0x180032537  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18003253c  nop
0x18003253d  xor     eax, eax
0x18003253f  add     rsp, 30h
0x180032543  pop     rdi
0x180032544  pop     rbx
0x180032545  pop     rbp
0x180032546  retn
```
