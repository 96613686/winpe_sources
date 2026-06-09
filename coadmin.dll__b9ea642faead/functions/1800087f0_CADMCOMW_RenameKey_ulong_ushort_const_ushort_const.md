# CADMCOMW::RenameKey(ulong,ushort const *,ushort const *)

- ea: `0x1800087f0`
- end: `0x180008aa9`
- name: `?RenameKey@CADMCOMW@@UEAAJKPEBG0@Z`
- size: `697`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x18000716c`
- `0x1800087f0`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `msvcrt!wcschr` at `0x180008870`
- `msvcrt!wcschr` at `0x180008885`
- `msvcrt!wcschr` at `0x180008870`
- `msvcrt!wcschr` at `0x180008885`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180008a81`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180008a81`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000899c`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000899c`
- `IisRTL!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008985`
- `IisRTL!?Append@STRU@@QEAAJPEBGK@Z` at `0x180008985`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180008964`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180008964`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000882e`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000882e`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RenameKey(
        CADMCOMW *this,
        unsigned int a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rdi
  signed int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rcx
  signed int v15; // eax
  unsigned int v17; // [rsp+60h] [rbp-49h] BYREF
  int v18; // [rsp+64h] [rbp-45h] BYREF
  int v19; // [rsp+68h] [rbp-41h] BYREF
  int v20; // [rsp+6Ch] [rbp-3Dh] BYREF
  int v21; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v22[56]; // [rsp+78h] [rbp-31h] BYREF

  v17 = 0;
  STRU::STRU((STRU *)v22);
  v20 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a2 )
    goto LABEL_33;
  if ( !a3 )
    goto LABEL_33;
  if ( !a4 )
    goto LABEL_33;
  if ( !*a4 )
    goto LABEL_33;
  if ( wcschr(a4, 0x2Fu) )
    goto LABEL_33;
  if ( wcschr(a4, 0x5Cu) )
    goto LABEL_33;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( (unsigned int)(v8 - 1) > 0xFE )
    goto LABEL_33;
  v9 = CADMCOMW::LookupAndAccessCheck(this, a2, &v17, (__int64)a3, 0, 2, 0, 0, 0, &v18, (__int64)&v20);
  if ( v9 < 0 )
    goto LABEL_34;
  v10 = (unsigned int)(v8 - 1);
  if ( a3[v10] == 47 || a3[v10] == 92 )
  {
    if ( (_DWORD)v8 != 1 )
    {
      v11 = (unsigned int)(v8 - 2);
      if ( a3[v11] != 47 && a3[v11] != 92 )
      {
        LODWORD(v8) = v8 - 1;
        goto LABEL_17;
      }
    }
LABEL_33:
    v9 = -2147024809;
    goto LABEL_34;
  }
LABEL_17:
  v12 = v8;
  while ( 1 )
  {
    v13 = (unsigned int)(v12 - 1);
    if ( a3[v13] == 47 || a3[v13] == 92 )
      break;
    --v12;
    if ( !(_DWORD)v13 )
      goto LABEL_23;
  }
  LODWORD(v8) = v12 - 1;
LABEL_23:
  v9 = STRU::Copy((STRU *)v22, a3, v12 != 0 ? v8 : 0);
  if ( v9 >= 0 )
  {
    v9 = STRU::Append((STRU *)v22, L"/", 1u);
    if ( v9 >= 0 )
    {
      v9 = STRU::Append((STRU *)v22, a4);
      if ( v9 >= 0 )
      {
        v9 = CADMCOMW::LookupAndAccessCheck(this, a2, &v17, (__int64)a3, 0, 2, 0, 0, 0, &v19, (__int64)&v21);
        if ( v9 >= 0 )
        {
          v14 = *((_QWORD *)this + 101);
          if ( v14 && v18 == 1 && v19 == 1 )
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v14 + 216LL))(
                    v14,
                    v17,
                    a3,
                    a4);
          else
            v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 4) + 136LL))(
                    *((_QWORD *)this + 4),
                    v17,
                    a3,
                    a4);
          v9 = v15;
        }
      }
    }
  }
LABEL_34:
  if ( v20 || v21 )
    CADMCOMW::AuditAccess(this, 0x1198u, v9, a2, a3, 0, 0, 0, 0, 0, a4);
  STRU::~STRU((STRU *)v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800087f0  push    rbp
0x1800087f2  push    rbx
0x1800087f3  push    rsi
0x1800087f4  push    rdi
0x1800087f5  push    r12
0x1800087f7  push    r13
0x1800087f9  push    r14
0x1800087fb  push    r15
0x1800087fd  lea     rbp, [rsp-1Fh]
0x180008802  sub     rsp, 0C8h
0x180008809  mov     rax, cs:__security_cookie
0x180008810  xor     rax, rsp
0x180008813  mov     [rbp+57h+var_50], rax
0x180008817  mov     r15, rcx
0x18000881a  xor     r13d, r13d
0x18000881d  lea     rcx, [rbp+57h+var_88]
0x180008821  mov     [rbp+57h+var_A0], r13d
0x180008825  mov     r14, r9
0x180008828  mov     rsi, r8
0x18000882b  mov     r12d, edx
0x18000882e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180008834  mov     [rbp+57h+var_94], r13d
0x180008838  mov     [rbp+57h+var_90], r13d
0x18000883c  mov     [rbp+57h+var_9C], r13d
0x180008840  mov     [rbp+57h+var_98], r13d
0x180008844  test    r12d, r12d
0x180008847  jz      loc_180008A36
0x18000884d  test    rsi, rsi
0x180008850  jz      loc_180008A36
0x180008856  test    r14, r14
0x180008859  jz      loc_180008A36
0x18000885f  cmp     [r14], r13w
0x180008863  jz      loc_180008A36
0x180008869  lea     edx, [r13+2Fh]; Ch
0x18000886d  mov     rcx, r14; Str
0x180008870  call    cs:__imp_wcschr
0x180008876  test    rax, rax
0x180008879  jnz     loc_180008A36
0x18000887f  lea     edx, [rax+5Ch]; Ch
0x180008882  mov     rcx, r14; Str
0x180008885  call    cs:__imp_wcschr
0x18000888b  test    rax, rax
0x18000888e  jnz     loc_180008A36
0x180008894  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008898  inc     rdi
0x18000889b  cmp     [rsi+rdi*2], r13w
0x1800088a0  jnz     short loc_180008898
0x1800088a2  lea     eax, [rdi-1]
0x1800088a5  cmp     eax, 0FEh
0x1800088aa  ja      loc_180008A36
0x1800088b0  lea     rax, [rbp+57h+var_94]
0x1800088b4  mov     r9, rsi
0x1800088b7  mov     [rsp+100h+var_B0], rax
0x1800088bc  lea     r8, [rbp+57h+var_A0]
0x1800088c0  lea     rax, [rbp+57h+var_9C]
0x1800088c4  mov     edx, r12d
0x1800088c7  mov     [rsp+100h+var_B8], rax
0x1800088cc  mov     rcx, r15
0x1800088cf  mov     [rsp+100h+var_C0], r13
0x1800088d4  mov     qword ptr [rsp+100h+var_C8], r13
0x1800088d9  mov     [rsp+100h+var_D0], r13
0x1800088de  mov     [rsp+100h+var_D8], 2
0x1800088e6  mov     dword ptr [rsp+100h+var_E0], r13d
0x1800088eb  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x1800088f0  mov     ebx, eax
0x1800088f2  test    eax, eax
0x1800088f4  js      loc_180008A3B
0x1800088fa  mov     r9d, 2Fh ; '/'
0x180008900  lea     edx, [rdi-1]
0x180008903  lea     r8d, [r9+2Dh]
0x180008907  cmp     [rsi+rdx*2], r9w
0x18000890c  jz      short loc_180008915
0x18000890e  cmp     [rsi+rdx*2], r8w
0x180008913  jnz     short loc_180008938
0x180008915  test    edx, edx
0x180008917  jz      loc_180008A36
0x18000891d  lea     eax, [rdx-1]
0x180008920  cmp     [rsi+rax*2], r9w
0x180008925  jz      loc_180008A36
0x18000892b  cmp     [rsi+rax*2], r8w
0x180008930  jz      loc_180008A36
0x180008936  mov     edi, edx
0x180008938  mov     ecx, edi
0x18000893a  lea     edx, [rcx-1]
0x18000893d  cmp     [rsi+rdx*2], r9w
0x180008942  jz      short loc_180008953
0x180008944  cmp     [rsi+rdx*2], r8w
0x180008949  jz      short loc_180008953
0x18000894b  mov     ecx, edx
0x18000894d  test    edx, edx
0x18000894f  jnz     short loc_18000893A
0x180008951  jmp     short loc_180008955
0x180008953  mov     edi, edx
0x180008955  neg     ecx
0x180008957  mov     rdx, rsi
0x18000895a  lea     rcx, [rbp+57h+var_88]
0x18000895e  sbb     r8d, r8d
0x180008961  and     r8d, edi
0x180008964  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000896a  mov     ebx, eax
0x18000896c  test    eax, eax
0x18000896e  js      loc_180008A3B
0x180008974  mov     r8d, 1
0x18000897a  lea     rdx, asc_180011C70; "/"
0x180008981  lea     rcx, [rbp+57h+var_88]
0x180008985  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18000898b  mov     ebx, eax
0x18000898d  test    eax, eax
0x18000898f  js      loc_180008A3B
0x180008995  mov     rdx, r14
0x180008998  lea     rcx, [rbp+57h+var_88]
0x18000899c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800089a2  mov     ebx, eax
0x1800089a4  test    eax, eax
0x1800089a6  js      loc_180008A3B
0x1800089ac  lea     rax, [rbp+57h+var_90]
0x1800089b0  mov     r9, rsi
0x1800089b3  mov     [rsp+100h+var_B0], rax
0x1800089b8  lea     r8, [rbp+57h+var_A0]
0x1800089bc  lea     rax, [rbp+57h+var_98]
0x1800089c0  mov     edx, r12d
0x1800089c3  mov     [rsp+100h+var_B8], rax
0x1800089c8  mov     rcx, r15
0x1800089cb  mov     [rsp+100h+var_C0], r13
0x1800089d0  mov     qword ptr [rsp+100h+var_C8], r13
0x1800089d5  mov     [rsp+100h+var_D0], r13
0x1800089da  mov     [rsp+100h+var_D8], 2
0x1800089e2  mov     dword ptr [rsp+100h+var_E0], r13d
0x1800089e7  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x1800089ec  mov     ebx, eax
0x1800089ee  test    eax, eax
0x1800089f0  js      short loc_180008A3B
0x1800089f2  mov     rcx, [r15+328h]
0x1800089f9  test    rcx, rcx
0x1800089fc  jz      short loc_180008A26
0x1800089fe  cmp     [rbp+57h+var_9C], 1
0x180008a02  jnz     short loc_180008A26
0x180008a04  cmp     [rbp+57h+var_98], 1
0x180008a08  jnz     short loc_180008A26
0x180008a0a  mov     rax, [rcx]
0x180008a0d  mov     rax, [rax+0D8h]
0x180008a14  mov     edx, [rbp+57h+var_A0]
0x180008a17  mov     r8, rsi
0x180008a1a  mov     r9, r14
0x180008a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a22  mov     ebx, eax
0x180008a24  jmp     short loc_180008A3B
0x180008a26  mov     rcx, [r15+20h]
0x180008a2a  mov     rax, [rcx]
0x180008a2d  mov     rax, [rax+88h]
0x180008a34  jmp     short loc_180008A14
0x180008a36  mov     ebx, 80070057h
0x180008a3b  cmp     [rbp+57h+var_94], r13d
0x180008a3f  jnz     short loc_180008A47
0x180008a41  cmp     [rbp+57h+var_90], r13d
0x180008a45  jz      short loc_180008A7D
0x180008a47  mov     [rsp+100h+var_B0], r14; unsigned __int16 *
0x180008a4c  mov     r9d, r12d; unsigned int
0x180008a4f  mov     [rsp+100h+var_B8], r13; struct _METADATA_RECORD *
0x180008a54  mov     r8d, ebx; int
0x180008a57  mov     [rsp+100h+var_C0], r13; struct _METADATA_RECORD *
0x180008a5c  mov     edx, 1198h; unsigned int
0x180008a61  mov     [rsp+100h+var_C8], r13d; unsigned int
0x180008a66  mov     rcx, r15; this
0x180008a69  mov     [rsp+100h+var_D0], r13; unsigned __int16 *
0x180008a6e  mov     [rsp+100h+var_D8], r13d; unsigned int
0x180008a73  mov     [rsp+100h+var_E0], rsi; unsigned __int16 *
0x180008a78  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180008a7d  lea     rcx, [rbp+57h+var_88]
0x180008a81  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008a87  mov     eax, ebx
0x180008a89  mov     rcx, [rbp+57h+var_50]
0x180008a8d  xor     rcx, rsp; StackCookie
0x180008a90  call    __security_check_cookie
0x180008a95  add     rsp, 0C8h
0x180008a9c  pop     r15
0x180008a9e  pop     r14
0x180008aa0  pop     r13
0x180008aa2  pop     r12
0x180008aa4  pop     rdi
0x180008aa5  pop     rsi
0x180008aa6  pop     rbx
0x180008aa7  pop     rbp
0x180008aa8  retn
```
