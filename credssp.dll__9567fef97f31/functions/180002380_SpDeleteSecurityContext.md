# SpDeleteSecurityContext

- ea: `0x180002380`
- end: `0x180002448`
- name: `SpDeleteSecurityContext`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002380`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x1800023a2`
- `SspiCli!DeleteSecurityContext` at `0x1800023b1`
- `SspiCli!DeleteSecurityContext` at `0x1800023a2`
- `SspiCli!DeleteSecurityContext` at `0x1800023b1`
- `SspiCli!FreeContextBuffer` at `0x18000241a`
- `SspiCli!FreeContextBuffer` at `0x18000241a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000242c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002435`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000242c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002435`

## pseudocode

```c
__int64 __fastcall SpDeleteSecurityContext(__int64 a1)
{
  __int64 v2; // rbx
  unsigned int v3; // edi
  SECURITY_STATUS v4; // eax
  SECURITY_STATUS v5; // eax
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rax
  void *v11; // rcx

  if ( !a1 )
    return 2148074241LL;
  v2 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  v4 = DeleteSecurityContext((PCtxtHandle)v2);
  if ( v4 < 0 )
    v3 = v4;
  v5 = DeleteSecurityContext((PCtxtHandle)(v2 + 16));
  v6 = *(void **)(v2 + 64);
  if ( v5 < 0 )
    v3 = v5;
  if ( v6 )
    LocalFree(v6);
  v7 = *(void **)(v2 + 96);
  if ( v7 )
    LocalFree(v7);
  v8 = *(void **)(v2 + 112);
  if ( v8 )
    LocalFree(v8);
  v9 = *(void **)(v2 + 128);
  if ( v9 )
    LocalFree(v9);
  v10 = *(_QWORD *)(v2 + 72);
  if ( v10 )
  {
    v11 = *(void **)(*(_QWORD *)(v10 + 8) + 8LL);
    if ( v11 )
    {
      if ( (*(_DWORD *)(v2 + 36) & 0x100) != 0 )
        FreeContextBuffer(v11);
      else
        LocalFree(v11);
    }
    LocalFree(*(HLOCAL *)(v2 + 72));
  }
  LocalFree((HLOCAL)v2);
  return v3;
}

```

## disassembly

```asm
0x180002380  mov     [rsp+arg_0], rbx
0x180002385  push    rdi
0x180002386  sub     rsp, 20h
0x18000238a  test    rcx, rcx
0x18000238d  jnz     short loc_180002399
0x18000238f  mov     eax, 80090301h
0x180002394  jmp     loc_18000243D
0x180002399  mov     rbx, [rcx+8]
0x18000239d  xor     edi, edi
0x18000239f  mov     rcx, rbx; phContext
0x1800023a2  call    cs:__imp_DeleteSecurityContext
0x1800023a8  test    eax, eax
0x1800023aa  lea     rcx, [rbx+10h]; phContext
0x1800023ae  cmovs   edi, eax
0x1800023b1  call    cs:__imp_DeleteSecurityContext
0x1800023b7  mov     rcx, [rbx+40h]; hMem
0x1800023bb  test    eax, eax
0x1800023bd  cmovs   edi, eax
0x1800023c0  test    rcx, rcx
0x1800023c3  jz      short loc_1800023CB
0x1800023c5  call    cs:__imp_LocalFree
0x1800023cb  mov     rcx, [rbx+60h]; hMem
0x1800023cf  test    rcx, rcx
0x1800023d2  jz      short loc_1800023DA
0x1800023d4  call    cs:__imp_LocalFree
0x1800023da  mov     rcx, [rbx+70h]; hMem
0x1800023de  test    rcx, rcx
0x1800023e1  jz      short loc_1800023E9
0x1800023e3  call    cs:__imp_LocalFree
0x1800023e9  mov     rcx, [rbx+80h]; hMem
0x1800023f0  test    rcx, rcx
0x1800023f3  jz      short loc_1800023FB
0x1800023f5  call    cs:__imp_LocalFree
0x1800023fb  mov     rax, [rbx+48h]
0x1800023ff  test    rax, rax
0x180002402  jz      short loc_180002432
0x180002404  mov     rax, [rax+8]
0x180002408  mov     rcx, [rax+8]; hMem
0x18000240c  test    rcx, rcx
0x18000240f  jz      short loc_180002428
0x180002411  test    dword ptr [rbx+24h], 100h
0x180002418  jz      short loc_180002422
0x18000241a  call    cs:__imp_FreeContextBuffer
0x180002420  jmp     short loc_180002428
0x180002422  call    cs:__imp_LocalFree
0x180002428  mov     rcx, [rbx+48h]; hMem
0x18000242c  call    cs:__imp_LocalFree
0x180002432  mov     rcx, rbx; hMem
0x180002435  call    cs:__imp_LocalFree
0x18000243b  mov     eax, edi
0x18000243d  mov     rbx, [rsp+28h+arg_0]
0x180002442  add     rsp, 20h
0x180002446  pop     rdi
0x180002447  retn
```
