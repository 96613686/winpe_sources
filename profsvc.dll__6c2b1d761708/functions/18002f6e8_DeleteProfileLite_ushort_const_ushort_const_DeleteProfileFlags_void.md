# DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)

- ea: `0x18002f6e8`
- end: `0x18002f83e`
- name: `?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *, char, DWORD *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008fa0`
- `0x18002e1dc`
- `0x18002eae0`
- `0x18002ef18`
- `0x180045614`

## callees

- `0x180024be0`
- `0x18002f6e8`
- `0x180030008`
- `0x1800313e4`
- `0x1800314a4`
- `0x180040bcc`
- `0x180042880`
- `0x180042a14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f822`
- `USERENV!__imp_DeleteProfileDirectory` at `0x18002f7ad`
- `USERENV!__imp_DeleteProfileDirectory` at `0x18002f7ad`
- `USERENV!__imp_DeleteProfileDirectory2` at `0x18002f79f`
- `USERENV!__imp_DeleteProfileDirectory2` at `0x18002f79f`

## string_xrefs

- `0x18002f741`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002f766`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

## pseudocode

```c
__int64 __fastcall DeleteProfileLite(const unsigned __int16 *a1, WCHAR *a2, char a3, DWORD *a4)
{
  char v8; // si
  int v10; // eax
  int v11; // eax
  int v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  DWORD v15; // ebx
  const wchar_t **v16; // rax
  __int64 v17; // rcx
  const wchar_t *v18; // r9
  WINBOOL *v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  LODWORD(hMem) = 0;
  v8 = 0;
  if ( a1 && *a1 )
  {
    if ( (unsigned int)IsProfileInUse(a1) )
      return 2147942487LL;
    if ( (a3 & 2) == 0 )
    {
      v10 = DeleteProfileGuidEntry(a1);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v10,
          (int)v19);
    }
    v11 = DeleteProfileListEntry(a1);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)(unsigned int)v11,
        (int)v19);
  }
  if ( a2 && *a2 )
  {
    v12 = a4 ? DeleteProfileDirectory2(a2, 2, 0, a4) : DeleteProfileDirectory(a2, (PRSOPTOKEN)2, 0, a4, v19);
    v15 = v12;
    if ( v12 < 0 && ((a3 & 8) == 0 || v12 != -2147024864 && v12 != -2147024751) )
    {
      wil::details::in1diag3::Log_Hr(retaddr, v13, v14, (const char *)(unsigned int)v12, (int)v19);
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
      {
        v16 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v15);
        v18 = L"???";
        if ( *v16 )
          v18 = *v16;
        McTemplateU0zz_EtwEventWriteTransfer(v17, EVENT_PROFILE_DIR_DELETE_FAIL, a2, v18);
        v8 = 1;
      }
      if ( (v8 & 1) != 0 )
        LocalFree(hMem);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002f6e8  push    rbx
0x18002f6ea  push    rbp
0x18002f6eb  push    rsi
0x18002f6ec  push    rdi
0x18002f6ed  push    r14
0x18002f6ef  push    r15
0x18002f6f1  sub     rsp, 28h
0x18002f6f5  xor     r15d, r15d
0x18002f6f8  mov     rbp, r9
0x18002f6fb  mov     dword ptr [rsp+58h+hMem], r15d
0x18002f700  mov     r14d, r8d
0x18002f703  mov     rdi, rdx
0x18002f706  mov     rbx, rcx
0x18002f709  mov     esi, r15d
0x18002f70c  test    rcx, rcx
0x18002f70f  jz      short loc_18002F77A
0x18002f711  cmp     [rcx], r15w
0x18002f715  jz      short loc_18002F77A
0x18002f717  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002f71c  test    eax, eax
0x18002f71e  jz      short loc_18002F72A
0x18002f720  mov     eax, 80070057h
0x18002f725  jmp     loc_18002F830
0x18002f72a  test    r14b, 2
0x18002f72e  jnz     short loc_18002F755
0x18002f730  mov     rcx, rbx; lpString1
0x18002f733  call    ?DeleteProfileGuidEntry@@YAJPEBG@Z; DeleteProfileGuidEntry(ushort const *)
0x18002f738  test    eax, eax
0x18002f73a  jns     short loc_18002F755
0x18002f73c  mov     rcx, [rsp+58h]; this
0x18002f741  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f748  mov     r9d, eax; char *
0x18002f74b  mov     edx, 0BCh; void *
0x18002f750  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f755  mov     rcx, rbx; lpString1
0x18002f758  call    ?DeleteProfileListEntry@@YAJPEBG@Z; DeleteProfileListEntry(ushort const *)
0x18002f75d  test    eax, eax
0x18002f75f  jns     short loc_18002F77A
0x18002f761  mov     rcx, [rsp+58h]; this
0x18002f766  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f76d  mov     r9d, eax; char *
0x18002f770  mov     edx, 0C1h; void *
0x18002f775  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f77a  test    rdi, rdi
0x18002f77d  jz      loc_18002F82E
0x18002f783  cmp     [rdi], r15w
0x18002f787  jz      loc_18002F82E
0x18002f78d  xor     r8d, r8d; dwDesiredAccessMask
0x18002f790  mov     rcx, rdi; pszFileName
0x18002f793  lea     edx, [r8+2]; pRsopToken
0x18002f797  test    rbp, rbp
0x18002f79a  jz      short loc_18002F7AD
0x18002f79c  mov     r9, rbp
0x18002f79f  call    cs:__imp_DeleteProfileDirectory2
0x18002f7a6  nop     dword ptr [rax+rax+00h]
0x18002f7ab  jmp     short loc_18002F7B9
0x18002f7ad  call    cs:__imp_DeleteProfileDirectory
0x18002f7b4  nop     dword ptr [rax+rax+00h]
0x18002f7b9  mov     ebx, eax
0x18002f7bb  test    eax, eax
0x18002f7bd  jns     short loc_18002F82E
0x18002f7bf  test    r14b, 8
0x18002f7c3  jz      short loc_18002F7D3
0x18002f7c5  cmp     eax, 80070020h
0x18002f7ca  jz      short loc_18002F82E
0x18002f7cc  cmp     eax, 80070091h
0x18002f7d1  jz      short loc_18002F82E
0x18002f7d3  mov     rcx, [rsp+58h]; this
0x18002f7d8  mov     r9d, ebx; char *
0x18002f7db  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002f7e0  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18002f7e7  jz      short loc_18002F817
0x18002f7e9  mov     edx, ebx; dwMessageId
0x18002f7eb  lea     rcx, [rsp+58h+hMem]; lpBuffer
0x18002f7f0  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18002f7f5  lea     r9, asc_180063710; "???"
0x18002f7fc  mov     r8, rdi
0x18002f7ff  lea     rdx, EVENT_PROFILE_DIR_DELETE_FAIL
0x18002f806  cmp     [rax], r15
0x18002f809  cmovnz  r9, [rax]
0x18002f80d  call    McTemplateU0zz_EtwEventWriteTransfer
0x18002f812  mov     esi, 1
0x18002f817  test    sil, 1
0x18002f81b  jz      short loc_18002F82E
0x18002f81d  mov     rcx, [rsp+58h+hMem]; hMem
0x18002f822  call    cs:__imp_LocalFree
0x18002f829  nop     dword ptr [rax+rax+00h]
0x18002f82e  xor     eax, eax
0x18002f830  add     rsp, 28h
0x18002f834  pop     r15
0x18002f836  pop     r14
0x18002f838  pop     rdi
0x18002f839  pop     rsi
0x18002f83a  pop     rbp
0x18002f83b  pop     rbx
0x18002f83c  retn
```
