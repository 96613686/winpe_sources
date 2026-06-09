# Pku2uComputeFinishedChecksum(_PKU2U_CONTEXT *,KERB_ENCRYPTION_KEY *,KERB_CHECKSUM *)

- ea: `0x18001b670`
- end: `0x18001b7d7`
- name: `?Pku2uComputeFinishedChecksum@@YAJPEAU_PKU2U_CONTEXT@@PEAUKERB_ENCRYPTION_KEY@@PEAUKERB_CHECKSUM@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, struct KERB_ENCRYPTION_KEY *, struct KERB_CHECKSUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d220`

## callees

- `0x180018870`
- `0x18001b670`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x18001b6b9`
- `cryptdll!CDLocateCSystem` at `0x18001b6b9`
- `cryptdll!CDLocateCheckSum` at `0x18001b6d4`
- `cryptdll!CDLocateCheckSum` at `0x18001b6d4`

## pseudocode

```c
__int64 __fastcall Pku2uComputeFinishedChecksum(
        struct _PKU2U_CONTEXT *a1,
        struct KERB_ENCRYPTION_KEY *a2,
        struct KERB_CHECKSUM *a3)
{
  int v6; // ebx
  void *v7; // rax
  __int64 v8; // r10
  __int64 (__fastcall *v9)(_QWORD, __int64, _QWORD, __int64, __int64 *); // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 ***v12; // r14
  __int64 **i; // rdi
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+68h] [rbp+28h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF

  v15 = 0;
  v16 = 0;
  *(_OWORD *)a3 = 0;
  v17 = 0;
  *((_QWORD *)a3 + 2) = 0;
  v6 = CDLocateCSystem(*(unsigned int *)a2, &v15);
  if ( v6 >= 0 )
  {
    v6 = CDLocateCheckSum(*(unsigned int *)(v15 + 20), &v16);
    if ( v6 >= 0 )
    {
      v7 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, *(unsigned int *)(v16 + 4));
      *((_QWORD *)a3 + 2) = v7;
      if ( v7 )
      {
        v8 = v16;
        *((_DWORD *)a3 + 2) = *(_DWORD *)(v16 + 4);
        *(_DWORD *)a3 = *(_DWORD *)(v15 + 20);
        v9 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64 *))(v8 + 56);
        v10 = *((unsigned int *)a2 + 2);
        if ( v9 )
          v11 = v9(*((_QWORD *)a2 + 2), v10, 0, 41, &v17);
        else
          v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))(v8 + 48))(
                  *((_QWORD *)a2 + 2),
                  v10,
                  41,
                  &v17);
        v6 = v11;
        if ( v11 >= 0 )
        {
          v12 = (__int64 ***)((char *)a1 + 304);
          for ( i = *v12; i != (__int64 **)v12; i = (__int64 **)*i )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(v16 + 24))(v17, *((unsigned int *)i + 8), i[3]);
            if ( v6 < 0 )
              goto LABEL_14;
          }
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(v16 + 32))(v17, *((_QWORD *)a3 + 2));
        }
      }
      else
      {
        v6 = -1073741801;
      }
    }
  }
