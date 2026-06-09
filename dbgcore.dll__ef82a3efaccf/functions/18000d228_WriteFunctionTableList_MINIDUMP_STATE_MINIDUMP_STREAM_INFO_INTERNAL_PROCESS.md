# WriteFunctionTableList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000d228`
- end: `0x18000d459`
- name: `?WriteFunctionTableList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x18000bcbc`
- `0x18000d228`
- `0x18001951c`
- `0x18002c010`

## string_xrefs

- `0x18000d426`: `WriteFunctionTableList.Seek(0x%x) failed, 0x%08x`
- `0x18000d3ff`: `WriteFunctionTableList.DumpTable.Write(0x%x) failed, 0x%08x`
- `0x18000d3f2`: `WriteFunctionTable.RawTable.Write(0x%x) failed, 0x%08x`
- `0x18000d3da`: `WriteFunctionTable.RawEntries.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteFunctionTableList(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  _QWORD *v3; // rsi
  unsigned int v5; // edx
  unsigned int v6; // r14d
  __int64 result; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // r12
  unsigned int v10; // r15d
  int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rcx
  const char *v14; // r8
  __int64 v15; // r9
  _DWORD v16[6]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+48h] [rbp-28h] BYREF
  __int128 v18; // [rsp+58h] [rbp-18h]

  v3 = (_QWORD *)((char *)a3 + 152);
  v17 = 0;
  v18 = 0;
  if ( (_QWORD *)*v3 == v3 )
    return 0;
  v5 = *((_DWORD *)a2 + 24);
  v16[2] = *((_DWORD *)a1 + 41);
  v16[3] = *((_DWORD *)a1 + 42);
  v16[4] = *((_DWORD *)a3 + 25);
  v6 = (v5 + 31) & 0xFFFFFFF8;
  v16[0] = 24;
  v16[1] = 32;
  v16[5] = v6 - (v5 + 24);
  result = WriteAtOffset(a1, v5, v16, 0x18u);
  if ( (_DWORD)result )
    return result;
  v8 = (_QWORD *)*v3;
  if ( (_QWORD *)*v3 == v3 )
    return 0;
  while ( !(unsigned int)GenCheckCancel(a1) )
  {
    v9 = (_QWORD *)*v8;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
            *((_QWORD *)a1 + 3),
            0,
            v6,
            0);
    if ( v10 )
    {
      v15 = v6;
      v14 = "WriteFunctionTableList.Seek(0x%x) failed, 0x%08x";
LABEL_16:
      (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        v14,
        v15,
        v10);
      return v10;
    }
    v17 = *((_OWORD *)v8 - 3);
    *(_QWORD *)&v18 = *(v8 - 4);
    DWORD2(v18) = *((_DWORD *)v8 - 6);
    v11 = v6 + 32 + *((_DWORD *)a1 + 41) + *((_DWORD *)a1 + 42) * *((_DWORD *)v8 - 6);
    v6 = (v11 + 7) & 0xFFFFFFF8;
    v12 = v6 - v11;
    v13 = *((_QWORD *)a1 + 3);
    HIDWORD(v18) = v12;
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v13 + 32LL))(v13, &v17, 32);
    if ( v10 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "WriteFunctionTableList.DumpTable.Write(0x%x) failed, 0x%08x");
      return v10;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
            *((_QWORD *)a1 + 3),
            *(v8 - 2),
            *((unsigned int *)a1 + 41));
    if ( v10 )
    {
      v15 = *((unsigned int *)a1 + 41);
      v14 = "WriteFunctionTable.RawTable.Write(0x%x) failed, 0x%08x";
      goto LABEL_16;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
            *((_QWORD *)a1 + 3),
            *(v8 - 1),
            (unsigned int)(*((_DWORD *)a1 + 42) * *((_DWORD *)v8 - 6)));
    if ( v10 )
    {
      v14 = "WriteFunctionTable.RawEntries.Write(0x%x) failed, 0x%08x";
      v15 = (unsigned int)(*((_DWORD *)a1 + 42) * *((_DWORD *)v8 - 6));
      goto LABEL_16;
    }
    v8 = v9;
    if ( v9 == v3 )
      return 0;
  }
  return 2147943623LL;
}

```

