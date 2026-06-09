# ATL::CAtlFile::Create(ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)

- ea: `0x1400375a0`
- end: `0x140037687`
- name: `?Create@CAtlFile@ATL@@QEAAJPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z`
- size: `231`
- prototype: `int(ATL::CAtlFile *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140052b24`

## callees

- `0x1400344fc`
- `0x1400375a0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14003765f`
- `KERNEL32!CreateFileW` at `0x14003765f`
- `KERNEL32!GetModuleHandleW` at `0x1400375cb`
- `KERNEL32!GetModuleHandleW` at `0x1400375cb`
- `KERNEL32!GetProcAddress` at `0x1400375e0`
- `KERNEL32!GetProcAddress` at `0x1400375e0`

## string_xrefs

- `0x1400375c4`: `kernel32.dll`
- `0x1400375d6`: `CreateFileTransactedW`

## pseudocode

```c
__int64 __fastcall ATL::CAtlFile::Create(
        ATL::CAtlFile *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        DWORD dwCreationDisposition)
{
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 FileW; // rax

  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    if ( *(_QWORD *)v5 )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "CreateFileTransactedW");
        if ( ProcAddress )
        {
          FileW = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, __int64))ProcAddress)(a2, 0x40000000, 1);
          goto LABEL_9;
        }
      }
      goto LABEL_7;
    }
    if ( !*(_DWORD *)(v5 + 8) )
    {
LABEL_7:
      FileW = -1;
      goto LABEL_9;
    }
  }
  FileW = (__int64)CreateFileW(a2, 0x40000000u, 1u, 0, dwCreationDisposition, 0x80u, 0);
LABEL_9:
  if ( FileW == -1 )
    return ATL::AtlHresultFromLastError();
  *(_QWORD *)this = FileW;
  return 0;
}

```

## disassembly

```asm
0x1400375a0  mov     [rsp+arg_0], rbx
0x1400375a5  mov     [rsp+arg_8], rsi
0x1400375aa  push    rdi
0x1400375ab  sub     rsp, 50h
0x1400375af  mov     rbx, [rcx+8]
0x1400375b3  mov     rsi, rdx
0x1400375b6  mov     rdi, rcx
0x1400375b9  test    rbx, rbx
0x1400375bc  jz      short loc_140037637
0x1400375be  cmp     qword ptr [rbx], 0
0x1400375c2  jz      short loc_14003762B
0x1400375c4  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1400375cb  call    cs:__imp_GetModuleHandleW
0x1400375d1  test    rax, rax
0x1400375d4  jz      short loc_140037631
0x1400375d6  lea     rdx, aCreatefiletran; "CreateFileTransactedW"
0x1400375dd  mov     rcx, rax; hModule
0x1400375e0  call    cs:__imp_GetProcAddress
0x1400375e6  test    rax, rax
0x1400375e9  jz      short loc_140037631
0x1400375eb  and     [rsp+58h+var_10], 0
0x1400375f1  xor     r9d, r9d
0x1400375f4  and     [rsp+58h+var_18], 0
0x1400375fa  mov     edx, 40000000h
0x1400375ff  mov     rcx, [rbx]
0x140037602  mov     [rsp+58h+var_20], rcx
0x140037607  and     [rsp+58h+var_28], 0
0x14003760d  lea     r8d, [r9+1]
0x140037611  mov     ecx, [rsp+58h+arg_20]
0x140037618  mov     [rsp+58h+dwFlagsAndAttributes], 80h
0x140037620  mov     [rsp+58h+dwCreationDisposition], ecx
0x140037624  mov     rcx, rsi
0x140037627  call    rax
0x140037629  jmp     short loc_140037665
0x14003762b  cmp     dword ptr [rbx+8], 0
0x14003762f  jnz     short loc_140037637
0x140037631  or      rax, 0FFFFFFFFFFFFFFFFh
0x140037635  jmp     short loc_140037665
0x140037637  and     [rsp+58h+var_28], 0
0x14003763d  xor     r9d, r9d; lpSecurityAttributes
0x140037640  mov     eax, [rsp+58h+arg_20]
0x140037647  mov     edx, 40000000h; dwDesiredAccess
0x14003764c  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140037654  mov     rcx, rsi; lpFileName
0x140037657  mov     [rsp+58h+dwCreationDisposition], eax; dwCreationDisposition
0x14003765b  lea     r8d, [r9+1]; dwShareMode
0x14003765f  call    cs:__imp_CreateFileW
0x140037665  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140037669  jnz     short loc_140037672
0x14003766b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140037670  jmp     short loc_140037677
0x140037672  mov     [rdi], rax
0x140037675  xor     eax, eax
0x140037677  mov     rbx, [rsp+58h+arg_0]
0x14003767c  mov     rsi, [rsp+58h+arg_8]
0x140037681  add     rsp, 50h
0x140037685  pop     rdi
0x140037686  retn
```
