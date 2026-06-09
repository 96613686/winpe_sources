# VerifyFileIsTrustedAndInPackage

- ea: `0x180023bc0`
- end: `0x180023dea`
- name: `VerifyFileIsTrustedAndInPackage`
- size: `554`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ff04`
- `0x18000ff24`
- `0x180012fb8`
- `0x180023bc0`
- `0x180098fbc`
- `0x1800b1c20`
- `0x1800b203c`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023dc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ca2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023dc1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023bfc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023bfc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023c92`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023cff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023db1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023c92`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023cff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023db1`

## string_xrefs

- `0x180023c23`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023c76`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023ce3`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall VerifyFileIsTrustedAndInPackage(unsigned __int16 *a1, __int64 a2, int *a3)
{
  char *FileW; // rbx
  const char *v7; // r9
  unsigned int LastError; // edi
  __int64 result; // rax
  int WindowsPplTrustLabelSid; // eax
  bool v11; // r8
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  __int64 v16; // r8
  char v17; // al
  bool v18; // zf
  int v19; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-98h]
  PSID pSid; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-70h] BYREF
  __int128 v23; // [rsp+60h] [rbp-58h] BYREF
  __int64 v24; // [rsp+70h] [rbp-48h]
  __int64 v25; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v27; // [rsp+D8h] [rbp+20h] BYREF

  FileW = (char *)CreateFileW(a1, 0x20000u, 1u, 0, 3u, 0, 0);
  v22[1] = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    pSid = 0;
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&pSid);
    v12 = WindowsPplTrustLabelSid;
    if ( WindowsPplTrustLabelSid >= 0 )
    {
      LOBYTE(v27) = 0;
      try
      {
        v13 = TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(a1, pSid, v11, (bool *)&v27);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v23 = 0;
          v24 = 0;
          v25 = 0;
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)(a2 + 2 * v16) );
          std::wstring::_Construct<1,unsigned short const *>(&v23, a2, v16);
          CreatePackageInformation(v22, &v23);
          v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)v22[0] + 8LL))(v22[0], a1);
          if ( !(_BYTE)v27 || (v18 = v17 == 0, v19 = 1, v18) )
            v19 = 0;
          *a3 = v19;
          if ( v22[0] )
            (**(void (__fastcall ***)(_QWORD, __int64))v22[0])(v22[0], 1);
          if ( pSid )
            FreeSid(pSid);
          CloseHandle(FileW);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x39B,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v13,
            dwCreationDisposition);
          if ( pSid )
            FreeSid(pSid);
          CloseHandle(FileW);
          result = v14;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x3A4,
                               (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x394,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)WindowsPplTrustLabelSid,
        dwCreationDisposition);
      if ( pSid )
        FreeSid(pSid);
      CloseHandle(FileW);
      return v12;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x391,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                  v7);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180023bc0  push    rbx
