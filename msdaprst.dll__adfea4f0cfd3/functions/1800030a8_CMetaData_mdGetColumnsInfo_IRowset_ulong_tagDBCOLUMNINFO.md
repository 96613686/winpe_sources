# CMetaData::mdGetColumnsInfo(IRowset *,ulong,tagDBCOLUMNINFO *)

- ea: `0x1800030a8`
- end: `0x1800031de`
- name: `?mdGetColumnsInfo@CMetaData@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z`
- size: `310`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned int, struct tagDBCOLUMNINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180002c1c`

## callees

- `0x180002fdc`
- `0x1800030a8`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0aa`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800030d3`
- `ole32!CoTaskMemAlloc` at `0x1800030d3`

## pseudocode

```c
void __fastcall CMetaData::mdGetColumnsInfo(
        CMetaData *this,
        struct IRowset *a2,
        unsigned int a3,
        struct tagDBCOLUMNINFO *a4)
{
  SIZE_T v6; // rbx
  unsigned __int16 v7; // si
  void *v9; // rax
  unsigned __int16 v10; // r15
  unsigned __int16 v11; // bx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D uGuid; // xmm1
  __int128 v15; // xmm0
  int ColInfo; // eax
  unsigned __int16 v17; // cx
  struct tagDBCOLUMNINFO v18; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int16 v19; // [rsp+D0h] [rbp+18h] BYREF

  v6 = 168LL * a3;
  v7 = 0;
  v19 = 0;
  v9 = CoTaskMemAlloc(v6);
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049448[0] )
        bidTraceW(off_1800491B8[0], 540672, off_180049448[0], 2147942414LL, 528);
    }
    ThrowHR(-2147024882);
  }
  memset_0(v9, 0, v6);
  v10 = 0;
  v11 = 0;
  if ( a3 )
  {
    do
    {
      v12 = *(_OWORD *)&a4[v10].iOrdinal;
      *(_OWORD *)&v18.pwszName = *(_OWORD *)&a4[v10].pwszName;
      v13 = *(_OWORD *)&a4[v10].ulColumnSize;
      *(_OWORD *)&v18.iOrdinal = v12;
      uGuid = a4[v10].columnid.uGuid;
      *(_OWORD *)&v18.ulColumnSize = v13;
      v15 = *(_OWORD *)&a4[v10].columnid.eKind;
      v18.columnid.uGuid = uGuid;
      *(_OWORD *)&v18.columnid.eKind = v15;
      ColInfo = CMetaData::mdGetColInfo(this, &v18, v11, &v19);
      v17 = v11 + 1;
      if ( !ColInfo )
        v17 = v11;
      ++v10;
      v11 = v17;
    }
    while ( v10 < a3 );
    v7 = v19;
  }
  *(_WORD *)this = v11;
  *((_WORD *)this + 1) = v11 - v7;
  *((_WORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1800030a8  mov     rax, rsp
0x1800030ab  push    rbx
0x1800030ac  push    rbp
0x1800030ad  push    rsi
0x1800030ae  push    rdi
0x1800030af  push    r14
0x1800030b1  push    r15
0x1800030b3  sub     rsp, 88h
0x1800030ba  mov     ebp, r8d
0x1800030bd  mov     rdi, rcx
0x1800030c0  imul    rbx, rbp, 0A8h
0x1800030c7  xor     esi, esi
0x1800030c9  mov     r14, r9
0x1800030cc  mov     rcx, rbx; cb
0x1800030cf  mov     [rax+18h], si
0x1800030d3  call    cs:__imp_CoTaskMemAlloc
0x1800030da  nop     dword ptr [rax+rax+00h]
0x1800030df  mov     [rdi+8], rax
0x1800030e3  test    rax, rax
0x1800030e6  jnz     short loc_18000312D
0x1800030e8  test    byte ptr cs:_bidGblFlags, 2
0x1800030ef  mov     ebx, 8007000Eh
0x1800030f4  jz      short loc_180003125
0x1800030f6  mov     rax, cs:off_180049448; "<CMetaData::mdGetColumnsInfo|ADO|ERR>  "...
0x1800030fd  test    rax, rax
0x180003100  jz      short loc_180003125
0x180003102  mov     r8, cs:off_180049448; "<CMetaData::mdGetColumnsInfo|ADO|ERR>  "...
0x180003109  mov     r9d, ebx
0x18000310c  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003113  mov     edx, 84000h
0x180003118  mov     [rsp+0B8h+var_98], 210h
0x180003120  call    _bidTraceW
0x180003125  mov     ecx, ebx; int
0x180003127  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000312d  mov     r8, rbx; Size
0x180003130  xor     edx, edx; Val
0x180003132  mov     rcx, rax; void *
0x180003135  call    memset_0
0x18000313a  xor     r15d, r15d
0x18000313d  xor     ebx, ebx
0x18000313f  test    ebp, ebp
0x180003141  jz      short loc_1800031BD
0x180003143  movzx   eax, r15w
0x180003147  lea     r9, [rsp+0B8h+arg_10]; unsigned __int16 *
0x18000314f  movzx   r8d, bx; unsigned __int16
0x180003153  lea     rdx, [rsp+0B8h+var_88]; struct tagDBCOLUMNINFO
0x180003158  lea     rcx, [rax+rax*4]
0x18000315c  add     rcx, rcx
0x18000315f  movups  xmm0, xmmword ptr [r14+rcx*8]
0x180003164  movups  xmm1, xmmword ptr [r14+rcx*8+10h]
0x18000316a  movaps  xmmword ptr [rsp+0B8h+var_88.pwszName], xmm0
0x18000316f  movups  xmm0, xmmword ptr [r14+rcx*8+20h]
0x180003175  movaps  xmmword ptr [rsp+0B8h+var_88.iOrdinal], xmm1
0x18000317a  movups  xmm1, xmmword ptr [r14+rcx*8+30h]
0x180003180  movaps  xmmword ptr [rsp+0B8h+var_88.ulColumnSize], xmm0
0x180003185  movups  xmm0, xmmword ptr [r14+rcx*8+40h]
0x18000318b  mov     rcx, rdi; this
0x18000318e  movaps  xmmword ptr [rsp+0B8h+var_88.columnid.uGuid], xmm1
0x180003193  movaps  xmmword ptr [rsp+0B8h+var_88.columnid.eKind], xmm0
0x180003198  call    ?mdGetColInfo@CMetaData@@AEAAHUtagDBCOLUMNINFO@@GPEAG@Z; CMetaData::mdGetColInfo(tagDBCOLUMNINFO,ushort,ushort *)
0x18000319d  test    eax, eax
0x18000319f  lea     ecx, [rbx+1]
0x1800031a2  cmovz   cx, bx
0x1800031a6  inc     r15w
0x1800031aa  movzx   eax, r15w
0x1800031ae  movzx   ebx, cx
0x1800031b1  cmp     eax, ebp
0x1800031b3  jb      short loc_180003143
0x1800031b5  movzx   esi, [rsp+0B8h+arg_10]
0x1800031bd  mov     [rdi], bx
0x1800031c0  sub     bx, si
0x1800031c3  xor     eax, eax
0x1800031c5  mov     [rdi+2], bx
0x1800031c9  mov     [rdi+4], ax
0x1800031cd  add     rsp, 88h
0x1800031d4  pop     r15
0x1800031d6  pop     r14
0x1800031d8  pop     rdi
0x1800031d9  pop     rsi
0x1800031da  pop     rbp
0x1800031db  pop     rbx
0x1800031dc  retn
```
