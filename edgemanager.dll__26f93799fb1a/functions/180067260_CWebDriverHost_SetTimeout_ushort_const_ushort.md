# CWebDriverHost::_SetTimeout(ushort const *,ushort * *)

- ea: `0x180067260`
- end: `0x180067437`
- name: `?_SetTimeout@CWebDriverHost@@AEAA?AW4WebDriverResponseCode@@PEBGPEAPEAG@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180065cd0`

## callees

- `0x18001afe4`
- `0x18001b038`
- `0x18001b178`
- `0x180020bec`
- `0x18002b530`
- `0x1800653e0`
- `0x180067260`
- `0x180067dd8`
- `0x180079594`
- `0x1800797f4`
- `0x180079924`
- `0x1800799c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006736c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006736c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800673f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800673f4`

## string_xrefs

- `0x180067365`: `edgehtml.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWebDriverHost::_SetTimeout(__int64 a1, __int64 a2, unsigned __int16 **a3)
{
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rcx
  signed int v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // r13d
  unsigned int v10; // r15d
  unsigned int v11; // ebx
  HMODULE Library; // rax
  HMODULE v13; // rsi
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  int v18; // [rsp+48h] [rbp-31h]
  int v19; // [rsp+4Ch] [rbp-2Dh]
  __int64 v20; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-21h] BYREF
  struct JSONNode *v22; // [rsp+60h] [rbp-19h] BYREF
  char v23; // [rsp+68h] [rbp-11h]
  _BYTE v24[32]; // [rsp+70h] [rbp-9h] BYREF

  std::wstring::wstring(v24);
  v20 = 0;
  v17 = 0;
  v19 = -1;
  v18 = -1;
  v21 = &v20;
  v22 = 0;
  v23 = 1;
  ParseJson((struct WebDriverReturnResponse *)&v17, v5, &v22);
  wil::details::out_param_t<std::unique_ptr<JSONNode>>::~out_param_t<std::unique_ptr<JSONNode>>(&v21);
  if ( !(_DWORD)v17 && v20 && *(_DWORD *)v20 == 5 && (v6 = *(_QWORD *)(v20 + 8)) != 0 )
  {
    v7 = SetW3CTimeoutValue(v6, (int)a1 + 160, (int)a1 + 164, (int)a1 + 168, (__int64)&v17);
    v8 = v19;
    v9 = v18;
    v10 = HIDWORD(v17);
    v11 = v17;
  }
  else
  {
    v7 = -1;
    v11 = 13;
    v10 = 50433;
    v8 = -1;
    v9 = -1;
  }
  if ( v11 )
  {
    Library = LoadLibraryExW(L"edgehtml.dll", 0, 0x60u);
    v13 = Library;
    if ( v9 == -1 )
    {
      if ( v8 != -1 )
      {
        ConvertCodeToName(v8);
        LoadResourceStringAndGenerateErrorResponse(v13, v10, v15, v11, a3);
        goto LABEL_17;
      }
    }
    else if ( v8 != -1 )
    {
      ConvertCodeToName(v8);
      ConvertCodeToName(v9);
      LoadResourceStringAndGenerateErrorResponse(v13, v10, v14, v11, a3);
LABEL_17:
      FreeLibrary(v13);
      goto LABEL_18;
    }
    LoadResourceStringAndGenerateErrorResponse(Library, v10, *(_QWORD *)(a1 + 176), v11, a3);
    goto LABEL_17;
  }
  if ( v7 > 300000 )
    CWebDriverDispatcher::PackAndPostIncreaseTimeoutMessage(*(CWebDriverDispatcher **)(a1 + 144), v7);
  GenerateSuccessResponse(*(const unsigned __int16 **)(a1 + 176), a3);
LABEL_18:
  std::unique_ptr<JSONNode>::~unique_ptr<JSONNode>(&v20);
  std::wstring::_Tidy_deallocate(v24);
  return v11;
}

```

## disassembly

