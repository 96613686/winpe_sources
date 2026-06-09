# PathIsSubFolder(ushort const *,ushort const *)

- ea: `0x18000a8b0`
- end: `0x18000a94c`
- name: `?PathIsSubFolder@@YAHPEBG0@Z`
- size: `156`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f71c`

## callees

- `0x18000a8b0`
- `0x18000a954`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a91c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a91c`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000a8cc`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000a8ec`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000a8cc`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18000a8ec`

## pseudocode

```c
__int64 __fastcall PathIsSubFolder(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  PWSTR v5; // [rsp+40h] [rbp+18h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp+20h] BYREF

  v2 = 0;
  ppszPathOut = 0;
  if ( PathAllocCanonicalize(a1, 1u, &ppszPathOut) >= 0 )
  {
    v5 = 0;
    if ( PathAllocCanonicalize(a2, 1u, &v5) >= 0 )
      v2 = PathComparePaths((unsigned __int64)ppszPathOut, v5) & 8;
    if ( v5 )
      LocalFree(v5);
  }
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return v2;
}

```

## disassembly

```asm
0x18000a8b0  mov     [rsp+arg_0], rbx
0x18000a8b5  push    rdi
0x18000a8b6  sub     rsp, 20h
0x18000a8ba  xor     ebx, ebx
0x18000a8bc  lea     r8, [rsp+28h+ppszPathOut]; ppszPathOut
0x18000a8c1  mov     rdi, rdx
0x18000a8c4  mov     [rsp+28h+ppszPathOut], rbx
0x18000a8c9  lea     edx, [rbx+1]; dwFlags
0x18000a8cc  call    cs:__imp_PathAllocCanonicalize
0x18000a8d3  nop     dword ptr [rax+rax+00h]
0x18000a8d8  test    eax, eax
0x18000a8da  js      short loc_18000A912
0x18000a8dc  lea     r8, [rsp+28h+arg_10]; ppszPathOut
0x18000a8e1  mov     [rsp+28h+arg_10], rbx
0x18000a8e6  lea     edx, [rbx+1]; dwFlags
0x18000a8e9  mov     rcx, rdi; pszPathIn
0x18000a8ec  call    cs:__imp_PathAllocCanonicalize
0x18000a8f3  nop     dword ptr [rax+rax+00h]
0x18000a8f8  test    eax, eax
0x18000a8fa  jns     short loc_18000A936
0x18000a8fc  mov     rcx, [rsp+28h+arg_10]; hMem
0x18000a901  test    rcx, rcx
0x18000a904  jz      short loc_18000A912
0x18000a906  call    cs:__imp_LocalFree
0x18000a90d  nop     dword ptr [rax+rax+00h]
0x18000a912  mov     rcx, [rsp+28h+ppszPathOut]; hMem
0x18000a917  test    rcx, rcx
0x18000a91a  jz      short loc_18000A928
0x18000a91c  call    cs:__imp_LocalFree
0x18000a923  nop     dword ptr [rax+rax+00h]
0x18000a928  mov     eax, ebx
0x18000a92a  mov     rbx, [rsp+28h+arg_0]
0x18000a92f  add     rsp, 20h
0x18000a933  pop     rdi
0x18000a934  retn
0x18000a936  mov     rdx, [rsp+28h+arg_10]; lpString1
0x18000a93b  mov     rcx, [rsp+28h+ppszPathOut]; lpString2
0x18000a940  call    ?PathComparePaths@@YAKPEAG0@Z; PathComparePaths(ushort *,ushort *)
0x18000a945  mov     ebx, eax
0x18000a947  and     ebx, 8
0x18000a94a  jmp     short loc_18000A8FC
```
