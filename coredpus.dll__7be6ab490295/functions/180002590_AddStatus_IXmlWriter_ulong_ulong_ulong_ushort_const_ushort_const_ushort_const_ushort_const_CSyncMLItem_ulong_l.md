# AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)

- ea: `0x180002590`
- end: `0x18000284d`
- name: `?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z`
- size: `701`
- prototype: `__int64 __fastcall(struct IXmlWriter *, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CSyncMLItem **, unsigned int, int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e490`
- `0x18001fee0`
- `0x1800208f0`
- `0x180020b30`
- `0x180020d80`

## callees

- `0x180002380`
- `0x180002590`
- `0x180002860`
- `0x1800029b0`
- `0x180003cd0`
- `0x180030010`

## pseudocode

```c
HRESULT __fastcall AddStatus(
        struct IXmlWriter *a1,
        int a2,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        struct CSyncMLItem **a9,
        unsigned int a10,
        unsigned int a11,
        int a12)
{
  HRESULT result; // eax
  STRSAFE_PCNZWCH v17; // rdi
  __int64 v18; // r10
  wchar_t *v19; // r15
  __int64 ElementName; // rax
  const unsigned __int16 *v21; // rsi
  __int64 v22; // rax
  const unsigned __int16 *v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // ebp
  struct CSyncMLItem **v28; // r14
  __int64 i; // rsi
  __int64 v30; // [rsp+20h] [rbp-48h]
  size_t pcchLength; // [rsp+70h] [rbp+8h] BYREF

  if ( !a1 || !psz )
    return -2147024809;
  result = StringLengthWorkerW(psz, 0x7FFFFFFFu, &pcchLength);
  if ( result < 0 )
    return result;
  v17 = off_18003E2E0;
  if ( !off_18003E2E0 )
    return -2147024809;
  result = StringLengthWorkerW(off_18003E2E0, 0x7FFFFFFFu, &pcchLength);
  if ( result >= 0 )
  {
    v19 = off_18003E2D8[0];
    result = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))a1->lpVtbl->WriteStartElement)(
               a1,
               0,
               v18,
               0);
    if ( result >= 0 )
    {
      result = AddSubnode(a1, 0, off_18003E258[0], 1, a3);
      if ( result >= 0 )
      {
        LODWORD(v30) = a4;
        result = AddSubnode(a1, 0, off_18003E290[0], 1, v30);
        if ( result >= 0 )
        {
          if ( a5 )
          {
            result = AddSubnode(a1, 0, off_18003E260[0], 2, a5);
            if ( result < 0 )
              return result;
          }
          else
          {
            ElementName = GetElementName(6);
            result = AddSubnode(a1, 0, ElementName, 2, &word_180032B28);
            if ( result < 0 )
              return result;
          }
          result = AddSubnode(a1, 0, off_18003E250[0], 2, a6);
          if ( result >= 0 )
          {
            v21 = a8;
            if ( !a8 || (v22 = GetElementName(18), result = AddSubnode(a1, 0, v22, 2, v21), result >= 0) )
            {
              v23 = a7;
              if ( !a7 || (v24 = GetElementName(16), result = AddSubnode(a1, 0, v24, 2, v23), result >= 0) )
              {
                v25 = GetElementName(21);
                v26 = a11;
                if ( !a12 )
                  v26 = 0;
                result = AddSubnodeWithOriginalError(a1, v26, 0, v25, 1, a2);
                if ( result >= 0 )
                {
                  v27 = a10;
                  if ( a10 )
                  {
                    v28 = a9;
                    if ( a9 )
                    {
                      for ( i = 0; (unsigned int)i < v27; i = (unsigned int)(i + 1) )
                      {
                        result = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, STRSAFE_PCNZWCH, _QWORD))a1->lpVtbl->WriteStartElement)(
                                   a1,
                                   0,
                                   v17,
                                   0);
                        if ( result < 0 )
                          return result;
                        result = AddSubnode(a1, 0, v19, 2, *((_QWORD *)v28[i] + 10));
                        if ( result < 0 )
                          return result;
                        result = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndElement)(a1);
                        if ( result < 0 )
                          return result;
                      }
                    }
                  }
                  return ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndElement)(a1);
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
0x180002590  push    rbx
0x180002592  push    rbp
0x180002593  push    rsi
0x180002594  push    rdi
0x180002595  push    r14
0x180002597  push    r15
0x180002599  sub     rsp, 38h
0x18000259d  mov     ebp, r9d
0x1800025a0  mov     esi, r8d
0x1800025a3  mov     r14d, edx
0x1800025a6  mov     rbx, rcx
0x1800025a9  test    rcx, rcx
0x1800025ac  jz      loc_18000283A
0x1800025b2  mov     r10, cs:psz
0x1800025b9  test    r10, r10
0x1800025bc  jz      loc_18000283A
0x1800025c2  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x1800025c7  mov     edx, 7FFFFFFFh; cchMax
0x1800025cc  mov     rcx, r10; psz
0x1800025cf  call    StringLengthWorkerW
0x1800025d4  test    eax, eax
0x1800025d6  js      loc_18000283F
0x1800025dc  mov     rdi, cs:off_18003E2E0; "Item"
0x1800025e3  test    rdi, rdi
0x1800025e6  jz      loc_18000283A
0x1800025ec  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x1800025f1  mov     edx, 7FFFFFFFh; cchMax
0x1800025f6  mov     rcx, rdi; psz
0x1800025f9  call    StringLengthWorkerW
0x1800025fe  test    eax, eax
0x180002600  js      loc_18000283F
0x180002606  mov     rax, [rbx]
0x180002609  xor     r9d, r9d
0x18000260c  mov     r15, cs:off_18003E2D8; "Data"
0x180002613  mov     r8, r10
0x180002616  xor     edx, edx
0x180002618  mov     rcx, rbx
0x18000261b  mov     rax, [rax+0D8h]
0x180002622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002627  test    eax, eax
0x180002629  js      loc_18000283F
0x18000262f  mov     r8, cs:off_18003E258; "CmdID"
0x180002636  mov     r9d, 1
0x18000263c  xor     edx, edx
0x18000263e  mov     dword ptr [rsp+68h+var_48], esi
0x180002642  mov     rcx, rbx
0x180002645  call    AddSubnode
0x18000264a  test    eax, eax
0x18000264c  js      loc_18000283F
0x180002652  mov     r8, cs:off_18003E290; "MsgRef"
0x180002659  mov     r9d, 1
0x18000265f  xor     edx, edx
0x180002661  mov     dword ptr [rsp+68h+var_48], ebp
0x180002665  mov     rcx, rbx
0x180002668  call    AddSubnode
0x18000266d  test    eax, eax
0x18000266f  js      loc_18000283F
0x180002675  mov     rax, [rsp+68h+arg_20]
0x18000267d  test    rax, rax
0x180002680  jnz     short loc_1800026B4
0x180002682  mov     ecx, 6
0x180002687  call    GetElementName
0x18000268c  mov     r8, rax
0x18000268f  xor     edx, edx
0x180002691  lea     rax, word_180032B28
0x180002698  mov     r9d, 2
0x18000269e  mov     rcx, rbx
0x1800026a1  mov     [rsp+68h+var_48], rax
0x1800026a6  call    AddSubnode
0x1800026ab  test    eax, eax
0x1800026ad  jns     short loc_1800026D8
0x1800026af  jmp     loc_18000283F
0x1800026b4  mov     r8, cs:off_18003E260; "CmdRef"
0x1800026bb  mov     r9d, 2
0x1800026c1  xor     edx, edx
0x1800026c3  mov     [rsp+68h+var_48], rax
0x1800026c8  mov     rcx, rbx
0x1800026cb  call    AddSubnode
0x1800026d0  test    eax, eax
0x1800026d2  js      loc_18000283F
0x1800026d8  mov     rax, [rsp+68h+arg_28]
0x1800026e0  mov     r9d, 2
0x1800026e6  mov     r8, cs:off_18003E250; "Cmd"
0x1800026ed  xor     edx, edx
0x1800026ef  mov     rcx, rbx
0x1800026f2  mov     [rsp+68h+var_48], rax
0x1800026f7  call    AddSubnode
0x1800026fc  test    eax, eax
0x1800026fe  js      loc_18000283F
0x180002704  mov     rsi, [rsp+68h+arg_38]
0x18000270c  test    rsi, rsi
0x18000270f  jz      short loc_18000273B
0x180002711  mov     ecx, 12h
0x180002716  call    GetElementName
0x18000271b  mov     r8, rax
0x18000271e  mov     [rsp+68h+var_48], rsi
0x180002723  xor     edx, edx
0x180002725  mov     r9d, 2
0x18000272b  mov     rcx, rbx
0x18000272e  call    AddSubnode
0x180002733  test    eax, eax
0x180002735  js      loc_18000283F
0x18000273b  mov     rsi, [rsp+68h+arg_30]
0x180002743  test    rsi, rsi
0x180002746  jz      short loc_180002772
0x180002748  mov     ecx, 10h
0x18000274d  call    GetElementName
0x180002752  mov     r8, rax
0x180002755  mov     [rsp+68h+var_48], rsi
0x18000275a  xor     edx, edx
0x18000275c  mov     r9d, 2
0x180002762  mov     rcx, rbx
0x180002765  call    AddSubnode
0x18000276a  test    eax, eax
0x18000276c  js      loc_18000283F
0x180002772  mov     ecx, 15h
0x180002777  call    GetElementName
0x18000277c  mov     edx, [rsp+68h+arg_50]
0x180002783  mov     r9, rax
0x180002786  xor     eax, eax
0x180002788  mov     [rsp+68h+var_40], r14d
0x18000278d  cmp     [rsp+68h+arg_58], eax
0x180002794  mov     rcx, rbx
0x180002797  mov     dword ptr [rsp+68h+var_48], 1
0x18000279f  cmovz   edx, eax
0x1800027a2  xor     r8d, r8d
0x1800027a5  call    ?AddSubnodeWithOriginalError@@YAJPEAUIXmlWriter@@JPEBG1W4value_t@@ZZ; AddSubnodeWithOriginalError(IXmlWriter *,long,ushort const *,ushort const *,value_t,...)
0x1800027aa  test    eax, eax
0x1800027ac  js      loc_18000283F
0x1800027b2  mov     ebp, [rsp+68h+arg_48]
0x1800027b9  test    ebp, ebp
0x1800027bb  jz      short loc_180002829
0x1800027bd  mov     r14, [rsp+68h+arg_40]
0x1800027c5  test    r14, r14
0x1800027c8  jz      short loc_180002829
0x1800027ca  xor     esi, esi
0x1800027cc  cmp     esi, ebp
0x1800027ce  jnb     short loc_180002829
0x1800027d0  mov     rax, [rbx]
0x1800027d3  xor     r9d, r9d
0x1800027d6  mov     r8, rdi
0x1800027d9  xor     edx, edx
0x1800027db  mov     rcx, rbx
0x1800027de  mov     rax, [rax+0D8h]
0x1800027e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ea  test    eax, eax
0x1800027ec  js      short loc_18000283F
0x1800027ee  mov     rcx, [r14+rsi*8]
0x1800027f2  mov     r9d, 2
0x1800027f8  mov     r8, r15
0x1800027fb  xor     edx, edx
0x1800027fd  mov     rax, [rcx+50h]
0x180002801  mov     rcx, rbx
0x180002804  mov     [rsp+68h+var_48], rax
0x180002809  call    AddSubnode
0x18000280e  test    eax, eax
0x180002810  js      short loc_18000283F
0x180002812  mov     rax, [rbx]
0x180002815  mov     rcx, rbx
0x180002818  mov     rax, [rax+78h]
0x18000281c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002821  test    eax, eax
0x180002823  js      short loc_18000283F
0x180002825  inc     esi
0x180002827  jmp     short loc_1800027CC
0x180002829  mov     rax, [rbx]
0x18000282c  mov     rcx, rbx
0x18000282f  mov     rax, [rax+78h]
0x180002833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002838  jmp     short loc_18000283F
0x18000283a  mov     eax, 80070057h
0x18000283f  add     rsp, 38h
0x180002843  pop     r15
0x180002845  pop     r14
0x180002847  pop     rdi
0x180002848  pop     rsi
0x180002849  pop     rbp
0x18000284a  pop     rbx
0x18000284b  retn
```
