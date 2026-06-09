# pUtilGetRedirectedFilePath

- ea: `0x180008628`
- end: `0x180008804`
- name: `pUtilGetRedirectedFilePath`
- size: `476`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000829c`

## callees

- `0x180008628`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800087c1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800087c1`
- `KERNEL32!SetLastError` at `0x1800087ee`
- `KERNEL32!SetLastError` at `0x1800087ee`
- `KERNEL32!GetProcAddress` at `0x18000866d`
- `KERNEL32!GetProcAddress` at `0x18000866d`
- `KERNEL32!LoadLibraryExW` at `0x180008651`
- `KERNEL32!LoadLibraryExW` at `0x180008651`
- `KERNEL32!FreeLibrary` at `0x1800087e6`
- `KERNEL32!FreeLibrary` at `0x1800087e6`
- `SETUPAPI!pSetupFree` at `0x1800087d5`
- `SETUPAPI!pSetupFree` at `0x1800087d5`
- `SETUPAPI!pSetupMalloc` at `0x1800086db`
- `SETUPAPI!pSetupMalloc` at `0x18000873e`
- `SETUPAPI!pSetupMalloc` at `0x1800086db`
- `SETUPAPI!pSetupMalloc` at `0x18000873e`

## string_xrefs

- `0x18000863e`: `ntdll.dll`
- `0x18000868e`: `%SystemRoot%\System32\DriverState\Devices`
- `0x180008765`: `%SystemRoot%\System32\DriverState\Devices`

## pseudocode

```c
__int64 __fastcall pUtilGetRedirectedFilePath(__int64 a1, __int64 a2)
{
  DWORD v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  __int64 (*v6)(_QWORD, _QWORD, _QWORD, ...); // rbp
  __int64 v7; // rdi
  int v8; // eax
  NTSTATUS v9; // ecx
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // r14
  _WORD *v13; // r9
  _WORD *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+28h] [rbp-50h]
  unsigned int v18; // [rsp+88h] [rbp+10h] BYREF
  int v19; // [rsp+8Ch] [rbp+14h]

  v19 = HIDWORD(a2);
  v18 = 0;
  v2 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation");
    v6 = (__int64 (*)(_QWORD, _QWORD, _QWORD, ...))ProcAddress;
    if ( ProcAddress )
    {
      v7 = 0;
      v8 = ((__int64 (*)(const wchar_t *, _QWORD, const wchar_t *, ...))ProcAddress)(
             L"DriverState_Devices",
             0,
             L"%SystemRoot%\\System32\\DriverState\\Devices",
             1,
             0,
             0,
             &v18);
      if ( v8 >= 0 )
      {
        v2 = 1359;
LABEL_28:
        FreeLibrary(v4);
        goto LABEL_29;
      }
      if ( v8 == -2147483643 )
      {
        v7 = pSetupMalloc(v18);
        if ( !v7 )
        {
          v2 = 8;
          goto LABEL_28;
        }
        LODWORD(v17) = v18;
        v8 = v6(L"DriverState_Devices", 0, L"%SystemRoot%\\System32\\DriverState\\Devices", 1, v7, v17, &v18);
        if ( v8 >= 0 )
          goto LABEL_28;
      }
      v9 = v8;
      goto LABEL_24;
    }
  }
  v18 = 84;
  v7 = ((__int64 (*)(void))pSetupMalloc)();
  if ( !v7 )
  {
    v2 = 8;
    goto LABEL_27;
  }
  v10 = (unsigned __int64)v18 >> 1;
  if ( !v10 )
  {
    v15 = -1073741811;
LABEL_23:
    v9 = v15;
LABEL_24:
    v2 = RtlNtStatusToDosErrorNoTeb(v9);
    if ( v2 && v7 )
    {
      pSetupFree(v7);
      v7 = 0;
    }
    goto LABEL_27;
  }
  v11 = 2147483646;
  v12 = L"%SystemRoot%\\System32\\DriverState\\Devices";
  v13 = (_WORD *)v7;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v13++ = *v12++;
    --v11;
    --v10;
  }
  while ( v10 );
  v14 = v13 - 1;
  v15 = v10 == 0 ? 0x80000005 : 0;
  if ( v10 )
    v14 = v13;
  *v14 = 0;
  if ( !v10 )
    goto LABEL_23;
LABEL_27:
  if ( v4 )
    goto LABEL_28;
LABEL_29:
  SetLastError(v2);
  return v7;
}

```

## disassembly

