# sfac_ReadCompositeInstructions(sfac_GHandle *,uchar const * *,ushort *)

- ea: `0x14004e2d8`
- end: `0x14004e34a`
- name: `?sfac_ReadCompositeInstructions@@YAHPEAUsfac_GHandle@@PEAPEBEPEAG@Z`
- size: `114`
- prototype: `__int64 __fastcall(struct sfac_GHandle *, const unsigned __int8 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400197e0`

## callees

- `0x14002926c`
- `0x14004e2d8`

## pseudocode

```c
__int64 __fastcall sfac_ReadCompositeInstructions(
        struct sfac_GHandle *a1,
        const unsigned __int8 **a2,
        unsigned __int16 *a3)
{
  unsigned __int8 *v4; // rcx
  unsigned __int64 v5; // rdi
  __int16 v6; // r9
  __int16 v7; // ax
  unsigned __int64 *v8; // rax
  bool v9; // cf
  unsigned __int8 *v11; // [rsp+30h] [rbp+8h] BYREF

  v4 = (unsigned __int8 *)*((_QWORD *)a1 + 3);
  v5 = *(unsigned int *)a1 + *((_QWORD *)a1 + 1);
  if ( (unsigned __int64)(v4 + 2) > v5 )
    return 5133;
  v6 = *v4;
  v7 = v4[1];
  v11 = v4 + 2;
  *a3 = v7 | (v6 << 8);
  *a2 = v4 + 2;
  v8 = (unsigned __int64 *)operator+=<unsigned char,unsigned short,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                             &v11,
                             *a3);
  v9 = v5 < *v8;
  *((_QWORD *)a1 + 3) = *v8;
  return v9 ? 0x140D : 0;
}

```

## disassembly

```asm
0x14004e2d8  mov     [rsp+arg_8], rbx
0x14004e2dd  push    rdi
0x14004e2de  sub     rsp, 20h
0x14004e2e2  mov     rbx, rcx
0x14004e2e5  mov     rcx, [rcx+18h]
0x14004e2e9  mov     r9d, [rbx]
0x14004e2ec  lea     r10, [rcx+2]
0x14004e2f0  mov     rdi, [rbx+8]
0x14004e2f4  add     rdi, r9
0x14004e2f7  cmp     r10, rdi
0x14004e2fa  ja      short loc_14004E343
0x14004e2fc  movzx   r9d, byte ptr [rcx]
0x14004e300  movzx   eax, byte ptr [rcx+1]
0x14004e304  lea     rcx, [rsp+28h+arg_0]
0x14004e309  shl     r9w, 8
0x14004e30e  or      r9w, ax
0x14004e312  mov     [rsp+28h+arg_0], r10
0x14004e317  mov     [r8], r9w
0x14004e31b  mov     [rdx], r10
0x14004e31e  movzx   edx, word ptr [r8]
0x14004e322  call    ??$?YEGV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEAEAEAPEAEV?$SafeInt@GV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar,ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar * &,SafeInt<ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14004e327  mov     rcx, [rax]
0x14004e32a  cmp     rdi, rcx
0x14004e32d  mov     [rbx+18h], rcx
0x14004e331  sbb     eax, eax
0x14004e333  and     eax, 140Dh
0x14004e338  mov     rbx, [rsp+28h+arg_8]
0x14004e33d  add     rsp, 20h
0x14004e341  pop     rdi
0x14004e342  retn
0x14004e343  mov     eax, 140Dh
0x14004e348  jmp     short loc_14004E338
```
