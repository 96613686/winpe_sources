# IsPathClusteredEx

- ea: `0x180029d60`
- end: `0x180029df7`
- name: `IsPathClusteredEx`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d798`

## callees

- `0x180029c30`
- `0x180029d60`
- `0x18002aaac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029da8`
- `KERNEL32!GetLastError` at `0x180029da8`
- `CLUSAPI!CloseCluster` at `0x180029dda`
- `CLUSAPI!CloseCluster` at `0x180029dda`
- `CLUSAPI!OpenCluster` at `0x180029d9a`
- `CLUSAPI!OpenCluster` at `0x180029d9a`
- `CLUSAPI!CloseClusterResource` at `0x180029dd1`
- `CLUSAPI!CloseClusterResource` at `0x180029dd1`

## pseudocode

```c
DWORD __fastcall IsPathClusteredEx(_WORD *a1, _BYTE *a2)
{
  DWORD result; // eax
  struct _HCLUSTER *v5; // rax
  struct _HCLUSTER *v6; // rbx
  int v7; // [rsp+40h] [rbp+18h] BYREF
  HRESOURCE hResource; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  hResource = 0;
  result = NfsClusterIsClusterNode(a1, &v7);
  if ( !result )
  {
    if ( v7 )
    {
      v5 = OpenCluster(0);
      v6 = v5;
      if ( !v5 )
        return GetLastError();
      if ( (unsigned int)NfsGetDiskResource(v5, a1, &hResource) )
        *a2 = 1;
      if ( hResource )
        CloseClusterResource(hResource);
      CloseCluster(v6);
    }
    else
    {
      *a2 = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180029d60  mov     rax, rsp
0x180029d63  mov     [rax+8], rbx
0x180029d67  mov     [rax+10h], rsi
0x180029d6b  push    rdi
0x180029d6c  sub     rsp, 20h
0x180029d70  mov     rdi, rdx
0x180029d73  mov     dword ptr [rax+18h], 0
0x180029d7a  lea     rdx, [rax+18h]
0x180029d7e  mov     qword ptr [rax+20h], 0
0x180029d86  mov     rsi, rcx
0x180029d89  call    NfsClusterIsClusterNode
0x180029d8e  test    eax, eax
0x180029d90  jnz     short loc_180029DE7
0x180029d92  cmp     [rsp+28h+arg_10], eax
0x180029d96  jz      short loc_180029DE2
0x180029d98  xor     ecx, ecx; lpszClusterName
0x180029d9a  call    cs:__imp_OpenCluster
0x180029da0  mov     rbx, rax
0x180029da3  test    rax, rax
0x180029da6  jnz     short loc_180029DB0
0x180029da8  call    cs:__imp_GetLastError
0x180029dae  jmp     short loc_180029DE7
0x180029db0  lea     r8, [rsp+28h+hResource]
0x180029db5  mov     rdx, rsi
0x180029db8  mov     rcx, rbx; hCluster
0x180029dbb  call    NfsGetDiskResource
0x180029dc0  test    eax, eax
0x180029dc2  jz      short loc_180029DC7
0x180029dc4  mov     byte ptr [rdi], 1
0x180029dc7  mov     rcx, [rsp+28h+hResource]; hResource
0x180029dcc  test    rcx, rcx
0x180029dcf  jz      short loc_180029DD7
0x180029dd1  call    cs:__imp_CloseClusterResource
0x180029dd7  mov     rcx, rbx; hCluster
0x180029dda  call    cs:__imp_CloseCluster
0x180029de0  jmp     short loc_180029DE5
0x180029de2  mov     byte ptr [rdi], 0
0x180029de5  xor     eax, eax
0x180029de7  mov     rbx, [rsp+28h+arg_0]
0x180029dec  mov     rsi, [rsp+28h+arg_8]
0x180029df1  add     rsp, 20h
0x180029df5  pop     rdi
0x180029df6  retn
```