```asm
0x180008628  mov     rax, rsp
0x18000862b  mov     [rax+10h], rdx
0x18000862f  push    rbx
0x180008630  push    rbp
0x180008631  push    rsi
0x180008632  push    rdi
0x180008633  push    r14
0x180008635  push    r15
0x180008637  sub     rsp, 48h
0x18000863b  xor     r15d, r15d
0x18000863e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008645  xor     r8d, r8d; dwFlags
0x180008648  mov     [rax+10h], r15d
0x18000864c  xor     edx, edx; hFile
0x18000864e  mov     ebx, r15d
0x180008651  call    cs:__imp_LoadLibraryExW
0x180008657  mov     rsi, rax
0x18000865a  test    rax, rax
0x18000865d  jz      loc_180008732
0x180008663  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x18000866a  mov     rcx, rax; hModule
0x18000866d  call    cs:__imp_GetProcAddress
0x180008673  mov     rbp, rax
0x180008676  test    rax, rax
0x180008679  jz      loc_180008732
0x18000867f  lea     rax, [rsp+78h+arg_8]
0x180008687  xor     edx, edx
0x180008689  mov     [rsp+78h+var_48], rax
0x18000868e  lea     r14, aSystemrootSyst; "%SystemRoot%\\System32\\DriverState\\De"...
0x180008695  mov     dword ptr [rsp+78h+var_50], r15d
0x18000869a  lea     r9d, [r15+1]
0x18000869e  mov     rax, rbp
0x1800086a1  mov     [rsp+78h+var_58], r15
0x1800086a6  mov     r8, r14
0x1800086a9  lea     rcx, aDriverstateDev; "DriverState_Devices"
0x1800086b0  mov     edi, r15d
0x1800086b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b8  test    eax, eax
0x1800086ba  js      short loc_1800086C6
0x1800086bc  mov     ebx, 54Fh
0x1800086c1  jmp     loc_1800087E3
0x1800086c6  cmp     eax, 80000005h
0x1800086cb  jz      short loc_1800086D4
0x1800086cd  mov     ecx, eax
0x1800086cf  jmp     loc_1800087C1
0x1800086d4  mov     ecx, [rsp+78h+arg_8]
0x1800086db  call    cs:__imp_pSetupMalloc
0x1800086e1  mov     rdi, rax
0x1800086e4  test    rax, rax
0x1800086e7  jnz     short loc_1800086F1
0x1800086e9  lea     ebx, [rax+8]
0x1800086ec  jmp     loc_1800087E3
0x1800086f1  lea     rax, [rsp+78h+arg_8]
0x1800086f9  mov     r9d, 1
0x1800086ff  mov     [rsp+78h+var_48], rax
0x180008704  lea     rcx, aDriverstateDev; "DriverState_Devices"
0x18000870b  mov     eax, [rsp+78h+arg_8]
0x180008712  mov     r8, r14
0x180008715  mov     dword ptr [rsp+78h+var_50], eax
0x180008719  xor     edx, edx
0x18000871b  mov     rax, rbp
0x18000871e  mov     [rsp+78h+var_58], rdi
0x180008723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008728  test    eax, eax
0x18000872a  jns     loc_1800087E3
0x180008730  jmp     short loc_1800086CD
0x180008732  mov     ecx, 54h ; 'T'
0x180008737  mov     [rsp+78h+arg_8], ecx
0x18000873e  call    cs:__imp_pSetupMalloc
0x180008744  mov     rdi, rax
0x180008747  test    rax, rax
0x18000874a  jnz     short loc_180008754
0x18000874c  lea     ebx, [rax+8]
0x18000874f  jmp     loc_1800087DE
0x180008754  mov     edx, [rsp+78h+arg_8]
0x18000875b  shr     rdx, 1
0x18000875e  jz      short loc_1800087B8
0x180008760  mov     eax, 7FFFFFFEh
0x180008765  lea     r14, aSystemrootSyst; "%SystemRoot%\\System32\\DriverState\\De"...
0x18000876c  mov     r9, rdi
0x18000876f  test    rax, rax
0x180008772  jz      short loc_180008792
0x180008774  movzx   ecx, word ptr [r14]
0x180008778  test    cx, cx
0x18000877b  jz      short loc_180008792
0x18000877d  mov     [r9], cx
0x180008781  add     r14, 2
0x180008785  add     r9, 2
0x180008789  dec     rax
0x18000878c  sub     rdx, 1
0x180008790  jnz     short loc_18000876F
0x180008792  mov     rax, rdx
0x180008795  lea     rcx, [r9-2]
0x180008799  neg     rax
0x18000879c  sbb     r8d, r8d
0x18000879f  not     r8d
0x1800087a2  and     r8d, 80000005h
0x1800087a9  test    rdx, rdx
0x1800087ac  cmovnz  rcx, r9
0x1800087b0  mov     [rcx], r15w
0x1800087b4  jnz     short loc_1800087DE
0x1800087b6  jmp     short loc_1800087BE
0x1800087b8  mov     r8d, 0C000000Dh
0x1800087be  mov     ecx, r8d; Status
0x1800087c1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800087c7  mov     ebx, eax
0x1800087c9  test    eax, eax
0x1800087cb  jz      short loc_1800087DE
0x1800087cd  test    rdi, rdi
0x1800087d0  jz      short loc_1800087DE
0x1800087d2  mov     rcx, rdi
0x1800087d5  call    cs:__imp_pSetupFree
0x1800087db  mov     rdi, r15
0x1800087de  test    rsi, rsi
0x1800087e1  jz      short loc_1800087EC
0x1800087e3  mov     rcx, rsi; hLibModule
0x1800087e6  call    cs:__imp_FreeLibrary
0x1800087ec  mov     ecx, ebx; dwErrCode
0x1800087ee  call    cs:__imp_SetLastError
0x1800087f4  mov     rax, rdi
0x1800087f7  add     rsp, 48h
0x1800087fb  pop     r15
0x1800087fd  pop     r14
0x1800087ff  pop     rdi
0x180008800  pop     rsi
0x180008801  pop     rbp
0x180008802  pop     rbx
0x180008803  retn
```
