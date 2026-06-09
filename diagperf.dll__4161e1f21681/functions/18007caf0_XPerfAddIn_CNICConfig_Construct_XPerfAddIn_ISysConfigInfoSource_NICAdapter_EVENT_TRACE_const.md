# XPerfAddIn::CNICConfig::Construct(XPerfAddIn::ISysConfigInfoSource::NICAdapter &,_EVENT_TRACE const *)

- ea: `0x18007caf0`
- end: `0x18007d338`
- name: `?Construct@CNICConfig@XPerfAddIn@@QEAAJAEAUNICAdapter@ISysConfigInfoSource@2@PEBU_EVENT_TRACE@@@Z`
- size: `2120`
- prototype: `__int64 __fastcall(XPerfAddIn::CNICConfig *__hidden this, struct XPerfAddIn::ISysConfigInfoSource::NICAdapter *, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x1800799b4`

## callees

- `0x180012ac0`
- `0x180042948`
- `0x180056c14`
- `0x18007b244`
- `0x18007b34c`
- `0x18007c690`
- `0x18007caf0`
- `0x180080130`
- `0x180081150`
- `0x1800811d0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18007cc3b`
- `msvcrt!wcstok_s` at `0x18007cc78`
- `msvcrt!wcstok_s` at `0x18007ccd3`
- `msvcrt!wcstok_s` at `0x18007cd0d`
- `msvcrt!wcstok_s` at `0x18007cc3b`
- `msvcrt!wcstok_s` at `0x18007cc78`
- `msvcrt!wcstok_s` at `0x18007ccd3`
- `msvcrt!wcstok_s` at `0x18007cd0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=2
__int64 __fastcall XPerfAddIn::CNICConfig::Construct(
        XPerfAddIn::CNICConfig *this,
        struct XPerfAddIn::ISysConfigInfoSource::NICAdapter *a2,
        const struct _EVENT_TRACE *a3)
{
  int Version; // eax
  unsigned __int64 MofLength; // rsi
  const unsigned __int16 *MofData; // rdi
  int v7; // eax
  wchar_t *v9; // rsi
  wchar_t *v10; // rsi
  void *v11; // rax
  void *v12; // rax
  __int64 v13; // rax
  int v14; // r13d
  __int64 v15; // rsi
  unsigned __int16 *v16; // r14
  __int64 v17; // rax
  int v18; // r13d
  __int64 v19; // rsi
  _QWORD *v20; // r14
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // r8
  bool v26; // r9
  __int64 v27; // rcx
  unsigned __int64 v28; // r8
  bool v29; // r9
  unsigned __int64 i; // r14
  __int64 v31; // rcx
  void *v32; // rcx
  wchar_t *v33; // rax
  unsigned __int16 *v34; // rax
  void *v35; // rax
  void *v36; // rcx
  __int64 v37; // rax
  int v38; // r13d
  __int64 v39; // rsi
  _QWORD *v40; // r14
  __int64 *v41; // rax
  __int64 v42; // rcx
  char **v43; // [rsp+20h] [rbp-D8h]
  char **v44; // [rsp+20h] [rbp-D8h]
  void *Block; // [rsp+30h] [rbp-C8h] BYREF
  void *v46; // [rsp+38h] [rbp-C0h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-B8h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-B0h] BYREF
  wchar_t *v49; // [rsp+50h] [rbp-A8h] BYREF
  __int128 v50; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-90h]
  __int128 v52; // [rsp+70h] [rbp-88h]
  int v53; // [rsp+80h] [rbp-78h]
  __int128 v54; // [rsp+88h] [rbp-70h] BYREF
  __int64 v55; // [rsp+98h] [rbp-60h]
  __int128 v56; // [rsp+A0h] [rbp-58h]
  int v57; // [rsp+B0h] [rbp-48h]
  unsigned __int16 *Delimiter; // [rsp+110h] [rbp+18h] BYREF
  void *v59; // [rsp+118h] [rbp+20h] BYREF

  Version = a3->Header.Class.Version;
  MofLength = a3->MofLength;
  MofData = (const unsigned __int16 *)a3->MofData;
  if ( Version != 2 || !*((_BYTE *)this + 24) )
  {
    v7 = Version - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        return 262401;
      if ( MofLength >= 0x18 && *((_DWORD *)MofData + 2) <= 8u )
      {
        v46 = 0;
        XPerfAddIn::CNICConfig::ParsePhysicalAddress(this, &v46, MofData, *((unsigned int *)MofData + 2));
        Delimiter = 0;
        XPerfCore::CWStrParser::CWStrParser(
          (XPerfCore::CWStrParser *)&v59,
          MofData + 10,
          MofLength - 20,
          1,
          (const unsigned __int16 **)&Delimiter);
        Block = 0;
        XPerfCore::CWStrParser::CWStrParser(
          (XPerfCore::CWStrParser *)&String,
          Delimiter,
          MofLength + (char *)MofData - (char *)Delimiter,
          1,
          (const unsigned __int16 **)&Block);
        XPerfCore::CWStrParser::CWStrParser(
          (XPerfCore::CWStrParser *)&v49,
          (const unsigned __int16 *)Block,
          MofLength + (char *)MofData - (_BYTE *)Block,
          0,
          (const unsigned __int16 **)&Delimiter);
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 10;
        wcscpy((wchar_t *)&Delimiter, L";");
        Context = 0;
        v9 = wcstok_s(String, (const wchar_t *)&Delimiter, &Context);
        while ( v9 )
        {
          XPerfCore::CWStrParser::CWStrParser((XPerfCore::CWStrParser *)&Block, v9);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::AddTail(
            &v54,
            &Block);
          v9 = wcstok_s(0, (const wchar_t *)&Delimiter, &Context);
          operator delete(Block);
          Block = 0;
        }
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v53 = 10;
        wcscpy((wchar_t *)&Delimiter, L";");
        Context = 0;
        v10 = wcstok_s(v49, (const wchar_t *)&Delimiter, &Context);
        while ( v10 )
        {
          XPerfCore::CWStrParser::CWStrParser((XPerfCore::CWStrParser *)&Block, v10);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::AddTail(
            &v50,
            &Block);
          v10 = wcstok_s(0, (const wchar_t *)&Delimiter, &Context);
          operator delete(Block);
          Block = 0;
        }
        Delimiter = 0;
        if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(&Delimiter) )
        {
          operator delete(Delimiter);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v54);
          operator delete(v49);
          v49 = 0;
          operator delete(String);
          String = 0;
          operator delete(v59);
          v59 = 0;
          operator delete(v46);
          return 2147942414LL;
        }
        Block = 0;
        if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(&Block) )
        {
          operator delete(Block);
          operator delete(Delimiter);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v54);
          operator delete(v49);
          v49 = 0;
          operator delete(String);
          String = 0;
          operator delete(v59);
          v59 = 0;
          operator delete(v46);
          return 2147942414LL;
        }
        v11 = v46;
        v46 = 0;
        *(_QWORD *)a2 = v11;
        v12 = v59;
        v59 = 0;
        *((_QWORD *)a2 + 1) = v12;
        v13 = v55;
        v14 = v55;
        v15 = v55 - 1;
        v16 = Delimiter;
        while ( v13 )
        {
          v23 = (__int64 *)ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveTail(
                             &v54,
                             &Context);
          v24 = *v23;
          *v23 = 0;
          *(_QWORD *)&v16[4 * v15] = v24;
          operator delete(Context);
          Context = 0;
          --v15;
          v13 = v55;
        }
        Delimiter = 0;
        *((_QWORD *)a2 + 4) = v16;
        *((_DWORD *)a2 + 6) = v14;
        v17 = v51;
        v18 = v51;
        v19 = v51 - 1;
        v20 = Block;
        while ( v17 )
        {
          v21 = (__int64 *)ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveTail(
                             &v50,
                             &Context);
          v22 = *v21;
          *v21 = 0;
          v20[v19] = v22;
          operator delete(Context);
          Context = 0;
          --v19;
          v17 = v51;
        }
        *((_QWORD *)a2 + 5) = v20;
        *((_DWORD *)a2 + 7) = v18;
        *((_DWORD *)a2 + 4) = *((_DWORD *)MofData + 3);
        *((_DWORD *)a2 + 5) = *((_DWORD *)MofData + 4);
        operator delete(0);
        operator delete(0);
        ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
        ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v54);
        operator delete(v49);
        v49 = 0;
        operator delete(String);
        String = 0;
        operator delete(v59);
        v59 = 0;
        operator delete(0);
        return 0;
      }
      return 262403;
    }
  }
  if ( MofLength < 0x248 || *((_DWORD *)MofData + 129) > 0x10u )
    return 262403;
  String = 0;
  XPerfAddIn::CNICConfig::ParsePhysicalAddress(this, &String, MofData + 260, *((unsigned int *)MofData + 129));
  XPerfCore::CWStrParser::CWStrParser((XPerfCore::CWStrParser *)&Delimiter, MofData, 0x200u, 0, 0);
  v27 = *((int *)MofData + 135);
  if ( (int)v27 >= 0 && MofLength >= (unsigned int)v27 && MofLength >= v27 + 16 )
  {
    XPerfCore::CWStrParser::CWStrParser(
      (XPerfCore::CWStrParser *)&v59,
      (const char *)MofData + v27,
      v25,
      v26,
      (const char **)v43);
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 10;
    for ( i = 0; i < 4; ++i )
    {
      v31 = *(int *)&MofData[2 * i + 282];
      if ( (int)v31 < 0 || MofLength < (unsigned int)v31 || MofLength < v31 + 16 )
      {
        ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
        operator delete(v59);
        v59 = 0;
        operator delete(Delimiter);
        Delimiter = 0;
        operator delete(String);
        return 262403;
      }
      XPerfCore::CWStrParser::CWStrParser(
        (XPerfCore::CWStrParser *)&v46,
        (const char *)MofData + v31,
        v28,
        v29,
        (const char **)v44);
      v32 = v46;
      if ( *(_WORD *)v46 )
      {
        ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::AddTail(
          &v50,
          &v46);
        v32 = v46;
      }
      operator delete(v32);
      v46 = 0;
    }
    v46 = 0;
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(&v46) )
    {
      operator delete(v46);
      ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
      operator delete(v59);
      v59 = 0;
      operator delete(Delimiter);
      Delimiter = 0;
      operator delete(String);
      return 2147942414LL;
    }
    Block = 0;
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(&Block) )
    {
      operator delete(Block);
      operator delete(v46);
      ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
      operator delete(v59);
      v59 = 0;
      operator delete(Delimiter);
      Delimiter = 0;
      operator delete(String);
      return 2147942414LL;
    }
    v33 = String;
    String = 0;
    *(_QWORD *)a2 = v33;
    v34 = Delimiter;
    Delimiter = 0;
    *((_QWORD *)a2 + 1) = v34;
    v35 = v59;
    v59 = 0;
    v36 = v46;
    *(_QWORD *)v46 = v35;
    v46 = 0;
    *((_QWORD *)a2 + 4) = v36;
    *((_DWORD *)a2 + 6) = 1;
    v37 = v51;
    v38 = v51;
    v39 = v51 - 1;
    v40 = Block;
    while ( v37 )
    {
      v41 = (__int64 *)ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveTail(
                         &v50,
                         &Context);
      v42 = *v41;
      *v41 = 0;
      v40[v39] = v42;
      operator delete(Context);
      Context = 0;
      --v39;
      v37 = v51;
    }
    *((_QWORD *)a2 + 5) = v40;
    *((_DWORD *)a2 + 7) = v38;
    *((_DWORD *)a2 + 4) = *((_DWORD *)MofData + 128);
    *((_DWORD *)a2 + 5) = 0;
    operator delete(0);
    operator delete(0);
    ATL::CAtlList<ATL::CAutoVectorPtr<unsigned short>,ATL::CAutoVectorPtrElementTraits<unsigned short>>::RemoveAll(&v50);
    operator delete(v59);
    v59 = 0;
    operator delete(Delimiter);
    Delimiter = 0;
    operator delete(0);
    return 0;
  }
  operator delete(Delimiter);
  Delimiter = 0;
  operator delete(String);
  return 262403;
}

```

