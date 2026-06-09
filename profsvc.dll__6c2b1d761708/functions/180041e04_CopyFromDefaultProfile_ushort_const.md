# _CopyFromDefaultProfile(ushort const *)

- ea: `0x180041e04`
- end: `0x180041f0a`
- name: `?_CopyFromDefaultProfile@@YAJPEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(HANDLE hEvent)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180030050`

## callees

- `0x18000e1a0`
- `0x18002df48`
- `0x180030ad0`
- `0x180040bcc`
- `0x180041e04`

## import_xrefs

- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180041ec7`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180041ec7`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180041e9c`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180041e9c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180041e4c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180041e4c`

## string_xrefs

- `0x180041e63`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180041eb1`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180041edc`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

## pseudocode

```c
__int64 __fastcall _CopyFromDefaultProfile(HANDLE hEvent)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned int LastError; // ebx
  const char *v4; // r9
  BOOL DirectoryJunctionsForUserProfile; // eax
  int v7; // [rsp+20h] [rbp-38h]
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v8);
  v9 = -1;
  v10 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(2, 0, &v8);
  LastError = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc >= 0 )
  {
    if ( (unsigned int)CopyProfileDirectoryEx2(v8, hEvent, 819459, 0) )
    {
      DirectoryJunctionsForUserProfile = CreateDirectoryJunctionsForUserProfile(hEvent);
      if ( DirectoryJunctionsForUserProfile < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
          (const char *)DirectoryJunctionsForUserProfile,
          0);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x30,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
                    v4);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\create.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      v7);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v8);
  return LastError;
}

```

## disassembly

```asm
0x180041e04  mov     rax, rsp
0x180041e07  mov     [rax+8], rbx
0x180041e0b  push    rdi
0x180041e0c  sub     rsp, 50h
0x180041e10  mov     rdi, rcx
0x180041e13  mov     qword ptr [rax-28h], 0
0x180041e1b  lea     rcx, [rax-28h]
0x180041e1f  mov     qword ptr [rax-20h], 0
0x180041e27  mov     qword ptr [rax-18h], 0
0x180041e2f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180041e34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041e38  lea     r8, [rsp+58h+var_28]
0x180041e3d  xor     edx, edx
0x180041e3f  mov     [rsp+58h+var_20], rax
0x180041e44  mov     [rsp+58h+var_18], rax
0x180041e49  lea     ecx, [rax+3]
0x180041e4c  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180041e53  nop     dword ptr [rax+rax+00h]
0x180041e58  mov     ebx, eax
0x180041e5a  test    eax, eax
0x180041e5c  jns     short loc_180041E79
0x180041e5e  mov     rcx, [rsp+58h]; this
0x180041e63  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041e6a  mov     r9d, eax; char *
0x180041e6d  mov     edx, 26h ; '&'; void *
0x180041e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041e77  jmp     short loc_180041EF2
0x180041e79  mov     rcx, [rsp+58h+var_28]
0x180041e7e  xor     r9d, r9d
0x180041e81  mov     [rsp+58h+var_30], 0
0x180041e8a  mov     r8d, 0C8103h
0x180041e90  mov     rdx, rdi
0x180041e93  mov     qword ptr [rsp+58h+var_38], 0; int
0x180041e9c  call    cs:__imp_CopyProfileDirectoryEx2
0x180041ea3  nop     dword ptr [rax+rax+00h]
0x180041ea8  test    eax, eax
0x180041eaa  jnz     short loc_180041EC4
0x180041eac  mov     rcx, [rsp+58h]; this
0x180041eb1  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041eb8  lea     edx, [rax+30h]; void *
0x180041ebb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180041ec0  mov     ebx, eax
0x180041ec2  jmp     short loc_180041EF2
0x180041ec4  mov     rcx, rdi; hEvent
0x180041ec7  call    cs:__imp_CreateDirectoryJunctionsForUserProfile
0x180041ece  nop     dword ptr [rax+rax+00h]
0x180041ed3  test    eax, eax
0x180041ed5  jns     short loc_180041EF0
0x180041ed7  mov     rcx, [rsp+58h]; this
0x180041edc  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180041ee3  mov     r9d, eax; char *
0x180041ee6  mov     edx, 33h ; '3'; void *
0x180041eeb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041ef0  xor     ebx, ebx
0x180041ef2  lea     rcx, [rsp+58h+var_28]
0x180041ef7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180041efc  mov     eax, ebx
0x180041efe  mov     rbx, [rsp+58h+arg_0]
0x180041f03  add     rsp, 50h
0x180041f07  pop     rdi
0x180041f08  retn
```
