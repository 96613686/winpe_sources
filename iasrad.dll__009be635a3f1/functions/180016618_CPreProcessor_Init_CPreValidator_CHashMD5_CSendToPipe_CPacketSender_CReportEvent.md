# CPreProcessor::Init(CPreValidator *,CHashMD5 *,CSendToPipe *,CPacketSender *,CReportEvent *)

- ea: `0x180016618`
- end: `0x18001683e`
- name: `?Init@CPreProcessor@@QEAAHPEAVCPreValidator@@PEAVCHashMD5@@PEAVCSendToPipe@@PEAVCPacketSender@@PEAVCReportEvent@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(CPreProcessor *__hidden this, struct CPreValidator *, struct CHashMD5 *, struct CSendToPipe *, struct CPacketSender *, struct CReportEvent *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b560`

## callees

- `0x1800094e4`
- `0x18000e4e0`
- `0x180016618`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x18001669e`: `Unable to crate Access-Processing object in Pre-Processor initialization`

## pseudocode

```c
__int64 __fastcall CPreProcessor::Init(
        CPreProcessor *this,
        struct CPreValidator *a2,
        struct CHashMD5 *a3,
        struct CSendToPipe *a4,
        struct CPacketSender *a5)
{
  _QWORD *v9; // rax
  const struct std::nothrow_t *v10; // rdx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  _QWORD *v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  unsigned int v16; // esi
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx

