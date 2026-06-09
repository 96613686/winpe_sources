# GetAppContainerRegistryHandle

- ea: `0x180003840`
- end: `0x18000390b`
- name: `GetAppContainerRegistryHandle`
- size: `203`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003840`
- `0x180003914`
- `0x180003fdc`
- `0x180005b60`
- `0x180005b90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038ab`

## string_xrefs

- `0x1800038d8`: `minio\profapi\registry.cpp`
- `0x1800038f3`: `minio\profapi\registry.cpp`

## pseudocode

```c
__int64 __fastcall GetAppContainerRegistryHandle(REGSAM samDesired, PHKEY phkResult)
{
  int AppContainerRegistryPathAlloc; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int phkResulta; // [rsp+20h] [rbp-38h]
  unsigned int phkResultb; // [rsp+20h] [rbp-38h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  lpSubKey = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  v11 = -1;
  v12 = -1;
  AppContainerRegistryPathAlloc = GetAppContainerRegistryPathAlloc((unsigned __int16 **)&lpSubKey);
  v5 = AppContainerRegistryPathAlloc;
  if ( AppContainerRegistryPathAlloc < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"minio\\profapi\\registry.cpp",
      (const char *)(unsigned int)AppContainerRegistryPathAlloc,
      phkResulta);
  }
  else
  {
    v6 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, samDesired, phkResult);
    if ( v6 )
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x8A,
             (unsigned int)"minio\\profapi\\registry.cpp",
             (const char *)v6,
             phkResultb);
    else
      v5 = 0;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x180003840  mov     rax, rsp
0x180003843  mov     [rax+8], rbx
0x180003847  mov     [rax+10h], rsi
0x18000384b  push    rdi
0x18000384c  sub     rsp, 50h
0x180003850  mov     esi, ecx
0x180003852  mov     qword ptr [rax-28h], 0
0x18000385a  lea     rcx, [rax-28h]
0x18000385e  mov     qword ptr [rax-20h], 0
0x180003866  mov     rdi, rdx
0x180003869  mov     qword ptr [rax-18h], 0
0x180003871  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003876  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000387a  lea     rcx, [rsp+58h+lpSubKey]; unsigned __int16 **
0x18000387f  mov     [rsp+58h+var_20], rax
0x180003884  mov     [rsp+58h+var_18], rax
0x180003889  call    ?GetAppContainerRegistryPathAlloc@@YAJPEAPEAG@Z; GetAppContainerRegistryPathAlloc(ushort * *)
0x18000388e  mov     ebx, eax
0x180003890  test    eax, eax
0x180003892  js      short loc_1800038D3
0x180003894  mov     rdx, [rsp+58h+lpSubKey]; lpSubKey
0x180003899  mov     r9d, esi; samDesired
0x18000389c  xor     r8d, r8d; ulOptions
0x18000389f  mov     qword ptr [rsp+58h+phkResult], rdi; unsigned int
0x1800038a4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800038ab  call    cs:__imp_RegOpenKeyExW
0x1800038b1  test    eax, eax
0x1800038b3  jnz     short loc_1800038EE
0x1800038b5  xor     ebx, ebx
0x1800038b7  lea     rcx, [rsp+58h+lpSubKey]
0x1800038bc  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800038c1  mov     rsi, [rsp+58h+arg_8]
0x1800038c6  mov     eax, ebx
0x1800038c8  mov     rbx, [rsp+58h+arg_0]
0x1800038cd  add     rsp, 50h
0x1800038d1  pop     rdi
0x1800038d2  retn
0x1800038d3  mov     rcx, [rsp+58h]; this
0x1800038d8  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x1800038df  mov     r9d, eax; char *
0x1800038e2  mov     edx, 89h; void *
0x1800038e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ec  jmp     short loc_1800038B7
0x1800038ee  mov     rcx, [rsp+58h]; this
0x1800038f3  lea     r8, aMinioProfapiRe; "minio\\profapi\\registry.cpp"
0x1800038fa  mov     r9d, eax; char *
0x1800038fd  mov     edx, 8Ah; void *
0x180003902  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180003907  mov     ebx, eax
0x180003909  jmp     short loc_1800038B7
```
