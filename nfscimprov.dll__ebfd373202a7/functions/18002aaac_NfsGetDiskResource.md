# NfsGetDiskResource

- ea: `0x18002aaac`
- end: `0x18002ac9f`
- name: `NfsGetDiskResource`
- size: `499`
- prototype: `__int64 __fastcall(HCLUSTER hCluster)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ef68`
- `0x180029d60`
- `0x18002a098`
- `0x18002a1d8`

## callees

- `0x18002aaac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002aafc`
- `KERNEL32!GetLastError` at `0x18002ac6e`
- `KERNEL32!GetLastError` at `0x18002aafc`
- `KERNEL32!GetLastError` at `0x18002ac6e`
- `KERNEL32!LocalFree` at `0x18002ab52`
- `KERNEL32!LocalFree` at `0x18002ac85`
- `KERNEL32!LocalFree` at `0x18002ab52`
- `KERNEL32!LocalFree` at `0x18002ac85`
- `KERNEL32!LocalAlloc` at `0x18002ab0e`
- `KERNEL32!LocalAlloc` at `0x18002ab6a`
- `KERNEL32!LocalAlloc` at `0x18002ab0e`
- `KERNEL32!LocalAlloc` at `0x18002ab6a`
- `CLUSAPI!ClusterResourceControl` at `0x18002abe4`
- `CLUSAPI!ClusterResourceControl` at `0x18002ac34`
- `CLUSAPI!ClusterResourceControl` at `0x18002abe4`
- `CLUSAPI!ClusterResourceControl` at `0x18002ac34`
- `CLUSAPI!OpenClusterResource` at `0x18002aba5`
- `CLUSAPI!OpenClusterResource` at `0x18002aba5`
- `CLUSAPI!ClusterOpenEnum` at `0x18002aaee`
- `CLUSAPI!ClusterOpenEnum` at `0x18002aaee`
- `CLUSAPI!ClusterEnum` at `0x18002ab42`
- `CLUSAPI!ClusterEnum` at `0x18002ab91`
- `CLUSAPI!ClusterEnum` at `0x18002ab42`
- `CLUSAPI!ClusterEnum` at `0x18002ab91`
- `CLUSAPI!ClusterCloseEnum` at `0x18002ac77`
- `CLUSAPI!ClusterCloseEnum` at `0x18002ac77`
- `CLUSAPI!CloseClusterResource` at `0x18002ac46`
- `CLUSAPI!CloseClusterResource` at `0x18002ac46`

## pseudocode