  *((_QWORD *)this + 4) = a4;
  v9 = operator new[](0x20u, a2);
  if ( v9 )
  {
    v9[1] = 0;
    *v9 = &CProcAccess::`vftable';
    v9[2] = 0;
    v9[3] = 0;
  }
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_23;
    }
    WppDbgPrint("Unable to crate Access-Processing object in Pre-Processor initialization");
    v11 = 10;
    goto LABEL_22;
  }
  v9[1] = a2;
  v9[2] = a3;
  v9[3] = a4;
  v12 = operator new[](0x20u, v10);
  if ( v12 )
  {
    v12[1] = 0;
    *v12 = &CProcAccess::`vftable';
    v12[2] = 0;
    v12[3] = 0;
  }
  *((_QWORD *)this + 2) = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_23;
    }
    WppDbgPrint("Unable to crate Accounting-Processing object in Pre-Processor initialization");
    v11 = 11;
    goto LABEL_22;
  }
  v12[2] = a5;
  v12[1] = a2;
  v12[3] = a4;
  v14 = operator new[](0x18u, v13);
  if ( v14 )
  {
    v14[1] = 0;
    *v14 = &CProcAccess::`vftable';
    v14[2] = 0;
  }
  *((_QWORD *)this + 3) = v14;
  if ( v14 )
  {
    v14[1] = a2;
    v16 = 1;
    v14[2] = a5;
    return v16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to crate Response-Processing object in Pre-Processor initialization");
    v11 = 12;
LABEL_22:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_42f104ab1e463fe3d359f244f6b57987_Traceguids, "NPSRAD");
  }
LABEL_23:
  v15 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  v16 = 0;
  if ( v15 )
    (**v15)(v15, 1);
  v17 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v17 )
    (**v17)(v17, 1);
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  if ( v18 )
    (**v18)(v18, 1);
  return v16;
}

```

## disassembly

```asm
0x180016618  push    rbx
0x18001661a  push    rbp
0x18001661b  push    rsi
0x18001661c  push    rdi
0x18001661d  sub     rsp, 28h
0x180016621  mov     rdi, rcx
0x180016624  mov     [rcx+20h], r9
0x180016628  mov     ecx, 20h ; ' '; Size
0x18001662d  mov     rbp, r9
0x180016630  mov     rbx, r8
0x180016633  mov     rsi, rdx
0x180016636  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001663b  mov     [rsp+48h+arg_0], rax
0x180016640  test    rax, rax
0x180016643  jz      short loc_180016667
0x180016645  lea     rcx, ??_7CProcAccess@@6B@; const CProcAccess::`vftable'
0x18001664c  mov     qword ptr [rax+8], 0
0x180016654  mov     [rax], rcx
0x180016657  mov     qword ptr [rax+10h], 0
0x18001665f  mov     qword ptr [rax+18h], 0
0x180016667  mov     [rdi+8], rax
0x18001666b  test    rax, rax
0x18001666e  jnz     short loc_1800166B4
0x180016670  mov     rcx, cs:WPP_GLOBAL_Control
0x180016677  lea     rax, WPP_GLOBAL_Control
0x18001667e  cmp     rcx, rax
0x180016681  jz      loc_1800167DD
0x180016687  cmp     byte ptr [rcx+19h], 2
0x18001668b  jb      loc_1800167DD
0x180016691  test    dword ptr [rcx+1Ch], 100h
0x180016698  jz      loc_1800167DD
0x18001669e  lea     rcx, aUnableToCrateA; "Unable to crate Access-Processing objec"...
0x1800166a5  call    WppDbgPrint
0x1800166aa  mov     edx, 0Ah
0x1800166af  jmp     loc_1800167BF
0x1800166b4  mov     ecx, 20h ; ' '; Size
0x1800166b9  mov     [rax+8], rsi
0x1800166bd  mov     [rax+10h], rbx
0x1800166c1  mov     [rax+18h], rbp
0x1800166c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800166ca  mov     [rsp+48h+arg_0], rax
0x1800166cf  test    rax, rax
0x1800166d2  jz      short loc_1800166F6
0x1800166d4  lea     rcx, ??_7CProcAccess@@6B@; const CProcAccess::`vftable'
0x1800166db  mov     qword ptr [rax+8], 0
0x1800166e3  mov     [rax], rcx
0x1800166e6  mov     qword ptr [rax+10h], 0
0x1800166ee  mov     qword ptr [rax+18h], 0
0x1800166f6  mov     [rdi+10h], rax
0x1800166fa  test    rax, rax
0x1800166fd  jnz     short loc_180016740
0x1800166ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016706  lea     rax, WPP_GLOBAL_Control
0x18001670d  cmp     rcx, rax
0x180016710  jz      loc_1800167DD
0x180016716  cmp     byte ptr [rcx+19h], 2
0x18001671a  jb      loc_1800167DD
0x180016720  test    dword ptr [rcx+1Ch], 100h
0x180016727  jz      loc_1800167DD
0x18001672d  lea     rcx, aUnableToCrateA_0; "Unable to crate Accounting-Processing o"...
0x180016734  call    WppDbgPrint
0x180016739  mov     edx, 0Bh
0x18001673e  jmp     short loc_1800167BF
0x180016740  mov     rbx, [rsp+48h+arg_20]
0x180016745  mov     ecx, 18h; Size
0x18001674a  mov     [rax+10h], rbx
0x18001674e  mov     [rax+8], rsi
0x180016752  mov     [rax+18h], rbp
0x180016756  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001675b  mov     [rsp+48h+arg_0], rax
0x180016760  test    rax, rax
0x180016763  jz      short loc_18001677F
0x180016765  lea     rcx, ??_7CProcAccess@@6B@; const CProcAccess::`vftable'
0x18001676c  mov     qword ptr [rax+8], 0
0x180016774  mov     [rax], rcx
0x180016777  mov     qword ptr [rax+10h], 0
0x18001677f  mov     [rdi+18h], rax
0x180016783  test    rax, rax
0x180016786  jnz     loc_180016826
0x18001678c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016793  lea     rax, WPP_GLOBAL_Control
0x18001679a  cmp     rcx, rax
0x18001679d  jz      short loc_1800167DD
0x18001679f  cmp     byte ptr [rcx+19h], 2
0x1800167a3  jb      short loc_1800167DD
0x1800167a5  test    dword ptr [rcx+1Ch], 100h
0x1800167ac  jz      short loc_1800167DD
0x1800167ae  lea     rcx, aUnableToCrateR; "Unable to crate Response-Processing obj"...
0x1800167b5  call    WppDbgPrint
0x1800167ba  mov     edx, 0Ch
0x1800167bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167c6  lea     r9, aNpsrad; "NPSRAD"
0x1800167cd  lea     r8, WPP_42f104ab1e463fe3d359f244f6b57987_Traceguids
0x1800167d4  mov     rcx, [rcx+10h]
0x1800167d8  call    WPP_SF_s
0x1800167dd  mov     rcx, [rdi+18h]
0x1800167e1  xor     esi, esi
0x1800167e3  lea     ebx, [rsi+1]
0x1800167e6  test    rcx, rcx
0x1800167e9  jz      short loc_1800167F8
0x1800167eb  mov     rax, [rcx]
0x1800167ee  mov     edx, ebx
0x1800167f0  mov     rax, [rax]
0x1800167f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f8  mov     rcx, [rdi+10h]
0x1800167fc  test    rcx, rcx
0x1800167ff  jz      short loc_18001680E
0x180016801  mov     rax, [rcx]
0x180016804  mov     edx, ebx
0x180016806  mov     rax, [rax]
0x180016809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001680e  mov     rcx, [rdi+8]
0x180016812  test    rcx, rcx
0x180016815  jz      short loc_180016833
0x180016817  mov     rax, [rcx]
0x18001681a  mov     edx, ebx
0x18001681c  mov     rax, [rax]
0x18001681f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016824  jmp     short loc_180016833
0x180016826  mov     [rax+8], rsi
0x18001682a  mov     esi, 1
0x18001682f  mov     [rax+10h], rbx
0x180016833  mov     eax, esi
0x180016835  add     rsp, 28h
0x180016839  pop     rdi
0x18001683a  pop     rsi
0x18001683b  pop     rbp
0x18001683c  pop     rbx
0x18001683d  retn
```
