# pSetupCreateKeyEx

- ea: `0x18000355c`
- end: `0x1800036a0`
- name: `pSetupCreateKeyEx`
- size: `324`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180001ad0`
- `0x180005970`

## callees

- `0x18000355c`
- `0x1800036a8`
- `0x180006f1c`

## import_xrefs

- `msvcrt!wcschr` at `0x1800035e3`
- `msvcrt!wcschr` at `0x1800035e3`
- `ntdll!NtClose` at `0x18000363b`
- `ntdll!NtClose` at `0x18000363b`
- `KERNEL32!HeapFree` at `0x180003664`
- `KERNEL32!HeapFree` at `0x180003664`

## pseudocode

```c
__int64 __fastcall pSetupCreateKeyEx(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        ACCESS_MASK a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 *v7; // r14
  __int64 v8; // rsi
  ACCESS_MASK v9; // r12d
  unsigned int KeyWorker; // edi
  __int64 v13; // rax
  void *v14; // rbp
  const wchar_t *v15; // rbx
  const WCHAR *v16; // rdi
  wchar_t *v17; // rax
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v21; // [rsp+28h] [rbp-60h]
  __int64 v22; // [rsp+28h] [rbp-60h]
  __int64 v23; // [rsp+A0h] [rbp+18h] BYREF

  v7 = a7;
  v8 = -2147483646;
  v9 = a5;
  v23 = 0;
  KeyWorker = pSetupCreateKeyWorker((void *)0xFFFFFFFF80000002LL, a2, a3, a4, a5, v21, a7);
  if ( KeyWorker != 2 || !a2 )
    return KeyWorker;
  v13 = pSetupDuplicateString(a2);
  v14 = (void *)v13;
  if ( !v13 )
    return 14;
  v15 = (const wchar_t *)v13;
  do
  {
    v16 = v15;
    v17 = wcschr(v15, 0x5Cu);
    v15 = v17;
    if ( !v17 )
      goto LABEL_11;
    *v17 = 0;
    do
      ++v15;
    while ( *v15 == 92 );
    if ( !*v15 )
    {
      v15 = 0;
LABEL_11:
      v19 = pSetupCreateKeyWorker((void *)v8, v16, v18, a4, v9, v22, &v23);
      goto LABEL_12;
    }
    if ( !v15 )
      goto LABEL_11;
    v19 = pSetupCreateKeyWorker((void *)v8, v16, v18, a4 & 0xFFFFFFFC, 4u, v22, &v23);
LABEL_12:
    KeyWorker = v19;
    if ( v8 != -2147483646 )
      NtClose((HANDLE)(unsigned int)v8);
    if ( KeyWorker )
      goto LABEL_17;
    v8 = v23;
  }
  while ( v15 );
  *v7 = v23;
LABEL_17:
  HeapFree(hHeap, 0, v14);
  return KeyWorker;
}

```

## disassembly

```asm
0x18000355c  mov     rax, rsp
0x18000355f  mov     [rax+18h], r8
0x180003563  push    rbx
0x180003564  push    rbp
0x180003565  push    rsi
0x180003566  push    rdi
0x180003567  push    r12
0x180003569  push    r13
0x18000356b  push    r14
0x18000356d  push    r15
0x18000356f  sub     rsp, 48h
0x180003573  mov     r14, [rsp+88h+arg_30]
0x18000357b  mov     rsi, 0FFFFFFFF80000002h
0x180003582  mov     r12d, [rsp+88h+arg_20]
0x18000358a  xor     r13d, r13d
0x18000358d  mov     [rax-58h], r14
0x180003591  mov     rcx, rsi
0x180003594  mov     [rax-68h], r12d
0x180003598  mov     r15d, r9d
0x18000359b  mov     rbx, rdx
0x18000359e  mov     [rax+18h], r13
0x1800035a2  call    pSetupCreateKeyWorker
0x1800035a7  mov     edi, eax
0x1800035a9  cmp     eax, 2
0x1800035ac  jnz     loc_18000366A
0x1800035b2  test    rbx, rbx
0x1800035b5  jz      loc_18000366A
0x1800035bb  mov     rcx, rbx; pszSrc
0x1800035be  call    pSetupDuplicateString
0x1800035c3  mov     rbp, rax
0x1800035c6  test    rax, rax
0x1800035c9  jnz     short loc_1800035D3
0x1800035cb  lea     edi, [rax+0Eh]
0x1800035ce  jmp     loc_18000366A
0x1800035d3  mov     rbx, rbp
0x1800035d6  mov     eax, 5Ch ; '\'
0x1800035db  mov     edx, eax; Ch
0x1800035dd  mov     rcx, rbx; Str
0x1800035e0  mov     rdi, rbx
0x1800035e3  call    cs:__imp_wcschr
0x1800035e9  mov     rbx, rax
0x1800035ec  test    rax, rax
0x1800035ef  jz      short loc_18000360E
0x1800035f1  mov     [rax], r13w
0x1800035f5  mov     ecx, 5Ch ; '\'
0x1800035fa  add     rbx, 2
0x1800035fe  movzx   eax, word ptr [rbx]
0x180003601  cmp     ax, cx
0x180003604  jz      short loc_1800035FA
0x180003606  test    ax, ax
0x180003609  jnz     short loc_18000367D
0x18000360b  mov     rbx, r13
0x18000360e  lea     rax, [rsp+88h+arg_10]
0x180003616  mov     r9d, r15d
0x180003619  mov     [rsp+88h+var_58], rax
0x18000361e  mov     [rsp+88h+var_68], r12d
0x180003623  mov     rdx, rdi
0x180003626  mov     rcx, rsi
0x180003629  call    pSetupCreateKeyWorker
0x18000362e  mov     edi, eax
0x180003630  cmp     rsi, 0FFFFFFFF80000002h
0x180003637  jz      short loc_180003641
0x180003639  mov     ecx, esi; Handle
0x18000363b  call    cs:__imp_NtClose
0x180003641  test    edi, edi
0x180003643  jnz     short loc_180003658
0x180003645  mov     rsi, [rsp+88h+arg_10]
0x18000364d  lea     eax, [rdi+5Ch]
0x180003650  test    rbx, rbx
0x180003653  jnz     short loc_1800035DB
0x180003655  mov     [r14], rsi
0x180003658  mov     rcx, cs:hHeap; hHeap
0x18000365f  mov     r8, rbp; lpMem
0x180003662  xor     edx, edx; dwFlags
0x180003664  call    cs:__imp_HeapFree
0x18000366a  mov     eax, edi
0x18000366c  add     rsp, 48h
0x180003670  pop     r15
0x180003672  pop     r14
0x180003674  pop     r13
0x180003676  pop     r12
0x180003678  pop     rdi
0x180003679  pop     rsi
0x18000367a  pop     rbp
0x18000367b  pop     rbx
0x18000367c  retn
0x18000367d  test    rbx, rbx
0x180003680  jz      short loc_18000360E
0x180003682  lea     rax, [rsp+88h+arg_10]
0x18000368a  mov     r9d, r15d
0x18000368d  mov     [rsp+88h+var_58], rax
0x180003692  and     r9d, 0FFFFFFFCh
0x180003696  mov     [rsp+88h+var_68], 4
0x18000369e  jmp     short loc_180003623
```
