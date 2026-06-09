# WriteCount

- ea: `0x180004640`
- end: `0x1800046be`
- name: `WriteCount`
- size: `126`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int (__fastcall *)(__int64, __int64, _QWORD, int *, __int64), _QWORD *, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a28`
- `0x180003340`
- `0x180003870`
- `0x1800039b8`
- `0x180014140`

## callees

- `0x180004640`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall WriteCount(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int (__fastcall *a4)(__int64, __int64, _QWORD, int *, __int64),
        _QWORD *a5,
        __int64 a6)
{
  unsigned int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  int v13; // eax
  int v14; // [rsp+50h] [rbp+18h] BYREF

  v7 = *(_DWORD *)a1 + a3;
  if ( *(_DWORD *)a1 > v7 )
  {
    v11 = a5;
    *a5 = 9;
    *((_DWORD *)v11 + 2) = 1;
  }
  else
  {
    v8 = a6;
    *(_DWORD *)a1 = v7;
    v9 = *(_QWORD *)(a1 + 8);
    v14 = 0;
    if ( a3 == a4(v9, a2, a3, &v14, v8) )
      return 1;
    v12 = a5;
    v13 = v14;
    *(_DWORD *)a5 = 4;
    *((_DWORD *)v12 + 1) = v13;
    *((_DWORD *)v12 + 2) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180004640  push    rbx
0x180004642  sub     rsp, 30h
0x180004646  mov     ebx, r8d
0x180004649  mov     r10, r9
0x18000464c  add     r8d, [rcx]
0x18000464f  cmp     [rcx], r8d
0x180004652  ja      short loc_18000468C
0x180004654  mov     rax, [rsp+38h+arg_28]
0x180004659  lea     r9, [rsp+38h+arg_10]
0x18000465e  mov     [rcx], r8d
0x180004661  mov     r8d, ebx
0x180004664  mov     rcx, [rcx+8]
0x180004668  mov     [rsp+38h+var_18], rax
0x18000466d  mov     rax, r10
0x180004670  mov     [rsp+38h+arg_10], 0
0x180004678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467d  cmp     ebx, eax
0x18000467f  jnz     short loc_1800046A1
0x180004681  mov     eax, 1
0x180004686  add     rsp, 30h
0x18000468a  pop     rbx
0x18000468b  retn
0x18000468c  mov     rax, [rsp+38h+arg_20]
0x180004691  mov     qword ptr [rax], 9
0x180004698  mov     dword ptr [rax+8], 1
0x18000469f  jmp     short loc_1800046BA
0x1800046a1  mov     rcx, [rsp+38h+arg_20]
0x1800046a6  mov     eax, [rsp+38h+arg_10]
0x1800046aa  mov     dword ptr [rcx], 4
0x1800046b0  mov     [rcx+4], eax
0x1800046b3  mov     dword ptr [rcx+8], 1
0x1800046ba  xor     eax, eax
0x1800046bc  jmp     short loc_180004686
```
