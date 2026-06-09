# Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap::operator()(ushort const *,ushort const *,ushort const *)

- ea: `0x1800af3a0`
- end: `0x1800af52e`
- name: `??RCResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@UEAAJPEBG00@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000892c`
- `0x18002c8d0`
- `0x18004db40`
- `0x180058c84`
- `0x180076230`
- `0x1800ae2f4`
- `0x1800af000`
- `0x1800af3a0`
- `0x1800b2e5c`
- `0x1800b2f94`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af4a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af4a0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800af4ba`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800af4ba`

## string_xrefs

- `0x1800af412`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x1800af4eb`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap::operator()(
        __int64 a1,
        const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rdi
  int v5; // eax
  int v6; // ebx
  const unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // rsi
  __int64 *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  int v13; // [rsp+20h] [rbp-39h]
  __int64 v14; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int64 v16; // [rsp+40h] [rbp-19h]
  __int64 v17; // [rsp+48h] [rbp-11h]
  char v18; // [rsp+50h] [rbp-9h]
  _QWORD v19[4]; // [rsp+58h] [rbp-1h] BYREF
  char v20; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v22; // [rsp+C8h] [rbp+6Fh] BYREF

  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(&v15, v4);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D5,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)(unsigned int)v5,
        v13);
      goto LABEL_15;
    }
    v7 = a2;
    v8 = v15;
    StringCchCopyNW(v15, v4 + 1, v7, v4);
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15);
    v4 = v16;
    v8 = v15;
  }
  v22 = a1 - 80;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v22);
  v19[0] = a1 - 80;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(v19);
  v19[2] = v4;
  v19[3] = v17;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  v19[1] = v8;
  v20 = 0;
  v18 = 1;
  v9 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_a0cf4949a1781e239ca7960bc40d95f7_____lambda_a0cf4949a1781e239ca7960bc40d95f7___(
                    &v14,
                    v19);
  v10 = *v9;
  *v9 = 0;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  lambda_a0cf4949a1781e239ca7960bc40d95f7_::__lambda_a0cf4949a1781e239ca7960bc40d95f7_(v19);
  if ( v6 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E6,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v6,
      v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
  }
LABEL_15:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800af3a0  push    rbp
0x1800af3a2  push    rbx
0x1800af3a3  push    rsi
0x1800af3a4  push    rdi
0x1800af3a5  push    r14
0x1800af3a7  push    r15
0x1800af3a9  lea     rbp, [rsp-2Fh]
0x1800af3ae  sub     rsp, 88h
0x1800af3b5  mov     rsi, rdx
0x1800af3b8  mov     r14, rcx
0x1800af3bb  xor     r15d, r15d
0x1800af3be  mov     [rbp+57h+var_78], r15
0x1800af3c2  mov     [rbp+57h+var_70], r15
0x1800af3c6  mov     [rbp+57h+var_68], r15
0x1800af3ca  mov     [rbp+57h+var_60], r15b
0x1800af3ce  test    rdx, rdx
0x1800af3d1  jz      short loc_1800AF428
0x1800af3d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800af3d7  inc     rdi
0x1800af3da  cmp     [rdx+rdi*2], r15w
0x1800af3df  jnz     short loc_1800AF3D7
0x1800af3e1  mov     rdx, rdi
0x1800af3e4  lea     rcx, [rbp+57h+var_78]
0x1800af3e8  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800af3ed  mov     ebx, eax
0x1800af3ef  test    eax, eax
0x1800af3f1  js      short loc_1800AF40B
0x1800af3f3  lea     rdx, [rdi+1]; unsigned __int64
0x1800af3f7  mov     r9, rdi; unsigned __int64
0x1800af3fa  mov     r8, rsi; unsigned __int16 *
0x1800af3fd  mov     rsi, [rbp+57h+var_78]
0x1800af401  mov     rcx, rsi; unsigned __int16 *
0x1800af404  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800af409  jmp     short loc_1800AF439
0x1800af40b  mov     rcx, [rbp+5Fh]; this
0x1800af40f  mov     r9d, eax; char *
0x1800af412  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800af419  mov     edx, 4D5h; void *
0x1800af41e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af423  jmp     loc_1800AF513
0x1800af428  lea     rcx, [rbp+57h+var_78]
0x1800af42c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800af431  mov     rdi, [rbp+57h+var_70]
0x1800af435  mov     rsi, [rbp+57h+var_78]
0x1800af439  lea     rbx, [r14-50h]
0x1800af43d  mov     [rbp+57h+arg_8], rbx
0x1800af441  lea     rcx, [rbp+57h+arg_8]
0x1800af445  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800af44a  mov     [rbp+57h+var_58], rbx
0x1800af44e  lea     rcx, [rbp+57h+var_58]
0x1800af452  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800af457  mov     [rbp+57h+var_48], rdi
0x1800af45b  mov     rax, [rbp+57h+var_68]
0x1800af45f  mov     [rbp+57h+var_40], rax
0x1800af463  mov     [rbp+57h+var_78], r15
0x1800af467  mov     [rbp+57h+var_68], r15
0x1800af46b  mov     [rbp+57h+var_70], r15
0x1800af46f  mov     [rbp+57h+var_50], rsi
0x1800af473  mov     [rbp+57h+var_38], r15b
0x1800af477  mov     [rbp+57h+var_60], 1
0x1800af47b  lea     rdx, [rbp+57h+var_58]
0x1800af47f  lea     rcx, [rbp+57h+var_80]
0x1800af483  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_a0cf4949a1781e239ca7960bc40d95f7_____lambda_a0cf4949a1781e239ca7960bc40d95f7___
0x1800af488  mov     rdi, [rax]
0x1800af48b  mov     [rax], r15
0x1800af48e  mov     rcx, [rbp+57h+var_80]
0x1800af492  test    rcx, rcx
0x1800af495  jz      short loc_1800AF4A0
0x1800af497  mov     [rbp+57h+var_80], r15
0x1800af49b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800af4a0  call    cs:__imp_GetCurrentThreadId
0x1800af4a6  mov     [rsp+0B0h+var_88], r15
0x1800af4ab  mov     qword ptr [rsp+0B0h+var_90], rdi; int
0x1800af4b0  xor     r9d, r9d
0x1800af4b3  mov     r8d, eax
0x1800af4b6  xor     edx, edx
0x1800af4b8  xor     ecx, ecx
0x1800af4ba  call    cs:__imp_SHTaskPoolQueueTask
0x1800af4c0  mov     ebx, eax
0x1800af4c2  test    rdi, rdi
0x1800af4c5  jz      short loc_1800AF4D7
0x1800af4c7  mov     rdx, [rdi]
0x1800af4ca  mov     rcx, rdi
0x1800af4cd  mov     rax, [rdx+10h]
0x1800af4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4d6  nop
0x1800af4d7  lea     rcx, [rbp+57h+var_58]
0x1800af4db  call    _lambda_a0cf4949a1781e239ca7960bc40d95f7_____lambda_a0cf4949a1781e239ca7960bc40d95f7_
0x1800af4e0  test    ebx, ebx
0x1800af4e2  jns     short loc_1800AF507
0x1800af4e4  mov     rcx, [rbp+5Fh]; this
0x1800af4e8  mov     r9d, ebx; char *
0x1800af4eb  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800af4f2  mov     edx, 4E6h; void *
0x1800af4f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af4fc  lea     rcx, [rbp+57h+arg_8]
0x1800af500  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800af505  jmp     short loc_1800AF513
0x1800af507  lea     rcx, [rbp+57h+arg_8]
0x1800af50b  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800af510  mov     ebx, r15d
0x1800af513  lea     rcx, [rbp+57h+var_78]
0x1800af517  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800af51c  mov     eax, ebx
0x1800af51e  add     rsp, 88h
0x1800af525  pop     r15
0x1800af527  pop     r14
0x1800af529  pop     rdi
0x1800af52a  pop     rsi
0x1800af52b  pop     rbx
0x1800af52c  pop     rbp
0x1800af52d  retn
```
