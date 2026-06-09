# CWbemObject::SetArrayPropRangeByHandle(long,long,ulong,ulong,ulong,void *)

- ea: `0x18004cf60`
- end: `0x18004d2c7`
- name: `?SetArrayPropRangeByHandle@CWbemObject@@UEAAJJJKKKPEAX@Z`
- size: `871`
- prototype: `__int64 __fastcall(CWbemObject *this, int, int, unsigned int, unsigned int, unsigned int, struct IUnknown **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180013ae0`
- `0x180013cd0`
- `0x180037120`
- `0x18004cf40`
- `0x18004cf60`
- `0x18004d500`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004d05a`
- `wbemcomn!GetMemLogObject` at `0x18004d170`
- `wbemcomn!GetMemLogObject` at `0x18004d1ec`
- `wbemcomn!GetMemLogObject` at `0x18004d252`
- `wbemcomn!GetMemLogObject` at `0x18004d05a`
- `wbemcomn!GetMemLogObject` at `0x18004d170`
- `wbemcomn!GetMemLogObject` at `0x18004d1ec`
- `wbemcomn!GetMemLogObject` at `0x18004d252`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d065`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d180`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d1fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d25d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d065`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d180`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d1fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d25d`

## pseudocode

```c
__int64 __fastcall CWbemObject::SetArrayPropRangeByHandle(
        CWbemObject *this,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        struct IUnknown **a7)
{
  char v7; // bl
  unsigned int v10; // r12d
  unsigned int v11; // edi
  unsigned int v12; // r14d
  int v13; // ebx
  CMemoryLog *v14; // rax
  struct CFastHeap *v15; // rbx
  __int64 v16; // rax
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  int v23; // [rsp+54h] [rbp-54h]
  _QWORD v24[2]; // [rsp+60h] [rbp-48h] BYREF
  int v25; // [rsp+70h] [rbp-38h]
  char v26; // [rsp+C0h] [rbp+18h]

  v26 = a3;
  v7 = a3;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( (a3 & 0xFFFFFFFE) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749896LL);
      }
      result = 2147749896LL;
    }
    else
    {
      v10 = (a2 >> 16) & 0x3FF;
      if ( !(unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), v10, 0)
        && !(unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), v10, 1) )
      {
        v23 = 0;
LABEL_6:
        v11 = 0;
        v12 = 0;
        if ( a2 >= 0 )
        {
          v13 = -2147217386;
          v20 = GetMemLogObject();
          CMemoryLog::Write(v20, -2147217386);
        }
        else
        {
          v13 = 0;
          if ( (a2 & 0x8000) != 0 )
            v11 = 8;
          else
            v11 = (a2 & 0x4000) != 0 ? 13 : 4095;
          v12 = (a2 >> 26) & 0xF;
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v13);
        }
        if ( v13 < 0 )
          goto LABEL_13;
        v15 = (struct CFastHeap *)*((_QWORD *)this + 17);
        v16 = *((_QWORD *)this + 16);
        v24[0] = &CDataTablePtr::`vftable';
        v24[1] = v16;
        v25 = a2 & 0x1FFF;
        if ( v23 )
          *(_DWORD *)CDataTablePtr::GetPointer((CDataTablePtr *)v24) = -1;
        v13 = CUntypedArray::SetRange((struct CPtrSource *)v24, v26, v11, v12, v15, a4, a5, a6, a7);
        if ( v13 < 0 )
        {
LABEL_13:
          v14 = GetMemLogObject();
          CMemoryLog::Write(v14, v13);
        }
        else
        {
          CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v10, 0);
          CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v10, 1);
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            163,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            (unsigned int)v13);
        }
        return (unsigned int)v13;
      }
      v23 = 1;
      if ( (v7 & 1) != 0 )
        goto LABEL_6;
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217386);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749910LL);
      }
      result = 2147749910LL;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          164,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749894LL);
      }
      result = 2147749894LL;
      __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_18004D2B6);
      return result;
    }
    if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217398);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          165,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749898LL);
      }
      result = 2147749898LL;
      __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_18004D2BD);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004cf60  mov     rax, rsp
