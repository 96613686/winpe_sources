# QueryProfilePaths

- ea: `0x140005b84`
- end: `0x140005ce8`
- name: `QueryProfilePaths`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, _OWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140005798`

## callees

- `0x140004e6c`
- `0x140005b84`
- `0x140006080`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140005bfe`
- `ntoskrnl!ZwQueryValueKey` at `0x140005bfe`

## pseudocode

```c
__int64 __fastcall QueryProfilePaths(HANDLE KeyHandle, _OWORD *a2, _OWORD *a3)
{
  _OWORD *v3; // rsi
  ULONG Length; // ebx
  __int64 Pool; // rdi
  NTSTATUS v8; // eax
  __int64 v9; // r8
  int v10; // ebx
  size_t v11; // rbx
  void *v12; // rax
  __int128 v13; // xmm1
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+48h] BYREF

  ResultLength = 0;
  v3 = a3;
  v15 = 0;
  v16 = 0;
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
    WORD1(v15) = *(_WORD *)(Pool + 8);
    v11 = (unsigned __int16)(WORD1(v15) - 2);
    LOWORD(v15) = WORD1(v15) - 2;
    v12 = (void *)LuafvAllocatePool(1, v11, v9);
    *((_QWORD *)&v15 + 1) = v12;
    if ( v12 )
    {
      memmove(v12, (const void *)(Pool + 12), v11);
      v10 = ConvertDosPathToNtPath(&v15, &v16);
      if ( v10 >= 0 )
      {
        v13 = v16;
        *a2 = v15;
        *v3 = v13;
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
  if ( *((_QWORD *)&v15 + 1) )
    LuafvFreePool(*((_QWORD *)&v15 + 1));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005b84  mov     [rsp-28h+arg_0], rbx
0x140005b89  mov     [rsp-28h+arg_8], rsi
0x140005b8e  push    rbp
0x140005b8f  push    rdi
0x140005b90  push    r13
0x140005b92  push    r14
0x140005b94  push    r15
0x140005b96  mov     rbp, rsp
0x140005b99  sub     rsp, 50h
0x140005b9d  xorps   xmm0, xmm0
0x140005ba0  mov     [rbp+arg_18], 0
0x140005ba7  xorps   xmm1, xmm1
0x140005baa  mov     rsi, r8
0x140005bad  movups  [rbp+var_20], xmm0
0x140005bb1  mov     r14, rdx
0x140005bb4  mov     r15, rcx
0x140005bb7  movups  [rbp+var_10], xmm1
0x140005bbb  mov     ebx, 214h
0x140005bc0  mov     r13d, 2
0x140005bc6  mov     r8b, 1
0x140005bc9  mov     edx, ebx
0x140005bcb  mov     ecx, 1
0x140005bd0  call    LuafvAllocatePool
0x140005bd5  mov     rdi, rax
0x140005bd8  test    rax, rax
0x140005bdb  jz      loc_140005CB9
0x140005be1  lea     rax, [rbp+arg_18]
0x140005be5  mov     r9, rdi; KeyValueInformation
0x140005be8  mov     [rsp+50h+ResultLength], rax; ResultLength
0x140005bed  lea     rdx, ProfileValueName; ValueName
0x140005bf4  mov     r8d, r13d; KeyValueInformationClass
0x140005bf7  mov     [rsp+50h+Length], ebx; Length
0x140005bfb  mov     rcx, r15; KeyHandle
0x140005bfe  call    cs:__imp_ZwQueryValueKey
0x140005c05  nop     dword ptr [rax+rax+00h]
0x140005c0a  mov     ebx, eax
0x140005c0c  test    eax, eax
0x140005c0e  jns     short loc_140005C2F
0x140005c10  cmp     eax, 0C0000023h
0x140005c15  jz      short loc_140005C22
0x140005c17  cmp     eax, 80000005h
0x140005c1c  jnz     loc_140005CAB
0x140005c22  mov     rcx, rdi
0x140005c25  call    LuafvFreePool
0x140005c2a  mov     ebx, [rbp+arg_18]
0x140005c2d  jmp     short loc_140005BC6
0x140005c2f  mov     eax, [rdi+4]
0x140005c32  dec     eax
0x140005c34  cmp     eax, 1
0x140005c37  jbe     short loc_140005C40
0x140005c39  mov     ebx, 0C0000024h
0x140005c3e  jmp     short loc_140005CAB
0x140005c40  movzx   r9d, word ptr [rdi+8]
0x140005c45  mov     r8b, r13b
0x140005c48  movzx   eax, r9w
0x140005c4c  mov     word ptr [rbp+var_20+2], r9w
0x140005c51  sub     ax, r13w
0x140005c55  mov     ecx, 1
0x140005c5a  movzx   edx, ax
0x140005c5d  mov     ebx, edx
0x140005c5f  mov     word ptr [rbp+var_20], dx
0x140005c63  call    LuafvAllocatePool
0x140005c68  mov     qword ptr [rbp+var_20+8], rax
0x140005c6c  test    rax, rax
0x140005c6f  jnz     short loc_140005C78
0x140005c71  mov     ebx, 0C000009Ah
0x140005c76  jmp     short loc_140005CAB
0x140005c78  mov     r8, rbx; Size
0x140005c7b  lea     rdx, [rdi+0Ch]; Src
0x140005c7f  mov     rcx, rax; void *
0x140005c82  call    memmove
0x140005c87  lea     rdx, [rbp+var_10]
0x140005c8b  lea     rcx, [rbp+var_20]
0x140005c8f  call    ConvertDosPathToNtPath
0x140005c94  mov     ebx, eax
0x140005c96  test    eax, eax
0x140005c98  js      short loc_140005CAB
0x140005c9a  movups  xmm0, [rbp+var_20]
0x140005c9e  movups  xmm1, [rbp+var_10]
0x140005ca2  movdqu  xmmword ptr [r14], xmm0
0x140005ca7  movdqu  xmmword ptr [rsi], xmm1
0x140005cab  mov     rcx, rdi
0x140005cae  call    LuafvFreePool
0x140005cb3  test    ebx, ebx
0x140005cb5  jns     short loc_140005CCC
0x140005cb7  jmp     short loc_140005CBE
0x140005cb9  mov     ebx, 0C000009Ah
0x140005cbe  mov     rcx, qword ptr [rbp+var_20+8]
0x140005cc2  test    rcx, rcx
0x140005cc5  jz      short loc_140005CCC
0x140005cc7  call    LuafvFreePool
0x140005ccc  lea     r11, [rsp+50h+var_s0]
0x140005cd1  mov     eax, ebx
0x140005cd3  mov     rbx, [r11+30h]
0x140005cd7  mov     rsi, [r11+38h]
0x140005cdb  mov     rsp, r11
0x140005cde  pop     r15
0x140005ce0  pop     r14
0x140005ce2  pop     r13
0x140005ce4  pop     rdi
0x140005ce5  pop     rbp
0x140005ce6  retn
```
