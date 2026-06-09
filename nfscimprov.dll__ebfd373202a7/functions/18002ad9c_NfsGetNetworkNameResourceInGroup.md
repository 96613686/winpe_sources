# NfsGetNetworkNameResourceInGroup

- ea: `0x18002ad9c`
- end: `0x18002aec3`
- name: `NfsGetNetworkNameResourceInGroup`
- size: `295`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ef68`
- `0x18002a098`
- `0x18002a1d8`

## callees

- `0x180029574`
- `0x180029608`
- `0x18002993c`
- `0x180029b04`
- `0x18002ad9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002aea8`
- `KERNEL32!GetLastError` at `0x18002aea8`
- `KERNEL32!LocalFree` at `0x18002ae25`
- `KERNEL32!LocalFree` at `0x18002ae5e`
- `KERNEL32!LocalFree` at `0x18002ae7f`
- `KERNEL32!LocalFree` at `0x18002ae25`
- `KERNEL32!LocalFree` at `0x18002ae5e`
- `KERNEL32!LocalFree` at `0x18002ae7f`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002adcc`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002adcc`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x18002aea0`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x18002aea0`
- `CLUSAPI!CloseClusterResource` at `0x18002ae6f`
- `CLUSAPI!CloseClusterResource` at `0x18002ae6f`

## pseudocode

```c
__int64 __fastcall NfsGetNetworkNameResourceInGroup(
        __int64 a1,
        struct _HGROUP *a2,
        const wchar_t *a3,
        struct _HRESOURCE **a4)
{
  struct _HGROUPENUM *v7; // r14
  DWORD i; // esi
  unsigned int ResourceNameFromGroupEnum; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  struct _HRESOURCE *v12; // rdi
  int v13; // eax
  HLOCAL v14; // rcx
  HLOCAL v16; // [rsp+20h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-20h]
  HRESOURCE hResource[3]; // [rsp+30h] [rbp-18h] BYREF

  v16 = 0;
  v7 = ClusterGroupOpenEnum(a2, 1u);
  if ( v7 )
  {
    for ( i = 0; ; ++i )
    {
      hMem = 0;
      hResource[0] = 0;
      ResourceNameFromGroupEnum = GetResourceNameFromGroupEnum(v7, i);
      if ( ResourceNameFromGroupEnum )
        break;
      ResourceNameFromGroupEnum = DoesResTypeMatch(a1, hMem, L"Network Name", hResource);
      LocalFree(hMem);
      if ( ResourceNameFromGroupEnum )
        goto LABEL_13;
      v12 = hResource[0];
      if ( hResource[0] )
      {
        ResourceNameFromGroupEnum = GetResourcePrivateSzProperty(hResource[0], v10, v11, &v16);
        if ( ResourceNameFromGroupEnum )
          goto LABEL_13;
        v13 = CompareHostNames((WCHAR *)v16, a3);
        v14 = v16;
        if ( !v13 )
        {
          *a4 = v12;
          LocalFree(v14);
          v16 = 0;
          goto LABEL_13;
        }
        LocalFree(v16);
        v16 = 0;
        CloseClusterResource(v12);
      }
    }
    if ( ResourceNameFromGroupEnum == 259 )
      ResourceNameFromGroupEnum = 1168;
LABEL_13:
    ClusterGroupCloseEnum(v7);
  }
  else
  {
    return GetLastError();
  }
  return ResourceNameFromGroupEnum;
}

