# AdjustHTokenImpersonateUser

- ea: `0x18000f7d4`
- end: `0x18000f8a4`
- name: `AdjustHTokenImpersonateUser`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000e86c`

## callees

- `0x18000f7d4`
- `0x18000fd10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f884`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f884`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f84f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f858`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f84f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f858`

## pseudocode

```c
int __fastcall AdjustHTokenImpersonateUser(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  __int64 *i; // rbx
  void *v5; // rbp
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  TargetHandle = 0;
  if ( *(_QWORD *)(v1 + 64) == -1 )
  {
    v3 = 0;
LABEL_3:
    if ( (unsigned int)v3 < (unsigned int)qword_18004C970 )
    {
      LODWORD(v1) = (_DWORD)PcbTable;
      for ( i = (__int64 *)*((_QWORD *)PcbTable + v3); ; i = (__int64 *)*i )
      {
        if ( !i )
        {
          v3 = (unsigned int)(v3 + 1);
          goto LABEL_3;
        }
        v1 = *(_QWORD *)(a1 + 16);
        if ( i[2] != v1 && (i[7] & 1) != 0 )
        {
          v5 = *(void **)(i[1] + 64);
          LODWORD(v1) = CanPortsBeBundled(i, a1, 0);
          if ( (_DWORD)v1 )
          {
            if ( v5 != (void *)-1LL )
              break;
          }
        }
      }
      CurrentProcess = GetCurrentProcess();
      v7 = GetCurrentProcess();
      LODWORD(v1) = DuplicateHandle(v7, v5, CurrentProcess, &TargetHandle, 0, 1, 2u);
      if ( (_DWORD)v1 )
      {
        LODWORD(v1) = (_DWORD)TargetHandle;
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL) = TargetHandle;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000f7d4  push    rbx
0x18000f7d6  push    rbp
0x18000f7d7  push    rsi
0x18000f7d8  push    rdi
0x18000f7d9  sub     rsp, 48h
0x18000f7dd  mov     rax, [rcx+8]
0x18000f7e1  mov     rsi, rcx
0x18000f7e4  mov     [rsp+68h+TargetHandle], 0
0x18000f7ed  cmp     qword ptr [rax+40h], 0FFFFFFFFFFFFFFFFh
0x18000f7f2  jnz     loc_18000F89B
0x18000f7f8  xor     edi, edi
0x18000f7fa  cmp     edi, dword ptr cs:qword_18004C970
0x18000f800  jnb     loc_18000F89B
0x18000f806  mov     rax, qword ptr cs:PcbTable
0x18000f80d  mov     rbx, [rax+rdi*8]
0x18000f811  test    rbx, rbx
0x18000f814  jz      short loc_18000F84B
0x18000f816  mov     rax, [rsi+10h]
0x18000f81a  cmp     [rbx+10h], rax
0x18000f81e  jz      short loc_18000F846
0x18000f820  test    byte ptr [rbx+38h], 1
0x18000f824  jz      short loc_18000F846
0x18000f826  mov     rax, [rbx+8]
0x18000f82a  xor     r8d, r8d
0x18000f82d  mov     rdx, rsi
0x18000f830  mov     rcx, rbx
0x18000f833  mov     rbp, [rax+40h]
0x18000f837  call    CanPortsBeBundled
0x18000f83c  test    eax, eax
0x18000f83e  jz      short loc_18000F846
0x18000f840  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000f844  jnz     short loc_18000F84F
0x18000f846  mov     rbx, [rbx]
0x18000f849  jmp     short loc_18000F811
0x18000f84b  inc     edi
0x18000f84d  jmp     short loc_18000F7FA
0x18000f84f  call    cs:__imp_GetCurrentProcess
0x18000f855  mov     rbx, rax
0x18000f858  call    cs:__imp_GetCurrentProcess
0x18000f85e  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18000f866  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18000f86b  mov     rcx, rax; hSourceProcessHandle
0x18000f86e  mov     [rsp+68h+bInheritHandle], 1; bInheritHandle
0x18000f876  mov     r8, rbx; hTargetProcessHandle
0x18000f879  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f881  mov     rdx, rbp; hSourceHandle
0x18000f884  call    cs:__imp_DuplicateHandle
0x18000f88a  test    eax, eax
0x18000f88c  jz      short loc_18000F89B
0x18000f88e  mov     rcx, [rsi+8]
0x18000f892  mov     rax, [rsp+68h+TargetHandle]
0x18000f897  mov     [rcx+40h], rax
0x18000f89b  add     rsp, 48h
0x18000f89f  pop     rdi
0x18000f8a0  pop     rsi
0x18000f8a1  pop     rbp
0x18000f8a2  pop     rbx
0x18000f8a3  retn
```
