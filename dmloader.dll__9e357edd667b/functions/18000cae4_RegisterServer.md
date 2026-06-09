# RegisterServer

- ea: `0x18000cae4`
- end: `0x18000cc97`
- name: `RegisterServer`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007d40`

## callees

- `0x1800015d0`
- `0x18000c7c0`
- `0x18000c8c4`
- `0x18000ca38`
- `0x18000cae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000cb98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000cb98`

## string_xrefs

- `0x18000cb3a`: `CLSID\`
- `0x18000cc2d`: `CLSID`
- `0x18000cc69`: `CLSID`
- `0x18000cbcf`: `ThreadingModel`

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
0x18000cae4  push    rbp
0x18000cae6  push    rbx
0x18000cae7  push    rsi
0x18000cae8  push    rdi
0x18000cae9  push    r14
0x18000caeb  lea     rbp, [rsp-260h]
0x18000caf3  sub     rsp, 360h
0x18000cafa  mov     rax, cs:__security_cookie
0x18000cb01  xor     rax, rsp
0x18000cb04  mov     [rbp+280h+var_30], rax
0x18000cb0b  mov     rdi, [rbp+280h+lpData]
0x18000cb12  mov     rcx, rdx; struct _GUID *
0x18000cb15  mov     r14, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x18000cb1c  lea     rdx, [rsp+380h+Data]; char *
0x18000cb21  mov     rbx, r9
0x18000cb24  mov     rsi, r8
0x18000cb27  call    ?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z; CLSIDToStr(_GUID const &,char *,int)
0x18000cb2c  test    eax, eax
0x18000cb2e  js      loc_18000CC7A
0x18000cb34  mov     r10d, 100h
0x18000cb3a  lea     rcx, aClsid; "CLSID\\"
0x18000cb41  mov     r9d, r10d
0x18000cb44  lea     r8, [rsp+380h+SubKey]
0x18000cb49  mov     eax, 7FFFFFFEh
0x18000cb4e  test    rax, rax
0x18000cb51  jz      short loc_18000CB6B
0x18000cb53  mov     dl, [rcx]
0x18000cb55  test    dl, dl
0x18000cb57  jz      short loc_18000CB6B
0x18000cb59  mov     [r8], dl
0x18000cb5c  inc     rcx
0x18000cb5f  inc     r8
0x18000cb62  dec     rax
0x18000cb65  sub     r9, 1
0x18000cb69  jnz     short loc_18000CB4E
0x18000cb6b  lea     rax, [r8-1]
0x18000cb6f  test    r9, r9
0x18000cb72  mov     rdx, r10; unsigned __int64
0x18000cb75  lea     rcx, [rsp+380h+SubKey]; char *
0x18000cb7a  cmovnz  rax, r8
0x18000cb7e  lea     r8, [rsp+380h+Data]; char *
0x18000cb83  mov     byte ptr [rax], 0
0x18000cb86  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18000cb8b  mov     r8d, 200h; nSize
0x18000cb91  lea     rdx, [rbp+280h+Filename]; lpFilename
0x18000cb95  mov     rcx, r14; hModule
0x18000cb98  call    cs:__imp_GetModuleFileNameA
0x18000cb9e  mov     r9, rsi; lpData
0x18000cba1  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x18000cba6  xor     r8d, r8d; lpValueName
0x18000cba9  xor     edx, edx; char *
0x18000cbab  call    RegSetDefValue
0x18000cbb0  lea     r9, [rbp+280h+Filename]; lpData
0x18000cbb4  xor     r8d, r8d; lpValueName
0x18000cbb7  lea     rdx, aInprocserver32; "InProcServer32"
0x18000cbbe  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x18000cbc3  call    RegSetDefValue
0x18000cbc8  lea     r9, Data; "Both"
0x18000cbcf  lea     r8, aThreadingmodel; "ThreadingModel"
0x18000cbd6  lea     rdx, aInprocserver32; "InProcServer32"
0x18000cbdd  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x18000cbe2  call    RegSetDefValue
0x18000cbe7  mov     r9, rdi; lpData
0x18000cbea  lea     rdx, aProgid; "ProgID"
0x18000cbf1  xor     r8d, r8d; lpValueName
0x18000cbf4  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x18000cbf9  call    RegSetDefValue
0x18000cbfe  mov     r9, rbx; lpData
0x18000cc01  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x18000cc08  xor     r8d, r8d; lpValueName
0x18000cc0b  lea     rcx, [rsp+380h+SubKey]; lpSubKey
0x18000cc10  call    RegSetDefValue
0x18000cc15  mov     r9, rsi; lpData
0x18000cc18  xor     r8d, r8d; lpValueName
0x18000cc1b  xor     edx, edx; char *
0x18000cc1d  mov     rcx, rbx; lpSubKey
0x18000cc20  call    RegSetDefValue
0x18000cc25  lea     r9, [rsp+380h+Data]; lpData
0x18000cc2a  xor     r8d, r8d; lpValueName
0x18000cc2d  lea     rdx, aClsid_0; "CLSID"
0x18000cc34  mov     rcx, rbx; lpSubKey
0x18000cc37  call    RegSetDefValue
0x18000cc3c  mov     r9, rdi; lpData
0x18000cc3f  lea     rdx, aCurver; "CurVer"
0x18000cc46  xor     r8d, r8d; lpValueName
0x18000cc49  mov     rcx, rbx; lpSubKey
0x18000cc4c  call    RegSetDefValue
0x18000cc51  mov     r9, rsi; lpData
0x18000cc54  xor     r8d, r8d; lpValueName
0x18000cc57  xor     edx, edx; char *
0x18000cc59  mov     rcx, rdi; lpSubKey
0x18000cc5c  call    RegSetDefValue
0x18000cc61  lea     r9, [rsp+380h+Data]; lpData
0x18000cc66  xor     r8d, r8d; lpValueName
0x18000cc69  lea     rdx, aClsid_0; "CLSID"
0x18000cc70  mov     rcx, rdi; lpSubKey
0x18000cc73  call    RegSetDefValue
0x18000cc78  xor     eax, eax
0x18000cc7a  mov     rcx, [rbp+280h+var_30]
0x18000cc81  xor     rcx, rsp; StackCookie
0x18000cc84  call    __security_check_cookie
0x18000cc89  add     rsp, 360h
0x18000cc90  pop     r14
0x18000cc92  pop     rdi
0x18000cc93  pop     rsi
0x18000cc94  pop     rbx
0x18000cc95  pop     rbp
0x18000cc96  retn
```