```

## disassembly

```asm
0x18002ad9c  push    rbp
0x18002ad9e  push    rbx
0x18002ad9f  push    rsi
0x18002ada0  push    rdi
0x18002ada1  push    r12
0x18002ada3  push    r13
0x18002ada5  push    r14
0x18002ada7  push    r15
0x18002ada9  mov     rbp, rsp
0x18002adac  sub     rsp, 48h
0x18002adb0  mov     rax, rdx
0x18002adb3  mov     [rbp+var_28], 0
0x18002adbb  mov     r13, rcx
0x18002adbe  mov     edx, 1; dwType
0x18002adc3  mov     rcx, rax; hGroup
0x18002adc6  mov     r15, r9
0x18002adc9  mov     r12, r8
0x18002adcc  call    cs:__imp_ClusterGroupOpenEnum
0x18002add2  mov     r14, rax
0x18002add5  test    rax, rax
0x18002add8  jz      loc_18002AEA8
0x18002adde  xor     esi, esi
0x18002ade0  lea     r8, [rbp+hMem]
0x18002ade4  mov     [rbp+hMem], 0
0x18002adec  mov     edx, esi; dwIndex
0x18002adee  mov     [rbp+hResource], 0
0x18002adf6  mov     rcx, r14; hGroupEnum
0x18002adf9  call    GetResourceNameFromGroupEnum
0x18002adfe  mov     ebx, eax
0x18002ae00  test    eax, eax
0x18002ae02  jnz     loc_18002AE8F
0x18002ae08  mov     rdx, [rbp+hMem]
0x18002ae0c  lea     r9, [rbp+hResource]
0x18002ae10  lea     r8, szResourceType; "Network Name"
0x18002ae17  mov     rcx, r13
0x18002ae1a  call    DoesResTypeMatch
0x18002ae1f  mov     rcx, [rbp+hMem]; hMem
0x18002ae23  mov     ebx, eax
0x18002ae25  call    cs:__imp_LocalFree
0x18002ae2b  test    ebx, ebx
0x18002ae2d  jnz     short loc_18002AE9D
0x18002ae2f  mov     rdi, [rbp+hResource]
0x18002ae33  test    rdi, rdi
0x18002ae36  jz      short loc_18002AE75
0x18002ae38  lea     r9, [rbp+var_28]
0x18002ae3c  mov     rcx, rdi
0x18002ae3f  call    GetResourcePrivateSzProperty
0x18002ae44  mov     ebx, eax
0x18002ae46  test    eax, eax
0x18002ae48  jnz     short loc_18002AE9D
0x18002ae4a  mov     rcx, [rbp+var_28]
0x18002ae4e  mov     rdx, r12
0x18002ae51  call    CompareHostNames
0x18002ae56  mov     rcx, [rbp+var_28]; hMem
0x18002ae5a  test    eax, eax
0x18002ae5c  jz      short loc_18002AE7C
0x18002ae5e  call    cs:__imp_LocalFree
0x18002ae64  mov     rcx, rdi; hResource
0x18002ae67  mov     [rbp+var_28], 0
0x18002ae6f  call    cs:__imp_CloseClusterResource
0x18002ae75  inc     esi
0x18002ae77  jmp     loc_18002ADE0
0x18002ae7c  mov     [r15], rdi
0x18002ae7f  call    cs:__imp_LocalFree
0x18002ae85  mov     [rbp+var_28], 0
0x18002ae8d  jmp     short loc_18002AE9D
0x18002ae8f  cmp     ebx, 103h
0x18002ae95  mov     eax, 490h
0x18002ae9a  cmovz   ebx, eax
0x18002ae9d  mov     rcx, r14; hGroupEnum
0x18002aea0  call    cs:__imp_ClusterGroupCloseEnum
0x18002aea6  jmp     short loc_18002AEB0
0x18002aea8  call    cs:__imp_GetLastError
0x18002aeae  mov     ebx, eax
0x18002aeb0  mov     eax, ebx
0x18002aeb2  add     rsp, 48h
0x18002aeb6  pop     r15
0x18002aeb8  pop     r14
0x18002aeba  pop     r13
0x18002aebc  pop     r12
0x18002aebe  pop     rdi
0x18002aebf  pop     rsi
0x18002aec0  pop     rbx
0x18002aec1  pop     rbp
0x18002aec2  retn
```
