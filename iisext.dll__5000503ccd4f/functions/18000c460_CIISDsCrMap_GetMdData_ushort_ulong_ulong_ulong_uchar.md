# CIISDsCrMap::GetMdData(ushort *,ulong,ulong,ulong *,uchar * *)

- ea: `0x18000c460`
- end: `0x18000c556`
- name: `?GetMdData@CIISDsCrMap@@QEAAJPEAGKKPEAKPEAPEAE@Z`
- size: `246`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000bd80`
- `0x18000c0ac`
- `0x18000cba0`
- `0x18000cdd8`

## callees

- `0x18000c460`
- `0x180012010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000c4dc`
- `KERNEL32!LocalAlloc` at `0x18000c4dc`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::GetMdData(
        CIISDsCrMap *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edx
  unsigned __int8 *v11; // rax
  __int64 v13; // rcx
  int v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+34h] [rbp-2Ch]
  int v16; // [rsp+3Ch] [rbp-24h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  unsigned __int8 *v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+50h] [rbp-10h]
  SIZE_T uBytes; // [rsp+80h] [rbp+20h] BYREF

  v16 = a4;
  v14 = a3;
  v8 = *((_QWORD *)this + 7);
  v15 = 0;
  v17 = 0;
  v19 = 0;
  LODWORD(uBytes) = 0;
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, int *, SIZE_T *))(*(_QWORD *)v8 + 80LL))(
         v8,
         *((unsigned int *)this + 16),
         a2,
         &v14,
         &uBytes);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *a5 = 0;
    *a6 = 0;
  }
  else if ( v9 == -2147024774 )
  {
    v11 = (unsigned __int8 *)LocalAlloc(0, (unsigned int)uBytes);
    *a6 = v11;
    if ( !v11 )
      return 2147942414LL;
    v13 = *((_QWORD *)this + 7);
    v18 = v11;
    LODWORD(v17) = uBytes;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, int *, SIZE_T *))(*(_QWORD *)v13 + 80LL))(
            v13,
            *((unsigned int *)this + 16),
            a2,
            &v14,
            &uBytes);
    *a5 = v17;
  }
  return v10;
}

```

## disassembly

```asm
0x18000c460  mov     [rsp-8+arg_0], rbx
0x18000c465  mov     [rsp-8+arg_8], rdi
0x18000c46a  push    rbp
0x18000c46b  mov     rbp, rsp
0x18000c46e  sub     rsp, 60h
0x18000c472  mov     rdi, rdx
0x18000c475  mov     [rbp+var_24], r9d
0x18000c479  mov     rbx, rcx
0x18000c47c  mov     [rbp+var_30], r8d
0x18000c480  mov     rcx, [rcx+38h]
0x18000c484  lea     rdx, [rbp+uBytes]
0x18000c488  mov     [rbp+var_2C], 0
0x18000c490  lea     r9, [rbp+var_30]
0x18000c494  mov     [rbp+var_20], 0
0x18000c49c  mov     r8, rdi
0x18000c49f  mov     [rbp+var_10], 0
0x18000c4a7  mov     dword ptr [rbp+uBytes], 0
0x18000c4ae  mov     [rbp+var_18], 0
0x18000c4b6  mov     rax, [rcx]
0x18000c4b9  mov     [rsp+60h+var_40], rdx
0x18000c4be  mov     edx, [rbx+40h]
0x18000c4c1  mov     rax, [rax+50h]
0x18000c4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ca  mov     edx, eax
0x18000c4cc  test    eax, eax
0x18000c4ce  jns     short loc_18000C52F
0x18000c4d0  cmp     eax, 8007007Ah
0x18000c4d5  jnz     short loc_18000C544
0x18000c4d7  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x18000c4da  xor     ecx, ecx; uFlags
0x18000c4dc  call    cs:__imp_LocalAlloc
0x18000c4e2  mov     rcx, [rbp+arg_28]
0x18000c4e6  mov     [rcx], rax
0x18000c4e9  test    rax, rax
0x18000c4ec  jnz     short loc_18000C4F5
0x18000c4ee  mov     eax, 8007000Eh
0x18000c4f3  jmp     short loc_18000C546
0x18000c4f5  mov     rcx, [rbx+38h]
0x18000c4f9  lea     rdx, [rbp+uBytes]
0x18000c4fd  mov     [rbp+var_18], rax
0x18000c501  lea     r9, [rbp+var_30]
0x18000c505  mov     eax, dword ptr [rbp+uBytes]
0x18000c508  mov     r8, rdi
0x18000c50b  mov     dword ptr [rbp+var_20], eax
0x18000c50e  mov     rax, [rcx]
0x18000c511  mov     [rsp+60h+var_40], rdx
0x18000c516  mov     edx, [rbx+40h]
0x18000c519  mov     rax, [rax+50h]
0x18000c51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c522  mov     rcx, [rbp+arg_20]
0x18000c526  mov     edx, eax
0x18000c528  mov     eax, dword ptr [rbp+var_20]
0x18000c52b  mov     [rcx], eax
0x18000c52d  jmp     short loc_18000C544
0x18000c52f  mov     rax, [rbp+arg_20]
0x18000c533  mov     dword ptr [rax], 0
0x18000c539  mov     rax, [rbp+arg_28]
0x18000c53d  mov     qword ptr [rax], 0
0x18000c544  mov     eax, edx
0x18000c546  mov     rbx, [rsp+60h+arg_0]
0x18000c54b  mov     rdi, [rsp+60h+arg_8]
0x18000c550  add     rsp, 60h
0x18000c554  pop     rbp
0x18000c555  retn
```