0x18004cf63  mov     [rax+8], rbx
0x18004cf67  mov     [rax+10h], rsi
0x18004cf6b  mov     [rax+20h], r9d
0x18004cf6f  mov     [rax+18h], r8d
0x18004cf73  push    rdi
0x18004cf74  push    r12
0x18004cf76  push    r13
0x18004cf78  push    r14
0x18004cf7a  push    r15
0x18004cf7c  sub     rsp, 80h
0x18004cf83  mov     ebx, r8d
0x18004cf86  mov     r15d, edx
0x18004cf89  mov     r13, rcx
0x18004cf8c  test    ebx, 0FFFFFFFEh
0x18004cf92  jnz     loc_18004D170
0x18004cf98  mov     r12d, edx
0x18004cf9b  sar     r12d, 10h
0x18004cf9f  and     r12d, 3FFh
0x18004cfa6  mov     rcx, [rcx+80h]
0x18004cfad  xor     r8d, r8d
0x18004cfb0  mov     edx, r12d
0x18004cfb3  mov     rcx, [rcx]
0x18004cfb6  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18004cfbb  test    eax, eax
0x18004cfbd  jnz     loc_18004D1DB
0x18004cfc3  mov     rcx, [r13+80h]
0x18004cfca  lea     r8d, [rax+1]
0x18004cfce  mov     edx, r12d
0x18004cfd1  mov     rcx, [rcx]
0x18004cfd4  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18004cfd9  test    eax, eax
0x18004cfdb  jnz     loc_18004D1DB
0x18004cfe1  mov     [rsp+0A8h+var_54], eax
0x18004cfe5  xor     edi, edi
0x18004cfe7  mov     [rsp+0A8h+var_58], edi
0x18004cfeb  xor     r14d, r14d
0x18004cfee  mov     [rsp+0A8h+var_50], r14d
0x18004cff3  test    r15d, r15d
0x18004cff6  jns     loc_18004D24D
0x18004cffc  xor     ebx, ebx
0x18004cffe  bt      r15d, 0Fh
0x18004d003  jb      loc_18004D243
0x18004d009  mov     eax, r15d
0x18004d00c  and     eax, 4000h
0x18004d011  neg     eax
0x18004d013  sbb     edi, edi
0x18004d015  and     edi, 0FFFFF00Eh
0x18004d01b  add     edi, 0FFFh
0x18004d021  mov     [rsp+0A8h+var_58], edi
0x18004d025  mov     r14d, r15d
0x18004d028  sar     r14d, 1Ah
0x18004d02c  and     r14d, 0Fh
0x18004d030  mov     [rsp+0A8h+var_50], r14d
0x18004d035  lea     rsi, WPP_GLOBAL_Control
0x18004d03c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d043  cmp     rcx, rsi
0x18004d046  jz      short loc_18004D052
0x18004d048  test    byte ptr [rcx+1Ch], 1
0x18004d04c  jnz     loc_18004D268
0x18004d052  mov     [rsp+0A8h+var_4C], ebx
0x18004d056  test    ebx, ebx
0x18004d058  jns     short loc_18004D070
0x18004d05a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d060  mov     edx, ebx
0x18004d062  mov     rcx, rax
0x18004d065  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d06b  jmp     loc_18004D13B
0x18004d070  mov     rbx, [r13+88h]
0x18004d077  mov     rax, [r13+80h]
0x18004d07e  lea     rcx, ??_7CPtrSource@@6B@; const CPtrSource::`vftable'
0x18004d085  mov     [rsp+0A8h+var_48], rcx
0x18004d08a  lea     rcx, ??_7CDataTablePtr@@6B@; const CDataTablePtr::`vftable'
0x18004d091  mov     [rsp+0A8h+var_48], rcx
0x18004d096  mov     [rsp+0A8h+var_40], rax
0x18004d09b  and     r15d, 1FFFh
0x18004d0a2  mov     [rsp+0A8h+var_38], r15d
0x18004d0a7  cmp     [rsp+0A8h+var_54], 0
0x18004d0ac  jnz     loc_18004D19D
0x18004d0b2  mov     rax, [rsp+0A8h+arg_30]
0x18004d0ba  mov     [rsp+0A8h+var_68], rax; void *
0x18004d0bf  mov     eax, [rsp+0A8h+arg_28]
0x18004d0c6  mov     [rsp+0A8h+var_70], eax; unsigned int
0x18004d0ca  mov     eax, [rsp+0A8h+arg_20]
0x18004d0d1  mov     [rsp+0A8h+var_78], eax; unsigned int
0x18004d0d5  mov     eax, [rsp+0A8h+arg_18]
0x18004d0dc  mov     [rsp+0A8h+var_80], eax; unsigned int
0x18004d0e0  mov     [rsp+0A8h+var_88], rbx; struct CFastHeap *
0x18004d0e5  mov     r9d, r14d; unsigned int
0x18004d0e8  mov     r8d, edi; unsigned int
0x18004d0eb  mov     edx, [rsp+0A8h+arg_10]; int
0x18004d0f2  lea     rcx, [rsp+0A8h+var_48]; struct CPtrSource *
0x18004d0f7  call    ?SetRange@CUntypedArray@@SAJPEAVCPtrSource@@JKKPEAVCFastHeap@@KKKPEAX@Z; CUntypedArray::SetRange(CPtrSource *,long,ulong,ulong,CFastHeap *,ulong,ulong,ulong,void *)
0x18004d0fc  mov     ebx, eax
0x18004d0fe  mov     [rsp+0A8h+var_4C], eax
0x18004d102  test    eax, eax
0x18004d104  js      loc_18004D05A
0x18004d10a  mov     rcx, [r13+80h]
0x18004d111  xor     r9d, r9d
0x18004d114  xor     r8d, r8d
0x18004d117  mov     edx, r12d
0x18004d11a  mov     rcx, [rcx]
0x18004d11d  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18004d122  mov     rcx, [r13+80h]
0x18004d129  xor     r9d, r9d
0x18004d12c  lea     r8d, [r9+1]
0x18004d130  mov     edx, r12d
0x18004d133  mov     rcx, [rcx]
0x18004d136  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18004d13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d142  cmp     rcx, rsi
0x18004d145  jz      short loc_18004D151
0x18004d147  test    byte ptr [rcx+1Ch], 1
0x18004d14b  jnz     loc_18004D28F
0x18004d151  mov     eax, ebx
0x18004d153  lea     r11, [rsp+0A8h+var_28]
0x18004d15b  mov     rbx, [r11+30h]
0x18004d15f  mov     rsi, [r11+38h]
0x18004d163  mov     rsp, r11
0x18004d166  pop     r15
0x18004d168  pop     r14
0x18004d16a  pop     r13
0x18004d16c  pop     r12
0x18004d16e  pop     rdi
0x18004d16f  retn
0x18004d170  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d176  mov     ebx, 80041008h
0x18004d17b  mov     edx, ebx
0x18004d17d  mov     rcx, rax
0x18004d180  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d186  lea     rsi, WPP_GLOBAL_Control
0x18004d18d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d194  cmp     rcx, rsi
0x18004d197  jnz     short loc_18004D1B2
0x18004d199  mov     eax, ebx
0x18004d19b  jmp     short loc_18004D153
0x18004d19d  lea     rcx, [rsp+0A8h+var_48]; this
0x18004d1a2  call    ?GetPointer@CDataTablePtr@@UEAAPEAEXZ; CDataTablePtr::GetPointer(void)
0x18004d1a7  mov     dword ptr [rax], 0FFFFFFFFh
0x18004d1ad  jmp     loc_18004D0B2
0x18004d1b2  test    byte ptr [rcx+1Ch], 1
0x18004d1b6  jz      short loc_18004D199
0x18004d1b8  cmp     byte ptr [rcx+19h], 2
0x18004d1bc  jb      short loc_18004D199
0x18004d1be  mov     edx, 0A1h
0x18004d1c3  mov     r9d, 80041008h
0x18004d1c9  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18004d1d0  mov     rcx, [rcx+10h]
0x18004d1d4  call    WPP_SF_d
0x18004d1d9  jmp     short loc_18004D199
0x18004d1db  mov     [rsp+0A8h+var_54], 1
0x18004d1e3  test    bl, 1
0x18004d1e6  jnz     loc_18004CFE5
0x18004d1ec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d1f2  mov     ebx, 80041016h
0x18004d1f7  mov     edx, ebx
0x18004d1f9  mov     rcx, rax
0x18004d1fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d202  lea     rsi, WPP_GLOBAL_Control
0x18004d209  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d210  cmp     rcx, rsi
0x18004d213  jz      short loc_18004D23C
0x18004d215  test    byte ptr [rcx+1Ch], 1
0x18004d219  jz      short loc_18004D23C
0x18004d21b  cmp     byte ptr [rcx+19h], 2
0x18004d21f  jb      short loc_18004D23C
0x18004d221  mov     edx, 0A2h
0x18004d226  mov     r9d, 80041016h
0x18004d22c  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18004d233  mov     rcx, [rcx+10h]
0x18004d237  call    WPP_SF_d
0x18004d23c  mov     eax, ebx
0x18004d23e  jmp     loc_18004D153
0x18004d243  mov     edi, 8
0x18004d248  jmp     loc_18004D021
0x18004d24d  mov     ebx, 80041016h
0x18004d252  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d258  mov     edx, ebx
0x18004d25a  mov     rcx, rax
0x18004d25d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d263  jmp     loc_18004D035
0x18004d268  cmp     byte ptr [rcx+19h], 2
0x18004d26c  jb      loc_18004D052
0x18004d272  mov     edx, 91h
0x18004d277  mov     r9d, ebx
0x18004d27a  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18004d281  mov     rcx, [rcx+10h]
0x18004d285  call    WPP_SF_d
0x18004d28a  jmp     loc_18004D052
0x18004d28f  cmp     byte ptr [rcx+19h], 2
0x18004d293  jb      loc_18004D151
0x18004d299  mov     edx, 0A3h
0x18004d29e  mov     r9d, ebx
0x18004d2a1  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18004d2a8  mov     rcx, [rcx+10h]
0x18004d2ac  call    WPP_SF_d
0x18004d2b1  jmp     loc_18004D151
0x18004d2b6  mov     eax, 80041006h
0x18004d2bb  jmp     short loc_18004D2C2
0x18004d2bd  mov     eax, 8004100Ah
0x18004d2c2  jmp     loc_18004D153
```
