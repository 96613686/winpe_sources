# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x1800022ac`
- end: `0x18000233a`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `142`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800024c0`
- `0x1800025bc`

## callees

- `0x1800022ac`
- `0x18000290c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002329`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002329`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800022f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800022f4`

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
0x1800022ac  mov     rax, rsp
0x1800022af  mov     [rax+10h], rbx
0x1800022b3  push    rdi
0x1800022b4  sub     rsp, 30h
0x1800022b8  mov     rdi, rdx
0x1800022bb  mov     rbx, rcx
0x1800022be  test    rcx, rcx
0x1800022c1  jz      short loc_180002325
0x1800022c3  test    byte ptr [rcx+288h], 2
0x1800022ca  jz      short loc_1800022FA
0x1800022cc  mov     rcx, [rcx+270h]; hFile
0x1800022d3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800022d7  jz      short loc_1800022FA
0x1800022d9  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x1800022dd  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1800022e1  mov     rdx, [rdx+20h]; lpBuffer
0x1800022e5  mov     dword ptr [rax+8], 0
0x1800022ec  mov     qword ptr [rax-18h], 0
0x1800022f4  call    cs:__imp_WriteFile
0x1800022fa  test    byte ptr [rbx+288h], 20h
0x180002301  jz      short loc_18000231C
0x180002303  mov     rcx, [rbx+290h]; this
0x18000230a  test    rcx, rcx
0x18000230d  jz      short loc_18000231C
0x18000230f  mov     r8d, [rdi+30h]; unsigned int
0x180002313  mov     rdx, [rdi+20h]; char *
0x180002317  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x18000231c  test    byte ptr [rbx+288h], 1
0x180002323  jz      short loc_18000232F
0x180002325  mov     rcx, [rdi+20h]; lpOutputString
0x180002329  call    cs:__imp_OutputDebugStringA
0x18000232f  mov     rbx, [rsp+38h+arg_8]
0x180002334  add     rsp, 30h
0x180002338  pop     rdi
0x180002339  retn
```
