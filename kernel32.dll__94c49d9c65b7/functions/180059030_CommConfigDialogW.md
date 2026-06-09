# CommConfigDialogW

- ea: `0x180059030`
- end: `0x18005911f`
- name: `CommConfigDialogW`
- size: `239`
- prototype: `BOOL __stdcall(LPCWSTR lpszName, HWND hWnd, LPCOMMCONFIG lpCC)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180060860`

## callees

- `0x18004586c`
- `0x180059030`
- `0x180060a10`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180059107`
- `ntdll!RtlSetLastWin32Error` at `0x180059107`
- `ntdll!RtlFreeHeap` at `0x1800590ed`
- `ntdll!RtlFreeHeap` at `0x1800590ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059091`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059091`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800590fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800590fb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059074`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059074`

## string_xrefs

- `0x180059087`: `drvCommConfigDialogW`

## pseudocode

```c
BOOL __stdcall CommConfigDialogW(LPCWSTR lpszName, HWND hWnd, LPCOMMCONFIG lpCC)
{
  BOOL v6; // esi
  HMODULE v7; // rdi
  ULONG LastErrorValue; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF

  v12 = 0;
  v6 = 1;
  v7 = 0;
  LastErrorValue = 0;
  GetFriendlyUi((__int64)lpszName, (__int64)&v12);
  if ( *((_QWORD *)&v12 + 1) )
  {
    LibraryW = LoadLibraryW(*((LPCWSTR *)&v12 + 1));
    v7 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "drvCommConfigDialogW");
      if ( ProcAddress )
      {
        LastErrorValue = ((__int64 (__fastcall *)(LPCWSTR, HWND, LPCOMMCONFIG))ProcAddress)(lpszName, hWnd, lpCC);
        goto LABEL_7;
      }
    }
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
  }
  v6 = 0;
LABEL_7:
  if ( *((_QWORD *)&v12 + 1) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&v12 + 1));
  if ( v7 )
    FreeLibrary(v7);
  if ( LastErrorValue )
  {
    RtlSetLastWin32Error(LastErrorValue);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180059030  mov     rax, rsp
0x180059033  push    rbx
0x180059034  push    rsi
0x180059035  push    rdi
0x180059036  push    r12
0x180059038  push    r14
0x18005903a  push    r15
0x18005903c  sub     rsp, 48h
0x180059040  mov     r15, r8
0x180059043  mov     r12, rdx
0x180059046  mov     r14, rcx
0x180059049  xorps   xmm0, xmm0
0x18005904c  movups  xmmword ptr [rax-48h], xmm0
0x180059050  mov     esi, 1
0x180059055  xor     edi, edi
0x180059057  mov     [rax-50h], rdi
0x18005905b  xor     ebx, ebx
0x18005905d  mov     [rax-58h], ebx
0x180059060  lea     rdx, [rax-48h]
0x180059064  call    GetFriendlyUi
0x180059069  nop
0x18005906a  mov     rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x18005906f  test    rcx, rcx
0x180059072  jz      short loc_1800590CF
0x180059074  call    cs:__imp_LoadLibraryW
0x18005907a  mov     rdi, rax
0x18005907d  mov     [rsp+78h+var_50], rax
0x180059082  test    rax, rax
0x180059085  jz      short loc_1800590C1
0x180059087  lea     rdx, aDrvcommconfigd; "drvCommConfigDialogW"
0x18005908e  mov     rcx, rax; hModule
0x180059091  call    cs:__imp_GetProcAddress
0x180059097  test    rax, rax
0x18005909a  jnz     short loc_1800590AA
0x18005909c  mov     ebx, gs:68h
0x1800590a4  mov     [rsp+78h+var_58], ebx
0x1800590a8  jmp     short loc_1800590CF
0x1800590aa  mov     r8, r15
0x1800590ad  mov     rdx, r12
0x1800590b0  mov     rcx, r14
0x1800590b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800590b8  mov     rbx, rax
0x1800590bb  mov     [rsp+78h+var_58], eax
0x1800590bf  jmp     short loc_1800590D1
0x1800590c1  mov     eax, gs:68h
0x1800590c9  mov     ebx, eax
0x1800590cb  mov     [rsp+78h+var_58], eax
0x1800590cf  xor     esi, esi
0x1800590d1  cmp     [rsp+78h+lpLibFileName], 0
0x1800590d7  jz      short loc_1800590F3
0x1800590d9  mov     rcx, gs:60h
0x1800590e2  mov     r8, [rsp+78h+lpLibFileName]; P
0x1800590e7  xor     edx, edx; Flags
0x1800590e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800590ed  call    cs:__imp_RtlFreeHeap
0x1800590f3  test    rdi, rdi
0x1800590f6  jz      short loc_180059101
0x1800590f8  mov     rcx, rdi; hLibModule
0x1800590fb  call    cs:__imp_FreeLibrary
0x180059101  test    ebx, ebx
0x180059103  jz      short loc_18005910F
0x180059105  mov     ecx, ebx; LastError
0x180059107  call    cs:__imp_RtlSetLastWin32Error
0x18005910d  xor     esi, esi
0x18005910f  mov     eax, esi
0x180059111  add     rsp, 48h
0x180059115  pop     r15
0x180059117  pop     r14
0x180059119  pop     r12
0x18005911b  pop     rdi
0x18005911c  pop     rsi
0x18005911d  pop     rbx
0x18005911e  retn
0x18007b63b  push    rbp
0x18007b63d  sub     rsp, 20h
0x18007b641  mov     rbp, rdx
0x18007b644  cmp     qword ptr [rbp+38h], 0
0x18007b649  jz      short loc_18007B665
0x18007b64b  mov     rcx, gs:60h
0x18007b654  mov     r8, [rbp+38h]; P
0x18007b658  xor     edx, edx; Flags
0x18007b65a  mov     rcx, [rcx+30h]; HeapHandle
0x18007b65e  call    cs:__imp_RtlFreeHeap
0x18007b664  nop
0x18007b665  mov     rcx, [rbp+28h]; hLibModule
0x18007b669  test    rcx, rcx
0x18007b66c  jz      short loc_18007B675
0x18007b66e  call    cs:__imp_FreeLibrary
0x18007b674  nop
0x18007b675  mov     ecx, [rbp+20h]; LastError
0x18007b678  test    ecx, ecx
0x18007b67a  jz      short loc_18007B683
0x18007b67c  call    cs:__imp_RtlSetLastWin32Error
0x18007b682  nop
0x18007b683  add     rsp, 20h
0x18007b687  pop     rbp
0x18007b688  retn
```
