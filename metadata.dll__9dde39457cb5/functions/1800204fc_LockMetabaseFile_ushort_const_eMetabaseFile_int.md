# LockMetabaseFile(ushort const *,_eMetabaseFile,int)

- ea: `0x1800204fc`
- end: `0x180020564`
- name: `?LockMetabaseFile@@YAJPEBGW4_eMetabaseFile@@H@Z`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001d6d4`
- `0x180021c40`
- `0x180023df4`
- `0x180024bc4`

## callees

- `0x1800204fc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002052b`
- `KERNEL32!CreateFileW` at `0x18002052b`
- `KERNEL32!GetLastError` at `0x180020542`
- `KERNEL32!GetLastError` at `0x180020542`

## pseudocode

```c
__int64 __fastcall LockMetabaseFile(const WCHAR *a1, int a2)
{
  unsigned int v2; // edi
  __int64 v3; // rbx
  void **FileW; // rax
  signed int LastError; // eax

  v2 = 0;
  v3 = a2;
  FileW = (void **)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
  (&g_ahMetabaseFile)[v3] = FileW;
  if ( FileW == (void **)-1LL )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x1800204fc  mov     rax, rsp
0x1800204ff  mov     [rax+8], rbx
0x180020503  push    rdi
0x180020504  sub     rsp, 40h
0x180020508  xor     edi, edi
0x18002050a  movsxd  rbx, edx
0x18002050d  mov     [rax-18h], rdi
0x180020511  xor     r9d, r9d; lpSecurityAttributes
0x180020514  mov     dword ptr [rax-20h], 8000080h
0x18002051b  mov     edx, 80000000h; dwDesiredAccess
0x180020520  mov     dword ptr [rax-28h], 3
0x180020527  lea     r8d, [rdi+1]; dwShareMode
0x18002052b  call    cs:__imp_CreateFileW
0x180020531  lea     rdx, ?g_ahMetabaseFile@@3PAPEAXA; void * near * g_ahMetabaseFile
0x180020538  mov     [rdx+rbx*8], rax
0x18002053c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020540  jnz     short loc_180020557
0x180020542  call    cs:__imp_GetLastError
0x180020548  mov     edi, eax
0x18002054a  test    eax, eax
0x18002054c  jle     short loc_180020557
0x18002054e  movzx   edi, ax
0x180020551  or      edi, 80070000h
0x180020557  mov     rbx, [rsp+48h+arg_0]
0x18002055c  mov     eax, edi
0x18002055e  add     rsp, 40h
0x180020562  pop     rdi
0x180020563  retn
```
