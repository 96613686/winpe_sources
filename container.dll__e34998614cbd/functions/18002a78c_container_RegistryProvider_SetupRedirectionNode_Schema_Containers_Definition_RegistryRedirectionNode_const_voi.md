# container::RegistryProvider::SetupRedirectionNode(Schema::Containers::Definition::RegistryRedirectionNode const &,void *,void *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x18002a78c`
- end: `0x18002abb8`
- name: `?SetupRedirectionNode@RegistryProvider@container@@YAXAEBURegistryRedirectionNode@Definition@Containers@Schema@@PEAX1AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180029a1c`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180004c40`
- `0x1800051b0`
- `0x18000b4bc`
- `0x180011fe8`
- `0x180012b10`
- `0x180012b30`
- `0x180021b68`
- `0x180022094`
- `0x180022b54`
- `0x1800278ac`
- `0x180027db0`
- `0x18002841c`
- `0x180028d8c`
- `0x18002a78c`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002a81d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aaf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aaf5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002aaa6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002aaa6`

## string_xrefs

- `0x18002a8d5`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002ab58`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002ab6a`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002ab7f`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002ab91`: `onecore\base\gendrv\silos\container\registry_provider.cpp`
- `0x18002aba6`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall container::RegistryProvider::SetupRedirectionNode(__int64 a1, __int64 a2, void *a3, __int64 *a4)
{
  __int64 v7; // r12
  wchar_t **v8; // rdi
  wchar_t **v9; // rdx
  wchar_t **v10; // r14
  wchar_t **v11; // rbx
  __int64 v12; // rdi
  const wchar_t *v13; // rdx
  size_t v14; // rbx
  size_t v15; // r14
  const wchar_t *v16; // rcx
  size_t v17; // r8
  int v18; // eax
  const char *v19; // rdx
  _QWORD *v20; // rdi
  _DWORD *v21; // rbx
  int v22; // eax
  int v23; // ecx
  unsigned __int64 v24; // rax
  unsigned __int16 v25; // cx
  unsigned int v26; // eax
  __int16 v27; // cx
  unsigned __int64 v28; // rax
  unsigned __int16 v29; // cx
  unsigned int v30; // eax
  __int16 v31; // cx
  _QWORD *v32; // rax
  __int64 v33; // rax
  unsigned __int64 v34; // rdx
  signed int LastError; // eax
  unsigned int v37; // ebx
  int lpOutBuffer; // [rsp+20h] [rbp-89h]
  int lpOutBuffera; // [rsp+20h] [rbp-89h]
  unsigned int lpOutBufferb; // [rsp+20h] [rbp-89h]
  int v41; // [rsp+40h] [rbp-69h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-65h] BYREF
  __int64 v43; // [rsp+48h] [rbp-61h] BYREF
  __int64 v44; // [rsp+50h] [rbp-59h] BYREF
  HANDLE hDevice; // [rsp+58h] [rbp-51h] BYREF
  __int128 v46; // [rsp+60h] [rbp-49h] BYREF
  __int64 v47; // [rsp+70h] [rbp-39h]
  LPVOID lpInBuffer; // [rsp+78h] [rbp-31h]
  DWORD nInBufferSize[2]; // [rsp+80h] [rbp-29h]
  char v50[16]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v51; // [rsp+98h] [rbp-11h]
  wchar_t *S1[2]; // [rsp+A0h] [rbp-9h] BYREF
  size_t N; // [rsp+B0h] [rbp+7h]
  unsigned __int64 v54; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hDevice = a3;
  v41 = 0;
  v7 = a1 + 64;
  if ( !*(_QWORD *)(a1 + 80) )
  {
    v20 = (_QWORD *)(a1 + 32);
    goto LABEL_27;
  }
  std::wstring::wstring(S1, a1 + 64);
  v41 = 1;
  if ( v54 > 7 )
  {
    v8 = (wchar_t **)S1[0];
    v9 = (wchar_t **)S1[0];
  }
  else
  {
    v8 = S1;
    v9 = S1;
  }
  v10 = (wchar_t **)((char *)v9 + 2 * N);
  v11 = S1;
  if ( v54 > 7 )
    v11 = (wchar_t **)S1[0];
  while ( v11 != v10 )
  {
    *(_WORD *)v8 = ((__int64 (__fastcall *)(_QWORD))_o_towlower)(*(unsigned __int16 *)v11);
    v8 = (wchar_t **)((char *)v8 + 2);
    v11 = (wchar_t **)((char *)v11 + 2);
  }
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
    a4,
    v50,
    S1);
  v12 = v51;
  if ( *(_BYTE *)(v51 + 25) )
    goto LABEL_21;
  v13 = (const wchar_t *)(v51 + 32);
  v14 = *(_QWORD *)(v51 + 48);
  if ( *(_QWORD *)(v51 + 56) > 7u )
    v13 = *(const wchar_t **)v13;
  v15 = N;
  v16 = (const wchar_t *)S1;
  if ( v54 > 7 )
    v16 = S1[0];
  v17 = *(_QWORD *)(v51 + 48);
  if ( v14 >= N )
    v17 = N;
  v18 = wmemcmp(v16, v13, v17);
  if ( v18 )
  {
    if ( v18 < 0 )
LABEL_21:
      v12 = *a4;
  }
  else if ( v15 < v14 )
  {
    goto LABEL_21;
  }
  std::wstring::~wstring(S1);
  if ( *(_QWORD *)(v7 + 24) <= 7u )
    v19 = (const char *)v7;
  else
    v19 = *(const char **)v7;
  LOBYTE(lpOutBuffer) = v12 == *a4;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x303,
    (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
    (const char *)0x80070057LL,
    lpOutBuffer,
    (bool)"Invalid RedirectionNode: %ws",
    v19);
  v20 = (_QWORD *)(v12 + 64);
