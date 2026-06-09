# CAMCDoc::ScGetMuiPath(ushort const *,CStr &)

- ea: `0x140054d20`
- end: `0x140054f29`
- name: `?ScGetMuiPath@CAMCDoc@@AEAA?AVSC@mmcerror@@PEBGAEAVCStr@@@Z`
- size: `521`
- prototype: `mmcerror::SC *__fastcall(__int64, mmcerror::SC *, const WCHAR *, CStr *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140030a94`

## callees

- `0x140005da0`
- `0x1400065e0`
- `0x140008d90`
- `0x140054d20`
- `0x14006623c`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054d4c`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140054d4c`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054df2`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054e9b`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054ece`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054df2`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054e9b`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140054ece`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054dbb`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054e64`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054dbb`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140054e64`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054e08`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ead`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ec5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ee6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054e08`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ead`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ec5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140054ee6`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140054d63`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140054d63`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x140054dae`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x140054e57`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x140054dae`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x140054e57`

## string_xrefs

- `0x140054d59`: `CAMCDoc::ScGetMuiPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
mmcerror::SC *__fastcall CAMCDoc::ScGetMuiPath(__int64 a1, mmcerror::SC *a2, const WCHAR *a3, CStr *a4)
{
  CHeapFactory *v7; // rcx
  unsigned int v8; // r8d
  __int64 v9; // rdx
  unsigned __int16 *pwszFileMUIPath; // rdi
  CHeapFactory *v11; // rcx
  unsigned int v12; // eax
  unsigned __int64 pululEnumerator; // [rsp+48h] [rbp-8h] BYREF
  __int64 pcchFileMUIPath; // [rsp+80h] [rbp+30h] BYREF
  mmcerror::SC *v16; // [rsp+88h] [rbp+38h]
  ULONG pcchLanguage; // [rsp+90h] [rbp+40h] BYREF

  v16 = a2;
  pcchFileMUIPath = a1;
  mmcerror::SC::SC(a2, 0);
  mmcerror::SC::SetFunctionName(a2, L"CAMCDoc::ScGetMuiPath");
  if ( a3 && *a3 )
  {
    pcchLanguage = 0;
    LODWORD(pcchFileMUIPath) = 0;
    pululEnumerator = 0;
    if ( GetFileMUIPath(0, a3, 0, &pcchLanguage, 0, (PULONG)&pcchFileMUIPath, &pululEnumerator) )
    {
      pwszFileMUIPath = (unsigned __int16 *)CHeapFactory::Alloc(v7, 2LL * (unsigned int)pcchFileMUIPath, v8);
      if ( !pwszFileMUIPath )
      {
        v9 = 2147942414LL;
        goto LABEL_9;
      }
      pcchLanguage = 0;
      if ( GetFileMUIPath(0, a3, 0, &pcchLanguage, pwszFileMUIPath, (PULONG)&pcchFileMUIPath, &pululEnumerator) )
      {
        v12 = CStr::Assign(a4, pwszFileMUIPath);
        mmcerror::SC::operator=(a2, v12);
        mmcerror::SC::IsError(a2);
      }
      else
      {
        mmcerror::SC::FromLastError(a2);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids);
        if ( !mmcerror::SC::IsError(a2) )
          mmcerror::SC::operator=(a2, 1);
      }
      CHeapFactory::Free(v11, pwszFileMUIPath);
    }
    else
    {
      mmcerror::SC::FromLastError(a2);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids);
      if ( !mmcerror::SC::IsError(a2) )
      {
        v9 = 1;
LABEL_9:
        mmcerror::SC::operator=(a2, v9);
      }
    }
  }
  else
  {
    mmcerror::SC::operator=(a2, 2147942487LL);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids);
  }
  return a2;
}

