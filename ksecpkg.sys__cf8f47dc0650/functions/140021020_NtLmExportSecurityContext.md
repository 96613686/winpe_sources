# NtLmExportSecurityContext

- ea: `0x140021020`
- end: `0x1400210fe`
- name: `NtLmExportSecurityContext`
- size: `222`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140010240`
- `0x140021020`
- `0x1400211a0`
- `0x14002fe40`

## import_xrefs

- `ntoskrnl!NtDuplicateObject` at `0x1400210d2`
- `ntoskrnl!NtDuplicateObject` at `0x1400210d2`

## pseudocode

```c
__int64 __fastcall NtLmExportSecurityContext(_QWORD *P, int a2, _QWORD *a3, void **a4)
{
  struct _SECPKG_KERNEL_FUNCTIONS *v8; // rax
  int PackedContext; // esi
  void *v10; // rdx
  char v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = LsaKernelFunctions;
  a3[1] = 0;
  *a3 = 0;
  PackedContext = (*((__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))v8 + 4))(P, 1296847950, 0);
  if ( PackedContext >= 0 )
  {
    PackedContext = NtLmMakePackedContext((__int64)P, &v12, (__int64)a3, a2);
    if ( PackedContext >= 0 && a4 )
    {
      v10 = (void *)P[7];
      if ( (a2 & 2) != 0 )
      {
        *a4 = v10;
        P[7] = 0;
      }
      else
      {
        PackedContext = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v10, 0, a4, 0, 0, 2u);
      }
    }
    NtlmDerefContext(P);
  }
  return (unsigned int)PackedContext;
}

```

## disassembly

```asm
0x140021020  mov     [rsp+arg_0], rbx
0x140021025  mov     [rsp+arg_8], rbp
0x14002102a  push    rsi
0x14002102b  push    rdi
0x14002102c  push    r14
0x14002102e  sub     rsp, 40h
0x140021032  mov     [rsp+58h+arg_10], 0
0x140021037  mov     rbx, r9
0x14002103a  mov     r14, r8
0x14002103d  mov     ebp, edx
0x14002103f  mov     rdi, rcx
0x140021042  test    r9, r9
0x140021045  jz      short loc_14002104E
0x140021047  mov     qword ptr [r9], 0
0x14002104e  mov     rax, cs:?LsaKernelFunctions@@3PEAU_SECPKG_KERNEL_FUNCTIONS@@EA; _SECPKG_KERNEL_FUNCTIONS * LsaKernelFunctions
0x140021055  mov     edx, 4D4C544Eh
0x14002105a  mov     qword ptr [r8+8], 0
0x140021062  mov     qword ptr [r8], 0
0x140021069  xor     r8d, r8d
0x14002106c  mov     rax, [rax+20h]
0x140021070  call    _guard_dispatch_icall
0x140021075  mov     esi, eax
0x140021077  test    eax, eax
0x140021079  js      short loc_1400210E8
0x14002107b  mov     r9d, ebp
0x14002107e  lea     rdx, [rsp+58h+arg_10]
0x140021083  mov     r8, r14
0x140021086  mov     rcx, rdi
0x140021089  call    NtLmMakePackedContext
0x14002108e  mov     esi, eax
0x140021090  test    eax, eax
0x140021092  js      short loc_1400210E0
0x140021094  test    rbx, rbx
0x140021097  jz      short loc_1400210E0
0x140021099  mov     rdx, [rdi+38h]; SourceHandle
0x14002109d  test    bpl, 2
0x1400210a1  jz      short loc_1400210B0
0x1400210a3  mov     [rbx], rdx
0x1400210a6  mov     qword ptr [rdi+38h], 0
0x1400210ae  jmp     short loc_1400210E0
0x1400210b0  mov     [rsp+58h+Options], 2; Options
0x1400210b8  mov     r9, rbx; TargetHandle
0x1400210bb  mov     [rsp+58h+HandleAttributes], 0; HandleAttributes
0x1400210c3  xor     r8d, r8d; TargetProcessHandle
0x1400210c6  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1400210ca  mov     [rsp+58h+DesiredAccess], 0; DesiredAccess
0x1400210d2  call    cs:__imp_NtDuplicateObject
0x1400210d9  nop     dword ptr [rax+rax+00h]
0x1400210de  mov     esi, eax
0x1400210e0  mov     rcx, rdi; P
0x1400210e3  call    NtlmDerefContext
0x1400210e8  mov     rbx, [rsp+58h+arg_0]
0x1400210ed  mov     eax, esi
0x1400210ef  mov     rbp, [rsp+58h+arg_8]
0x1400210f4  add     rsp, 40h
0x1400210f8  pop     r14
0x1400210fa  pop     rdi
0x1400210fb  pop     rsi
0x1400210fc  retn
```
