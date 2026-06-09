# CSLTAudit::DumpObject(CTableInfo *,ulong,ulong,ushort * *,ulong,ushort * *)

- ea: `0x1800222d0`
- end: `0x1800224a4`
- name: `?DumpObject@CSLTAudit@@EEAAJPEAVCTableInfo@@KKPEAPEAGK1@Z`
- size: `468`
- prototype: `int(CSLTAudit *__hidden this, struct CTableInfo *, unsigned int, unsigned int, unsigned __int16 **, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180021ad8`
- `0x1800222d0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002243b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002244b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002245b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002246b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002247b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002248b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002243b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002244b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002245b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002246b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002247b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002248b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800223b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800223b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::DumpObject(
        CSLTAudit *this,
        struct CTableInfo *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned int a6,
        unsigned __int16 **a7)
{
  const unsigned __int16 *v10; // r15
  int v11; // ebx
  CTransactionToAuditLog *v12; // rax
  CTransactionToAuditLog *v13; // rax
  CTransactionToAuditLog *v14; // rdi
  LPVOID pv; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int16 *v19; // [rsp+68h] [rbp-9h] BYREF
  struct _LUID *v20; // [rsp+70h] [rbp-1h] BYREF
  LPVOID v21; // [rsp+C8h] [rbp+57h] BYREF

  pv = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v10 = (const unsigned __int16 *)**((_QWORD **)a2 + 5);
  v11 = (*(__int64 (__fastcall **)(CSLTAudit *, LPVOID *, struct _LUID **))(*(_QWORD *)this + 120LL))(this, &v21, &v20);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(CSLTAudit *, LPVOID, LPVOID *, unsigned __int16 **))(*(_QWORD *)this + 128LL))(
            this,
            v21,
            &pv,
            &v17);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)this + 136LL))(
              this,
              a4,
              a5,
              &v18);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(CSLTAudit *, _QWORD, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)this + 136LL))(
                this,
                a6,
                a7,
                &v19);
        if ( v11 >= 0 )
        {
          v12 = (CTransactionToAuditLog *)CoTaskMemAlloc(0x58u);
          if ( v12 )
          {
            v13 = CTransactionToAuditLog::CTransactionToAuditLog(
                    v12,
                    v10,
                    a3,
                    v18,
                    v19,
                    v21,
                    v17,
                    (unsigned __int16 *)pv,
                    v20);
            v14 = v13;
            if ( v13 )
            {
              v11 = (*(__int64 (__fastcall **)(CTransactionToAuditLog *))(*(_QWORD *)v13 + 56LL))(v13);
              (*(void (__fastcall **)(CTransactionToAuditLog *))(*(_QWORD *)v14 + 16LL))(v14);
              return (unsigned int)v11;
            }
          }
          v11 = -2147024882;
        }
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v17 )
    CoTaskMemFree(v17);
  if ( v21 )
    CoTaskMemFree(v21);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v19 )
    CoTaskMemFree(v19);
  if ( v20 )
    CoTaskMemFree(v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800222d0  push    rbp
0x1800222d2  push    rbx
0x1800222d3  push    rsi
0x1800222d4  push    rdi
0x1800222d5  push    r14
0x1800222d7  push    r15
0x1800222d9  lea     rbp, [rsp-17h]
0x1800222de  sub     rsp, 88h
0x1800222e5  mov     esi, r9d
0x1800222e8  mov     r14d, r8d
0x1800222eb  mov     rdi, rcx
0x1800222ee  mov     [rbp+3Fh+pv], 0
0x1800222f6  mov     [rbp+3Fh+var_58], 0
0x1800222fe  mov     [rbp+3Fh+var_50], 0
0x180022306  mov     [rbp+3Fh+var_48], 0
0x18002230e  mov     [rbp+3Fh+arg_8], 0
0x180022316  mov     [rbp+3Fh+var_40], 0
0x18002231e  mov     rax, [rdx+28h]
0x180022322  mov     r15, [rax]
0x180022325  mov     rax, [rcx]
0x180022328  lea     r8, [rbp+3Fh+var_40]
0x18002232c  lea     rdx, [rbp+3Fh+arg_8]
0x180022330  mov     rax, [rax+78h]
0x180022334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022339  mov     ebx, eax
0x18002233b  test    eax, eax
0x18002233d  js      loc_180022432
0x180022343  mov     rax, [rdi]
0x180022346  lea     r9, [rbp+3Fh+var_58]
0x18002234a  lea     r8, [rbp+3Fh+pv]
0x18002234e  mov     rdx, [rbp+3Fh+arg_8]
0x180022352  mov     rcx, rdi
0x180022355  mov     rax, [rax+80h]
0x18002235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022361  mov     ebx, eax
0x180022363  test    eax, eax
0x180022365  js      loc_180022432
0x18002236b  mov     rax, [rdi]
0x18002236e  lea     r9, [rbp+3Fh+var_50]
0x180022372  mov     r8, [rbp+3Fh+arg_20]
0x180022376  mov     edx, esi
0x180022378  mov     rcx, rdi
0x18002237b  mov     rax, [rax+88h]
0x180022382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022387  mov     ebx, eax
0x180022389  test    eax, eax
0x18002238b  js      loc_180022432
0x180022391  mov     rax, [rdi]
0x180022394  lea     r9, [rbp+3Fh+var_48]
0x180022398  mov     r8, [rbp+3Fh+arg_30]
0x18002239c  mov     edx, [rbp+3Fh+arg_28]
0x18002239f  mov     rcx, rdi
0x1800223a2  mov     rax, [rax+88h]
0x1800223a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ae  mov     ebx, eax
0x1800223b0  test    eax, eax
0x1800223b2  js      short loc_180022432
0x1800223b4  mov     ecx, 58h ; 'X'; cb
0x1800223b9  call    cs:__imp_CoTaskMemAlloc
0x1800223bf  test    rax, rax
0x1800223c2  jz      short loc_18002242D
0x1800223c4  mov     rcx, [rbp+3Fh+var_40]
0x1800223c8  mov     [rsp+0B0h+var_70], rcx; struct _LUID *
0x1800223cd  mov     rcx, [rbp+3Fh+pv]
0x1800223d1  mov     [rsp+0B0h+var_78], rcx; unsigned __int16 *
0x1800223d6  mov     rcx, [rbp+3Fh+var_58]
0x1800223da  mov     [rsp+0B0h+var_80], rcx; unsigned __int16 *
0x1800223df  mov     rcx, [rbp+3Fh+arg_8]
0x1800223e3  mov     [rsp+0B0h+var_88], rcx; void *
0x1800223e8  mov     rcx, [rbp+3Fh+var_48]
0x1800223ec  mov     [rsp+0B0h+var_90], rcx; unsigned __int16 *
0x1800223f1  mov     r9, [rbp+3Fh+var_50]; unsigned __int16 *
0x1800223f5  mov     r8d, r14d; unsigned int
0x1800223f8  mov     rdx, r15; unsigned __int16 *
0x1800223fb  mov     rcx, rax; this
0x1800223fe  call    ??0CTransactionToAuditLog@@QEAA@PEBGKPEAG1PEAX11PEAU_LUID@@@Z; CTransactionToAuditLog::CTransactionToAuditLog(ushort const *,ulong,ushort *,ushort *,void *,ushort *,ushort *,_LUID *)
0x180022403  mov     rdi, rax
0x180022406  test    rax, rax
0x180022409  jz      short loc_18002242D
0x18002240b  mov     rcx, [rax]
0x18002240e  mov     rax, [rcx+38h]
0x180022412  mov     rcx, rdi
0x180022415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002241a  mov     ebx, eax
0x18002241c  mov     rcx, [rdi]
0x18002241f  mov     rax, [rcx+10h]
0x180022423  mov     rcx, rdi
0x180022426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002242b  jmp     short loc_180022492
0x18002242d  mov     ebx, 8007000Eh
0x180022432  mov     rcx, [rbp+3Fh+pv]; pv
0x180022436  test    rcx, rcx
0x180022439  jz      short loc_180022442
0x18002243b  call    cs:__imp_CoTaskMemFree
0x180022441  nop
0x180022442  mov     rcx, [rbp+3Fh+var_58]; pv
0x180022446  test    rcx, rcx
0x180022449  jz      short loc_180022452
0x18002244b  call    cs:__imp_CoTaskMemFree
0x180022451  nop
0x180022452  mov     rcx, [rbp+3Fh+arg_8]; pv
0x180022456  test    rcx, rcx
0x180022459  jz      short loc_180022462
0x18002245b  call    cs:__imp_CoTaskMemFree
0x180022461  nop
0x180022462  mov     rcx, [rbp+3Fh+var_50]; pv
0x180022466  test    rcx, rcx
0x180022469  jz      short loc_180022472
0x18002246b  call    cs:__imp_CoTaskMemFree
0x180022471  nop
0x180022472  mov     rcx, [rbp+3Fh+var_48]; pv
0x180022476  test    rcx, rcx
0x180022479  jz      short loc_180022482
0x18002247b  call    cs:__imp_CoTaskMemFree
0x180022481  nop
0x180022482  mov     rcx, [rbp+3Fh+var_40]; pv
0x180022486  test    rcx, rcx
0x180022489  jz      short loc_180022492
0x18002248b  call    cs:__imp_CoTaskMemFree
0x180022491  nop
0x180022492  mov     eax, ebx
0x180022494  add     rsp, 88h
0x18002249b  pop     r15
0x18002249d  pop     r14
0x18002249f  pop     rdi
0x1800224a0  pop     rsi
0x1800224a1  pop     rbx
0x1800224a2  pop     rbp
0x1800224a3  retn
```