```

## disassembly

```asm
0x140054d20  mov     [rsp-28h+arg_8], rdx
0x140054d25  mov     [rsp-28h+arg_0], rcx
0x140054d2a  push    rbp
0x140054d2b  push    rbx
0x140054d2c  push    rsi
0x140054d2d  push    rdi
0x140054d2e  push    r14
0x140054d30  mov     rbp, rsp
0x140054d33  sub     rsp, 50h
0x140054d37  mov     r14, r9
0x140054d3a  mov     rsi, r8
0x140054d3d  mov     rbx, rdx
0x140054d40  mov     [rbp+var_10], 0
0x140054d47  xor     edx, edx
0x140054d49  mov     rcx, rbx
0x140054d4c  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140054d52  mov     [rbp+var_10], 1
0x140054d59  lea     rdx, aCamcdocScgetmu; "CAMCDoc::ScGetMuiPath"
0x140054d60  mov     rcx, rbx
0x140054d63  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140054d69  test    rsi, rsi
0x140054d6c  jz      loc_140054EDE
0x140054d72  xor     eax, eax
0x140054d74  cmp     ax, [rsi]
0x140054d77  jz      loc_140054EDE
0x140054d7d  mov     [rbp+pcchLanguage], eax
0x140054d80  mov     dword ptr [rbp+arg_0], eax
0x140054d83  mov     [rbp+var_8], rax
0x140054d87  lea     rax, [rbp+var_8]
0x140054d8b  mov     [rsp+50h+pululEnumerator], rax; pululEnumerator
0x140054d90  lea     rax, [rbp+arg_0]
0x140054d94  mov     [rsp+50h+pcchFileMUIPath], rax; pcchFileMUIPath
0x140054d99  mov     [rsp+50h+pwszFileMUIPath], 0; pwszFileMUIPath
0x140054da2  lea     r9, [rbp+pcchLanguage]; pcchLanguage
0x140054da6  xor     r8d, r8d; pwszLanguage
0x140054da9  mov     rdx, rsi; pcwszFilePath
0x140054dac  xor     ecx, ecx; dwFlags
0x140054dae  call    cs:__imp_GetFileMUIPath
0x140054db4  test    eax, eax
0x140054db6  jnz     short loc_140054E13
0x140054db8  mov     rcx, rbx
0x140054dbb  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x140054dc1  lea     rax, WPP_GLOBAL_Control
0x140054dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140054dcf  cmp     rcx, rax
0x140054dd2  jz      short loc_140054DEF
0x140054dd4  cmp     byte ptr [rcx+19h], 5
0x140054dd8  jb      short loc_140054DEF
0x140054dda  mov     edx, 16h
0x140054ddf  lea     r8, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids
0x140054de6  mov     rcx, [rcx+10h]
0x140054dea  call    WPP_SF_
0x140054def  mov     rcx, rbx
0x140054df2  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x140054df8  test    al, al
0x140054dfa  jnz     loc_140054F1A
0x140054e00  mov     edx, 1
0x140054e05  mov     rcx, rbx
0x140054e08  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054e0e  jmp     loc_140054F1A
0x140054e13  mov     edx, dword ptr [rbp+arg_0]
0x140054e16  add     rdx, rdx; unsigned __int64
0x140054e19  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x140054e1e  mov     rdi, rax
0x140054e21  test    rax, rax
0x140054e24  jnz     short loc_140054E2D
0x140054e26  mov     edx, 8007000Eh
0x140054e2b  jmp     short loc_140054E05
0x140054e2d  mov     [rbp+pcchLanguage], 0
0x140054e34  lea     rax, [rbp+var_8]
0x140054e38  mov     [rsp+50h+pululEnumerator], rax; pululEnumerator
0x140054e3d  lea     rax, [rbp+arg_0]
0x140054e41  mov     [rsp+50h+pcchFileMUIPath], rax; pcchFileMUIPath
0x140054e46  mov     [rsp+50h+pwszFileMUIPath], rdi; pwszFileMUIPath
0x140054e4b  lea     r9, [rbp+pcchLanguage]; pcchLanguage
0x140054e4f  xor     r8d, r8d; pwszLanguage
0x140054e52  mov     rdx, rsi; pcwszFilePath
0x140054e55  xor     ecx, ecx; dwFlags
0x140054e57  call    cs:__imp_GetFileMUIPath
0x140054e5d  test    eax, eax
0x140054e5f  jnz     short loc_140054EB5
0x140054e61  mov     rcx, rbx
0x140054e64  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x140054e6a  lea     rax, WPP_GLOBAL_Control
0x140054e71  mov     rcx, cs:WPP_GLOBAL_Control
0x140054e78  cmp     rcx, rax
0x140054e7b  jz      short loc_140054E98
0x140054e7d  cmp     byte ptr [rcx+19h], 5
0x140054e81  jb      short loc_140054E98
0x140054e83  mov     edx, 17h
0x140054e88  lea     r8, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids
0x140054e8f  mov     rcx, [rcx+10h]
0x140054e93  call    WPP_SF_
0x140054e98  mov     rcx, rbx
0x140054e9b  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x140054ea1  test    al, al
0x140054ea3  jnz     short loc_140054ED4
0x140054ea5  mov     edx, 1
0x140054eaa  mov     rcx, rbx
0x140054ead  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054eb3  jmp     short loc_140054ED4
0x140054eb5  mov     rdx, rdi; unsigned __int16 *
0x140054eb8  mov     rcx, r14; this
0x140054ebb  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x140054ec0  mov     edx, eax
0x140054ec2  mov     rcx, rbx
0x140054ec5  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054ecb  mov     rcx, rbx
0x140054ece  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x140054ed4  mov     rdx, rdi; void *
0x140054ed7  call    ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
0x140054edc  jmp     short loc_140054F1A
0x140054ede  mov     edx, 80070057h
0x140054ee3  mov     rcx, rbx
0x140054ee6  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140054eec  lea     rax, WPP_GLOBAL_Control
0x140054ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140054efa  cmp     rcx, rax
0x140054efd  jz      short loc_140054F1A
0x140054eff  cmp     byte ptr [rcx+19h], 2
0x140054f03  jb      short loc_140054F1A
0x140054f05  mov     edx, 15h
0x140054f0a  lea     r8, WPP_52b81e8ff91338b733ca1f96ced02381_Traceguids
0x140054f11  mov     rcx, [rcx+10h]
0x140054f15  call    WPP_SF_
0x140054f1a  mov     rax, rbx
0x140054f1d  add     rsp, 50h
0x140054f21  pop     r14
0x140054f23  pop     rdi
0x140054f24  pop     rsi
0x140054f25  pop     rbx
0x140054f26  pop     rbp
0x140054f27  retn
```
