# CADMCOMW::CopyKey(ulong,ushort const *,ulong,ushort const *,int,int)

- ea: `0x180003400`
- end: `0x180003588`
- name: `?CopyKey@CADMCOMW@@UEAAJKPEBGK0HH@Z`
- size: `392`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x180003400`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CopyKey(
        CADMCOMW *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        int a7)
{
  signed int v11; // ebx
  __int64 v12; // rcx
  signed int v13; // eax
  unsigned int v15; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v16; // [rsp+64h] [rbp-1Dh] BYREF
  int v17; // [rsp+68h] [rbp-19h] BYREF
  int v18; // [rsp+6Ch] [rbp-15h] BYREF
  int v19; // [rsp+70h] [rbp-11h] BYREF
  _DWORD v20[19]; // [rsp+74h] [rbp-Dh] BYREF

  v16 = 0;
  v15 = 0;
  v19 = 0;
  v20[0] = 0;
  v17 = 0;
  v18 = 0;
  v11 = CADMCOMW::LookupAndAccessCheck(this, a2, &v16, (__int64)a3, 2u, a7 == 0 ? 2 : 0, 0, 0, 0, &v17, (__int64)&v19);
  if ( v11 >= 0 )
  {
    v11 = CADMCOMW::LookupAndAccessCheck(this, a4, &v15, (__int64)a5, 0, 2, 0, 0, 0, &v18, (__int64)v20);
    if ( v11 >= 0 )
    {
      v12 = *((_QWORD *)this + 101);
      if ( v12 && v17 == 1 && v18 == 1 )
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, unsigned __int16 *, int, int))(*(_QWORD *)v12 + 208LL))(
                v12,
                v16,
                a3,
                v15,
                a5,
                a6,
                a7);
      else
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, unsigned __int16 *, int, int))(**((_QWORD **)this + 4) + 120LL))(
                *((_QWORD *)this + 4),
                v16,
                a3,
                v15,
                a5,
                a6,
                a7);
      v11 = v13;
    }
  }
  if ( v19 || v20[0] )
    CADMCOMW::AuditAccess(this, 0x1197u, v11, a2, a3, a4, a5, 0, 0, 0, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003400  push    rbp
0x180003402  push    rbx
0x180003403  push    rsi
0x180003404  push    rdi
0x180003405  push    r12
0x180003407  push    r13
0x180003409  push    r14
0x18000340b  push    r15
0x18000340d  lea     rbp, [rsp-7]
0x180003412  sub     rsp, 88h
0x180003419  mov     r12d, [rbp+3Fh+arg_30]
0x18000341d  mov     r14, r8
0x180003420  mov     rdi, rcx
0x180003423  mov     eax, r12d
0x180003426  xor     ecx, ecx
0x180003428  mov     r15d, r9d
0x18000342b  neg     eax
0x18000342d  mov     [rbp+3Fh+var_5C], ecx
0x180003430  lea     rax, [rbp+3Fh+var_50]
0x180003434  mov     [rbp+3Fh+var_60], ecx
0x180003437  mov     [rsp+0C0h+var_70], rax
0x18000343c  sbb     r8d, r8d
0x18000343f  not     r8d
0x180003442  mov     [rbp+3Fh+var_50], ecx
0x180003445  and     r8d, 2
0x180003449  mov     [rbp+3Fh+var_4C], ecx
0x18000344c  lea     rax, [rbp+3Fh+var_58]
0x180003450  mov     [rbp+3Fh+var_58], ecx
0x180003453  mov     [rsp+0C0h+var_78], rax
0x180003458  mov     r9, r14
0x18000345b  mov     [rsp+0C0h+var_80], rcx
0x180003460  mov     r13d, edx
0x180003463  mov     qword ptr [rsp+0C0h+var_88], rcx
0x180003468  mov     [rsp+0C0h+var_90], rcx
0x18000346d  mov     [rsp+0C0h+var_98], r8d
0x180003472  lea     r8, [rbp+3Fh+var_5C]
0x180003476  mov     [rbp+3Fh+var_54], ecx
0x180003479  mov     rcx, rdi
0x18000347c  mov     dword ptr [rsp+0C0h+var_A0], 2
0x180003484  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180003489  mov     rsi, [rbp+3Fh+arg_20]
0x18000348d  xor     edx, edx
0x18000348f  mov     ebx, eax
0x180003491  test    eax, eax
0x180003493  js      loc_180003533
0x180003499  lea     rax, [rbp+3Fh+var_4C]
0x18000349d  mov     r9, rsi
0x1800034a0  mov     [rsp+0C0h+var_70], rax
0x1800034a5  lea     r8, [rbp+3Fh+var_60]
0x1800034a9  lea     rax, [rbp+3Fh+var_54]
0x1800034ad  mov     rcx, rdi
0x1800034b0  mov     [rsp+0C0h+var_78], rax
0x1800034b5  mov     [rsp+0C0h+var_80], rdx
0x1800034ba  mov     qword ptr [rsp+0C0h+var_88], rdx
0x1800034bf  mov     [rsp+0C0h+var_90], rdx
0x1800034c4  mov     [rsp+0C0h+var_98], 2
0x1800034cc  mov     dword ptr [rsp+0C0h+var_A0], edx
0x1800034d0  mov     edx, r15d
0x1800034d3  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x1800034d8  xor     edx, edx
0x1800034da  mov     ebx, eax
0x1800034dc  test    eax, eax
0x1800034de  js      short loc_180003533
0x1800034e0  mov     rcx, [rdi+328h]
0x1800034e7  test    rcx, rcx
0x1800034ea  jz      short loc_180003504
0x1800034ec  cmp     [rbp+3Fh+var_58], 1
0x1800034f0  jnz     short loc_180003504
0x1800034f2  cmp     [rbp+3Fh+var_54], 1
0x1800034f6  jnz     short loc_180003504
0x1800034f8  mov     rax, [rcx]
0x1800034fb  mov     rax, [rax+0D0h]
0x180003502  jmp     short loc_18000350F
0x180003504  mov     rcx, [rdi+20h]
0x180003508  mov     rax, [rcx]
0x18000350b  mov     rax, [rax+78h]
0x18000350f  mov     edx, [rbp+3Fh+arg_28]
0x180003512  mov     r8, r14
0x180003515  mov     r9d, [rbp+3Fh+var_60]
0x180003519  mov     dword ptr [rsp+0C0h+var_90], r12d
0x18000351e  mov     [rsp+0C0h+var_98], edx
0x180003522  mov     edx, [rbp+3Fh+var_5C]
0x180003525  mov     [rsp+0C0h+var_A0], rsi
0x18000352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352f  xor     edx, edx
0x180003531  mov     ebx, eax
0x180003533  cmp     [rbp+3Fh+var_50], edx
0x180003536  jnz     short loc_18000353D
0x180003538  cmp     [rbp+3Fh+var_4C], edx
0x18000353b  jz      short loc_180003572
0x18000353d  mov     [rsp+0C0h+var_70], rdx; unsigned __int16 *
0x180003542  mov     r9d, r13d; unsigned int
0x180003545  mov     [rsp+0C0h+var_78], rdx; struct _METADATA_RECORD *
0x18000354a  mov     r8d, ebx; int
0x18000354d  mov     [rsp+0C0h+var_80], rdx; struct _METADATA_RECORD *
0x180003552  mov     rcx, rdi; this
0x180003555  mov     [rsp+0C0h+var_88], edx; unsigned int
0x180003559  mov     edx, 1197h; unsigned int
0x18000355e  mov     [rsp+0C0h+var_90], rsi; unsigned __int16 *
0x180003563  mov     [rsp+0C0h+var_98], r15d; unsigned int
0x180003568  mov     [rsp+0C0h+var_A0], r14; unsigned __int16 *
0x18000356d  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180003572  mov     eax, ebx
0x180003574  add     rsp, 88h
0x18000357b  pop     r15
0x18000357d  pop     r14
0x18000357f  pop     r13
0x180003581  pop     r12
0x180003583  pop     rdi
0x180003584  pop     rsi
0x180003585  pop     rbx
0x180003586  pop     rbp
0x180003587  retn
```
