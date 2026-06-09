# ProcessCopyFiles(void *,ushort const *,ushort const *,ushort * *)

- ea: `0x18002d50c`
- end: `0x18002d601`
- name: `?ProcessCopyFiles@@YAJPEAXPEBG1PEAPEAG@Z`
- size: `245`
- prototype: `__int64 __fastcall(HINF InfHandle, LPCWSTR lpFileName, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d044`
- `0x18002d300`

## callees

- `0x18000d7e0`
- `0x18002c9fc`
- `0x18002d0d8`
- `0x18002d50c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d5e1`

## string_xrefs

- `0x18002d562`: `CopyFiles`

## pseudocode

```c
__int64 __fastcall ProcessCopyFiles(
        char *InfHandle,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int LineText; // eax
  unsigned __int16 *v8; // rdi
  int v9; // ebx
  wchar_t *v10; // rbp
  wchar_t *v11; // rax
  wchar_t *v12; // rsi
  wchar_t *Str; // [rsp+70h] [rbp+8h] BYREF

  Str = 0;
  if ( (unsigned __int64)(InfHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL && lpFileName && a3 && a4 )
  {
    *a4 = 0;
    LineText = GetLineText(InfHandle, a3, L"CopyFiles", &Str);
    v8 = Str;
    v9 = LineText;
    if ( LineText >= 0 )
    {
      v10 = Str;
      while ( v10 )
      {
        v11 = wcschr(v10, 0x2Cu);
        v12 = v11;
        if ( v11 )
          *v11 = 0;
        if ( *v10 != 64 )
          v9 = ProcessASectionInCopyFiles(InfHandle, lpFileName, v10);
        if ( v12 )
          *v12++ = 44;
        v10 = v12;
        if ( v9 < 0 )
          goto LABEL_17;
      }
      *a4 = v8;
      v8 = 0;
    }
LABEL_17:
    if ( v8 )
      LocalFree(v8);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002d50c  push    rbx
0x18002d50e  push    rbp
0x18002d50f  push    rsi
0x18002d510  push    rdi
0x18002d511  push    r12
0x18002d513  push    r13
0x18002d515  push    r14
0x18002d517  push    r15
0x18002d519  sub     rsp, 28h
0x18002d51d  lea     rax, [rcx-1]
0x18002d521  mov     [rsp+68h+Str], 0
0x18002d52a  mov     r14, r9
0x18002d52d  mov     r10, r8
0x18002d530  mov     r12, rdx
0x18002d533  mov     r15, rcx
0x18002d536  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d53a  ja      loc_18002D5E9
0x18002d540  test    rdx, rdx
0x18002d543  jz      loc_18002D5E9
0x18002d549  test    r8, r8
0x18002d54c  jz      loc_18002D5E9
0x18002d552  test    r9, r9
0x18002d555  jz      loc_18002D5E9
0x18002d55b  mov     qword ptr [r9], 0
0x18002d562  lea     r8, KeyName; "CopyFiles"
0x18002d569  lea     r9, [rsp+68h+Str]; unsigned __int16 **
0x18002d56e  mov     rdx, r10; unsigned __int16 *
0x18002d571  call    ?GetLineText@@YAJPEAXPEBG1PEAPEAG@Z; GetLineText(void *,ushort const *,ushort const *,ushort * *)
0x18002d576  mov     rdi, [rsp+68h+Str]
0x18002d57b  mov     ebx, eax
0x18002d57d  test    eax, eax
0x18002d57f  js      short loc_18002D5D9
0x18002d581  mov     rbp, rdi
0x18002d584  mov     r13d, 2Ch ; ','
0x18002d58a  test    rbp, rbp
0x18002d58d  jz      short loc_18002D5D4
0x18002d58f  mov     edx, r13d; Ch
0x18002d592  mov     rcx, rbp; Str
0x18002d595  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18002d59a  mov     rsi, rax
0x18002d59d  test    rax, rax
0x18002d5a0  jz      short loc_18002D5A7
0x18002d5a2  xor     ecx, ecx
0x18002d5a4  mov     [rax], cx
0x18002d5a7  cmp     word ptr [rbp+0], 40h ; '@'
0x18002d5ac  jz      short loc_18002D5BE
0x18002d5ae  mov     r8, rbp; unsigned __int16 *
0x18002d5b1  mov     rdx, r12; lpFileName
0x18002d5b4  mov     rcx, r15; InfHandle
0x18002d5b7  call    ?ProcessASectionInCopyFiles@@YAJPEAXPEBG1@Z; ProcessASectionInCopyFiles(void *,ushort const *,ushort const *)
0x18002d5bc  mov     ebx, eax
0x18002d5be  test    rsi, rsi
0x18002d5c1  jz      short loc_18002D5CB
0x18002d5c3  mov     [rsi], r13w
0x18002d5c7  add     rsi, 2
0x18002d5cb  mov     rbp, rsi
0x18002d5ce  test    ebx, ebx
0x18002d5d0  jns     short loc_18002D58A
0x18002d5d2  jmp     short loc_18002D5D9
0x18002d5d4  mov     [r14], rdi
0x18002d5d7  xor     edi, edi
0x18002d5d9  test    rdi, rdi
0x18002d5dc  jz      short loc_18002D5EE
0x18002d5de  mov     rcx, rdi; hMem
0x18002d5e1  call    cs:__imp_LocalFree
0x18002d5e7  jmp     short loc_18002D5EE
0x18002d5e9  mov     ebx, 80070057h
0x18002d5ee  mov     eax, ebx
0x18002d5f0  add     rsp, 28h
0x18002d5f4  pop     r15
0x18002d5f6  pop     r14
0x18002d5f8  pop     r13
0x18002d5fa  pop     r12
0x18002d5fc  pop     rdi
0x18002d5fd  pop     rsi
0x18002d5fe  pop     rbp
0x18002d5ff  pop     rbx
0x18002d600  retn
```
