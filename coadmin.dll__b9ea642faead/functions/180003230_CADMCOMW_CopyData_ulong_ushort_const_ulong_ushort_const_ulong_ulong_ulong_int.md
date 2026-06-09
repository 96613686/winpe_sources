# CADMCOMW::CopyData(ulong,ushort const *,ulong,ushort const *,ulong,ulong,ulong,int)

- ea: `0x180003230`
- end: `0x1800033f5`
- name: `?CopyData@CADMCOMW@@UEAAJKPEBGK0KKKH@Z`
- size: `453`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x180003230`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CopyData(
        CADMCOMW *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  signed int v12; // ebx
  __int64 v13; // rcx
  signed int v14; // eax
  unsigned int v16; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v17; // [rsp+64h] [rbp-1Dh] BYREF
  int v18; // [rsp+68h] [rbp-19h] BYREF
  int v19; // [rsp+6Ch] [rbp-15h] BYREF
  int v20; // [rsp+70h] [rbp-11h] BYREF
  _DWORD v21[19]; // [rsp+74h] [rbp-Dh] BYREF

  v17 = 0;
  v16 = 0;
  v20 = 0;
  v21[0] = 0;
  v18 = 0;
  v19 = 0;
  if ( (a9 || (a6 & 1) == 0) && ((a6 & 2) == 0 || (a6 & 1) != 0) )
  {
    v12 = CADMCOMW::LookupAndAccessCheck(this, a2, &v17, (__int64)a3, 2u, a9 == 0 ? 2 : 0, 0, 0, 0, &v18, (__int64)&v20);
    if ( v12 >= 0 )
    {
      v12 = CADMCOMW::LookupAndAccessCheck(this, a4, &v16, (__int64)a5, 0, 2, 0, 0, 0, &v19, (__int64)v21);
      if ( v12 >= 0 )
      {
        v13 = *((_QWORD *)this + 101);
        if ( v13 && v18 == 1 && v19 == 1 )
          v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned int, unsigned int, unsigned int, int))(*(_QWORD *)v13 + 200LL))(
                  v13,
                  v17,
                  a3,
                  v16,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9);
        else
          v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned int, unsigned int, unsigned int, int))(**((_QWORD **)this + 4) + 248LL))(
                  *((_QWORD *)this + 4),
                  v17,
                  a3,
                  v16,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9);
        v12 = v14;
      }
    }
    if ( v20 || v21[0] )
      CADMCOMW::AuditAccess(this, 0x119Cu, v12, a2, a3, a4, a5, 0, 0, 0, 0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003230  mov     [rsp-8+arg_8], edx
0x180003234  push    rbp
0x180003235  push    rbx
0x180003236  push    rsi
0x180003237  push    rdi
0x180003238  push    r12
0x18000323a  push    r13
0x18000323c  push    r14
0x18000323e  push    r15
0x180003240  lea     rbp, [rsp-7]
0x180003245  sub     rsp, 88h
0x18000324c  mov     esi, [rbp+3Fh+arg_28]
0x18000324f  mov     r15, r8
0x180003252  mov     r12d, [rbp+3Fh+arg_40]
0x180003259  xor     r8d, r8d
0x18000325c  mov     eax, esi
0x18000325e  mov     [rbp+3Fh+var_5C], r8d
0x180003262  and     eax, 1
0x180003265  mov     [rbp+3Fh+var_60], r8d
0x180003269  mov     [rbp+3Fh+var_50], r8d
0x18000326d  mov     r13d, r9d
0x180003270  mov     [rbp+3Fh+var_4C], r8d
0x180003274  mov     rdi, rcx
0x180003277  mov     [rbp+3Fh+var_58], r8d
0x18000327b  mov     [rbp+3Fh+var_54], r8d
0x18000327f  test    r12d, r12d
0x180003282  jnz     short loc_180003288
0x180003284  test    eax, eax
0x180003286  jnz     short loc_180003292
0x180003288  test    sil, 2
0x18000328c  jz      short loc_18000329C
0x18000328e  test    eax, eax
0x180003290  jnz     short loc_18000329C
0x180003292  mov     ebx, 80070057h
0x180003297  jmp     loc_1800033DF
0x18000329c  mov     eax, r12d
0x18000329f  mov     r9, r15
0x1800032a2  neg     eax
0x1800032a4  lea     rax, [rbp+3Fh+var_50]
0x1800032a8  mov     [rsp+0C0h+var_70], rax
0x1800032ad  sbb     ecx, ecx
0x1800032af  not     ecx
0x1800032b1  lea     rax, [rbp+3Fh+var_58]
0x1800032b5  mov     [rsp+0C0h+var_78], rax
0x1800032ba  and     ecx, 2
0x1800032bd  mov     [rsp+0C0h+var_80], r8
0x1800032c2  mov     qword ptr [rsp+0C0h+var_88], r8
0x1800032c7  mov     [rsp+0C0h+var_90], r8
0x1800032cc  lea     r8, [rbp+3Fh+var_5C]
0x1800032d0  mov     [rsp+0C0h+var_98], ecx
0x1800032d4  mov     rcx, rdi
0x1800032d7  mov     dword ptr [rsp+0C0h+var_A0], 2
0x1800032df  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x1800032e4  mov     r14, [rbp+3Fh+arg_20]
0x1800032e8  xor     edx, edx
0x1800032ea  mov     ebx, eax
0x1800032ec  test    eax, eax
0x1800032ee  js      loc_18000339F
0x1800032f4  lea     rax, [rbp+3Fh+var_4C]
0x1800032f8  mov     r9, r14
0x1800032fb  mov     [rsp+0C0h+var_70], rax
0x180003300  lea     r8, [rbp+3Fh+var_60]
0x180003304  lea     rax, [rbp+3Fh+var_54]
0x180003308  mov     rcx, rdi
0x18000330b  mov     [rsp+0C0h+var_78], rax
0x180003310  mov     [rsp+0C0h+var_80], rdx
0x180003315  mov     qword ptr [rsp+0C0h+var_88], rdx
0x18000331a  mov     [rsp+0C0h+var_90], rdx
0x18000331f  mov     [rsp+0C0h+var_98], 2
0x180003327  mov     dword ptr [rsp+0C0h+var_A0], edx
0x18000332b  mov     edx, r13d
0x18000332e  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180003333  xor     edx, edx
0x180003335  mov     ebx, eax
0x180003337  test    eax, eax
0x180003339  js      short loc_18000339F
0x18000333b  mov     rcx, [rdi+328h]
0x180003342  test    rcx, rcx
0x180003345  jz      short loc_18000335F
0x180003347  cmp     [rbp+3Fh+var_58], 1
0x18000334b  jnz     short loc_18000335F
0x18000334d  cmp     [rbp+3Fh+var_54], 1
0x180003351  jnz     short loc_18000335F
0x180003353  mov     rax, [rcx]
0x180003356  mov     rax, [rax+0C8h]
0x18000335d  jmp     short loc_18000336D
0x18000335f  mov     rcx, [rdi+20h]
0x180003363  mov     rax, [rcx]
0x180003366  mov     rax, [rax+0F8h]
0x18000336d  mov     edx, [rbp+3Fh+arg_38]
0x180003373  mov     r8, r15
0x180003376  mov     r9d, [rbp+3Fh+var_60]
0x18000337a  mov     dword ptr [rsp+0C0h+var_80], r12d
0x18000337f  mov     [rsp+0C0h+var_88], edx
0x180003383  mov     edx, [rbp+3Fh+arg_30]
0x180003386  mov     dword ptr [rsp+0C0h+var_90], edx
0x18000338a  mov     edx, [rbp+3Fh+var_5C]
0x18000338d  mov     [rsp+0C0h+var_98], esi
0x180003391  mov     [rsp+0C0h+var_A0], r14
0x180003396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339b  xor     edx, edx
0x18000339d  mov     ebx, eax
0x18000339f  cmp     [rbp+3Fh+var_50], edx
0x1800033a2  jnz     short loc_1800033A9
0x1800033a4  cmp     [rbp+3Fh+var_4C], edx
0x1800033a7  jz      short loc_1800033DF
0x1800033a9  mov     r9d, [rbp+3Fh+arg_8]; unsigned int
0x1800033ad  mov     r8d, ebx; int
0x1800033b0  mov     [rsp+0C0h+var_70], rdx; unsigned __int16 *
0x1800033b5  mov     rcx, rdi; this
0x1800033b8  mov     [rsp+0C0h+var_78], rdx; struct _METADATA_RECORD *
0x1800033bd  mov     [rsp+0C0h+var_80], rdx; struct _METADATA_RECORD *
0x1800033c2  mov     [rsp+0C0h+var_88], edx; unsigned int
0x1800033c6  mov     edx, 119Ch; unsigned int
0x1800033cb  mov     [rsp+0C0h+var_90], r14; unsigned __int16 *
0x1800033d0  mov     [rsp+0C0h+var_98], r13d; unsigned int
0x1800033d5  mov     [rsp+0C0h+var_A0], r15; unsigned __int16 *
0x1800033da  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x1800033df  mov     eax, ebx
0x1800033e1  add     rsp, 88h
0x1800033e8  pop     r15
0x1800033ea  pop     r14
0x1800033ec  pop     r13
0x1800033ee  pop     r12
0x1800033f0  pop     rdi
0x1800033f1  pop     rsi
0x1800033f2  pop     rbx
0x1800033f3  pop     rbp
0x1800033f4  retn
```
