# CPersistStreamInit::WriteColumnMetaData(CRowInfo &,ushort)

- ea: `0x18001d828`
- end: `0x18001db1c`
- name: `?WriteColumnMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `756`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001d42c`

## callees

- `0x180002de4`
- `0x180002e2c`
- `0x180002e74`
- `0x180002ebc`
- `0x180002f04`
- `0x180002f4c`
- `0x180002f94`
- `0x18001b558`
- `0x18001d054`
- `0x18001d1c8`
- `0x18001d828`
- `0x18001ed5c`
- `0x18001fe94`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteColumnMetaData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  __int64 v4; // rsi
  char *v6; // r14
  unsigned __int16 *BaseCatalogName; // rax
  bool v8; // r9
  int v9; // r10d
  unsigned __int16 *BaseSchemaName; // rax
  bool v11; // r9
  unsigned __int16 *BaseTableName; // rax
  bool v13; // r9
  bool v14; // r9
  unsigned __int16 *BaseColumnName; // rax
  bool v16; // r9
  __int64 v17; // rcx
  __int16 v18; // cx
  __int64 v19; // rax
  bool v20; // r9
  unsigned int CalculationInfoSize; // ebp
  unsigned __int8 *CalculationInfo; // rax
  unsigned int v24; // [rsp+78h] [rbp+10h] BYREF

  v4 = a3;
  v6 = (char *)this + 72;
  v24 = 0;
  if ( CMetaData::mdGetBaseCatalogName(a2, a3) )
  {
    BaseCatalogName = CMetaData::mdGetBaseCatalogName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1920LL),
           BaseCatalogName,
           v8,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseSchemaName(a2, v4) )
  {
    BaseSchemaName = CMetaData::mdGetBaseSchemaName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1936LL),
           BaseSchemaName,
           v11,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseTableName(a2, v4) )
  {
    BaseTableName = CMetaData::mdGetBaseTableName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1952LL),
           BaseTableName,
           v13,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  if ( CMetaData::mdGetBaseColumnName(a2, v4) )
  {
    BaseColumnName = CMetaData::mdGetBaseColumnName(a2, v4);
    v9 = CPersistStreamInit::WriteAttributeDefinition(
           this,
           *(void **)(*(_QWORD *)v6 + 1968LL),
           BaseColumnName,
           v16,
           65,
           1);
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  v17 = *((_QWORD *)a2 + 1);
  if ( v17 )
  {
    v18 = *(_WORD *)(168 * v4 + v17 + 112);
LABEL_13:
    if ( v18 )
    {
      v9 = CPersistStreamInit::WriteAttributeDefinition(
             this,
             *(void **)(*((_QWORD *)this + 9) + 2128LL),
             *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
             v14,
             65,
             0);
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
    goto LABEL_15;
  }
  v19 = *((_QWORD *)a2 + 4);
  if ( !*(_DWORD *)(9648 * v4 + v19 + 9584) )
  {
    v18 = *(_WORD *)(9648 * v4 + v19 + 9580);
    goto LABEL_13;
  }
LABEL_15:
  if ( (unsigned __int16)v4 < *((_WORD *)a2 + 1)
    || (v9 = CPersistStreamInit::WriteAttributeDefinition(
               this,
               *(void **)(*((_QWORD *)this + 9) + 2144LL),
               *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
               v14,
               65,
               0),
        v9 >= 0) )
  {
    if ( !CMetaData::mdGetAutoIncrement(a2, v4)
      || (v9 = CPersistStreamInit::WriteAttributeDefinition(
                 this,
                 *(void **)(*((_QWORD *)this + 9) + 2048LL),
                 *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                 v20,
                 65,
                 0),
          v9 >= 0) )
    {
      CalculationInfoSize = CMetaData::mdGetCalculationInfoSize(a2, v4);
      if ( CalculationInfoSize )
      {
        v9 = CPersistStreamInit::Write(
               this,
               *(_BYTE **)(*((_QWORD *)this + 9) + 704LL),
               *(unsigned __int8 *)(*((_QWORD *)this + 9) + 712LL),
               &v24,
               1);
        if ( v9 >= 0 )
        {
          v9 = CPersistStreamInit::WriteNamespace(this, 0x41u);
          if ( v9 >= 0 )
          {
            v9 = CPersistStreamInit::WriteTag(this, 0x8Fu, &v24);
            if ( v9 >= 0 )
            {
              v9 = CPersistStreamInit::WriteTag(this, 0x2Bu, &v24);
              if ( v9 >= 0 )
              {
                v9 = CPersistStreamInit::WriteTag(this, 0x29u, &v24);
                if ( v9 >= 0 )
                {
                  CalculationInfo = CMetaData::mdGetCalculationInfo(a2, v4);
                  v9 = CPersistStreamInit::BinaryOut(this, CalculationInfo, CalculationInfoSize);
                  if ( v9 >= 0 )
                    return (unsigned int)CPersistStreamInit::WriteTag(this, 0x29u, &v24);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d828  push    rbx
0x18001d82a  push    rbp
0x18001d82b  push    rsi
0x18001d82c  push    rdi
0x18001d82d  push    r14
0x18001d82f  push    r15
0x18001d831  sub     rsp, 38h
0x18001d835  mov     rdi, rdx
0x18001d838  movzx   esi, r8w
0x18001d83c  mov     rbx, rcx
0x18001d83f  lea     r14, [rcx+48h]
0x18001d843  xor     r15d, r15d
0x18001d846  movzx   edx, si; unsigned __int16
0x18001d849  mov     rcx, rdi; this
0x18001d84c  mov     [rsp+68h+arg_8], r15d
0x18001d851  mov     r10d, r15d
0x18001d854  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x18001d859  test    rax, rax
0x18001d85c  jz      short loc_18001D893
0x18001d85e  movzx   edx, si; unsigned __int16
0x18001d861  mov     rcx, rdi; this
0x18001d864  call    ?mdGetBaseCatalogName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseCatalogName(ushort)
0x18001d869  mov     rdx, [r14]
0x18001d86c  mov     r8, rax; unsigned __int16 *
0x18001d86f  mov     [rsp+68h+var_40], 1; bool
0x18001d874  mov     rcx, rbx; this
0x18001d877  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d87c  mov     rdx, [rdx+780h]; void *
0x18001d883  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d888  mov     r10d, eax
0x18001d88b  test    eax, eax
0x18001d88d  js      loc_18001DB0B
0x18001d893  movzx   edx, si; unsigned __int16
0x18001d896  mov     rcx, rdi; this
0x18001d899  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x18001d89e  test    rax, rax
0x18001d8a1  jz      short loc_18001D8D8
0x18001d8a3  movzx   edx, si; unsigned __int16
0x18001d8a6  mov     rcx, rdi; this
0x18001d8a9  call    ?mdGetBaseSchemaName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseSchemaName(ushort)
0x18001d8ae  mov     rdx, [r14]
0x18001d8b1  mov     r8, rax; unsigned __int16 *
0x18001d8b4  mov     [rsp+68h+var_40], 1; bool
0x18001d8b9  mov     rcx, rbx; this
0x18001d8bc  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d8c1  mov     rdx, [rdx+790h]; void *
0x18001d8c8  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d8cd  mov     r10d, eax
0x18001d8d0  test    eax, eax
0x18001d8d2  js      loc_18001DB0B
0x18001d8d8  movzx   edx, si; unsigned __int16
0x18001d8db  mov     rcx, rdi; this
0x18001d8de  call    ?mdGetBaseTableName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseTableName(ushort)
0x18001d8e3  test    rax, rax
0x18001d8e6  jz      short loc_18001D91D
0x18001d8e8  movzx   edx, si; unsigned __int16
0x18001d8eb  mov     rcx, rdi; this
0x18001d8ee  call    ?mdGetBaseTableName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseTableName(ushort)
0x18001d8f3  mov     rdx, [r14]
0x18001d8f6  mov     r8, rax; unsigned __int16 *
0x18001d8f9  mov     [rsp+68h+var_40], 1; bool
0x18001d8fe  mov     rcx, rbx; this
0x18001d901  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d906  mov     rdx, [rdx+7A0h]; void *
0x18001d90d  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d912  mov     r10d, eax
0x18001d915  test    eax, eax
0x18001d917  js      loc_18001DB0B
0x18001d91d  movzx   edx, si; unsigned __int16
0x18001d920  mov     rcx, rdi; this
0x18001d923  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x18001d928  test    rax, rax
0x18001d92b  jz      short loc_18001D962
0x18001d92d  movzx   edx, si; unsigned __int16
0x18001d930  mov     rcx, rdi; this
0x18001d933  call    ?mdGetBaseColumnName@CMetaData@@QEAAPEAGG@Z; CMetaData::mdGetBaseColumnName(ushort)
0x18001d938  mov     rdx, [r14]
0x18001d93b  mov     r8, rax; unsigned __int16 *
0x18001d93e  mov     [rsp+68h+var_40], 1; bool
0x18001d943  mov     rcx, rbx; this
0x18001d946  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d94b  mov     rdx, [rdx+7B0h]; void *
0x18001d952  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d957  mov     r10d, eax
0x18001d95a  test    eax, eax
0x18001d95c  js      loc_18001DB0B
0x18001d962  mov     rcx, [rdi+8]
0x18001d966  mov     rax, rsi
0x18001d969  test    rcx, rcx
0x18001d96c  jz      short loc_18001D97C
0x18001d96e  imul    rax, 0A8h
0x18001d975  movzx   ecx, word ptr [rax+rcx+70h]
0x18001d97a  jmp     short loc_18001D999
0x18001d97c  imul    rcx, rax, 25B0h
0x18001d983  mov     rax, [rdi+20h]
0x18001d987  cmp     [rcx+rax+2570h], r15d
0x18001d98f  jnz     short loc_18001D9CD
0x18001d991  movzx   ecx, word ptr [rcx+rax+256Ch]
0x18001d999  test    cx, cx
0x18001d99c  jz      short loc_18001D9CD
0x18001d99e  mov     rdx, [rbx+48h]
0x18001d9a2  mov     rcx, rbx; this
0x18001d9a5  mov     [rsp+68h+var_40], r15b; bool
0x18001d9aa  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d9af  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001d9b6  mov     rdx, [rdx+850h]; void *
0x18001d9bd  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d9c2  mov     r10d, eax
0x18001d9c5  test    eax, eax
0x18001d9c7  js      loc_18001DB0B
0x18001d9cd  cmp     si, [rdi+2]
0x18001d9d1  jb      short loc_18001DA02
0x18001d9d3  mov     rdx, [rbx+48h]
0x18001d9d7  mov     rcx, rbx; this
0x18001d9da  mov     [rsp+68h+var_40], r15b; bool
0x18001d9df  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001d9e4  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001d9eb  mov     rdx, [rdx+860h]; void *
0x18001d9f2  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d9f7  mov     r10d, eax
0x18001d9fa  test    eax, eax
0x18001d9fc  js      loc_18001DB0B
0x18001da02  movzx   edx, si; unsigned __int16
0x18001da05  mov     rcx, rdi; this
0x18001da08  call    ?mdGetAutoIncrement@CMetaData@@QEAAFG@Z; CMetaData::mdGetAutoIncrement(ushort)
0x18001da0d  test    ax, ax
0x18001da10  jz      short loc_18001DA41
0x18001da12  mov     rdx, [rbx+48h]
0x18001da16  mov     rcx, rbx; this
0x18001da19  mov     [rsp+68h+var_40], r15b; bool
0x18001da1e  mov     [rsp+68h+var_48], 41h ; 'A'; char
0x18001da23  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001da2a  mov     rdx, [rdx+800h]; void *
0x18001da31  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001da36  mov     r10d, eax
0x18001da39  test    eax, eax
0x18001da3b  js      loc_18001DB0B
0x18001da41  movzx   edx, si; unsigned __int16
0x18001da44  mov     rcx, rdi; this
0x18001da47  call    ?mdGetCalculationInfoSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetCalculationInfoSize(ushort)
0x18001da4c  mov     ebp, eax
0x18001da4e  test    eax, eax
0x18001da50  jz      loc_18001DB0B
0x18001da56  mov     rdx, [rbx+48h]
0x18001da5a  lea     r9, [rsp+68h+arg_8]; unsigned int *
0x18001da5f  mov     rcx, rbx; this
0x18001da62  mov     [rsp+68h+var_48], 1; bool
0x18001da67  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001da6f  mov     rdx, [rdx+2C0h]; Src
0x18001da76  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001da7b  mov     r10d, eax
0x18001da7e  test    eax, eax
0x18001da80  js      loc_18001DB0B
0x18001da86  mov     dl, 41h ; 'A'; unsigned __int8
0x18001da88  mov     rcx, rbx; this
0x18001da8b  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001da90  mov     r10d, eax
0x18001da93  test    eax, eax
0x18001da95  js      short loc_18001DB0B
0x18001da97  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001da9c  mov     dl, 8Fh; unsigned __int8
0x18001da9e  mov     rcx, rbx; this
0x18001daa1  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001daa6  mov     r10d, eax
0x18001daa9  test    eax, eax
0x18001daab  js      short loc_18001DB0B
0x18001daad  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001dab2  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001dab4  mov     rcx, rbx; this
0x18001dab7  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dabc  mov     r10d, eax
0x18001dabf  test    eax, eax
0x18001dac1  js      short loc_18001DB0B
0x18001dac3  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001dac8  mov     dl, 29h ; ')'; unsigned __int8
0x18001daca  mov     rcx, rbx; this
0x18001dacd  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dad2  mov     r10d, eax
0x18001dad5  test    eax, eax
0x18001dad7  js      short loc_18001DB0B
0x18001dad9  movzx   edx, si; unsigned __int16
0x18001dadc  mov     rcx, rdi; this
0x18001dadf  call    ?mdGetCalculationInfo@CMetaData@@QEAAPEAEG@Z; CMetaData::mdGetCalculationInfo(ushort)
0x18001dae4  mov     rdx, rax; unsigned __int8 *
0x18001dae7  mov     r8d, ebp; unsigned int
0x18001daea  mov     rcx, rbx; this
0x18001daed  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001daf2  mov     r10d, eax
0x18001daf5  test    eax, eax
0x18001daf7  js      short loc_18001DB0B
0x18001daf9  lea     r8, [rsp+68h+arg_8]; unsigned int *
0x18001dafe  mov     dl, 29h ; ')'; unsigned __int8
0x18001db00  mov     rcx, rbx; this
0x18001db03  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001db08  mov     r10d, eax
0x18001db0b  mov     eax, r10d
0x18001db0e  add     rsp, 38h
0x18001db12  pop     r15
0x18001db14  pop     r14
0x18001db16  pop     rdi
0x18001db17  pop     rsi
0x18001db18  pop     rbp
0x18001db19  pop     rbx
0x18001db1a  retn
```
