# _CopyFromDefaultProfile(ushort const *)

- ea: `0x18004066c`
- end: `0x18004075f`
- name: `?_CopyFromDefaultProfile@@YAJPEBG@Z`
- size: `243`
- prototype: `__int64 __fastcall(HANDLE hEvent)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002ed00`

## callees

- `0x1800111a0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003f42c`
- `0x18004066c`

## import_xrefs

- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180040723`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x180040723`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x1800406fe`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x1800406fe`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800406b4`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800406b4`

## string_xrefs

- `0x1800406c5`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x18004070d`: `onecore\ds\security\gina\profile\profsvc\create.cpp`
- `0x180040732`: `onecore\ds\security\gina\profile\profsvc\create.cpp`

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
0x18004066c  mov     rax, rsp
0x18004066f  mov     [rax+8], rbx
0x180040673  push    rdi
0x180040674  sub     rsp, 50h
0x180040678  mov     rdi, rcx
0x18004067b  mov     qword ptr [rax-28h], 0
0x180040683  lea     rcx, [rax-28h]
0x180040687  mov     qword ptr [rax-20h], 0
0x18004068f  mov     qword ptr [rax-18h], 0
0x180040697  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004069c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800406a0  lea     r8, [rsp+58h+var_28]
0x1800406a5  xor     edx, edx
0x1800406a7  mov     [rsp+58h+var_20], rax
0x1800406ac  mov     [rsp+58h+var_18], rax
0x1800406b1  lea     ecx, [rax+3]
0x1800406b4  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800406ba  mov     ebx, eax
0x1800406bc  test    eax, eax
0x1800406be  jns     short loc_1800406DB
0x1800406c0  mov     rcx, [rsp+58h]; this
0x1800406c5  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800406cc  mov     r9d, eax; char *
0x1800406cf  mov     edx, 26h ; '&'; void *
0x1800406d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800406d9  jmp     short loc_180040748
0x1800406db  mov     rcx, [rsp+58h+var_28]
0x1800406e0  xor     r9d, r9d
0x1800406e3  mov     [rsp+58h+var_30], 0
0x1800406ec  mov     r8d, 0C8103h
0x1800406f2  mov     rdx, rdi
0x1800406f5  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800406fe  call    cs:__imp_CopyProfileDirectoryEx2
0x180040704  test    eax, eax
0x180040706  jnz     short loc_180040720
0x180040708  mov     rcx, [rsp+58h]; this
0x18004070d  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180040714  lea     edx, [rax+30h]; void *
0x180040717  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004071c  mov     ebx, eax
0x18004071e  jmp     short loc_180040748
0x180040720  mov     rcx, rdi; hEvent
0x180040723  call    cs:__imp_CreateDirectoryJunctionsForUserProfile
0x180040729  test    eax, eax
0x18004072b  jns     short loc_180040746
0x18004072d  mov     rcx, [rsp+58h]; this
0x180040732  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\gina\\profile\\p"...
0x180040739  mov     r9d, eax; char *
0x18004073c  mov     edx, 33h ; '3'; void *
0x180040741  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040746  xor     ebx, ebx
0x180040748  lea     rcx, [rsp+58h+var_28]
0x18004074d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180040752  mov     eax, ebx
0x180040754  mov     rbx, [rsp+58h+arg_0]
0x180040759  add     rsp, 50h
0x18004075d  pop     rdi
0x18004075e  retn
```
