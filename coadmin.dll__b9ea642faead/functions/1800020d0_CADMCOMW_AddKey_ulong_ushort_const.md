# CADMCOMW::AddKey(ulong,ushort const *)

- ea: `0x1800020d0`
- end: `0x1800021dd`
- name: `?AddKey@CADMCOMW@@UEAAJKPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800020d0`
- `0x18000238c`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::AddKey(CADMCOMW *this, unsigned int a2, unsigned __int16 *a3)
{
  signed int v6; // ebx
  __int64 v7; // rcx
  signed int v8; // eax
  int v10; // [rsp+60h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+A0h] [rbp+18h] BYREF
  int v13; // [rsp+A8h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  v10 = 0;
  if ( a3 && *a3 )
  {
    v6 = CADMCOMW::LookupAndAccessCheck(this, a2, &v12, (__int64)a3, 0, 1, 0, 0, &v11, &v13, (__int64)&v10);
    if ( v6 >= 0 )
    {
      v7 = *((_QWORD *)this + 101);
      if ( v7 && v13 == 1 )
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v7 + 72LL))(v7, v12, a3);
      else
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 56LL))(
               *((_QWORD *)this + 4),
               v12,
               a3);
      v6 = v8;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v10 )
    CADMCOMW::AuditAccess(this, 0x1194u, v6, a2, a3, 0, 0, 0, 0, 0, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800020d0  mov     r11, rsp
0x1800020d3  mov     [r11+8], rbx
0x1800020d7  mov     [r11+10h], rbp
0x1800020db  push    rsi
0x1800020dc  push    rdi
0x1800020dd  push    r14
0x1800020df  sub     rsp, 70h
0x1800020e3  xor     r14d, r14d
0x1800020e6  mov     rdi, r8
0x1800020e9  mov     [r11+18h], r14d
0x1800020ed  mov     ebp, edx
0x1800020ef  mov     [r11+20h], r14d
0x1800020f3  mov     rsi, rcx
0x1800020f6  mov     [r11-28h], r14d
0x1800020fa  test    r8, r8
0x1800020fd  jz      loc_180002184
0x180002103  cmp     [r8], r14w
0x180002107  jz      short loc_180002184
0x180002109  lea     rax, [r11-28h]
0x18000210d  mov     r9, r8
0x180002110  mov     [r11-38h], rax
0x180002114  lea     r8, [r11+18h]
0x180002118  lea     rax, [r11+20h]
0x18000211c  mov     [r11-40h], rax
0x180002120  lea     rax, [r11-20h]
0x180002124  mov     [r11-48h], rax
0x180002128  mov     [r11-50h], r14
0x18000212c  mov     [r11-58h], r14
0x180002130  mov     [rsp+88h+var_60], 1
0x180002138  mov     [r11-68h], r14d
0x18000213c  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180002141  mov     ebx, eax
0x180002143  test    eax, eax
0x180002145  js      short loc_180002189
0x180002147  mov     rcx, [rsi+328h]
0x18000214e  test    rcx, rcx
0x180002151  jz      short loc_180002166
0x180002153  cmp     [rsp+88h+arg_18], 1
0x18000215b  jnz     short loc_180002166
0x18000215d  mov     rax, [rcx]
0x180002160  mov     rax, [rax+48h]
0x180002164  jmp     short loc_180002171
0x180002166  mov     rcx, [rsi+20h]
0x18000216a  mov     rax, [rcx]
0x18000216d  mov     rax, [rax+38h]
0x180002171  mov     edx, [rsp+88h+arg_10]
0x180002178  mov     r8, rdi
0x18000217b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002180  mov     ebx, eax
0x180002182  jmp     short loc_180002189
0x180002184  mov     ebx, 80070057h
0x180002189  cmp     [rsp+88h+var_28], r14d
0x18000218e  jz      short loc_1800021C6
0x180002190  mov     [rsp+88h+var_38], r14; unsigned __int16 *
0x180002195  mov     r9d, ebp; unsigned int
0x180002198  mov     [rsp+88h+var_40], r14; struct _METADATA_RECORD *
0x18000219d  mov     r8d, ebx; int
0x1800021a0  mov     [rsp+88h+var_48], r14; struct _METADATA_RECORD *
0x1800021a5  mov     edx, 1194h; unsigned int
0x1800021aa  mov     [rsp+88h+var_50], r14d; unsigned int
0x1800021af  mov     rcx, rsi; this
0x1800021b2  mov     [rsp+88h+var_58], r14; unsigned __int16 *
0x1800021b7  mov     [rsp+88h+var_60], r14d; unsigned int
0x1800021bc  mov     [rsp+88h+var_68], rdi; unsigned __int16 *
0x1800021c1  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x1800021c6  lea     r11, [rsp+88h+var_18]
0x1800021cb  mov     eax, ebx
0x1800021cd  mov     rbx, [r11+20h]
0x1800021d1  mov     rbp, [r11+28h]
0x1800021d5  mov     rsp, r11
0x1800021d8  pop     r14
0x1800021da  pop     rdi
0x1800021db  pop     rsi
0x1800021dc  retn
```