```c
__int64 __fastcall NfsGetDiskResource(HCLUSTER hCluster, _WORD *a2, struct _HRESOURCE **a3)
{
  struct _HCLUSTER *v3; // rdi
  unsigned int v4; // r12d
  struct _HCLUSENUM *v5; // r15
  WCHAR *v6; // rbx
  DWORD v7; // r13d
  DWORD i; // esi
  DWORD v9; // eax
  SIZE_T v10; // rdx
  struct _HRESOURCE *v11; // rdi
  DWORD v12; // r14d
  __int64 v13; // rax
  DWORD v14; // eax
  DWORD dwType; // [rsp+40h] [rbp-18h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-14h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+60h] BYREF

  v3 = hCluster;
  dwType = 0;
  v4 = 0;
  BytesReturned = 0;
  cchName = 0;
  OutBuffer = 0;
  *a3 = 0;
  v5 = ClusterOpenEnum(hCluster, 4u);
  if ( v5 )
  {
    v6 = (WCHAR *)LocalAlloc(0, 0x208u);
    if ( v6 )
    {
      v7 = 260;
      for ( i = 0; ; ++i )
      {
        cchName = v7;
        v9 = ClusterEnum(v5, i, &dwType, v6, &cchName);
        if ( v9 == 234 )
        {
          LocalFree(v6);
          v10 = 2LL * ++cchName;
          v7 = cchName;
          v6 = (WCHAR *)LocalAlloc(0, v10);
          if ( !v6 )
            goto LABEL_19;
          v9 = ClusterEnum(v5, i, &dwType, v6, &cchName);
        }
        if ( v9 )
          break;
        v11 = OpenClusterResource(v3, v6);
        if ( !v11 )
          goto LABEL_19;
        v12 = ClusterResourceControl(v11, 0, 0x100000Du, 0, 0, &OutBuffer, 8u, &BytesReturned);
        if ( !v12 && (_DWORD)OutBuffer == 1 )
        {
          v13 = -1;
          v12 = 0;
          do
            ++v13;
          while ( a2[v13] );
          v14 = ClusterResourceControl(v11, 0, 0x1000199u, a2, 2 * v13 + 2, 0, 0, 0);
          if ( !v14 || v14 == 3 )
          {
            v4 = 1;
            *a3 = v11;
            break;
          }
        }
        CloseClusterResource(v11);
        if ( v12 )
          break;
        v3 = hCluster;
      }
    }
    else
    {
LABEL_19:
      GetLastError();
    }
    ClusterCloseEnum(v5);
    if ( v6 )
      LocalFree(v6);
  }
  else
  {
    GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x18002aaac  mov     [rsp-40h+arg_10], r8
0x18002aab1  mov     [rsp-40h+lpInBuffer], rdx
0x18002aab6  mov     [rsp-40h+arg_0], rcx
0x18002aabb  push    rbp
0x18002aabc  push    rbx
0x18002aabd  push    rsi
0x18002aabe  push    rdi
0x18002aabf  push    r12
0x18002aac1  push    r13
0x18002aac3  push    r14
0x18002aac5  push    r15
0x18002aac7  mov     rbp, rsp
0x18002aaca  sub     rsp, 58h
0x18002aace  xor     r14d, r14d
0x18002aad1  mov     rdi, rcx
0x18002aad4  mov     [rbp+dwType], r14d
0x18002aad8  mov     r12d, r14d
0x18002aadb  mov     [rbp+BytesReturned], r14d
0x18002aadf  mov     [rbp+cchName], r14d
0x18002aae3  lea     edx, [r14+4]; dwType
0x18002aae7  mov     [rbp+OutBuffer], r14
0x18002aaeb  mov     [r8], r14
0x18002aaee  call    cs:__imp_ClusterOpenEnum
0x18002aaf4  mov     r15, rax
0x18002aaf7  test    rax, rax
0x18002aafa  jnz     short loc_18002AB07
0x18002aafc  call    cs:__imp_GetLastError
0x18002ab02  jmp     loc_18002AC8B
0x18002ab07  mov     edx, 208h; uBytes
0x18002ab0c  xor     ecx, ecx; uFlags
0x18002ab0e  call    cs:__imp_LocalAlloc
0x18002ab14  mov     rbx, rax
0x18002ab17  test    rax, rax
0x18002ab1a  jz      loc_18002AC6E
0x18002ab20  mov     r13d, 104h
0x18002ab26  mov     esi, r14d
0x18002ab29  lea     rax, [rbp+cchName]
0x18002ab2d  mov     [rbp+cchName], r13d
0x18002ab31  mov     r9, rbx; lpszName
0x18002ab34  mov     [rsp+58h+lpcchName], rax; lpcchName
0x18002ab39  lea     r8, [rbp+dwType]; lpdwType
0x18002ab3d  mov     edx, esi; dwIndex
0x18002ab3f  mov     rcx, r15; hEnum
0x18002ab42  call    cs:__imp_ClusterEnum
0x18002ab48  cmp     eax, 0EAh
0x18002ab4d  jnz     short loc_18002AB97
0x18002ab4f  mov     rcx, rbx; hMem
0x18002ab52  call    cs:__imp_LocalFree
0x18002ab58  mov     eax, [rbp+cchName]
0x18002ab5b  xor     ecx, ecx; uFlags
0x18002ab5d  inc     eax
0x18002ab5f  mov     edx, eax
0x18002ab61  add     rdx, rdx; uBytes
0x18002ab64  mov     [rbp+cchName], eax
0x18002ab67  mov     r13d, eax
0x18002ab6a  call    cs:__imp_LocalAlloc
0x18002ab70  mov     rbx, rax
0x18002ab73  test    rax, rax
0x18002ab76  jz      loc_18002AC6E
0x18002ab7c  lea     rax, [rbp+cchName]
0x18002ab80  mov     r9, rbx; lpszName
0x18002ab83  lea     r8, [rbp+dwType]; lpdwType
0x18002ab87  mov     [rsp+58h+lpcchName], rax; lpcchName
0x18002ab8c  mov     edx, esi; dwIndex
0x18002ab8e  mov     rcx, r15; hEnum
0x18002ab91  call    cs:__imp_ClusterEnum
0x18002ab97  test    eax, eax
0x18002ab99  jnz     loc_18002AC74
0x18002ab9f  mov     rdx, rbx; lpszResourceName
0x18002aba2  mov     rcx, rdi; hCluster
0x18002aba5  call    cs:__imp_OpenClusterResource
0x18002abab  mov     rdi, rax
0x18002abae  test    rax, rax
0x18002abb1  jz      loc_18002AC6E
0x18002abb7  lea     rax, [rbp+BytesReturned]
0x18002abbb  xor     r9d, r9d; lpInBuffer
0x18002abbe  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x18002abc3  xor     edx, edx; hHostNode
0x18002abc5  lea     rax, [rbp+OutBuffer]
0x18002abc9  mov     [rsp+58h+cbOutBufferSize], 8; cbOutBufferSize
0x18002abd1  mov     [rsp+58h+lpOutBuffer], rax; lpOutBuffer
0x18002abd6  mov     r8d, 100000Dh; dwControlCode
0x18002abdc  mov     rcx, rdi; hResource
0x18002abdf  mov     dword ptr [rsp+58h+lpcchName], r14d; cbInBufferSize
0x18002abe4  call    cs:__imp_ClusterResourceControl
0x18002abea  mov     r14d, eax
0x18002abed  test    eax, eax
0x18002abef  jnz     short loc_18002AC43
0x18002abf1  cmp     dword ptr [rbp+OutBuffer], 1
0x18002abf5  jnz     short loc_18002AC43
0x18002abf7  mov     rcx, [rbp+lpInBuffer]
0x18002abfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002abff  xor     r14d, r14d
0x18002ac02  inc     rax
0x18002ac05  cmp     [rcx+rax*2], r14w
0x18002ac0a  jnz     short loc_18002AC02
0x18002ac0c  mov     [rsp+58h+lpBytesReturned], r14; lpBytesReturned
0x18002ac11  lea     eax, ds:2[rax*2]
0x18002ac18  mov     [rsp+58h+cbOutBufferSize], r14d; cbOutBufferSize
0x18002ac1d  mov     r9, rcx; lpInBuffer
0x18002ac20  mov     [rsp+58h+lpOutBuffer], r14; lpOutBuffer
0x18002ac25  xor     edx, edx; hHostNode
0x18002ac27  mov     r8d, 1000199h; dwControlCode
0x18002ac2d  mov     dword ptr [rsp+58h+lpcchName], eax; cbInBufferSize
0x18002ac31  mov     rcx, rdi; hResource
0x18002ac34  call    cs:__imp_ClusterResourceControl
0x18002ac3a  test    eax, eax
0x18002ac3c  jz      short loc_18002AC5F
0x18002ac3e  cmp     eax, 3
0x18002ac41  jz      short loc_18002AC5F
0x18002ac43  mov     rcx, rdi; hResource
0x18002ac46  call    cs:__imp_CloseClusterResource
0x18002ac4c  test    r14d, r14d
0x18002ac4f  jnz     short loc_18002AC74
0x18002ac51  mov     rdi, [rbp+arg_0]
0x18002ac55  inc     esi
0x18002ac57  xor     r14d, r14d
0x18002ac5a  jmp     loc_18002AB29
0x18002ac5f  mov     rax, [rbp+arg_10]
0x18002ac63  mov     r12d, 1
0x18002ac69  mov     [rax], rdi
0x18002ac6c  jmp     short loc_18002AC74
0x18002ac6e  call    cs:__imp_GetLastError
0x18002ac74  mov     rcx, r15; hEnum
0x18002ac77  call    cs:__imp_ClusterCloseEnum
0x18002ac7d  test    rbx, rbx
0x18002ac80  jz      short loc_18002AC8B
0x18002ac82  mov     rcx, rbx; hMem
0x18002ac85  call    cs:__imp_LocalFree
0x18002ac8b  mov     eax, r12d
0x18002ac8e  add     rsp, 58h
0x18002ac92  pop     r15
0x18002ac94  pop     r14
0x18002ac96  pop     r13
0x18002ac98  pop     r12
0x18002ac9a  pop     rdi
0x18002ac9b  pop     rsi
0x18002ac9c  pop     rbx
0x18002ac9d  pop     rbp
0x18002ac9e  retn
```
