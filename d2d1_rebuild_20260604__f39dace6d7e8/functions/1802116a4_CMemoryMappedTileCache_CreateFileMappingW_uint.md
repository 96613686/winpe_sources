# CMemoryMappedTileCache::CreateFileMappingW(uint)

- ea: `0x1802116a4`
- end: `0x18021179b`
- name: `?CreateFileMappingW@CMemoryMappedTileCache@@IEAAJI@Z`
- size: `247`
- prototype: `int(CMemoryMappedTileCache *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180211198`

## callees

- `0x18001fd58`
- `0x180111300`
- `0x180183aa0`
- `0x180211670`
- `0x1802116a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021176d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021176d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1802116c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1802116c8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180211760`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180211760`

## pseudocode

```c
__int64 __fastcall CMemoryMappedTileCache::CreateFileMappingW(UINT *this, unsigned int a2)
{
  ULONGLONG v2; // rdi
  CMemoryMappedTileCache *v4; // rcx
  int v5; // ebx
  unsigned int *v7; // rdx
  ULONGLONG v8; // rdx
  HRESULT v9; // eax
  unsigned int v10; // edi
  signed int LastError; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF
  ULONGLONG pullResult; // [rsp+A0h] [rbp+38h] BYREF

  v2 = a2;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  LODWORD(pullResult) = 0;
  v5 = CMemoryMappedTileCache::DivideAndRoundUp(
         v4,
         0x10000u,
         SystemInfo.dwAllocationGranularity,
         (unsigned int *)&pullResult);
  if ( v5 < 0 )
    goto LABEL_2;
  v5 = ULongLongToUInt((unsigned int)pullResult * (unsigned __int64)SystemInfo.dwAllocationGranularity, this + 47);
  if ( v5 < 0 )
    goto LABEL_2;
  v8 = *v7;
  pullResult = 0;
  v9 = ULongLongMult(v2, v8, &pullResult);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *((_QWORD *)this + 24) = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, HIDWORD(pullResult), pullResult, 0);
    LastError = GetLastError();
    v5 = LastError;
    if ( *((_QWORD *)this + 24) )
      return v10;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
LABEL_2:
    DoStackCapture(v5);
    return (unsigned int)v5;
  }
  DoStackCapture(v9);
  return v10;
}

```

## disassembly

```asm
0x1802116a4  push    rbp
0x1802116a6  push    rbx
0x1802116a7  push    rsi
0x1802116a8  push    rdi
0x1802116a9  mov     rbp, rsp
0x1802116ac  sub     rsp, 68h
0x1802116b0  xorps   xmm0, xmm0
0x1802116b3  mov     edi, edx
0x1802116b5  mov     rsi, rcx
0x1802116b8  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1802116bc  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1802116c0  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1802116c4  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1802116c8  call    cs:__imp_GetSystemInfo
0x1802116ce  mov     r8d, [rbp+SystemInfo.dwAllocationGranularity]; unsigned int
0x1802116d2  lea     r9, [rbp+pullResult]; unsigned int *
0x1802116d6  mov     edx, 10000h; unsigned int
0x1802116db  mov     dword ptr [rbp+pullResult], 0
0x1802116e2  call    ?DivideAndRoundUp@CMemoryMappedTileCache@@IEAAJIIPEAI@Z; CMemoryMappedTileCache::DivideAndRoundUp(uint,uint,uint *)
0x1802116e7  mov     ebx, eax
0x1802116e9  test    eax, eax
0x1802116eb  jns     short loc_1802116F8
0x1802116ed  mov     ecx, ebx; int
0x1802116ef  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1802116f4  mov     eax, ebx
0x1802116f6  jmp     short loc_180211739
0x1802116f8  mov     eax, dword ptr [rbp+pullResult]
0x1802116fb  lea     rdx, [rsi+0BCh]; puResult
0x180211702  mov     ecx, [rbp+SystemInfo.dwAllocationGranularity]
0x180211705  imul    rcx, rax; ullOperand
0x180211709  call    ULongLongToUInt
0x18021170e  mov     ebx, eax
0x180211710  test    eax, eax
0x180211712  js      short loc_1802116ED
0x180211714  mov     edx, [rdx]; ullMultiplier
0x180211716  lea     r8, [rbp+pullResult]; pullResult
0x18021171a  mov     rcx, rdi; ullMultiplicand
0x18021171d  mov     [rbp+pullResult], 0
0x180211725  call    ULongLongMult
0x18021172a  mov     edi, eax
0x18021172c  test    eax, eax
0x18021172e  jns     short loc_180211742
0x180211730  mov     ecx, eax; int
0x180211732  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180211737  mov     eax, edi
0x180211739  add     rsp, 68h
0x18021173d  pop     rdi
0x18021173e  pop     rsi
0x18021173f  pop     rbx
0x180211740  pop     rbp
0x180211741  retn
0x180211742  mov     eax, dword ptr [rbp+pullResult]
0x180211745  xor     edx, edx; lpFileMappingAttributes
0x180211747  mov     r9d, dword ptr [rbp+pullResult+4]; dwMaximumSizeHigh
0x18021174b  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18021174f  mov     [rsp+68h+lpName], 0; lpName
0x180211758  mov     [rsp+68h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18021175c  lea     r8d, [rdx+4]; flProtect
0x180211760  call    cs:__imp_CreateFileMappingW
0x180211766  mov     [rsi+0C0h], rax
0x18021176d  call    cs:__imp_GetLastError
0x180211773  cmp     qword ptr [rsi+0C0h], 0
0x18021177b  mov     ebx, eax
0x18021177d  jnz     short loc_180211737
0x18021177f  test    eax, eax
0x180211781  jle     short loc_18021178C
0x180211783  movzx   ebx, ax
0x180211786  or      ebx, 80070000h
0x18021178c  test    ebx, ebx
0x18021178e  mov     eax, 80004005h
0x180211793  cmovns  ebx, eax
0x180211796  jmp     loc_1802116ED
```
