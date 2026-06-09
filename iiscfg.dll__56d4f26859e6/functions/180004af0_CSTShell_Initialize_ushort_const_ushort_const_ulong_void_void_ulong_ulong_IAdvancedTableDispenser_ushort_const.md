# CSTShell::Initialize(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,IAdvancedTableDispenser *,ushort const *,void *,IInterceptorPlugin *,ISimplePlugin *,ISimplePlugin *,void * *)

- ea: `0x180004af0`
- end: `0x180004ccc`
- name: `?Initialize@CSTShell@@UEAAJPEBG0KPEAX1KKPEAUIAdvancedTableDispenser@@01PEAUIInterceptorPlugin@@PEAUISimplePlugin@@4PEAPEAX@Z`
- size: `476`
- prototype: `__int64 __fastcall(CSTShell *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, void *, unsigned int, unsigned int, struct IAdvancedTableDispenser *, const unsigned __int16 *, void *, struct IInterceptorPlugin *, struct ISimplePlugin *, struct ISimplePlugin *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004af0`
- `0x180030010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x180004b51`
- `ATL!__imp_AtlComPtrAssign` at `0x180004b51`

## pseudocode

```c
__int64 __fastcall CSTShell::Initialize(
        CSTShell *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        void *a5,
        void *a6,
        unsigned int a7,
        unsigned int a8,
        struct IAdvancedTableDispenser *a9,
        const unsigned __int16 *a10,
        void *a11,
        struct IInterceptorPlugin *a12,
        struct ISimplePlugin *a13,
        struct ISimplePlugin *a14,
        void **a15)
{
  unsigned int v18; // r15d
  __int64 result; // rax
  char *v20; // rbp

  if ( __PAIR128__((unsigned __int64)a13, (unsigned __int64)a12) == 0 && !a14 )
    return 2147942487LL;
  AtlComPtrAssign((char *)this + 40, a9);
  if ( a12 )
  {
    v18 = (*(__int64 (__fastcall **)(struct IInterceptorPlugin *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, void *, void *, unsigned int, unsigned int, struct IAdvancedTableDispenser *, const unsigned __int16 *, void *, char *))(*(_QWORD *)a12 + 24LL))(
            a12,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            a10,
            a11,
            (char *)this + 48);
    if ( (int)(v18 + 0x80000000) >= 0 && v18 != -2145318895 )
      return v18;
    goto LABEL_10;
  }
  if ( !a11 )
    return 2147942487LL;
  v18 = 0;
  *((_QWORD *)this + 6) = a11;
LABEL_10:
  v20 = (char *)this - 16;
  result = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 6))(
             *((_QWORD *)this + 6),
             &IID_ISimpleTableController,
             (char *)this + 56);
  if ( (int)result < 0 )
    return result;
  *((_QWORD *)this + 8) = a12;
  if ( a12 )
    (*(void (__fastcall **)(struct IInterceptorPlugin *))(*(_QWORD *)a12 + 8LL))(a12);
  *((_QWORD *)this + 9) = a13;
  if ( a13 )
    (*(void (__fastcall **)(struct ISimplePlugin *))(*(_QWORD *)a13 + 8LL))(a13);
  *((_QWORD *)this + 10) = a14;
  if ( a14 )
    (*(void (__fastcall **)(struct ISimplePlugin *))(*(_QWORD *)a14 + 8LL))(a14);
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = a3;
  *((_DWORD *)this + 8) = a8;
  _InterlockedIncrement((volatile signed __int32 *)this + 3);
  *a15 = v20;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 8LL))((char *)this - 16);
  return v18;
}

```

## disassembly

