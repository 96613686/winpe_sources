# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(ushort const *,int)

- ea: `0x14001a7a0`
- end: `0x14001a846`
- name: `?InitializePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGH@Z`
- size: `166`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400197a4`
- `0x140019f78`
- `0x14001a304`
- `0x14001a628`

## callees

- `0x14000b0f4`
- `0x140019b64`
- `0x14001a7a0`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x14001a805`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x14001a805`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this,
        const unsigned __int16 *a2,
        int a3)
{
  int PersistFile; // eax
  unsigned int v6; // ebx
  HRESULT v8; // eax
  int pstmTemplate; // [rsp+20h] [rbp-18h]
  int pstmTemplatea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  PersistFile = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreatePersistFile((LPWSTR *)this, a2);
  v6 = PersistFile;
  if ( PersistFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)PersistFile,
      pstmTemplate);
    return v6;
  }
  if ( a3 )
  {
    v8 = SHCreateStreamOnFileEx(*(LPCWSTR *)this, 0x1002u, 0x100u, 0, 0, (IStream **)this + 2);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v8,
        pstmTemplatea);
      return v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001a7a0  mov     [rsp+arg_0], rbx
0x14001a7a5  mov     [rsp+arg_8], rsi
0x14001a7aa  push    rdi
0x14001a7ab  sub     rsp, 30h
0x14001a7af  mov     esi, r8d
0x14001a7b2  mov     rdi, rcx
0x14001a7b5  call    ?CreatePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreatePersistFile(ushort const *)
0x14001a7ba  mov     ebx, eax
0x14001a7bc  test    eax, eax
0x14001a7be  jns     short loc_14001A7DE
0x14001a7c0  mov     rcx, [rsp+38h]; this
0x14001a7c5  mov     r9d, eax; char *
0x14001a7c8  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a7cf  mov     edx, 260h; void *
0x14001a7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a7d9  nop
0x14001a7da  mov     eax, ebx
0x14001a7dc  jmp     short loc_14001A835
0x14001a7de  test    esi, esi
0x14001a7e0  jz      short loc_14001A833
0x14001a7e2  lea     rax, [rdi+10h]
0x14001a7e6  mov     [rsp+38h+ppstm], rax; ppstm
0x14001a7eb  mov     [rsp+38h+pstmTemplate], 0; int
0x14001a7f4  xor     r9d, r9d; fCreate
0x14001a7f7  mov     edx, 1002h; grfMode
0x14001a7fc  mov     r8d, 100h; dwAttributes
0x14001a802  mov     rcx, [rdi]; pszFile
0x14001a805  call    cs:__imp_SHCreateStreamOnFileEx
0x14001a80c  nop     dword ptr [rax+rax+00h]
0x14001a811  mov     ebx, eax
0x14001a813  test    eax, eax
0x14001a815  jns     short loc_14001A833
0x14001a817  mov     rcx, [rsp+38h]; this
0x14001a81c  mov     r9d, eax; char *
0x14001a81f  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a826  mov     edx, 26Bh; void *
0x14001a82b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a830  nop
0x14001a831  jmp     short loc_14001A7DA
0x14001a833  xor     eax, eax
0x14001a835  mov     rbx, [rsp+38h+arg_0]
0x14001a83a  mov     rsi, [rsp+38h+arg_8]
0x14001a83f  add     rsp, 30h
0x14001a843  pop     rdi
0x14001a844  retn
```
