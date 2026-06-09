# LsapLoadExtension

- ea: `0x140003654`
- end: `0x1400037af`
- name: `LsapLoadExtension`
- size: `347`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400037b8`
- `0x140003a6c`

## callees

- `0x140003584`
- `0x140003654`
- `0x140006010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000369b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000369b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000366e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14000366e`
- `ntdll!RtlNtStatusToDosError` at `0x140003774`
- `ntdll!RtlNtStatusToDosError` at `0x140003774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003726`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000373c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003758`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000373c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003758`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003718`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140003718`

## string_xrefs

- `0x14000372e`: `InitializeLsaExtension`

## pseudocode

```c
ULONG __fastcall LsapLoadExtension(void *Src, __int64 *a2)
{
  __int64 i; // rbx
  ULONG result; // eax
  __int64 *v6; // rax
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v10)(_QWORD); // rsi
  NTSTATUS v11; // eax
  NTSTATUS v12; // edi
  __int64 v13; // [rsp+60h] [rbp+18h]

  i = 0;
  v13 = 0;
  if ( wcschr((const wchar_t *)Src, 0x5Cu) )
  {
    result = 13;
  }
  else
  {
    for ( i = gLsapExtensionList; (__int64 *)i != &gLsapExtensionList; i = *(_QWORD *)i )
    {
      if ( !(unsigned int)_o__wcsicmp(Src, *(_QWORD *)(i + 40)) )
      {
        v13 = i;
        if ( i )
        {
          result = *(_DWORD *)(i + 60);
          if ( !result )
          {
            if ( *(_DWORD *)(i + 56) )
              goto LABEL_25;
            result = 1359;
          }
          goto LABEL_23;
        }
        break;
      }
    }
    result = LsapCreateLsaExtension(Src);
    if ( result )
    {
      i = v13;
    }
    else
    {
      v6 = (__int64 *)qword_14000C2E8;
      if ( *(__int64 **)qword_14000C2E8 != &gLsapExtensionList )
        __fastfail(3u);
      i = v13;
      *(_QWORD *)v13 = &gLsapExtensionList;
      *(_QWORD *)(v13 + 8) = v6;
      *v6 = v13;
      qword_14000C2E8 = v13;
      Library = LoadLibraryExW((LPCWSTR)Src, 0, 0);
      v8 = Library;
      if ( Library
        && (*(_QWORD *)(v13 + 48) = Library,
            ProcAddress = GetProcAddress(Library, "InitializeLsaExtension"),
            (v10 = (__int64 (__fastcall *)(_QWORD))ProcAddress) != 0) )
      {
        *(_QWORD *)(v13 + 72) = ProcAddress;
        *(_QWORD *)(v13 + 80) = GetProcAddress(v8, "QueryLsaInterface");
        v11 = v10(0);
        v12 = v11;
        if ( v11 >= 0 )
        {
          *(_DWORD *)(v13 + 56) = 1;
          result = 0;
          goto LABEL_25;
        }
        result = RtlNtStatusToDosError(v11);
        *(_DWORD *)(v13 + 64) = v12;
      }
      else
      {
        result = GetLastError();
      }
      if ( !result )
        goto LABEL_25;
    }
LABEL_23:
    if ( i )
    {
      *(_DWORD *)(i + 60) = result;
      i = 0;
    }
  }
LABEL_25:
  if ( a2 )
    *a2 = i;
  return result;
}

