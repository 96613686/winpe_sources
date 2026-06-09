# XMLParserShimFileStream::Read(void *,ulong,ulong *)

- ea: `0x1800302f0`
- end: `0x180030342`
- name: `?Read@XMLParserShimFileStream@@UEAAJPEAXKPEAK@Z`
- size: `82`
- prototype: `__int64 __fastcall(XMLParserShimFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x1800302f0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180030320`
- `KERNEL32!ReadFile` at `0x180030320`

## pseudocode

```c
__int64 __fastcall XMLParserShimFileStream::Read(XMLParserShimFileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v6; // rcx
  BOOL v7; // eax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 24) )
    return 2147500037LL;
  v6 = (void *)*((_QWORD *)this + 2);
  NumberOfBytesRead = 0;
  v7 = ReadFile(v6, a2, a3, &NumberOfBytesRead, 0);
  if ( a4 )
    *a4 = NumberOfBytesRead;
  return !v7 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800302f0  push    rbx
0x1800302f2  sub     rsp, 30h
0x1800302f6  cmp     byte ptr [rcx+18h], 0
0x1800302fa  mov     rbx, r9
0x1800302fd  jnz     short loc_180030306
0x1800302ff  mov     eax, 80004005h
0x180030304  jmp     short loc_18003033C
0x180030306  mov     rcx, [rcx+10h]; hFile
0x18003030a  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003030f  mov     [rsp+38h+NumberOfBytesRead], 0
0x180030317  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180030320  call    cs:__imp_ReadFile
0x180030326  test    rbx, rbx
0x180030329  jz      short loc_180030331
0x18003032b  mov     ecx, [rsp+38h+NumberOfBytesRead]
0x18003032f  mov     [rbx], ecx
0x180030331  neg     eax
0x180030333  sbb     eax, eax
0x180030335  not     eax
0x180030337  and     eax, 80004005h
0x18003033c  add     rsp, 30h
0x180030340  pop     rbx
0x180030341  retn
```