0x180023bc2  push    rsi
0x180023bc3  push    rdi
0x180023bc4  push    r12
0x180023bc6  push    r14
0x180023bc8  push    r15
0x180023bca  sub     rsp, 88h
0x180023bd1  mov     r15, r8
0x180023bd4  mov     r14, rdx
0x180023bd7  mov     rsi, rcx
0x180023bda  xor     r12d, r12d
0x180023bdd  mov     [rsp+0B8h+hTemplateFile], r12; hTemplateFile
0x180023be2  mov     [rsp+0B8h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180023be7  mov     [rsp+0B8h+dwCreationDisposition], 3; int
0x180023bef  xor     r9d, r9d; lpSecurityAttributes
0x180023bf2  mov     edx, 20000h; dwDesiredAccess
0x180023bf7  lea     r8d, [r12+1]; dwShareMode
0x180023bfc  call    cs:__imp_CreateFileW
0x180023c03  nop     dword ptr [rax+rax+00h]
0x180023c08  mov     rbx, rax
0x180023c0b  mov     [rsp+0B8h+var_68], rax
0x180023c10  inc     rax
0x180023c13  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023c19  jnz     short loc_180023C56
0x180023c1b  mov     rcx, [rsp+0B8h]; this
0x180023c23  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180023c2a  mov     edx, 391h; void *
0x180023c2f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023c34  mov     edi, eax
0x180023c36  lea     rcx, [rbx-1]
0x180023c3a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180023c3e  ja      short loc_180023C4F
0x180023c40  mov     rcx, rbx; hObject
0x180023c43  call    cs:__imp_CloseHandle
0x180023c4a  nop     dword ptr [rax+rax+00h]
0x180023c4f  mov     eax, edi
0x180023c51  jmp     loc_180023DD8
0x180023c56  mov     [rsp+0B8h+pSid], r12
0x180023c5b  lea     rcx, [rsp+0B8h+pSid]; Sid
0x180023c60  call    ?GetWindowsPplTrustLabelSid@TrustLabelAceHelpers@@SAJPEAPEAX@Z; TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(void * *)
0x180023c65  mov     edi, eax
0x180023c67  test    eax, eax
0x180023c69  jns     short loc_180023CB5
0x180023c6b  mov     rcx, [rsp+0B8h]; this
0x180023c73  mov     r9d, eax; char *
0x180023c76  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180023c7d  mov     edx, 394h; void *
0x180023c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023c87  nop
0x180023c88  mov     rcx, [rsp+0B8h+pSid]; pSid
0x180023c8d  test    rcx, rcx
0x180023c90  jz      short loc_180023C9F
0x180023c92  call    cs:__imp_FreeSid
0x180023c99  nop     dword ptr [rax+rax+00h]
0x180023c9e  nop
0x180023c9f  mov     rcx, rbx; hObject
0x180023ca2  call    cs:__imp_CloseHandle
0x180023ca9  nop     dword ptr [rax+rax+00h]
0x180023cae  mov     eax, edi
0x180023cb0  jmp     loc_180023DD8
0x180023cb5  mov     byte ptr [rsp+0B8h+arg_18], r12b
0x180023cbd  lea     r9, [rsp+0B8h+arg_18]; bool *
0x180023cc5  mov     rdx, [rsp+0B8h+pSid]; void *
0x180023cca  mov     rcx, rsi; unsigned __int16 *
0x180023ccd  call    ?VerifyTrustSidPresentOnFilesystemObject@TrustLabelAceHelpers@@SAJPEBGPEAX_NPEA_N@Z; TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(ushort const *,void *,bool,bool *)
0x180023cd2  mov     edi, eax
0x180023cd4  test    eax, eax
0x180023cd6  jns     short loc_180023D22
0x180023cd8  mov     rcx, [rsp+0B8h]; this
0x180023ce0  mov     r9d, eax; char *
0x180023ce3  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180023cea  mov     edx, 39Bh; void *
0x180023cef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cf4  nop
0x180023cf5  mov     rcx, [rsp+0B8h+pSid]; pSid
0x180023cfa  test    rcx, rcx
0x180023cfd  jz      short loc_180023D0C
0x180023cff  call    cs:__imp_FreeSid
0x180023d06  nop     dword ptr [rax+rax+00h]
0x180023d0b  nop
0x180023d0c  mov     rcx, rbx; hObject
0x180023d0f  call    cs:__imp_CloseHandle
0x180023d16  nop     dword ptr [rax+rax+00h]
0x180023d1b  mov     eax, edi
0x180023d1d  jmp     loc_180023DD8
0x180023d22  xorps   xmm0, xmm0
0x180023d25  movups  [rsp+0B8h+var_58], xmm0
0x180023d2a  mov     [rsp+0B8h+var_48], r12
0x180023d2f  mov     [rsp+0B8h+var_40], r12
0x180023d34  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023d38  inc     r8
0x180023d3b  cmp     [r14+r8*2], r12w
0x180023d40  jnz     short loc_180023D38
0x180023d42  mov     rdx, r14
0x180023d45  lea     rcx, [rsp+0B8h+var_58]
0x180023d4a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023d4f  lea     rdx, [rsp+0B8h+var_58]
0x180023d54  lea     rcx, [rsp+0B8h+var_70]
0x180023d59  call    ?CreatePackageInformation@@YA?AV?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; CreatePackageInformation(std::wstring)
0x180023d5e  nop
0x180023d5f  mov     rcx, [rsp+0B8h+var_70]
0x180023d64  mov     rax, [rcx]
0x180023d67  mov     rdx, rsi
0x180023d6a  mov     rax, [rax+8]
0x180023d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d73  cmp     byte ptr [rsp+0B8h+arg_18], r12b
0x180023d7b  jz      short loc_180023D86
0x180023d7d  test    al, al
0x180023d7f  mov     eax, 1
0x180023d84  jnz     short loc_180023D89
0x180023d86  mov     eax, r12d
0x180023d89  mov     [r15], eax
0x180023d8c  mov     rcx, [rsp+0B8h+var_70]
0x180023d91  test    rcx, rcx
0x180023d94  jz      short loc_180023DA7
0x180023d96  mov     rax, [rcx]
0x180023d99  mov     edx, 1
0x180023d9e  mov     rax, [rax]
0x180023da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023da6  nop
0x180023da7  mov     rcx, [rsp+0B8h+pSid]; pSid
0x180023dac  test    rcx, rcx
0x180023daf  jz      short loc_180023DBE
0x180023db1  call    cs:__imp_FreeSid
0x180023db8  nop     dword ptr [rax+rax+00h]
0x180023dbd  nop
0x180023dbe  mov     rcx, rbx; hObject
0x180023dc1  call    cs:__imp_CloseHandle
0x180023dc8  nop     dword ptr [rax+rax+00h]
0x180023dcd  xor     eax, eax
0x180023dcf  jmp     short loc_180023DD8
0x180023dd1  mov     eax, [rsp+0B8h+arg_18]
0x180023dd8  add     rsp, 88h
0x180023ddf  pop     r15
0x180023de1  pop     r14
0x180023de3  pop     r12
0x180023de5  pop     rdi
0x180023de6  pop     rsi
0x180023de7  pop     rbx
0x180023de8  retn
```
