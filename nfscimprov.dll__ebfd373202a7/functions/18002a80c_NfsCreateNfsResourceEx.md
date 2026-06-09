# NfsCreateNfsResourceEx

- ea: `0x18002a80c`
- end: `0x18002a97b`
- name: `NfsCreateNfsResourceEx`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f2d8`
- `0x18001f674`

## callees

- `0x180029b78`
- `0x18002a80c`
- `0x180035b02`
- `0x180035b0e`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002a8c2`
- `msvcrt!wcscpy_s` at `0x18002a8c2`
- `msvcrt!wcscat_s` at `0x18002a8d3`
- `msvcrt!wcscat_s` at `0x18002a8d3`
- `msvcrt!wcsnlen` at `0x18002a868`
- `msvcrt!wcsnlen` at `0x18002a885`
- `msvcrt!wcsnlen` at `0x18002a868`
- `msvcrt!wcsnlen` at `0x18002a885`
- `KERNEL32!GetLastError` at `0x18002a928`
- `KERNEL32!GetLastError` at `0x18002a95d`
- `KERNEL32!GetLastError` at `0x18002a928`
- `KERNEL32!GetLastError` at `0x18002a95d`
- `KERNEL32!LocalFree` at `0x18002a953`
- `KERNEL32!LocalFree` at `0x18002a953`
- `KERNEL32!LocalAlloc` at `0x18002a89a`
- `KERNEL32!LocalAlloc` at `0x18002a89a`
- `CLUSAPI!OnlineClusterResource` at `0x18002a90a`
- `CLUSAPI!OnlineClusterResource` at `0x18002a90a`
- `CLUSAPI!DeleteClusterResource` at `0x18002a93c`
- `CLUSAPI!DeleteClusterResource` at `0x18002a93c`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a8fb`
- `CLUSAPI!AddClusterResourceDependency` at `0x18002a8fb`
- `CLUSAPI!CreateClusterResource` at `0x18002a8e7`
- `CLUSAPI!CreateClusterResource` at `0x18002a8e7`
- `CLUSAPI!CloseClusterResource` at `0x18002a945`
- `CLUSAPI!CloseClusterResource` at `0x18002a945`

## pseudocode

```c
DWORD __fastcall NfsCreateNfsResourceEx(
        struct _HGROUP *a1,
        struct _HRESOURCE *a2,
        struct _HRESOURCE **a3,
        const wchar_t *a4,
        wchar_t *Source)
{
  const wchar_t *v8; // r15
  size_t v9; // rbx
  size_t v10; // rax
  rsize_t v11; // rbx
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  struct _HRESOURCE *ClusterResource; // rax
  struct _HRESOURCE *v15; // rdi
  DWORD v16; // ebx
  DWORD LastError; // eax

  *a3 = 0;
  v8 = L"NFS-";
  if ( !wcsncmp_0(a4, L"NFS Multi Server Namespace", 0x104u) )
    v8 = L"MsnsNFS-";
  v9 = wcsnlen(v8, 0x104u);
  if ( Source )
    v10 = wcsnlen(Source, 0x104u);
  else
    v10 = 0;
  v11 = v10 + v9 + 1;
  v12 = (wchar_t *)LocalAlloc(0, 2 * v11);
  v13 = v12;
  if ( !v12 )
    return GetLastError();
  memset_0(v12, 0, 2 * v11);
  wcscpy_s(v13, v11, v8);
  wcscat_s(v13, v11, Source);
  ClusterResource = CreateClusterResource(a1, v13, a4, 0);
  v15 = ClusterResource;
  if ( !ClusterResource )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  v16 = AddClusterResourceDependency(ClusterResource, a2);
  if ( !v16 )
  {
    v16 = OnlineClusterResource(v15);
    if ( v16 == 997 )
    {
      LastError = WaitForTargetState(v15, 2);
LABEL_12:
      v16 = LastError;
    }
  }
  if ( v16 )
  {
    if ( v15 )
    {
      DeleteClusterResource(v15);
      CloseClusterResource(v15);
    }
  }
  else
  {
    *a3 = v15;
  }
  LocalFree(v13);
  return v16;
}

