# GenExecuteIncludeThreadCallback(_MINIDUMP_STATE *,ulong,ulong *)

- ea: `0x1800196fc`
- end: `0x1800197cb`
- name: `?GenExecuteIncludeThreadCallback@@YAHPEAU_MINIDUMP_STATE@@KPEAK@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ad48`

## callees

- `0x1800021f4`
- `0x1800196fc`
- `0x18001a518`
- `0x18002c010`

## string_xrefs

- `0x180019795`: `Thread(0x%x) will not be included`

## pseudocode

```c
__int64 __fastcall GenExecuteIncludeThreadCallback(struct _MINIDUMP_STATE *a1, unsigned int a2, unsigned int *a3)
{
  unsigned int (__fastcall *v6)(__int64, int *, unsigned int *); // rax
  __int64 v7; // rcx
  unsigned int v9[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+40h] [rbp-C0h]
  __int128 v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  __int64 v14; // [rsp+74h] [rbp-8Ch]
  int v15; // [rsp+7Ch] [rbp-84h]
  unsigned int v16; // [rsp+80h] [rbp-80h]
  _BYTE v17[1324]; // [rsp+84h] [rbp-7Ch] BYREF

  memset_0(v17, 0, 0x50Cu);
  v12 = 0;
  *(_OWORD *)v9 = 0;
  v10 = 0;
  v11 = 0;
  GenGetDefaultWriteFlags(a1, v9, a3);
  v6 = (unsigned int (__fastcall *)(__int64, int *, unsigned int *))*((_QWORD *)a1 + 8);
  if ( v6 )
  {
    v14 = *(_QWORD *)a1;
    v13 = *((_DWORD *)a1 + 2);
    v9[0] = *a3;
    v7 = *((_QWORD *)a1 + 10);
    v15 = 3;
    v16 = a2;
    if ( !v6(v7, &v13, v9) )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        1,
        "Thread(0x%x) will not be included",
        a2);
      return 0;
    }
    *a3 &= v9[0];
  }
  return 1;
}

```

## disassembly

```asm
0x1800196fc  push    rbp
0x1800196fe  push    rbx
0x1800196ff  push    rsi
0x180019700  push    rdi
0x180019701  lea     rbp, [rsp-498h]
0x180019709  sub     rsp, 598h
0x180019710  mov     rbx, r8
0x180019713  mov     esi, edx
0x180019715  mov     rdi, rcx
0x180019718  xor     edx, edx; Val
0x18001971a  mov     r8d, 50Ch; Size
0x180019720  lea     rcx, [rbp+4B0h+var_52C]; void *
0x180019724  call    memset_0
0x180019729  xorps   xmm0, xmm0
0x18001972c  lea     rdx, [rsp+5B0h+var_580]; unsigned int *
0x180019731  xor     eax, eax
0x180019733  mov     r8, rbx; unsigned int *
0x180019736  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x180019739  mov     [rsp+5B0h+var_550], eax
0x18001973d  movups  xmmword ptr [rsp+5B0h+var_580], xmm0
0x180019742  movups  [rsp+5B0h+var_570], xmm0
0x180019747  movups  [rsp+5B0h+var_560], xmm0
0x18001974c  call    ?GenGetDefaultWriteFlags@@YAXPEAU_MINIDUMP_STATE@@PEAK1@Z; GenGetDefaultWriteFlags(_MINIDUMP_STATE *,ulong *,ulong *)
0x180019751  mov     rax, [rdi+40h]
0x180019755  test    rax, rax
0x180019758  jz      short loc_1800197BA
0x18001975a  mov     rcx, [rdi]
0x18001975d  lea     r8, [rsp+5B0h+var_580]
0x180019762  mov     [rsp+5B0h+var_53C], rcx
0x180019767  lea     rdx, [rsp+5B0h+var_540]
0x18001976c  mov     ecx, [rdi+8]
0x18001976f  mov     [rsp+5B0h+var_540], ecx
0x180019773  mov     ecx, [rbx]
0x180019775  mov     [rsp+5B0h+var_580], ecx
0x180019779  mov     rcx, [rdi+50h]
0x18001977d  mov     [rsp+5B0h+var_534], 3
0x180019785  mov     [rbp+4B0h+var_530], esi
0x180019788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001978d  test    eax, eax
0x18001978f  jnz     short loc_1800197B4
0x180019791  mov     rcx, [rdi+28h]
0x180019795  lea     r8, aThread0xXWillN; "Thread(0x%x) will not be included"
0x18001979c  mov     r9d, esi
0x18001979f  mov     edx, 1
0x1800197a4  mov     rax, [rcx]
0x1800197a7  mov     rax, [rax+8]
0x1800197ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197b0  xor     eax, eax
0x1800197b2  jmp     short loc_1800197BF
0x1800197b4  mov     eax, [rsp+5B0h+var_580]
0x1800197b8  and     [rbx], eax
0x1800197ba  mov     eax, 1
0x1800197bf  add     rsp, 598h
0x1800197c6  pop     rdi
0x1800197c7  pop     rsi
0x1800197c8  pop     rbx
0x1800197c9  pop     rbp
0x1800197ca  retn
```
