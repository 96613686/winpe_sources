# DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)

- ea: `0x18002fb04`
- end: `0x18002fc47`
- name: `?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(const unsigned __int16 *, WCHAR *, char, DWORD *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000b540`
- `0x18002fc50`
- `0x180030624`
- `0x180032ce0`
- `0x180043b40`

## callees

- `0x180021bd0`
- `0x18002f89c`
- `0x18002fb04`
- `0x180031460`
- `0x180031518`
- `0x18003f42c`
- `0x180040e94`
- `0x180041024`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fc32`
- `USERENV!__imp_DeleteProfileDirectory` at `0x18002fbc3`
- `USERENV!__imp_DeleteProfileDirectory` at `0x18002fbc3`
- `USERENV!__imp_DeleteProfileDirectory2` at `0x18002fbbb`
- `USERENV!__imp_DeleteProfileDirectory2` at `0x18002fbbb`

## string_xrefs

- `0x18002fb5d`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002fb82`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

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
0x18002fb04  push    rbx
0x18002fb06  push    rbp
0x18002fb07  push    rsi
0x18002fb08  push    rdi
0x18002fb09  push    r14
0x18002fb0b  push    r15
0x18002fb0d  sub     rsp, 28h
0x18002fb11  xor     r15d, r15d
0x18002fb14  mov     rbp, r9
0x18002fb17  mov     dword ptr [rsp+58h+hMem], r15d
0x18002fb1c  mov     r14d, r8d
0x18002fb1f  mov     rdi, rdx
0x18002fb22  mov     rbx, rcx
0x18002fb25  mov     esi, r15d
0x18002fb28  test    rcx, rcx
0x18002fb2b  jz      short loc_18002FB96
0x18002fb2d  cmp     [rcx], r15w
0x18002fb31  jz      short loc_18002FB96
0x18002fb33  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002fb38  test    eax, eax
0x18002fb3a  jz      short loc_18002FB46
0x18002fb3c  mov     eax, 80070057h
0x18002fb41  jmp     loc_18002FC3A
0x18002fb46  test    r14b, 2
0x18002fb4a  jnz     short loc_18002FB71
0x18002fb4c  mov     rcx, rbx; lpString1
0x18002fb4f  call    ?DeleteProfileGuidEntry@@YAJPEBG@Z; DeleteProfileGuidEntry(ushort const *)
0x18002fb54  test    eax, eax
0x18002fb56  jns     short loc_18002FB71
0x18002fb58  mov     rcx, [rsp+58h]; this
0x18002fb5d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fb64  mov     r9d, eax; char *
0x18002fb67  mov     edx, 0BCh; void *
0x18002fb6c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fb71  mov     rcx, rbx; lpString1
0x18002fb74  call    ?DeleteProfileListEntry@@YAJPEBG@Z; DeleteProfileListEntry(ushort const *)
0x18002fb79  test    eax, eax
0x18002fb7b  jns     short loc_18002FB96
0x18002fb7d  mov     rcx, [rsp+58h]; this
0x18002fb82  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002fb89  mov     r9d, eax; char *
0x18002fb8c  mov     edx, 0C1h; void *
0x18002fb91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002fb96  test    rdi, rdi
0x18002fb99  jz      loc_18002FC38
0x18002fb9f  cmp     [rdi], r15w
0x18002fba3  jz      loc_18002FC38
0x18002fba9  xor     r8d, r8d; dwDesiredAccessMask
0x18002fbac  mov     rcx, rdi; pszFileName
0x18002fbaf  lea     edx, [r8+2]; pRsopToken
0x18002fbb3  test    rbp, rbp
0x18002fbb6  jz      short loc_18002FBC3
0x18002fbb8  mov     r9, rbp
0x18002fbbb  call    cs:__imp_DeleteProfileDirectory2
0x18002fbc1  jmp     short loc_18002FBC9
0x18002fbc3  call    cs:__imp_DeleteProfileDirectory
0x18002fbc9  mov     ebx, eax
0x18002fbcb  test    eax, eax
0x18002fbcd  jns     short loc_18002FC38
0x18002fbcf  test    r14b, 8
0x18002fbd3  jz      short loc_18002FBE3
0x18002fbd5  cmp     eax, 80070020h
0x18002fbda  jz      short loc_18002FC38
0x18002fbdc  cmp     eax, 80070091h
0x18002fbe1  jz      short loc_18002FC38
0x18002fbe3  mov     rcx, [rsp+58h]; this
0x18002fbe8  mov     r9d, ebx; char *
0x18002fbeb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002fbf0  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18002fbf7  jz      short loc_18002FC27
0x18002fbf9  mov     edx, ebx; dwMessageId
0x18002fbfb  lea     rcx, [rsp+58h+hMem]; lpBuffer
0x18002fc00  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18002fc05  lea     r9, asc_180060EA8; "???"
0x18002fc0c  mov     r8, rdi
0x18002fc0f  lea     rdx, EVENT_PROFILE_DIR_DELETE_FAIL
0x18002fc16  cmp     [rax], r15
0x18002fc19  cmovnz  r9, [rax]
0x18002fc1d  call    McTemplateU0zz_EtwEventWriteTransfer
0x18002fc22  mov     esi, 1
0x18002fc27  test    sil, 1
0x18002fc2b  jz      short loc_18002FC38
0x18002fc2d  mov     rcx, [rsp+58h+hMem]; hMem
0x18002fc32  call    cs:__imp_LocalFree
0x18002fc38  xor     eax, eax
0x18002fc3a  add     rsp, 28h
0x18002fc3e  pop     r15
0x18002fc40  pop     r14
0x18002fc42  pop     rdi
0x18002fc43  pop     rsi
0x18002fc44  pop     rbp
0x18002fc45  pop     rbx
0x18002fc46  retn
```
