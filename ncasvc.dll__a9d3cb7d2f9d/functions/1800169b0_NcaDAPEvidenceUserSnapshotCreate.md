# NcaDAPEvidenceUserSnapshotCreate

- ea: `0x1800169b0`
- end: `0x180016c01`
- name: `NcaDAPEvidenceUserSnapshotCreate`
- size: `593`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180017bc8`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18000b51c`
- `0x180015e04`
- `0x180015e80`
- `0x1800169b0`
- `0x180018ffc`
- `0x18001abd4`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016bb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ad9`

## pseudocode

```c
__int64 __fastcall NcaDAPEvidenceUserSnapshotCreate(PVOID pv)
{
  unsigned __int64 v1; // rbx
  void *v2; // rax
  __int64 v3; // rdi
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // eax
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  _OWORD *v12; // rdi
  __int128 v13; // xmm1

  v1 = (unsigned int)pv;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_618387925699392817eae358b6323a44_Traceguids);
  v2 = NcaAlloc(0x290u);
  v3 = (__int64)v2;
  if ( !v2 )
  {
    v4 = 14;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v6 = 22;
    v7 = 14;
    goto LABEL_15;
  }
  memset_0(v2, 0, 0x290u);
  *(_DWORD *)(v3 + 612) = v1;
  *(_QWORD *)(v3 + 616) = 1;
  *(_DWORD *)(v3 + 632) = 4;
  *(_DWORD *)(v3 + 636) = 12;
  if ( (int)NcaCriticalSectionCreate((LPCRITICAL_SECTION)(v3 + 16)) < 0
    || (int)NcaCriticalSectionCreate((LPCRITICAL_SECTION)(v3 + 64)) < 0 )
  {
    v4 = 14;
LABEL_16:
    NcaDAPEvidenceUserSnapshotDestroy((struct NCA_DAP_USER_EVSNPSHT_ *)v3);
    goto LABEL_22;
  }
  v8 = NcaTriggerRegisterWait((PTP_WAIT_CALLBACK)NcaDAPProcessRequest, (PVOID)v1);
  v4 = v8;
  if ( v8 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v6 = 23;
    v7 = v8;
LABEL_15:
    WPP_SF_d(v5[2], v6, WPP_618387925699392817eae358b6323a44_Traceguids, v7);
    goto LABEL_16;
  }
  EnterCriticalSection(&gNcaDapEvSnpshot);
  NcaDAPEvidenceUserSnapshotAddRef((struct NCA_DAP_USER_EVSNPSHT_ *)v3);
  v9 = (__int64 *)qword_180029530;
  if ( *(struct NCA_DAP_USER_EVSNPSHT_ ***)qword_180029530 != &qword_180029528 )
    __fastfail(3u);
  *(_QWORD *)v3 = &qword_180029528;
  v10 = 3;
  *(_QWORD *)(v3 + 8) = v9;
  *v9 = v3;
  v11 = qword_180029330;
  qword_180029530 = v3;
  v12 = (_OWORD *)(v3 + 112);
  do
  {
    *v12 = *(_OWORD *)v11;
    v12[1] = *((_OWORD *)v11 + 1);
    v12[2] = *((_OWORD *)v11 + 2);
    v12[3] = *((_OWORD *)v11 + 3);
    v12[4] = *((_OWORD *)v11 + 4);
    v12[5] = *((_OWORD *)v11 + 5);
    v12[6] = *((_OWORD *)v11 + 6);
    v13 = *((_OWORD *)v11 + 7);
    v11 += 16;
    v12[7] = v13;
    v12 += 8;
    --v10;
  }
  while ( v10 );
  *v12 = *(_OWORD *)v11;
  v12[1] = *((_OWORD *)v11 + 1);
  v12[2] = *((_OWORD *)v11 + 2);
  v12[3] = *((_OWORD *)v11 + 3);
  v12[4] = *((_OWORD *)v11 + 4);
  v12[5] = *((_OWORD *)v11 + 5);
  v12[6] = *((_OWORD *)v11 + 6);
  *((_DWORD *)v12 + 28) = *((_DWORD *)v11 + 28);
  LeaveCriticalSection(&gNcaDapEvSnpshot);