```

## disassembly

```asm
0x18002a80c  mov     [rsp+arg_8], rbx
0x18002a811  mov     [rsp+arg_10], rsi
0x18002a816  mov     [rsp+hGroup], rcx
0x18002a81b  push    rdi
0x18002a81c  push    r12
0x18002a81e  push    r13
0x18002a820  push    r14
0x18002a822  push    r15
0x18002a824  sub     rsp, 20h
0x18002a828  mov     r14, r8
0x18002a82b  mov     qword ptr [r8], 0
0x18002a832  mov     r12, rdx
0x18002a835  mov     edi, 104h
0x18002a83a  mov     r8d, edi; MaxCount
0x18002a83d  lea     rdx, aNfsMultiServer; "NFS Multi Server Namespace"
0x18002a844  mov     rcx, r9; String1
0x18002a847  mov     r13, r9
0x18002a84a  call    wcsncmp_0
0x18002a84f  test    eax, eax
0x18002a851  lea     rcx, Source; "MsnsNFS-"
0x18002a858  lea     r15, aNfs; "NFS-"
0x18002a85f  mov     edx, edi; MaxCount
0x18002a861  cmovz   r15, rcx
0x18002a865  mov     rcx, r15; Source
0x18002a868  call    cs:__imp_wcsnlen
0x18002a86e  cmp     [rsp+48h+Source], 0
0x18002a874  mov     rbx, rax
0x18002a877  jnz     short loc_18002A87D
0x18002a879  xor     eax, eax
0x18002a87b  jmp     short loc_18002A88B
0x18002a87d  mov     rcx, [rsp+48h+Source]; Source
0x18002a882  mov     rdx, rdi; MaxCount
0x18002a885  call    cs:__imp_wcsnlen
0x18002a88b  inc     rbx
0x18002a88e  xor     ecx, ecx; uFlags
0x18002a890  add     rbx, rax
0x18002a893  lea     rdi, [rbx+rbx]
0x18002a897  mov     rdx, rdi; uBytes
0x18002a89a  call    cs:__imp_LocalAlloc
0x18002a8a0  mov     rsi, rax
0x18002a8a3  test    rax, rax
0x18002a8a6  jz      loc_18002A95D
0x18002a8ac  mov     r8, rdi; Size
0x18002a8af  xor     edx, edx; Val
0x18002a8b1  mov     rcx, rax; void *
0x18002a8b4  call    memset_0
0x18002a8b9  mov     r8, r15; Source
0x18002a8bc  mov     rdx, rbx; SizeInWords
0x18002a8bf  mov     rcx, rsi; Destination
0x18002a8c2  call    cs:__imp_wcscpy_s
0x18002a8c8  mov     r8, [rsp+48h+Source]; Source
0x18002a8cd  mov     rdx, rbx; SizeInWords
0x18002a8d0  mov     rcx, rsi; Destination
0x18002a8d3  call    cs:__imp_wcscat_s
0x18002a8d9  mov     rcx, [rsp+48h+hGroup]; hGroup
0x18002a8de  xor     r9d, r9d; dwFlags
0x18002a8e1  mov     r8, r13; lpszResourceType
0x18002a8e4  mov     rdx, rsi; lpszResourceName
0x18002a8e7  call    cs:__imp_CreateClusterResource
0x18002a8ed  mov     rdi, rax
0x18002a8f0  test    rax, rax
0x18002a8f3  jz      short loc_18002A928
0x18002a8f5  mov     rdx, r12; hDependsOn
0x18002a8f8  mov     rcx, rax; hResource
0x18002a8fb  call    cs:__imp_AddClusterResourceDependency
0x18002a901  mov     ebx, eax
0x18002a903  test    eax, eax
0x18002a905  jnz     short loc_18002A930
0x18002a907  mov     rcx, rdi; hResource
0x18002a90a  call    cs:__imp_OnlineClusterResource
0x18002a910  mov     ebx, eax
0x18002a912  cmp     eax, 3E5h
0x18002a917  jnz     short loc_18002A930
0x18002a919  mov     edx, 2
0x18002a91e  mov     rcx, rdi
0x18002a921  call    WaitForTargetState
0x18002a926  jmp     short loc_18002A92E
0x18002a928  call    cs:__imp_GetLastError
0x18002a92e  mov     ebx, eax
0x18002a930  test    ebx, ebx
0x18002a932  jz      short loc_18002A94D
0x18002a934  test    rdi, rdi
0x18002a937  jz      short loc_18002A950
0x18002a939  mov     rcx, rdi; hResource
0x18002a93c  call    cs:__imp_DeleteClusterResource
0x18002a942  mov     rcx, rdi; hResource
0x18002a945  call    cs:__imp_CloseClusterResource
0x18002a94b  jmp     short loc_18002A950
0x18002a94d  mov     [r14], rdi
0x18002a950  mov     rcx, rsi; hMem
0x18002a953  call    cs:__imp_LocalFree
0x18002a959  mov     eax, ebx
0x18002a95b  jmp     short loc_18002A963
0x18002a95d  call    cs:__imp_GetLastError
0x18002a963  mov     rbx, [rsp+48h+arg_8]
0x18002a968  mov     rsi, [rsp+48h+arg_10]
0x18002a96d  add     rsp, 20h
0x18002a971  pop     r15
0x18002a973  pop     r14
0x18002a975  pop     r13
0x18002a977  pop     r12
0x18002a979  pop     rdi
0x18002a97a  retn
```
