# CResourceManager::CResourceManager(void)

- ea: `0x180072218`
- end: `0x180072511`
- name: `??0CResourceManager@@QEAA@XZ`
- size: `761`
- prototype: `CResourceManager *__fastcall(CResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180074c6c`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18000f634`
- `0x18000f7e4`
- `0x18002c6c8`
- `0x180071bd4`
- `0x180072218`
- `0x180075708`
- `0x18009bd1c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800723af`
- `KERNEL32!GetLastError` at `0x1800723af`
- `KERNEL32!CreateEventW` at `0x18007239d`
- `KERNEL32!CreateEventW` at `0x18007239d`
- `mqsec!GetFalconKeyValue` at `0x18007245a`
- `mqsec!GetFalconKeyValue` at `0x1800724ca`
- `mqsec!GetFalconKeyValue` at `0x18007245a`
- `mqsec!GetFalconKeyValue` at `0x1800724ca`

## string_xrefs

- `0x180072298`: `StoreXactLogPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
CResourceManager *__fastcall CResourceManager::CResourceManager(CResourceManager *this)
{
  unsigned int v2; // edx
  _DWORD *v3; // rax
  _DWORD *v4; // rax
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v7; // ebx
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+98h] [rbp+40h] BYREF
  _DWORD *v11; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v12; // [rsp+A8h] [rbp+50h] BYREF

  *(_QWORD *)this = &CResourceManager::`vftable';
  *((_QWORD *)this + 1) = &CMap<unsigned long,unsigned long,CSeqPacket *,CSeqPacket * &>::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 17;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 10;
  *((_QWORD *)this + 7) = &CMap<unsigned long,unsigned long,CSeqPacket *,CSeqPacket * &>::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 17;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 10;
  CPingPong::CPingPong((CResourceManager *)((char *)this + 136), this, L"MQTrans", L"StoreXactLogPath", L"Transactions");
  CIResourceManagerSink::CIResourceManagerSink((CResourceManager *)((char *)this + 2752), this);
  *((_QWORD *)this + 347) = 0;
  *((_QWORD *)this + 348) = 0;
  *((_QWORD *)this + 350) = 0;
  CCriticalSection::CCriticalSection((CResourceManager *)((char *)this + 2808), v2);
  *((_QWORD *)this + 341) = 0;
  *((_QWORD *)this + 342) = 0;
  *((_QWORD *)this + 343) = 0;
  *((_DWORD *)this + 27) = 0;
  v3 = MmAllocate(0x40u);
  v11 = v3;
  if ( v3 )
  {
    *(_QWORD *)v3 = &CList<CQueue *,CQueue * &>::`vftable';
    v3[6] = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 5) = 0;
    v3[12] = 10;
    *((_QWORD *)v3 + 7) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 347) = v3;
  v4 = MmAllocate(0x40u);
  v11 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &CList<CQueue *,CQueue * &>::`vftable';
    v4[6] = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 5) = 0;
    v4[12] = 10;
    v4[15] = 1;
    v4[14] = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 348) = v4;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 356) = 0;
  *((_DWORD *)this + 698) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 350) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 10, WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids, LastError);
    if ( v7 )
      LogMsgNTStatus(v7, (wchar_t *)L"xactrm", 0x5DDu);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
    throw (bad_win32_error *)pExceptionObject;
  }
  v10 = 180000;
  *((_DWORD *)this + 714) = 180000;
  LODWORD(v11) = 4;
  v12 = 4;
  GetFalconKeyValue(L"Q890746_WaitMilliseconds", &v12, (char *)this + 2856, (unsigned int *)&v11, (const wchar_t *)&v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      11,
      WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids,
      *((unsigned int *)this + 714));
  v10 = 2;
  *((_DWORD *)this + 715) = 2;
  LODWORD(v11) = 4;
  v12 = 4;
  GetFalconKeyValue(
    L"Q890746_SleepMilliseconds",
    &v12,
    (char *)this + 2860,
    (unsigned int *)&v11,
    (const wchar_t *)&v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      12,
      WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids,
      *((unsigned int *)this + 715));
  return this;
}

```

## disassembly