```

## disassembly

```asm
0x140003654  push    rbx
0x140003656  push    rsi
0x140003657  push    rdi
0x140003658  push    r14
0x14000365a  sub     rsp, 28h
0x14000365e  xor     ebx, ebx
0x140003660  mov     r14, rdx
0x140003663  mov     rdi, rcx
0x140003666  mov     [rsp+48h+arg_10], rbx
0x14000366b  lea     edx, [rbx+5Ch]; Ch
0x14000366e  call    cs:__imp_wcschr
0x140003674  test    rax, rax
0x140003677  jz      short loc_140003681
0x140003679  lea     eax, [rbx+0Dh]
0x14000367c  jmp     loc_14000379D
0x140003681  mov     rbx, cs:gLsapExtensionList
0x140003688  lea     rsi, gLsapExtensionList
0x14000368f  cmp     rbx, rsi
0x140003692  jz      short loc_1400036D2
0x140003694  mov     rdx, [rbx+28h]
0x140003698  mov     rcx, rdi
0x14000369b  call    cs:__imp__o__wcsicmp
0x1400036a1  test    eax, eax
0x1400036a3  jz      short loc_1400036AA
0x1400036a5  mov     rbx, [rbx]
0x1400036a8  jmp     short loc_14000368F
0x1400036aa  mov     [rsp+48h+arg_10], rbx
0x1400036af  test    rbx, rbx
0x1400036b2  jz      short loc_1400036D2
0x1400036b4  mov     eax, [rbx+3Ch]
0x1400036b7  test    eax, eax
0x1400036b9  jnz     loc_140003793
0x1400036bf  cmp     [rbx+38h], eax
0x1400036c2  jnz     loc_14000379D
0x1400036c8  mov     eax, 54Fh
0x1400036cd  jmp     loc_140003793
0x1400036d2  lea     rdx, [rsp+48h+arg_10]
0x1400036d7  mov     rcx, rdi; Src
0x1400036da  call    LsapCreateLsaExtension
0x1400036df  test    eax, eax
0x1400036e1  jnz     loc_14000378E
0x1400036e7  mov     rax, cs:qword_14000C2E8
0x1400036ee  cmp     [rax], rsi
0x1400036f1  jz      short loc_1400036FA
0x1400036f3  mov     ecx, 3
0x1400036f8  int     29h; Win8: RtlFailFast(ecx)
0x1400036fa  mov     rbx, [rsp+48h+arg_10]
0x1400036ff  xor     r8d, r8d; dwFlags
0x140003702  xor     edx, edx; hFile
0x140003704  mov     rcx, rdi; lpLibFileName
0x140003707  mov     [rbx], rsi
0x14000370a  mov     [rbx+8], rax
0x14000370e  mov     [rax], rbx
0x140003711  mov     cs:qword_14000C2E8, rbx
0x140003718  call    cs:__imp_LoadLibraryExW
0x14000371e  mov     rdi, rax
0x140003721  test    rax, rax
0x140003724  jnz     short loc_14000372E
0x140003726  call    cs:__imp_GetLastError
0x14000372c  jmp     short loc_14000377D
0x14000372e  lea     rdx, ProcName; "InitializeLsaExtension"
0x140003735  mov     [rbx+30h], rdi
0x140003739  mov     rcx, rdi; hModule
0x14000373c  call    cs:__imp_GetProcAddress
0x140003742  mov     rsi, rax
0x140003745  test    rax, rax
0x140003748  jz      short loc_140003726
0x14000374a  lea     rdx, aQuerylsainterf; "QueryLsaInterface"
0x140003751  mov     [rbx+48h], rax
0x140003755  mov     rcx, rdi; hModule
0x140003758  call    cs:__imp_GetProcAddress
0x14000375e  mov     [rbx+50h], rax
0x140003762  xor     ecx, ecx
0x140003764  mov     rax, rsi
0x140003767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000376c  mov     edi, eax
0x14000376e  test    eax, eax
0x140003770  jns     short loc_140003783
0x140003772  mov     ecx, eax; Status
0x140003774  call    cs:__imp_RtlNtStatusToDosError
0x14000377a  mov     [rbx+40h], edi
0x14000377d  test    eax, eax
0x14000377f  jz      short loc_14000379D
0x140003781  jmp     short loc_140003793
0x140003783  mov     dword ptr [rbx+38h], 1
0x14000378a  xor     eax, eax
0x14000378c  jmp     short loc_14000379D
0x14000378e  mov     rbx, [rsp+48h+arg_10]
0x140003793  test    rbx, rbx
0x140003796  jz      short loc_14000379D
0x140003798  mov     [rbx+3Ch], eax
0x14000379b  xor     ebx, ebx
0x14000379d  test    r14, r14
0x1400037a0  jz      short loc_1400037A5
0x1400037a2  mov     [r14], rbx
0x1400037a5  add     rsp, 28h
0x1400037a9  pop     r14
0x1400037ab  pop     rdi
0x1400037ac  pop     rsi
0x1400037ad  pop     rbx
0x1400037ae  retn
```
