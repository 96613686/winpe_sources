# RegisterServer

- ea: `0x180015474`
- end: `0x180015627`
- name: `RegisterServer`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d620`

## callees

- `0x1800016d0`
- `0x180015150`
- `0x180015254`
- `0x1800153c8`
- `0x180015474`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180015528`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x180015528`

## string_xrefs

- `0x1800154ca`: `CLSID\`
- `0x1800155bd`: `CLSID`
- `0x1800155f9`: `CLSID`
- `0x18001555f`: `ThreadingModel`

## pseudocode

```c
HRESULT __fastcall RegisterServer(__int64 a1, const struct _GUID *a2, BYTE *a3, BYTE *a4, BYTE *lpData)
{
  HMODULE v5; // r14
  HRESULT result; // eax
  const char *v9; // rcx
  __int64 v10; // r9
  CHAR *v11; // r8
  __int64 v12; // rax
  CHAR *v13; // rax
  BYTE Data[48]; // [rsp+20h] [rbp-E0h] BYREF
  CHAR SubKey[256]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Filename[512]; // [rsp+150h] [rbp+50h] BYREF

  v5 = g_hModule;
  result = CLSIDToStr(a2, (char *)Data);
  if ( result >= 0 )
  {
    v9 = "CLSID\\";
    v10 = 256;
    v11 = SubKey;
    v12 = 2147483646;
    do
    {
      if ( !v12 )
        break;
      if ( !*v9 )
        break;
      *v11++ = *v9++;
      --v12;
      --v10;
    }
    while ( v10 );
    v13 = v11 - 1;
    if ( v10 )
      v13 = v11;
    *v13 = 0;
    StringCchCatA(SubKey, 0x100u, (const char *)Data);
    GetModuleFileNameA(v5, Filename, 0x200u);
    RegSetDefValue(SubKey, 0, 0, a3);
    RegSetDefValue(SubKey, "InProcServer32", 0, (BYTE *)Filename);
    RegSetDefValue(SubKey, "InProcServer32", "ThreadingModel", (BYTE *)"Both");
    RegSetDefValue(SubKey, "ProgID", 0, lpData);
    RegSetDefValue(SubKey, "VersionIndependentProgID", 0, a4);
    RegSetDefValue((char *)a4, 0, 0, a3);
    RegSetDefValue((char *)a4, "CLSID", 0, Data);
    RegSetDefValue((char *)a4, "CurVer", 0, lpData);
    RegSetDefValue((char *)lpData, 0, 0, a3);
    RegSetDefValue((char *)lpData, "CLSID", 0, Data);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015474  push    rbp
0x180015476  push    rbx
0x180015477  push    rsi
0x180015478  push    rdi
0x180015479  push    r14
0x18001547b  lea     rbp, [rsp-260h]
0x180015483  sub     rsp, 360h
0x18001548a  mov     rax, cs:__security_cookie
0x180015491  xor     rax, rsp
0x180015494  mov     [rbp+280h+var_30], rax
0x18001549b  mov     rdi, [rbp+280h+lpData]
0x1800154a2  mov     rcx, rdx; struct _GUID *
0x1800154a5  mov     r14, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x1800154ac  lea     rdx, [rsp+380h+Data]; char *
0x1800154b1  mov     rbx, r9
0x1800154b4  mov     rsi, r8
0x1800154b7  call    ?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z; CLSIDToStr(_GUID const &,char *,int)
0x1800154bc  test    eax, eax
0x1800154be  js      loc_18001560A
0x1800154c4  mov     r10d, 100h
0x1800154ca  lea     rcx, aClsid; "CLSID\\"
0x1800154d1  mov     r9d, r10d
0x1800154d4  lea     r8, [rsp+380h+SubKey]
0x1800154d9  mov     eax, 7FFFFFFEh
0x1800154de  test    rax, rax
0x1800154e1  jz      short loc_1800154FB
0x1800154e3  mov     dl, [rcx]
0x1800154e5  test    dl, dl
0x1800154e7  jz      short loc_1800154FB
0x1800154e9  mov     [r8], dl
0x1800154ec  inc     rcx
0x1800154ef  inc     r8
0x1800154f2  dec     rax
0x1800154f5  sub     r9, 1
0x1800154f9  jnz     short loc_1800154DE
0x1800154fb  lea     rax, [r8-1]
0x1800154ff  test    r9, r9
0x180015502  mov     rdx, r10; unsigned __int64
0x180015505  lea     rcx, [rsp+380h+SubKey]; char *
0x18001550a  cmovnz  rax, r8
0x18001550e  lea     r8, [rsp+380h+Data]; char *
0x180015513  mov     byte ptr [rax], 0
0x180015516  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18001551b  mov     r8d, 200h; nSize
0x180015521  lea     rdx, [rbp+280h+Filename]; lpFilename
0x180015525  mov     rcx, r14; hModule
0x180015528  call    cs:__imp_GetModuleFileNameA
0x18001552e  mov     r9, rsi; lpData
0x180015531  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x180015536  xor     r8d, r8d; lpValueName
0x180015539  xor     edx, edx; char *
0x18001553b  call    RegSetDefValue
0x180015540  lea     r9, [rbp+280h+Filename]; lpData
0x180015544  xor     r8d, r8d; lpValueName
0x180015547  lea     rdx, aInprocserver32; "InProcServer32"
0x18001554e  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x180015553  call    RegSetDefValue
0x180015558  lea     r9, Data; "Both"
0x18001555f  lea     r8, aThreadingmodel; "ThreadingModel"
0x180015566  lea     rdx, aInprocserver32; "InProcServer32"
0x18001556d  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x180015572  call    RegSetDefValue
0x180015577  mov     r9, rdi; lpData
0x18001557a  lea     rdx, aProgid; "ProgID"
0x180015581  xor     r8d, r8d; lpValueName
0x180015584  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x180015589  call    RegSetDefValue
0x18001558e  mov     r9, rbx; lpData
0x180015591  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x180015598  xor     r8d, r8d; lpValueName
0x18001559b  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x1800155a0  call    RegSetDefValue
0x1800155a5  mov     r9, rsi; lpData
0x1800155a8  xor     r8d, r8d; lpValueName
0x1800155ab  xor     edx, edx; char *
0x1800155ad  mov     rcx, rbx; lpSubKey
0x1800155b0  call    RegSetDefValue
0x1800155b5  lea     r9, [rsp+380h+Data]; lpData
0x1800155ba  xor     r8d, r8d; lpValueName
0x1800155bd  lea     rdx, aClsid_0; "CLSID"
0x1800155c4  mov     rcx, rbx; lpSubKey
0x1800155c7  call    RegSetDefValue
0x1800155cc  mov     r9, rdi; lpData
0x1800155cf  lea     rdx, aCurver; "CurVer"
0x1800155d6  xor     r8d, r8d; lpValueName
0x1800155d9  mov     rcx, rbx; lpSubKey
0x1800155dc  call    RegSetDefValue
0x1800155e1  mov     r9, rsi; lpData
0x1800155e4  xor     r8d, r8d; lpValueName
0x1800155e7  xor     edx, edx; char *
0x1800155e9  mov     rcx, rdi; lpSubKey
0x1800155ec  call    RegSetDefValue
0x1800155f1  lea     r9, [rsp+380h+Data]; lpData
0x1800155f6  xor     r8d, r8d; lpValueName
0x1800155f9  lea     rdx, aClsid_0; "CLSID"
0x180015600  mov     rcx, rdi; lpSubKey
0x180015603  call    RegSetDefValue
0x180015608  xor     eax, eax
0x18001560a  mov     rcx, [rbp+280h+var_30]
0x180015611  xor     rcx, rsp; StackCookie
0x180015614  call    __security_check_cookie
0x180015619  add     rsp, 360h
0x180015620  pop     r14
0x180015622  pop     rdi
0x180015623  pop     rsi
0x180015624  pop     rbx
0x180015625  pop     rbp
0x180015626  retn
```
