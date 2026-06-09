# CPersistStreamInit::WriteColumnDefinition(CRowInfo &,ushort)

- ea: `0x18001d42c`
- end: `0x18001d6a8`
- name: `?WriteColumnDefinition@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `636`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18001f1bc`

## callees

- `0x180003c38`
- `0x1800041b4`
- `0x1800041ec`
- `0x180004384`
- `0x18001c0a0`
- `0x18001d1c8`
- `0x18001d42c`
- `0x18001d6b0`
- `0x18001d828`
- `0x18001dd70`
- `0x18001ed5c`
- `0x18001fe94`
- `0x180020274`
- `0x18002f0e0`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteColumnDefinition(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  __int64 v3; // rax
  __int64 v7; // r14
  unsigned __int16 *v8; // r12
  unsigned __int16 *Name; // rax
  CMetaData *v10; // rcx
  unsigned __int16 *v11; // r15
  unsigned __int16 v12; // dx
  BOOL v13; // eax
  unsigned __int8 v14; // bp
  __int64 result; // rax
  bool v16; // r9
  bool v17; // r9
  unsigned int Ordinal; // eax
  unsigned __int64 v19; // r9
  bool v20; // r9
  unsigned int Flags; // eax
  int v22; // [rsp+20h] [rbp-268h]
  unsigned int v23[4]; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int16 v24[256]; // [rsp+40h] [rbp-248h] BYREF

  v3 = *((_QWORD *)a2 + 8);
  v23[0] = 0;
  v7 = 2LL * a3;
  v8 = *(unsigned __int16 **)(v3 + 16LL * a3);
  Name = CMetaData::mdGetName(a2, a3);
  v11 = (unsigned __int16 *)&wszZls;
  if ( Name )
    v11 = Name;
  v13 = (CMetaData::mdGetFlags(v10, a3) & 0x2000) != 0 || CMetaData::mdGetType(a2, v12) == 136;
  v14 = 6 - v13;
  result = CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
  if ( (int)result >= 0 )
  {
    result = CPersistStreamInit::WriteTag(this, 0x30u, v23);
    if ( (int)result >= 0 )
    {
      result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
      if ( (int)result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, v14, v23);
        if ( (int)result >= 0 )
        {
          result = CPersistStreamInit::WriteAttributeDefinition(
                     this,
                     *(void **)(*((_QWORD *)this + 9) + 48LL),
                     v8,
                     v16,
                     0,
                     0);
          if ( (int)result >= 0 )
          {
            ++*((_DWORD *)this + 12);
            if ( !*(_BYTE *)(*((_QWORD *)a2 + 8) + 8 * v7 + 8)
              || (result = CPersistStreamInit::WriteAttributeDefinition(
                             this,
                             *(void **)(*((_QWORD *)this + 9) + 1728LL),
                             v11,
                             v17,
                             65,
                             1),
                  (int)result >= 0) )
            {
              Ordinal = CMetaData::mdGetOrdinal(a2, a3);
              CPersistStreamInit::_ulto(this, Ordinal, v24, v19, v22);
              result = CPersistStreamInit::WriteAttributeDefinition(
                         this,
                         *(void **)(*((_QWORD *)this + 9) + 1680LL),
                         v24,
                         v20,
                         65,
                         0);
              if ( (int)result >= 0 )
              {
                Flags = CMetaData::mdGetFlags(a2, a3);
                result = CPersistStreamInit::WriteColumnFlags(this, Flags);
                if ( (int)result >= 0 )
                {
                  result = CPersistStreamInit::WriteColumnMetaData(this, a2, a3);
                  if ( (int)result >= 0 )
                  {
                    result = CPersistStreamInit::WriteTag(this, 0x31u, v23);
                    if ( (int)result >= 0 )
                    {
                      result = CPersistStreamInit::WriteTag(this, 0x28u, v23);
                      if ( (int)result >= 0 )
                      {
                        result = CPersistStreamInit::WriteColumnTypeInfo(this, a2, a3);
                        if ( (int)result >= 0 )
                        {
                          CPersistStreamInit::Indent(this, --*((_DWORD *)this + 12));
                          result = CPersistStreamInit::WriteTag(this, 0x33u, v23);
                          if ( (int)result >= 0 )
                          {
                            result = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
                            if ( (int)result >= 0 )
                            {
                              result = CPersistStreamInit::WriteTag(this, v14, v23);
                              if ( (int)result >= 0 )
                              {
                                result = CPersistStreamInit::WriteTag(this, 0x31u, v23);
                                if ( (int)result >= 0 )
                                  return CPersistStreamInit::WriteTag(this, 0x28u, v23);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d42c  push    rbx
0x18001d42e  push    rbp
0x18001d42f  push    rsi
0x18001d430  push    rdi
0x18001d431  push    r12
0x18001d433  push    r14
0x18001d435  push    r15
0x18001d437  sub     rsp, 250h
0x18001d43e  mov     rax, cs:__security_cookie
0x18001d445  xor     rax, rsp
0x18001d448  mov     [rsp+288h+var_48], rax
0x18001d450  mov     rax, [rdx+40h]
0x18001d454  mov     rdi, rdx
0x18001d457  movzx   esi, r8w
0x18001d45b  mov     rbx, rcx
0x18001d45e  mov     [rsp+288h+var_258], 0
0x18001d466  mov     r14d, esi
0x18001d469  add     r14, r14
0x18001d46c  movzx   edx, si; unsigned __int16
0x18001d46f  mov     rcx, rdi; this
0x18001d472  mov     r12, [rax+r14*8]
0x18001d476  call    ?mdGetName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetName(ushort)
0x18001d47b  test    rax, rax
0x18001d47e  lea     r15, ?wszZls@@3PAGA; ushort near * wszZls
0x18001d485  movzx   edx, si; unsigned __int16
0x18001d488  cmovnz  r15, rax
0x18001d48c  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001d491  bt      eax, 0Dh
0x18001d495  jb      short loc_18001D4AD
0x18001d497  mov     rcx, rdi; this
0x18001d49a  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001d49f  mov     ecx, 88h
0x18001d4a4  cmp     ax, cx
0x18001d4a7  jz      short loc_18001D4AD
0x18001d4a9  xor     eax, eax
0x18001d4ab  jmp     short loc_18001D4B2
0x18001d4ad  mov     eax, 1
0x18001d4b2  mov     edx, [rbx+30h]; unsigned int
0x18001d4b5  neg     eax
0x18001d4b7  mov     rcx, rbx; this
0x18001d4ba  sbb     bpl, bpl
0x18001d4bd  add     bpl, 6
0x18001d4c1  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001d4c6  test    eax, eax
0x18001d4c8  js      loc_18001D685
0x18001d4ce  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d4d3  mov     dl, 30h ; '0'; unsigned __int8
0x18001d4d5  mov     rcx, rbx; this
0x18001d4d8  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d4dd  test    eax, eax
0x18001d4df  js      loc_18001D685
0x18001d4e5  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001d4e7  mov     rcx, rbx; this
0x18001d4ea  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001d4ef  test    eax, eax
0x18001d4f1  js      loc_18001D685
0x18001d4f7  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d4fc  mov     dl, bpl; unsigned __int8
0x18001d4ff  mov     rcx, rbx; this
0x18001d502  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d507  test    eax, eax
0x18001d509  js      loc_18001D685
0x18001d50f  mov     rdx, [rbx+48h]
0x18001d513  mov     r8, r12; unsigned __int16 *
0x18001d516  mov     [rsp+288h+var_260], 0; bool
0x18001d51b  mov     rcx, rbx; this
0x18001d51e  mov     [rsp+288h+var_268], 0; char
0x18001d523  mov     rdx, [rdx+30h]; void *
0x18001d527  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d52c  test    eax, eax
0x18001d52e  js      loc_18001D685
0x18001d534  inc     dword ptr [rbx+30h]
0x18001d537  mov     rax, [rdi+40h]
0x18001d53b  cmp     byte ptr [rax+r14*8+8], 0
0x18001d541  jz      short loc_18001D56B
0x18001d543  mov     rdx, [rbx+48h]
0x18001d547  mov     r8, r15; unsigned __int16 *
0x18001d54a  mov     [rsp+288h+var_260], 1; bool
0x18001d54f  mov     rcx, rbx; this
0x18001d552  mov     [rsp+288h+var_268], 41h ; 'A'; int
0x18001d557  mov     rdx, [rdx+6C0h]; void *
0x18001d55e  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d563  test    eax, eax
0x18001d565  js      loc_18001D685
0x18001d56b  movzx   edx, si; unsigned __int16
0x18001d56e  mov     rcx, rdi; this
0x18001d571  call    ?mdGetOrdinal@CMetaData@@QEAAKG@Z; CMetaData::mdGetOrdinal(ushort)
0x18001d576  mov     edx, eax; unsigned int
0x18001d578  lea     r8, [rsp+288h+var_248]; void *
0x18001d57d  mov     rcx, rbx; this
0x18001d580  call    ?_ulto@CPersistStreamInit@@AEBAXKPEAX_KH@Z; CPersistStreamInit::_ulto(ulong,void *,unsigned __int64,int)
0x18001d585  mov     rdx, [rbx+48h]
0x18001d589  lea     r8, [rsp+288h+var_248]; unsigned __int16 *
0x18001d58e  mov     [rsp+288h+var_260], 0; bool
0x18001d593  mov     rcx, rbx; this
0x18001d596  mov     [rsp+288h+var_268], 41h ; 'A'; char
0x18001d59b  mov     rdx, [rdx+690h]; void *
0x18001d5a2  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d5a7  test    eax, eax
0x18001d5a9  js      loc_18001D685
0x18001d5af  movzx   edx, si; unsigned __int16
0x18001d5b2  mov     rcx, rdi; this
0x18001d5b5  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001d5ba  mov     edx, eax; unsigned int
0x18001d5bc  mov     rcx, rbx; this
0x18001d5bf  call    ?WriteColumnFlags@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::WriteColumnFlags(ulong)
0x18001d5c4  test    eax, eax
0x18001d5c6  js      loc_18001D685
0x18001d5cc  movzx   r8d, si; unsigned __int16
0x18001d5d0  mov     rdx, rdi; struct CRowInfo *
0x18001d5d3  mov     rcx, rbx; this
0x18001d5d6  call    ?WriteColumnMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnMetaData(CRowInfo &,ushort)
0x18001d5db  test    eax, eax
0x18001d5dd  js      loc_18001D685
0x18001d5e3  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d5e8  mov     dl, 31h ; '1'; unsigned __int8
0x18001d5ea  mov     rcx, rbx; this
0x18001d5ed  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d5f2  test    eax, eax
0x18001d5f4  js      loc_18001D685
0x18001d5fa  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d5ff  mov     dl, 28h ; '('; unsigned __int8
0x18001d601  mov     rcx, rbx; this
0x18001d604  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d609  test    eax, eax
0x18001d60b  js      short loc_18001D685
0x18001d60d  movzx   r8d, si; unsigned __int16
0x18001d611  mov     rdx, rdi; struct CRowInfo *
0x18001d614  mov     rcx, rbx; this
0x18001d617  call    ?WriteColumnTypeInfo@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z; CPersistStreamInit::WriteColumnTypeInfo(CRowInfo &,ushort)
0x18001d61c  test    eax, eax
0x18001d61e  js      short loc_18001D685
0x18001d620  dec     dword ptr [rbx+30h]
0x18001d623  mov     rcx, rbx; this
0x18001d626  mov     edx, [rbx+30h]; unsigned int
0x18001d629  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001d62e  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d633  mov     dl, 33h ; '3'; unsigned __int8
0x18001d635  mov     rcx, rbx; this
0x18001d638  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d63d  test    eax, eax
0x18001d63f  js      short loc_18001D685
0x18001d641  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001d643  mov     rcx, rbx; this
0x18001d646  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001d64b  test    eax, eax
0x18001d64d  js      short loc_18001D685
0x18001d64f  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d654  mov     dl, bpl; unsigned __int8
0x18001d657  mov     rcx, rbx; this
0x18001d65a  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d65f  test    eax, eax
0x18001d661  js      short loc_18001D685
0x18001d663  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d668  mov     dl, 31h ; '1'; unsigned __int8
0x18001d66a  mov     rcx, rbx; this
0x18001d66d  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d672  test    eax, eax
0x18001d674  js      short loc_18001D685
0x18001d676  lea     r8, [rsp+288h+var_258]; unsigned int *
0x18001d67b  mov     dl, 28h ; '('; unsigned __int8
0x18001d67d  mov     rcx, rbx; this
0x18001d680  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d685  mov     rcx, [rsp+288h+var_48]
0x18001d68d  xor     rcx, rsp; StackCookie
0x18001d690  call    __security_check_cookie
0x18001d695  add     rsp, 250h
0x18001d69c  pop     r15
0x18001d69e  pop     r14
0x18001d6a0  pop     r12
0x18001d6a2  pop     rdi
0x18001d6a3  pop     rsi
0x18001d6a4  pop     rbp
0x18001d6a5  pop     rbx
0x18001d6a6  retn
```