## disassembly

```asm
0x18007caf0  mov     [rsp+arg_0], rbx
0x18007caf5  push    rsi
0x18007caf6  push    rdi
0x18007caf7  push    r13
0x18007caf9  push    r14
0x18007cafb  push    r15
0x18007cafd  sub     rsp, 0D0h
0x18007cb04  mov     r15, rdx
0x18007cb07  movzx   eax, word ptr [r8+6]
0x18007cb0c  mov     esi, [r8+50h]
0x18007cb10  mov     rdi, [r8+48h]
0x18007cb14  xor     ebx, ebx
0x18007cb16  cmp     eax, 2
0x18007cb19  jnz     short loc_18007CB24
0x18007cb1b  cmp     [rcx+18h], bl
0x18007cb1e  jnz     loc_18007CFA7
0x18007cb24  sub     eax, 1
0x18007cb27  jz      loc_18007CFA7
0x18007cb2d  cmp     eax, 1
0x18007cb30  jz      short loc_18007CB3C
0x18007cb32  mov     eax, 40101h
0x18007cb37  jmp     loc_18007D31F
0x18007cb3c  cmp     rsi, 18h
0x18007cb40  jb      loc_18007D31A
0x18007cb46  cmp     dword ptr [rdi+8], 8
0x18007cb4a  ja      loc_18007D31A
0x18007cb50  mov     [rsp+0F8h+var_C0], rbx
0x18007cb55  mov     r9d, [rdi+8]
0x18007cb59  mov     r8, rdi
0x18007cb5c  lea     rdx, [rsp+0F8h+var_C0]
0x18007cb61  call    ?ParsePhysicalAddress@CNICConfig@XPerfAddIn@@AEAAXAEAV?$CAutoVectorPtr@G@ATL@@PEBE_K@Z; XPerfAddIn::CNICConfig::ParsePhysicalAddress(ATL::CAutoVectorPtr<ushort> &,uchar const *,unsigned __int64)
0x18007cb66  mov     [rsp+0F8h+Delimiter], rbx
0x18007cb6e  lea     r8, [rsi-14h]; unsigned __int64
0x18007cb72  lea     rdx, [rdi+14h]; unsigned __int16 *
0x18007cb76  lea     rax, [rsp+0F8h+Delimiter]
0x18007cb7e  mov     [rsp+0F8h+var_D8], rax; unsigned __int16 **
0x18007cb83  mov     r9b, 1; bool
0x18007cb86  lea     rcx, [rsp+0F8h+arg_18]; this
0x18007cb8e  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG_K_NPEAPEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *,unsigned __int64,bool,ushort const * *)
0x18007cb93  nop
0x18007cb94  mov     [rsp+0F8h+Block], rbx
0x18007cb99  mov     r8, rdi
0x18007cb9c  mov     rdx, [rsp+0F8h+Delimiter]; unsigned __int16 *
0x18007cba4  sub     r8, rdx
0x18007cba7  add     r8, rsi; unsigned __int64
0x18007cbaa  lea     rax, [rsp+0F8h+Block]
0x18007cbaf  mov     [rsp+0F8h+var_D8], rax; unsigned __int16 **
0x18007cbb4  mov     r9b, 1; bool
0x18007cbb7  lea     rcx, [rsp+0F8h+String]; this
0x18007cbbc  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG_K_NPEAPEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *,unsigned __int64,bool,ushort const * *)
0x18007cbc1  nop
0x18007cbc2  mov     r8, rdi
0x18007cbc5  mov     rdx, [rsp+0F8h+Block]; unsigned __int16 *
0x18007cbca  sub     r8, rdx
0x18007cbcd  add     r8, rsi; unsigned __int64
0x18007cbd0  lea     rax, [rsp+0F8h+Delimiter]
0x18007cbd8  mov     [rsp+0F8h+var_D8], rax; unsigned __int16 **
0x18007cbdd  xor     r9d, r9d; bool
0x18007cbe0  lea     rcx, [rsp+0F8h+var_A8]; this
0x18007cbe5  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG_K_NPEAPEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *,unsigned __int64,bool,ushort const * *)
0x18007cbea  nop
0x18007cbeb  xorps   xmm0, xmm0
0x18007cbee  movdqu  [rsp+0F8h+var_70], xmm0
0x18007cbf7  mov     [rsp+0F8h+var_60], rbx
0x18007cbff  xorps   xmm1, xmm1
0x18007cc02  movdqu  [rsp+0F8h+var_58], xmm1
0x18007cc0b  mov     [rsp+0F8h+var_48], 0Ah
0x18007cc16  mov     r14d, 3Bh ; ';'
0x18007cc1c  mov     dword ptr [rsp+0F8h+Delimiter], r14d
0x18007cc24  mov     [rsp+0F8h+Context], rbx
0x18007cc29  lea     r8, [rsp+0F8h+Context]; Context
0x18007cc2e  lea     rdx, [rsp+0F8h+Delimiter]; Delimiter
0x18007cc36  mov     rcx, [rsp+0F8h+String]; String
0x18007cc3b  call    cs:__imp_wcstok_s
0x18007cc41  mov     rsi, rax
0x18007cc44  test    rsi, rsi
0x18007cc47  jz      short loc_18007CC92
0x18007cc49  mov     rdx, rsi; unsigned __int16 *
0x18007cc4c  lea     rcx, [rsp+0F8h+Block]; this
0x18007cc51  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *)
0x18007cc56  nop
0x18007cc57  lea     rdx, [rsp+0F8h+Block]
0x18007cc5c  lea     rcx, [rsp+0F8h+var_70]
0x18007cc64  call    ?AddTail@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAPEAU__POSITION@@AEAV?$CAutoVectorPtr@G@2@@Z; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::AddTail(ATL::CAutoVectorPtr<ushort> &)
0x18007cc69  lea     r8, [rsp+0F8h+Context]; Context
0x18007cc6e  lea     rdx, [rsp+0F8h+Delimiter]; Delimiter
0x18007cc76  xor     ecx, ecx; String
0x18007cc78  call    cs:__imp_wcstok_s
0x18007cc7e  mov     rsi, rax
0x18007cc81  mov     rcx, [rsp+0F8h+Block]; Block
0x18007cc86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cc8b  mov     [rsp+0F8h+Block], rbx
0x18007cc90  jmp     short loc_18007CC44
0x18007cc92  xorps   xmm0, xmm0
0x18007cc95  movdqu  [rsp+0F8h+var_A0], xmm0
0x18007cc9b  mov     [rsp+0F8h+var_90], rbx
0x18007cca0  xorps   xmm1, xmm1
0x18007cca3  movdqu  [rsp+0F8h+var_88], xmm1
0x18007cca9  mov     [rsp+0F8h+var_78], 0Ah
0x18007ccb4  mov     dword ptr [rsp+0F8h+Delimiter], r14d
0x18007ccbc  mov     [rsp+0F8h+Context], rbx
0x18007ccc1  lea     r8, [rsp+0F8h+Context]; Context
0x18007ccc6  lea     rdx, [rsp+0F8h+Delimiter]; Delimiter
0x18007ccce  mov     rcx, [rsp+0F8h+var_A8]; String
0x18007ccd3  call    cs:__imp_wcstok_s
0x18007ccd9  mov     rsi, rax
0x18007ccdc  test    rsi, rsi
0x18007ccdf  jz      short loc_18007CD27
0x18007cce1  mov     rdx, rsi; unsigned __int16 *
0x18007cce4  lea     rcx, [rsp+0F8h+Block]; this
0x18007cce9  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *)
0x18007ccee  nop
0x18007ccef  lea     rdx, [rsp+0F8h+Block]
0x18007ccf4  lea     rcx, [rsp+0F8h+var_A0]
0x18007ccf9  call    ?AddTail@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAPEAU__POSITION@@AEAV?$CAutoVectorPtr@G@2@@Z; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::AddTail(ATL::CAutoVectorPtr<ushort> &)
0x18007ccfe  lea     r8, [rsp+0F8h+Context]; Context
0x18007cd03  lea     rdx, [rsp+0F8h+Delimiter]; Delimiter
0x18007cd0b  xor     ecx, ecx; String
0x18007cd0d  call    cs:__imp_wcstok_s
0x18007cd13  mov     rsi, rax
0x18007cd16  mov     rcx, [rsp+0F8h+Block]; Block
0x18007cd1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cd20  mov     [rsp+0F8h+Block], rbx
0x18007cd25  jmp     short loc_18007CCDC
0x18007cd27  mov     [rsp+0F8h+Delimiter], rbx
0x18007cd2f  mov     rdx, [rsp+0F8h+var_60]
0x18007cd37  lea     rcx, [rsp+0F8h+Delimiter]
0x18007cd3f  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18007cd44  test    al, al
0x18007cd46  jnz     short loc_18007CDB6
0x18007cd48  mov     rcx, [rsp+0F8h+Delimiter]; Block
0x18007cd50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cd55  nop
0x18007cd56  lea     rcx, [rsp+0F8h+var_A0]
0x18007cd5b  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cd60  nop
0x18007cd61  lea     rcx, [rsp+0F8h+var_70]
0x18007cd69  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cd6e  nop
0x18007cd6f  mov     rcx, [rsp+0F8h+var_A8]; Block
0x18007cd74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cd79  mov     [rsp+0F8h+var_A8], rbx
0x18007cd7e  mov     rcx, [rsp+0F8h+String]; Block
0x18007cd83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cd88  mov     [rsp+0F8h+String], rbx
0x18007cd8d  mov     rcx, [rsp+0F8h+arg_18]; Block
0x18007cd95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cd9a  mov     [rsp+0F8h+arg_18], rbx
0x18007cda2  mov     rcx, [rsp+0F8h+var_C0]; Block
0x18007cda7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cdac  mov     eax, 8007000Eh
0x18007cdb1  jmp     loc_18007D31F
0x18007cdb6  mov     [rsp+0F8h+Block], rbx
0x18007cdbb  mov     rdx, [rsp+0F8h+var_90]
0x18007cdc0  lea     rcx, [rsp+0F8h+Block]
0x18007cdc5  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18007cdca  test    al, al
0x18007cdcc  jnz     short loc_18007CE47
0x18007cdce  mov     rcx, [rsp+0F8h+Block]; Block
0x18007cdd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cdd8  nop
0x18007cdd9  mov     rcx, [rsp+0F8h+Delimiter]; Block
0x18007cde1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cde6  nop
0x18007cde7  lea     rcx, [rsp+0F8h+var_A0]
0x18007cdec  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cdf1  nop
0x18007cdf2  lea     rcx, [rsp+0F8h+var_70]
0x18007cdfa  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cdff  nop
0x18007ce00  mov     rcx, [rsp+0F8h+var_A8]; Block
0x18007ce05  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ce0a  mov     [rsp+0F8h+var_A8], rbx
0x18007ce0f  mov     rcx, [rsp+0F8h+String]; Block
0x18007ce14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ce19  mov     [rsp+0F8h+String], rbx
0x18007ce1e  mov     rcx, [rsp+0F8h+arg_18]; Block
0x18007ce26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ce2b  mov     [rsp+0F8h+arg_18], rbx
0x18007ce33  mov     rcx, [rsp+0F8h+var_C0]; Block
0x18007ce38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ce3d  mov     eax, 8007000Eh
0x18007ce42  jmp     loc_18007D31F
0x18007ce47  mov     rax, [rsp+0F8h+var_C0]
0x18007ce4c  mov     [rsp+0F8h+var_C0], rbx
0x18007ce51  mov     [r15], rax
0x18007ce54  mov     rax, [rsp+0F8h+arg_18]
0x18007ce5c  mov     [rsp+0F8h+arg_18], rbx
0x18007ce64  mov     [r15+8], rax
0x18007ce68  mov     rax, [rsp+0F8h+var_60]
0x18007ce70  mov     r13, rax
0x18007ce73  lea     rsi, [rax-1]
0x18007ce77  mov     r14, [rsp+0F8h+Delimiter]
0x18007ce7f  test    rax, rax
0x18007ce82  jnz     loc_18007CF67
0x18007ce88  mov     [rsp+0F8h+Delimiter], rbx
0x18007ce90  mov     [r15+20h], r14
0x18007ce94  mov     [r15+18h], r13d
0x18007ce98  mov     rax, [rsp+0F8h+var_90]
0x18007ce9d  mov     r13, rax
0x18007cea0  lea     rsi, [rax-1]
0x18007cea4  mov     r14, [rsp+0F8h+Block]
0x18007cea9  test    rax, rax
0x18007ceac  jnz     loc_18007CF32
0x18007ceb2  mov     [r15+28h], r14
0x18007ceb6  mov     [r15+1Ch], r13d
0x18007ceba  mov     eax, [rdi+0Ch]
0x18007cebd  mov     [r15+10h], eax
0x18007cec1  mov     eax, [rdi+10h]
0x18007cec4  mov     [r15+14h], eax
0x18007cec8  xor     ecx, ecx; Block
0x18007ceca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cecf  nop
0x18007ced0  mov     rcx, rbx; Block
0x18007ced3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ced8  nop
0x18007ced9  lea     rcx, [rsp+0F8h+var_A0]
0x18007cede  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cee3  nop
0x18007cee4  lea     rcx, [rsp+0F8h+var_70]
0x18007ceec  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveAll(void)
0x18007cef1  nop
0x18007cef2  mov     rcx, [rsp+0F8h+var_A8]; Block
0x18007cef7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cefc  mov     [rsp+0F8h+var_A8], rbx
0x18007cf01  mov     rcx, [rsp+0F8h+String]; Block
0x18007cf06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cf0b  mov     [rsp+0F8h+String], rbx
0x18007cf10  mov     rcx, [rsp+0F8h+arg_18]; Block
0x18007cf18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cf1d  mov     [rsp+0F8h+arg_18], rbx
0x18007cf25  mov     rcx, rbx; Block
0x18007cf28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cf2d  jmp     loc_18007D2B2
0x18007cf32  lea     rdx, [rsp+0F8h+Context]
0x18007cf37  lea     rcx, [rsp+0F8h+var_A0]
0x18007cf3c  call    ?RemoveTail@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAA?AV?$CAutoVectorPtr@G@2@XZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveTail(void)
0x18007cf41  mov     rcx, [rax]
0x18007cf44  mov     [rax], rbx
0x18007cf47  mov     [r14+rsi*8], rcx
0x18007cf4b  mov     rcx, [rsp+0F8h+Context]; Block
0x18007cf50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cf55  mov     [rsp+0F8h+Context], rbx
0x18007cf5a  dec     rsi
0x18007cf5d  mov     rax, [rsp+0F8h+var_90]
0x18007cf62  jmp     loc_18007CEA9
0x18007cf67  lea     rdx, [rsp+0F8h+Context]
0x18007cf6c  lea     rcx, [rsp+0F8h+var_70]
0x18007cf74  call    ?RemoveTail@?$CAtlList@V?$CAutoVectorPtr@G@ATL@@V?$CAutoVectorPtrElementTraits@G@2@@ATL@@QEAA?AV?$CAutoVectorPtr@G@2@XZ; ATL::CAtlList<ATL::CAutoVectorPtr<ushort>,ATL::CAutoVectorPtrElementTraits<ushort>>::RemoveTail(void)
0x18007cf79  mov     rcx, [rax]
0x18007cf7c  mov     [rax], rbx
0x18007cf7f  mov     [r14+rsi*8], rcx
0x18007cf83  mov     rcx, [rsp+0F8h+Context]; Block
0x18007cf88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cf8d  mov     [rsp+0F8h+Context], rbx
0x18007cf92  dec     rsi
0x18007cf95  mov     rax, [rsp+0F8h+var_60]
0x18007cf9d  jmp     loc_18007CE7F
0x18007cfa2  jmp     loc_18007D311
0x18007cfa7  cmp     rsi, 248h
0x18007cfae  jb      loc_18007D31A
0x18007cfb4  cmp     dword ptr [rdi+204h], 10h
0x18007cfbb  ja      loc_18007D31A
0x18007cfc1  mov     [rsp+0F8h+String], rbx
0x18007cfc6  mov     r9d, [rdi+204h]
0x18007cfcd  lea     r8, [rdi+208h]
0x18007cfd4  lea     rdx, [rsp+0F8h+String]
0x18007cfd9  call    ?ParsePhysicalAddress@CNICConfig@XPerfAddIn@@AEAAXAEAV?$CAutoVectorPtr@G@ATL@@PEBE_K@Z; XPerfAddIn::CNICConfig::ParsePhysicalAddress(ATL::CAutoVectorPtr<ushort> &,uchar const *,unsigned __int64)
0x18007cfde  mov     [rsp+0F8h+var_D8], rbx; char **
0x18007cfe3  xor     r9d, r9d; bool
0x18007cfe6  mov     r8d, 200h; unsigned __int64
0x18007cfec  mov     rdx, rdi; unsigned __int16 *
0x18007cfef  lea     rcx, [rsp+0F8h+Delimiter]; this
0x18007cff7  call    ??0CWStrParser@XPerfCore@@QEAA@PEBG_K_NPEAPEBG@Z; XPerfCore::CWStrParser::CWStrParser(ushort const *,unsigned __int64,bool,ushort const * *)
0x18007cffc  nop
0x18007cffd  movsxd  rcx, dword ptr [rdi+21Ch]
0x18007d004  test    ecx, ecx
0x18007d006  js      loc_18007D2EB
0x18007d00c  mov     eax, ecx
0x18007d00e  cmp     rsi, rax
0x18007d011  jb      loc_18007D2EB
0x18007d017  mov     rdx, rcx
0x18007d01a  lea     rax, [rcx+10h]
0x18007d01e  cmp     rsi, rax
0x18007d021  jb      loc_18007D2EB
0x18007d027  add     rdx, rdi; char *
0x18007d02a  lea     rcx, [rsp+0F8h+arg_18]; this
0x18007d032  call    ??0CWStrParser@XPerfCore@@QEAA@PEBD_K_NPEAPEBD@Z; XPerfCore::CWStrParser::CWStrParser(char const *,unsigned __int64,bool,char const * *)
0x18007d037  nop
0x18007d038  xorps   xmm0, xmm0
0x18007d03b  movdqu  [rsp+0F8h+var_A0], xmm0
0x18007d041  mov     [rsp+0F8h+var_90], rbx
0x18007d046  xorps   xmm1, xmm1
0x18007d049  movdqu  [rsp+0F8h+var_88], xmm1
0x18007d04f  mov     [rsp+0F8h+var_78], 0Ah
0x18007d05a  mov     r14, rbx
0x18007d05d  cmp     r14, 4
0x18007d061  jnb     loc_18007D10A
0x18007d067  movsxd  rcx, dword ptr [rdi+r14*4+234h]
0x18007d06f  test    ecx, ecx
  ... truncated ...
```
