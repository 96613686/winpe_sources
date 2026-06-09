# OpenPFsSubkeyFromComponent

- ea: `0x18002ca24`
- end: `0x18002cafb`
- name: `OpenPFsSubkeyFromComponent`
- size: `215`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cf98`
- `0x18002d088`

## callees

- `0x180001da6`
- `0x18002ca24`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002cae0`
- `KERNEL32!HeapFree` at `0x18002cae0`
- `KERNEL32!HeapAlloc` at `0x18002ca5f`
- `KERNEL32!HeapAlloc` at `0x18002ca5f`
- `KERNEL32!GetProcessHeap` at `0x18002ca4b`
- `KERNEL32!GetProcessHeap` at `0x18002cad2`
- `KERNEL32!GetProcessHeap` at `0x18002ca4b`
- `KERNEL32!GetProcessHeap` at `0x18002cad2`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cab9`
- `ADVAPI32!RegOpenKeyExW` at `0x18002cab9`
- `CLUSAPI!ClusterRegOpenKey` at `0x18002ca9e`
- `CLUSAPI!ClusterRegOpenKey` at `0x18002ca9e`

## pseudocode

```c
__int64 __fastcall OpenPFsSubkeyFromComponent(HKEY hKey, const void **a2, char a3, __int64 a4, HKEY *a5)
{
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v10; // r8
  unsigned int v11; // ebx
  WCHAR *v12; // rax
  WCHAR *v13; // rdi
  size_t v14; // rbx
  LONG v15; // eax
  HANDLE v16; // rax
  HKEY phkResult; // [rsp+58h] [rbp+10h] BYREF

  v5 = *(unsigned __int16 *)a2;
  phkResult = 0;
  ProcessHeap = GetProcessHeap();
  v10 = v5 + 2;
  v11 = 8;
  v12 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v10);
  v13 = v12;
  if ( v12 )
  {
    v14 = *(unsigned __int16 *)a2;
    memcpy_0(v12, a2[1], v14);
    v13[v14 >> 1] = 0;
    if ( a3 )
      v15 = ClusterRegOpenKey(hKey, v13, 0xF003Fu, &phkResult);
    else
      v15 = RegOpenKeyExW(hKey, v13, 0, 0xF003Fu, &phkResult);
    v11 = v15;
    if ( !v15 )
      *a5 = phkResult;
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v13);
  }
  return v11;
}

```

## disassembly

```asm
0x18002ca24  mov     [rsp+arg_0], rbx
0x18002ca29  mov     [rsp+arg_10], rbp
0x18002ca2e  push    rsi
0x18002ca2f  push    rdi
0x18002ca30  push    r14
0x18002ca32  sub     rsp, 30h
0x18002ca36  movzx   ebx, word ptr [rdx]
0x18002ca39  mov     r14b, r8b
0x18002ca3c  mov     rsi, rdx
0x18002ca3f  mov     [rsp+48h+phkResult], 0
0x18002ca48  mov     rbp, rcx
0x18002ca4b  call    cs:__imp_GetProcessHeap
0x18002ca51  lea     r8, [rbx+2]; dwBytes
0x18002ca55  mov     ebx, 8
0x18002ca5a  mov     edx, ebx; dwFlags
0x18002ca5c  mov     rcx, rax; hHeap
0x18002ca5f  call    cs:__imp_HeapAlloc
0x18002ca65  mov     rdi, rax
0x18002ca68  test    rax, rax
0x18002ca6b  jz      short loc_18002CAE6
0x18002ca6d  movzx   ebx, word ptr [rsi]
0x18002ca70  mov     rcx, rax; void *
0x18002ca73  mov     rdx, [rsi+8]; Src
0x18002ca77  mov     r8d, ebx; Size
0x18002ca7a  call    memcpy_0
0x18002ca7f  shr     rbx, 1
0x18002ca82  xor     eax, eax
0x18002ca84  mov     rdx, rdi; lpSubKey
0x18002ca87  mov     rcx, rbp; hKey
0x18002ca8a  mov     [rdi+rbx*2], ax
0x18002ca8e  test    r14b, r14b
0x18002ca91  jz      short loc_18002CAA6
0x18002ca93  lea     r9, [rsp+48h+phkResult]; phkResult
0x18002ca98  mov     r8d, 0F003Fh; samDesired
0x18002ca9e  call    cs:__imp_ClusterRegOpenKey
0x18002caa4  jmp     short loc_18002CABF
0x18002caa6  lea     rax, [rsp+48h+phkResult]
0x18002caab  mov     r9d, 0F003Fh; samDesired
0x18002cab1  xor     r8d, r8d; ulOptions
0x18002cab4  mov     [rsp+48h+var_28], rax; phkResult
0x18002cab9  call    cs:__imp_RegOpenKeyExW
0x18002cabf  mov     ebx, eax
0x18002cac1  test    eax, eax
0x18002cac3  jnz     short loc_18002CAD2
0x18002cac5  mov     rcx, [rsp+48h+arg_20]
0x18002caca  mov     rax, [rsp+48h+phkResult]
0x18002cacf  mov     [rcx], rax
0x18002cad2  call    cs:__imp_GetProcessHeap
0x18002cad8  mov     r8, rdi; lpMem
0x18002cadb  xor     edx, edx; dwFlags
0x18002cadd  mov     rcx, rax; hHeap
0x18002cae0  call    cs:__imp_HeapFree
0x18002cae6  mov     rbp, [rsp+48h+arg_10]
0x18002caeb  mov     eax, ebx
0x18002caed  mov     rbx, [rsp+48h+arg_0]
0x18002caf2  add     rsp, 30h
0x18002caf6  pop     r14
0x18002caf8  pop     rdi
0x18002caf9  pop     rsi
0x18002cafa  retn
```
