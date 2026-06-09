# GetFinalPath

- ea: `0x14000dfb8`
- end: `0x14000e10a`
- name: `GetFinalPath`
- size: `338`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000df1c`
- `0x14000e4c0`

## callees

- `0x14000dfb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e0b1`
- `ntdll!RtlAllocateHeap` at `0x14000e04f`
- `ntdll!RtlAllocateHeap` at `0x14000e04f`
- `ntdll!RtlFreeHeap` at `0x14000e087`
- `ntdll!RtlFreeHeap` at `0x14000e0e8`
- `ntdll!RtlFreeHeap` at `0x14000e087`
- `ntdll!RtlFreeHeap` at `0x14000e0e8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000dfff`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000dfff`

## pseudocode

```c
__int64 __fastcall GetFinalPath(HANDLE hFile, PVOID *a2, DWORD *a3)
{
  WCHAR *Heap; // rdi
  char v7; // si
  DWORD v8; // ebp
  DWORD FinalPathNameByHandleW; // ebp
  int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  int v13; // eax

  if ( !a2 )
    __int2c();
  if ( !a3 )
    __int2c();
  Heap = (WCHAR *)*a2;
  v7 = 0;
  v8 = *a3;
  while ( 1 )
  {
    SetLastError(0);
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, Heap, v8, 0);
    if ( FinalPathNameByHandleW )
    {
      if ( GetLastError() != 8 )
        break;
    }
    if ( GetLastError() != 8 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    if ( v7 )
    {
      v11 = -2147418113;
LABEL_22:
      if ( Heap )
      {
        if ( v7 )
        {
          LOBYTE(v13) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          if ( !v13 )
            __int2c();
        }
      }
      return v11;
    }
    v8 = FinalPathNameByHandleW + 1;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v8);
    if ( !Heap )
      return (unsigned int)-2147024882;
    v7 = 1;
  }
  if ( v7 )
  {
    if ( *a2 )
    {
      LOBYTE(v10) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a2);
      if ( !v10 )
        __int2c();
    }
    *a2 = Heap;
    *a3 = FinalPathNameByHandleW;
  }
  return 0;
}

```

## disassembly

```asm
0x14000dfb8  push    rbx
0x14000dfba  push    rbp
0x14000dfbb  push    rsi
0x14000dfbc  push    rdi
0x14000dfbd  push    r14
0x14000dfbf  push    r15
0x14000dfc1  sub     rsp, 28h
0x14000dfc5  mov     r14, r8
0x14000dfc8  mov     rbx, rdx
0x14000dfcb  mov     r15, rcx
0x14000dfce  test    rdx, rdx
0x14000dfd1  jnz     short loc_14000DFD5
0x14000dfd3  int     2Ch; Windows NT - assertion failure
0x14000dfd5  test    r14, r14
0x14000dfd8  jnz     short loc_14000DFDC
0x14000dfda  int     2Ch; Windows NT - assertion failure
0x14000dfdc  mov     rdi, [rdx]
0x14000dfdf  xor     sil, sil
0x14000dfe2  mov     ebp, [r8]
0x14000dfe5  xor     ecx, ecx; dwErrCode
0x14000dfe7  call    cs:__imp_SetLastError
0x14000dfee  nop     dword ptr [rax+rax+00h]
0x14000dff3  xor     r9d, r9d; dwFlags
0x14000dff6  mov     r8d, ebp; cchFilePath
0x14000dff9  mov     rdx, rdi; lpszFilePath
0x14000dffc  mov     rcx, r15; hFile
0x14000dfff  call    cs:__imp_GetFinalPathNameByHandleW
0x14000e006  nop     dword ptr [rax+rax+00h]
0x14000e00b  mov     ebp, eax
0x14000e00d  test    eax, eax
0x14000e00f  jz      short loc_14000E022
0x14000e011  call    cs:__imp_GetLastError
0x14000e018  nop     dword ptr [rax+rax+00h]
0x14000e01d  cmp     eax, 8
0x14000e020  jnz     short loc_14000E06B
0x14000e022  call    cs:__imp_GetLastError
0x14000e029  nop     dword ptr [rax+rax+00h]
0x14000e02e  cmp     eax, 8
0x14000e031  jnz     short loc_14000E0B1
0x14000e033  test    sil, sil
0x14000e036  jnz     short loc_14000E0AA
0x14000e038  mov     rcx, gs:60h
0x14000e041  inc     ebp
0x14000e043  mov     r8d, ebp
0x14000e046  xor     edx, edx; Flags
0x14000e048  add     r8, r8; Size
0x14000e04b  mov     rcx, [rcx+30h]; HeapHandle
0x14000e04f  call    cs:__imp_RtlAllocateHeap
0x14000e056  nop     dword ptr [rax+rax+00h]
0x14000e05b  mov     rdi, rax
0x14000e05e  test    rax, rax
0x14000e061  jz      short loc_14000E0A3
0x14000e063  mov     sil, 1
0x14000e066  jmp     loc_14000DFE5
0x14000e06b  test    sil, sil
0x14000e06e  jz      short loc_14000E09F
0x14000e070  mov     r8, [rbx]; P
0x14000e073  test    r8, r8
0x14000e076  jz      short loc_14000E099
0x14000e078  mov     rcx, gs:60h
0x14000e081  xor     edx, edx; Flags
0x14000e083  mov     rcx, [rcx+30h]; HeapHandle
0x14000e087  call    cs:__imp_RtlFreeHeap
0x14000e08e  nop     dword ptr [rax+rax+00h]
0x14000e093  test    eax, eax
0x14000e095  jnz     short loc_14000E099
0x14000e097  int     2Ch; Windows NT - assertion failure
0x14000e099  mov     [rbx], rdi
0x14000e09c  mov     [r14], ebp
0x14000e09f  xor     ebx, ebx
0x14000e0a1  jmp     short loc_14000E0FA
0x14000e0a3  mov     ebx, 8007000Eh
0x14000e0a8  jmp     short loc_14000E0FA
0x14000e0aa  mov     ebx, 8000FFFFh
0x14000e0af  jmp     short loc_14000E0CC
0x14000e0b1  call    cs:__imp_GetLastError
0x14000e0b8  nop     dword ptr [rax+rax+00h]
0x14000e0bd  mov     ebx, eax
0x14000e0bf  test    eax, eax
0x14000e0c1  jle     short loc_14000E0CC
0x14000e0c3  movzx   ebx, ax
0x14000e0c6  or      ebx, 80070000h
0x14000e0cc  test    rdi, rdi
0x14000e0cf  jz      short loc_14000E0FA
0x14000e0d1  test    sil, sil
0x14000e0d4  jz      short loc_14000E0FA
0x14000e0d6  mov     rcx, gs:60h
0x14000e0df  mov     r8, rdi; P
0x14000e0e2  xor     edx, edx; Flags
0x14000e0e4  mov     rcx, [rcx+30h]; HeapHandle
0x14000e0e8  call    cs:__imp_RtlFreeHeap
0x14000e0ef  nop     dword ptr [rax+rax+00h]
0x14000e0f4  test    eax, eax
0x14000e0f6  jnz     short loc_14000E0FA
0x14000e0f8  int     2Ch; Windows NT - assertion failure
0x14000e0fa  mov     eax, ebx
0x14000e0fc  add     rsp, 28h
0x14000e100  pop     r15
0x14000e102  pop     r14
0x14000e104  pop     rdi
0x14000e105  pop     rsi
0x14000e106  pop     rbp
0x14000e107  pop     rbx
0x14000e108  retn
```