```asm
0x180004af0  mov     [rsp+arg_0], rbx
0x180004af5  mov     [rsp+arg_18], r9d
0x180004afa  mov     [rsp+arg_8], rdx
0x180004aff  push    rbp
0x180004b00  push    rsi
0x180004b01  push    rdi
0x180004b02  push    r12
0x180004b04  push    r13
0x180004b06  push    r14
0x180004b08  push    r15
0x180004b0a  sub     rsp, 70h
0x180004b0e  mov     rdi, [rsp+0A8h+arg_58]
0x180004b16  mov     r13, r8
0x180004b19  mov     rsi, [rsp+0A8h+arg_68]
0x180004b21  mov     r15, rdx
0x180004b24  mov     r14, [rsp+0A8h+arg_60]
0x180004b2c  mov     rbx, rcx
0x180004b2f  test    rdi, rdi
0x180004b32  jnz     short loc_180004B42
0x180004b34  test    r14, r14
0x180004b37  jnz     short loc_180004B42
0x180004b39  test    rsi, rsi
0x180004b3c  jz      loc_180004C03
0x180004b42  mov     rbp, [rsp+0A8h+arg_40]
0x180004b4a  add     rcx, 28h ; '('
0x180004b4e  mov     rdx, rbp
0x180004b51  call    cs:__imp_AtlComPtrAssign
0x180004b57  mov     r12d, [rsp+0A8h+arg_38]
0x180004b5f  test    rdi, rdi
0x180004b62  jz      loc_180004BF6
0x180004b68  mov     rax, [rdi]
0x180004b6b  lea     rcx, [rbx+30h]
0x180004b6f  mov     r9d, [rsp+0A8h+arg_18]
0x180004b77  mov     r8, r13
0x180004b7a  mov     [rsp+0A8h+var_50], rcx
0x180004b7f  mov     rdx, r15
0x180004b82  mov     rcx, [rsp+0A8h+arg_48]
0x180004b8a  mov     r10, [rax+18h]
0x180004b8e  mov     rax, [rsp+0A8h+arg_50]
0x180004b96  mov     [rsp+0A8h+var_58], rax
0x180004b9b  mov     rax, r10
0x180004b9e  mov     [rsp+0A8h+var_60], rcx
0x180004ba3  mov     ecx, [rsp+0A8h+arg_30]
0x180004baa  mov     [rsp+0A8h+var_68], rbp
0x180004baf  mov     [rsp+0A8h+var_70], r12d
0x180004bb4  mov     [rsp+0A8h+var_78], ecx
0x180004bb8  mov     rcx, [rsp+0A8h+arg_28]
0x180004bc0  mov     [rsp+0A8h+var_80], rcx
0x180004bc5  mov     rcx, [rsp+0A8h+arg_20]
0x180004bcd  mov     [rsp+0A8h+var_88], rcx
0x180004bd2  mov     rcx, rdi
0x180004bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bda  mov     ecx, 80000000h
0x180004bdf  mov     r15d, eax
0x180004be2  add     eax, ecx
0x180004be4  test    ecx, eax
0x180004be6  jnz     short loc_180004C14
0x180004be8  cmp     r15d, 80210811h
0x180004bef  jz      short loc_180004C14
0x180004bf1  jmp     loc_180004CB1
0x180004bf6  mov     rax, [rsp+0A8h+arg_50]
0x180004bfe  test    rax, rax
0x180004c01  jnz     short loc_180004C0D
0x180004c03  mov     eax, 80070057h
0x180004c08  jmp     loc_180004CB4
0x180004c0d  xor     r15d, r15d
0x180004c10  mov     [rbx+30h], rax
0x180004c14  lea     rbp, [rbx-10h]
0x180004c18  mov     rcx, [rbp+40h]
0x180004c1c  lea     r8, [rbx+38h]
0x180004c20  lea     rdx, IID_ISimpleTableController
0x180004c27  mov     rax, [rcx]
0x180004c2a  mov     rax, [rax]
0x180004c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c32  test    eax, eax
0x180004c34  js      short loc_180004CB4
0x180004c36  mov     [rbx+40h], rdi
0x180004c3a  test    rdi, rdi
0x180004c3d  jz      short loc_180004C4E
0x180004c3f  mov     rax, [rdi]
0x180004c42  mov     rcx, rdi
0x180004c45  mov     rax, [rax+8]
0x180004c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c4e  mov     [rbx+48h], r14
0x180004c52  test    r14, r14
0x180004c55  jz      short loc_180004C66
0x180004c57  mov     rax, [r14]
0x180004c5a  mov     rcx, r14
0x180004c5d  mov     rax, [rax+8]
0x180004c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c66  mov     [rbx+50h], rsi
0x180004c6a  test    rsi, rsi
0x180004c6d  jz      short loc_180004C7E
0x180004c6f  mov     rax, [rsi]
0x180004c72  mov     rcx, rsi
0x180004c75  mov     rax, [rax+8]
0x180004c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c7e  mov     rax, [rsp+0A8h+arg_8]
0x180004c86  mov     [rbx+10h], rax
0x180004c8a  mov     [rbx+18h], r13
0x180004c8e  mov     [rbx+20h], r12d
0x180004c92  lock inc dword ptr [rbx+0Ch]
0x180004c96  mov     rdx, [rsp+0A8h+arg_70]
0x180004c9e  mov     rcx, rbp
0x180004ca1  mov     [rdx], rbp
0x180004ca4  mov     rdx, [rbp+0]
0x180004ca8  mov     rax, [rdx+8]
0x180004cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb1  mov     eax, r15d
0x180004cb4  mov     rbx, [rsp+0A8h+arg_0]
0x180004cbc  add     rsp, 70h
0x180004cc0  pop     r15
0x180004cc2  pop     r14
0x180004cc4  pop     r13
0x180004cc6  pop     r12
0x180004cc8  pop     rdi
0x180004cc9  pop     rsi
0x180004cca  pop     rbp
0x180004ccb  retn
```
