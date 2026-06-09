# CADMCOMW::DeleteData(ulong,ushort const *,ulong,ulong)

- ea: `0x180003fd0`
- end: `0x180004196`
- name: `?DeleteData@CADMCOMW@@UEAAJKPEBGKK@Z`
- size: `454`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x180003fd0`
- `0x18000716c`
- `0x18000b2d4`
- `0x18000f468`
- `0x180010010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180004154`
- `KERNEL32!GetProcessHeap` at `0x18000416c`
- `KERNEL32!GetProcessHeap` at `0x180004154`
- `KERNEL32!GetProcessHeap` at `0x18000416c`
- `KERNEL32!HeapFree` at `0x180004162`
- `KERNEL32!HeapFree` at `0x18000417a`
- `KERNEL32!HeapFree` at `0x180004162`
- `KERNEL32!HeapFree` at `0x18000417a`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteData(
        struct IMDCOM **this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  struct _METADATA_RECORD *v9; // rbx
  signed int v10; // edi
  int v11; // eax
  struct IMDCOM *v12; // rcx
  signed int v13; // eax
  unsigned __int8 *pbMDData; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  unsigned int v18; // [rsp+60h] [rbp-41h] BYREF
  int v19; // [rsp+64h] [rbp-3Dh] BYREF
  int v20; // [rsp+68h] [rbp-39h] BYREF
  struct _METADATA_RECORD *v21; // [rsp+70h] [rbp-31h] BYREF
  __int64 v22; // [rsp+78h] [rbp-29h] BYREF
  _DWORD v23[4]; // [rsp+80h] [rbp-21h] BYREF
  __int128 v24; // [rsp+90h] [rbp-11h]
  __int64 v25; // [rsp+A0h] [rbp-1h]

  v18 = 0;
  v23[2] = 0;
  v25 = 0;
  v19 = 0;
  v9 = 0;
  v21 = 0;
  v20 = 0;
  v24 = 0;
  if ( a5 < 6 )
  {
    v23[0] = a4;
    v23[3] = a5;
    v23[1] = 16;
    v10 = CADMCOMW::LookupAndAccessCheck(
            (CADMCOMW *)this,
            a2,
            &v18,
            (__int64)a3,
            0,
            5,
            (__int64)v23,
            0,
            &v22,
            &v20,
            (__int64)&v19);
    if ( v10 >= 0 )
    {
      if ( a4 == 6027 )
        CAdminAclCache::Flush((CAdminAclCache *)g_AclCache);
      if ( v19 )
      {
        v11 = RetrieveOldValue((struct CADMCOMW *)this, this[4], a2, a4, a3, &v21);
        v9 = v21;
        if ( v11 < 0 )
          v9 = 0;
      }
      v12 = this[101];
      if ( v12 && v20 == 1 )
        v13 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(*(_QWORD *)v12 + 112LL))(
                v12,
                v18,
                a3,
                a4,
                a5);
      else
        v13 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, unsigned __int16 *, _QWORD, unsigned int))(*(_QWORD *)this[4] + 184LL))(
                this[4],
                v18,
                a3,
                a4,
                a5);
      v10 = v13;
    }
    if ( v19 )
      CADMCOMW::AuditAccess((CADMCOMW *)this, 0x119Au, v10, a2, a3, 0, 0, a4, v9, 0, 0);
    if ( v9 )
    {
      pbMDData = v9->pbMDData;
      if ( pbMDData )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, pbMDData);
        v9->pbMDData = 0;
      }
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v9);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003fd0  push    rbp
0x180003fd2  push    rbx
0x180003fd3  push    rsi
0x180003fd4  push    rdi
0x180003fd5  push    r12
0x180003fd7  push    r13
0x180003fd9  push    r14
0x180003fdb  push    r15
0x180003fdd  lea     rbp, [rsp-17h]
0x180003fe2  sub     rsp, 0B8h
0x180003fe9  mov     r12d, [rbp+4Fh+arg_20]
0x180003fed  mov     r14, rcx
0x180003ff0  xor     ecx, ecx
0x180003ff2  xorps   xmm0, xmm0
0x180003ff5  mov     [rbp+4Fh+var_90], ecx
0x180003ff8  mov     esi, r9d
0x180003ffb  mov     [rbp+4Fh+var_68], ecx
0x180003ffe  mov     r15, r8
0x180004001  mov     [rbp+4Fh+var_50], rcx
0x180004005  mov     r13d, edx
0x180004008  mov     [rbp+4Fh+var_8C], ecx
0x18000400b  mov     ebx, ecx
0x18000400d  mov     [rbp+4Fh+var_80], rcx
0x180004011  mov     [rbp+4Fh+var_88], ecx
0x180004014  movdqu  [rbp+4Fh+var_60], xmm0
0x180004019  cmp     r12d, 6
0x18000401d  jb      short loc_180004029
0x18000401f  mov     edi, 80070057h
0x180004024  jmp     loc_180004180
0x180004029  lea     rax, [rbp+4Fh+var_8C]
0x18000402d  mov     [rbp+4Fh+var_70], esi
0x180004030  mov     [rsp+0F0h+var_A0], rax
0x180004035  lea     r8, [rbp+4Fh+var_90]
0x180004039  lea     rax, [rbp+4Fh+var_88]
0x18000403d  mov     [rbp+4Fh+var_64], r12d
0x180004041  mov     [rsp+0F0h+var_A8], rax
0x180004046  mov     r9, r15
0x180004049  lea     rax, [rbp+4Fh+var_78]
0x18000404d  mov     [rbp+4Fh+var_6C], 10h
0x180004054  mov     [rsp+0F0h+var_B0], rax
0x180004059  lea     rax, [rbp+4Fh+var_70]
0x18000405d  mov     qword ptr [rsp+0F0h+var_B8], rcx
0x180004062  mov     [rsp+0F0h+var_C0], rax
0x180004067  mov     dword ptr [rsp+0F0h+var_C8], 5
0x18000406f  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180004073  mov     rcx, r14
0x180004076  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x18000407b  mov     edi, eax
0x18000407d  test    eax, eax
0x18000407f  js      loc_180004108
0x180004085  cmp     esi, 178Bh
0x18000408b  jnz     short loc_180004099
0x18000408d  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x180004094  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x180004099  cmp     [rbp+4Fh+var_8C], ebx
0x18000409c  jz      short loc_1800040CA
0x18000409e  mov     rdx, [r14+20h]; struct IMDCOM *
0x1800040a2  lea     rax, [rbp+4Fh+var_80]
0x1800040a6  mov     [rsp+0F0h+var_C8], rax; struct _METADATA_RECORD **
0x1800040ab  mov     r9d, esi; unsigned int
0x1800040ae  mov     r8d, r13d; unsigned int
0x1800040b1  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x1800040b6  mov     rcx, r14; struct CADMCOMW *
0x1800040b9  call    ?RetrieveOldValue@@YAJPEAVCADMCOMW@@PEAUIMDCOM@@KKPEBGPEAPEAU_METADATA_RECORD@@@Z; RetrieveOldValue(CADMCOMW *,IMDCOM *,ulong,ulong,ushort const *,_METADATA_RECORD * *)
0x1800040be  mov     rbx, [rbp+4Fh+var_80]
0x1800040c2  xor     ecx, ecx
0x1800040c4  test    eax, eax
0x1800040c6  cmovs   rbx, rcx
0x1800040ca  mov     rcx, [r14+328h]
0x1800040d1  test    rcx, rcx
0x1800040d4  jz      short loc_1800040E5
0x1800040d6  cmp     [rbp+4Fh+var_88], 1
0x1800040da  jnz     short loc_1800040E5
0x1800040dc  mov     rax, [rcx]
0x1800040df  mov     rax, [rax+70h]
0x1800040e3  jmp     short loc_1800040F3
0x1800040e5  mov     rcx, [r14+20h]
0x1800040e9  mov     rax, [rcx]
0x1800040ec  mov     rax, [rax+0B8h]
0x1800040f3  mov     edx, [rbp+4Fh+var_90]
0x1800040f6  mov     r9d, esi
0x1800040f9  mov     r8, r15
0x1800040fc  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x180004101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004106  mov     edi, eax
0x180004108  xor     r12d, r12d
0x18000410b  cmp     [rbp+4Fh+var_8C], r12d
0x18000410f  jz      short loc_180004146
0x180004111  mov     [rsp+0F0h+var_A0], r12; unsigned __int16 *
0x180004116  mov     r9d, r13d; unsigned int
0x180004119  mov     [rsp+0F0h+var_A8], r12; struct _METADATA_RECORD *
0x18000411e  mov     r8d, edi; int
0x180004121  mov     [rsp+0F0h+var_B0], rbx; struct _METADATA_RECORD *
0x180004126  mov     edx, 119Ah; unsigned int
0x18000412b  mov     [rsp+0F0h+var_B8], esi; unsigned int
0x18000412f  mov     rcx, r14; this
0x180004132  mov     [rsp+0F0h+var_C0], r12; unsigned __int16 *
0x180004137  mov     dword ptr [rsp+0F0h+var_C8], r12d; unsigned int
0x18000413c  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x180004141  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180004146  test    rbx, rbx
0x180004149  jz      short loc_180004180
0x18000414b  mov     rsi, [rbx+18h]
0x18000414f  test    rsi, rsi
0x180004152  jz      short loc_18000416C
0x180004154  call    cs:__imp_GetProcessHeap
0x18000415a  mov     r8, rsi; lpMem
0x18000415d  xor     edx, edx; dwFlags
0x18000415f  mov     rcx, rax; hHeap
0x180004162  call    cs:__imp_HeapFree
0x180004168  mov     [rbx+18h], r12
0x18000416c  call    cs:__imp_GetProcessHeap
0x180004172  mov     r8, rbx; lpMem
0x180004175  xor     edx, edx; dwFlags
0x180004177  mov     rcx, rax; hHeap
0x18000417a  call    cs:__imp_HeapFree
0x180004180  mov     eax, edi
0x180004182  add     rsp, 0B8h
0x180004189  pop     r15
0x18000418b  pop     r14
0x18000418d  pop     r13
0x18000418f  pop     r12
0x180004191  pop     rdi
0x180004192  pop     rsi
0x180004193  pop     rbx
0x180004194  pop     rbp
0x180004195  retn
```
