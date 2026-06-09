# CADMCOMW::DeleteAllData(ulong,ushort const *,ulong,ulong)

- ea: `0x180003ca0`
- end: `0x180003dc5`
- name: `?DeleteAllData@CADMCOMW@@UEAAJKPEBGKK@Z`
- size: `293`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x180003ca0`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteAllData(
        CADMCOMW *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  signed int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v13; // [rsp+60h] [rbp-58h] BYREF
  int v14; // [rsp+64h] [rbp-54h] BYREF
  int v15; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v16[9]; // [rsp+70h] [rbp-48h] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  if ( a5 < 6 )
  {
    v9 = CADMCOMW::LookupAndAccessCheck(this, a2, &v13, (__int64)a3, 0, 2, 0, 0, v16, &v14, (__int64)&v15);
    if ( v9 >= 0 )
    {
      v10 = *((_QWORD *)this + 101);
      if ( v10 && v14 == 1 )
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(*(_QWORD *)v10 + 120LL))(
                v10,
                v13,
                a3,
                a4,
                a5);
      else
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(**((_QWORD **)this + 4)
                                                                                                  + 232LL))(
                *((_QWORD *)this + 4),
                v13,
                a3,
                a4,
                a5);
      v9 = v11;
      if ( v11 >= 0 )
        v9 = 0;
    }
    if ( v15 )
      CADMCOMW::AuditAccess(this, 0x119Bu, v9, a2, a3, 0, 0, 0, 0, 0, 0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003ca0  push    rbx
0x180003ca2  push    rbp
0x180003ca3  push    rsi
0x180003ca4  push    rdi
0x180003ca5  push    r12
0x180003ca7  push    r14
0x180003ca9  push    r15
0x180003cab  sub     rsp, 80h
0x180003cb2  mov     ebp, [rsp+0B8h+arg_20]
0x180003cb9  xor     r12d, r12d
0x180003cbc  mov     [rsp+0B8h+var_58], r12d
0x180003cc1  mov     r15d, r9d
0x180003cc4  mov     [rsp+0B8h+var_50], r12d
0x180003cc9  mov     rsi, r8
0x180003ccc  mov     [rsp+0B8h+var_54], r12d
0x180003cd1  mov     r14d, edx
0x180003cd4  mov     rdi, rcx
0x180003cd7  cmp     ebp, 6
0x180003cda  jb      short loc_180003CE6
0x180003cdc  mov     ebx, 80070057h
0x180003ce1  jmp     loc_180003DB1
0x180003ce6  lea     rax, [rsp+0B8h+var_50]
0x180003ceb  mov     r9, rsi
0x180003cee  mov     [rsp+0B8h+var_68], rax
0x180003cf3  lea     r8, [rsp+0B8h+var_58]
0x180003cf8  lea     rax, [rsp+0B8h+var_54]
0x180003cfd  mov     [rsp+0B8h+var_70], rax
0x180003d02  lea     rax, [rsp+0B8h+var_48]
0x180003d07  mov     [rsp+0B8h+var_78], rax
0x180003d0c  mov     qword ptr [rsp+0B8h+var_80], r12
0x180003d11  mov     [rsp+0B8h+var_88], r12
0x180003d16  mov     [rsp+0B8h+var_90], 2
0x180003d1e  mov     dword ptr [rsp+0B8h+var_98], r12d
0x180003d23  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180003d28  mov     ebx, eax
0x180003d2a  test    eax, eax
0x180003d2c  js      short loc_180003D74
0x180003d2e  mov     rcx, [rdi+328h]
0x180003d35  test    rcx, rcx
0x180003d38  jz      short loc_180003D4A
0x180003d3a  cmp     [rsp+0B8h+var_54], 1
0x180003d3f  jnz     short loc_180003D4A
0x180003d41  mov     rax, [rcx]
0x180003d44  mov     rax, [rax+78h]
0x180003d48  jmp     short loc_180003D58
0x180003d4a  mov     rcx, [rdi+20h]
0x180003d4e  mov     rax, [rcx]
0x180003d51  mov     rax, [rax+0E8h]
0x180003d58  mov     edx, [rsp+0B8h+var_58]
0x180003d5c  mov     r9d, r15d
0x180003d5f  mov     r8, rsi
0x180003d62  mov     dword ptr [rsp+0B8h+var_98], ebp
0x180003d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6b  mov     ebx, eax
0x180003d6d  test    eax, eax
0x180003d6f  js      short loc_180003D74
0x180003d71  mov     ebx, r12d
0x180003d74  cmp     [rsp+0B8h+var_50], r12d
0x180003d79  jz      short loc_180003DB1
0x180003d7b  mov     [rsp+0B8h+var_68], r12; unsigned __int16 *
0x180003d80  mov     r9d, r14d; unsigned int
0x180003d83  mov     [rsp+0B8h+var_70], r12; struct _METADATA_RECORD *
0x180003d88  mov     r8d, ebx; int
0x180003d8b  mov     [rsp+0B8h+var_78], r12; struct _METADATA_RECORD *
0x180003d90  mov     edx, 119Bh; unsigned int
0x180003d95  mov     [rsp+0B8h+var_80], r12d; unsigned int
0x180003d9a  mov     rcx, rdi; this
0x180003d9d  mov     [rsp+0B8h+var_88], r12; unsigned __int16 *
0x180003da2  mov     [rsp+0B8h+var_90], r12d; unsigned int
0x180003da7  mov     [rsp+0B8h+var_98], rsi; unsigned __int16 *
0x180003dac  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180003db1  mov     eax, ebx
0x180003db3  add     rsp, 80h
0x180003dba  pop     r15
0x180003dbc  pop     r14
0x180003dbe  pop     r12
0x180003dc0  pop     rdi
0x180003dc1  pop     rsi
0x180003dc2  pop     rbp
0x180003dc3  pop     rbx
0x180003dc4  retn
```