LABEL_27:
  v46 = 0;
  v47 = 0;
  std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v46, 0, a1);
  if ( *((_QWORD *)&v46 + 1) == v47 )
  {
    std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v46, *((_QWORD *)&v46 + 1), v20);
  }
  else
  {
    std::wstring::wstring(*((_QWORD *)&v46 + 1), v20);
    *((_QWORD *)&v46 + 1) += 32LL;
  }
  *(_QWORD *)nInBufferSize = 0;
  lpInBuffer = 0;
  container::RegistryProvider::BuildTightlyPackgedStringBuffer(0x14u);
  v21 = lpInBuffer;
  v22 = 0;
  v41 = 0;
  v23 = 0;
  if ( *(_BYTE *)(a1 + 101) )
  {
    v22 = 4;
    v41 = 4;
    v23 = 4;
  }
  if ( *(_BYTE *)(a1 + 100) )
  {
    v22 = v23 | 2;
    v41 = v23 | 2;
  }
  *(_QWORD *)lpInBuffer = a2;
  v21[3] = v22;
  v21[4] = *(_DWORD *)(a1 + 96);
  v24 = *(_QWORD *)(a1 + 16);
  if ( v24 > 0xFFFF )
    v25 = -1;
  else
    v25 = *(_QWORD *)(a1 + 16);
  *((_WORD *)v21 + 4) = v25;
  if ( v24 > 0xFFFF )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v24 > 0xFFFF ? (const char *)0xC0000095LL : 0,
      lpOutBuffer);
  v26 = 2 * v25;
  if ( v26 > 0xFFFF )
    v27 = -1;
  else
    v27 = 2 * v25;
  *((_WORD *)v21 + 4) = v27;
  if ( v26 > 0xFFFF )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x333,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v26 > 0xFFFF ? (const char *)0xC0000095LL : 0,
      lpOutBuffer);
  v28 = v20[2];
  if ( v28 > 0xFFFF )
    v29 = -1;
  else
    v29 = v20[2];
  *((_WORD *)v21 + 5) = v29;
  if ( v28 > 0xFFFF )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x33C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v28 > 0xFFFF ? (const char *)0xC0000095LL : 0,
      lpOutBuffer);
  v30 = 2 * v29;
  if ( v30 > 0xFFFF )
    v31 = -1;
  else
    v31 = 2 * v29;
  *((_WORD *)v21 + 5) = v31;
  if ( v30 > 0xFFFF )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x341,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      v30 > 0xFFFF ? (const char *)0xC0000095LL : 0,
      lpOutBuffer);
  if ( v20[3] <= 7u )
    v32 = v20;
  else
    v32 = (_QWORD *)*v20;
  v43 = (__int64)v32;
  if ( *(_QWORD *)(a1 + 24) <= 7u )
    v33 = a1;
  else
    v33 = *(_QWORD *)a1;
  v44 = v33;
  ContainerProvider::CreateRegNamespaceNode<unsigned short const *,unsigned short const *,unsigned int const &,unsigned long &>(
    &v44,
    &v43,
    a1 + 96,
    &v41);
  BytesReturned = 0;
  if ( !DeviceIoControl(hDevice, 0x22000Cu, v21, nInBufferSize[0], 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v37 = LastError;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v41 = LastError;
    hDevice = (HANDLE)std::wstring::c_str(v7);
    v44 = std::wstring::c_str(v20);
    v43 = std::wstring::c_str(a1);
    ContainerProvider::RegistryRedirectionNodeFailure<unsigned short const *,unsigned short const *,unsigned short const *,long,unsigned short const (&)[56],unsigned int const &>(
      (unsigned int)&v43,
      (unsigned int)&v44,
      (unsigned int)&hDevice,
      (unsigned int)&v41,
      lpOutBuffera,
      a1 + 96);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)v37,
      lpOutBufferb);
  }
  if ( v21 )
    operator delete(v21, v34);
  return std::vector<std::wstring>::_Tidy(&v46);
}

