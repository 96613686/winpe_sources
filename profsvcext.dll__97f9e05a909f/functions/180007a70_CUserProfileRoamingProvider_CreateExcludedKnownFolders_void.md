# CUserProfileRoamingProvider::_CreateExcludedKnownFolders(void)

- ea: `0x180007a70`
- end: `0x180007bc7`
- name: `?_CreateExcludedKnownFolders@CUserProfileRoamingProvider@@AEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c68`

## callees

- `0x180006a80`
- `0x180006a9c`
- `0x180007a70`
- `0x180007bd0`
- `0x18000fca8`
- `0x180020010`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180007b5d`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180007b5d`

## string_xrefs

- `0x180007acf`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007b3c`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007b92`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_CreateExcludedKnownFolders(CUserProfileRoamingProvider *this)
{
  unsigned int v2; // esi
  int v3; // eax
  const unsigned __int16 *v4; // rax
  int v5; // eax
  int BasicProfileFolderPathAlloc; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1)) & 0xC) != 0
     ? 0xFFFE1000
     : 0;
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1)) & 0x200) == 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 216LL))(*((_QWORD *)this + 1));
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x708,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)v3);
  }
  if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1))
    && *(_WORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1)) )
  {
    v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1));
    v5 = CUserProfileRoamingProvider::_CopyExclusionListFolders((WCHAR *)this, v4, v2 + 821510);
    if ( v5 >= 0 )
      return 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x70F,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v5);
  }
  v12 = 0;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(2, 0, &v12);
  v7 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v8 = 1817;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
    return v7;
  }
  BasicProfileFolderPathAlloc = CUserProfileRoamingProvider::_CopyExclusionListFolders((WCHAR *)this, v12, v2 + 821510);
  v7 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v8 = 1818;
    goto LABEL_12;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  return 0;
}

```

## disassembly

```asm
0x180007a70  push    rbx
0x180007a72  push    rbp
0x180007a73  push    rsi
0x180007a74  push    rdi
0x180007a75  sub     rsp, 28h
0x180007a79  mov     rdi, rcx
0x180007a7c  mov     rcx, [rcx+8]
0x180007a80  mov     rax, [rcx]
0x180007a83  mov     rax, [rax+8]
0x180007a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8c  and     al, 0Ch
0x180007a8e  neg     al
0x180007a90  sbb     esi, esi
0x180007a92  and     esi, 0FFFE1000h
0x180007a98  mov     rcx, [rdi+8]
0x180007a9c  mov     rax, [rcx]
0x180007a9f  mov     rax, [rax+10h]
0x180007aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa8  xor     ebp, ebp
0x180007aaa  bt      eax, 9
0x180007aae  jb      short loc_180007AE0
0x180007ab0  mov     rcx, [rdi+8]
0x180007ab4  mov     rax, [rcx]
0x180007ab7  mov     rax, [rax+0D8h]
0x180007abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac3  mov     rcx, [rsp+48h]; this
0x180007ac8  test    eax, eax
0x180007aca  jns     short loc_180007AE0
0x180007acc  mov     r9d, eax; char *
0x180007acf  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007ad6  mov     edx, 708h; void *
0x180007adb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007ae0  mov     rcx, [rdi+8]
0x180007ae4  mov     rax, [rcx]
0x180007ae7  mov     rax, [rax+28h]
0x180007aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af0  test    rax, rax
0x180007af3  jz      short loc_180007B4E
0x180007af5  mov     rcx, [rdi+8]
0x180007af9  mov     rax, [rcx]
0x180007afc  mov     rax, [rax+28h]
0x180007b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b05  cmp     [rax], bp
0x180007b08  jz      short loc_180007B4E
0x180007b0a  mov     rcx, [rdi+8]
0x180007b0e  mov     rax, [rcx]
0x180007b11  mov     rax, [rax+28h]
0x180007b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1a  mov     rdx, rax; unsigned __int16 *
0x180007b1d  lea     r8d, [rsi+0C8906h]; unsigned int
0x180007b24  mov     rcx, rdi; this
0x180007b27  call    ?_CopyExclusionListFolders@CUserProfileRoamingProvider@@AEAAJPEBGK@Z; CUserProfileRoamingProvider::_CopyExclusionListFolders(ushort const *,ulong)
0x180007b2c  mov     rcx, [rsp+48h]; this
0x180007b31  test    eax, eax
0x180007b33  jns     loc_180007BBC
0x180007b39  mov     r9d, eax; char *
0x180007b3c  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007b43  mov     edx, 70Fh; void *
0x180007b48  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007b4d  nop
0x180007b4e  mov     [rsp+48h+arg_0], rbp
0x180007b53  lea     r8, [rsp+48h+arg_0]
0x180007b58  xor     edx, edx
0x180007b5a  lea     ecx, [rdx+2]
0x180007b5d  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180007b63  mov     ebx, eax
0x180007b65  test    eax, eax
0x180007b67  jns     short loc_180007B70
0x180007b69  mov     edx, 719h
0x180007b6e  jmp     short loc_180007B8F
0x180007b70  lea     r8d, [rsi+0C8906h]; unsigned int
0x180007b77  mov     rdx, [rsp+48h+arg_0]; unsigned __int16 *
0x180007b7c  mov     rcx, rdi; this
0x180007b7f  call    ?_CopyExclusionListFolders@CUserProfileRoamingProvider@@AEAAJPEBGK@Z; CUserProfileRoamingProvider::_CopyExclusionListFolders(ushort const *,ulong)
0x180007b84  mov     ebx, eax
0x180007b86  test    eax, eax
0x180007b88  jns     short loc_180007BB2
0x180007b8a  mov     edx, 71Ah; void *
0x180007b8f  mov     r9d, eax; char *
0x180007b92  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007b99  mov     rcx, [rsp+48h]; this
0x180007b9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ba3  nop
0x180007ba4  lea     rcx, [rsp+48h+arg_0]
0x180007ba9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007bae  mov     eax, ebx
0x180007bb0  jmp     short loc_180007BBE
0x180007bb2  lea     rcx, [rsp+48h+arg_0]
0x180007bb7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007bbc  xor     eax, eax
0x180007bbe  add     rsp, 28h
0x180007bc2  pop     rdi
0x180007bc3  pop     rsi
0x180007bc4  pop     rbp
0x180007bc5  pop     rbx
0x180007bc6  retn
```
