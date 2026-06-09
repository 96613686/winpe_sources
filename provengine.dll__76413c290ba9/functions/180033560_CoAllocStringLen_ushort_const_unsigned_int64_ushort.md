# CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180033560`
- end: `0x1800335e6`
- name: `?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z`
- size: `134`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033784`
- `0x18003795c`

## callees

- `0x18001fdec`
- `0x180033560`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003359e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003359e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoAllocStringLen(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 **a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 **v9; // [rsp+20h] [rbp-28h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-20h]
  unsigned int v11; // [rsp+30h] [rbp-18h]

  v3 = a2 + 1;
  *a3 = 0;
  if ( a2 + 1 >= a2 && is_mul_ok(v3, 2u) )
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v3);
    *a3 = v6;
    v7 = v6 == 0 ? 0x8007000E : 0;
    if ( v6 )
      StringCchCopyNExW(v6, v3, 0, a2, v9, v10, v11);
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x180033560  mov     [rsp+arg_8], rbx
0x180033565  mov     [rsp+arg_10], rsi
0x18003356a  push    rdi
0x18003356b  sub     rsp, 40h
0x18003356f  lea     rsi, [rdx+1]
0x180033573  mov     qword ptr [r8], 0
0x18003357a  mov     rbx, r8
0x18003357d  mov     rdi, rdx
0x180033580  cmp     rsi, rdx
0x180033583  jb      short loc_1800335CF
0x180033585  mov     eax, 2
0x18003358a  mov     [rsp+48h+arg_0], 0
0x180033593  mul     rsi
0x180033596  test    rdx, rdx
0x180033599  jnz     short loc_1800335CF
0x18003359b  mov     rcx, rax; cb
0x18003359e  call    cs:__imp_CoTaskMemAlloc
0x1800335a4  mov     [rbx], rax
0x1800335a7  mov     rcx, rax
0x1800335aa  neg     rcx
0x1800335ad  sbb     ebx, ebx
0x1800335af  not     ebx
0x1800335b1  and     ebx, 8007000Eh
0x1800335b7  test    rax, rax
0x1800335ba  jz      short loc_1800335D4
0x1800335bc  mov     r9, rdi; unsigned __int64
0x1800335bf  xor     r8d, r8d; unsigned __int16 *
0x1800335c2  mov     rdx, rsi; unsigned __int64
0x1800335c5  mov     rcx, rax; unsigned __int16 *
0x1800335c8  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800335cd  jmp     short loc_1800335D4
0x1800335cf  mov     ebx, 80070216h
0x1800335d4  mov     rsi, [rsp+48h+arg_10]
0x1800335d9  mov     eax, ebx
0x1800335db  mov     rbx, [rsp+48h+arg_8]
0x1800335e0  add     rsp, 40h
0x1800335e4  pop     rdi
0x1800335e5  retn
```
