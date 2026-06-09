# Pku2uExportContext

- ea: `0x14000db50`
- end: `0x14000dca2`
- name: `Pku2uExportContext`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140007008`
- `0x14000db50`
- `0x140029d94`
- `0x140029dd0`
- `0x140029f3c`

## import_xrefs

- `ntoskrnl!NtDuplicateObject` at `0x14000dc56`
- `ntoskrnl!NtDuplicateObject` at `0x14000dc56`

## string_xrefs

- `0x14000dbdf`: `Invalid handle supplied for ExportSecurityContext(%p)n`

## pseudocode

```c
__int64 __fastcall Pku2uExportContext(const void *a1, int a2, _QWORD *a3, void **a4)
{
  char v6; // bp
  __int64 v9; // rax
  volatile __int64 *v10; // rdi
  NTSTATUS v11; // esi
  void *v12; // rdx
  char v13; // [rsp+88h] [rbp+10h] BYREF

  v13 = 0;
  v6 = a2;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "Pku2uExportContext context %p, flags 0x%x\n", a1, a2);
  if ( (v6 & 1) != 0 )
    return 2148074242LL;
  if ( a4 )
    *a4 = 0;
  a3[1] = 0;
  *a3 = 0;
  v9 = Pku2uReferenceContext(a1, 0);
  v10 = (volatile __int64 *)v9;
  if ( v9 )
  {
    v11 = Pku2uMapKernelModeContext(v9, &v13, a3);
    if ( v11 >= 0 )
    {
      *(_DWORD *)(a3[1] + 40LL) |= 0x100u;
      if ( a4 )
      {
        if ( (v6 & 2) != 0 )
        {
          *a4 = (void *)_InterlockedExchange64(v10 + 7, 0);
        }
        else
        {
          v12 = (void *)*((_QWORD *)v10 + 7);
          if ( v12 )
            v11 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL, a4, 0, 0, 2u);
          else
            *a4 = 0;
        }
      }
    }
    Pku2uDereferenceContext((PVOID)v10);
    goto LABEL_18;
  }
  v11 = -1073741816;
  if ( KsecInfoLevel )
  {
    KsecDebugOut(1, "Invalid handle supplied for ExportSecurityContext(%p)n", a1);
LABEL_18:
    if ( KsecInfoLevel )
      KsecDebugOut(4, "Pku2uExportContext returned 0x%x\n", v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000db50  mov     rax, rsp
0x14000db53  push    rbx
0x14000db54  push    rbp
0x14000db55  push    rsi
0x14000db56  push    rdi
0x14000db57  push    r14
0x14000db59  push    r15
0x14000db5b  sub     rsp, 48h
0x14000db5f  cmp     cs:KsecInfoLevel, 0
0x14000db66  mov     rbx, r9
0x14000db69  mov     r14, r8
0x14000db6c  mov     byte ptr [rax+10h], 0
0x14000db70  mov     ebp, edx
0x14000db72  mov     r15, rcx
0x14000db75  jz      short loc_14000DB8E
0x14000db77  mov     r9d, edx
0x14000db7a  mov     r8, rcx
0x14000db7d  lea     rdx, aPku2uexportcon; "Pku2uExportContext context %p, flags 0x"...
0x14000db84  mov     ecx, 4
0x14000db89  call    KsecDebugOut
0x14000db8e  test    bpl, 1
0x14000db92  jz      short loc_14000DB9E
0x14000db94  mov     eax, 80090302h
0x14000db99  jmp     loc_14000DC94
0x14000db9e  test    rbx, rbx
0x14000dba1  jz      short loc_14000DBAA
0x14000dba3  mov     qword ptr [rbx], 0
0x14000dbaa  xor     edx, edx
0x14000dbac  mov     qword ptr [r14+8], 0
0x14000dbb4  mov     rcx, r15
0x14000dbb7  mov     qword ptr [r14], 0
0x14000dbbe  call    Pku2uReferenceContext
0x14000dbc3  mov     rdi, rax
0x14000dbc6  test    rax, rax
0x14000dbc9  jnz     short loc_14000DBF3
0x14000dbcb  cmp     cs:KsecInfoLevel, eax
0x14000dbd1  mov     esi, 0C0000008h
0x14000dbd6  jz      loc_14000DC92
0x14000dbdc  mov     r8, r15
0x14000dbdf  lea     rdx, aInvalidHandleS; "Invalid handle supplied for ExportSecur"...
0x14000dbe6  lea     ecx, [rax+1]
0x14000dbe9  call    KsecDebugOut
0x14000dbee  jmp     loc_14000DC75
0x14000dbf3  mov     r8, r14
0x14000dbf6  lea     rdx, [rsp+78h+arg_8]
0x14000dbfe  mov     rcx, rdi
0x14000dc01  call    Pku2uMapKernelModeContext
0x14000dc06  mov     esi, eax
0x14000dc08  test    eax, eax
0x14000dc0a  js      short loc_14000DC6D
0x14000dc0c  mov     rcx, [r14+8]
0x14000dc10  bts     dword ptr [rcx+28h], 8
0x14000dc15  test    rbx, rbx
0x14000dc18  jz      short loc_14000DC6D
0x14000dc1a  test    bpl, 2
0x14000dc1e  jz      short loc_14000DC2B
0x14000dc20  xor     eax, eax
0x14000dc22  xchg    rax, [rdi+38h]
0x14000dc26  mov     [rbx], rax
0x14000dc29  jmp     short loc_14000DC6D
0x14000dc2b  mov     rdx, [rdi+38h]; SourceHandle
0x14000dc2f  test    rdx, rdx
0x14000dc32  jz      short loc_14000DC66
0x14000dc34  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000dc38  mov     [rsp+78h+Options], 2; Options
0x14000dc40  mov     r8, rcx; TargetProcessHandle
0x14000dc43  mov     [rsp+78h+HandleAttributes], 0; HandleAttributes
0x14000dc4b  mov     r9, rbx; TargetHandle
0x14000dc4e  mov     [rsp+78h+DesiredAccess], 0; DesiredAccess
0x14000dc56  call    cs:__imp_NtDuplicateObject
0x14000dc5d  nop     dword ptr [rax+rax+00h]
0x14000dc62  mov     esi, eax
0x14000dc64  jmp     short loc_14000DC6D
0x14000dc66  mov     qword ptr [rbx], 0
0x14000dc6d  mov     rcx, rdi; P
0x14000dc70  call    Pku2uDereferenceContext
0x14000dc75  cmp     cs:KsecInfoLevel, 0
0x14000dc7c  jz      short loc_14000DC92
0x14000dc7e  mov     r8d, esi
0x14000dc81  lea     rdx, aPku2uexportcon_0; "Pku2uExportContext returned 0x%x\n"
0x14000dc88  mov     ecx, 4
0x14000dc8d  call    KsecDebugOut
0x14000dc92  mov     eax, esi
0x14000dc94  add     rsp, 48h
0x14000dc98  pop     r15
0x14000dc9a  pop     r14
0x14000dc9c  pop     rdi
0x14000dc9d  pop     rsi
0x14000dc9e  pop     rbp
0x14000dc9f  pop     rbx
0x14000dca0  retn
```
