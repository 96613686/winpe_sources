# MarshalExceptionPointers(_MINIDUMP_STATE *,_MINIDUMP_EXCEPTION_INFORMATION64 const *,_EXCEPTION_INFO *)

- ea: `0x180008738`
- end: `0x180008939`
- name: `?MarshalExceptionPointers@@YAJPEAU_MINIDUMP_STATE@@PEBU_MINIDUMP_EXCEPTION_INFORMATION64@@PEAU_EXCEPTION_INFO@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, const struct _MINIDUMP_EXCEPTION_INFORMATION64 *, struct _EXCEPTION_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007234`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180008738`
- `0x18002c010`

## string_xrefs

- `0x1800087b9`: `MarshalExceptionPointers.ExRecord.Read(0x%I64x, 0x%x) failed, 0x%08x`
- `0x1800088ee`: `MarshalExceptionPointers.CxRecord.Read(0x%I64x, 0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall MarshalExceptionPointers(
        struct _MINIDUMP_STATE *a1,
        const struct _MINIDUMP_EXCEPTION_INFORMATION64 *a2,
        struct _EXCEPTION_INFO *a3)
{
  __int64 v3; // r14
  __int64 v5; // r15
  unsigned int v8; // r14d
  __int64 v10; // rcx
  __int128 v11; // xmm1
  __int64 v12; // rax
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // [rsp+20h] [rbp-99h]
  __int128 v21; // [rsp+40h] [rbp-79h] BYREF
  _OWORD v22[8]; // [rsp+50h] [rbp-69h]
  __int64 v23; // [rsp+D0h] [rbp+17h]

  v3 = *((_QWORD *)a1 + 2);
  v5 = 80;
  if ( *((_DWORD *)a1 + 38) == 80 )
  {
    memset_0(&v21, 0, 0x50u);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONG64, __int128 *, int))(*(_QWORD *)v3 + 240LL))(
           v3,
           *(_QWORD *)a1,
           a2->ExceptionRecord,
           &v21,
           80);
    if ( v8 )
    {
LABEL_3:
      (*(void (__fastcall **)(_QWORD, __int64, const char *, ULONG64, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "MarshalExceptionPointers.ExRecord.Read(0x%I64x, 0x%x) failed, 0x%08x",
        a2->ExceptionRecord,
        v5,
        v8);
      return v8;
    }
    v10 = 0;
    *(_QWORD *)((char *)a3 + 4) = v21;
    *(_QWORD *)((char *)a3 + 12) = SDWORD2(v21);
    *(_QWORD *)((char *)a3 + 20) = SHIDWORD(v21);
    *((_DWORD *)a3 + 7) = v22[0];
    do
    {
      *(_QWORD *)((char *)a3 + 8 * v10 + 36) = *((int *)v22 + v10 + 1);
      ++v10;
    }
    while ( v10 != 15 );
  }
  else
  {
    v5 = 152;
    memset_0(&v21, 0, 0x98u);
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONG64, __int128 *, int))(*(_QWORD *)v3 + 240LL))(
           v3,
           *(_QWORD *)a1,
           a2->ExceptionRecord,
           &v21,
           152);
    if ( v8 )
      goto LABEL_3;
    v11 = v22[0];
    v12 = v23;
    *(_OWORD *)((char *)a3 + 4) = v21;
    v13 = v22[1];
    *(_OWORD *)((char *)a3 + 20) = v11;
    v14 = v22[2];
    *(_OWORD *)((char *)a3 + 36) = v13;
    v15 = v22[3];
    *(_OWORD *)((char *)a3 + 52) = v14;
    v16 = v22[4];
    *(_OWORD *)((char *)a3 + 68) = v15;
    v17 = v22[5];
    *(_OWORD *)((char *)a3 + 84) = v16;
    v18 = v22[6];
    *(_OWORD *)((char *)a3 + 100) = v17;
    v19 = v22[7];
    *(_OWORD *)((char *)a3 + 116) = v18;
    *(_OWORD *)((char *)a3 + 132) = v19;
    *(_QWORD *)((char *)a3 + 148) = v12;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, ULONG64, _QWORD, _DWORD))(**((_QWORD **)a1 + 2) + 240LL))(
         *((_QWORD *)a1 + 2),
         *(_QWORD *)a1,
         a2->ContextRecord,
         *((_QWORD *)a3 + 20),
         *((_DWORD *)a3 + 42));
  if ( v8 )
  {
    LODWORD(v20) = *((_DWORD *)a3 + 42);
    (*(void (__fastcall **)(_QWORD, __int64, const char *, ULONG64, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "MarshalExceptionPointers.CxRecord.Read(0x%I64x, 0x%x) failed, 0x%08x",
      a2->ContextRecord,
      v20,
      v8);
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180008738  mov     [rsp-8+arg_18], rbx
0x18000873d  push    rbp
0x18000873e  push    rsi
0x18000873f  push    rdi
0x180008740  push    r14
0x180008742  push    r15
0x180008744  lea     rbp, [rsp-37h]
0x180008749  sub     rsp, 0F0h
0x180008750  mov     rax, cs:__security_cookie
0x180008757  xor     rax, rsp
0x18000875a  mov     [rbp+57h+var_30], rax
0x18000875e  mov     r14, [rcx+10h]
0x180008762  mov     rsi, rdx
0x180008765  xor     edx, edx; Val
0x180008767  mov     r15d, 50h ; 'P'
0x18000876d  mov     rbx, r8
0x180008770  mov     rdi, rcx
0x180008773  cmp     [rcx+98h], r15d
0x18000877a  jnz     loc_180008823
0x180008780  mov     r8d, r15d; Size
0x180008783  lea     rcx, [rbp+57h+var_D0]; void *
0x180008787  call    memset_0
0x18000878c  mov     rax, [r14]
0x18000878f  lea     r9, [rbp+57h+var_D0]
0x180008793  mov     r8, [rsi+4]
0x180008797  mov     rcx, r14
0x18000879a  mov     rdx, [rdi]
0x18000879d  mov     dword ptr [rsp+110h+var_F0], r15d
0x1800087a2  mov     rax, [rax+0F0h]
0x1800087a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ae  mov     r14d, eax
0x1800087b1  test    eax, eax
0x1800087b3  jz      short loc_1800087E7
0x1800087b5  mov     rcx, [rdi+28h]
0x1800087b9  lea     r8, aMarshalexcepti_0; "MarshalExceptionPointers.ExRecord.Read("...
0x1800087c0  mov     r9, [rsi+4]
0x1800087c4  mov     [rsp+110h+var_E8], r14d
0x1800087c9  mov     [rsp+110h+var_F0], r15
0x1800087ce  mov     rdx, [rcx]
0x1800087d1  mov     rax, [rdx+8]
0x1800087d5  mov     edx, 4
0x1800087da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087df  mov     eax, r14d
0x1800087e2  jmp     loc_180008916
0x1800087e7  mov     eax, dword ptr [rbp+57h+var_D0]
0x1800087ea  xor     ecx, ecx
0x1800087ec  mov     [rbx+4], eax
0x1800087ef  mov     eax, dword ptr [rbp+57h+var_D0+4]
0x1800087f2  mov     [rbx+8], eax
0x1800087f5  movsxd  rax, dword ptr [rbp+57h+var_D0+8]
0x1800087f9  mov     [rbx+0Ch], rax
0x1800087fd  movsxd  rax, dword ptr [rbp+57h+var_D0+0Ch]
0x180008801  mov     [rbx+14h], rax
0x180008805  mov     eax, dword ptr [rbp+57h+var_C0]
0x180008808  mov     [rbx+1Ch], eax
0x18000880b  movsxd  rax, dword ptr [rbp+rcx*4+57h+var_C0+4]
0x180008810  mov     [rbx+rcx*8+24h], rax
0x180008815  inc     rcx
0x180008818  cmp     rcx, 0Fh
0x18000881c  jnz     short loc_18000880B
0x18000881e  jmp     loc_1800088B8
0x180008823  mov     r15d, 98h
0x180008829  lea     rcx, [rbp+57h+var_D0]; void *
0x18000882d  mov     r8d, r15d; Size
0x180008830  call    memset_0
0x180008835  mov     rax, [r14]
0x180008838  lea     r9, [rbp+57h+var_D0]
0x18000883c  mov     r8, [rsi+4]
0x180008840  mov     rcx, r14
0x180008843  mov     rdx, [rdi]
0x180008846  mov     dword ptr [rsp+110h+var_F0], r15d
0x18000884b  mov     rax, [rax+0F0h]
0x180008852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008857  mov     r14d, eax
0x18000885a  test    eax, eax
0x18000885c  jnz     loc_1800087B5
0x180008862  movaps  xmm0, [rbp+57h+var_D0]
0x180008866  movaps  xmm1, [rbp+57h+var_C0]
0x18000886a  mov     rax, [rbp+57h+var_40]
0x18000886e  movups  xmmword ptr [rbx+4], xmm0
0x180008872  movaps  xmm0, [rbp+57h+var_B0]
0x180008876  movups  xmmword ptr [rbx+14h], xmm1
0x18000887a  movaps  xmm1, [rbp+57h+var_A0]
0x18000887e  movups  xmmword ptr [rbx+24h], xmm0
0x180008882  movaps  xmm0, [rbp+57h+var_90]
0x180008886  movups  xmmword ptr [rbx+34h], xmm1
0x18000888a  movaps  xmm1, [rbp+57h+var_80]
0x18000888e  movups  xmmword ptr [rbx+44h], xmm0
0x180008892  movaps  xmm0, [rbp+57h+var_70]
0x180008896  movups  xmmword ptr [rbx+54h], xmm1
0x18000889a  movaps  xmm1, [rbp+57h+var_60]
0x18000889e  movups  xmmword ptr [rbx+64h], xmm0
0x1800088a2  movaps  xmm0, [rbp+57h+var_50]
0x1800088a6  movups  xmmword ptr [rbx+74h], xmm1
0x1800088aa  movups  xmmword ptr [rbx+84h], xmm0
0x1800088b1  mov     [rbx+94h], rax
0x1800088b8  mov     edx, [rbx+0A8h]
0x1800088be  mov     rcx, [rdi+10h]
0x1800088c2  mov     r9, [rbx+0A0h]
0x1800088c9  mov     r8, [rsi+0Ch]
0x1800088cd  mov     dword ptr [rsp+110h+var_F0], edx
0x1800088d1  mov     rax, [rcx]
0x1800088d4  mov     rdx, [rdi]
0x1800088d7  mov     rax, [rax+0F0h]
0x1800088de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e3  mov     r14d, eax
0x1800088e6  test    eax, eax
0x1800088e8  jz      short loc_180008914
0x1800088ea  mov     rcx, [rdi+28h]
0x1800088ee  lea     r8, aMarshalexcepti; "MarshalExceptionPointers.CxRecord.Read("...
0x1800088f5  mov     r9, [rsi+0Ch]
0x1800088f9  mov     [rsp+110h+var_E8], r14d
0x1800088fe  mov     rdx, [rcx]
0x180008901  mov     rax, [rdx+8]
0x180008905  mov     edx, [rbx+0A8h]
0x18000890b  mov     dword ptr [rsp+110h+var_F0], edx
0x18000890f  jmp     loc_1800087D5
0x180008914  xor     eax, eax
0x180008916  mov     rcx, [rbp+57h+var_30]
0x18000891a  xor     rcx, rsp; StackCookie
0x18000891d  call    __security_check_cookie
0x180008922  mov     rbx, [rsp+110h+arg_18]
0x18000892a  add     rsp, 0F0h
0x180008931  pop     r15
0x180008933  pop     r14
0x180008935  pop     rdi
0x180008936  pop     rsi
0x180008937  pop     rbp
0x180008938  retn
```
