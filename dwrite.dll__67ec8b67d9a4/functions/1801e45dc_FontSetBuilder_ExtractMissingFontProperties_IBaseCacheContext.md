# FontSetBuilder::ExtractMissingFontProperties(IBaseCacheContext *)

- ea: `0x1801e45dc`
- end: `0x1801e4833`
- name: `?ExtractMissingFontProperties@FontSetBuilder@@QEAAXPEAUIBaseCacheContext@@@Z`
- size: `599`
- prototype: `void __fastcall(FontSetBuilder *__hidden this, struct IBaseCacheContext *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801e453c`

## callees

- `0x18011ed18`
- `0x18011ee34`
- `0x18011f978`
- `0x18012104c`
- `0x180131390`
- `0x180141df0`
- `0x18014d27c`
- `0x180152858`
- `0x180154068`
- `0x1801644d0`
- `0x1801e45dc`
- `0x180212490`
- `0x18021e1da`
- `0x18023737c`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1801e4807`
- `ntdll!NtSetInformationThread` at `0x1801e4807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801e47ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801e47ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall FontSetBuilder::ExtractMissingFontProperties(FontSetBuilder *this, struct IBaseCacheContext *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rax
  HANDLE CurrentThread; // rax
  char v10; // [rsp+30h] [rbp-128h]
  __int64 ThreadInformation; // [rsp+38h] [rbp-120h] BYREF
  __int64 v12; // [rsp+40h] [rbp-118h]
  __int64 v13; // [rsp+48h] [rbp-110h] BYREF
  int v14; // [rsp+50h] [rbp-108h] BYREF
  __int64 v15; // [rsp+58h] [rbp-100h] BYREF
  struct DWrite::RefString::Data *v16; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v17; // [rsp+68h] [rbp-F0h]
  struct IBaseCacheContext *v18; // [rsp+70h] [rbp-E8h]
  FontSetBuilder *v19; // [rsp+78h] [rbp-E0h]
  _QWORD v20[3]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v21[8]; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v23[144]; // [rsp+B0h] [rbp-A8h] BYREF

  v19 = this;
  v18 = a2;
  LowMemoryPriority::LowMemoryPriority((LowMemoryPriority *)&v14);
  v10 = 0;
  v3 = 0;
  v12 = 0;
  v13 = 0;
  v4 = *((_QWORD *)this + 3);
  v17 = *((_QWORD *)this + 4);
  while ( 1 )
  {
    ThreadInformation = v4;
    if ( v4 == v17 )
      break;
    if ( *(_DWORD *)(v4 + 172) < *(_DWORD *)(v4 + 168) )
    {
      try
      {
        if ( v3
          && *(_QWORD *)v4 == *(_QWORD *)v3
          && (v5 = *(_DWORD *)(v4 + 12), v5 == *(_DWORD *)(v3 + 12))
          && !memcmp_0(*(const void **)(v4 + 24), *(const void **)(v3 + 24), v5) )
        {
          v6 = v13;
        }
        else
        {
          v6 = 0;
        }
        FontFaceElementKeyBase::FontFaceElementKeyBase(v20, v4, v6, 2);
        v20[0] = &FontFaceElementKey::`vftable';
        FontFaceLight::FontFaceLight((FontFaceLight *)v23, v18, (const struct FontFaceElementKey *)v20);
        v7 = v22;
        v15 = v22;
        ComPtr<IDWriteFontFaceReference>::AddRef(&v15);
        v8 = v13;
        v13 = v7;
        v15 = v8;
        ComPtr<IDWriteFontFamily>::Deref(&v15);
        v3 = v4;
        v12 = v4;
        v16 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
        FontSetBuilder::AddFontInformation(v19, v4, v23, 0, &v16);
        DWrite::RefString::DecrementRef(v16);
        FontFaceLight::~FontFaceLight((FontFaceLight *)v23);
        ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(&v22);
        ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(v21);
      }
      catch ( RemoteFontException )
      {
        v10 = 1;
        v4 = ThreadInformation;
        v3 = v12;
      }
      catch ( PageableException )
      {
        v4 = ThreadInformation;
        v3 = v12;
      }
      catch ( FileFormatException )
      {
        v4 = ThreadInformation;
        v3 = v12;
      }
      catch ( CallbackException )
      {
        v4 = ThreadInformation;
        v3 = v12;
      }
    }
    v4 += 200;
  }
  if ( v10 )
  {
    Exception::Exception((Exception *)v20, -2003283955, 0);
    v20[1] = 0;
    v20[2] = 0;
    LogAndThrow<RemoteFontException>(v20, 0x646C6274657366LL, 500);
  }
  ComPtr<IDWriteFontFamily>::Deref(&v13);
  if ( v14 )
  {
    LODWORD(ThreadInformation) = v14;
    CurrentThread = GetCurrentThread();
    NtSetInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u);
  }
}

```

## disassembly

```asm
0x1801e45dc  mov     [rsp+arg_10], rbx
0x1801e45e1  mov     [rsp+arg_18], rsi
0x1801e45e6  push    rdi
0x1801e45e7  sub     rsp, 150h
0x1801e45ee  mov     rax, cs:__security_cookie
0x1801e45f5  xor     rax, rsp
0x1801e45f8  mov     [rsp+158h+var_18], rax
0x1801e4600  mov     rbx, rcx
0x1801e4603  mov     [rsp+158h+var_E0], rcx
0x1801e4608  mov     [rsp+158h+var_E8], rdx
0x1801e460d  lea     rcx, [rsp+158h+var_108]; this
0x1801e4612  call    ??0LowMemoryPriority@@QEAA@XZ; LowMemoryPriority::LowMemoryPriority(void)
0x1801e4617  nop
0x1801e4618  mov     [rsp+158h+var_128], 0
0x1801e461d  xor     esi, esi
0x1801e461f  mov     [rsp+158h+var_118], rsi
0x1801e4624  mov     [rsp+158h+var_110], rsi
0x1801e4629  mov     rdi, [rbx+18h]
0x1801e462d  mov     rax, [rbx+20h]
0x1801e4631  mov     [rsp+158h+var_F0], rax
0x1801e4636  mov     [rsp+158h+ThreadInformation], rdi
0x1801e463b  cmp     rdi, [rsp+158h+var_F0]
0x1801e4640  jz      loc_1801E4786
0x1801e4646  mov     eax, [rdi+0A8h]
0x1801e464c  cmp     [rdi+0ACh], eax
0x1801e4652  jnb     loc_1801E477A
0x1801e4658  test    rsi, rsi
0x1801e465b  jz      short loc_1801E4688
0x1801e465d  mov     rax, [rsi]
0x1801e4660  cmp     [rdi], rax
0x1801e4663  jnz     short loc_1801E4688
0x1801e4665  mov     eax, [rdi+0Ch]
0x1801e4668  cmp     eax, [rsi+0Ch]
0x1801e466b  jnz     short loc_1801E4688
0x1801e466d  mov     r8d, eax; Size
0x1801e4670  mov     rdx, [rsi+18h]; Buf2
0x1801e4674  mov     rcx, [rdi+18h]; Buf1
0x1801e4678  call    memcmp_0
0x1801e467d  test    eax, eax
0x1801e467f  jnz     short loc_1801E4688
0x1801e4681  mov     r8, [rsp+158h+var_110]
0x1801e4686  jmp     short loc_1801E468B
0x1801e4688  xor     r8d, r8d
0x1801e468b  mov     r9d, 2
0x1801e4691  mov     rdx, rdi
0x1801e4694  lea     rcx, [rsp+158h+var_D8]
0x1801e469c  call    ??0FontFaceElementKeyBase@@QEAA@AEBVFontFaceKey@@PEAUIDWriteFontFileStream@@W4CacheElementType@@@Z; FontFaceElementKeyBase::FontFaceElementKeyBase(FontFaceKey const &,IDWriteFontFileStream *,CacheElementType)
0x1801e46a1  lea     rax, ??_7FontFaceElementKey@@6B@; const FontFaceElementKey::`vftable'
0x1801e46a8  mov     [rsp+158h+var_D8], rax
0x1801e46b0  lea     r8, [rsp+158h+var_D8]; struct FontFaceElementKey *
0x1801e46b8  mov     rdx, [rsp+158h+var_E8]; struct IBaseCacheContext *
0x1801e46bd  lea     rcx, [rsp+158h+var_A8]; this
0x1801e46c5  call    ??0FontFaceLight@@QEAA@PEAUIBaseCacheContext@@AEBVFontFaceElementKey@@@Z; FontFaceLight::FontFaceLight(IBaseCacheContext *,FontFaceElementKey const &)
0x1801e46ca  nop
0x1801e46cb  mov     rbx, [rsp+158h+var_B8]
0x1801e46d3  mov     [rsp+158h+var_100], rbx
0x1801e46d8  lea     rcx, [rsp+158h+var_100]
0x1801e46dd  call    ?AddRef@?$ComPtr@UIDWriteFontFaceReference@@@@AEBAXXZ; ComPtr<IDWriteFontFaceReference>::AddRef(void)
0x1801e46e2  nop
0x1801e46e3  mov     rax, [rsp+158h+var_110]
0x1801e46e8  mov     [rsp+158h+var_110], rbx
0x1801e46ed  mov     [rsp+158h+var_100], rax
0x1801e46f2  lea     rcx, [rsp+158h+var_100]
0x1801e46f7  call    ?Deref@?$ComPtr@UIDWriteFontFamily@@@@AEAAXXZ; ComPtr<IDWriteFontFamily>::Deref(void)
0x1801e46fc  nop
0x1801e46fd  mov     rsi, rdi
0x1801e4700  mov     [rsp+158h+var_118], rdi
0x1801e4705  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1801e470c  mov     [rsp+158h+var_F8], rax
0x1801e4711  lea     rax, [rsp+158h+var_F8]
0x1801e4716  mov     [rsp+158h+var_138], rax
0x1801e471b  xor     r9d, r9d
0x1801e471e  lea     r8, [rsp+158h+var_A8]
0x1801e4726  mov     rdx, rdi
0x1801e4729  mov     rcx, [rsp+158h+var_E0]
0x1801e472e  call    ?AddFontInformation@FontSetBuilder@@IEAAXAEAUFontEntryWithProperties@1@AEBVFontFaceLight@@W4DWRITE_FONT_SOURCE_TYPE@@AEBVRefString@DWrite@@@Z; FontSetBuilder::AddFontInformation(FontSetBuilder::FontEntryWithProperties &,FontFaceLight const &,DWRITE_FONT_SOURCE_TYPE,DWrite::RefString const &)
0x1801e4733  nop
0x1801e4734  mov     rcx, [rsp+158h+var_F8]; struct DWrite::RefString::Data *
0x1801e4739  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801e473e  nop
0x1801e473f  lea     rcx, [rsp+158h+var_A8]; this
0x1801e4747  call    ??1FontFaceLight@@QEAA@XZ; FontFaceLight::~FontFaceLight(void)
0x1801e474c  nop
0x1801e474d  lea     rcx, [rsp+158h+var_B8]
0x1801e4755  call    ??1?$ComPtr@VClientSideRemoteFileStream@@@@QEAA@XZ; ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(void)
0x1801e475a  lea     rcx, [rsp+158h+var_C0]
0x1801e4762  call    ??1?$ComPtr@VClientSideRemoteFileStream@@@@QEAA@XZ; ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(void)
0x1801e4767  nop
0x1801e4768  jmp     short loc_1801E477A
0x1801e476a  jmp     short loc_1801E4770
0x1801e476c  jmp     short loc_1801E4770
0x1801e476e  jmp     short $+2
0x1801e4770  mov     rdi, [rsp+158h+ThreadInformation]
0x1801e4775  mov     rsi, [rsp+158h+var_118]
0x1801e477a  add     rdi, 0C8h
0x1801e4781  jmp     loc_1801E4636
0x1801e4786  cmp     [rsp+158h+var_128], 0
0x1801e478b  jz      short loc_1801E47D8
0x1801e478d  xor     r8d, r8d; unsigned int
0x1801e4790  mov     edx, 8898500Dh; int
0x1801e4795  lea     rcx, [rsp+158h+var_D8]; this
0x1801e479d  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1801e47a2  mov     [rsp+158h+var_D0], 0
0x1801e47ae  mov     [rsp+158h+var_C8], 0
0x1801e47ba  mov     rdx, 646C6274657366h
0x1801e47c4  mov     r8d, 1F4h
0x1801e47ca  lea     rcx, [rsp+158h+var_D8]
0x1801e47d2  call    ??$LogAndThrow@VRemoteFontException@@@@YAXAEBVRemoteFontException@@VEventTag@@I@Z; LogAndThrow<RemoteFontException>(RemoteFontException const &,EventTag,uint)
0x1801e47d8  lea     rcx, [rsp+158h+var_110]
0x1801e47dd  call    ?Deref@?$ComPtr@UIDWriteFontFamily@@@@AEAAXXZ; ComPtr<IDWriteFontFamily>::Deref(void)
0x1801e47e2  nop
0x1801e47e3  mov     eax, [rsp+158h+var_108]
0x1801e47e7  test    eax, eax
0x1801e47e9  jz      short loc_1801E480E
0x1801e47eb  mov     dword ptr [rsp+158h+ThreadInformation], eax
0x1801e47ef  call    cs:__imp_GetCurrentThread
0x1801e47f5  mov     rcx, rax; ThreadHandle
0x1801e47f8  mov     r9d, 4; ThreadInformationLength
0x1801e47fe  lea     r8, [rsp+158h+ThreadInformation]; ThreadInformation
0x1801e4803  lea     edx, [r9+14h]; ThreadInformationClass
0x1801e4807  call    cs:__imp_NtSetInformationThread
0x1801e480d  nop
0x1801e480e  mov     rcx, [rsp+158h+var_18]
0x1801e4816  xor     rcx, rsp; StackCookie
0x1801e4819  call    __security_check_cookie
0x1801e481e  lea     r11, [rsp+158h+var_8]
0x1801e4826  mov     rbx, [r11+20h]
0x1801e482a  mov     rsi, [r11+28h]
0x1801e482e  mov     rsp, r11
0x1801e4831  pop     rdi
0x1801e4832  retn
```
