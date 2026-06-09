# SockOpenNetworkDataBase

- ea: `0x1800011d8`
- end: `0x1800013c2`
- name: `SockOpenNetworkDataBase`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180001124`

## callees

- `0x1800011d8`
- `0x1800013c8`
- `0x180001600`
- `0x1800016a0`
- `0x18000170c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000121e`
- `ntdll!RtlAllocateHeap` at `0x180001248`
- `ntdll!RtlAllocateHeap` at `0x18000121e`
- `ntdll!RtlAllocateHeap` at `0x180001248`
- `ntdll!NtClose` at `0x18000128b`
- `ntdll!NtClose` at `0x18000128b`
- `ntdll!RtlFreeHeap` at `0x18000132d`
- `ntdll!RtlFreeHeap` at `0x180001350`
- `ntdll!RtlFreeHeap` at `0x18000132d`
- `ntdll!RtlFreeHeap` at `0x180001350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000138c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000138c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013a6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180001302`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180001302`

## string_xrefs

- `0x180001373`: `services`

## pseudocode

```c
HANDLE __fastcall SockOpenNetworkDataBase(__int64 a1, char *a2)
{
  HANDLE FileA; // rbp
  char *Heap; // rdi
  PVOID v5; // r14
  int SingleValue; // ebx
  __int64 v7; // rax
  size_t v8; // rdx
  size_t v9; // rdx
  DWORD v11; // ecx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-38h]
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+78h] [rbp+20h]

  Handle = 0;
  v14 = 0;
  FileA = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  if ( !Heap )
  {
    SetLastError(8u);
    return FileA;
  }
  v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  if ( v5 )
  {
    if ( (int)SockOpenKeyEx(&Handle) < 0 )
    {
      v11 = 1011;
    }
    else
    {
      SingleValue = SockGetSingleValue(Handle, dwCreationDisposition);
      NtClose(Handle);
      if ( SingleValue < 0 )
      {
        v11 = 1012;
      }
      else
      {
        v7 = -1;
        do
          ++v7;
        while ( Heap[v7] );
        if ( (int)v7 + 10 <= 270 )
        {
          if ( StringCbCopyA(a2, 0x10Eu, Heap) >= 0 && StringCbCatA(a2, v8, "\\") >= 0 )
            StringCbCatA(a2, v9, "services");
          FileA = CreateFileA(a2, 0x80000000, 1u, 0, 3u, 0, 0);
          if ( FileA == (HANDLE)-1LL )
            FileA = 0;
          goto LABEL_13;
        }
        v11 = 122;
      }
    }
  }
  else
  {
    v11 = 8;
  }
  SetLastError(v11);
LABEL_13:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return FileA;
}

```

## disassembly

