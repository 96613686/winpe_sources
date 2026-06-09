# CPersistStreamInit::WriteRowsetMetaData(CRowInfo &)

- ea: `0x18001f7c8`
- end: `0x18001fbbf`
- name: `?WriteRowsetMetaData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z`
- size: `1015`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001f1bc`

## callees

- `0x180002770`
- `0x18001b558`
- `0x18001d054`
- `0x18001d1c8`
- `0x18001ed5c`
- `0x18001f7c8`
- `0x18001fe94`
- `0x180020204`
- `0x180028aec`
- `0x18002b0e4`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001f9a9`
- `msvcrt!_wcsicmp` at `0x18001f9a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPersistStreamInit::WriteRowsetMetaData(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        __int64 a3,
        bool a4)
{
  int v6; // ebx
  __int64 i; // rax
  __int64 v8; // r12
  unsigned __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r14
  __int16 v12; // ax
  int v13; // edx
  bool v14; // r9
  bool v15; // r9
  __int16 v16; // dx
  int *v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+48h] [rbp-B8h]
  unsigned int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v26[256]; // [rsp+70h] [rbp-90h] BYREF

  v6 = 0;
  v19 = 0;
  v25[0] = 0;
  if ( !*((_BYTE *)a2 + 168)
    || (v6 = CPersistStreamInit::WriteAttributeDefinition(
               this,
               *(void **)(*((_QWORD *)this + 9) + 1728LL),
               *((unsigned __int16 **)a2 + 22),
               a4,
               65,
               1),
        v6 >= 0) )
  {
    if ( (***((int (__fastcall ****)(_QWORD, GUID *, _QWORD *))a2 + 13))(*((_QWORD *)a2 + 13), &IID_IRowsetInfo, v25) >= 0 )
    {
      v23 = 0;
      *(_QWORD *)v24 = 0;
      if ( !XMLProps::m_fInitialized )
        XMLProps::_InitProps();
      v18 = v24;
      if ( (*(int (__fastcall **)(_QWORD, __int64, struct tagDBPROPIDSET near **, unsigned int *))(*(_QWORD *)v25[0]
                                                                                                 + 24LL))(
             v25[0],
             2,
             &XMLProps::m_rgPropSets,
             &v23) >= 0 )
      {
        for ( i = 0; ; i = (unsigned int)(v22 + 1) )
        {
          v22 = i;
          if ( (unsigned int)i >= v23 )
            break;
          v8 = 0;
          v9 = (unsigned int)i;
          v21 = (unsigned int)i;
          v10 = 32 * i;
          v20 = v10;
          while ( (unsigned int)v8 < *(_DWORD *)(v10 + *(_QWORD *)v24 + 8) )
          {
            v11 = *(_QWORD *)(v10 + *(_QWORD *)v24);
            if ( *(_DWORD *)(v11 + 72 * v8 + 8) )
              goto LABEL_27;
            v12 = *(_WORD *)(v11 + 72 * v8 + 48);
            if ( v12 != 3 )
            {
              if ( v12 == 8 )
              {
                if ( _wcsicmp(
                       *(const wchar_t **)(v11 + 72 * v8 + 56),
                       &(&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]->vt) )
                {
                  v6 = CPersistStreamInit::WriteAttributeDefinition(
                         this,
                         *(void **)(*((_QWORD *)this + 9)
                                  + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v21] + v8)),
                         *(unsigned __int16 **)(v11 + 72 * v8 + 56),
                         v15,
                         65,
                         1);
                  if ( v6 < 0 )
                  {
LABEL_15:
                    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v23);
                    goto LABEL_39;
                  }
                }
              }
              else
              {
                if ( v12 != 11
                  || *(_DWORD *)(v11 + 72 * v8) == 134 && !*(_WORD *)(v11 + 72LL * (unsigned int)(v8 - 1) + 56) )
                {
                  goto LABEL_26;
                }
                v16 = *(_WORD *)(v11 + 72 * v8 + 56);
                if ( v16 == LOWORD((&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]) )
                  goto LABEL_26;
                v6 = CPersistStreamInit::WriteAttributeDefinition(
                       this,
                       *(void **)(*((_QWORD *)this + 9) + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v9] + v8)),
                       *(unsigned __int16 **)((-(__int64)(v16 != 0) & 0xFFFFFFFFFFFFFFF0uLL)
                                            + *((_QWORD *)this + 9)
                                            + 848),
                       v9,
                       65,
                       0);
                if ( v6 < 0 )
                  goto LABEL_15;
              }
              goto LABEL_25;
            }
            v13 = *(_DWORD *)(v11 + 72 * v8 + 56);
            if ( v13 != LODWORD((&XMLProps::m_rgDefaultSets)[v9][3 * v8 + 1]) )
            {
              CPersistStreamInit::_ito(this, v13, v26, v9, (int)v18);
              v6 = CPersistStreamInit::WriteAttributeDefinition(
                     this,
                     *(void **)(*((_QWORD *)this + 9) + 16LL * *((unsigned __int8 *)(&XMLProps::m_rgTagSets)[v21] + v8)),
                     v26,
                     v14,
                     65,
                     0);
              if ( v6 < 0 )
                goto LABEL_15;
LABEL_25:
              v9 = v21;
            }
LABEL_26:
            v10 = v20;
LABEL_27:
            v8 = (unsigned int)(v8 + 1);
          }
        }
      }
      DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v23);
    }
    if ( *((_DWORD *)a2 + 36) )
    {
      v6 = CPersistStreamInit::Write(
             this,
             *(_BYTE **)(*((_QWORD *)this + 9) + 704LL),
             *(unsigned __int8 *)(*((_QWORD *)this + 9) + 712LL),
             &v19,
             1);
      if ( v6 >= 0 )
      {
        v6 = CPersistStreamInit::WriteNamespace(this, 0x41u);
        if ( v6 >= 0 )
        {
          v6 = CPersistStreamInit::WriteTag(this, 0x8Eu, &v19);
          if ( v6 >= 0 )
          {
            v6 = CPersistStreamInit::WriteTag(this, 0x2Bu, &v19);
            if ( v6 >= 0 )
            {
              v6 = CPersistStreamInit::WriteTag(this, 0x29u, &v19);
              if ( v6 >= 0 )
              {
                v6 = CPersistStreamInit::BinaryOut(this, *((unsigned __int8 **)a2 + 19), *((_DWORD *)a2 + 36));
                if ( v6 >= 0 )
                  v6 = CPersistStreamInit::WriteTag(this, 0x29u, &v19);
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f7c8  mov     [rsp-8+arg_10], rbx
0x18001f7cd  push    rbp
0x18001f7ce  push    rsi
0x18001f7cf  push    rdi
0x18001f7d0  push    r12
0x18001f7d2  push    r13
0x18001f7d4  push    r14
0x18001f7d6  push    r15
0x18001f7d8  lea     rbp, [rsp-180h]
0x18001f7e0  sub     rsp, 280h
0x18001f7e7  mov     rax, cs:__security_cookie
0x18001f7ee  xor     rax, rsp
0x18001f7f1  mov     [rbp+1B0h+var_40], rax
0x18001f7f8  mov     r13, rdx
0x18001f7fb  mov     rdi, rcx
0x18001f7fe  xor     ebx, ebx
0x18001f800  mov     [rsp+2B0h+var_280], ebx
0x18001f804  mov     [rsp+2B0h+var_250], rbx
0x18001f809  cmp     [rdx+0A8h], bl
0x18001f80f  jz      short loc_18001F83C
0x18001f811  mov     rdx, [rcx+48h]
0x18001f815  mov     [rsp+2B0h+var_288], 1; bool
0x18001f81a  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001f81f  mov     r8, [r13+0B0h]; unsigned __int16 *
0x18001f826  mov     rdx, [rdx+6C0h]; void *
0x18001f82d  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f832  mov     ebx, eax
0x18001f834  test    eax, eax
0x18001f836  js      loc_18001FB88
0x18001f83c  mov     r9, [r13+68h]
0x18001f840  mov     rcx, [r9]
0x18001f843  mov     rax, [rcx]
0x18001f846  lea     r8, [rsp+2B0h+var_250]
0x18001f84b  lea     rdx, IID_IRowsetInfo
0x18001f852  mov     rcx, r9
0x18001f855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f85a  test    eax, eax
0x18001f85c  js      loc_18001FAD3
0x18001f862  mov     [rsp+2B0h+var_260], 0
0x18001f86a  mov     qword ptr [rsp+2B0h+var_258], 0
0x18001f873  cmp     cs:?m_fInitialized@XMLProps@@0KA, 0; ulong XMLProps::m_fInitialized
0x18001f87a  jnz     short loc_18001F881
0x18001f87c  call    ?_InitProps@XMLProps@@CAXXZ; XMLProps::_InitProps(void)
0x18001f881  mov     rcx, [rsp+2B0h+var_250]
0x18001f886  mov     rax, [rcx]
0x18001f889  lea     rdx, [rsp+2B0h+var_258]
0x18001f88e  mov     qword ptr [rsp+2B0h+var_290], rdx; int
0x18001f893  lea     r9, [rsp+2B0h+var_260]
0x18001f898  lea     r8, ?m_rgPropSets@XMLProps@@0PAUtagDBPROPIDSET@@A; tagDBPROPIDSET near * XMLProps::m_rgPropSets
0x18001f89f  mov     edx, 2
0x18001f8a4  mov     rax, [rax+18h]
0x18001f8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8ad  test    eax, eax
0x18001f8af  js      loc_18001FAC8
0x18001f8b5  xor     eax, eax
0x18001f8b7  lea     r10, cs:180000000h
0x18001f8be  mov     [rsp+2B0h+var_268], eax
0x18001f8c2  cmp     eax, [rsp+2B0h+var_260]
0x18001f8c6  jnb     loc_18001FAC8
0x18001f8cc  xor     r12d, r12d
0x18001f8cf  mov     r9d, eax; bool
0x18001f8d2  mov     [rsp+2B0h+var_270], r9
0x18001f8d7  shl     rax, 5
0x18001f8db  mov     [rsp+2B0h+var_278], rax
0x18001f8e0  mov     r14, qword ptr [rsp+2B0h+var_258]
0x18001f8e5  cmp     r12d, [rax+r14+8]
0x18001f8ea  jnb     loc_18001FAAD
0x18001f8f0  mov     r14, [rax+r14]
0x18001f8f4  lea     r15, [r12+r12*8]
0x18001f8f8  cmp     dword ptr [r14+r15*8+8], 0
0x18001f8fe  jnz     loc_18001FAA5
0x18001f904  movzx   eax, word ptr [r14+r15*8+30h]
0x18001f90a  cmp     ax, 3
0x18001f90e  jnz     short loc_18001F98D
0x18001f910  mov     edx, [r14+r15*8+38h]; int
0x18001f915  lea     rcx, [r12+r12*2]
0x18001f919  mov     rax, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001f921  cmp     edx, [rax+rcx*8+8]
0x18001f925  jz      loc_18001FAA0
0x18001f92b  lea     r8, [rsp+2B0h+var_240]; void *
0x18001f930  mov     rcx, rdi; this
0x18001f933  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001f938  mov     rax, [rsp+2B0h+var_270]
0x18001f93d  lea     rcx, cs:180000000h
0x18001f944  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[rcx+rax*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001f94c  movzx   ecx, byte ptr [rax+r12]
0x18001f951  add     rcx, rcx
0x18001f954  mov     rdx, [rdi+48h]
0x18001f958  mov     [rsp+2B0h+var_288], 0; bool
0x18001f95d  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001f962  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18001f967  mov     rdx, [rdx+rcx*8]; void *
0x18001f96b  mov     rcx, rdi; this
0x18001f96e  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f973  mov     ebx, eax
0x18001f975  test    eax, eax
0x18001f977  jns     loc_18001FA94
0x18001f97d  lea     rcx, [rsp+2B0h+var_260]; this
0x18001f982  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001f987  nop
0x18001f988  jmp     loc_18001FB88
0x18001f98d  cmp     ax, 8
0x18001f991  jnz     short loc_18001FA12
0x18001f993  lea     rax, [r12+r12*2]
0x18001f997  mov     rdx, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001f99f  mov     rdx, [rdx+rax*8+8]; String2
0x18001f9a4  mov     rcx, [r14+r15*8+38h]; String1
0x18001f9a9  call    cs:__imp__wcsicmp
0x18001f9b0  nop     dword ptr [rax+rax+00h]
0x18001f9b5  test    eax, eax
0x18001f9b7  jz      loc_18001FA94
0x18001f9bd  mov     rax, [rsp+2B0h+var_270]
0x18001f9c2  lea     rcx, cs:180000000h
0x18001f9c9  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[rcx+rax*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001f9d1  movzx   ecx, byte ptr [rax+r12]
0x18001f9d6  add     rcx, rcx
0x18001f9d9  mov     rdx, [rdi+48h]
0x18001f9dd  mov     [rsp+2B0h+var_288], 1; bool
0x18001f9e2  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001f9e7  mov     r8, [r14+r15*8+38h]; unsigned __int16 *
0x18001f9ec  mov     rdx, [rdx+rcx*8]; void *
0x18001f9f0  mov     rcx, rdi; this
0x18001f9f3  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f9f8  mov     ebx, eax
0x18001f9fa  test    eax, eax
0x18001f9fc  jns     loc_18001FA94
0x18001fa02  lea     rcx, [rsp+2B0h+var_260]; this
0x18001fa07  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001fa0c  nop
0x18001fa0d  jmp     loc_18001FB88
0x18001fa12  cmp     ax, 0Bh
0x18001fa16  jnz     loc_18001FAA0
0x18001fa1c  cmp     dword ptr [r14+r15*8], 86h
0x18001fa24  jnz     short loc_18001FA39
0x18001fa26  lea     eax, [r12-1]
0x18001fa2b  lea     rdx, [rax+rax*8]
0x18001fa2f  xor     eax, eax
0x18001fa31  cmp     ax, [r14+rdx*8+38h]
0x18001fa37  jz      short loc_18001FAA0
0x18001fa39  movzx   edx, word ptr [r14+r15*8+38h]
0x18001fa3f  lea     rcx, [r12+r12*2]
0x18001fa43  mov     rax, rva ?m_rgDefaultSets@XMLProps@@0PAPEAUtagVARIANT@@A[r10+r9*8]; tagVARIANT * near * XMLProps::m_rgDefaultSets ...
0x18001fa4b  cmp     dx, [rax+rcx*8+8]
0x18001fa50  jz      short loc_18001FAA0
0x18001fa52  mov     rcx, [rdi+48h]
0x18001fa56  neg     dx
0x18001fa59  sbb     r8, r8
0x18001fa5c  and     r8, 0FFFFFFFFFFFFFFF0h
0x18001fa60  mov     rax, rva ?m_rgTagSets@XMLProps@@0PAPEAEA[r10+r9*8]; uchar * near * XMLProps::m_rgTagSets ...
0x18001fa68  movzx   edx, byte ptr [rax+r12]
0x18001fa6d  add     rdx, rdx
0x18001fa70  mov     [rsp+2B0h+var_288], 0; bool
0x18001fa75  mov     [rsp+2B0h+var_290], 41h ; 'A'; char
0x18001fa7a  mov     r8, [r8+rcx+350h]; unsigned __int16 *
0x18001fa82  mov     rdx, [rcx+rdx*8]; void *
0x18001fa86  mov     rcx, rdi; this
0x18001fa89  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001fa8e  mov     ebx, eax
0x18001fa90  test    eax, eax
0x18001fa92  js      short loc_18001FAB8
0x18001fa94  lea     r10, cs:180000000h
0x18001fa9b  mov     r9, [rsp+2B0h+var_270]
0x18001faa0  mov     rax, [rsp+2B0h+var_278]
0x18001faa5  inc     r12d
0x18001faa8  jmp     loc_18001F8E0
0x18001faad  mov     eax, [rsp+2B0h+var_268]
0x18001fab1  inc     eax
0x18001fab3  jmp     loc_18001F8BE
0x18001fab8  lea     rcx, [rsp+2B0h+var_260]; this
0x18001fabd  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001fac2  nop
0x18001fac3  jmp     loc_18001FB88
0x18001fac8  lea     rcx, [rsp+2B0h+var_260]; this
0x18001facd  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18001fad2  nop
0x18001fad3  cmp     dword ptr [r13+90h], 0
0x18001fadb  jz      loc_18001FB88
0x18001fae1  mov     rdx, [rdi+48h]
0x18001fae5  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001faed  mov     [rsp+2B0h+var_290], 1; bool
0x18001faf2  lea     r9, [rsp+2B0h+var_280]; unsigned int *
0x18001faf7  mov     rdx, [rdx+2C0h]; Src
0x18001fafe  mov     rcx, rdi; this
0x18001fb01  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001fb06  mov     ebx, eax
0x18001fb08  test    eax, eax
0x18001fb0a  js      short loc_18001FB88
0x18001fb0c  mov     dl, 41h ; 'A'; unsigned __int8
0x18001fb0e  mov     rcx, rdi; this
0x18001fb11  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001fb16  mov     ebx, eax
0x18001fb18  test    eax, eax
0x18001fb1a  js      short loc_18001FB88
0x18001fb1c  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001fb21  mov     dl, 8Eh; unsigned __int8
0x18001fb23  mov     rcx, rdi; this
0x18001fb26  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001fb2b  mov     ebx, eax
0x18001fb2d  test    eax, eax
0x18001fb2f  js      short loc_18001FB88
0x18001fb31  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001fb36  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001fb38  mov     rcx, rdi; this
0x18001fb3b  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001fb40  mov     ebx, eax
0x18001fb42  test    eax, eax
0x18001fb44  js      short loc_18001FB88
0x18001fb46  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001fb4b  mov     dl, 29h ; ')'; unsigned __int8
0x18001fb4d  mov     rcx, rdi; this
0x18001fb50  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001fb55  mov     ebx, eax
0x18001fb57  test    eax, eax
0x18001fb59  js      short loc_18001FB88
0x18001fb5b  mov     r8d, [r13+90h]; unsigned int
0x18001fb62  mov     rdx, [r13+98h]; unsigned __int8 *
0x18001fb69  mov     rcx, rdi; this
0x18001fb6c  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001fb71  mov     ebx, eax
0x18001fb73  test    eax, eax
0x18001fb75  js      short loc_18001FB88
0x18001fb77  lea     r8, [rsp+2B0h+var_280]; unsigned int *
0x18001fb7c  mov     dl, 29h ; ')'; unsigned __int8
0x18001fb7e  mov     rcx, rdi; this
0x18001fb81  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001fb86  mov     ebx, eax
0x18001fb88  lea     rcx, [rsp+2B0h+var_250]
0x18001fb8d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001fb92  mov     eax, ebx
0x18001fb94  mov     rcx, [rbp+1B0h+var_40]
0x18001fb9b  xor     rcx, rsp; StackCookie
0x18001fb9e  call    __security_check_cookie
0x18001fba3  mov     rbx, [rsp+2B0h+arg_10]
0x18001fbab  add     rsp, 280h
0x18001fbb2  pop     r15
0x18001fbb4  pop     r14
0x18001fbb6  pop     r13
0x18001fbb8  pop     r12
0x18001fbba  pop     rdi
0x18001fbbb  pop     rsi
0x18001fbbc  pop     rbp
0x18001fbbd  retn
```
