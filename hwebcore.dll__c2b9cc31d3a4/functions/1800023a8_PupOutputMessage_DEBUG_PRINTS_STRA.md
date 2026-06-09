# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x1800023a8`
- end: `0x180002443`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `155`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002600`
- `0x180002714`

## callees

- `0x1800023a8`
- `0x180002acc`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000242b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000242b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800023f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800023f0`

## pseudocode

```c
void __fastcall PupOutputMessage(struct _DEBUG_PRINTS *a1, struct STRA *a2)
{
  void *v4; // rcx
  DWORD v5; // r8d
  const void *v6; // rdx
  CMemoryLog *v7; // rcx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    goto LABEL_9;
  if ( (*((_BYTE *)a1 + 648) & 2) != 0 )
  {
    v4 = (void *)*((_QWORD *)a1 + 78);
    if ( v4 != (void *)-1LL )
    {
      v5 = *((_DWORD *)a2 + 12);
      v6 = (const void *)*((_QWORD *)a2 + 4);
      v8 = 0;
      WriteFile(v4, v6, v5, &v8, 0);
    }
  }
  if ( (*((_BYTE *)a1 + 648) & 0x20) != 0 )
  {
    v7 = (CMemoryLog *)*((_QWORD *)a1 + 82);
    if ( v7 )
      CMemoryLog::Append(v7, *((const char **)a2 + 4), *((_DWORD *)a2 + 12));
  }
  if ( (*((_BYTE *)a1 + 648) & 1) != 0 )
LABEL_9:
    OutputDebugStringA(*((LPCSTR *)a2 + 4));
}

```

## disassembly

```asm
0x1800023a8  mov     rax, rsp
0x1800023ab  mov     [rax+10h], rbx
0x1800023af  push    rdi
0x1800023b0  sub     rsp, 30h
0x1800023b4  mov     rdi, rdx
0x1800023b7  mov     rbx, rcx
0x1800023ba  test    rcx, rcx
0x1800023bd  jz      short loc_180002427
0x1800023bf  test    byte ptr [rcx+288h], 2
0x1800023c6  jz      short loc_1800023FC
0x1800023c8  mov     rcx, [rcx+270h]; hFile
0x1800023cf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800023d3  jz      short loc_1800023FC
0x1800023d5  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x1800023d9  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1800023dd  mov     rdx, [rdx+20h]; lpBuffer
0x1800023e1  mov     dword ptr [rax+8], 0
0x1800023e8  mov     qword ptr [rax-18h], 0
0x1800023f0  call    cs:__imp_WriteFile
0x1800023f7  nop     dword ptr [rax+rax+00h]
0x1800023fc  test    byte ptr [rbx+288h], 20h
0x180002403  jz      short loc_18000241E
0x180002405  mov     rcx, [rbx+290h]; this
0x18000240c  test    rcx, rcx
0x18000240f  jz      short loc_18000241E
0x180002411  mov     r8d, [rdi+30h]; unsigned int
0x180002415  mov     rdx, [rdi+20h]; char *
0x180002419  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x18000241e  test    byte ptr [rbx+288h], 1
0x180002425  jz      short loc_180002437
0x180002427  mov     rcx, [rdi+20h]; lpOutputString
0x18000242b  call    cs:__imp_OutputDebugStringA
0x180002432  nop     dword ptr [rax+rax+00h]
0x180002437  mov     rbx, [rsp+38h+arg_8]
0x18000243c  add     rsp, 30h
0x180002440  pop     rdi
0x180002441  retn
```
