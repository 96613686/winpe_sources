# CADMCOMW::SetData(ulong,ushort const *,_METADATA_RECORD *)

- ea: `0x180009200`
- end: `0x1800093b4`
- name: `?SetData@CADMCOMW@@UEAAJKPEBGPEAU_METADATA_RECORD@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct IMDCOM **this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x18000716c`
- `0x180009200`
- `0x18000b2d4`
- `0x18000f468`
- `0x180010010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009372`
- `KERNEL32!GetProcessHeap` at `0x18000938a`
- `KERNEL32!GetProcessHeap` at `0x180009372`
- `KERNEL32!GetProcessHeap` at `0x18000938a`
- `KERNEL32!HeapFree` at `0x180009380`
- `KERNEL32!HeapFree` at `0x180009398`
- `KERNEL32!HeapFree` at `0x180009380`
- `KERNEL32!HeapFree` at `0x180009398`

## pseudocode

```c
__int64 __fastcall CADMCOMW::SetData(
        struct IMDCOM **this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4)
{
  struct _METADATA_RECORD *v5; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v11; // eax
  struct IMDCOM *v12; // rcx
  unsigned int v13; // eax
  unsigned __int8 *pbMDData; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  unsigned int v18; // [rsp+60h] [rbp-9h] BYREF
  int v19; // [rsp+64h] [rbp-5h] BYREF
  struct _METADATA_RECORD *v20; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v21[10]; // [rsp+70h] [rbp+7h] BYREF
  int v22; // [rsp+E8h] [rbp+7Fh] BYREF

  v18 = 0;
  v5 = 0;
  v20 = 0;
  v19 = 0;
  v22 = 0;
  if ( a4 )
  {
    v10 = CADMCOMW::LookupAndAccessCheck(
            (CADMCOMW *)this,
            a2,
            &v18,
            (__int64)a3,
            0,
            5,
            (__int64)a4,
            0,
            v21,
            &v19,
            (__int64)&v22);
    v9 = v10;
    if ( a4->dwMDIdentifier == 9027 || a4->dwMDIdentifier == 1016 || a4->dwMDIdentifier == 1099 )
      v22 = 0;
    if ( v10 >= 0 )
    {
      if ( !v22
        || (v11 = RetrieveOldValue((struct CADMCOMW *)this, this[4], a2, a4->dwMDIdentifier, a3, &v20),
            v5 = v20,
            v9 = v11,
            v11 >= 0) )
      {
        if ( a4->dwMDIdentifier == 6027 )
          CAdminAclCache::Flush((CAdminAclCache *)&g_AclCache);
        v12 = this[101];
        if ( v12 && v19 == 1 )
          v13 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *))(*(_QWORD *)v12 + 64LL))(
                  v12,
                  v18,
                  a3,
                  a4);
        else
          v13 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *))(*(_QWORD *)this[4] + 152LL))(
                  this[4],
                  v18,
                  a3,
                  a4);
        v9 = v13;
      }
    }
    if ( v22 )
      CADMCOMW::AuditAccess((CADMCOMW *)this, 0x1199u, v9, a2, a3, 0, 0, a4->dwMDIdentifier, v5, a4, 0);
    if ( v5 )
    {
      pbMDData = v5->pbMDData;
      if ( pbMDData )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, pbMDData);
        v5->pbMDData = 0;
      }
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v5);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x180009200  push    rbp
0x180009202  push    rbx
0x180009203  push    rsi
0x180009204  push    rdi
0x180009205  push    r12
0x180009207  push    r13
0x180009209  push    r14
0x18000920b  push    r15
0x18000920d  lea     rbp, [rsp-1Fh]
0x180009212  sub     rsp, 88h
0x180009219  xor     r13d, r13d
0x18000921c  mov     rsi, r9
0x18000921f  mov     [rbp+57h+var_60], r13d
0x180009223  mov     ebx, r13d
0x180009226  mov     [rbp+57h+var_58], rbx
0x18000922a  mov     r15, r8
0x18000922d  mov     [rbp+57h+var_5C], r13d
0x180009231  mov     r12d, edx
0x180009234  mov     [rbp+57h+arg_18], r13d
0x180009238  mov     r14, rcx
0x18000923b  test    r9, r9
0x18000923e  jnz     short loc_18000924A
0x180009240  mov     edi, 80070057h
0x180009245  jmp     loc_18000939E
0x18000924a  lea     rax, [rbp+57h+arg_18]
0x18000924e  mov     r9, r15
0x180009251  mov     [rsp+0C0h+var_70], rax
0x180009256  lea     r8, [rbp+57h+var_60]
0x18000925a  lea     rax, [rbp+57h+var_5C]
0x18000925e  mov     [rsp+0C0h+var_78], rax
0x180009263  lea     rax, [rbp+57h+var_50]
0x180009267  mov     [rsp+0C0h+var_80], rax
0x18000926c  mov     qword ptr [rsp+0C0h+var_88], r13
0x180009271  mov     [rsp+0C0h+var_90], rsi
0x180009276  mov     dword ptr [rsp+0C0h+var_98], 5
0x18000927e  mov     dword ptr [rsp+0C0h+var_A0], r13d
0x180009283  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180009288  cmp     dword ptr [rsi], 2343h
0x18000928e  mov     edi, eax
0x180009290  jz      short loc_1800092A2
0x180009292  cmp     dword ptr [rsi], 3F8h
0x180009298  jz      short loc_1800092A2
0x18000929a  cmp     dword ptr [rsi], 44Bh
0x1800092a0  jnz     short loc_1800092A6
0x1800092a2  mov     [rbp+57h+arg_18], r13d
0x1800092a6  test    eax, eax
0x1800092a8  js      short loc_180009327
0x1800092aa  cmp     [rbp+57h+arg_18], r13d
0x1800092ae  jz      short loc_1800092DA
0x1800092b0  mov     r9d, [rsi]; unsigned int
0x1800092b3  lea     rax, [rbp+57h+var_58]
0x1800092b7  mov     rdx, [r14+20h]; struct IMDCOM *
0x1800092bb  mov     r8d, r12d; unsigned int
0x1800092be  mov     [rsp+0C0h+var_98], rax; struct _METADATA_RECORD **
0x1800092c3  mov     rcx, r14; struct CADMCOMW *
0x1800092c6  mov     [rsp+0C0h+var_A0], r15; unsigned __int16 *
0x1800092cb  call    ?RetrieveOldValue@@YAJPEAVCADMCOMW@@PEAUIMDCOM@@KKPEBGPEAPEAU_METADATA_RECORD@@@Z; RetrieveOldValue(CADMCOMW *,IMDCOM *,ulong,ulong,ushort const *,_METADATA_RECORD * *)
0x1800092d0  mov     rbx, [rbp+57h+var_58]
0x1800092d4  mov     edi, eax
0x1800092d6  test    eax, eax
0x1800092d8  js      short loc_180009327
0x1800092da  cmp     dword ptr [rsi], 178Bh
0x1800092e0  jnz     short loc_1800092EE
0x1800092e2  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x1800092e9  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x1800092ee  mov     rcx, [r14+328h]
0x1800092f5  test    rcx, rcx
0x1800092f8  jz      short loc_180009309
0x1800092fa  cmp     [rbp+57h+var_5C], 1
0x1800092fe  jnz     short loc_180009309
0x180009300  mov     rax, [rcx]
0x180009303  mov     rax, [rax+40h]
0x180009307  jmp     short loc_180009317
0x180009309  mov     rcx, [r14+20h]
0x18000930d  mov     rax, [rcx]
0x180009310  mov     rax, [rax+98h]
0x180009317  mov     edx, [rbp+57h+var_60]
0x18000931a  mov     r9, rsi
0x18000931d  mov     r8, r15
0x180009320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009325  mov     edi, eax
0x180009327  cmp     [rbp+57h+arg_18], r13d
0x18000932b  jz      short loc_180009364
0x18000932d  mov     eax, [rsi]
0x18000932f  mov     r9d, r12d; unsigned int
0x180009332  mov     [rsp+0C0h+var_70], r13; unsigned __int16 *
0x180009337  mov     r8d, edi; int
0x18000933a  mov     [rsp+0C0h+var_78], rsi; struct _METADATA_RECORD *
0x18000933f  mov     edx, 1199h; unsigned int
0x180009344  mov     [rsp+0C0h+var_80], rbx; struct _METADATA_RECORD *
0x180009349  mov     rcx, r14; this
0x18000934c  mov     [rsp+0C0h+var_88], eax; unsigned int
0x180009350  mov     [rsp+0C0h+var_90], r13; unsigned __int16 *
0x180009355  mov     dword ptr [rsp+0C0h+var_98], r13d; unsigned int
0x18000935a  mov     [rsp+0C0h+var_A0], r15; unsigned __int16 *
0x18000935f  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180009364  test    rbx, rbx
0x180009367  jz      short loc_18000939E
0x180009369  mov     rsi, [rbx+18h]
0x18000936d  test    rsi, rsi
0x180009370  jz      short loc_18000938A
0x180009372  call    cs:__imp_GetProcessHeap
0x180009378  mov     r8, rsi; lpMem
0x18000937b  xor     edx, edx; dwFlags
0x18000937d  mov     rcx, rax; hHeap
0x180009380  call    cs:__imp_HeapFree
0x180009386  mov     [rbx+18h], r13
0x18000938a  call    cs:__imp_GetProcessHeap
0x180009390  mov     r8, rbx; lpMem
0x180009393  xor     edx, edx; dwFlags
0x180009395  mov     rcx, rax; hHeap
0x180009398  call    cs:__imp_HeapFree
0x18000939e  mov     eax, edi
0x1800093a0  add     rsp, 88h
0x1800093a7  pop     r15
0x1800093a9  pop     r14
0x1800093ab  pop     r13
0x1800093ad  pop     r12
0x1800093af  pop     rdi
0x1800093b0  pop     rsi
0x1800093b1  pop     rbx
0x1800093b2  pop     rbp
0x1800093b3  retn
```
