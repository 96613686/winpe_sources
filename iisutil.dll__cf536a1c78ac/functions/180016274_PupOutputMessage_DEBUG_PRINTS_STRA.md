# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x180016274`
- end: `0x18001630f`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `155`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008000`
- `0x180018ec0`
- `0x180020340`

## callees

- `0x180016274`
- `0x180024b30`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800162f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800162f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800162bc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800162bc`

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
0x180016274  mov     rax, rsp
0x180016277  mov     [rax+10h], rbx
0x18001627b  push    rdi
0x18001627c  sub     rsp, 30h
0x180016280  mov     rdi, rdx
0x180016283  mov     rbx, rcx
0x180016286  test    rcx, rcx
0x180016289  jz      short loc_1800162F3
0x18001628b  test    byte ptr [rcx+288h], 2
0x180016292  jz      short loc_1800162C8
0x180016294  mov     rcx, [rcx+270h]; hFile
0x18001629b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001629f  jz      short loc_1800162C8
0x1800162a1  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x1800162a5  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1800162a9  mov     rdx, [rdx+20h]; lpBuffer
0x1800162ad  mov     dword ptr [rax+8], 0
0x1800162b4  mov     qword ptr [rax-18h], 0
0x1800162bc  call    cs:__imp_WriteFile
0x1800162c3  nop     dword ptr [rax+rax+00h]
0x1800162c8  test    byte ptr [rbx+288h], 20h
0x1800162cf  jz      short loc_1800162EA
0x1800162d1  mov     rcx, [rbx+290h]; this
0x1800162d8  test    rcx, rcx
0x1800162db  jz      short loc_1800162EA
0x1800162dd  mov     r8d, [rdi+30h]; unsigned int
0x1800162e1  mov     rdx, [rdi+20h]; char *
0x1800162e5  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x1800162ea  test    byte ptr [rbx+288h], 1
0x1800162f1  jz      short loc_180016303
0x1800162f3  mov     rcx, [rdi+20h]; lpOutputString
0x1800162f7  call    cs:__imp_OutputDebugStringA
0x1800162fe  nop     dword ptr [rax+rax+00h]
0x180016303  mov     rbx, [rsp+38h+arg_8]
0x180016308  add     rsp, 30h
0x18001630c  pop     rdi
0x18001630d  retn
```