```asm
0x1800011d8  mov     rax, rsp
0x1800011db  mov     [rax+10h], rbx
0x1800011df  mov     [rax+18h], rbp
0x1800011e3  mov     [rax+20h], r9d
0x1800011e7  mov     [rax+8], rcx
0x1800011eb  push    rsi
0x1800011ec  push    rdi
0x1800011ed  push    r14
0x1800011ef  sub     rsp, 40h
0x1800011f3  mov     qword ptr [rax+8], 0
0x1800011fb  mov     rsi, rdx
0x1800011fe  mov     rcx, gs:60h
0x180001207  mov     ebx, 400h
0x18000120c  mov     r8d, ebx; Size
0x18000120f  mov     dword ptr [rax+20h], 0
0x180001216  xor     edx, edx; Flags
0x180001218  xor     ebp, ebp
0x18000121a  mov     rcx, [rcx+30h]; HeapHandle
0x18000121e  call    cs:__imp_RtlAllocateHeap
0x180001225  nop     dword ptr [rax+rax+00h]
0x18000122a  mov     rdi, rax
0x18000122d  test    rax, rax
0x180001230  jz      loc_1800013A1
0x180001236  mov     rcx, gs:60h
0x18000123f  mov     r8d, ebx; Size
0x180001242  xor     edx, edx; Flags
0x180001244  mov     rcx, [rcx+30h]; HeapHandle
0x180001248  call    cs:__imp_RtlAllocateHeap
0x18000124f  nop     dword ptr [rax+rax+00h]
0x180001254  mov     r14, rax
0x180001257  test    rax, rax
0x18000125a  jz      loc_1800013B4
0x180001260  lea     rcx, [rsp+58h+Handle]; KeyHandle
0x180001265  call    SockOpenKeyEx
0x18000126a  test    eax, eax
0x18000126c  js      loc_18000139A
0x180001272  mov     rcx, [rsp+58h+Handle]; KeyHandle
0x180001277  lea     r9, [rsp+58h+arg_18]
0x18000127c  mov     r8, rdi
0x18000127f  call    SockGetSingleValue
0x180001284  mov     rcx, [rsp+58h+Handle]; Handle
0x180001289  mov     ebx, eax
0x18000128b  call    cs:__imp_NtClose
0x180001292  nop     dword ptr [rax+rax+00h]
0x180001297  test    ebx, ebx
0x180001299  js      loc_1800013BB
0x18000129f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800012a3  inc     rax
0x1800012a6  cmp     [rdi+rax], bpl
0x1800012aa  jnz     short loc_1800012A3
0x1800012ac  add     eax, 0Ah
0x1800012af  mov     edx, 10Eh; cbDest
0x1800012b4  cmp     eax, edx
0x1800012b6  jg      loc_180001387
0x1800012bc  mov     r8, rdi; pszSrc
0x1800012bf  mov     rcx, rsi; pszDest
0x1800012c2  call    StringCbCopyA
0x1800012c7  test    eax, eax
0x1800012c9  js      short loc_1800012E2
0x1800012cb  lea     r8, pszSrc; "\\"
0x1800012d2  mov     rcx, rsi; pszDest
0x1800012d5  call    StringCbCatA
0x1800012da  test    eax, eax
0x1800012dc  jns     loc_180001373
0x1800012e2  xor     r9d, r9d; lpSecurityAttributes
0x1800012e5  mov     [rsp+58h+hTemplateFile], rbp; hTemplateFile
0x1800012ea  mov     [rsp+58h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1800012ee  mov     edx, 80000000h; dwDesiredAccess
0x1800012f3  mov     rcx, rsi; lpFileName
0x1800012f6  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800012fe  lea     r8d, [r9+1]; dwShareMode
0x180001302  call    cs:__imp_CreateFileA
0x180001309  nop     dword ptr [rax+rax+00h]
0x18000130e  mov     rbp, rax
0x180001311  xor     eax, eax
0x180001313  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180001317  cmovz   rbp, rax
0x18000131b  mov     rcx, gs:60h
0x180001324  mov     r8, rdi; P
0x180001327  xor     edx, edx; Flags
0x180001329  mov     rcx, [rcx+30h]; HeapHandle
0x18000132d  call    cs:__imp_RtlFreeHeap
0x180001334  nop     dword ptr [rax+rax+00h]
0x180001339  test    r14, r14
0x18000133c  jz      short loc_18000135C
0x18000133e  mov     rcx, gs:60h
0x180001347  mov     r8, r14; P
0x18000134a  xor     edx, edx; Flags
0x18000134c  mov     rcx, [rcx+30h]; HeapHandle
0x180001350  call    cs:__imp_RtlFreeHeap
0x180001357  nop     dword ptr [rax+rax+00h]
0x18000135c  mov     rbx, [rsp+58h+arg_8]
0x180001361  mov     rax, rbp
0x180001364  mov     rbp, [rsp+58h+arg_10]
0x180001369  add     rsp, 40h
0x18000136d  pop     r14
0x18000136f  pop     rdi
0x180001370  pop     rsi
0x180001371  retn
0x180001373  lea     r8, aServices; "services"
0x18000137a  mov     rcx, rsi; pszDest
0x18000137d  call    StringCbCatA
0x180001382  jmp     loc_1800012E2
0x180001387  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000138c  call    cs:__imp_SetLastError
0x180001393  nop     dword ptr [rax+rax+00h]
0x180001398  jmp     short loc_18000131B
0x18000139a  mov     ecx, 3F3h
0x18000139f  jmp     short loc_18000138C
0x1800013a1  mov     ecx, 8; dwErrCode
0x1800013a6  call    cs:__imp_SetLastError
0x1800013ad  nop     dword ptr [rax+rax+00h]
0x1800013b2  jmp     short loc_18000135C
0x1800013b4  mov     ecx, 8
0x1800013b9  jmp     short loc_18000138C
0x1800013bb  mov     ecx, 3F4h
0x1800013c0  jmp     short loc_18000138C
```
