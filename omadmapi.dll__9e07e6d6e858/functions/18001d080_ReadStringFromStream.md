# ReadStringFromStream

- ea: `0x18001d080`
- end: `0x18001d1a9`
- name: `ReadStringFromStream`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d080`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d18f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d18f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d134`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d134`

## pseudocode

```c
__int64 __fastcall ReadStringFromStream(__int64 *a1, _QWORD *a2)
{
  _WORD *v2; // rdi
  int v5; // ebx
  __int64 v6; // rax
  _WORD *v7; // rax
  int v9; // [rsp+60h] [rbp+30h] BYREF
  SIZE_T uBytes; // [rsp+70h] [rbp+40h] BYREF
  int v11; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  LODWORD(uBytes) = 0;
  v11 = 0;
  v9 = 0;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64, int *))(*a1 + 24))(a1, &v11, 4, &v9);
    if ( v5 >= 0 )
    {
      if ( v9 != 4 )
      {
LABEL_6:
        v5 = -2147467259;
        goto LABEL_17;
      }
      if ( v11 )
      {
        v6 = *a1;
        v9 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64, int *))(v6 + 24))(a1, &uBytes, 4, &v9);
        if ( v5 >= 0 )
        {
          if ( v9 == 4 )
          {
            if ( (unsigned int)uBytes < 2 )
            {
              v5 = -2147418113;
              goto LABEL_17;
            }
            v7 = LocalAlloc(0x40u, (unsigned int)uBytes);
            v2 = v7;
            if ( !v7 )
            {
              v5 = -2147024882;
              goto LABEL_17;
            }
            v5 = (*(__int64 (__fastcall **)(__int64 *, _WORD *, _QWORD, int *))(*a1 + 24))(
                   a1,
                   v7,
                   (unsigned int)uBytes,
                   &v9);
            if ( v5 < 0 )
              goto LABEL_17;
            if ( (_DWORD)uBytes == v9 )
            {
              v2[((unsigned __int64)(unsigned int)uBytes >> 1) - 1] = 0;
              *a2 = v2;
              v2 = 0;
              goto LABEL_17;
            }
          }
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_17:
  LocalFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d080  push    rbp
0x18001d082  push    rbx
0x18001d083  push    rsi
0x18001d084  push    rdi
0x18001d085  push    r14
0x18001d087  mov     rbp, rsp
0x18001d08a  sub     rsp, 30h
0x18001d08e  xor     edi, edi
0x18001d090  mov     r14, rdx
0x18001d093  mov     dword ptr [rbp+uBytes], edi
0x18001d096  mov     rsi, rcx
0x18001d099  mov     [rbp+arg_18], edi
0x18001d09c  mov     [rbp+arg_0], edi
0x18001d09f  test    rcx, rcx
0x18001d0a2  jnz     short loc_18001D0AE
0x18001d0a4  mov     ebx, 80004003h
0x18001d0a9  jmp     loc_18001D18C
0x18001d0ae  test    r14, r14
0x18001d0b1  jz      short loc_18001D0A4
0x18001d0b3  mov     [rdx], rdi
0x18001d0b6  lea     r9, [rbp+arg_0]
0x18001d0ba  mov     rax, [rcx]
0x18001d0bd  lea     rdx, [rbp+arg_18]
0x18001d0c1  mov     r8d, 4
0x18001d0c7  mov     rax, [rax+18h]
0x18001d0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0d0  mov     ebx, eax
0x18001d0d2  test    eax, eax
0x18001d0d4  js      loc_18001D18C
0x18001d0da  cmp     [rbp+arg_0], 4
0x18001d0de  jz      short loc_18001D0EA
0x18001d0e0  mov     ebx, 80004005h
0x18001d0e5  jmp     loc_18001D18C
0x18001d0ea  cmp     [rbp+arg_18], edi
0x18001d0ed  jz      loc_18001D18C
0x18001d0f3  mov     rax, [rsi]
0x18001d0f6  lea     r9, [rbp+arg_0]
0x18001d0fa  mov     r8d, 4
0x18001d100  mov     [rbp+arg_0], edi
0x18001d103  lea     rdx, [rbp+uBytes]
0x18001d107  mov     rcx, rsi
0x18001d10a  mov     rax, [rax+18h]
0x18001d10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d113  mov     ebx, eax
0x18001d115  test    eax, eax
0x18001d117  js      short loc_18001D18C
0x18001d119  cmp     [rbp+arg_0], 4
0x18001d11d  jnz     short loc_18001D0E0
0x18001d11f  cmp     dword ptr [rbp+uBytes], 2
0x18001d123  jnb     short loc_18001D12C
0x18001d125  mov     ebx, 8000FFFFh
0x18001d12a  jmp     short loc_18001D18C
0x18001d12c  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18001d12f  mov     ecx, 40h ; '@'; uFlags
0x18001d134  call    cs:__imp_LocalAlloc
0x18001d13b  nop     dword ptr [rax+rax+00h]
0x18001d140  mov     rdi, rax
0x18001d143  test    rax, rax
0x18001d146  jnz     short loc_18001D14F
0x18001d148  mov     ebx, 8007000Eh
0x18001d14d  jmp     short loc_18001D18C
0x18001d14f  mov     rax, [rsi]
0x18001d152  lea     r9, [rbp+arg_0]
0x18001d156  mov     r8d, dword ptr [rbp+uBytes]
0x18001d15a  mov     rdx, rdi
0x18001d15d  mov     rcx, rsi
0x18001d160  mov     rax, [rax+18h]
0x18001d164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d169  mov     ebx, eax
0x18001d16b  test    eax, eax
0x18001d16d  js      short loc_18001D18C
0x18001d16f  mov     eax, dword ptr [rbp+uBytes]
0x18001d172  cmp     eax, [rbp+arg_0]
0x18001d175  jnz     loc_18001D0E0
0x18001d17b  mov     ecx, eax
0x18001d17d  xor     eax, eax
0x18001d17f  shr     rcx, 1
0x18001d182  mov     [rdi+rcx*2-2], ax
0x18001d187  mov     [r14], rdi
0x18001d18a  xor     edi, edi
0x18001d18c  mov     rcx, rdi; hMem
0x18001d18f  call    cs:__imp_LocalFree
0x18001d196  nop     dword ptr [rax+rax+00h]
0x18001d19b  mov     eax, ebx
0x18001d19d  add     rsp, 30h
0x18001d1a1  pop     r14
0x18001d1a3  pop     rdi
0x18001d1a4  pop     rsi
0x18001d1a5  pop     rbx
0x18001d1a6  pop     rbp
0x18001d1a7  retn
```