```

## disassembly

```asm
0x18002a78c  mov     [rsp-8+arg_8], rbx
0x18002a791  push    rbp
0x18002a792  push    rsi
0x18002a793  push    rdi
0x18002a794  push    r12
0x18002a796  push    r13
0x18002a798  push    r14
0x18002a79a  push    r15
0x18002a79c  lea     rbp, [rsp-27h]
0x18002a7a1  sub     rsp, 0D0h
0x18002a7a8  mov     rax, cs:__security_cookie
0x18002a7af  xor     rax, rsp
0x18002a7b2  mov     [rbp+57h+var_40], rax
0x18002a7b6  mov     r15, r9
0x18002a7b9  mov     [rbp+57h+hDevice], r8
0x18002a7bd  mov     r13, rdx
0x18002a7c0  mov     rsi, rcx
0x18002a7c3  mov     [rbp+57h+var_C0], 0
0x18002a7ca  lea     r12, [rcx+40h]
0x18002a7ce  cmp     qword ptr [r12+10h], 0
0x18002a7d4  jz      loc_18002A8EC
0x18002a7da  mov     rdx, r12
0x18002a7dd  lea     rcx, [rbp+57h+S1]
0x18002a7e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002a7e6  mov     [rbp+57h+var_C0], 1
0x18002a7ed  mov     rcx, [rbp+57h+S1]
0x18002a7f1  cmp     [rbp+57h+var_48], 7
0x18002a7f6  ja      short loc_18002A802
0x18002a7f8  lea     rdi, [rbp+57h+S1]
0x18002a7fc  lea     rdx, [rbp+57h+S1]
0x18002a800  jmp     short loc_18002A808
0x18002a802  mov     rdi, rcx
0x18002a805  mov     rdx, rcx
0x18002a808  mov     rax, [rbp+57h+N]
0x18002a80c  lea     r14, [rdx+rax*2]
0x18002a810  lea     rbx, [rbp+57h+S1]
0x18002a814  cmova   rbx, rcx
0x18002a818  jmp     short loc_18002A834
0x18002a81a  movzx   ecx, word ptr [rbx]
0x18002a81d  mov     rax, cs:__imp__o_towlower
0x18002a824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a829  mov     [rdi], ax
0x18002a82c  lea     rdi, [rdi+2]
0x18002a830  add     rbx, 2
0x18002a834  cmp     rbx, r14
0x18002a837  jnz     short loc_18002A81A
0x18002a839  lea     r8, [rbp+57h+S1]
0x18002a83d  lea     rdx, [rbp+57h+var_78]
0x18002a841  mov     rcx, r15
0x18002a844  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18002a849  mov     rdi, [rbp+57h+var_68]
0x18002a84d  cmp     byte ptr [rdi+19h], 0
0x18002a851  jnz     short loc_18002A893
0x18002a853  lea     rdx, [rdi+20h]
0x18002a857  mov     rbx, [rdx+10h]
0x18002a85b  cmp     qword ptr [rdx+18h], 7
0x18002a860  jbe     short loc_18002A865
0x18002a862  mov     rdx, [rdx]; S2
0x18002a865  mov     r14, [rbp+57h+N]
0x18002a869  lea     rcx, [rbp+57h+S1]
0x18002a86d  cmp     [rbp+57h+var_48], 7
0x18002a872  cmova   rcx, [rbp+57h+S1]; S1
0x18002a877  mov     r8, rbx
0x18002a87a  cmp     rbx, r14
0x18002a87d  cmovnb  r8, r14; N
0x18002a881  call    wmemcmp
0x18002a886  test    eax, eax
0x18002a888  jnz     short loc_18002A891
0x18002a88a  cmp     r14, rbx
0x18002a88d  jnb     short loc_18002A896
0x18002a88f  jmp     short loc_18002A893
0x18002a891  jns     short loc_18002A896
0x18002a893  mov     rdi, [r15]
0x18002a896  lea     rcx, [rbp+57h+S1]
0x18002a89a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a89f  cmp     qword ptr [r12+18h], 7
0x18002a8a5  jbe     short loc_18002A8AD
0x18002a8a7  mov     rdx, [r12]
0x18002a8ab  jmp     short loc_18002A8B0
0x18002a8ad  mov     rdx, r12
0x18002a8b0  cmp     rdi, [r15]
0x18002a8b3  setz    al
0x18002a8b6  mov     rcx, [rbp+5Fh]; this
0x18002a8ba  mov     [rsp+100h+lpBytesReturned], rdx; char *
0x18002a8bf  lea     rdx, aInvalidRedirec; "Invalid RedirectionNode: %ws"
0x18002a8c6  mov     qword ptr [rsp+100h+nOutBufferSize], rdx; bool
0x18002a8cb  mov     byte ptr [rsp+100h+lpOutBuffer], al; int
0x18002a8cf  mov     r9d, 80070057h; char *
0x18002a8d5  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002a8dc  mov     edx, 303h; void *
0x18002a8e1  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002a8e6  add     rdi, 40h ; '@'
0x18002a8ea  jmp     short loc_18002A8F0
0x18002a8ec  lea     rdi, [rcx+20h]
0x18002a8f0  xorps   xmm0, xmm0
0x18002a8f3  movdqu  [rbp+57h+var_A0], xmm0
0x18002a8f8  xor     r15d, r15d
0x18002a8fb  mov     [rbp+57h+var_90], r15
0x18002a8ff  mov     r8, rsi
0x18002a902  xor     edx, edx
0x18002a904  lea     rcx, [rbp+57h+var_A0]
0x18002a908  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002a90d  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x18002a911  cmp     rax, [rbp+57h+var_90]
0x18002a915  jz      short loc_18002A929
0x18002a917  mov     rdx, rdi
0x18002a91a  mov     rcx, rax
0x18002a91d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002a922  add     qword ptr [rbp+57h+var_A0+8], 20h ; ' '
0x18002a927  jmp     short loc_18002A938
0x18002a929  mov     r8, rdi
0x18002a92c  mov     rdx, rax
0x18002a92f  lea     rcx, [rbp+57h+var_A0]
0x18002a933  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18002a938  mov     qword ptr [rbp+57h+nInBufferSize], r15
0x18002a93c  mov     [rbp+57h+lpInBuffer], r15
0x18002a940  lea     r9, [rbp+57h+nInBufferSize]
0x18002a944  lea     r8, [rbp+57h+lpInBuffer]
0x18002a948  lea     rdx, [rbp+57h+var_A0]
0x18002a94c  mov     ecx, 14h; unsigned __int64
0x18002a951  call    ?BuildTightlyPackgedStringBuffer@RegistryProvider@container@@YAX_KAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@4@PEA_K@Z; container::RegistryProvider::BuildTightlyPackgedStringBuffer(unsigned __int64,std::vector<std::wstring> const &,std::unique_ptr<uchar [0]> *,unsigned __int64 *)
0x18002a956  mov     rbx, [rbp+57h+lpInBuffer]
0x18002a95a  mov     eax, r15d
0x18002a95d  mov     [rbp+57h+var_C0], eax
0x18002a960  mov     ecx, r15d
0x18002a963  cmp     [rsi+65h], r15b
0x18002a967  jz      short loc_18002A973
0x18002a969  mov     eax, 4
0x18002a96e  mov     [rbp+57h+var_C0], eax
0x18002a971  mov     ecx, eax
0x18002a973  cmp     [rsi+64h], r15b
0x18002a977  jz      short loc_18002A981
0x18002a979  mov     eax, ecx
0x18002a97b  or      eax, 2
0x18002a97e  mov     [rbp+57h+var_C0], eax
0x18002a981  mov     [rbx], r13
0x18002a984  mov     [rbx+0Ch], eax
0x18002a987  lea     r14, [rsi+60h]
0x18002a98b  mov     eax, [r14]
0x18002a98e  mov     [rbx+10h], eax
0x18002a991  mov     rax, [rsi+10h]
0x18002a995  mov     edx, 0FFFFh
0x18002a99a  cmp     rax, rdx
0x18002a99d  ja      short loc_18002A9A4
0x18002a99f  movzx   ecx, ax
0x18002a9a2  jmp     short loc_18002A9A6
0x18002a9a4  mov     ecx, edx
0x18002a9a6  cmp     rdx, rax
0x18002a9a9  sbb     r9d, r9d
0x18002a9ac  mov     r11d, 0C0000095h
0x18002a9b2  and     r9d, r11d; char *
0x18002a9b5  mov     [rbx+8], cx
0x18002a9b9  mov     r10, [rbp+5Fh]
0x18002a9bd  cmp     rax, rdx
0x18002a9c0  ja      loc_18002AB6A
0x18002a9c6  movzx   eax, cx
0x18002a9c9  add     eax, eax
0x18002a9cb  cmp     eax, edx
0x18002a9cd  ja      short loc_18002A9D4
0x18002a9cf  movzx   ecx, ax
0x18002a9d2  jmp     short loc_18002A9D6
0x18002a9d4  mov     ecx, edx
0x18002a9d6  cmp     edx, eax
0x18002a9d8  sbb     r9d, r9d
0x18002a9db  and     r9d, r11d; char *
0x18002a9de  mov     [rbx+8], cx
0x18002a9e2  mov     rcx, [rbp+5Fh]; this
0x18002a9e6  cmp     eax, edx
0x18002a9e8  ja      loc_18002AB7F
0x18002a9ee  mov     rax, [rdi+10h]
0x18002a9f2  cmp     rax, rdx
0x18002a9f5  ja      short loc_18002A9FC
0x18002a9f7  movzx   ecx, ax
0x18002a9fa  jmp     short loc_18002A9FE
0x18002a9fc  mov     ecx, edx
0x18002a9fe  cmp     rdx, rax
0x18002aa01  sbb     r9d, r9d
0x18002aa04  and     r9d, r11d; char *
0x18002aa07  mov     [rbx+0Ah], cx
0x18002aa0b  mov     r10, [rbp+5Fh]
0x18002aa0f  cmp     rax, rdx
0x18002aa12  ja      loc_18002AB91
0x18002aa18  movzx   eax, cx
0x18002aa1b  add     eax, eax
0x18002aa1d  cmp     eax, edx
0x18002aa1f  ja      short loc_18002AA26
0x18002aa21  movzx   ecx, ax
0x18002aa24  jmp     short loc_18002AA28
0x18002aa26  mov     ecx, edx
0x18002aa28  cmp     edx, eax
0x18002aa2a  sbb     r9d, r9d
0x18002aa2d  and     r9d, r11d; char *
0x18002aa30  mov     [rbx+0Ah], cx
0x18002aa34  mov     rcx, [rbp+5Fh]; this
0x18002aa38  cmp     eax, edx
0x18002aa3a  ja      loc_18002ABA6
0x18002aa40  cmp     qword ptr [rdi+18h], 7
0x18002aa45  jbe     short loc_18002AA4C
0x18002aa47  mov     rax, [rdi]
0x18002aa4a  jmp     short loc_18002AA4F
0x18002aa4c  mov     rax, rdi
0x18002aa4f  mov     [rbp+57h+var_B8], rax
0x18002aa53  cmp     qword ptr [rsi+18h], 7
0x18002aa58  jbe     short loc_18002AA5F
0x18002aa5a  mov     rax, [rsi]
0x18002aa5d  jmp     short loc_18002AA62
0x18002aa5f  mov     rax, rsi
0x18002aa62  mov     [rbp+57h+var_B0], rax
0x18002aa66  lea     r9, [rbp+57h+var_C0]
0x18002aa6a  mov     r8, r14
0x18002aa6d  lea     rdx, [rbp+57h+var_B8]
0x18002aa71  lea     rcx, [rbp+57h+var_B0]
0x18002aa75  call    ??$CreateRegNamespaceNode@PEBGPEBGAEBIAEAK@ContainerProvider@@SAX$$QEAPEBG0AEBIAEAK@Z; ContainerProvider::CreateRegNamespaceNode<ushort const *,ushort const *,uint const &,ulong &>(ushort const * &&,ushort const * &&,uint const &,ulong &)
0x18002aa7a  mov     [rbp+57h+BytesReturned], r15d
0x18002aa7e  mov     [rsp+100h+lpOverlapped], r15; lpOverlapped
0x18002aa83  lea     rax, [rbp+57h+BytesReturned]
0x18002aa87  mov     [rsp+100h+lpBytesReturned], rax; lpBytesReturned
0x18002aa8c  mov     [rsp+100h+nOutBufferSize], r15d; nOutBufferSize
0x18002aa91  mov     [rsp+100h+lpOutBuffer], r15; unsigned int
0x18002aa96  mov     r9d, [rbp+57h+nInBufferSize]; nInBufferSize
0x18002aa9a  mov     r8, rbx; lpInBuffer
0x18002aa9d  mov     edx, 22000Ch; dwIoControlCode
0x18002aaa2  mov     rcx, [rbp+57h+hDevice]; hDevice
0x18002aaa6  call    cs:__imp_DeviceIoControl
0x18002aaad  nop     dword ptr [rax+rax+00h]
0x18002aab2  test    eax, eax
0x18002aab4  jz      short loc_18002AAF5
0x18002aab6  test    rbx, rbx
0x18002aab9  jz      short loc_18002AAC4
0x18002aabb  mov     rcx, rbx; void *
0x18002aabe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002aac3  nop
0x18002aac4  lea     rcx, [rbp+57h+var_A0]
0x18002aac8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002aacd  mov     rcx, [rbp+57h+var_40]
0x18002aad1  xor     rcx, rsp; StackCookie
0x18002aad4  call    __security_check_cookie
0x18002aad9  mov     rbx, [rsp+100h+arg_8]
0x18002aae1  add     rsp, 0D0h
0x18002aae8  pop     r15
0x18002aaea  pop     r14
0x18002aaec  pop     r13
0x18002aaee  pop     r12
0x18002aaf0  pop     rdi
0x18002aaf1  pop     rsi
0x18002aaf2  pop     rbp
0x18002aaf3  retn
0x18002aaf5  call    cs:__imp_GetLastError
0x18002aafc  nop     dword ptr [rax+rax+00h]
0x18002ab01  nop
0x18002ab02  mov     ebx, eax
0x18002ab04  test    eax, eax
0x18002ab06  jle     short loc_18002AB10
0x18002ab08  movzx   eax, bx
0x18002ab0b  or      eax, 80070000h
0x18002ab10  mov     [rbp+57h+var_C0], eax
0x18002ab13  mov     rcx, r12
0x18002ab16  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ab1b  mov     [rbp+57h+hDevice], rax
0x18002ab1f  mov     rcx, rdi
0x18002ab22  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ab27  mov     [rbp+57h+var_B0], rax
0x18002ab2b  mov     rcx, rsi
0x18002ab2e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002ab33  mov     [rbp+57h+var_B8], rax
0x18002ab37  mov     qword ptr [rsp+100h+nOutBufferSize], r14
0x18002ab3c  lea     r9, [rbp+57h+var_C0]
0x18002ab40  lea     r8, [rbp+57h+hDevice]
0x18002ab44  lea     rdx, [rbp+57h+var_B0]
0x18002ab48  lea     rcx, [rbp+57h+var_B8]
0x18002ab4c  call    ??$RegistryRedirectionNodeFailure@PEBGPEBGPEBGJAEAY0DI@$$CBGAEBI@ContainerProvider@@SAX$$QEAPEBG00$$QEAJAEAY0DI@$$CBGAEBI@Z; ContainerProvider::RegistryRedirectionNodeFailure<ushort const *,ushort const *,ushort const *,long,ushort const (&)[56],uint const &>(ushort const * &&,ushort const * &&,ushort const * &&,long &&,ushort const (&)[56],uint const &)
0x18002ab51  mov     rcx, [rbp+5Fh]; this
0x18002ab55  mov     r9d, ebx; char *
0x18002ab58  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002ab5f  mov     edx, 360h; void *
0x18002ab64  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ab6a  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002ab71  mov     edx, 32Eh; void *
0x18002ab76  mov     rcx, r10; this
0x18002ab79  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002ab7f  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002ab86  mov     edx, 333h; void *
0x18002ab8b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002ab91  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002ab98  mov     edx, 33Ch; void *
0x18002ab9d  mov     rcx, r10; this
0x18002aba0  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002aba6  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002abad  mov     edx, 341h; void *
0x18002abb2  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
