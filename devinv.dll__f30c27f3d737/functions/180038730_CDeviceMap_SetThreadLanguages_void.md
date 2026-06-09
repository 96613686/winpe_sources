# CDeviceMap::SetThreadLanguages(void)

- ea: `0x180038730`
- end: `0x18003890c`
- name: `?SetThreadLanguages@CDeviceMap@@AEAAJXZ`
- size: `476`
- prototype: `__int64 __fastcall(CDeviceMap *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180034d4c`
- `0x180037eb4`

## callees

- `0x180006210`
- `0x18000624c`
- `0x180038730`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038754`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038787`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003879e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038787`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003879e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003883d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003889f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003883d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003889f`

## string_xrefs

- `0x18003877d`: `SetThreadPreferredUILanguages`
- `0x18003878d`: `GetThreadPreferredUILanguages`
- `0x180038863`: `CDeviceMap::SetThreadLanguages`
- `0x1800388c5`: `CDeviceMap::SetThreadLanguages`

## pseudocode

```c
signed int __fastcall CDeviceMap::SetThreadLanguages(CDeviceMap *this)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rdi
  signed int result; // eax
  FARPROC ProcAddress; // rax
  bool v6; // zf
  void *v7; // rdi
  unsigned __int64 v8; // rax
  void *v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  unsigned int (__fastcall *v12)(__int64, const wchar_t *, int *); // rax
  signed int LastError; // eax
  int v14; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = 0;
  v14 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernel32");
  v3 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    *((_QWORD *)this + 98) = GetProcAddress(ModuleHandleW, "SetThreadPreferredUILanguages");
    ProcAddress = GetProcAddress(v3, "GetThreadPreferredUILanguages");
    v6 = *((_QWORD *)this + 98) == 0;
    *((_QWORD *)this + 97) = ProcAddress;
    if ( v6 || !ProcAddress )
      return -2147467263;
    if ( ((unsigned int (__fastcall *)(__int64, int *, _QWORD, unsigned int *))ProcAddress)(72, &v14, 0, &v15) )
    {
      v7 = 0;
      if ( !v14 )
        goto LABEL_16;
      v8 = 2LL * v15;
      if ( !is_mul_ok(v15, 2u) )
        v8 = -1;
      v9 = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
      v7 = v9;
      if ( !v9 )
        return -2147024888;
      if ( (*((unsigned int (__fastcall **)(__int64, int *, void *, unsigned int *))this + 97))(72, &v14, v9, &v15) )
      {
LABEL_16:
        v12 = (unsigned int (__fastcall *)(__int64, const wchar_t *, int *))*((_QWORD *)this + 98);
        v14 = 1;
        if ( v12(8, L"en-us", &v14) )
        {
          *((_QWORD *)this + 96) = v7;
          *((_DWORD *)this + 190) = 1;
          return 0;
        }
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        AslLogCallPrintf(1, "CDeviceMap::SetThreadLanguages", 2359, "[0x%x]", v11);
        if ( !v7 )
          return v11;
      }
      else
      {
        v10 = GetLastError();
        v11 = v10;
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        AslLogCallPrintf(1, "CDeviceMap::SetThreadLanguages", 2344, "[0x%x]", v11);
      }
      operator delete(v7);
      return v11;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180038730  mov     [rsp+arg_0], rbx
0x180038735  push    rdi
0x180038736  sub     rsp, 30h
0x18003873a  mov     rbx, rcx
0x18003873d  mov     [rsp+38h+arg_10], 0
0x180038745  lea     rcx, aKernel32; "kernel32"
0x18003874c  mov     [rsp+38h+arg_8], 0
0x180038754  call    cs:__imp_GetModuleHandleW
0x18003875a  mov     rdi, rax
0x18003875d  test    rax, rax
0x180038760  jnz     short loc_18003877D
0x180038762  call    cs:__imp_GetLastError
0x180038768  test    eax, eax
0x18003876a  jle     loc_180038901
0x180038770  movzx   eax, ax
0x180038773  or      eax, 80070000h
0x180038778  jmp     loc_180038901
0x18003877d  lea     rdx, aSetthreadprefe; "SetThreadPreferredUILanguages"
0x180038784  mov     rcx, rdi; hModule
0x180038787  call    cs:__imp_GetProcAddress
0x18003878d  lea     rdx, aGetthreadprefe; "GetThreadPreferredUILanguages"
0x180038794  mov     rcx, rdi; hModule
0x180038797  mov     [rbx+310h], rax
0x18003879e  call    cs:__imp_GetProcAddress
0x1800387a4  cmp     qword ptr [rbx+310h], 0
0x1800387ac  mov     [rbx+308h], rax
0x1800387b3  jz      loc_1800388FC
0x1800387b9  test    rax, rax
0x1800387bc  jz      loc_1800388FC
0x1800387c2  xor     r8d, r8d
0x1800387c5  lea     r9, [rsp+38h+arg_10]
0x1800387ca  lea     rdx, [rsp+38h+arg_8]
0x1800387cf  lea     ecx, [r8+48h]
0x1800387d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387d8  test    eax, eax
0x1800387da  jz      short loc_180038762
0x1800387dc  xor     edi, edi
0x1800387de  cmp     [rsp+38h+arg_8], edi
0x1800387e2  jbe     loc_180038876
0x1800387e8  mov     ecx, [rsp+38h+arg_10]
0x1800387ec  lea     eax, [rdi+2]
0x1800387ef  mul     rcx
0x1800387f2  lea     rcx, [rdi-1]
0x1800387f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800387fd  cmovb   rax, rcx
0x180038801  mov     rcx, rax; unsigned __int64
0x180038804  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180038809  mov     rdi, rax
0x18003880c  test    rax, rax
0x18003880f  jnz     short loc_18003881B
0x180038811  mov     eax, 80070008h
0x180038816  jmp     loc_180038901
0x18003881b  mov     r8, rax
0x18003881e  lea     r9, [rsp+38h+arg_10]
0x180038823  mov     rax, [rbx+308h]
0x18003882a  lea     rdx, [rsp+38h+arg_8]
0x18003882f  mov     ecx, 48h ; 'H'
0x180038834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038839  test    eax, eax
0x18003883b  jnz     short loc_180038876
0x18003883d  call    cs:__imp_GetLastError
0x180038843  mov     ebx, eax
0x180038845  test    eax, eax
0x180038847  jle     short loc_180038852
0x180038849  movzx   ebx, ax
0x18003884c  or      ebx, 80070000h
0x180038852  lea     r9, a0xX_0; "[0x%x]"
0x180038859  mov     [rsp+38h+var_18], ebx
0x18003885d  mov     r8d, 928h
0x180038863  lea     rdx, aCdevicemapSett; "CDeviceMap::SetThreadLanguages"
0x18003886a  mov     ecx, 1
0x18003886f  call    AslLogCallPrintf
0x180038874  jmp     short loc_1800388DB
0x180038876  mov     rax, [rbx+310h]
0x18003887d  lea     r8, [rsp+38h+arg_8]
0x180038882  lea     rdx, aEnUs; "en-us"
0x180038889  mov     [rsp+38h+arg_8], 1
0x180038891  mov     ecx, 8
0x180038896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003889b  test    eax, eax
0x18003889d  jnz     short loc_1800388E5
0x18003889f  call    cs:__imp_GetLastError
0x1800388a5  mov     ebx, eax
0x1800388a7  test    eax, eax
0x1800388a9  jle     short loc_1800388B4
0x1800388ab  movzx   ebx, ax
0x1800388ae  or      ebx, 80070000h
0x1800388b4  lea     r9, a0xX_0; "[0x%x]"
0x1800388bb  mov     [rsp+38h+var_18], ebx
0x1800388bf  mov     r8d, 937h
0x1800388c5  lea     rdx, aCdevicemapSett; "CDeviceMap::SetThreadLanguages"
0x1800388cc  mov     ecx, 1
0x1800388d1  call    AslLogCallPrintf
0x1800388d6  test    rdi, rdi
0x1800388d9  jz      short loc_1800388F8
0x1800388db  mov     rcx, rdi; Block
0x1800388de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800388e3  jmp     short loc_1800388F8
0x1800388e5  mov     [rbx+300h], rdi
0x1800388ec  mov     dword ptr [rbx+2F8h], 1
0x1800388f6  xor     ebx, ebx
0x1800388f8  mov     eax, ebx
0x1800388fa  jmp     short loc_180038901
0x1800388fc  mov     eax, 80004001h
0x180038901  mov     rbx, [rsp+38h+arg_0]
0x180038906  add     rsp, 30h
0x18003890a  pop     rdi
0x18003890b  retn
```
