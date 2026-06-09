# CVolume::MoveBitlockerMetadata(void)

- ea: `0x18003b1c0`
- end: `0x18003b39e`
- name: `?MoveBitlockerMetadata@CVolume@@UEAAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(CVolume *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18003b1c0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b25d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b2c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b25d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b2c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b36d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b36d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003b223`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003b223`

## string_xrefs

- `0x18003b1e4`: `CVolume::MoveBitlockerMetadata`
- `0x18003b21c`: `fveapi.dll`
- `0x18003b253`: `FveOpenVolumeByHandle`
- `0x18003b286`: `FveRecalculateOffsetsAndMoveMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVolume::MoveBitlockerMetadata(CVolume *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  HMODULE LibraryW; // rbx
  __int64 v5; // r8
  __int64 v6; // r9
  __int16 v7; // ax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  FARPROC ProcAddress; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  FARPROC v15; // rsi
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // ebx
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-19h] BYREF
  __int16 v25; // [rsp+44h] [rbp-15h]
  __int16 v26; // [rsp+46h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CVolume::MoveBitlockerMetadata",
    2808,
    1);
  if ( (unsigned __int64)(*((_QWORD *)this + 5) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = -2147467259;
    v26 = 2815;
    goto LABEL_17;
  }
  LastFailureAsHRESULT = 0;
  v25 = 2815;
  LibraryW = LoadLibraryW(L"fveapi.dll");
  if ( !LibraryW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v3, v2, v5, v6);
    v7 = 2818;
LABEL_4:
    v26 = v7;
    goto LABEL_14;
  }
  LastFailureAsHRESULT = 0;
  v25 = 2818;
  ProcAddress = GetProcAddress(LibraryW, "FveOpenVolumeByHandle");
  if ( !ProcAddress )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9, v8, v10, v11);
    v7 = 2821;
    goto LABEL_4;
  }
  LastFailureAsHRESULT = 0;
  v25 = 2821;
  v15 = GetProcAddress(LibraryW, "FveRecalculateOffsetsAndMoveMetadata");
  if ( !v15 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14, v13, v16, v17);
    v7 = 2824;
    goto LABEL_4;
  }
  LastFailureAsHRESULT = 0;
  v25 = 2824;
  if ( !GetProcAddress(LibraryW, "FveCloseVolume") )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v19, v18, v20, v21);
    v7 = 2826;
    goto LABEL_4;
  }
  LastFailureAsHRESULT = 0;
  v25 = 2826;
  LastFailureAsHRESULT = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(*((_QWORD *)this + 5), 1, 1);
  v7 = 2828;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v25 = 2828;
  LastFailureAsHRESULT = ((__int64 (__fastcall *)(_QWORD))v15)(0);
  v7 = 2829;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_4;
  v25 = 2829;
LABEL_14:
  if ( LibraryW )
    FreeLibrary(LibraryW);
LABEL_17:
  v22 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v22;
}

