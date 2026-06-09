# CWbemObject::SetPropByHandle(long,long,ulong,void *)

- ea: `0x18005f9e0`
- end: `0x18005ff8d`
- name: `?SetPropByHandle@CWbemObject@@UEAAJJJKPEAX@Z`
- size: `1453`
- prototype: `__int64 __fastcall(CWbemObject *this, int, int, unsigned int, void *Src)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002290`
- `0x18000e720`
- `0x180013ae0`
- `0x180013cd0`
- `0x180021820`
- `0x180037120`
- `0x180045140`
- `0x18004fac0`
- `0x18005b4a0`
- `0x18005b500`
- `0x18005f9e0`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18005fb59`
- `wbemcomn!GetMemLogObject` at `0x18005fbd3`
- `wbemcomn!GetMemLogObject` at `0x18005fc3d`
- `wbemcomn!GetMemLogObject` at `0x18005fdc9`
- `wbemcomn!GetMemLogObject` at `0x18005fddf`
- `wbemcomn!GetMemLogObject` at `0x18005fb59`
- `wbemcomn!GetMemLogObject` at `0x18005fbd3`
- `wbemcomn!GetMemLogObject` at `0x18005fc3d`
- `wbemcomn!GetMemLogObject` at `0x18005fdc9`
- `wbemcomn!GetMemLogObject` at `0x18005fddf`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18005fe3b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18005fe3b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fb69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fbe3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fc4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fdd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fdef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fb69`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fbe3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fc4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fdd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005fdef`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005ff16`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005ff16`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemObject::SetPropByHandle(CWbemObject *this, int a2, int a3, unsigned int a4, void *Src)
{
  unsigned __int64 v6; // rbx
  int v8; // edi
  unsigned int v9; // r14d
  const void *v10; // rdx
  int v11; // r13d
  int v12; // esi
  __int64 result; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  CFastHeap *v17; // rsi
  _QWORD *v18; // r12
  unsigned int v19; // r12d
  unsigned int v20; // r8d
  unsigned int v21; // esi
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CClassPart *v24; // rax
  __int64 v25; // rax
  unsigned __int16 VARTYPE; // ax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  unsigned int v29; // [rsp+34h] [rbp-84h] BYREF
  int v30; // [rsp+38h] [rbp-80h]
  int v31; // [rsp+3Ch] [rbp-7Ch]
  _QWORD v32[2]; // [rsp+40h] [rbp-78h] BYREF
  int v33; // [rsp+50h] [rbp-68h]
  _BYTE v34[96]; // [rsp+58h] [rbp-60h] BYREF

  v6 = a2;
  try
  {
    if ( a3 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749896LL);
      }
      return 2147749896LL;
    }
    v8 = 0;
    v9 = (a2 >> 16) & 0x3FF;
    v10 = Src;
    if ( Src )
    {
      v11 = 0;
      v30 = 0;
      if ( (v6 & 0x4000) != 0 && (v6 & 0xA000) == 0xA000 )
      {
        v12 = v6 & 0x2000;
      }
      else
      {
        v12 = v6 & 0x2000;
        if ( (unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), v9, 1)
          || (v11 = 1, (unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), v9, 0)) )
        {
          v11 = 0;
        }
        v30 = v11;
        if ( (v6 & 0x2000) == 0 )
        {
          CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v9, 0);
          CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v9, 1);
        }
        v10 = Src;
      }
      if ( (v6 & 0x80000000) == 0LL )
      {
        if ( a4 == (((unsigned int)v6 >> 26) & 0xF) )
        {
          memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)this + 16) + 8LL) + (v6 & 0x1FFF)), v10, (v6 >> 26) & 0xF);
          goto LABEL_13;
        }
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            137,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            2147749896LL);
        }
        return 2147749896LL;
      }
      v31 = 0;
      if ( (_DWORD)v6 == -2 )
      {
        v31 = 1;
      }
      else
      {
        if ( (_DWORD)v6 == -3 || v12 )
        {
          v8 = -2147217386;
LABEL_56:
          v22 = GetMemLogObject();
          CMemoryLog::Write(v22, v8);
LABEL_14:
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              138,
              WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
              (unsigned int)v8);
          }
          return (unsigned int)v8;
        }
        v21 = 13;
        if ( (v6 & 0x8000) == 0 )
          goto LABEL_62;
      }
      if ( a4 < 2 || (a4 & 1) != 0 || *((_WORD *)v10 + (a4 >> 1) - 1) )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, -2147217400);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            136,
            WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
            2147749896LL);
        }
        return 2147749896LL;
      }
      v21 = 8;
LABEL_62:
      CVar::CVar((CVar *)v34);
      v8 = CUntypedValue::FillCVarFromUserBuffer(v21, (struct CVar *)v34, a4, Src);
      if ( v8 >= 0 )
      {
        if ( (_DWORD)v6 == -2 )
        {
          v24 = (CClassPart *)(*(__int64 (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 800LL))(this, 0);
          v8 = CClassPart::SetClassName(v24, (struct CVar *)v34);
        }
        else
        {
          v25 = *((_QWORD *)this + 16);
          v32[0] = &CDataTablePtr::`vftable';
          v32[1] = v25;
          v33 = v6 & 0x1FFF;
          v29 = 0;
          VARTYPE = CType::GetVARTYPE(v21);
          v8 = CUntypedValue::LoadFromCVar(
                 (struct CPtrSource *)v32,
                 (struct CVar *)v34,
                 VARTYPE,
                 *((struct CFastHeap **)this + 17),
                 &v29,
                 v11);
          if ( v29 == 4095 )
            v8 = -2147217403;
        }
      }
      CVar::~CVar((CVar *)v34);