```asm
0x180067260  mov     [rsp-8+arg_18], rbx
0x180067265  push    rbp
0x180067266  push    rsi
0x180067267  push    rdi
0x180067268  push    r12
0x18006726a  push    r13
0x18006726c  push    r14
0x18006726e  push    r15
0x180067270  lea     rbp, [rsp-27h]
0x180067275  sub     rsp, 0A0h
0x18006727c  mov     rax, cs:__security_cookie
0x180067283  xor     rax, rsp
0x180067286  mov     [rbp+57h+var_40], rax
0x18006728a  mov     r12, r8
0x18006728d  mov     r14, rcx
0x180067290  lea     rcx, [rbp+57h+var_60]
0x180067294  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180067299  nop
0x18006729a  xor     ebx, ebx
0x18006729c  mov     [rbp+57h+var_80], rbx
0x1800672a0  mov     [rbp+57h+var_90], rbx
0x1800672a4  or      esi, 0FFFFFFFFh
0x1800672a7  mov     [rbp+57h+var_84], esi
0x1800672aa  mov     [rbp+57h+var_88], esi
0x1800672ad  lea     rax, [rbp+57h+var_80]
0x1800672b1  mov     [rbp+57h+var_78], rax
0x1800672b5  mov     [rbp+57h+var_70], rbx
0x1800672b9  mov     [rbp+57h+var_68], 1
0x1800672bd  lea     r8, [rbp+57h+var_70]; struct JSONNode **
0x1800672c1  lea     rcx, [rbp+57h+var_90]; struct WebDriverReturnResponse *
0x1800672c5  call    ?ParseJson@@YAXPEAUWebDriverReturnResponse@@PEBGPEAPEAUJSONNode@@@Z; ParseJson(WebDriverReturnResponse *,ushort const *,JSONNode * *)
0x1800672ca  nop
0x1800672cb  lea     rcx, [rbp+57h+var_78]
0x1800672cf  call    ??1?$out_param_t@V?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<JSONNode>>::~out_param_t<std::unique_ptr<JSONNode>>(void)
0x1800672d4  cmp     dword ptr [rbp+57h+var_90], ebx
0x1800672d7  jnz     short loc_180067320
0x1800672d9  mov     rax, [rbp+57h+var_80]
0x1800672dd  test    rax, rax
0x1800672e0  jz      short loc_180067320
0x1800672e2  cmp     dword ptr [rax], 5
0x1800672e5  jnz     short loc_180067320
0x1800672e7  mov     rcx, [rax+8]
0x1800672eb  test    rcx, rcx
0x1800672ee  jz      short loc_180067320
0x1800672f0  lea     rdx, [r14+0A0h]
0x1800672f7  lea     r9, [r14+0A8h]
0x1800672fe  lea     r8, [rdx+4]
0x180067302  lea     rax, [rbp+57h+var_90]
0x180067306  mov     [rsp+0D0h+var_B0], rax
0x18006730b  call    ?SetW3CTimeoutValue@@YAHPEAV?$NtMap@PEBGPEAUJSONNode@@UlessPCWSTR@@VJSONUtilsAllocator@@@@PEAK11PEAUWebDriverReturnResponse@@@Z; SetW3CTimeoutValue(NtMap<ushort const *,JSONNode *,lessPCWSTR,JSONUtilsAllocator> *,ulong *,ulong *,ulong *,WebDriverReturnResponse *)
0x180067310  mov     edi, [rbp+57h+var_84]
0x180067313  mov     r13d, [rbp+57h+var_88]
0x180067317  mov     r15d, dword ptr [rbp+57h+var_90+4]
0x18006731b  mov     ebx, dword ptr [rbp+57h+var_90]
0x18006731e  jmp     short loc_180067332
0x180067320  mov     eax, esi
0x180067322  mov     ebx, 0Dh
0x180067327  mov     r15d, 0C501h
0x18006732d  mov     edi, esi
0x18006732f  mov     r13d, esi
0x180067332  test    ebx, ebx
0x180067334  jnz     short loc_18006735F
0x180067336  cmp     eax, 493E0h
0x18006733b  jle     short loc_18006734B
0x18006733d  mov     edx, eax; unsigned int
0x18006733f  mov     rcx, [r14+90h]; this
0x180067346  call    ?PackAndPostIncreaseTimeoutMessage@CWebDriverDispatcher@@QEAAXK@Z; CWebDriverDispatcher::PackAndPostIncreaseTimeoutMessage(ulong)
0x18006734b  mov     rdx, r12; unsigned __int16 **
0x18006734e  mov     rcx, [r14+0B0h]; unsigned __int16 *
0x180067355  call    ?GenerateSuccessResponse@@YAXPEBGPEAPEAG@Z; GenerateSuccessResponse(ushort const *,ushort * *)
0x18006735a  jmp     loc_1800673FB
0x18006735f  xor     edx, edx; hFile
0x180067361  lea     r8d, [rdx+60h]; dwFlags
0x180067365  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x18006736c  call    cs:__imp_LoadLibraryExW
0x180067372  mov     rsi, rax
0x180067375  mov     r8, [r14+0B0h]
0x18006737c  cmp     r13d, 0FFFFFFFFh
0x180067380  jz      short loc_1800673B8
0x180067382  cmp     edi, 0FFFFFFFFh
0x180067385  jz      short loc_1800673DE
0x180067387  mov     ecx, edi
0x180067389  call    ?ConvertCodeToName@@YAPEBGW4WebDriverName@@@Z; ConvertCodeToName(WebDriverName)
0x18006738e  mov     r9, rax
0x180067391  mov     ecx, r13d
0x180067394  call    ?ConvertCodeToName@@YAPEBGW4WebDriverName@@@Z; ConvertCodeToName(WebDriverName)
0x180067399  mov     [rsp+0D0h+var_A0], r9
0x18006739e  mov     [rsp+0D0h+var_A8], rax
0x1800673a3  mov     [rsp+0D0h+var_B0], r12
0x1800673a8  mov     r9d, ebx
0x1800673ab  mov     edx, r15d
0x1800673ae  mov     rcx, rsi
0x1800673b1  call    ?LoadResourceStringAndGenerateErrorResponse@@YAJQEAUHINSTANCE__@@IPEBGW4WebDriverResponseCode@@PEAPEAGZZ; LoadResourceStringAndGenerateErrorResponse(HINSTANCE__ * const,uint,ushort const *,WebDriverResponseCode,ushort * *,...)
0x1800673b6  jmp     short loc_1800673F1
0x1800673b8  cmp     edi, 0FFFFFFFFh
0x1800673bb  jz      short loc_1800673DE
0x1800673bd  mov     ecx, edi
0x1800673bf  call    ?ConvertCodeToName@@YAPEBGW4WebDriverName@@@Z; ConvertCodeToName(WebDriverName)
0x1800673c4  mov     [rsp+0D0h+var_A8], rax
0x1800673c9  mov     [rsp+0D0h+var_B0], r12
0x1800673ce  mov     r9d, ebx
0x1800673d1  mov     edx, r15d
0x1800673d4  mov     rcx, rsi
0x1800673d7  call    ?LoadResourceStringAndGenerateErrorResponse@@YAJQEAUHINSTANCE__@@IPEBGW4WebDriverResponseCode@@PEAPEAGZZ; LoadResourceStringAndGenerateErrorResponse(HINSTANCE__ * const,uint,ushort const *,WebDriverResponseCode,ushort * *,...)
0x1800673dc  jmp     short loc_1800673F1
0x1800673de  mov     [rsp+0D0h+var_B0], r12
0x1800673e3  mov     r9d, ebx
0x1800673e6  mov     edx, r15d
0x1800673e9  mov     rcx, rsi
0x1800673ec  call    ?LoadResourceStringAndGenerateErrorResponse@@YAJQEAUHINSTANCE__@@IPEBGW4WebDriverResponseCode@@PEAPEAGZZ; LoadResourceStringAndGenerateErrorResponse(HINSTANCE__ * const,uint,ushort const *,WebDriverResponseCode,ushort * *,...)
0x1800673f1  mov     rcx, rsi; hLibModule
0x1800673f4  call    cs:__imp_FreeLibrary
0x1800673fa  nop
0x1800673fb  lea     rcx, [rbp+57h+var_80]
0x1800673ff  call    ??1?$unique_ptr@UJSONNode@@U?$default_delete@UJSONNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<JSONNode>::~unique_ptr<JSONNode>(void)
0x180067404  nop
0x180067405  lea     rcx, [rbp+57h+var_60]
0x180067409  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006740e  mov     eax, ebx
0x180067410  mov     rcx, [rbp+57h+var_40]
0x180067414  xor     rcx, rsp; StackCookie
0x180067417  call    __security_check_cookie
0x18006741c  mov     rbx, [rsp+0D0h+arg_18]
0x180067424  add     rsp, 0A0h
0x18006742b  pop     r15
0x18006742d  pop     r14
0x18006742f  pop     r13
0x180067431  pop     r12
0x180067433  pop     rdi
0x180067434  pop     rsi
0x180067435  pop     rbp
0x180067436  retn
```
