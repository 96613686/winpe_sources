# ATL::CAtlFile::Create(ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x180005060`
- end: `0x1800050c6`
- name: `?Create@CAtlFile@ATL@@QEAAJPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `102`
- prototype: `int(ATL::CAtlFile *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001914c`

## callees

- `0x180005060`
- `0x180019034`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000509b`
- `KERNEL32!CreateFileW` at `0x18000509b`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Create(
        ATL::CAtlFile *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
    return ATL::AtlHresultFromLastError();
  *(_QWORD *)this = FileW;
  return 0;
}

```

## disassembly

```asm
0x180005060  mov     [rsp+arg_0], rbx
0x180005065  push    rdi
0x180005066  sub     rsp, 40h
0x18000506a  mov     eax, [rsp+48h+arg_28]
0x18000506e  mov     r10d, r9d
0x180005071  mov     r11d, r8d
0x180005074  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000507d  mov     rbx, rdx
0x180005080  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180005084  mov     eax, [rsp+48h+arg_20]
0x180005088  mov     rdi, rcx
0x18000508b  mov     r8d, r10d; dwShareMode
0x18000508e  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x180005092  mov     edx, r11d; dwDesiredAccess
0x180005095  mov     rcx, rbx; lpFileName
0x180005098  xor     r9d, r9d; lpSecurityAttributes
0x18000509b  call    cs:__imp_CreateFileW
0x1800050a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800050a5  jnz     short loc_1800050B6
0x1800050a7  mov     rbx, [rsp+48h+arg_0]
0x1800050ac  add     rsp, 40h
0x1800050b0  pop     rdi
0x1800050b1  jmp     ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800050b6  mov     rbx, [rsp+48h+arg_0]
0x1800050bb  mov     [rdi], rax
0x1800050be  xor     eax, eax
0x1800050c0  add     rsp, 40h
0x1800050c4  pop     rdi
0x1800050c5  retn
```
