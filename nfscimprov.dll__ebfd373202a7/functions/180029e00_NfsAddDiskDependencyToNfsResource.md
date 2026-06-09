# NfsAddDiskDependencyToNfsResource

- ea: `0x180029e00`
- end: `0x180029fee`
- name: `NfsAddDiskDependencyToNfsResource`
- size: `494`
- prototype: `__int64 __fastcall(HRESOURCE hResource, HRESOURCE)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ef68`

## callees

- `0x180001cde`
- `0x180029894`
- `0x180029c74`
- `0x180029e00`
- `0x18002aecc`
- `0x18002b08c`
- `0x18002b19c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029e83`
- `KERNEL32!GetLastError` at `0x180029f9e`
- `KERNEL32!GetLastError` at `0x180029e83`
- `KERNEL32!GetLastError` at `0x180029f9e`
- `KERNEL32!LocalFree` at `0x180029ebd`
- `KERNEL32!LocalFree` at `0x180029ecf`
- `KERNEL32!LocalFree` at `0x180029efc`
- `KERNEL32!LocalFree` at `0x180029fbb`
- `KERNEL32!LocalFree` at `0x180029fc4`
- `KERNEL32!LocalFree` at `0x180029fcd`
- `KERNEL32!LocalFree` at `0x180029ebd`
- `KERNEL32!LocalFree` at `0x180029ecf`
- `KERNEL32!LocalFree` at `0x180029efc`
- `KERNEL32!LocalFree` at `0x180029fbb`
- `KERNEL32!LocalFree` at `0x180029fc4`
- `KERNEL32!LocalFree` at `0x180029fcd`
- `KERNEL32!LocalAlloc` at `0x180029f4e`
- `KERNEL32!LocalAlloc` at `0x180029f4e`
- `CLUSAPI!SetClusterResourceDependencyExpression` at `0x180029fb0`
- `CLUSAPI!SetClusterResourceDependencyExpression` at `0x180029fb0`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x180029e72`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x180029e72`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x180029ef2`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x180029ef2`

## pseudocode

```c
__int64 __fastcall NfsAddDiskDependencyToNfsResource(HRESOURCE hResource, HRESOURCE a2, char a3)
{
  DWORD ResourceName; // ebx
  struct _HRESENUM *v6; // rsi
  bool v7; // di
  DWORD i; // ebx
  DWORD ResourceNameFromResEnum; // r14d
  HLOCAL v10; // rdi

  if ( !a3 )
    goto LABEL_26;
  ResourceName = GetResourceName(a2);
  if ( !ResourceName )
  {
    v6 = ClusterResourceOpenEnum(hResource, 1u);
    if ( v6 || (v7 = 0, (ResourceName = GetLastError()) == 0) )
    {
      for ( i = 0; ; ++i )
      {
        ResourceNameFromResEnum = GetResourceNameFromResEnum(v6, i);
        if ( ResourceNameFromResEnum )
          break;
        if ( !wcsicmp_0(0, 0) )
        {
          LocalFree(0);
          break;
        }
        LocalFree(0);
      }
      v7 = ResourceNameFromResEnum == 259;
      ResourceName = 0;
      if ( ResourceNameFromResEnum != 259 )
        ResourceName = ResourceNameFromResEnum;
      if ( v6 )
        ClusterResourceCloseEnum(v6);
    }
    LocalFree(0);
    if ( !ResourceName && v7 )
    {
LABEL_26:
      ResourceName = NfsResourceControl(a2);
      if ( !ResourceName )
      {
        NfsGetResourceDependencyExpression(hResource);
        v10 = LocalAlloc(0, 0x14u);
        if ( v10 )
        {
          if ( StringCbPrintfExW((STRSAFE_LPWSTR)v10, 0x14u, 0, 0, 0, L"%s AND ([%s])", 0, 0) < 0 )
          {
            ResourceName = 13;
LABEL_22:
            LocalFree(0);
            LocalFree(0);
            LocalFree(v10);
            return ResourceName;
          }
        }
        else
        {
          ResourceName = GetLastError();
          if ( ResourceName )
            goto LABEL_22;
        }
        ResourceName = SetClusterResourceDependencyExpression(hResource, (LPCWSTR)v10);
        goto LABEL_22;
      }
    }
  }
  return ResourceName;
}

```

## disassembly