LABEL_13:
      if ( v8 >= 0 )
        goto LABEL_14;
      goto LABEL_56;
    }
    if ( (v6 & 0x4000) != 0 && (v6 & 0xA000) == 0xA000 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2147217378);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          2147749918LL);
      }
      return 2147749918LL;
    }
    if ( (v6 & 0x80000000) == 0LL )
    {
LABEL_23:
      CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v9, 0);
      CBitBlockTable<2>::SetBit(**((_QWORD **)this + 16), v9, 1);
      goto LABEL_14;
    }
    v17 = (CFastHeap *)*((_QWORD *)this + 17);
    v18 = (_QWORD *)*((_QWORD *)this + 16);
    if ( (unsigned int)CBitBlockTable<2>::GetBit(*v18, v9, 1) )
    {
      v17 = (CFastHeap *)((*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this) + 200);
      v18 = (_QWORD *)((*(__int64 (__fastcall **)(CWbemObject *))(*(_QWORD *)this + 800LL))(this) + 168);
    }
    v19 = *(_DWORD *)((v6 & 0x1FFF) + v18[1]);
    if ( (v6 & 0x2000) != 0 )
    {
      v20 = *(_DWORD *)CFastHeap::ResolveHeapPointer(v17, v19) * (((int)v6 >> 26) & 0xF) + 4;
    }
    else
    {
      if ( (v6 & 0x8000) != 0 )
      {
        CFastHeap::FreeString(v17, v19);
        goto LABEL_23;
      }
      v20 = *(_DWORD *)CFastHeap::ResolveHeapPointer(v17, v19) + 4;
    }
    CFastHeap::Free(v17, v19, v20);
    goto LABEL_23;
  }
  catch ( CX_MemoryException )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  if ( a3 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
}