LABEL_14:
  if ( v17 && v16 )
    (*(void (__fastcall **)(__int64 *))(v16 + 40))(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b670  mov     [rsp-18h+arg_0], rbx
0x18001b675  mov     [rsp-18h+arg_10], rsi
0x18001b67a  push    rbp
0x18001b67b  push    rdi
0x18001b67c  push    r14
0x18001b67e  mov     rbp, rsp
0x18001b681  sub     rsp, 40h
0x18001b685  mov     rdi, rdx
0x18001b688  mov     [rbp+var_10], 0
0x18001b690  xorps   xmm0, xmm0
0x18001b693  mov     [rbp+arg_8], 0
0x18001b69b  movups  xmmword ptr [r8], xmm0
0x18001b69f  xor     eax, eax
0x18001b6a1  mov     [rbp+arg_18], 0
0x18001b6a9  mov     r14, rcx
0x18001b6ac  mov     [r8+10h], rax
0x18001b6b0  mov     ecx, [rdi]
0x18001b6b2  lea     rdx, [rbp+var_10]
0x18001b6b6  mov     rsi, r8
0x18001b6b9  call    cs:__imp_CDLocateCSystem
0x18001b6bf  mov     ebx, eax
0x18001b6c1  test    eax, eax
0x18001b6c3  js      loc_18001B7A5
0x18001b6c9  mov     rcx, [rbp+var_10]
0x18001b6cd  lea     rdx, [rbp+arg_8]
0x18001b6d1  mov     ecx, [rcx+14h]
0x18001b6d4  call    cs:__imp_CDLocateCheckSum
0x18001b6da  mov     ebx, eax
0x18001b6dc  test    eax, eax
0x18001b6de  js      loc_18001B7A5
0x18001b6e4  mov     rax, [rbp+arg_8]
0x18001b6e8  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18001b6ef  mov     edx, [rax+4]; unsigned __int64
0x18001b6f2  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001b6f7  mov     [rsi+10h], rax
0x18001b6fb  test    rax, rax
0x18001b6fe  jnz     short loc_18001B70A
0x18001b700  mov     ebx, 0C0000017h
0x18001b705  jmp     loc_18001B7A5
0x18001b70a  mov     r10, [rbp+arg_8]
0x18001b70e  mov     eax, [r10+4]
0x18001b712  mov     [rsi+8], eax
0x18001b715  mov     rax, [rbp+var_10]
0x18001b719  mov     ecx, [rax+14h]
0x18001b71c  mov     [rsi], ecx
0x18001b71e  mov     rax, [r10+38h]
0x18001b722  mov     edx, [rdi+8]
0x18001b725  test    rax, rax
0x18001b728  jz      short loc_18001B747
0x18001b72a  lea     rcx, [rbp+arg_18]
0x18001b72e  mov     r9d, 29h ; ')'
0x18001b734  mov     [rsp+40h+var_20], rcx
0x18001b739  xor     r8d, r8d
0x18001b73c  mov     rcx, [rdi+10h]
0x18001b740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b745  jmp     short loc_18001B75E
0x18001b747  mov     rcx, [rdi+10h]
0x18001b74b  lea     r9, [rbp+arg_18]
0x18001b74f  mov     rax, [r10+30h]
0x18001b753  mov     r8d, 29h ; ')'
0x18001b759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b75e  mov     ebx, eax
0x18001b760  test    eax, eax
0x18001b762  js      short loc_18001B7A5
0x18001b764  add     r14, 130h
0x18001b76b  mov     rdi, [r14]
0x18001b76e  mov     rax, [rbp+arg_8]
0x18001b772  mov     rcx, [rbp+arg_18]
0x18001b776  cmp     rdi, r14
0x18001b779  jz      short loc_18001B796
0x18001b77b  mov     r8, [rdi+18h]
0x18001b77f  mov     edx, [rdi+20h]
0x18001b782  mov     rax, [rax+18h]
0x18001b786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b78b  mov     ebx, eax
0x18001b78d  test    eax, eax
0x18001b78f  js      short loc_18001B7A5
0x18001b791  mov     rdi, [rdi]
0x18001b794  jmp     short loc_18001B76E
0x18001b796  mov     rdx, [rsi+10h]
0x18001b79a  mov     rax, [rax+20h]
0x18001b79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7a3  mov     ebx, eax
0x18001b7a5  cmp     [rbp+arg_18], 0
0x18001b7aa  jz      short loc_18001B7C2
0x18001b7ac  mov     rax, [rbp+arg_8]
0x18001b7b0  test    rax, rax
0x18001b7b3  jz      short loc_18001B7C2
0x18001b7b5  mov     rax, [rax+28h]
0x18001b7b9  lea     rcx, [rbp+arg_18]
0x18001b7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7c2  mov     rsi, [rsp+40h+arg_10]
0x18001b7c7  mov     eax, ebx
0x18001b7c9  mov     rbx, [rsp+40h+arg_0]
0x18001b7ce  add     rsp, 40h
0x18001b7d2  pop     r14
0x18001b7d4  pop     rdi
0x18001b7d5  pop     rbp
0x18001b7d6  retn
```
