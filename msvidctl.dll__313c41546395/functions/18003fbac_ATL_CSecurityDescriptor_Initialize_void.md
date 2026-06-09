# ATL::CSecurityDescriptor::Initialize(void)

- ea: `0x18003fbac`
- end: `0x18003fc81`
- name: `?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CSecurityDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003acc0`
- `0x18003f8f8`

## callees

- `0x180004740`
- `0x180004b54`
- `0x18003fbac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fbd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fbef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fc06`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fc1d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fbd8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fbef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fc06`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fc1d`
- `KERNEL32!GetLastError` at `0x18003fc4a`
- `KERNEL32!GetLastError` at `0x18003fc4a`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18003fc40`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18003fc40`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::Initialize(ATL::CSecurityDescriptor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rax
  signed int LastError; // eax
  unsigned int v9; // edi
  __int64 result; // rax

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2, 0);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)this + 1) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    free(v5);
    *((_QWORD *)this + 3) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = operator new(0x28u);
  *(_QWORD *)this = v7;
  if ( InitializeSecurityDescriptor(v7, 1u) )
    return 0;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  operator delete(*(void **)this, 0);
  result = v9;
  *(_QWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x18003fbac  mov     [rsp+arg_0], rbx
0x18003fbb1  push    rdi
0x18003fbb2  sub     rsp, 20h
0x18003fbb6  mov     rbx, rcx
0x18003fbb9  mov     rcx, [rcx]; void *
0x18003fbbc  test    rcx, rcx
0x18003fbbf  jz      short loc_18003FBCF
0x18003fbc1  xor     edx, edx; unsigned __int64
0x18003fbc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fbc8  mov     qword ptr [rbx], 0
0x18003fbcf  mov     rcx, [rbx+8]; Block
0x18003fbd3  test    rcx, rcx
0x18003fbd6  jz      short loc_18003FBE6
0x18003fbd8  call    cs:__imp_free
0x18003fbde  mov     qword ptr [rbx+8], 0
0x18003fbe6  mov     rcx, [rbx+10h]; Block
0x18003fbea  test    rcx, rcx
0x18003fbed  jz      short loc_18003FBFD
0x18003fbef  call    cs:__imp_free
0x18003fbf5  mov     qword ptr [rbx+10h], 0
0x18003fbfd  mov     rcx, [rbx+18h]; Block
0x18003fc01  test    rcx, rcx
0x18003fc04  jz      short loc_18003FC14
0x18003fc06  call    cs:__imp_free
0x18003fc0c  mov     qword ptr [rbx+18h], 0
0x18003fc14  mov     rcx, [rbx+20h]; Block
0x18003fc18  test    rcx, rcx
0x18003fc1b  jz      short loc_18003FC2B
0x18003fc1d  call    cs:__imp_free
0x18003fc23  mov     qword ptr [rbx+20h], 0
0x18003fc2b  mov     ecx, 28h ; '('; Size
0x18003fc30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003fc35  mov     edx, 1; dwRevision
0x18003fc3a  mov     [rbx], rax
0x18003fc3d  mov     rcx, rax; pSecurityDescriptor
0x18003fc40  call    cs:__imp_InitializeSecurityDescriptor
0x18003fc46  test    eax, eax
0x18003fc48  jnz     short loc_18003FC74
0x18003fc4a  call    cs:__imp_GetLastError
0x18003fc50  mov     edi, eax
0x18003fc52  test    eax, eax
0x18003fc54  jle     short loc_18003FC5F
0x18003fc56  movzx   edi, ax
0x18003fc59  or      edi, 80070000h
0x18003fc5f  mov     rcx, [rbx]; void *
0x18003fc62  xor     edx, edx; unsigned __int64
0x18003fc64  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fc69  mov     eax, edi
0x18003fc6b  mov     qword ptr [rbx], 0
0x18003fc72  jmp     short loc_18003FC76
0x18003fc74  xor     eax, eax
0x18003fc76  mov     rbx, [rsp+28h+arg_0]
0x18003fc7b  add     rsp, 20h
0x18003fc7f  pop     rdi
0x18003fc80  retn
```
