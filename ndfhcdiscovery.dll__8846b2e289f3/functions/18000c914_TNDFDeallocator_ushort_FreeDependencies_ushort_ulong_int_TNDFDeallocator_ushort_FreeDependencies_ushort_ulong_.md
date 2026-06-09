# TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>::~TNDFDeallocator<ushort * *,&FreeDependencies(ushort * *,ulong,int)>(void)

- ea: `0x18000c914`
- end: `0x18000c972`
- name: `??1?$TNDFDeallocator@PEAPEAG$1?FreeDependencies@@YAXPEAPEAGKH@Z@@QEAA@XZ`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013f4d`

## callees

- `0x18000c914`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c95a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c95a`

## pseudocode

```c
void __fastcall TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>::~TNDFDeallocator<unsigned short * *,&void FreeDependencies(unsigned short * *,unsigned long,int)>(
        __int64 a1)
{
  LPVOID *v1; // rdi
  unsigned int v2; // ebp
  __int64 v3; // rsi
  int i; // r14d

  v1 = *(LPVOID **)a1;
  if ( *(_QWORD *)a1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    v3 = 0;
    for ( i = *(_DWORD *)(a1 + 12); (unsigned int)v3 < v2; v3 = (unsigned int)(v3 + 1) )
    {
      CoTaskMemFree(v1[v3]);
      v1[v3] = 0;
    }
    if ( i )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x18000c914  push    rbx
0x18000c916  push    rbp
0x18000c917  push    rsi
0x18000c918  push    rdi
0x18000c919  push    r14
0x18000c91b  sub     rsp, 20h
0x18000c91f  mov     rdi, [rcx]
0x18000c922  test    rdi, rdi
0x18000c925  jz      short loc_18000C966
0x18000c927  mov     ebp, [rcx+8]
0x18000c92a  xor     esi, esi
0x18000c92c  mov     r14d, [rcx+0Ch]
0x18000c930  test    ebp, ebp
0x18000c932  jz      short loc_18000C952
0x18000c934  mov     rcx, [rdi+rsi*8]; pv
0x18000c938  call    cs:__imp_CoTaskMemFree
0x18000c93f  nop     dword ptr [rax+rax+00h]
0x18000c944  mov     qword ptr [rdi+rsi*8], 0
0x18000c94c  inc     esi
0x18000c94e  cmp     esi, ebp
0x18000c950  jb      short loc_18000C934
0x18000c952  test    r14d, r14d
0x18000c955  jz      short loc_18000C966
0x18000c957  mov     rcx, rdi; pv
0x18000c95a  call    cs:__imp_CoTaskMemFree
0x18000c961  nop     dword ptr [rax+rax+00h]
0x18000c966  add     rsp, 20h
0x18000c96a  pop     r14
0x18000c96c  pop     rdi
0x18000c96d  pop     rsi
0x18000c96e  pop     rbp
0x18000c96f  pop     rbx
0x18000c970  retn
```
