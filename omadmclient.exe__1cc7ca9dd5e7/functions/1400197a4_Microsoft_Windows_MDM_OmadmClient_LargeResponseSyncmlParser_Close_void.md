# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::Close(void)

- ea: `0x1400197a4`
- end: `0x140019855`
- name: `?Close@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@QEAAJXZ`
- size: `177`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140042b00`
- `0x14004f290`

## callees

- `0x14000b0f4`
- `0x140013068`
- `0x1400197a4`
- `0x14001a7a0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019817`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140019807`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140019807`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::Close(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this)
{
  int v2; // eax
  int v3; // edi
  __int64 v5; // rcx
  DWORD LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)this
    || (v2 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(
               this,
               *((const unsigned __int16 **)this + 1),
               0),
        v3 = v2,
        v2 >= 0) )
  {
    v5 = *((_QWORD *)this + 2);
    if ( v5 )
    {
      *((_QWORD *)this + 2) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    if ( DeleteFileW(*(LPCWSTR *)this) )
      return 0;
    LastError = GetLastError();
    if ( LastError == 2 || !LastError )
      return 0;
    else
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x13D,
               (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
               (const char *)LastError,
               v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v2,
      v7);
    return v3;
  }
}

```

## disassembly

```asm
0x1400197a4  mov     [rsp+arg_0], rbx
0x1400197a9  push    rdi; unsigned int
0x1400197aa  sub     rsp, 20h
0x1400197ae  mov     rbx, rcx
0x1400197b1  cmp     qword ptr [rcx], 0
0x1400197b5  jnz     short loc_1400197E6
0x1400197b7  xor     r8d, r8d; int
0x1400197ba  mov     rdx, [rcx+8]; unsigned __int16 *
0x1400197be  call    ?InitializePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGH@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(ushort const *,int)
0x1400197c3  mov     edi, eax
0x1400197c5  test    eax, eax
0x1400197c7  jns     short loc_1400197E6
0x1400197c9  mov     rcx, [rsp+28h]; this
0x1400197ce  mov     r9d, eax; char *
0x1400197d1  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400197d8  mov     edx, 132h; void *
0x1400197dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400197e2  mov     eax, edi
0x1400197e4  jmp     short loc_140019849
0x1400197e6  mov     rcx, [rbx+10h]
0x1400197ea  test    rcx, rcx
0x1400197ed  jz      short loc_140019804
0x1400197ef  mov     qword ptr [rbx+10h], 0
0x1400197f7  mov     rax, [rcx]
0x1400197fa  mov     rax, [rax+10h]
0x1400197fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019803  nop
0x140019804  mov     rcx, [rbx]; lpFileName
0x140019807  call    cs:__imp_DeleteFileW
0x14001980e  nop     dword ptr [rax+rax+00h]
0x140019813  test    eax, eax
0x140019815  jnz     short loc_140019847
0x140019817  call    cs:__imp_GetLastError
0x14001981e  nop     dword ptr [rax+rax+00h]
0x140019823  cmp     eax, 2
0x140019826  jz      short loc_140019847
0x140019828  test    eax, eax
0x14001982a  jz      short loc_140019847
0x14001982c  mov     rcx, [rsp+28h]; this
0x140019831  mov     r9d, eax; char *
0x140019834  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001983b  mov     edx, 13Dh; void *
0x140019840  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140019845  jmp     short loc_140019849
0x140019847  xor     eax, eax
0x140019849  mov     rbx, [rsp+28h+arg_0]
0x14001984e  add     rsp, 20h
0x140019852  pop     rdi
0x140019853  retn
```