```

## disassembly

```asm
0x18003b1c0  push    rbp
0x18003b1c2  push    rbx
0x18003b1c3  push    rsi
0x18003b1c4  push    rdi
0x18003b1c5  push    r14
0x18003b1c7  push    r15
0x18003b1c9  lea     rbp, [rsp-2Fh]
0x18003b1ce  sub     rsp, 88h
0x18003b1d5  mov     r15, rcx
0x18003b1d8  mov     r9d, 1; unsigned __int16
0x18003b1de  mov     r8d, 0AF8h; unsigned __int16
0x18003b1e4  lea     rdx, aCvolumeMovebit; "CVolume::MoveBitlockerMetadata"
0x18003b1eb  lea     rcx, [rbp+57h+var_70]; this
0x18003b1ef  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003b1f4  nop
0x18003b1f5  mov     [rbp+57h+arg_0], 0
0x18003b1fd  mov     rax, [r15+28h]
0x18003b201  dec     rax
0x18003b204  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b208  mov     eax, 0AFFh
0x18003b20d  ja      loc_18003B375
0x18003b213  xor     edi, edi
0x18003b215  mov     [rbp+57h+var_70], edi
0x18003b218  mov     [rbp+57h+var_6C], ax
0x18003b21c  lea     rcx, LibFileName; "fveapi.dll"
0x18003b223  call    cs:__imp_LoadLibraryW
0x18003b229  mov     rbx, rax
0x18003b22c  test    rax, rax
0x18003b22f  jnz     short loc_18003B247
0x18003b231  call    GetLastFailureAsHRESULT
0x18003b236  mov     [rbp+57h+var_70], eax
0x18003b239  mov     eax, 0B02h
0x18003b23e  mov     [rbp+57h+var_6A], ax
0x18003b242  jmp     loc_18003B34F
0x18003b247  mov     [rbp+57h+var_70], edi
0x18003b24a  mov     eax, 0B02h
0x18003b24f  mov     [rbp+57h+var_6C], ax
0x18003b253  lea     rdx, ProcName; "FveOpenVolumeByHandle"
0x18003b25a  mov     rcx, rbx; hModule
0x18003b25d  call    cs:__imp_GetProcAddress
0x18003b263  mov     r14, rax
0x18003b266  test    rax, rax
0x18003b269  jnz     short loc_18003B27A
0x18003b26b  call    GetLastFailureAsHRESULT
0x18003b270  mov     [rbp+57h+var_70], eax
0x18003b273  mov     eax, 0B05h
0x18003b278  jmp     short loc_18003B23E
0x18003b27a  mov     [rbp+57h+var_70], edi
0x18003b27d  mov     eax, 0B05h
0x18003b282  mov     [rbp+57h+var_6C], ax
0x18003b286  lea     rdx, aFverecalculate; "FveRecalculateOffsetsAndMoveMetadata"
0x18003b28d  mov     rcx, rbx; hModule
0x18003b290  call    cs:__imp_GetProcAddress
0x18003b296  mov     rsi, rax
0x18003b299  test    rax, rax
0x18003b29c  jnz     short loc_18003B2AD
0x18003b29e  call    GetLastFailureAsHRESULT
0x18003b2a3  mov     [rbp+57h+var_70], eax
0x18003b2a6  mov     eax, 0B08h
0x18003b2ab  jmp     short loc_18003B23E
0x18003b2ad  mov     [rbp+57h+var_70], edi
0x18003b2b0  mov     eax, 0B08h
0x18003b2b5  mov     [rbp+57h+var_6C], ax
0x18003b2b9  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x18003b2c0  mov     rcx, rbx; hModule
0x18003b2c3  call    cs:__imp_GetProcAddress
0x18003b2c9  mov     rdi, rax
0x18003b2cc  test    rax, rax
0x18003b2cf  jnz     short loc_18003B2E3
0x18003b2d1  call    GetLastFailureAsHRESULT
0x18003b2d6  mov     [rbp+57h+var_70], eax
0x18003b2d9  mov     eax, 0B0Ah
0x18003b2de  jmp     loc_18003B23E
0x18003b2e3  mov     [rbp+57h+var_70], 0
0x18003b2ea  mov     eax, 0B0Ah
0x18003b2ef  mov     [rbp+57h+var_6C], ax
0x18003b2f3  lea     rax, [rbp+57h+arg_0]
0x18003b2f7  mov     [rsp+0B0h+var_88], rax
0x18003b2fc  mov     [rsp+0B0h+var_90], 0
0x18003b304  or      r9d, 0FFFFFFFFh
0x18003b308  lea     edx, [r9+2]
0x18003b30c  mov     r8d, edx
0x18003b30f  mov     rcx, [r15+28h]
0x18003b313  mov     rax, r14
0x18003b316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b31b  mov     [rbp+57h+var_70], eax
0x18003b31e  test    eax, eax
0x18003b320  mov     eax, 0B0Ch
0x18003b325  js      loc_18003B23E
0x18003b32b  mov     [rbp+57h+var_6C], ax
0x18003b32f  mov     rcx, [rbp+57h+arg_0]
0x18003b333  mov     rax, rsi
0x18003b336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b33b  mov     [rbp+57h+var_70], eax
0x18003b33e  test    eax, eax
0x18003b340  mov     eax, 0B0Dh
0x18003b345  js      loc_18003B23E
0x18003b34b  mov     [rbp+57h+var_6C], ax
0x18003b34f  mov     rcx, [rbp+57h+arg_0]
0x18003b353  test    rcx, rcx
0x18003b356  jz      short loc_18003B365
0x18003b358  test    rdi, rdi
0x18003b35b  jz      short loc_18003B365
0x18003b35d  mov     rax, rdi
0x18003b360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b365  test    rbx, rbx
0x18003b368  jz      short loc_18003B380
0x18003b36a  mov     rcx, rbx; hLibModule
0x18003b36d  call    cs:__imp_FreeLibrary
0x18003b373  jmp     short loc_18003B380
0x18003b375  mov     [rbp+57h+var_70], 80004005h
0x18003b37c  mov     [rbp+57h+var_6A], ax
0x18003b380  mov     ebx, [rbp+57h+var_70]
0x18003b383  lea     rcx, [rbp+57h+var_70]; this
0x18003b387  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003b38c  mov     eax, ebx
0x18003b38e  add     rsp, 88h
0x18003b395  pop     r15
0x18003b397  pop     r14
0x18003b399  pop     rdi
0x18003b39a  pop     rsi
0x18003b39b  pop     rbx
0x18003b39c  pop     rbp
0x18003b39d  retn
```
