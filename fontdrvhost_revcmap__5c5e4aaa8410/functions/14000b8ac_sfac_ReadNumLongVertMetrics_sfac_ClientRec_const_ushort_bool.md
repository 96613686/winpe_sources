# sfac_ReadNumLongVertMetrics(sfac_ClientRec const *,ushort *,bool *)

- ea: `0x14000b8ac`
- end: `0x14000b94e`
- name: `?sfac_ReadNumLongVertMetrics@@YAHPEBUsfac_ClientRec@@PEAGPEA_N@Z`
- size: `162`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000a670`

## callees

- `0x14000b8ac`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sfac_ReadNumLongVertMetrics(const struct sfac_ClientRec *a1, unsigned __int16 *a2, bool *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = 0;
  v10 = 0;
  if ( *((_DWORD *)a1 + 47) )
  {
    v7 = *((unsigned int *)a1 + 46);
    if ( (unsigned int)v7 > 0x7FFFFFFF )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(0, v7);
      __debugbreak();
    }
    v8 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64 *))a1 + 1))(*(_QWORD *)a1, v7, 36, &v10);
    v6 = v10;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    *a2 = _byteswap_ushort(*(_WORD *)(v8 + 34));
    *a3 = 1;
  }
  if ( v6 )
    (*((void (**)(void))a1 + 2))();
  return 0;
}

```

## disassembly

```asm
0x14000b8ac  mov     rax, rsp
0x14000b8af  mov     [rax+8], rbx
0x14000b8b3  mov     [rax+10h], rsi
0x14000b8b7  push    rdi
0x14000b8b8  sub     rsp, 40h
0x14000b8bc  mov     rdi, r8
0x14000b8bf  mov     rsi, rdx
0x14000b8c2  mov     rbx, rcx
0x14000b8c5  mov     byte ptr [r8], 0
0x14000b8c9  xor     ecx, ecx
0x14000b8cb  mov     [rax+18h], rcx
0x14000b8cf  cmp     [rbx+0BCh], ecx
0x14000b8d5  jbe     short loc_14000B939
0x14000b8d7  mov     edx, [rbx+0B8h]
0x14000b8dd  cmp     edx, 7FFFFFFFh
0x14000b8e3  ja      short loc_14000B93D
0x14000b8e5  lea     r9, [rax+18h]
0x14000b8e9  lea     r8d, [rcx+24h]
0x14000b8ed  mov     rcx, [rbx]
0x14000b8f0  mov     rax, [rbx+8]
0x14000b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8f9  mov     rcx, [rsp+48h+arg_10]
0x14000b8fe  mov     [rsp+48h+var_18], rbx
0x14000b903  mov     [rsp+48h+var_10], rcx
0x14000b908  test    rax, rax
0x14000b90b  jz      short loc_14000B922
0x14000b90d  movzx   edx, byte ptr [rax+22h]
0x14000b911  shl     dx, 8
0x14000b915  movzx   eax, byte ptr [rax+23h]
0x14000b919  or      dx, ax
0x14000b91c  mov     [rsi], dx
0x14000b91f  mov     byte ptr [rdi], 1
0x14000b922  test    rcx, rcx
0x14000b925  jnz     short loc_14000B943
0x14000b927  xor     eax, eax
0x14000b929  mov     rbx, [rsp+48h+arg_0]
0x14000b92e  mov     rsi, [rsp+48h+arg_8]
0x14000b933  add     rsp, 40h
0x14000b937  pop     rdi
0x14000b938  retn
0x14000b939  xor     eax, eax
0x14000b93b  jmp     short loc_14000B8FE
0x14000b93d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14000b942  int     3; Trap to Debugger
0x14000b943  mov     rax, [rbx+10h]
0x14000b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b94c  jmp     short loc_14000B927
```
