# CldiStreamAllocateRequest

- ea: `0x140035dc8`
- end: `0x140035f57`
- name: `CldiStreamAllocateRequest`
- size: `399`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14003fc70`
- `0x140040090`
- `0x1400413b4`
- `0x1400829e0`

## callees

- `0x14000d2fc`
- `0x14001e580`
- `0x140035dc8`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035df7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035e23`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035e60`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035df7`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035e23`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140035e60`
- `FLTMGR!FltReferenceContext` at `0x140035ed8`
- `FLTMGR!FltReferenceContext` at `0x140035ed8`

## pseudocode

```c
char *__fastcall CldiStreamAllocateRequest(
        _OWORD *a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        __int64 a10)
{
  char *v14; // rax
  char *v15; // rbx
  size_t v16; // r8
  char *v17; // rax

  if ( (unsigned __int16)a5 == 1 )
  {
    v14 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
    v15 = v14;
    if ( !v14 )
      return v15;
    v16 = 372;
    goto LABEL_7;
  }
  if ( (unsigned __int16)a5 == 2 )
  {
    v14 = (char *)ExAllocateFromPagedLookasideList(&stru_140028980);
    v15 = v14;
    if ( !v14 )
      return v15;
    v16 = 300;
LABEL_7:
    memset(v14 + 4, 0, v16);
    goto LABEL_11;
  }
  v15 = 0;
  if ( (unsigned __int16)a5 != 3 )
    return v15;
  v17 = (char *)ExAllocateFromPagedLookasideList(&stru_140028A00);
  v15 = v17;
  if ( !v17 )
    return v15;
  memset(v17, 0, 0x138u);
  *((_QWORD *)v15 + 7) = _InterlockedIncrement64((volatile signed __int64 *)(a4 + 8));
LABEL_11:
  *(_DWORD *)v15 = a5;
  *((_QWORD *)v15 + 16) = MEMORY[0xFFFFF78000000014];
  *((_QWORD *)v15 + 4) = v15 + 24;
  *((_QWORD *)v15 + 3) = v15 + 24;
  *((_QWORD *)v15 + 2) = v15 + 8;
  *((_QWORD *)v15 + 1) = v15 + 8;
  *((_QWORD *)v15 + 6) = v15 + 40;
  *((_QWORD *)v15 + 5) = v15 + 40;
  *((_QWORD *)v15 + 15) = a4;
  FltReferenceContext(**(PFLT_CONTEXT **)a4);
  *((_QWORD *)v15 + 14) = a6;
  *((_QWORD *)v15 + 19) = a7;
  *((_QWORD *)v15 + 20) = a8;
  v15[106] = a9;
  if ( a1 )
    *((_OWORD *)v15 + 4) = *a1;
  *((_DWORD *)v15 + 20) = a2;
  *((_DWORD *)v15 + 21) = a3;
  if ( a10 )
    TlmIncrementExtendCV(a10, v15 + 168);
  return v15;
}

```

## disassembly

