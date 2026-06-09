# CErrClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180022670`
- end: `0x1800228c9`
- name: `?CreateInstance@CErrClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `601`
- prototype: `int(CErrClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180013870`
- `0x18001b0a0`
- `0x18001d0f0`
- `0x180022670`
- `0x180029560`
- `0x18007b0d0`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180022728`
- `MSDART!MpHeapAlloc` at `0x180022728`

## string_xrefs

- `0x18002269a`: `<CErrClassFactory::CreateInstance|OLEDB|ERR> `
- `0x1800226f7`: `<CErrClassFactory::CreateInstance|OLEDB|ERR> `
- `0x1800227ca`: `<CErrClassFactory::CreateInstance|OLEDB|ERR> `
- `0x180022830`: `<CErrClassFactory::CreateInstance|OLEDB|ERR> `
- `0x180022881`: `<CErrClassFactory::CreateInstance|OLEDB|ERR> `
- `0x1800226b7`: `<CErrClassFactory::CreateInstance|Trace|HR> `
- `0x1800227ec`: `<CErrClassFactory::CreateInstance|Trace|HR> `
- `0x180022852`: `<CErrClassFactory::CreateInstance|Trace|HR> `
- `0x18002289c`: `<CErrClassFactory::CreateInstance|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CErrClassFactory::CreateInstance(
        CErrClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // edi
  int Interface; // eax
  unsigned int v14; // edx
  unsigned int v15; // ebx

  if ( !a4 )
  {
    v6 = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    OLEDBTraceErr(-2147024809, L"<CErrClassFactory::CreateInstance|OLEDB|ERR> ", 0x1A0u);
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    v7 = 427017;
    return (unsigned int)bidTraceHR(off_1800C8530[0], v7, L"<CErrClassFactory::CreateInstance|Trace|HR> ", v6);
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    OLEDBTraceErr(-2147221232, L"<CErrClassFactory::CreateInstance|OLEDB|ERR> ", 0x1AAu);
    if ( (bidGblFlags & 2) == 0 )
      return v6;
    v7 = 437257;
    return (unsigned int)bidTraceHR(off_1800C8530[0], v7, L"<CErrClassFactory::CreateInstance|Trace|HR> ", v6);
  }
  v9 = MpHeapAlloc(g_hHeapHandle, 19922944, 96);
  if ( v9 )
  {
    *(_QWORD *)v9 = &CError::`vftable';
    _InterlockedIncrement(&g_cObj);
    *(_DWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v9 + 16) = v9;
    *(_QWORD *)(v9 + 24) = 0;
    *(_QWORD *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 48) = 0;
    *(_BYTE *)(v9 + 88) = 0;
    *(_QWORD *)(v9 + 72) = 0;
    *(_QWORD *)(v9 + 80) = 0;
    *(_DWORD *)(v9 + 40) = 0;
    *(_DWORD *)(v9 + 64) = 0;
    *(_DWORD *)(v9 + 68) = 1;
    *(_QWORD *)(v9 + 56) = 0;
    v10 = CError::FInit((CError *)v9);
    v12 = v10;
    if ( v10 >= 0 )
    {
      Interface = CError::QueryInterface((CError *)v9, a3, a4);
      v12 = Interface;
      if ( Interface < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(Interface, L"<CErrClassFactory::CreateInstance|OLEDB|ERR> ", 0x1CBu);
        CError::`scalar deleting destructor'((CError *)v9, v14);
      }
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_1800C8530[0], 474121, L"<CErrClassFactory::CreateInstance|Trace|HR> ", v12);
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v10, L"<CErrClassFactory::CreateInstance|OLEDB|ERR> ", 0x1C3u);
      CError::`scalar deleting destructor'((CError *)v9, v11);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(off_1800C8530[0], 464905, L"<CErrClassFactory::CreateInstance|Trace|HR> ", v12);
    }
    return v12;
  }
  else
  {
    v15 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CErrClassFactory::CreateInstance|OLEDB|ERR> ", 0x1B5u);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C8530[0],
                               448521,
                               L"<CErrClassFactory::CreateInstance|Trace|HR> ",
                               2147942414LL);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x180022670  push    rbx
0x180022672  push    rsi
0x180022673  push    rdi
0x180022674  push    r14
0x180022676  sub     rsp, 38h
0x18002267a  mov     rsi, r9
0x18002267d  mov     r14, r8
0x180022680  test    r9, r9
0x180022683  jnz     short loc_1800226D6
0x180022685  mov     eax, cs:_bidGblFlags
0x18002268b  mov     ebx, 80070057h
0x180022690  test    al, 2
0x180022692  jz      short loc_1800226CF
0x180022694  mov     r8d, 1A0h; unsigned int
0x18002269a  lea     rdx, aCerrclassfacto_2; "<CErrClassFactory::CreateInstance|OLEDB"...
0x1800226a1  mov     ecx, ebx; int
0x1800226a3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800226a8  mov     eax, cs:_bidGblFlags
0x1800226ae  test    al, 2
0x1800226b0  jz      short loc_1800226CF
0x1800226b2  mov     edx, 68409h
0x1800226b7  lea     r8, aCerrclassfacto_1; "<CErrClassFactory::CreateInstance|Trace"...
0x1800226be  mov     r9d, ebx
0x1800226c1  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800226c8  call    _bidTraceHR
0x1800226cd  mov     ebx, eax
0x1800226cf  mov     eax, ebx
0x1800226d1  jmp     loc_1800228BE
0x1800226d6  mov     qword ptr [r9], 0
0x1800226dd  test    rdx, rdx
0x1800226e0  jz      short loc_180022716
0x1800226e2  mov     eax, cs:_bidGblFlags
0x1800226e8  mov     ebx, 80040110h
0x1800226ed  test    al, 2
0x1800226ef  jz      short loc_1800226CF
0x1800226f1  mov     r8d, 1AAh; unsigned int
0x1800226f7  lea     rdx, aCerrclassfacto_2; "<CErrClassFactory::CreateInstance|OLEDB"...
0x1800226fe  mov     ecx, ebx; int
0x180022700  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180022705  mov     eax, cs:_bidGblFlags
0x18002270b  test    al, 2
0x18002270d  jz      short loc_1800226CF
0x18002270f  mov     edx, 6AC09h
0x180022714  jmp     short loc_1800226B7
0x180022716  mov     edx, 1300000h
0x18002271b  mov     r8d, 60h ; '`'
0x180022721  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180022728  call    cs:__imp_MpHeapAlloc
0x18002272e  mov     rbx, rax
0x180022731  mov     [rsp+58h+arg_18], rax
0x180022736  test    rax, rax
0x180022739  jz      loc_18002286C
0x18002273f  lea     rax, ??_7CError@@6B@; const CError::`vftable'
0x180022746  mov     [rbx], rax
0x180022749  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180022750  mov     dword ptr [rbx+8], 0
0x180022757  mov     [rbx+10h], rbx
0x18002275b  mov     qword ptr [rbx+18h], 0
0x180022763  mov     qword ptr [rbx+20h], 0
0x18002276b  mov     qword ptr [rbx+30h], 0
0x180022773  mov     byte ptr [rbx+58h], 0
0x180022777  mov     qword ptr [rbx+48h], 0
0x18002277f  mov     qword ptr [rbx+50h], 0
0x180022787  mov     dword ptr [rbx+28h], 0
0x18002278e  mov     dword ptr [rbx+40h], 0
0x180022795  mov     dword ptr [rbx+44h], 1
0x18002279c  mov     qword ptr [rbx+38h], 0
0x1800227a4  test    rbx, rbx
0x1800227a7  jz      loc_18002286C
0x1800227ad  mov     rcx, rbx; this
0x1800227b0  call    ?FInit@CError@@QEAAJXZ; CError::FInit(void)
0x1800227b5  mov     edi, eax
0x1800227b7  test    eax, eax
0x1800227b9  jns     short loc_18002280D
0x1800227bb  test    byte ptr cs:_bidGblFlags, 2
0x1800227c2  jz      short loc_1800227D8
0x1800227c4  mov     r8d, 1C3h; unsigned int
0x1800227ca  lea     rdx, aCerrclassfacto_2; "<CErrClassFactory::CreateInstance|OLEDB"...
0x1800227d1  mov     ecx, eax; int
0x1800227d3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800227d8  mov     rcx, rbx; this
0x1800227db  call    ??_GCError@@QEAAPEAXI@Z; CError::`scalar deleting destructor'(uint)
0x1800227e0  test    byte ptr cs:_bidGblFlags, 2
0x1800227e7  jz      short loc_180022806
0x1800227e9  mov     r9d, edi
0x1800227ec  lea     r8, aCerrclassfacto_1; "<CErrClassFactory::CreateInstance|Trace"...
0x1800227f3  mov     edx, 71809h
0x1800227f8  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800227ff  call    _bidTraceHR
0x180022804  mov     edi, eax
0x180022806  mov     eax, edi
0x180022808  jmp     loc_1800228BE
0x18002280d  mov     r8, rsi; void **
0x180022810  mov     rdx, r14; struct _GUID *
0x180022813  mov     rcx, rbx; this
0x180022816  call    ?QueryInterface@CError@@UEAAJAEBU_GUID@@PEAPEAX@Z; CError::QueryInterface(_GUID const &,void * *)
0x18002281b  mov     edi, eax
0x18002281d  test    eax, eax
0x18002281f  jns     short loc_180022846
0x180022821  test    byte ptr cs:_bidGblFlags, 2
0x180022828  jz      short loc_18002283E
0x18002282a  mov     r8d, 1CBh; unsigned int
0x180022830  lea     rdx, aCerrclassfacto_2; "<CErrClassFactory::CreateInstance|OLEDB"...
0x180022837  mov     ecx, eax; int
0x180022839  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002283e  mov     rcx, rbx; this
0x180022841  call    ??_GCError@@QEAAPEAXI@Z; CError::`scalar deleting destructor'(uint)
0x180022846  test    byte ptr cs:_bidGblFlags, 2
0x18002284d  jz      short loc_180022806
0x18002284f  mov     r9d, edi
0x180022852  lea     r8, aCerrclassfacto_1; "<CErrClassFactory::CreateInstance|Trace"...
0x180022859  mov     edx, 73C09h
0x18002285e  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180022865  call    _bidTraceHR
0x18002286a  jmp     short loc_180022806
0x18002286c  mov     eax, cs:_bidGblFlags
0x180022872  mov     ebx, 8007000Eh
0x180022877  test    al, 2
0x180022879  jz      short loc_1800228B6
0x18002287b  mov     r8d, 1B5h; unsigned int
0x180022881  lea     rdx, aCerrclassfacto_2; "<CErrClassFactory::CreateInstance|OLEDB"...
0x180022888  mov     ecx, ebx; int
0x18002288a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002288f  mov     eax, cs:_bidGblFlags
0x180022895  test    al, 2
0x180022897  jz      short loc_1800228B6
0x180022899  mov     r9d, ebx
0x18002289c  lea     r8, aCerrclassfacto_1; "<CErrClassFactory::CreateInstance|Trace"...
0x1800228a3  mov     edx, 6D809h
0x1800228a8  mov     rcx, cs:off_1800C8530; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800228af  call    _bidTraceHR
0x1800228b4  mov     ebx, eax
0x1800228b6  mov     eax, ebx
0x1800228b8  jmp     short loc_1800228BE
0x1800228ba  mov     eax, dword ptr [rsp+58h+arg_18]
0x1800228be  add     rsp, 38h
0x1800228c2  pop     r14
0x1800228c4  pop     rdi
0x1800228c5  pop     rsi
0x1800228c6  pop     rbx
0x1800228c7  retn
```
