# GenInvokeEnumStackProviders(ulong,_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort const *,_LIST_ENTRY *)

- ea: `0x18001bb40`
- end: `0x18001bc97`
- name: `?GenInvokeEnumStackProviders@@YAJKPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEBGPEAU_LIST_ENTRY@@@Z`
- size: `343`
- prototype: `int(unsigned int, struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, const unsigned __int16 *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001ad48`

## callees

- `0x180016b74`
- `0x18001bb40`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001bb76`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001bb76`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001bbbd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001bbbd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bc20`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bc81`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bc20`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001bc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb8e`

## pseudocode

```c
int __fastcall GenInvokeEnumStackProviders(
        unsigned int a1,
        struct _MINIDUMP_STATE *a2,
        struct _INTERNAL_PROCESS *a3,
        const unsigned __int16 *a4,
        struct _LIST_ENTRY *a5)
{
  __int64 v6; // rax
  HMODULE Library; // rax
  HMODULE v9; // rsi
  int result; // eax
  FARPROC ProcAddress; // rdi
  struct _LIST_ENTRY *v12; // rax
  struct _LIST_ENTRY *v13; // rbx
  struct _LIST_ENTRY *Flink; // rdx
  _QWORD v15[9]; // [rsp+20h] [rbp-48h] BYREF

  v15[1] = a2;
  v15[0] = &StackProviderDataTarget::`vftable';
  v6 = *((_QWORD *)a2 + 6);
  v15[2] = a3;
  v15[3] = v6;
  Library = LoadLibraryExW(a4, 0, 0);
  v9 = Library;
  if ( !Library )
  {
    if ( !GetLastError() )
      return -2147467259;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  ProcAddress = GetProcAddress(Library, "GetDumpStreams");
  if ( !ProcAddress )
  {
LABEL_11:
    FreeLibrary(v9);
    return (int)ProcAddress;
  }
  v12 = (struct _LIST_ENTRY *)AllocMemory(a2, 0x20u);
  v13 = v12;
  if ( !v12 )
  {
    LODWORD(ProcAddress) = -2147024882;
    goto LABEL_11;
  }
  *v12 = 0;
  v12[1] = 0;
  LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *, _QWORD, struct _LIST_ENTRY *))ProcAddress)(v15, a1, v12);
  if ( (int)ProcAddress < 0 )
  {
    (*(void (__fastcall **)(_QWORD, struct _LIST_ENTRY *))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4), v13);
    goto LABEL_11;
  }
  if ( v13->Flink && *(struct _LIST_ENTRY **)((char *)&v13->Flink->Flink + 4) )
  {
    v13->Blink = (struct _LIST_ENTRY *)v9;
    Flink = a5->Flink;
    if ( a5->Flink->Blink != a5 )
      __fastfail(3u);
    v13[1].Flink = Flink;
    v13[1].Blink = a5;
    Flink->Blink = v13 + 1;
    a5->Flink = v13 + 1;
    return 0;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, struct _LIST_ENTRY *))(**((_QWORD **)a2 + 4) + 24LL))(*((_QWORD *)a2 + 4), v13);
    FreeLibrary(v9);
    return -2147467261;
  }
}

