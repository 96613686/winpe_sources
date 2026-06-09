# SecCreateHandleContext

- ea: `0x1400233b4`
- end: `0x1400234ec`
- name: `SecCreateHandleContext`
- size: `312`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x140007180`
- `0x140023a2c`
- `0x140023e10`
- `0x14002466c`
- `0x140024900`

## callees

- `0x140010347`
- `0x1400103b3`
- `0x1400103d7`
- `0x140011650`
- `0x1400119c0`
- `0x1400233b4`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140023448`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140023448`

## pseudocode

```c
__int64 __fastcall SecCreateHandleContext(__int64 a1, PFLT_CONTEXT *a2)
{
  NTSTATUS v4; // ebx
  PFLT_CONTEXT NewContext; // [rsp+38h] [rbp-30h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+40h] [rbp-28h] BYREF

  NewContext = 0;
  OldContext = 0;
  v4 = FltAllocateContext_0(*(PFLT_FILTER *)(a1 + 8), 0x10u, 0xD0u, PagedPool, &NewContext);
  if ( v4 >= 0 )
  {
    memset(NewContext, 0, 0xD0u);
    *(_WORD *)NewContext = -9725;
    *((_WORD *)NewContext + 1) = 208;
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)NewContext + 1);
    v4 = FltSetStreamHandleContext_0(
           *(PFLT_INSTANCE *)(a1 + 24),
           *(PFILE_OBJECT *)(a1 + 32),
           FLT_SET_CONTEXT_KEEP_IF_EXISTS,
           NewContext,
           &OldContext);
    if ( v4 < 0 )
    {
      FltReleaseContext_0(NewContext);
      NewContext = 0;
      if ( v4 == -1071906814 )
      {
        *a2 = OldContext;
        v4 = 0;
      }
    }
    else
    {
      *a2 = NewContext;
      NewContext = 0;
    }
  }
  if ( NewContext )
    FltReleaseContext_0(NewContext);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400233b4  mov     r11, rsp
0x1400233b7  mov     [r11+18h], rbx
0x1400233bb  push    rsi
0x1400233bc  push    rdi
0x1400233bd  push    r15
0x1400233bf  sub     rsp, 50h
0x1400233c3  mov     rax, cs:__security_cookie
0x1400233ca  xor     rax, rsp
0x1400233cd  mov     [rsp+68h+var_20], rax
0x1400233d2  mov     rdi, rdx
0x1400233d5  mov     rsi, rcx
0x1400233d8  mov     qword ptr [r11-30h], 0
0x1400233e0  mov     qword ptr [r11-28h], 0
0x1400233e8  mov     edx, 10h; ContextType
0x1400233ed  lea     rax, [r11-30h]
0x1400233f1  mov     [r11-48h], rax
0x1400233f5  lea     r9d, [rdx-0Fh]; PoolType
0x1400233f9  mov     r15d, 0D0h
0x1400233ff  mov     r8d, r15d; ContextSize
0x140023402  mov     rcx, [rcx+8]; Filter
0x140023406  call    FltAllocateContext_0
0x14002340b  mov     ebx, eax
0x14002340d  mov     [rsp+68h+var_38], eax
0x140023411  test    eax, eax
0x140023413  js      loc_1400234BC
0x140023419  mov     r8d, r15d; Size
0x14002341c  xor     edx, edx; Val
0x14002341e  mov     rcx, [rsp+68h+NewContext]; void *
0x140023423  call    memset
0x140023428  mov     ecx, 0DA03h
0x14002342d  mov     rax, [rsp+68h+NewContext]
0x140023432  mov     [rax], cx
0x140023435  mov     rax, [rsp+68h+NewContext]
0x14002343a  mov     [rax+2], r15w
0x14002343f  mov     rcx, [rsp+68h+NewContext]
0x140023444  add     rcx, 8; RunRef
0x140023448  call    cs:__imp_ExInitializeRundownProtection
0x14002344f  nop     dword ptr [rax+rax+00h]
0x140023454  lea     rax, [rsp+68h+var_28]
0x140023459  mov     [rsp+68h+OldContext], rax; OldContext
0x14002345e  mov     r9, [rsp+68h+NewContext]; NewContext
0x140023463  mov     r8d, 1; Operation
0x140023469  mov     rdx, [rsi+20h]; FileObject
0x14002346d  mov     rcx, [rsi+18h]; Instance
0x140023471  call    FltSetStreamHandleContext_0
0x140023476  mov     ebx, eax
0x140023478  mov     [rsp+68h+var_38], eax
0x14002347c  test    eax, eax
0x14002347e  js      short loc_140023493
0x140023480  mov     rax, [rsp+68h+NewContext]
0x140023485  mov     [rdi], rax
0x140023488  mov     [rsp+68h+NewContext], 0
0x140023491  jmp     short loc_1400234BC
0x140023493  mov     rcx, [rsp+68h+NewContext]; Context
0x140023498  call    FltReleaseContext_0
0x14002349d  mov     [rsp+68h+NewContext], 0
0x1400234a6  cmp     ebx, 0C01C0002h
0x1400234ac  jnz     short loc_1400234BC
0x1400234ae  mov     rax, [rsp+68h+var_28]
0x1400234b3  mov     [rdi], rax
0x1400234b6  xor     ebx, ebx
0x1400234b8  mov     [rsp+68h+var_38], ebx
0x1400234bc  mov     rcx, [rsp+68h+NewContext]; Context
0x1400234c1  test    rcx, rcx
0x1400234c4  jz      short loc_1400234CB
0x1400234c6  call    FltReleaseContext_0
0x1400234cb  mov     eax, ebx
0x1400234cd  mov     rcx, [rsp+68h+var_20]
0x1400234d2  xor     rcx, rsp; StackCookie
0x1400234d5  call    __security_check_cookie
0x1400234da  mov     rbx, [rsp+68h+arg_10]
0x1400234e2  add     rsp, 50h
0x1400234e6  pop     r15
0x1400234e8  pop     rdi
0x1400234e9  pop     rsi
0x1400234ea  retn
0x1400444e7  push    rbp
0x1400444e9  sub     rsp, 30h
0x1400444ed  mov     rbp, rdx
0x1400444f0  mov     rcx, [rbp+38h]; Context
0x1400444f4  test    rcx, rcx
0x1400444f7  jz      short loc_1400444FF
0x1400444f9  call    FltReleaseContext_0
0x1400444fe  nop
0x1400444ff  add     rsp, 30h
0x140044503  pop     rbp
0x140044504  retn
```
