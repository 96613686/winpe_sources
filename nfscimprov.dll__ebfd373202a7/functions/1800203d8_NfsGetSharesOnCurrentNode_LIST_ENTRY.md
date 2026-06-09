# NfsGetSharesOnCurrentNode(_LIST_ENTRY *)

- ea: `0x1800203d8`
- end: `0x1800204dc`
- name: `?NfsGetSharesOnCurrentNode@@YAKPEAU_LIST_ENTRY@@@Z`
- size: `260`
- prototype: `unsigned int __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e418`

## callees

- `0x1800203d8`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002042d`
- `KERNEL32!GetLastError` at `0x18002042d`
- `KERNEL32!GetComputerNameExW` at `0x180020423`
- `KERNEL32!GetComputerNameExW` at `0x180020423`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18002046d`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18002049d`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18002046d`
- `RESUTILS!ResUtilEnumResourcesEx` at `0x18002049d`
- `CLUSAPI!CloseCluster` at `0x1800204b3`
- `CLUSAPI!CloseCluster` at `0x1800204b3`
- `CLUSAPI!OpenCluster` at `0x180020442`
- `CLUSAPI!OpenCluster` at `0x180020442`

## pseudocode

```c
DWORD __fastcall NfsGetSharesOnCurrentNode(struct _LIST_ENTRY *a1)
{
  struct _HCLUSTER *v3; // rdi
  DWORD v4; // eax
  DWORD v5; // ebx
  DWORD nSize[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-228h] BYREF
  struct _LIST_ENTRY *v8; // [rsp+240h] [rbp-28h]

  memset_0(Buffer, 0, 0x208u);
  nSize[0] = 256;
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsHostname, Buffer, nSize) )
    return GetLastError();
  v8 = a1;
  v3 = OpenCluster(0);
  if ( !v3 )
    return GetLastError();
  v4 = ResUtilEnumResourcesEx(v3, 0, L"Network File System", NfsGetSharesOnCurrentNodeCallBack, Buffer);
  v5 = v4;
  if ( v4 == 5078 || !v4 )
  {
    v5 = ResUtilEnumResourcesEx(v3, 0, L"NFS Multi Server Namespace", NfsGetSharesOnCurrentNodeCallBack, Buffer);
    if ( v5 == 5078 )
      v5 = 0;
  }
  CloseCluster(v3);
  return v5;
}

```

## disassembly

```asm
0x1800203d8  mov     [rsp+arg_8], rbx
0x1800203dd  push    rdi
0x1800203de  sub     rsp, 260h
0x1800203e5  mov     rax, cs:__security_cookie
0x1800203ec  xor     rax, rsp
0x1800203ef  mov     [rsp+268h+var_18], rax
0x1800203f7  mov     rbx, rcx
0x1800203fa  xor     edx, edx; Val
0x1800203fc  lea     rcx, [rsp+268h+Buffer]; void *
0x180020401  mov     r8d, 208h; Size
0x180020407  call    memset_0
0x18002040c  lea     r8, [rsp+268h+nSize]; nSize
0x180020411  mov     [rsp+268h+nSize], 100h
0x180020419  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x18002041e  mov     ecx, 5; NameType
0x180020423  call    cs:__imp_GetComputerNameExW
0x180020429  test    eax, eax
0x18002042b  jnz     short loc_180020438
0x18002042d  call    cs:__imp_GetLastError
0x180020433  jmp     loc_1800204BB
0x180020438  xor     ecx, ecx; lpszClusterName
0x18002043a  mov     [rsp+268h+var_28], rbx
0x180020442  call    cs:__imp_OpenCluster
0x180020448  mov     rdi, rax
0x18002044b  test    rax, rax
0x18002044e  jz      short loc_18002042D
0x180020450  lea     rax, [rsp+268h+Buffer]
0x180020455  xor     edx, edx; hSelf
0x180020457  lea     r9, ?NfsGetSharesOnCurrentNodeCallBack@@YAKPEAU_HCLUSTER@@PEAU_HRESOURCE@@1PEAX@Z; pResCallBack
0x18002045e  mov     [rsp+268h+pParameter], rax; pParameter
0x180020463  lea     r8, szResourceTypeName; "Network File System"
0x18002046a  mov     rcx, rdi; hCluster
0x18002046d  call    cs:__imp_ResUtilEnumResourcesEx
0x180020473  mov     ebx, eax
0x180020475  cmp     eax, 13D6h
0x18002047a  jz      short loc_180020480
0x18002047c  test    eax, eax
0x18002047e  jnz     short loc_1800204B0
0x180020480  lea     rax, [rsp+268h+Buffer]
0x180020485  xor     edx, edx; hSelf
0x180020487  lea     r9, ?NfsGetSharesOnCurrentNodeCallBack@@YAKPEAU_HCLUSTER@@PEAU_HRESOURCE@@1PEAX@Z; pResCallBack
0x18002048e  mov     [rsp+268h+pParameter], rax; pParameter
0x180020493  lea     r8, aNfsMultiServer; "NFS Multi Server Namespace"
0x18002049a  mov     rcx, rdi; hCluster
0x18002049d  call    cs:__imp_ResUtilEnumResourcesEx
0x1800204a3  mov     ebx, eax
0x1800204a5  xor     eax, eax
0x1800204a7  cmp     ebx, 13D6h
0x1800204ad  cmovz   ebx, eax
0x1800204b0  mov     rcx, rdi; hCluster
0x1800204b3  call    cs:__imp_CloseCluster
0x1800204b9  mov     eax, ebx
0x1800204bb  mov     rcx, [rsp+268h+var_18]
0x1800204c3  xor     rcx, rsp; StackCookie
0x1800204c6  call    __security_check_cookie
0x1800204cb  mov     rbx, [rsp+268h+arg_8]
0x1800204d3  add     rsp, 260h
0x1800204da  pop     rdi
0x1800204db  retn
```
