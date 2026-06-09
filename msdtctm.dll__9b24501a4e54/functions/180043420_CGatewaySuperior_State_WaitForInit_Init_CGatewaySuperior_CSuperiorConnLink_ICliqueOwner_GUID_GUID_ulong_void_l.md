# CGatewaySuperior_State_WaitForInit::Init(CGatewaySuperior *,CSuperiorConnLink *,ICliqueOwner *,_GUID *,_GUID *,ulong,void *,long,_GUID *,void *,long,_Trun_TxRestartInfo_Display_ *,_GUID *)

- ea: `0x180043420`
- end: `0x180043702`
- name: `?Init@CGatewaySuperior_State_WaitForInit@@UEAA?AW4_GatewaySuperiorJoin_Result@@PEAVCGatewaySuperior@@PEAVCSuperiorConnLink@@PEAUICliqueOwner@@PEAU_GUID@@3KPEAXJ34JPEAU_Trun_TxRestartInfo_Display_@@3@Z`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180043420`
- `0x180044a00`
- `0x18006e904`
- `0x18006e928`
- `0x18006ed68`
- `0x180073720`
- `0x180085624`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004350e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004350e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800434ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800434ba`

## string_xrefs

- `0x1800434ca`: `com\complus\dtc\dtc\tm\src\tmgatewaysuperior.cpp`
- `0x180043669`: `com\complus\dtc\dtc\tm\src\tmgatewaysuperior.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGatewaySuperior_State_WaitForInit::Init(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        _OWORD *a6,
        __int64 a7,
        _DWORD *a8,
        int a9,
        struct _GUID *a10,
        __int64 a11,
        int a12,
        __int64 a13,
        struct _GUID *a14)
{
  __int64 v17; // rax
  struct _GUID *v18; // rdi
  CTmTrace *v19; // rcx
  struct _GUID *v20; // rbp
  CTx *v22; // rax
  CTx *v23; // rdi
  const char *v24; // r8
  int v25; // eax
  int inited; // edi
  CTmTrace *v27; // rcx
  void *v28; // r9

  *(_OWORD *)(a2 + 144) = *a5;
  *(_OWORD *)(a2 + 160) = *a6;
  *(_QWORD *)(a2 + 232) = a11;
  *(_DWORD *)(a2 + 240) = a12;
  *(_QWORD *)(a2 + 248) = a13;
  *(_QWORD *)(a2 + 88) = a4;
  v17 = *(_QWORD *)&a10->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a10->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v17 = *(_QWORD *)a10->Data4 - *(_QWORD *)GUID_NULL.Data4;
  v18 = (struct _GUID *)(a2 + 272);
  if ( v17 )
  {
    *v18 = *a10;
  }
  else if ( CoCreateGuid((GUID *)(a2 + 272)) < 0 )
  {
    CTmTrace::InternalError(v19, "com\\complus\\dtc\\dtc\\tm\\src\\tmgatewaysuperior.cpp", 3168);
  }
  v20 = v18;
  if ( a9 && a9 != 52 )
    return 5;
  v22 = (CTx *)HeapAlloc(g_CTx_MemAlloc, 0, 0x5D8u);
  if ( v22 )
    v23 = CTx::CTx(v22, v18);
  else
    v23 = 0;
  if ( !v23 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 88) + 16LL))(*(_QWORD *)(a2 + 88));
    *(_QWORD *)(a2 + 88) = 0;
    return 2;
  }
  if ( a9 == 52 )
  {
    *(_DWORD *)(a2 + 176) = *a8;
    *(_DWORD *)(a2 + 224) = a8[12];
    v24 = (const char *)(a8 + 2);
    v25 = a8[1];
  }
  else
  {
    *(_DWORD *)(a2 + 176) = 0x100000;
    *(_DWORD *)(a2 + 224) = 0;
    v24 = "GatewaySupTx";
    v25 = 0;
  }
  *(_DWORD *)(a2 + 180) = v25;
  TracedStringCchCopyA((char *)(a2 + 184), 0x28u, v24);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 88) + 8LL))(*(_QWORD *)(a2 + 88));
  inited = CTx::InitGatewaySuperior(v23, *(_QWORD *)(a2 + 88), *(unsigned int *)(a2 + 180), *(unsigned int *)(a2 + 176));
  if ( inited == 3 )
  {
    (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)(a2 + 104) + 8LL))(a2 + 104, a3 + 8);
    *(_QWORD *)(a3 + 56) = (a2 + 8) & -(__int64)(a2 != 0);
    (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)a1 + 264LL))(a1, a2);
    *a14 = *v20;
    return 1;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 88) + 16LL))(*(_QWORD *)(a2 + 88));
    *(_QWORD *)(a2 + 88) = 0;
    switch ( inited )
    {
      case 1:
        DtcWriteToEventLoggerExUnFilteredA(
          1u,
          2u,
          0xC0001046,
          v28,
          0,
          a2 + 184,
          0,
          (void *)((a2 + 80) & ((unsigned __int128)-(__int128)a2 >> 64)),
          a2 + 96);
        return 4;
      case 2:
        return 2;
      case 4:
        return 3;
      default:
        CTmTrace::InvalidValue(v27, "com\\complus\\dtc\\dtc\\tm\\src\\tmgatewaysuperior.cpp", 3241, inited);
    }
  }
}

```

