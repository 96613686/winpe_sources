# Win32LiveSystemProvider::GetContextSizesEx(ulong *,ulong *,ulong *,ulong)

- ea: `0x180012920`
- end: `0x1800129cb`
- name: `?GetContextSizesEx@Win32LiveSystemProvider@@UEAAXPEAK00K@Z`
- size: `171`
- prototype: `void __fastcall(Win32LiveSystemProvider *__hidden this, unsigned int *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012900`
- `0x180020fb0`

## callees

- `0x180012920`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012999`

## pseudocode

```c
void __fastcall Win32LiveSystemProvider::GetContextSizesEx(
        Win32LiveSystemProvider *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int a5)
{
  bool v5; // zf
  unsigned int v10; // r10d
  __int64 (*v11)(void); // rax
  __int64 v12; // rax

  v5 = (a5 & 0x200000) == 0;
  *a2 = 1232;
  if ( !v5 )
  {
    v10 = 0;
    a5 = 0;
    v11 = (__int64 (*)(void))*((_QWORD *)this + 93);
    if ( v11 && *((_QWORD *)this + 94) )
    {
      v12 = v11();
      *((_QWORD *)this + 95) = v12;
      if ( (v12 & 0xE4) != 0
        && ((*((unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))this + 94))(0, 1048671, 0, &a5)
         || GetLastError() != 122) )
      {
        v10 = 0;
      }
      else
      {
        v10 = a5;
      }
    }
    if ( v10 )
      *a2 = v10;
  }
  *a3 = -1;
  *a4 = -1;
}

```

## disassembly

```asm
0x180012920  mov     rax, rsp
0x180012923  push    rbx
0x180012924  push    rsi
0x180012925  push    rdi
0x180012926  push    r14
0x180012928  sub     rsp, 38h
0x18001292c  test    [rsp+58h+arg_20], 200000h
0x180012937  mov     rsi, r9
0x18001293a  mov     r14, r8
0x18001293d  mov     dword ptr [rdx], 4D0h
0x180012943  mov     rdi, rdx
0x180012946  mov     rbx, rcx
0x180012949  jz      short loc_1800129B9
0x18001294b  xor     r10d, r10d
0x18001294e  mov     [rax+28h], r10d
0x180012952  mov     rax, [rcx+2E8h]
0x180012959  test    rax, rax
0x18001295c  jz      short loc_1800129B1
0x18001295e  cmp     [rcx+2F0h], r10
0x180012965  jz      short loc_1800129B1
0x180012967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001296c  mov     [rbx+2F8h], rax
0x180012973  test    al, 0E4h
0x180012975  jz      short loc_1800129A9
0x180012977  mov     rax, [rbx+2F0h]
0x18001297e  lea     r9, [rsp+58h+arg_20]
0x180012986  xor     r8d, r8d
0x180012989  mov     edx, 10005Fh
0x18001298e  xor     ecx, ecx
0x180012990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012995  test    eax, eax
0x180012997  jnz     short loc_1800129A4
0x180012999  call    cs:__imp_GetLastError
0x18001299f  cmp     eax, 7Ah ; 'z'
0x1800129a2  jz      short loc_1800129A9
0x1800129a4  xor     r10d, r10d
0x1800129a7  jmp     short loc_1800129B1
0x1800129a9  mov     r10d, [rsp+58h+arg_20]
0x1800129b1  test    r10d, r10d
0x1800129b4  jz      short loc_1800129B9
0x1800129b6  mov     [rdi], r10d
0x1800129b9  or      eax, 0FFFFFFFFh
0x1800129bc  mov     [r14], eax
0x1800129bf  mov     [rsi], eax
0x1800129c1  add     rsp, 38h
0x1800129c5  pop     r14
0x1800129c7  pop     rdi
0x1800129c8  pop     rsi
0x1800129c9  pop     rbx
0x1800129ca  retn
```