```asm
0x180029e00  mov     [rsp-28h+arg_0], rbx
0x180029e05  mov     [rsp-28h+arg_8], rsi
0x180029e0a  push    rbp
0x180029e0b  push    rdi
0x180029e0c  push    r12
0x180029e0e  push    r14
0x180029e10  push    r15
0x180029e12  mov     rbp, rsp
0x180029e15  sub     rsp, 60h
0x180029e19  mov     [rbp+hMem], 0
0x180029e21  mov     r15, rdx
0x180029e24  mov     [rbp+var_8], 0
0x180029e2c  mov     r12, rcx
0x180029e2f  mov     [rbp+arg_10], 0
0x180029e36  mov     [rbp+arg_18], 0
0x180029e3d  mov     [rbp+String2], 0
0x180029e45  mov     [rbp+String1], 0
0x180029e4d  test    r8b, r8b
0x180029e50  jz      loc_180029F13
0x180029e56  lea     rdx, [rbp+String2]
0x180029e5a  mov     rcx, r15; hResource
0x180029e5d  call    GetResourceName
0x180029e62  mov     ebx, eax
0x180029e64  test    eax, eax
0x180029e66  jnz     loc_180029FD3
0x180029e6c  lea     edx, [rax+1]; dwType
0x180029e6f  mov     rcx, r12; hResource
0x180029e72  call    cs:__imp_ClusterResourceOpenEnum
0x180029e78  mov     rsi, rax
0x180029e7b  test    rax, rax
0x180029e7e  jnz     short loc_180029E8F
0x180029e80  xor     dil, dil
0x180029e83  call    cs:__imp_GetLastError
0x180029e89  mov     ebx, eax
0x180029e8b  test    eax, eax
0x180029e8d  jnz     short loc_180029EF8
0x180029e8f  xor     ebx, ebx
0x180029e91  lea     r8, [rbp+String1]
0x180029e95  mov     edx, ebx; dwIndex
0x180029e97  mov     rcx, rsi; hResEnum
0x180029e9a  call    GetResourceNameFromResEnum
0x180029e9f  mov     r14d, eax
0x180029ea2  test    eax, eax
0x180029ea4  jnz     short loc_180029ED5
0x180029ea6  mov     rdi, [rbp+String1]
0x180029eaa  mov     rdx, [rbp+String2]; String2
0x180029eae  mov     rcx, rdi; String1
0x180029eb1  call    _wcsicmp_0
0x180029eb6  mov     rcx, rdi; hMem
0x180029eb9  test    eax, eax
0x180029ebb  jz      short loc_180029ECF
0x180029ebd  call    cs:__imp_LocalFree
0x180029ec3  inc     ebx
0x180029ec5  mov     [rbp+String1], 0
0x180029ecd  jmp     short loc_180029E91
0x180029ecf  call    cs:__imp_LocalFree
0x180029ed5  mov     eax, 103h
0x180029eda  cmp     r14d, eax
0x180029edd  setz    dil
0x180029ee1  xor     ebx, ebx
0x180029ee3  cmp     r14d, eax
0x180029ee6  cmovnz  ebx, r14d
0x180029eea  test    rsi, rsi
0x180029eed  jz      short loc_180029EF8
0x180029eef  mov     rcx, rsi; hResEnum
0x180029ef2  call    cs:__imp_ClusterResourceCloseEnum
0x180029ef8  mov     rcx, [rbp+String2]; hMem
0x180029efc  call    cs:__imp_LocalFree
0x180029f02  test    ebx, ebx
0x180029f04  jnz     loc_180029FD3
0x180029f0a  test    dil, dil
0x180029f0d  jz      loc_180029FD3
0x180029f13  lea     r9, [rbp+arg_18]
0x180029f17  mov     rcx, r15; hResource
0x180029f1a  lea     r8, [rbp+hMem]
0x180029f1e  call    NfsResourceControl
0x180029f23  mov     ebx, eax
0x180029f25  test    eax, eax
0x180029f27  jnz     loc_180029FD3
0x180029f2d  lea     r8, [rbp+arg_10]
0x180029f31  mov     rcx, r12; hResource
0x180029f34  lea     rdx, [rbp+var_8]
0x180029f38  call    NfsGetResourceDependencyExpression
0x180029f3d  mov     eax, [rbp+arg_18]
0x180029f40  mov     ecx, [rbp+arg_10]
0x180029f43  add     eax, 14h
0x180029f46  add     ecx, eax
0x180029f48  mov     ebx, ecx
0x180029f4a  mov     edx, ecx; uBytes
0x180029f4c  xor     ecx, ecx; uFlags
0x180029f4e  call    cs:__imp_LocalAlloc
0x180029f54  mov     rsi, [rbp+hMem]
0x180029f58  mov     rdi, rax
0x180029f5b  mov     r14, [rbp+var_8]
0x180029f5f  test    rax, rax
0x180029f62  jz      short loc_180029F9E
0x180029f64  mov     [rsp+60h+var_28], rsi
0x180029f69  lea     rax, aSAndS; "%s AND ([%s])"
0x180029f70  mov     [rsp+60h+var_30], r14
0x180029f75  xor     r9d, r9d; pcbRemaining
0x180029f78  mov     [rsp+60h+pszFormat], rax; pszFormat
0x180029f7d  xor     r8d, r8d; ppszDestEnd
0x180029f80  mov     edx, ebx; cbDest
0x180029f82  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x180029f8b  mov     rcx, rdi; pszDest
0x180029f8e  call    StringCbPrintfExW
0x180029f93  test    eax, eax
0x180029f95  jns     short loc_180029FAA
0x180029f97  mov     ebx, 0Dh
0x180029f9c  jmp     short loc_180029FB8
0x180029f9e  call    cs:__imp_GetLastError
0x180029fa4  mov     ebx, eax
0x180029fa6  test    eax, eax
0x180029fa8  jnz     short loc_180029FB8
0x180029faa  mov     rdx, rdi; lpszDependencyExpression
0x180029fad  mov     rcx, r12; hResource
0x180029fb0  call    cs:__imp_SetClusterResourceDependencyExpression
0x180029fb6  mov     ebx, eax
0x180029fb8  mov     rcx, rsi; hMem
0x180029fbb  call    cs:__imp_LocalFree
0x180029fc1  mov     rcx, r14; hMem
0x180029fc4  call    cs:__imp_LocalFree
0x180029fca  mov     rcx, rdi; hMem
0x180029fcd  call    cs:__imp_LocalFree
0x180029fd3  lea     r11, [rsp+60h+var_s0]
0x180029fd8  mov     eax, ebx
0x180029fda  mov     rbx, [r11+30h]
0x180029fde  mov     rsi, [r11+38h]
0x180029fe2  mov     rsp, r11
0x180029fe5  pop     r15
0x180029fe7  pop     r14
0x180029fe9  pop     r12
0x180029feb  pop     rdi
0x180029fec  pop     rbp
0x180029fed  retn
```