```

## disassembly

```asm
0x18005f9e0  push    rbx
0x18005f9e2  push    rsi
0x18005f9e3  push    rdi
0x18005f9e4  push    r12
0x18005f9e6  push    r13
0x18005f9e8  push    r14
0x18005f9ea  push    r15
0x18005f9ec  sub     rsp, 80h
0x18005f9f3  mov     r12d, r9d
0x18005f9f6  movsxd  rbx, edx
0x18005f9f9  mov     r15, rcx
0x18005f9fc  xor     r9d, r9d
0x18005f9ff  test    r8d, r8d
0x18005fa02  jnz     loc_18005FBD3
0x18005fa08  mov     edi, r9d
0x18005fa0b  mov     [rsp+0B8h+var_88], r9d
0x18005fa10  mov     r14d, ebx
0x18005fa13  sar     r14d, 10h
0x18005fa17  and     r14d, 3FFh
0x18005fa1e  mov     eax, ebx
0x18005fa20  and     eax, 4000h
0x18005fa25  mov     rdx, [rsp+0B8h+Src]
0x18005fa2d  test    rdx, rdx
0x18005fa30  jz      loc_18005FB8A
0x18005fa36  mov     r13d, r9d
0x18005fa39  mov     [rsp+0B8h+var_80], r9d
0x18005fa3e  test    eax, eax
0x18005fa40  jnz     loc_18005FD50
0x18005fa46  mov     esi, ebx
0x18005fa48  and     esi, 2000h
0x18005fa4e  mov     rcx, [r15+80h]
0x18005fa55  mov     r8d, 1
0x18005fa5b  mov     edx, r14d
0x18005fa5e  mov     rcx, [rcx]
0x18005fa61  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18005fa66  xor     r9d, r9d
0x18005fa69  test    eax, eax
0x18005fa6b  jz      loc_18005FB30
0x18005fa71  mov     r13d, r9d
0x18005fa74  mov     [rsp+0B8h+var_80], r13d
0x18005fa79  test    esi, esi
0x18005fa7b  jnz     short loc_18005FAB1
0x18005fa7d  mov     rcx, [r15+80h]
0x18005fa84  xor     r9d, r9d
0x18005fa87  xor     r8d, r8d
0x18005fa8a  mov     edx, r14d
0x18005fa8d  mov     rcx, [rcx]
0x18005fa90  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18005fa95  mov     rcx, [r15+80h]
0x18005fa9c  xor     r9d, r9d
0x18005fa9f  lea     r8d, [rsi+1]
0x18005faa3  mov     edx, r14d
0x18005faa6  mov     rcx, [rcx]
0x18005faa9  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18005faae  xor     r9d, r9d
0x18005fab1  mov     rdx, [rsp+0B8h+Src]; Src
0x18005fab9  test    ebx, ebx
0x18005fabb  js      loc_18005FD6E
0x18005fac1  mov     eax, ebx
0x18005fac3  shr     eax, 1Ah
0x18005fac6  and     eax, 0Fh
0x18005fac9  cmp     r12d, eax
0x18005facc  jnz     loc_18005FB59
0x18005fad2  mov     rcx, rbx
0x18005fad5  mov     r8, rbx
0x18005fad8  shr     r8, 1Ah
0x18005fadc  and     r8d, 0Fh; Size
0x18005fae0  mov     rax, [r15+80h]
0x18005fae7  and     ecx, 1FFFh
0x18005faed  add     rcx, [rax+8]; void *
0x18005faf1  call    memcpy_0
0x18005faf6  test    edi, edi
0x18005faf8  js      loc_18005FDC9
0x18005fafe  lea     rax, WPP_GLOBAL_Control
0x18005fb05  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fb0c  cmp     rcx, rax
0x18005fb0f  jz      short loc_18005FB1B
0x18005fb11  test    byte ptr [rcx+1Ch], 1
0x18005fb15  jnz     loc_18005FF55
0x18005fb1b  mov     eax, edi
0x18005fb1d  add     rsp, 80h
0x18005fb24  pop     r15
0x18005fb26  pop     r14
0x18005fb28  pop     r13
0x18005fb2a  pop     r12
0x18005fb2c  pop     rdi
0x18005fb2d  pop     rsi
0x18005fb2e  pop     rbx
0x18005fb2f  retn
0x18005fb30  mov     rcx, [r15+80h]
0x18005fb37  xor     r8d, r8d
0x18005fb3a  mov     edx, r14d
0x18005fb3d  mov     rcx, [rcx]
0x18005fb40  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18005fb45  xor     r9d, r9d
0x18005fb48  test    eax, eax
0x18005fb4a  lea     r13d, [r9+1]
0x18005fb4e  jz      loc_18005FA74
0x18005fb54  jmp     loc_18005FA71
0x18005fb59  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005fb5f  mov     ebx, 80041008h
0x18005fb64  mov     edx, ebx
0x18005fb66  mov     rcx, rax
0x18005fb69  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005fb6f  lea     rax, WPP_GLOBAL_Control
0x18005fb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fb7d  cmp     rcx, rax
0x18005fb80  jnz     loc_18005FF21
0x18005fb86  mov     eax, ebx
0x18005fb88  jmp     short loc_18005FB1D
0x18005fb8a  test    eax, eax
0x18005fb8c  jnz     loc_18005FC2C
0x18005fb92  test    ebx, ebx
0x18005fb94  js      loc_18005FC94
0x18005fb9a  mov     rcx, [r15+80h]
0x18005fba1  mov     r9d, 1
0x18005fba7  xor     r8d, r8d
0x18005fbaa  mov     edx, r14d
0x18005fbad  mov     rcx, [rcx]
0x18005fbb0  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18005fbb5  mov     rcx, [r15+80h]
0x18005fbbc  xor     r9d, r9d
0x18005fbbf  lea     r8d, [r9+1]
0x18005fbc3  mov     edx, r14d
0x18005fbc6  mov     rcx, [rcx]
0x18005fbc9  call    ?SetBit@?$CBitBlockTable@$01@@QEAAXHHH@Z; CBitBlockTable<2>::SetBit(int,int,int)
0x18005fbce  jmp     loc_18005FAFE
0x18005fbd3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005fbd9  mov     ebx, 80041008h
0x18005fbde  mov     edx, ebx
0x18005fbe0  mov     rcx, rax
0x18005fbe3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005fbe9  lea     rax, WPP_GLOBAL_Control
0x18005fbf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fbf7  cmp     rcx, rax
0x18005fbfa  jnz     short loc_18005FC03
0x18005fbfc  mov     eax, ebx
0x18005fbfe  jmp     loc_18005FB1D
0x18005fc03  test    byte ptr [rcx+1Ch], 1
0x18005fc07  jz      short loc_18005FBFC
0x18005fc09  cmp     byte ptr [rcx+19h], 2
0x18005fc0d  jb      short loc_18005FBFC
0x18005fc0f  mov     edx, 86h
0x18005fc14  mov     r9d, 80041008h
0x18005fc1a  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18005fc21  mov     rcx, [rcx+10h]
0x18005fc25  call    WPP_SF_d
0x18005fc2a  jmp     short loc_18005FBFC
0x18005fc2c  mov     eax, ebx
0x18005fc2e  mov     ecx, 0A000h
0x18005fc33  and     eax, ecx
0x18005fc35  cmp     eax, ecx
0x18005fc37  jnz     loc_18005FB92
0x18005fc3d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005fc43  mov     ebx, 8004101Eh
0x18005fc48  mov     edx, ebx
0x18005fc4a  mov     rcx, rax
0x18005fc4d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005fc53  lea     rax, WPP_GLOBAL_Control
0x18005fc5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fc61  cmp     rcx, rax
0x18005fc64  jz      short loc_18005FC8D
0x18005fc66  test    byte ptr [rcx+1Ch], 1
0x18005fc6a  jz      short loc_18005FC8D
0x18005fc6c  cmp     byte ptr [rcx+19h], 2
0x18005fc70  jb      short loc_18005FC8D
0x18005fc72  mov     edx, 87h
0x18005fc77  mov     r9d, 8004101Eh
0x18005fc7d  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18005fc84  mov     rcx, [rcx+10h]
0x18005fc88  call    WPP_SF_d
0x18005fc8d  mov     eax, ebx
0x18005fc8f  jmp     loc_18005FB1D
0x18005fc94  mov     r13d, ebx
0x18005fc97  and     r13d, 2000h
0x18005fc9e  mov     rsi, [r15+88h]
0x18005fca5  mov     r12, [r15+80h]
0x18005fcac  mov     r8d, 1
0x18005fcb2  mov     edx, r14d
0x18005fcb5  mov     rcx, [r12]
0x18005fcb9  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18005fcbe  test    eax, eax
0x18005fcc0  jz      short loc_18005FCF4
0x18005fcc2  mov     rax, [r15]
0x18005fcc5  mov     rcx, r15
0x18005fcc8  mov     rax, [rax+320h]
0x18005fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcd4  lea     rsi, [rax+0C8h]
0x18005fcdb  mov     rax, [r15]
0x18005fcde  mov     rcx, r15
0x18005fce1  mov     rax, [rax+320h]
0x18005fce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fced  lea     r12, [rax+0A8h]
0x18005fcf4  mov     ecx, ebx
0x18005fcf6  and     ecx, 1FFFh
0x18005fcfc  mov     rax, [r12+8]
0x18005fd01  mov     r12d, [rcx+rax]
0x18005fd05  mov     edx, r12d; unsigned int
0x18005fd08  mov     rcx, rsi; this
0x18005fd0b  test    r13d, r13d
0x18005fd0e  jz      short loc_18005FD24
0x18005fd10  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18005fd15  sar     ebx, 1Ah
0x18005fd18  and     ebx, 0Fh
0x18005fd1b  imul    ebx, [rax]
0x18005fd1e  lea     r8d, [rbx+4]
0x18005fd22  jmp     short loc_18005FD40
0x18005fd24  bt      ebx, 0Fh
0x18005fd28  jnb     short loc_18005FD34
0x18005fd2a  call    ?FreeString@CFastHeap@@QEAAXK@Z; CFastHeap::FreeString(ulong)
0x18005fd2f  jmp     loc_18005FB9A
0x18005fd34  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18005fd39  mov     r8d, [rax]
0x18005fd3c  add     r8d, 4; unsigned int
0x18005fd40  mov     edx, r12d; unsigned int
0x18005fd43  mov     rcx, rsi; this
0x18005fd46  call    ?Free@CFastHeap@@QEAAXKK@Z; CFastHeap::Free(ulong,ulong)
0x18005fd4b  jmp     loc_18005FB9A
0x18005fd50  mov     eax, ebx
0x18005fd52  mov     ecx, 0A000h
0x18005fd57  and     eax, ecx
0x18005fd59  cmp     eax, ecx
0x18005fd5b  jnz     loc_18005FA46
0x18005fd61  mov     esi, ebx
0x18005fd63  and     esi, 2000h
0x18005fd69  jmp     loc_18005FAB9
0x18005fd6e  mov     [rsp+0B8h+var_7C], r9d
0x18005fd73  mov     r14d, 0FFFFFFFEh
0x18005fd79  cmp     ebx, r14d
0x18005fd7c  jnz     short loc_18005FDAA
0x18005fd7e  mov     [rsp+0B8h+var_7C], 1
0x18005fd86  cmp     r12d, 2
0x18005fd8a  jb      short loc_18005FDDF
0x18005fd8c  test    r12b, 1
0x18005fd90  jnz     short loc_18005FDDF
0x18005fd92  mov     eax, r12d
0x18005fd95  shr     eax, 1
0x18005fd97  dec     eax
0x18005fd99  cmp     [rdx+rax*2], r9w
0x18005fd9e  jnz     short loc_18005FDDF
0x18005fda0  mov     esi, 8
0x18005fda5  jmp     loc_18005FE36
0x18005fdaa  cmp     ebx, 0FFFFFFFDh
0x18005fdad  jz      short loc_18005FDC0
0x18005fdaf  test    esi, esi
0x18005fdb1  jnz     short loc_18005FDC0
0x18005fdb3  mov     esi, 0Dh
0x18005fdb8  bt      ebx, 0Fh
0x18005fdbc  jb      short loc_18005FD86
0x18005fdbe  jmp     short loc_18005FE36
0x18005fdc0  mov     edi, 80041016h
0x18005fdc5  mov     [rsp+0B8h+var_88], edi
0x18005fdc9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005fdcf  mov     edx, edi
0x18005fdd1  mov     rcx, rax
0x18005fdd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005fdda  jmp     loc_18005FAFE
0x18005fddf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005fde5  mov     ebx, 80041008h
0x18005fdea  mov     edx, ebx
0x18005fdec  mov     rcx, rax
0x18005fdef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005fdf5  lea     rax, WPP_GLOBAL_Control
0x18005fdfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe03  cmp     rcx, rax
0x18005fe06  jz      short loc_18005FE2F
0x18005fe08  test    byte ptr [rcx+1Ch], 1
0x18005fe0c  jz      short loc_18005FE2F
0x18005fe0e  cmp     byte ptr [rcx+19h], 2
0x18005fe12  jb      short loc_18005FE2F
0x18005fe14  mov     edx, 88h
0x18005fe19  mov     r9d, 80041008h
0x18005fe1f  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x18005fe26  mov     rcx, [rcx+10h]
0x18005fe2a  call    WPP_SF_d
0x18005fe2f  mov     eax, ebx
0x18005fe31  jmp     loc_18005FB1D
0x18005fe36  lea     rcx, [rsp+0B8h+var_60]
0x18005fe3b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18005fe41  nop
0x18005fe42  mov     r9, [rsp+0B8h+Src]; void *
0x18005fe4a  mov     r8d, r12d; unsigned int
0x18005fe4d  lea     rdx, [rsp+0B8h+var_60]; struct CVar *
0x18005fe52  mov     ecx, esi; unsigned int
0x18005fe54  call    ?FillCVarFromUserBuffer@CUntypedValue@@SAJKPEAVCVar@@KPEAX@Z; CUntypedValue::FillCVarFromUserBuffer(ulong,CVar *,ulong,void *)
0x18005fe59  mov     edi, eax
0x18005fe5b  mov     [rsp+0B8h+var_88], eax
0x18005fe5f  xor     edx, edx
0x18005fe61  test    eax, eax
0x18005fe63  js      loc_18005FF11
0x18005fe69  cmp     ebx, r14d
0x18005fe6c  jnz     short loc_18005FE95
0x18005fe6e  mov     rax, [r15]
0x18005fe71  mov     rcx, r15
0x18005fe74  mov     rax, [rax+320h]
0x18005fe7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe80  lea     rdx, [rsp+0B8h+var_60]; struct CVar *
0x18005fe85  mov     rcx, rax; this
0x18005fe88  call    ?SetClassName@CClassPart@@QEAAJPEAVCVar@@@Z; CClassPart::SetClassName(CVar *)
0x18005fe8d  mov     edi, eax
  ... truncated ...
```
