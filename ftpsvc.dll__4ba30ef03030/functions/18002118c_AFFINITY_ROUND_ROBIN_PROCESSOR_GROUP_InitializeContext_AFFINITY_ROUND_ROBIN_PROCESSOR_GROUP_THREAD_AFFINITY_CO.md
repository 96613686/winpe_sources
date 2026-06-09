# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)

- ea: `0x18002118c`
- end: `0x1800212c2`
- name: `?InitializeContext@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJPEAUTHREAD_AFFINITY_CONTEXT@1@@Z`
- size: `310`
- prototype: `__int64 __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this, struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180020c84`

## callees

- `0x18002118c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800211c2`
- `KERNEL32!GetLastError` at `0x180021209`
- `KERNEL32!GetLastError` at `0x18002122c`
- `KERNEL32!GetLastError` at `0x180021277`
- `KERNEL32!GetLastError` at `0x1800211c2`
- `KERNEL32!GetLastError` at `0x180021209`
- `KERNEL32!GetLastError` at `0x18002122c`
- `KERNEL32!GetLastError` at `0x180021277`
- `KERNEL32!HeapFree` at `0x1800212a3`
- `KERNEL32!HeapFree` at `0x1800212a3`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1800211b8`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021222`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x1800211b8`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180021222`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18002126d`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18002126d`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002128f`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002128f`
- `KERNEL32!HeapAlloc` at `0x1800211fb`
- `KERNEL32!HeapAlloc` at `0x1800211fb`
- `KERNEL32!GetProcessHeap` at `0x1800211ea`
- `KERNEL32!GetProcessHeap` at `0x180021295`
- `KERNEL32!GetProcessHeap` at `0x1800211ea`
- `KERNEL32!GetProcessHeap` at `0x180021295`

## pseudocode

```c
__int64 __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *this,
        struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rdi
  signed int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rax
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF

  dwBytes = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &dwBytes) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError != 122 )
    {
LABEL_3:
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v4;
    }
  }
  v5 = dwBytes;
  ProcessHeap = GetProcessHeap();
  v7 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 8u, v5);
  v8 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    v4 = LastError;
    goto LABEL_3;
  }
  if ( InitializeProcThreadAttributeList(v7, 1u, 0, &dwBytes) )
  {
    if ( UpdateProcThreadAttribute(v8, 0, 0x30003u, (char *)a2 + 8, 0x10u, 0, 0) )
    {
      v4 = 0;
      *(_QWORD *)a2 = v8;
      return v4;
    }
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    DeleteProcThreadAttributeList(v8);
  }
  else
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
  }
  v11 = GetProcessHeap();
  HeapFree(v11, 0, v8);
  return v4;
}

```

## disassembly

```asm
0x18002118c  mov     rax, rsp
0x18002118f  mov     [rax+10h], rbx
0x180021193  mov     [rax+18h], rsi
0x180021197  mov     [rax+8], rcx
0x18002119b  push    rdi
0x18002119c  sub     rsp, 40h
0x1800211a0  xor     r8d, r8d; dwFlags
0x1800211a3  mov     qword ptr [rax+8], 0
0x1800211ab  mov     rsi, rdx
0x1800211ae  lea     r9, [rax+8]; lpSize
0x1800211b2  xor     ecx, ecx; lpAttributeList
0x1800211b4  lea     edx, [r8+1]; dwAttributeCount
0x1800211b8  call    cs:__imp_InitializeProcThreadAttributeList
0x1800211be  test    eax, eax
0x1800211c0  jnz     short loc_1800211E5
0x1800211c2  call    cs:__imp_GetLastError
0x1800211c8  mov     ebx, eax
0x1800211ca  cmp     eax, 7Ah ; 'z'
0x1800211cd  jz      short loc_1800211E5
0x1800211cf  test    eax, eax
0x1800211d1  jle     loc_1800212B0
0x1800211d7  movzx   ebx, ax
0x1800211da  or      ebx, 80070000h
0x1800211e0  jmp     loc_1800212B0
0x1800211e5  mov     rbx, [rsp+48h+dwBytes]
0x1800211ea  call    cs:__imp_GetProcessHeap
0x1800211f0  mov     r8, rbx; dwBytes
0x1800211f3  mov     edx, 8; dwFlags
0x1800211f8  mov     rcx, rax; hHeap
0x1800211fb  call    cs:__imp_HeapAlloc
0x180021201  mov     rdi, rax
0x180021204  test    rax, rax
0x180021207  jnz     short loc_180021213
0x180021209  call    cs:__imp_GetLastError
0x18002120f  mov     ebx, eax
0x180021211  jmp     short loc_1800211CF
0x180021213  xor     r8d, r8d; dwFlags
0x180021216  lea     r9, [rsp+48h+dwBytes]; lpSize
0x18002121b  mov     rcx, rdi; lpAttributeList
0x18002121e  lea     edx, [r8+1]; dwAttributeCount
0x180021222  call    cs:__imp_InitializeProcThreadAttributeList
0x180021228  test    eax, eax
0x18002122a  jnz     short loc_180021243
0x18002122c  call    cs:__imp_GetLastError
0x180021232  mov     ebx, eax
0x180021234  test    eax, eax
0x180021236  jle     short loc_180021295
0x180021238  movzx   ebx, ax
0x18002123b  or      ebx, 80070000h
0x180021241  jmp     short loc_180021295
0x180021243  mov     [rsp+48h+lpReturnSize], 0; lpReturnSize
0x18002124c  lea     r9, [rsi+8]; lpValue
0x180021250  mov     [rsp+48h+lpPreviousValue], 0; lpPreviousValue
0x180021259  xor     edx, edx; dwFlags
0x18002125b  mov     r8d, 30003h; Attribute
0x180021261  mov     [rsp+48h+cbSize], 10h; cbSize
0x18002126a  mov     rcx, rdi; lpAttributeList
0x18002126d  call    cs:__imp_UpdateProcThreadAttribute
0x180021273  test    eax, eax
0x180021275  jnz     short loc_1800212AB
0x180021277  call    cs:__imp_GetLastError
0x18002127d  mov     ebx, eax
0x18002127f  test    eax, eax
0x180021281  jle     short loc_18002128C
0x180021283  movzx   ebx, ax
0x180021286  or      ebx, 80070000h
0x18002128c  mov     rcx, rdi; lpAttributeList
0x18002128f  call    cs:__imp_DeleteProcThreadAttributeList
0x180021295  call    cs:__imp_GetProcessHeap
0x18002129b  mov     r8, rdi; lpMem
0x18002129e  xor     edx, edx; dwFlags
0x1800212a0  mov     rcx, rax; hHeap
0x1800212a3  call    cs:__imp_HeapFree
0x1800212a9  jmp     short loc_1800212B0
0x1800212ab  xor     ebx, ebx
0x1800212ad  mov     [rsi], rdi
0x1800212b0  mov     rsi, [rsp+48h+arg_10]
0x1800212b5  mov     eax, ebx
0x1800212b7  mov     rbx, [rsp+48h+arg_8]
0x1800212bc  add     rsp, 40h
0x1800212c0  pop     rdi
0x1800212c1  retn
```