LABEL_22:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_618387925699392817eae358b6323a44_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800169b0  mov     [rsp+arg_0], rbx
0x1800169b5  mov     [rsp+arg_8], rsi
0x1800169ba  push    rdi
0x1800169bb  sub     rsp, 20h
0x1800169bf  mov     ebx, ecx
0x1800169c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169c8  lea     rsi, WPP_GLOBAL_Control
0x1800169cf  cmp     rcx, rsi
0x1800169d2  jz      short loc_1800169EF
0x1800169d4  test    byte ptr [rcx+1Ch], 8
0x1800169d8  jz      short loc_1800169EF
0x1800169da  mov     rcx, [rcx+10h]
0x1800169de  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x1800169e5  mov     edx, 15h
0x1800169ea  call    WPP_SF_
0x1800169ef  mov     ecx, 290h
0x1800169f4  call    NcaAlloc
0x1800169f9  mov     rdi, rax
0x1800169fc  test    rax, rax
0x1800169ff  jnz     short loc_180016A29
0x180016a01  lea     ebx, [rax+0Eh]
0x180016a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a0b  cmp     rcx, rsi
0x180016a0e  jz      loc_180016AC5
0x180016a14  test    byte ptr [rcx+1Ch], 1
0x180016a18  jz      loc_180016AC5
0x180016a1e  lea     edx, [rax+16h]
0x180016a21  mov     r9d, ebx
0x180016a24  jmp     loc_180016AB5
0x180016a29  xor     edx, edx; Val
0x180016a2b  mov     r8d, 290h; Size
0x180016a31  mov     rcx, rdi; void *
0x180016a34  call    memset_0
0x180016a39  lea     rcx, [rdi+10h]; lpCriticalSection
0x180016a3d  mov     [rdi+264h], ebx
0x180016a43  mov     qword ptr [rdi+268h], 1
0x180016a4e  mov     dword ptr [rdi+278h], 4
0x180016a58  mov     dword ptr [rdi+27Ch], 0Ch
0x180016a62  call    NcaCriticalSectionCreate
0x180016a67  test    eax, eax
0x180016a69  jns     short loc_180016A72
0x180016a6b  mov     ebx, 0Eh
0x180016a70  jmp     short loc_180016AC5
0x180016a72  lea     rcx, [rdi+40h]; lpCriticalSection
0x180016a76  call    NcaCriticalSectionCreate
0x180016a7b  test    eax, eax
0x180016a7d  js      short loc_180016A6B
0x180016a7f  lea     r8, [rdi+270h]
0x180016a86  mov     rdx, rbx; pv
0x180016a89  lea     rcx, ?NcaDAPProcessRequest@@YAXPEAX000@Z; pfnwa
0x180016a90  call    NcaTriggerRegisterWait
0x180016a95  mov     ebx, eax
0x180016a97  test    eax, eax
0x180016a99  jz      short loc_180016AD2
0x180016a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016aa2  cmp     rcx, rsi
0x180016aa5  jz      short loc_180016AC5
0x180016aa7  test    byte ptr [rcx+1Ch], 1
0x180016aab  jz      short loc_180016AC5
0x180016aad  mov     edx, 17h
0x180016ab2  mov     r9d, eax
0x180016ab5  mov     rcx, [rcx+10h]
0x180016ab9  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180016ac0  call    WPP_SF_d
0x180016ac5  mov     rcx, rdi; lpMem
0x180016ac8  call    ?NcaDAPEvidenceUserSnapshotDestroy@@YAXPEAUNCA_DAP_USER_EVSNPSHT_@@@Z; NcaDAPEvidenceUserSnapshotDestroy(NCA_DAP_USER_EVSNPSHT_ *)
0x180016acd  jmp     loc_180016BC4
0x180016ad2  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180016ad9  call    cs:__imp_EnterCriticalSection
0x180016ae0  nop     dword ptr [rax+rax+00h]
0x180016ae5  mov     rcx, rdi; struct NCA_DAP_USER_EVSNPSHT_ *
0x180016ae8  call    ?NcaDAPEvidenceUserSnapshotAddRef@@YAXPEAUNCA_DAP_USER_EVSNPSHT_@@@Z; NcaDAPEvidenceUserSnapshotAddRef(NCA_DAP_USER_EVSNPSHT_ *)
0x180016aed  mov     rax, cs:qword_180029530
0x180016af4  lea     rcx, qword_180029528
0x180016afb  cmp     [rax], rcx
0x180016afe  jz      short loc_180016B07
0x180016b00  mov     ecx, 3
0x180016b05  int     29h; Win8: RtlFailFast(ecx)
0x180016b07  mov     [rdi], rcx
0x180016b0a  mov     ecx, 3
0x180016b0f  mov     [rdi+8], rax
0x180016b13  mov     [rax], rdi
0x180016b16  lea     rax, qword_180029330
0x180016b1d  mov     cs:qword_180029530, rdi
0x180016b24  add     rdi, 70h ; 'p'
0x180016b28  lea     edx, [rcx+7Dh]
0x180016b2b  movups  xmm0, xmmword ptr [rax]
0x180016b2e  movups  xmmword ptr [rdi], xmm0
0x180016b31  movups  xmm1, xmmword ptr [rax+10h]
0x180016b35  movups  xmmword ptr [rdi+10h], xmm1
0x180016b39  movups  xmm0, xmmword ptr [rax+20h]
0x180016b3d  movups  xmmword ptr [rdi+20h], xmm0
0x180016b41  movups  xmm1, xmmword ptr [rax+30h]
0x180016b45  movups  xmmword ptr [rdi+30h], xmm1
0x180016b49  movups  xmm0, xmmword ptr [rax+40h]
0x180016b4d  movups  xmmword ptr [rdi+40h], xmm0
0x180016b51  movups  xmm1, xmmword ptr [rax+50h]
0x180016b55  movups  xmmword ptr [rdi+50h], xmm1
0x180016b59  movups  xmm0, xmmword ptr [rax+60h]
0x180016b5d  movups  xmmword ptr [rdi+60h], xmm0
0x180016b61  movups  xmm1, xmmword ptr [rax+70h]
0x180016b65  add     rax, rdx
0x180016b68  movups  xmmword ptr [rdi+70h], xmm1
0x180016b6c  add     rdi, rdx
0x180016b6f  sub     rcx, 1
0x180016b73  jnz     short loc_180016B2B
0x180016b75  movups  xmm0, xmmword ptr [rax]
0x180016b78  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180016b7f  movups  xmmword ptr [rdi], xmm0
0x180016b82  movups  xmm1, xmmword ptr [rax+10h]
0x180016b86  movups  xmmword ptr [rdi+10h], xmm1
0x180016b8a  movups  xmm0, xmmword ptr [rax+20h]
0x180016b8e  movups  xmmword ptr [rdi+20h], xmm0
0x180016b92  movups  xmm1, xmmword ptr [rax+30h]
0x180016b96  movups  xmmword ptr [rdi+30h], xmm1
0x180016b9a  movups  xmm0, xmmword ptr [rax+40h]
0x180016b9e  movups  xmmword ptr [rdi+40h], xmm0
0x180016ba2  movups  xmm1, xmmword ptr [rax+50h]
0x180016ba6  movups  xmmword ptr [rdi+50h], xmm1
0x180016baa  movups  xmm0, xmmword ptr [rax+60h]
0x180016bae  movups  xmmword ptr [rdi+60h], xmm0
0x180016bb2  mov     eax, [rax+70h]
0x180016bb5  mov     [rdi+70h], eax
0x180016bb8  call    cs:__imp_LeaveCriticalSection
0x180016bbf  nop     dword ptr [rax+rax+00h]
0x180016bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bcb  cmp     rcx, rsi
0x180016bce  jz      short loc_180016BEE
0x180016bd0  test    byte ptr [rcx+1Ch], 8
0x180016bd4  jz      short loc_180016BEE
0x180016bd6  mov     rcx, [rcx+10h]
0x180016bda  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180016be1  mov     edx, 18h
0x180016be6  mov     r9d, ebx
0x180016be9  call    WPP_SF_d
0x180016bee  mov     rsi, [rsp+28h+arg_8]
0x180016bf3  mov     eax, ebx
0x180016bf5  mov     rbx, [rsp+28h+arg_0]
0x180016bfa  add     rsp, 20h
0x180016bfe  pop     rdi
0x180016bff  retn
```
