# IsRestoreInProgress(ulong &)

- ea: `0x18001d6b0`
- end: `0x18001d7b4`
- name: `?IsRestoreInProgress@@YAJAEAK@Z`
- size: `260`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c950`

## callees

- `0x1800012b8`
- `0x18001d6b0`
- `0x180029fe4`
- `0x180043fa0`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001d74b`
- `wbemcomn!GetMemLogObject` at `0x18001d74b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d756`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d703`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d6f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d6f1`

## string_xrefs

- `0x18001d6ea`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall IsRestoreInProgress(unsigned int *a1)
{
  FARPROC ProcAddress; // rax
  int RegistryDll; // ebx
  DWORD LastError; // eax
  bool v5; // sf
  CMemoryLog *MemLogObject; // rax
  __int64 v8; // rcx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  ProcAddress = (FARPROC)qword_180059CD0;
  v9 = 0;
  *a1 = 0;
  if ( ProcAddress )
    goto LABEL_5;
  RegistryDll = DLpLoadRegistryDll();
  if ( RegistryDll )
    goto LABEL_7;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_180059CD0 = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, __int64, __int64 *))ProcAddress)(
                  -2147483646,
                  L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\RepositoryRestoreInProgress",
                  0,
                  131097,
                  &v9);
  else
    LastError = GetLastError();
  RegistryDll = LastError;
LABEL_7:
  if ( RegistryDll == 2 )
    return 0;
  v5 = RegistryDll < 0;
  if ( !RegistryDll )
  {
    v8 = v9;
    *a1 = 1;
    DLRegCloseKey(v8);
    return 0;
  }
  if ( RegistryDll > 0 )
  {
    RegistryDll = (unsigned __int16)RegistryDll | 0x80070000;
    v5 = RegistryDll < 0;
  }
  if ( v5 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, RegistryDll);
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
      (unsigned int)RegistryDll);
  }
  return (unsigned int)RegistryDll;
}

```

## disassembly

```asm
0x18001d6b0  mov     [rsp+arg_8], rbx
0x18001d6b5  push    rdi
0x18001d6b6  sub     rsp, 30h
0x18001d6ba  mov     rax, cs:qword_180059CD0
0x18001d6c1  mov     rdi, rcx
0x18001d6c4  mov     [rsp+38h+arg_0], 0
0x18001d6cd  mov     dword ptr [rcx], 0
0x18001d6d3  test    rax, rax
0x18001d6d6  jnz     short loc_18001D70B
0x18001d6d8  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18001d6dd  mov     ebx, eax
0x18001d6df  test    eax, eax
0x18001d6e1  jnz     short loc_18001D733
0x18001d6e3  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d6ea  lea     rdx, ProcName; "RegOpenKeyExW"
0x18001d6f1  call    cs:__imp_GetProcAddress
0x18001d6f7  mov     cs:qword_180059CD0, rax
0x18001d6fe  test    rax, rax
0x18001d701  jnz     short loc_18001D70B
0x18001d703  call    cs:__imp_GetLastError
0x18001d709  jmp     short loc_18001D731
0x18001d70b  lea     rcx, [rsp+38h+arg_0]
0x18001d710  mov     r9d, 20019h
0x18001d716  mov     [rsp+38h+var_18], rcx
0x18001d71b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Repos"...
0x18001d722  mov     rcx, 0FFFFFFFF80000002h
0x18001d729  xor     r8d, r8d
0x18001d72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d731  mov     ebx, eax
0x18001d733  cmp     ebx, 2
0x18001d736  jz      short loc_18001D7A7
0x18001d738  test    ebx, ebx
0x18001d73a  jz      short loc_18001D797
0x18001d73c  jle     short loc_18001D749
0x18001d73e  movzx   ebx, bx
0x18001d741  or      ebx, 80070000h
0x18001d747  test    ebx, ebx
0x18001d749  jns     short loc_18001D75C
0x18001d74b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d751  mov     rcx, rax
0x18001d754  mov     edx, ebx
0x18001d756  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d763  lea     rax, WPP_GLOBAL_Control
0x18001d76a  cmp     rcx, rax
0x18001d76d  jz      short loc_18001D793
0x18001d76f  test    byte ptr [rcx+1Ch], 1
0x18001d773  jz      short loc_18001D793
0x18001d775  cmp     byte ptr [rcx+19h], 2
0x18001d779  jb      short loc_18001D793
0x18001d77b  mov     rcx, [rcx+10h]
0x18001d77f  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18001d786  mov     edx, 2Ch ; ','
0x18001d78b  mov     r9d, ebx
0x18001d78e  call    WPP_SF_d
0x18001d793  mov     eax, ebx
0x18001d795  jmp     short loc_18001D7A9
0x18001d797  mov     rcx, [rsp+38h+arg_0]
0x18001d79c  mov     dword ptr [rdi], 1
0x18001d7a2  call    DLRegCloseKey
0x18001d7a7  xor     eax, eax
0x18001d7a9  mov     rbx, [rsp+38h+arg_8]
0x18001d7ae  add     rsp, 30h
0x18001d7b2  pop     rdi
0x18001d7b3  retn
```
