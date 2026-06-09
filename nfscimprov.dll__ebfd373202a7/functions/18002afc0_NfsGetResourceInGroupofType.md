# NfsGetResourceInGroupofType

- ea: `0x18002afc0`
- end: `0x18002b083`
- name: `NfsGetResourceInGroupofType`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ef68`

## callees

- `0x180029608`
- `0x18002993c`
- `0x18002afc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b06c`
- `KERNEL32!GetLastError` at `0x18002b06c`
- `KERNEL32!LocalFree` at `0x18002b034`
- `KERNEL32!LocalFree` at `0x18002b034`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002afe1`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x18002afe1`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x18002b064`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x18002b064`

## pseudocode

```c
__int64 __fastcall NfsGetResourceInGroupofType(__int64 a1, struct _HGROUP *a2, __int64 a3, _QWORD *a4)
{
  struct _HGROUPENUM *v7; // rsi
  DWORD i; // edi
  unsigned int ResourceNameFromGroupEnum; // ebx
  _QWORD v11[8]; // [rsp+28h] [rbp-40h] BYREF

  v7 = ClusterGroupOpenEnum(a2, 1u);
  if ( v7 )
  {
    for ( i = 0; ; ++i )
    {
      v11[0] = 0;
      ResourceNameFromGroupEnum = GetResourceNameFromGroupEnum(v7, i);
      if ( ResourceNameFromGroupEnum )
        break;
      ResourceNameFromGroupEnum = DoesResTypeMatch(a1, 0, a3, v11);
      LocalFree(0);
      if ( ResourceNameFromGroupEnum )
        goto LABEL_10;
      if ( v11[0] )
      {
        *a4 = v11[0];
        ResourceNameFromGroupEnum = 0;
        goto LABEL_10;
      }
    }
    if ( ResourceNameFromGroupEnum == 259 )
      ResourceNameFromGroupEnum = 1168;
LABEL_10:
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
0x18002afc0  push    rbx
0x18002afc2  push    rbp
0x18002afc3  push    rsi
0x18002afc4  push    rdi
0x18002afc5  push    r14
0x18002afc7  push    r15
0x18002afc9  sub     rsp, 38h
0x18002afcd  mov     rax, rdx
0x18002afd0  mov     r15, rcx
0x18002afd3  mov     rcx, rax; hGroup
0x18002afd6  mov     edx, 1; dwType
0x18002afdb  mov     r14, r9
0x18002afde  mov     rbp, r8
0x18002afe1  call    cs:__imp_ClusterGroupOpenEnum
0x18002afe7  mov     rsi, rax
0x18002afea  test    rax, rax
0x18002afed  jz      short loc_18002B06C
0x18002afef  xor     edi, edi
0x18002aff1  lea     r8, [rsp+68h+hMem]
0x18002aff6  mov     [rsp+68h+hMem], 0
0x18002afff  mov     edx, edi; dwIndex
0x18002b001  mov     [rsp+68h+var_40], 0
0x18002b00a  mov     rcx, rsi; hGroupEnum
0x18002b00d  call    GetResourceNameFromGroupEnum
0x18002b012  mov     ebx, eax
0x18002b014  test    eax, eax
0x18002b016  jnz     short loc_18002B053
0x18002b018  mov     rdx, [rsp+68h+hMem]
0x18002b01d  lea     r9, [rsp+68h+var_40]
0x18002b022  mov     r8, rbp
0x18002b025  mov     rcx, r15
0x18002b028  call    DoesResTypeMatch
0x18002b02d  mov     rcx, [rsp+68h+hMem]; hMem
0x18002b032  mov     ebx, eax
0x18002b034  call    cs:__imp_LocalFree
0x18002b03a  test    ebx, ebx
0x18002b03c  jnz     short loc_18002B061
0x18002b03e  mov     rax, [rsp+68h+var_40]
0x18002b043  test    rax, rax
0x18002b046  jnz     short loc_18002B04C
0x18002b048  inc     edi
0x18002b04a  jmp     short loc_18002AFF1
0x18002b04c  mov     [r14], rax
0x18002b04f  xor     ebx, ebx
0x18002b051  jmp     short loc_18002B061
0x18002b053  cmp     ebx, 103h
0x18002b059  mov     eax, 490h
0x18002b05e  cmovz   ebx, eax
0x18002b061  mov     rcx, rsi; hGroupEnum
0x18002b064  call    cs:__imp_ClusterGroupCloseEnum
0x18002b06a  jmp     short loc_18002B074
0x18002b06c  call    cs:__imp_GetLastError
0x18002b072  mov     ebx, eax
0x18002b074  mov     eax, ebx
0x18002b076  add     rsp, 38h
0x18002b07a  pop     r15
0x18002b07c  pop     r14
0x18002b07e  pop     rdi
0x18002b07f  pop     rsi
0x18002b080  pop     rbp
0x18002b081  pop     rbx
0x18002b082  retn
```