```asm
0x180072218  mov     [rsp-30h+arg_0], rcx
0x18007221d  push    rbp
0x18007221e  push    rbx
0x18007221f  push    rsi
0x180072220  push    rdi
0x180072221  push    r14
0x180072223  push    r15
0x180072225  mov     rbp, rsp
0x180072228  sub     rsp, 58h
0x18007222c  mov     rbx, rcx
0x18007222f  lea     rax, ??_7CResourceManager@@6B@; const CResourceManager::`vftable'
0x180072236  mov     [rcx], rax
0x180072239  lea     rax, ??_7?$CMap@KKPEAVCSeqPacket@@AEAPEAV1@@@6B@; const CMap<ulong,ulong,CSeqPacket *,CSeqPacket * &>::`vftable'
0x180072240  mov     [rcx+8], rax
0x180072244  xor     esi, esi
0x180072246  mov     [rcx+10h], rsi
0x18007224a  mov     qword ptr [rcx+18h], 11h
0x180072252  mov     [rcx+20h], rsi
0x180072256  mov     [rcx+28h], rsi
0x18007225a  lea     r15d, [rsi+0Ah]
0x18007225e  mov     [rcx+30h], r15d
0x180072262  lea     rax, ??_7?$CMap@KKPEAVCSeqPacket@@AEAPEAV1@@@6B@; const CMap<ulong,ulong,CSeqPacket *,CSeqPacket * &>::`vftable'
0x180072269  mov     [rcx+38h], rax
0x18007226d  mov     [rcx+40h], rsi
0x180072271  mov     qword ptr [rcx+48h], 11h
0x180072279  mov     [rcx+50h], rsi
0x18007227d  mov     [rcx+58h], rsi
0x180072281  mov     [rcx+60h], r15d
0x180072285  add     rcx, 88h; this
0x18007228c  lea     rax, aTransactions; "Transactions"
0x180072293  mov     [rsp+58h+var_38], rax; wchar_t *
0x180072298  lea     r9, aStorexactlogpa; "StoreXactLogPath"
0x18007229f  lea     r8, aMqtrans_0; "MQTrans"
0x1800722a6  mov     rdx, rbx; struct CPersist *
0x1800722a9  call    ??0CPingPong@@QEAA@PEAVCPersist@@PEB_W11@Z; CPingPong::CPingPong(CPersist *,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800722ae  lea     rcx, [rbx+0AC0h]; this
0x1800722b5  mov     rdx, rbx; struct CResourceManager *
0x1800722b8  call    ??0CIResourceManagerSink@@QEAA@PEAVCResourceManager@@@Z; CIResourceManagerSink::CIResourceManagerSink(CResourceManager *)
0x1800722bd  nop
0x1800722be  mov     [rbx+0AD8h], rsi
0x1800722c5  mov     [rbx+0AE0h], rsi
0x1800722cc  mov     [rbx+0AF0h], rsi
0x1800722d3  lea     rcx, [rbx+0AF8h]; this
0x1800722da  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x1800722df  nop
0x1800722e0  mov     [rbx+0AA8h], rsi
0x1800722e7  mov     [rbx+0AB0h], rsi
0x1800722ee  mov     [rbx+0AB8h], rsi
0x1800722f5  mov     [rbx+6Ch], esi
0x1800722f8  lea     r14d, [rsi+40h]
0x1800722fc  mov     ecx, r14d; unsigned __int64
0x1800722ff  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180072304  mov     [rbp+arg_10], rax
0x180072308  lea     rdi, ??_7?$CList@PEAVCQueue@@AEAPEAV1@@@6B@; const CList<CQueue *,CQueue * &>::`vftable'
0x18007230f  test    rax, rax
0x180072312  jz      short loc_180072334
0x180072314  mov     [rax], rdi
0x180072317  mov     [rax+18h], esi
0x18007231a  mov     [rax+20h], rsi
0x18007231e  mov     [rax+10h], rsi
0x180072322  mov     [rax+8], rsi
0x180072326  mov     [rax+28h], rsi
0x18007232a  mov     [rax+30h], r15d
0x18007232e  mov     [rax+38h], rsi
0x180072332  jmp     short loc_180072337
0x180072334  mov     rax, rsi
0x180072337  mov     [rbx+0AD8h], rax
0x18007233e  mov     rcx, r14; unsigned __int64
0x180072341  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180072346  mov     [rbp+arg_10], rax
0x18007234a  mov     r14d, 1
0x180072350  test    rax, rax
0x180072353  jz      short loc_180072378
0x180072355  mov     [rax], rdi
0x180072358  mov     [rax+18h], esi
0x18007235b  mov     [rax+20h], rsi
0x18007235f  mov     [rax+10h], rsi
0x180072363  mov     [rax+8], rsi
0x180072367  mov     [rax+28h], rsi
0x18007236b  mov     [rax+30h], r15d
0x18007236f  mov     [rax+3Ch], r14d
0x180072373  mov     [rax+38h], esi
0x180072376  jmp     short loc_18007237B
0x180072378  mov     rax, rsi
0x18007237b  mov     [rbx+0AE0h], rax
0x180072382  mov     [rbx+70h], esi
0x180072385  mov     [rbx+0B20h], rsi
0x18007238c  mov     [rbx+0AE8h], esi
0x180072392  xor     r9d, r9d; lpName
0x180072395  xor     r8d, r8d; bInitialState
0x180072398  mov     edx, r14d; bManualReset
0x18007239b  xor     ecx, ecx; lpEventAttributes
0x18007239d  call    cs:__imp_CreateEventW
0x1800723a3  mov     [rbx+0AF0h], rax
0x1800723aa  test    rax, rax
0x1800723ad  jnz     short loc_180072420
0x1800723af  call    cs:__imp_GetLastError
0x1800723b5  mov     ebx, eax
0x1800723b7  lea     rdi, WPP_GLOBAL_Control
0x1800723be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800723c5  cmp     rcx, rdi
0x1800723c8  jz      short loc_1800723EC
0x1800723ca  test    [rcx+15Ch], r14b
0x1800723d1  jz      short loc_1800723EC
0x1800723d3  mov     edx, r15d
0x1800723d6  mov     r9d, eax
0x1800723d9  lea     r8, WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids
0x1800723e0  mov     rcx, [rcx+150h]
0x1800723e7  call    WPP_SF_d
0x1800723ec  test    ebx, ebx
0x1800723ee  jz      short loc_180072404
0x1800723f0  mov     r8d, 5DDh; unsigned __int16
0x1800723f6  lea     rdx, aXactrm; "xactrm"
0x1800723fd  mov     ecx, ebx; int
0x1800723ff  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180072404  mov     edx, ebx; unsigned int
0x180072406  lea     rcx, [rbp+pExceptionObject]; this
0x18007240a  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18007240f  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180072416  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18007241a  call    _CxxThrowException_0
0x180072420  mov     eax, 2BF20h
0x180072425  mov     [rbp+arg_8], eax
0x180072428  lea     rsi, [rbx+0B28h]
0x18007242f  mov     [rsi], eax
0x180072431  mov     r14d, 4
0x180072437  mov     dword ptr [rbp+arg_10], r14d
0x18007243b  mov     [rbp+arg_18], r14d
0x18007243f  lea     rax, [rbp+arg_8]
0x180072443  mov     [rsp+58h+var_38], rax
0x180072448  lea     r9, [rbp+arg_10]
0x18007244c  mov     r8, rsi
0x18007244f  lea     rdx, [rbp+arg_18]
0x180072453  lea     rcx, aQ890746Waitmil; "Q890746_WaitMilliseconds"
0x18007245a  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180072460  lea     rdi, WPP_GLOBAL_Control
0x180072467  mov     rcx, cs:WPP_GLOBAL_Control
0x18007246e  cmp     rcx, rdi
0x180072471  jz      short loc_180072496
0x180072473  test    [rcx+15Ch], r14b
0x18007247a  jz      short loc_180072496
0x18007247c  lea     edx, [r14+7]
0x180072480  mov     r9d, [rsi]
0x180072483  lea     r8, WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids
0x18007248a  mov     rcx, [rcx+150h]
0x180072491  call    WPP_SF_d
0x180072496  mov     eax, 2
0x18007249b  mov     [rbp+arg_8], eax
0x18007249e  lea     rsi, [rbx+0B2Ch]
0x1800724a5  mov     [rsi], eax
0x1800724a7  mov     dword ptr [rbp+arg_10], r14d
0x1800724ab  mov     [rbp+arg_18], r14d
0x1800724af  lea     rax, [rbp+arg_8]
0x1800724b3  mov     [rsp+58h+var_38], rax
0x1800724b8  lea     r9, [rbp+arg_10]
0x1800724bc  mov     r8, rsi
0x1800724bf  lea     rdx, [rbp+arg_18]
0x1800724c3  lea     rcx, aQ890746Sleepmi; "Q890746_SleepMilliseconds"
0x1800724ca  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x1800724d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724d7  cmp     rcx, rdi
0x1800724da  jz      short loc_180072501
0x1800724dc  test    [rcx+15Ch], r14b
0x1800724e3  jz      short loc_180072501
0x1800724e5  mov     edx, 0Ch
0x1800724ea  mov     r9d, [rsi]
0x1800724ed  lea     r8, WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids
0x1800724f4  mov     rcx, [rcx+150h]
0x1800724fb  call    WPP_SF_d
0x180072500  nop
0x180072501  mov     rax, rbx
0x180072504  add     rsp, 58h
0x180072508  pop     r15
0x18007250a  pop     r14
0x18007250c  pop     rdi
0x18007250d  pop     rsi
0x18007250e  pop     rbx
0x18007250f  pop     rbp
0x180072510  retn
```
