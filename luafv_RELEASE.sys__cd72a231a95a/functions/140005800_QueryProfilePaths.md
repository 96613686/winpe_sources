# QueryProfilePaths

- ea: `0x140005800`
- end: `0x140005964`
- name: `QueryProfilePaths`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14000561c`

## callees

- `0x140005034`
- `0x140005800`
- `0x140005d00`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14000587a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000587a`

## pseudocode

```c
__int64 __fastcall QueryProfilePaths(HANDLE KeyHandle, UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  struct _UNICODE_STRING *v3; // rsi
  ULONG Length; // ebx
  __int64 Pool; // rdi
  NTSTATUS v8; // eax
  __int64 v9; // r8
  int v10; // ebx
  size_t v11; // rbx
  WCHAR *v12; // rax
  __int64 v13; // r8
  struct _UNICODE_STRING v14; // xmm1
  UNICODE_STRING v16; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING v17; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+48h] BYREF

  ResultLength = 0;
  v3 = a3;
  v16 = 0;
  v17 = 0;
  for ( Length = 532; ; Length = ResultLength )
  {
    LOBYTE(a3) = 1;
    Pool = LuafvAllocatePool(1, Length, a3);
    if ( !Pool )
    {
      v10 = -1073741670;
      goto LABEL_16;
    }
    v8 = ZwQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&ProfileValueName,
           KeyValuePartialInformation,
           (PVOID)Pool,
           Length,
           &ResultLength);
    v10 = v8;
    if ( v8 >= 0 )
      break;
    if ( v8 != -1073741789 && v8 != -2147483643 )
      goto LABEL_13;
    LuafvFreePool(Pool);
  }
  if ( (unsigned int)(*(_DWORD *)(Pool + 4) - 1) <= 1 )
  {
    LOBYTE(v9) = 2;
    v16.MaximumLength = *(_WORD *)(Pool + 8);
    v11 = (unsigned __int16)(v16.MaximumLength - 2);
    v16.Length = v16.MaximumLength - 2;
    v12 = (WCHAR *)LuafvAllocatePool(1, v11, v9);
    v16.Buffer = v12;
    if ( v12 )
    {
      memmove(v12, (const void *)(Pool + 12), v11);
      v10 = ConvertDosPathToNtPath(&v16, &v17, v13);
      if ( v10 >= 0 )
      {
        v14 = v17;
        *a2 = v16;
        *v3 = v14;
      }
    }
    else
    {
      v10 = -1073741670;
    }
  }
  else
  {
    v10 = -1073741788;
  }
LABEL_13:
  LuafvFreePool(Pool);
  if ( v10 >= 0 )
    return (unsigned int)v10;
LABEL_16:
  if ( v16.Buffer )
    LuafvFreePool(v16.Buffer);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005800  mov     [rsp-28h+arg_0], rbx
0x140005805  mov     [rsp-28h+arg_8], rsi
0x14000580a  push    rbp
0x14000580b  push    rdi
0x14000580c  push    r13
0x14000580e  push    r14
0x140005810  push    r15
0x140005812  mov     rbp, rsp
0x140005815  sub     rsp, 50h
0x140005819  xorps   xmm0, xmm0
0x14000581c  mov     [rbp+arg_18], 0
0x140005823  xorps   xmm1, xmm1
0x140005826  mov     rsi, r8
0x140005829  movups  [rbp+var_20], xmm0
0x14000582d  mov     r14, rdx
0x140005830  mov     r15, rcx
0x140005833  movups  [rbp+var_10], xmm1
0x140005837  mov     ebx, 214h
0x14000583c  mov     r13d, 2
0x140005842  mov     r8b, 1
0x140005845  mov     edx, ebx
0x140005847  mov     ecx, 1
0x14000584c  call    LuafvAllocatePool
0x140005851  mov     rdi, rax
0x140005854  test    rax, rax
0x140005857  jz      loc_140005935
0x14000585d  lea     rax, [rbp+arg_18]
0x140005861  mov     r9, rdi; KeyValueInformation
0x140005864  mov     [rsp+50h+ResultLength], rax; ResultLength
0x140005869  lea     rdx, ProfileValueName; ValueName
0x140005870  mov     r8d, r13d; KeyValueInformationClass
0x140005873  mov     [rsp+50h+Length], ebx; Length
0x140005877  mov     rcx, r15; KeyHandle
0x14000587a  call    cs:__imp_ZwQueryValueKey
0x140005881  nop     dword ptr [rax+rax+00h]
0x140005886  mov     ebx, eax
0x140005888  test    eax, eax
0x14000588a  jns     short loc_1400058AB
0x14000588c  cmp     eax, 0C0000023h
0x140005891  jz      short loc_14000589E
0x140005893  cmp     eax, 80000005h
0x140005898  jnz     loc_140005927
0x14000589e  mov     rcx, rdi
0x1400058a1  call    LuafvFreePool
0x1400058a6  mov     ebx, [rbp+arg_18]
0x1400058a9  jmp     short loc_140005842
0x1400058ab  mov     eax, [rdi+4]
0x1400058ae  dec     eax
0x1400058b0  cmp     eax, 1
0x1400058b3  jbe     short loc_1400058BC
0x1400058b5  mov     ebx, 0C0000024h
0x1400058ba  jmp     short loc_140005927
0x1400058bc  movzx   r9d, word ptr [rdi+8]
0x1400058c1  mov     r8b, r13b
0x1400058c4  movzx   eax, r9w
0x1400058c8  mov     word ptr [rbp+var_20+2], r9w
0x1400058cd  sub     ax, r13w
0x1400058d1  mov     ecx, 1
0x1400058d6  movzx   edx, ax
0x1400058d9  mov     ebx, edx
0x1400058db  mov     word ptr [rbp+var_20], dx
0x1400058df  call    LuafvAllocatePool
0x1400058e4  mov     qword ptr [rbp+var_20+8], rax
0x1400058e8  test    rax, rax
0x1400058eb  jnz     short loc_1400058F4
0x1400058ed  mov     ebx, 0C000009Ah
0x1400058f2  jmp     short loc_140005927
0x1400058f4  mov     r8, rbx; Size
0x1400058f7  lea     rdx, [rdi+0Ch]; Src
0x1400058fb  mov     rcx, rax; void *
0x1400058fe  call    memmove
0x140005903  lea     rdx, [rbp+var_10]
0x140005907  lea     rcx, [rbp+var_20]
0x14000590b  call    ConvertDosPathToNtPath
0x140005910  mov     ebx, eax
0x140005912  test    eax, eax
0x140005914  js      short loc_140005927
0x140005916  movups  xmm0, [rbp+var_20]
0x14000591a  movups  xmm1, [rbp+var_10]
0x14000591e  movdqu  xmmword ptr [r14], xmm0
0x140005923  movdqu  xmmword ptr [rsi], xmm1
0x140005927  mov     rcx, rdi
0x14000592a  call    LuafvFreePool
0x14000592f  test    ebx, ebx
0x140005931  jns     short loc_140005948
0x140005933  jmp     short loc_14000593A
0x140005935  mov     ebx, 0C000009Ah
0x14000593a  mov     rcx, qword ptr [rbp+var_20+8]
0x14000593e  test    rcx, rcx
0x140005941  jz      short loc_140005948
0x140005943  call    LuafvFreePool
0x140005948  lea     r11, [rsp+50h+var_s0]
0x14000594d  mov     eax, ebx
0x14000594f  mov     rbx, [r11+30h]
0x140005953  mov     rsi, [r11+38h]
0x140005957  mov     rsp, r11
0x14000595a  pop     r15
0x14000595c  pop     r14
0x14000595e  pop     r13
0x140005960  pop     rdi
0x140005961  pop     rbp
0x140005962  retn
```