## disassembly

```asm
0x18000d228  push    rbp
0x18000d22a  push    rbx
0x18000d22b  push    rsi
0x18000d22c  push    rdi
0x18000d22d  push    r12
0x18000d22f  push    r14
0x18000d231  push    r15
0x18000d233  mov     rbp, rsp
0x18000d236  sub     rsp, 70h
0x18000d23a  mov     rax, cs:__security_cookie
0x18000d241  xor     rax, rsp
0x18000d244  mov     [rbp+var_8], rax
0x18000d248  xorps   xmm0, xmm0
0x18000d24b  lea     rsi, [r8+98h]
0x18000d252  mov     rbx, rcx
0x18000d255  movups  [rbp+var_28], xmm0
0x18000d259  movups  [rbp+var_18], xmm0
0x18000d25d  cmp     [rsi], rsi
0x18000d260  jz      loc_18000D3B9
0x18000d266  mov     eax, [rcx+0A4h]
0x18000d26c  mov     r9d, 18h; unsigned int
0x18000d272  mov     edx, [rdx+60h]; unsigned int
0x18000d275  mov     [rbp+var_38], eax
0x18000d278  mov     eax, [rcx+0A8h]
0x18000d27e  mov     [rbp+var_34], eax
0x18000d281  mov     eax, [r8+64h]
0x18000d285  lea     ecx, [rdx+18h]
0x18000d288  lea     r14d, [rcx+7]
0x18000d28c  mov     [rbp+var_30], eax
0x18000d28f  and     r14d, 0FFFFFFF8h
0x18000d293  mov     [rbp+var_40], r9d
0x18000d297  mov     eax, r14d
0x18000d29a  mov     [rbp+var_3C], 20h ; ' '
0x18000d2a1  sub     eax, ecx
0x18000d2a3  lea     r8, [rbp+var_40]; void *
0x18000d2a7  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000d2aa  mov     [rbp+var_2C], eax
0x18000d2ad  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000d2b2  test    eax, eax
0x18000d2b4  jnz     loc_18000D3BB
0x18000d2ba  mov     rdi, [rsi]
0x18000d2bd  cmp     rdi, rsi
0x18000d2c0  jz      loc_18000D3B9
0x18000d2c6  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000d2c9  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000d2ce  test    eax, eax
0x18000d2d0  jnz     loc_18000D44F
0x18000d2d6  mov     rcx, [rbx+18h]
0x18000d2da  xor     r9d, r9d
0x18000d2dd  mov     r12, [rdi]
0x18000d2e0  xor     edx, edx
0x18000d2e2  mov     r8d, r14d
0x18000d2e5  mov     rax, [rcx]
0x18000d2e8  mov     rax, [rax+18h]
0x18000d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2f1  mov     r15d, eax
0x18000d2f4  test    eax, eax
0x18000d2f6  jnz     loc_18000D423
0x18000d2fc  mov     rax, [rdi-30h]
0x18000d300  lea     r8d, [r15+20h]
0x18000d304  mov     qword ptr [rbp+var_28], rax
0x18000d308  lea     rdx, [rbp+var_28]
0x18000d30c  mov     rax, [rdi-28h]
0x18000d310  add     r14d, 20h ; ' '
0x18000d314  mov     qword ptr [rbp+var_28+8], rax
0x18000d318  mov     rax, [rdi-20h]
0x18000d31c  mov     qword ptr [rbp+var_18], rax
0x18000d320  mov     eax, [rdi-18h]
0x18000d323  mov     dword ptr [rbp+var_18+8], eax
0x18000d326  mov     ecx, [rdi-18h]
0x18000d329  imul    ecx, [rbx+0A8h]
0x18000d330  add     ecx, [rbx+0A4h]
0x18000d336  add     ecx, r14d
0x18000d339  lea     r14d, [rcx+7]
0x18000d33d  and     r14d, 0FFFFFFF8h
0x18000d341  mov     eax, r14d
0x18000d344  sub     eax, ecx
0x18000d346  mov     rcx, [rbx+18h]
0x18000d34a  mov     dword ptr [rbp+var_18+0Ch], eax
0x18000d34d  mov     rax, [rcx]
0x18000d350  mov     rax, [rax+20h]
0x18000d354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d359  mov     r15d, eax
0x18000d35c  test    eax, eax
0x18000d35e  jnz     loc_18000D3FB
0x18000d364  mov     rcx, [rbx+18h]
0x18000d368  mov     r8d, [rbx+0A4h]
0x18000d36f  mov     rdx, [rdi-10h]
0x18000d373  mov     rax, [rcx]
0x18000d376  mov     rax, [rax+20h]
0x18000d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37f  mov     r15d, eax
0x18000d382  test    eax, eax
0x18000d384  jnz     short loc_18000D3EB
0x18000d386  mov     rcx, [rbx+18h]
0x18000d38a  mov     r8d, [rdi-18h]
0x18000d38e  imul    r8d, [rbx+0A8h]
0x18000d396  mov     rdx, [rdi-8]
0x18000d39a  mov     rax, [rcx]
0x18000d39d  mov     rax, [rax+20h]
0x18000d3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a6  mov     r15d, eax
0x18000d3a9  test    eax, eax
0x18000d3ab  jnz     short loc_18000D3D6
0x18000d3ad  mov     rdi, r12
0x18000d3b0  cmp     r12, rsi
0x18000d3b3  jnz     loc_18000D2C6
0x18000d3b9  xor     eax, eax
0x18000d3bb  mov     rcx, [rbp+var_8]
0x18000d3bf  xor     rcx, rsp; StackCookie
0x18000d3c2  call    __security_check_cookie
0x18000d3c7  add     rsp, 70h
0x18000d3cb  pop     r15
0x18000d3cd  pop     r14
0x18000d3cf  pop     r12
0x18000d3d1  pop     rdi
0x18000d3d2  pop     rsi
0x18000d3d3  pop     rbx
0x18000d3d4  pop     rbp
0x18000d3d5  retn
0x18000d3d6  mov     r9d, [rdi-18h]
0x18000d3da  lea     r8, aWritefunctiont_1; "WriteFunctionTable.RawEntries.Write(0x%"...
0x18000d3e1  imul    r9d, [rbx+0A8h]
0x18000d3e9  jmp     short loc_18000D42D
0x18000d3eb  mov     r9d, [rbx+0A4h]
0x18000d3f2  lea     r8, aWritefunctiont; "WriteFunctionTable.RawTable.Write(0x%x)"...
0x18000d3f9  jmp     short loc_18000D42D
0x18000d3fb  mov     rcx, [rbx+28h]
0x18000d3ff  lea     r8, aWritefunctiont_0; "WriteFunctionTableList.DumpTable.Write("...
0x18000d406  mov     r9d, 20h ; ' '
0x18000d40c  mov     [rsp+70h+var_50], r15d
0x18000d411  mov     rax, [rcx]
0x18000d414  lea     edx, [r9-1Ch]
0x18000d418  mov     rax, [rax+8]
0x18000d41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d421  jmp     short loc_18000D447
0x18000d423  mov     r9d, r14d
0x18000d426  lea     r8, aWritefunctiont_2; "WriteFunctionTableList.Seek(0x%x) faile"...
0x18000d42d  mov     rcx, [rbx+28h]
0x18000d431  mov     edx, 4
0x18000d436  mov     [rsp+70h+var_50], r15d
0x18000d43b  mov     rax, [rcx]
0x18000d43e  mov     rax, [rax+8]
0x18000d442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d447  mov     eax, r15d
0x18000d44a  jmp     loc_18000D3BB
0x18000d44f  mov     eax, 800704C7h
0x18000d454  jmp     loc_18000D3BB
```
