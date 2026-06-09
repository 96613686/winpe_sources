# SpExportSecurityContext

- ea: `0x140025cf0`
- end: `0x140025df0`
- name: `SpExportSecurityContext`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140020980`

## callees

- `0x140025cf0`
- `0x140025df0`
- `0x140025e28`
- `0x140025e70`

## import_xrefs

- `ntoskrnl!NtDuplicateObject` at `0x140025db0`
- `ntoskrnl!NtDuplicateObject` at `0x140025db0`

## pseudocode

```c
__int64 __fastcall SpExportSecurityContext(__int64 a1, char a2, _QWORD *a3, void **a4)
{
  __int64 v8; // rax
  volatile __int64 *v9; // rbp
  NTSTATUS v10; // r14d
  void *v11; // rdx
  char v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  if ( (a2 & 1) != 0 )
    return 2148074242LL;
  if ( a4 )
    *a4 = 0;
  a3[1] = 0;
  *a3 = 0;
  v8 = KerbReferenceContext(a1, 0);
  v9 = (volatile __int64 *)v8;
  if ( v8 )
  {
    v10 = KerbMapKernelModeContext(v8, &v12, a3);
    if ( v10 >= 0 )
    {
      *(_DWORD *)(a3[1] + 108LL) |= 0x100u;
      if ( a4 )
      {
        if ( (a2 & 2) != 0 )
        {
          *a4 = (void *)_InterlockedExchange64(v9 + 13, 0);
        }
        else
        {
          v11 = (void *)*((_QWORD *)v9 + 13);
          if ( v11 )
            v10 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL, a4, 0, 0, 2u);
          else
            *a4 = 0;
        }
      }
    }
    KerbDereferenceContext((PVOID)v9);
  }
  else
  {
    return (unsigned int)-1073741816;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140025cf0  push    rbx
0x140025cf2  push    rsi
0x140025cf3  push    rdi
0x140025cf4  sub     rsp, 40h
0x140025cf8  mov     [rsp+58h+arg_8], 0
0x140025cfd  mov     rsi, r9
0x140025d00  mov     rdi, r8
0x140025d03  mov     ebx, edx
0x140025d05  test    dl, 1
0x140025d08  jz      short loc_140025D18
0x140025d0a  mov     eax, 80090302h
0x140025d0f  add     rsp, 40h
0x140025d13  pop     rdi
0x140025d14  pop     rsi
0x140025d15  pop     rbx
0x140025d16  retn
0x140025d18  mov     [rsp+58h+arg_0], rbp
0x140025d1d  mov     [rsp+58h+arg_10], r14
0x140025d22  mov     [rsp+58h+arg_18], r15
0x140025d27  xor     r15d, r15d
0x140025d2a  test    rsi, rsi
0x140025d2d  jz      short loc_140025D32
0x140025d2f  mov     [r9], r15
0x140025d32  xor     edx, edx
0x140025d34  mov     [r8+8], r15
0x140025d38  mov     [r8], r15
0x140025d3b  call    KerbReferenceContext
0x140025d40  mov     rbp, rax
0x140025d43  test    rax, rax
0x140025d46  jnz     short loc_140025D50
0x140025d48  mov     r14d, 0C0000008h
0x140025d4e  jmp     short loc_140025DCC
0x140025d50  mov     r8, rdi
0x140025d53  lea     rdx, [rsp+58h+arg_8]
0x140025d58  mov     rcx, rbp
0x140025d5b  call    KerbMapKernelModeContext
0x140025d60  mov     r14d, eax
0x140025d63  test    eax, eax
0x140025d65  js      short loc_140025DC4
0x140025d67  mov     rcx, [rdi+8]
0x140025d6b  or      dword ptr [rcx+6Ch], 100h
0x140025d72  test    rsi, rsi
0x140025d75  jz      short loc_140025DC4
0x140025d77  test    bl, 2
0x140025d7a  jz      short loc_140025D88
0x140025d7c  mov     rax, r15
0x140025d7f  xchg    rax, [rbp+68h]
0x140025d83  mov     [rsi], rax
0x140025d86  jmp     short loc_140025DC4
0x140025d88  mov     rdx, [rbp+68h]; SourceHandle
0x140025d8c  test    rdx, rdx
0x140025d8f  jz      short loc_140025DC1
0x140025d91  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x140025d98  mov     [rsp+58h+Options], 2; Options
0x140025da0  mov     r8, rcx; TargetProcessHandle
0x140025da3  mov     [rsp+58h+HandleAttributes], r15d; HandleAttributes
0x140025da8  mov     r9, rsi; TargetHandle
0x140025dab  mov     [rsp+58h+DesiredAccess], r15d; DesiredAccess
0x140025db0  call    cs:__imp_NtDuplicateObject
0x140025db7  nop     dword ptr [rax+rax+00h]
0x140025dbc  mov     r14d, eax
0x140025dbf  jmp     short loc_140025DC4
0x140025dc1  mov     [rsi], r15
0x140025dc4  mov     rcx, rbp; P
0x140025dc7  call    KerbDereferenceContext
0x140025dcc  mov     r15, [rsp+58h+arg_18]
0x140025dd1  mov     eax, r14d
0x140025dd4  mov     r14, [rsp+58h+arg_10]
0x140025dd9  mov     rbp, [rsp+58h+arg_0]
0x140025dde  add     rsp, 40h
0x140025de2  pop     rdi
0x140025de3  pop     rsi
0x140025de4  pop     rbx
0x140025de5  retn
```
