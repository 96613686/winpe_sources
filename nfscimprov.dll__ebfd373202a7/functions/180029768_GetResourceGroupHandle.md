# GetResourceGroupHandle

- ea: `0x180029768`
- end: `0x1800297be`
- name: `GetResourceGroupHandle`
- size: `86`
- prototype: `__int64 __fastcall(HCLUSTER hCluster, HRESOURCE hResource)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ef68`
- `0x18001f2d8`
- `0x18001f674`
- `0x18002a098`
- `0x18002a1d8`
- `0x18002a6f8`

## callees

- `0x180029768`
- `0x1800297c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800297aa`
- `KERNEL32!LocalFree` at `0x1800297aa`
- `CLUSAPI!OpenClusterGroup` at `0x18002979c`
- `CLUSAPI!OpenClusterGroup` at `0x18002979c`

## pseudocode

```c
HGROUP __fastcall GetResourceGroupHandle(HCLUSTER hCluster, HRESOURCE hResource)
{
  HGROUP v3; // rbx

  v3 = 0;
  if ( !(unsigned int)GetResourceGroupName(hResource) )
    v3 = OpenClusterGroup(hCluster, 0);
  LocalFree(0);
  return v3;
}

```

## disassembly

```asm
0x180029768  mov     [rsp+arg_0], rbx
0x18002976d  push    rdi
0x18002976e  sub     rsp, 20h
0x180029772  mov     rax, rdx
0x180029775  mov     [rsp+28h+lpszGroupName], 0
0x18002977e  mov     rdi, rcx
0x180029781  lea     rdx, [rsp+28h+lpszGroupName]
0x180029786  mov     rcx, rax; hResource
0x180029789  xor     ebx, ebx
0x18002978b  call    GetResourceGroupName
0x180029790  test    eax, eax
0x180029792  jnz     short loc_1800297A5
0x180029794  mov     rdx, [rsp+28h+lpszGroupName]; lpszGroupName
0x180029799  mov     rcx, rdi; hCluster
0x18002979c  call    cs:__imp_OpenClusterGroup
0x1800297a2  mov     rbx, rax
0x1800297a5  mov     rcx, [rsp+28h+lpszGroupName]; hMem
0x1800297aa  call    cs:__imp_LocalFree
0x1800297b0  mov     rax, rbx
0x1800297b3  mov     rbx, [rsp+28h+arg_0]
0x1800297b8  add     rsp, 20h
0x1800297bc  pop     rdi
0x1800297bd  retn
```
