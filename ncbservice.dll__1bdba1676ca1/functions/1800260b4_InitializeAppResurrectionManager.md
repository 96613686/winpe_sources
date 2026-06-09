# InitializeAppResurrectionManager

- ea: `0x1800260b4`
- end: `0x18002615e`
- name: `InitializeAppResurrectionManager`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180020a90`

## callees

- `0x18001dd2c`
- `0x180026070`
- `0x1800260b4`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x180026113`
- `ntdll!RtlCreateHashTable` at `0x180026113`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026127`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180026127`

## pseudocode

```c
__int64 __fastcall InitializeAppResurrectionManager(unsigned int a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rdi
  unsigned int v7; // ebx
  _QWORD *v9; // [rsp+40h] [rbp+18h] BYREF
  char *v10; // [rsp+48h] [rbp+20h] BYREF

  v9 = a3;
  v5 = operator new(0x68u);
  v6 = (__int64)v5;
  v5[11] = a2;
  *((_BYTE *)v5 + 80) = 0;
  if ( a1 >= 5 )
  {
    a1 = 5;
  }
  else if ( !a1 )
  {
    a1 = 1;
  }
  *((_DWORD *)v5 + 24) = a1;
  v9 = v5;
  v10 = (char *)(v5 + 5);
  if ( (unsigned __int8)RtlCreateHashTable(&v10, 0, 0) )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)v6);
    *(_BYTE *)(v6 + 80) = 1;
    v7 = 0;
    g_NcbCCResetAppResurrectionManager = v6;
    v9 = 0;
  }
  else
  {
    v7 = 8;
  }
  CleanupAppResurrectionManager(&v9);
  return v7;
}

```

## disassembly

```asm
0x1800260b4  mov     [rsp+arg_0], rbx
0x1800260b9  mov     [rsp+arg_8], rsi
0x1800260be  mov     [rsp+arg_10], r8
0x1800260c3  push    rdi
0x1800260c4  sub     rsp, 20h
0x1800260c8  mov     esi, ecx
0x1800260ca  mov     rbx, rdx
0x1800260cd  mov     ecx, 68h ; 'h'; Size
0x1800260d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800260d7  mov     rdi, rax
0x1800260da  mov     [rax+58h], rbx
0x1800260de  mov     ebx, 1
0x1800260e3  mov     byte ptr [rax+50h], 0
0x1800260e7  cmp     esi, 5
0x1800260ea  jnb     short loc_1800260F3
0x1800260ec  cmp     esi, ebx
0x1800260ee  cmovb   esi, ebx
0x1800260f1  jmp     short loc_1800260F8
0x1800260f3  mov     esi, 5
0x1800260f8  mov     [rax+60h], esi
0x1800260fb  lea     rcx, [rsp+28h+arg_18]
0x180026100  add     rax, 28h ; '('
0x180026104  mov     [rsp+28h+arg_10], rdi
0x180026109  xor     r8d, r8d
0x18002610c  mov     [rsp+28h+arg_18], rax
0x180026111  xor     edx, edx
0x180026113  call    cs:__imp_RtlCreateHashTable
0x180026119  test    al, al
0x18002611b  jnz     short loc_180026124
0x18002611d  mov     ebx, 8
0x180026122  jmp     short loc_180026142
0x180026124  mov     rcx, rdi; lpCriticalSection
0x180026127  call    cs:__imp_InitializeCriticalSection
0x18002612d  mov     [rdi+50h], bl
0x180026130  xor     ebx, ebx
0x180026132  mov     cs:g_NcbCCResetAppResurrectionManager, rdi
0x180026139  mov     [rsp+28h+arg_10], 0
0x180026142  lea     rcx, [rsp+28h+arg_10]
0x180026147  call    CleanupAppResurrectionManager
0x18002614c  mov     rsi, [rsp+28h+arg_8]
0x180026151  mov     eax, ebx
0x180026153  mov     rbx, [rsp+28h+arg_0]
0x180026158  add     rsp, 20h
0x18002615c  pop     rdi
0x18002615d  retn
```