```

## disassembly

```asm
0x18001bb40  mov     r11, rsp
0x18001bb43  push    rbx
0x18001bb44  push    rbp
0x18001bb45  push    rsi
0x18001bb46  push    rdi
0x18001bb47  push    r14
0x18001bb49  sub     rsp, 40h
0x18001bb4d  lea     rax, ??_7StackProviderDataTarget@@6B@; const StackProviderDataTarget::`vftable'
0x18001bb54  mov     [r11-40h], rdx
0x18001bb58  mov     [r11-48h], rax
0x18001bb5c  mov     rbp, rdx
0x18001bb5f  mov     rax, [rdx+30h]
0x18001bb63  mov     r14d, ecx
0x18001bb66  mov     [r11-38h], r8
0x18001bb6a  xor     edx, edx; hFile
0x18001bb6c  xor     r8d, r8d; dwFlags
0x18001bb6f  mov     [r11-30h], rax
0x18001bb73  mov     rcx, r9; lpLibFileName
0x18001bb76  call    cs:__imp_LoadLibraryExW
0x18001bb7c  mov     rsi, rax
0x18001bb7f  test    rax, rax
0x18001bb82  jnz     short loc_18001BBB3
0x18001bb84  call    cs:__imp_GetLastError
0x18001bb8a  test    eax, eax
0x18001bb8c  jz      short loc_18001BBA9
0x18001bb8e  call    cs:__imp_GetLastError
0x18001bb94  test    eax, eax
0x18001bb96  jle     loc_18001BC8C
0x18001bb9c  movzx   eax, ax
0x18001bb9f  or      eax, 80070000h
0x18001bba4  jmp     loc_18001BC8C
0x18001bba9  mov     eax, 80004005h
0x18001bbae  jmp     loc_18001BC8C
0x18001bbb3  lea     rdx, aGetdumpstreams; "GetDumpStreams"
0x18001bbba  mov     rcx, rsi; hModule
0x18001bbbd  call    cs:__imp_GetProcAddress
0x18001bbc3  mov     rdi, rax
0x18001bbc6  test    rax, rax
0x18001bbc9  jz      short loc_18001BC1D
0x18001bbcb  mov     edx, 20h ; ' '; unsigned int
0x18001bbd0  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x18001bbd3  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x18001bbd8  mov     rbx, rax
0x18001bbdb  test    rax, rax
0x18001bbde  jnz     short loc_18001BBE7
0x18001bbe0  mov     edi, 8007000Eh
0x18001bbe5  jmp     short loc_18001BC1D
0x18001bbe7  xorps   xmm0, xmm0
0x18001bbea  lea     rcx, [rsp+68h+var_48]
0x18001bbef  movups  xmmword ptr [rax], xmm0
0x18001bbf2  mov     r8, rbx
0x18001bbf5  mov     edx, r14d
0x18001bbf8  movups  xmmword ptr [rax+10h], xmm0
0x18001bbfc  mov     rax, rdi
0x18001bbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc04  mov     edi, eax
0x18001bc06  test    eax, eax
0x18001bc08  jns     short loc_18001BC2A
0x18001bc0a  mov     rcx, [rbp+20h]
0x18001bc0e  mov     rdx, [rcx]
0x18001bc11  mov     rax, [rdx+18h]
0x18001bc15  mov     rdx, rbx
0x18001bc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc1d  mov     rcx, rsi; hLibModule
0x18001bc20  call    cs:__imp_FreeLibrary
0x18001bc26  mov     eax, edi
0x18001bc28  jmp     short loc_18001BC8C
0x18001bc2a  mov     rax, [rbx]
0x18001bc2d  test    rax, rax
0x18001bc30  jz      short loc_18001BC6B
0x18001bc32  cmp     qword ptr [rax+4], 0
0x18001bc37  jz      short loc_18001BC6B
0x18001bc39  mov     rcx, [rsp+68h+arg_20]
0x18001bc41  mov     [rbx+8], rsi
0x18001bc45  mov     rdx, [rcx]
0x18001bc48  cmp     [rdx+8], rcx
0x18001bc4c  jz      short loc_18001BC55
0x18001bc4e  mov     ecx, 3
0x18001bc53  int     29h; Win8: RtlFailFast(ecx)
0x18001bc55  lea     rax, [rbx+10h]
0x18001bc59  mov     [rax], rdx
0x18001bc5c  mov     [rax+8], rcx
0x18001bc60  mov     [rdx+8], rax
0x18001bc64  mov     [rcx], rax
0x18001bc67  xor     eax, eax
0x18001bc69  jmp     short loc_18001BC8C
0x18001bc6b  mov     rcx, [rbp+20h]
0x18001bc6f  mov     rdx, rbx
0x18001bc72  mov     rax, [rcx]
0x18001bc75  mov     rax, [rax+18h]
0x18001bc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc7e  mov     rcx, rsi; hLibModule
0x18001bc81  call    cs:__imp_FreeLibrary
0x18001bc87  mov     eax, 80004003h
0x18001bc8c  add     rsp, 40h
0x18001bc90  pop     r14
0x18001bc92  pop     rdi
0x18001bc93  pop     rsi
0x18001bc94  pop     rbp
0x18001bc95  pop     rbx
0x18001bc96  retn
```