## disassembly

```asm
0x180043420  push    rbx
0x180043422  push    rbp
0x180043423  push    rdi
0x180043424  push    r12
0x180043426  push    r14
0x180043428  push    r15
0x18004342a  sub     rsp, 68h
0x18004342e  mov     r15, r8
0x180043431  mov     rbx, rdx
0x180043434  mov     r12, rcx
0x180043437  mov     rax, [rsp+98h+arg_20]
0x18004343f  movups  xmm0, xmmword ptr [rax]
0x180043442  movdqu  xmmword ptr [rdx+90h], xmm0
0x18004344a  mov     rax, [rsp+98h+arg_28]
0x180043452  movups  xmm1, xmmword ptr [rax]
0x180043455  movdqu  xmmword ptr [rdx+0A0h], xmm1
0x18004345d  mov     rax, [rsp+98h+arg_50]
0x180043465  mov     [rdx+0E8h], rax
0x18004346c  mov     eax, [rsp+98h+arg_58]
0x180043473  mov     [rdx+0F0h], eax
0x180043479  mov     rax, [rsp+98h+arg_60]
0x180043481  mov     [rdx+0F8h], rax
0x180043488  mov     [rdx+58h], r9
0x18004348c  mov     rcx, [rsp+98h+arg_48]
0x180043494  mov     rax, [rcx]
0x180043497  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18004349e  jnz     short loc_1800434AB
0x1800434a0  mov     rax, [rcx+8]
0x1800434a4  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800434ab  lea     rdi, [rdx+110h]
0x1800434b2  test    rax, rax
0x1800434b5  jnz     short loc_1800434D7
0x1800434b7  mov     rcx, rdi; pguid
0x1800434ba  call    cs:__imp_CoCreateGuid
0x1800434c0  test    eax, eax
0x1800434c2  jns     short loc_1800434DE
0x1800434c4  mov     r8d, 0C60h; int
0x1800434ca  lea     rdx, aComComplusDtcD_98; "com\\complus\\dtc\\dtc\\tm\\src\\tmgate"...
0x1800434d1  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x1800434d7  movups  xmm0, xmmword ptr [rcx]
0x1800434da  movdqu  xmmword ptr [rdi], xmm0
0x1800434de  mov     rbp, rdi
0x1800434e1  cmp     [rsp+98h+arg_40], 0
0x1800434e9  jz      short loc_1800434FF
0x1800434eb  cmp     [rsp+98h+arg_40], 34h ; '4'
0x1800434f3  jz      short loc_1800434FF
0x1800434f5  mov     eax, 5
0x1800434fa  jmp     loc_1800436F4
0x1800434ff  xor     edx, edx; dwFlags
0x180043501  mov     r8d, 5D8h; dwBytes
0x180043507  mov     rcx, cs:?g_CTx_MemAlloc@@3VMemMgrSimple@@A; hHeap
0x18004350e  call    cs:__imp_HeapAlloc
0x180043514  mov     [rsp+98h+arg_20], rax
0x18004351c  test    rax, rax
0x18004351f  jz      short loc_180043531
0x180043521  mov     rdx, rdi; struct _GUID *
0x180043524  mov     rcx, rax; this
0x180043527  call    ??0CTx@@QEAA@PEAU_GUID@@@Z; CTx::CTx(_GUID *)
0x18004352c  mov     rdi, rax
0x18004352f  jmp     short loc_180043533
0x180043531  xor     edi, edi
0x180043533  test    rdi, rdi
0x180043536  jnz     short loc_180043556
0x180043538  mov     rcx, [rbx+58h]
0x18004353c  mov     rax, [rcx]
0x18004353f  mov     rax, [rax+10h]
0x180043543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043548  mov     [rbx+58h], rdi
0x18004354c  mov     eax, 2
0x180043551  jmp     loc_1800436F4
0x180043556  lea     r14, [rbx+0B8h]
0x18004355d  cmp     [rsp+98h+arg_40], 34h ; '4'
0x180043565  jnz     short loc_180043589
0x180043567  mov     rcx, [rsp+98h+arg_38]
0x18004356f  mov     eax, [rcx]
0x180043571  mov     [rbx+0B0h], eax
0x180043577  mov     eax, [rcx+30h]
0x18004357a  mov     [rbx+0E0h], eax
0x180043580  lea     r8, [rcx+8]
0x180043584  mov     eax, [rcx+4]
0x180043587  jmp     short loc_1800435A6
0x180043589  mov     dword ptr [rbx+0B0h], 100000h
0x180043593  mov     dword ptr [rbx+0E0h], 0
0x18004359d  lea     r8, aGatewaysuptx; "GatewaySupTx"
0x1800435a4  xor     eax, eax
0x1800435a6  mov     [rbx+0B4h], eax
0x1800435ac  mov     edx, 28h ; '('; unsigned __int64
0x1800435b1  mov     rcx, r14; char *
0x1800435b4  call    ?TracedStringCchCopyA@@YAXPEAD_KPEBD@Z; TracedStringCchCopyA(char *,unsigned __int64,char const *)
0x1800435b9  mov     rcx, [rbx+58h]
0x1800435bd  mov     rax, [rcx]
0x1800435c0  mov     rax, [rax+8]
0x1800435c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435c9  mov     rax, rbx
0x1800435cc  lea     rcx, [rbx+10h]
0x1800435d0  neg     rax
0x1800435d3  sbb     r10, r10
0x1800435d6  and     r10, rcx
0x1800435d9  lea     r8, [rbx+120h]
0x1800435e0  lea     r9, [rbx+60h]
0x1800435e4  mov     rax, rbx
0x1800435e7  lea     rcx, [rbx+50h]
0x1800435eb  neg     rax
0x1800435ee  sbb     rdx, rdx
0x1800435f1  and     rdx, rcx
0x1800435f4  mov     [rsp+98h+var_48], r10
0x1800435f9  mov     [rsp+98h+var_50], r8
0x1800435fe  mov     qword ptr [rsp+98h+var_58], r9; int
0x180043603  mov     [rsp+98h+var_60], rdx; void *
0x180043608  mov     [rsp+98h+var_68], rbx
0x18004360d  mov     qword ptr [rsp+98h+var_70], r14; unsigned int
0x180043612  mov     r9d, [rbx+0B0h]
0x180043619  mov     r8d, [rbx+0B4h]
0x180043620  mov     rdx, [rbx+58h]
0x180043624  mov     rcx, rdi
0x180043627  call    ?InitGatewaySuperior@CTx@@QEAA?AW4_Init_Tx_GatewaySuperior@@PEAUICliqueOwner@@KJKPEADPEAVITxToSuperior@@PEAVITxToGatewaySuperior@@PEAPEAVISuperiorToTx@@PEAPEAVIGatewaySuperiorToTx@@PEAVCTxStatusNotify@@@Z; CTx::InitGatewaySuperior(ICliqueOwner *,ulong,long,ulong,char *,ITxToSuperior *,ITxToGatewaySuperior *,ISuperiorToTx * *,IGatewaySuperiorToTx * *,CTxStatusNotify *)
0x18004362c  mov     edi, eax
0x18004362e  cmp     eax, 3
0x180043631  jz      short loc_1800436A1
0x180043633  mov     rcx, [rbx+58h]
0x180043637  mov     rdx, [rcx]
0x18004363a  mov     rax, [rdx+10h]
0x18004363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043643  mov     qword ptr [rbx+58h], 0
0x18004364b  mov     edx, edi
0x18004364d  sub     edx, 1
0x180043650  jz      short loc_18004367D
0x180043652  sub     edx, 1
0x180043655  jz      loc_18004354C
0x18004365b  cmp     edx, 2
0x18004365e  jz      short loc_180043676
0x180043660  mov     r9d, edi; int
0x180043663  mov     r8d, 0CA9h; int
0x180043669  lea     rdx, aComComplusDtcD_98; "com\\complus\\dtc\\dtc\\tm\\src\\tmgate"...
0x180043670  call    ?InvalidValue@CTmTrace@@QEAAXPEBDHJ@Z; CTmTrace::InvalidValue(char const *,int,long)
0x180043676  mov     eax, 3
0x18004367b  jmp     short loc_1800436F4
0x18004367d  xor     eax, eax
0x18004367f  lea     edx, [rax+2]; unsigned __int16
0x180043682  lea     ecx, [rax+1]; unsigned __int16
0x180043685  mov     [rsp+98h+var_68], rax; char **
0x18004368a  mov     [rsp+98h+var_78], ax; unsigned __int16
0x18004368f  mov     r8d, 0C0001046h; unsigned int
0x180043695  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExUnFilteredA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x18004369a  mov     eax, 4
0x18004369f  jmp     short loc_1800436F4
0x1800436a1  lea     rcx, [rbx+68h]
0x1800436a5  mov     rax, [rcx]
0x1800436a8  lea     rdx, [r15+8]
0x1800436ac  mov     rax, [rax+8]
0x1800436b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b5  mov     rax, rbx
0x1800436b8  lea     rdx, [rbx+8]
0x1800436bc  neg     rax
0x1800436bf  sbb     rcx, rcx
0x1800436c2  and     rcx, rdx
0x1800436c5  mov     [r15+38h], rcx
0x1800436c9  mov     rax, [r12]
0x1800436cd  mov     rdx, rbx
0x1800436d0  mov     rcx, r12
0x1800436d3  mov     rax, [rax+108h]
0x1800436da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436df  movups  xmm0, xmmword ptr [rbp+0]
0x1800436e3  mov     rax, [rsp+98h+arg_68]
0x1800436eb  movdqu  xmmword ptr [rax], xmm0
0x1800436ef  mov     eax, 1
0x1800436f4  add     rsp, 68h
0x1800436f8  pop     r15
0x1800436fa  pop     r14
0x1800436fc  pop     r12
0x1800436fe  pop     rdi
0x1800436ff  pop     rbp
0x180043700  pop     rbx
0x180043701  retn
```
