# sub_1801BAA4C

- ea: `0x1801baa4c`
- end: `0x1801baad4`
- name: `sub_1801BAA4C`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `93`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801a8d20`
- `0x1801a934c`
- `0x1801ba828`
- `0x1801ba920`
- `0x1801bd7b8`
- `0x1801be2bc`
- `0x1801bf7b0`
- `0x1801c1394`
- `0x180227a94`
- `0x1802283f8`
- `0x180228730`
- `0x1802393c0`
- `0x180239590`
- `0x180239770`
- `0x180239910`
- `0x180239ab0`
- `0x180239c50`
- `0x180239df0`
- `0x180239f90`
- `0x18023a130`
- `0x18023a2f0`
- `0x18023a4a0`
- `0x18023a6a0`
- `0x18023a850`
- `0x18023aa10`
- `0x18023abe0`
- `0x18023ada0`
- `0x18023af60`
- `0x18023b160`
- `0x18023b360`
- `0x18023b560`
- `0x18023b720`
- `0x18023b8e0`
- `0x18023bab0`
- `0x18023bc80`
- `0x18023be30`
- `0x18023bff0`
- `0x18023c1b0`
- `0x18023c370`
- `0x18023c5e0`
- `0x18023c7a0`
- `0x18023c920`
- `0x18023caa0`
- `0x18023cc10`
- `0x18023cd80`
- `0x18023cf90`
- `0x18023d110`
- `0x18023d280`
- `0x18023d3f0`
- `0x18023d550`

## callees

- `0x1801baa4c`
- `0x180309e70`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801baa89`
- `KERNEL32!LoadLibraryExW` at `0x1801baa89`
- `api-ms-win-downlevel-ole32-l1-1-0!GetErrorInfo` at `0x1801baab3`
- `api-ms-win-downlevel-ole32-l1-1-0!GetErrorInfo` at `0x1801baab3`

## pseudocode

```c
HRESULT __fastcall sub_1801BAA4C(__int64 a1)
{
  __int64 v1; // rbx
  const WCHAR *v2; // rax
  HRESULT result; // eax
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 1184) + 8480LL;
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 1184) + 8496LL) )
  {
    v2 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(*(_QWORD *)(a1 + 1184) + 8480LL);
    *(_QWORD *)(v1 + 8) = LoadLibraryExW(v2, 0, 0x800u);
    *(_BYTE *)(v1 + 16) = 1;
  }
  result = sub_180309E70(v1);
  if ( result < 0 )
  {
    pperrinfo = 0;
    result = GetErrorInfo(0, &pperrinfo);
    if ( !result )
      return ((__int64 (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
  return result;
}

```

## disassembly

```asm
0x1801baa4c  mov     [rsp+arg_0], rcx
0x1801baa51  push    rbx
0x1801baa52  sub     rsp, 30h
0x1801baa56  mov     rax, [rsp+38h+arg_0]
0x1801baa5b  mov     rbx, [rax+4A0h]
0x1801baa62  add     rbx, 2120h
0x1801baa69  cmp     byte ptr [rbx+10h], 0
0x1801baa6d  jnz     short loc_1801BAA97
0x1801baa6f  mov     rax, [rbx]
0x1801baa72  mov     rcx, rbx
0x1801baa75  mov     rax, [rax+8]
0x1801baa79  call    j_j__guard_dispatch_icall_nop
0x1801baa7e  mov     rcx, rax; lpLibFileName
0x1801baa81  xor     edx, edx; hFile
0x1801baa83  mov     r8d, 800h; dwFlags
0x1801baa89  call    cs:LoadLibraryExW
0x1801baa8f  mov     [rbx+8], rax
0x1801baa93  mov     byte ptr [rbx+10h], 1
0x1801baa97  mov     rcx, rbx
0x1801baa9a  call    sub_180309E70
0x1801baa9f  test    eax, eax
0x1801baaa1  jns     short loc_1801BAACE
0x1801baaa3  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x1801baaa8  mov     [rsp+38h+pperrinfo], 0
0x1801baab1  xor     ecx, ecx; dwReserved
0x1801baab3  call    cs:GetErrorInfo
0x1801baab9  test    eax, eax
0x1801baabb  jnz     short loc_1801BAACE
0x1801baabd  mov     rcx, [rsp+38h+pperrinfo]
0x1801baac2  mov     rax, [rcx]
0x1801baac5  mov     rax, [rax+10h]
0x1801baac9  call    j_j__guard_dispatch_icall_nop
0x1801baace  add     rsp, 30h
0x1801baad2  pop     rbx
0x1801baad3  retn
```