```asm
0x140035dc8  push    rbx
0x140035dca  push    rbp
0x140035dcb  push    rsi
0x140035dcc  push    rdi
0x140035dcd  push    r14
0x140035dcf  push    r15
0x140035dd1  sub     rsp, 28h
0x140035dd5  mov     ebp, [rsp+58h+arg_20]
0x140035ddc  mov     rdi, r9
0x140035ddf  movzx   eax, bp
0x140035de2  mov     r14d, r8d
0x140035de5  mov     r15d, edx
0x140035de8  mov     rsi, rcx
0x140035deb  cmp     eax, 1
0x140035dee  jnz     short loc_140035E17
0x140035df0  lea     rcx, Lookaside; Lookaside
0x140035df7  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140035dfe  nop     dword ptr [rax+rax+00h]
0x140035e03  mov     rbx, rax
0x140035e06  test    rax, rax
0x140035e09  jz      loc_140035F46
0x140035e0f  mov     r8d, 174h
0x140035e15  jmp     short loc_140035E41
0x140035e17  cmp     eax, 2
0x140035e1a  jnz     short loc_140035E4E
0x140035e1c  lea     rcx, stru_140028980; Lookaside
0x140035e23  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140035e2a  nop     dword ptr [rax+rax+00h]
0x140035e2f  mov     rbx, rax
0x140035e32  test    rax, rax
0x140035e35  jz      loc_140035F46
0x140035e3b  mov     r8d, 12Ch; Size
0x140035e41  xor     edx, edx; Val
0x140035e43  lea     rcx, [rax+4]; void *
0x140035e47  call    memset
0x140035e4c  jmp     short loc_140035E9A
0x140035e4e  xor     ebx, ebx
0x140035e50  cmp     eax, 3
0x140035e53  jnz     loc_140035F46
0x140035e59  lea     rcx, stru_140028A00; Lookaside
0x140035e60  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140035e67  nop     dword ptr [rax+rax+00h]
0x140035e6c  mov     rbx, rax
0x140035e6f  test    rax, rax
0x140035e72  jz      loc_140035F46
0x140035e78  xor     edx, edx; Val
0x140035e7a  mov     r8d, 138h; Size
0x140035e80  mov     rcx, rax; void *
0x140035e83  call    memset
0x140035e88  mov     ecx, 1
0x140035e8d  lock xadd [rdi+8], rcx
0x140035e93  inc     rcx
0x140035e96  mov     [rbx+38h], rcx
0x140035e9a  mov     [rbx], ebp
0x140035e9c  mov     rax, ds:0FFFFF78000000014h
0x140035ea6  mov     [rbx+80h], rax
0x140035ead  lea     rax, [rbx+18h]
0x140035eb1  mov     [rax+8], rax
0x140035eb5  mov     [rax], rax
0x140035eb8  lea     rax, [rbx+8]
0x140035ebc  mov     [rax+8], rax
0x140035ec0  mov     [rax], rax
0x140035ec3  lea     rax, [rbx+28h]
0x140035ec7  mov     [rax+8], rax
0x140035ecb  mov     [rax], rax
0x140035ece  mov     [rbx+78h], rdi
0x140035ed2  mov     rcx, [rdi]
0x140035ed5  mov     rcx, [rcx]; Context
0x140035ed8  call    cs:__imp_FltReferenceContext
0x140035edf  nop     dword ptr [rax+rax+00h]
0x140035ee4  mov     rax, [rsp+58h+arg_28]
0x140035eec  mov     [rbx+70h], rax
0x140035ef0  mov     rax, [rsp+58h+arg_30]
0x140035ef8  mov     [rbx+98h], rax
0x140035eff  mov     rax, [rsp+58h+arg_38]
0x140035f07  mov     [rbx+0A0h], rax
0x140035f0e  mov     al, [rsp+58h+arg_40]
0x140035f15  mov     [rbx+6Ah], al
0x140035f18  test    rsi, rsi
0x140035f1b  jz      short loc_140035F25
0x140035f1d  movups  xmm0, xmmword ptr [rsi]
0x140035f20  movdqu  xmmword ptr [rbx+40h], xmm0
0x140035f25  mov     rcx, [rsp+58h+arg_48]
0x140035f2d  mov     [rbx+50h], r15d
0x140035f31  mov     [rbx+54h], r14d
0x140035f35  test    rcx, rcx
0x140035f38  jz      short loc_140035F46
0x140035f3a  lea     rdx, [rbx+0A8h]
0x140035f41  call    TlmIncrementExtendCV
0x140035f46  mov     rax, rbx
0x140035f49  add     rsp, 28h
0x140035f4d  pop     r15
0x140035f4f  pop     r14
0x140035f51  pop     rdi
0x140035f52  pop     rsi
0x140035f53  pop     rbp
0x140035f54  pop     rbx
0x140035f55  retn
```
