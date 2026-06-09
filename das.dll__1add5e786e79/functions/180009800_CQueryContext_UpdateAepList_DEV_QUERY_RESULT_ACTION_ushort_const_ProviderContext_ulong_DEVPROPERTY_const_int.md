# CQueryContext::UpdateAepList(_DEV_QUERY_RESULT_ACTION,ushort const *,ProviderContext *,ulong,_DEVPROPERTY * const,int)

- ea: `0x180009800`
- end: `0x180009cf5`
- name: `?UpdateAepList@CQueryContext@@QEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGPEAVProviderContext@@KQEAU_DEVPROPERTY@@H@Z`
- size: `1269`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005924`
- `0x180008ba0`
- `0x180014394`
- `0x18005379c`

## callees

- `0x1800061c0`
- `0x1800095bc`
- `0x180009800`
- `0x180009d50`
- `0x180009d7c`
- `0x18000aad0`
- `0x180016dc0`
- `0x180016f70`
- `0x18001a760`
- `0x180021b14`
- `0x180023f34`
- `0x180053b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009864`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009a77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009a77`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009930`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009930`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQueryContext::UpdateAepList(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v9; // r15
  int v10; // r8d
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  int updated; // r14d
  int v14; // ebx
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  char v18; // r12
  int IsObjectInList; // eax
  signed int LastError; // eax
  struct _AEP_ENTRY **v21; // rdi
  struct _AEP_ENTRY *v22; // rbx
  int v23; // edi
  int v24; // edx
  int v25; // r8d
  int v26; // edx
  int v27; // r8d
  unsigned __int64 i; // rbx
  PVOID v29; // rdx
  const WCHAR *v31; // r8
  __int64 v32; // rcx
  const WCHAR *v33; // rax
  int v34; // eax
  int v35; // edx
  struct _AEP_ENTRY *v36; // rax
  struct _AEP_ENTRY **v37; // rcx
  struct _AEP_ENTRY **v38; // rax
  int v39; // [rsp+28h] [rbp-38h]
  void **v40; // [rsp+40h] [rbp-20h] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-18h]
  unsigned __int64 v42; // [rsp+50h] [rbp-10h]
  __int64 v43; // [rsp+58h] [rbp-8h]
  struct _AEP_ENTRY *v44; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v45; // [rsp+A8h] [rbp+48h]
  __int64 v46; // [rsp+B8h] [rbp+58h]

  v46 = a4;
  v45 = a2;
  Buffer = 0;
  v42 = 0;
  v43 = 0;
  v40 = &DafDynamicArray<_DEVPROPERTY>::`vftable';
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      31,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v39,
      a1);
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 264);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  if ( !a3 )
  {
    v14 = -2147024809;
LABEL_67:
    updated = v14;
    goto LABEL_28;
  }
  v11 = 768;
  v12 = a3;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  updated = -2147024809;
  v14 = -2147024809;
  if ( v11 )
    v14 = 0;
  v15 = 768 - v11;
  if ( !v11 )
    goto LABEL_67;
  v16 = *(_QWORD *)(a1 + 136);
  v17 = *(_DWORD *)(v16 + 20);
  v18 = 1;
  if ( v17 == 1 )
  {
    v31 = *(const WCHAR **)(v16 + 24);
    if ( !v31 )
      goto LABEL_28;
    v32 = 768;
    v33 = v31;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v32;
    }
    while ( v32 );
    if ( !v32 )
      goto LABEL_28;
    updated = 0;
    v34 = CompareStringOrdinal(a3, v15 + 1, v31, 768 - v32 + 1, 1);
    if ( v34 )
    {
      IsObjectInList = v34 == 2;
    }
    else
    {
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      if ( updated < 0 )
        goto LABEL_28;
      IsObjectInList = 0;
    }
  }
  else
  {
    if ( v17 != 2 )
      goto LABEL_18;
    IsObjectInList = DafIsObjectInList(*(LPCWCH *)(v16 + 32), a3);
    updated = v14;
  }
  if ( !IsObjectInList )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v15,
        v10,
        32,
        &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
        (__int64)a3);
    goto LABEL_28;
  }
LABEL_18:
  v21 = (struct _AEP_ENTRY **)(a1 + 304);
  if ( a1 == -304 || (v22 = *v21, *v21 == (struct _AEP_ENTRY *)v21) )
  {
LABEL_43:
    v44 = 0;
  }
  else
  {
    while ( 1 )
    {
      if ( v22 == (struct _AEP_ENTRY *)v21 )
        goto LABEL_43;
      if ( !lstrcmpiW(*((LPCWSTR *)v22 + 2), a3) )
        break;
      v22 = *(struct _AEP_ENTRY **)v22;
    }
    v44 = v22;
    if ( v22 )
    {
      v23 = 0;
      goto LABEL_25;
    }
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v10,
      33,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      (__int64)a3);
  v35 = v46;
  if ( v46 )
    v35 = *(_DWORD *)(v46 + 52);
  updated = CreateAepEntry(a3, v35, &v44);
  if ( updated < 0 )
  {
    v22 = v44;
    goto LABEL_27;
  }
  v38 = *(struct _AEP_ENTRY ***)(a1 + 312);
  if ( *v38 != (struct _AEP_ENTRY *)v21 )
    goto LABEL_72;
  v22 = v44;
  *(_QWORD *)v44 = v21;
  *((_QWORD *)v22 + 1) = v38;
  *v38 = v22;
  *(_QWORD *)(a1 + 312) = v22;
  v23 = 1;
LABEL_25:
  v39 = a7;
  updated = CQueryContext::UpdateAepEntry(a1, a3, v45, a5, a6);
  if ( updated < 0 || (*(_BYTE *)(*(_QWORD *)(a1 + 136) + 40LL) & 1) == 0 )
    goto LABEL_26;
  if ( !*((_DWORD *)v22 + 17) )
  {
    v18 = 3;
    goto LABEL_55;
  }
  if ( v23 )
  {
LABEL_55:
    updated = CQueryContext::MakeResult(a1, v18);
    goto LABEL_26;
  }
  if ( Buffer )
  {
    v18 = 2;
    goto LABEL_55;
  }
LABEL_26:
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 264);
LABEL_27:
  if ( v22 && !*((_DWORD *)v22 + 17) )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v24,
        v25,
        34,
        &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
        (__int64)a3);
    v36 = *(struct _AEP_ENTRY **)v22;
    if ( *(struct _AEP_ENTRY **)(*(_QWORD *)v22 + 8LL) == v22 )
    {
      v37 = (struct _AEP_ENTRY **)*((_QWORD *)v22 + 1);
      if ( *v37 == v22 )
      {
        *v37 = v36;
        *((_QWORD *)v36 + 1) = v37;
        FreeAepEntry(v22);
        goto LABEL_28;
      }
    }
LABEL_72:
    __fastfail(3u);
  }
LABEL_28:
  LeaveCriticalSection(v9);
  for ( i = 0; i < v42; ++i )
    DafDevPropCompKeyFree((char *)Buffer + 32 * i);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v26,
      v27,
      35,
      &WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids,
      v39,
      a1,
      updated);
  v40 = &DafDynamicArray<_DEVPROPERTY>::`vftable';
  v42 = 0;
  v29 = Buffer;
  if ( Buffer )
  {
    FreeTableEntry((struct _RTL_AVL_TABLE *)&v40, Buffer);
    v29 = 0;
    Buffer = 0;
  }
  v40 = &TDynamicArray<unsigned short *>::`vftable';
  v42 = 0;
  if ( v29 )
    TDynamicArray<_DEVPROPERTY>::free(&v40);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180009800  mov     [rsp-38h+arg_10], rbx
0x180009805  mov     [rsp-38h+arg_18], r9
0x18000980a  mov     [rsp-38h+arg_8], edx
0x18000980e  push    rbp
0x18000980f  push    rsi
0x180009810  push    rdi
0x180009811  push    r12
0x180009813  push    r13
0x180009815  push    r14
0x180009817  push    r15
0x180009819  mov     rbp, rsp
0x18000981c  sub     rsp, 60h
0x180009820  mov     rsi, r8
0x180009823  mov     r13, rcx
0x180009826  xor     edi, edi
0x180009828  mov     [rbp+Buffer], rdi
0x18000982c  mov     [rbp+var_10], rdi
0x180009830  mov     [rbp+var_8], rdi
0x180009834  lea     r12, ??_7?$DafDynamicArray@U_DEVPROPERTY@@@@6B@; const DafDynamicArray<_DEVPROPERTY>::`vftable'
0x18000983b  mov     [rbp+var_20], r12
0x18000983f  lea     rax, WPP_RECORDER_INITIALIZED
0x180009846  lea     rcx, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x18000984d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009854  jnz     loc_180009A96
0x18000985a  lea     r15, [r13+108h]
0x180009861  mov     rcx, r15; lpCriticalSection
0x180009864  call    cs:__imp_EnterCriticalSection
0x18000986a  test    rsi, rsi
0x18000986d  jz      loc_180009C1D
0x180009873  mov     r9d, 300h
0x180009879  mov     ecx, r9d
0x18000987c  mov     rax, rsi
0x18000987f  nop
0x180009880  cmp     [rax], di
0x180009883  jz      short loc_18000988F
0x180009885  add     rax, 2
0x180009889  sub     rcx, 1
0x18000988d  jnz     short loc_180009880
0x18000988f  mov     r14d, 80070057h
0x180009895  mov     ebx, r14d
0x180009898  test    rcx, rcx
0x18000989b  cmovnz  ebx, edi
0x18000989e  mov     rdx, r9
0x1800098a1  sub     rdx, rcx
0x1800098a4  test    rcx, rcx
0x1800098a7  cmovz   rdx, rdi
0x1800098ab  jz      loc_180009C22
0x1800098b1  mov     rcx, [r13+88h]
0x1800098b8  mov     eax, [rcx+14h]
0x1800098bb  mov     r12d, 1
0x1800098c1  cmp     eax, r12d
0x1800098c4  jz      loc_180009A32
0x1800098ca  cmp     eax, 2
0x1800098cd  jnz     short loc_180009904
0x1800098cf  mov     rdx, rsi; lpString2
0x1800098d2  mov     rcx, [rcx+20h]; lpString1
0x1800098d6  call    DafIsObjectInList
0x1800098db  mov     r14d, ebx
0x1800098de  jmp     short loc_1800098FC
0x1800098e0  call    cs:__imp_GetLastError
0x1800098e6  mov     r14d, eax
0x1800098e9  test    eax, eax
0x1800098eb  jg      loc_180009C31
0x1800098f1  test    r14d, r14d
0x1800098f4  js      loc_18000999F
0x1800098fa  mov     eax, edi
0x1800098fc  test    eax, eax
0x1800098fe  jz      loc_180009C41
0x180009904  lea     rdi, [r13+130h]
0x18000990b  test    rdi, rdi
0x18000990e  jz      loc_180009ABB
0x180009914  mov     rbx, [rdi]
0x180009917  cmp     rbx, rdi
0x18000991a  jz      loc_180009ABB
0x180009920  cmp     rbx, rdi
0x180009923  jz      loc_180009ABB
0x180009929  mov     rdx, rsi; lpString2
0x18000992c  mov     rcx, [rbx+10h]; lpString1
0x180009930  call    cs:__imp_lstrcmpiW
0x180009936  test    eax, eax
0x180009938  jz      short loc_18000993F
0x18000993a  mov     rbx, [rbx]
0x18000993d  jmp     short loc_180009920
0x18000993f  mov     [rbp+arg_0], rbx
0x180009943  test    rbx, rbx
0x180009946  jz      loc_180009AC3
0x18000994c  xor     edi, edi
0x18000994e  mov     r15, rbx
0x180009951  lea     rax, [rbp+var_20]
0x180009955  mov     qword ptr [rsp+60h+var_28], rax
0x18000995a  mov     qword ptr [rsp+60h+var_30], rbx
0x18000995f  mov     eax, [rbp+arg_30]
0x180009962  mov     dword ptr [rsp+60h+var_38], eax; int
0x180009966  mov     rax, [rbp+arg_28]
0x18000996a  mov     qword ptr [rsp+60h+bIgnoreCase], rax
0x18000996f  mov     r9d, [rbp+arg_20]
0x180009973  mov     r8d, [rbp+arg_8]
0x180009977  mov     rdx, rsi
0x18000997a  mov     rcx, r13
0x18000997d  call    ?UpdateAepEntry@CQueryContext@@IEAAJPEBGW4_DEV_QUERY_RESULT_ACTION@@KQEAU_DEVPROPERTY@@HPEAU_AEP_ENTRY@@AEAV?$DafDynamicArray@U_DEVPROPCOMPKEY@@@@@Z; CQueryContext::UpdateAepEntry(ushort const *,_DEV_QUERY_RESULT_ACTION,ulong,_DEVPROPERTY * const,int,_AEP_ENTRY *,DafDynamicArray<_DEVPROPCOMPKEY> &)
0x180009982  mov     r14d, eax
0x180009985  test    eax, eax
0x180009987  jns     loc_180009B03
0x18000998d  lea     r15, [r13+108h]
0x180009994  test    rbx, rbx
0x180009997  jnz     loc_180009B4E
0x18000999d  xor     edi, edi
0x18000999f  lea     rsi, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x1800099a6  lea     r12, ??_7?$DafDynamicArray@U_DEVPROPERTY@@@@6B@; const DafDynamicArray<_DEVPROPERTY>::`vftable'
0x1800099ad  mov     rcx, r15; lpCriticalSection
0x1800099b0  call    cs:__imp_LeaveCriticalSection
0x1800099b6  mov     rbx, rdi
0x1800099b9  cmp     [rbp+var_10], 0
0x1800099be  ja      loc_180009BD0
0x1800099c4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800099cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800099d2  jnz     loc_180009CCB
0x1800099d8  mov     [rbp+var_20], r12
0x1800099dc  mov     [rbp+var_10], rdi
0x1800099e0  mov     rdx, [rbp+Buffer]; Buffer
0x1800099e4  test    rdx, rdx
0x1800099e7  jz      short loc_1800099F9
0x1800099e9  lea     rcx, [rbp+var_20]; Table
0x1800099ed  call    FreeTableEntry
0x1800099f2  mov     rdx, rdi
0x1800099f5  mov     [rbp+Buffer], rdx
0x1800099f9  lea     rax, ??_7?$TDynamicArray@PEAG@@6B@; const TDynamicArray<ushort *>::`vftable'
0x180009a00  mov     [rbp+var_20], rax
0x180009a04  mov     [rbp+var_10], rdi
0x180009a08  test    rdx, rdx
0x180009a0b  jz      short loc_180009A17
0x180009a0d  lea     rcx, [rbp+var_20]
0x180009a11  call    ?free@?$TDynamicArray@U_DEVPROPERTY@@@@MEAAXPEAX@Z; TDynamicArray<_DEVPROPERTY>::free(void *)
0x180009a16  nop
0x180009a17  mov     eax, r14d
0x180009a1a  mov     rbx, [rsp+60h+arg_10]
0x180009a22  add     rsp, 60h
0x180009a26  pop     r15
0x180009a28  pop     r14
0x180009a2a  pop     r13
0x180009a2c  pop     r12
0x180009a2e  pop     rdi
0x180009a2f  pop     rsi
0x180009a30  pop     rbp
0x180009a31  retn
0x180009a32  mov     r8, [rcx+18h]; lpString2
0x180009a36  test    r8, r8
0x180009a39  jz      loc_18000999F
0x180009a3f  mov     rcx, r9
0x180009a42  mov     rax, r8
0x180009a45  cmp     [rax], di
0x180009a48  jz      short loc_180009A53
0x180009a4a  add     rax, 2
0x180009a4e  sub     rcx, r12
0x180009a51  jnz     short loc_180009A45
0x180009a53  test    rcx, rcx
0x180009a56  cmovnz  r14d, edi
0x180009a5a  sub     r9, rcx
0x180009a5d  test    rcx, rcx
0x180009a60  cmovz   r9, rdi
0x180009a64  jz      loc_18000999F
0x180009a6a  inc     r9d; cchCount2
0x180009a6d  inc     edx; cchCount1
0x180009a6f  mov     [rsp+60h+bIgnoreCase], r12d; bIgnoreCase
0x180009a74  mov     rcx, rsi; lpString1
0x180009a77  call    cs:__imp_CompareStringOrdinal
0x180009a7d  test    eax, eax
0x180009a7f  jz      loc_1800098E0
0x180009a85  cmp     eax, 2
0x180009a88  jnz     loc_180009C16
0x180009a8e  mov     eax, r12d
0x180009a91  jmp     loc_1800098FC
0x180009a96  mov     r9d, 1Fh; int
0x180009a9c  mov     qword ptr [rsp+60h+var_30], r13; char
0x180009aa1  mov     qword ptr [rsp+60h+bIgnoreCase], rcx; MessageGuid
0x180009aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aad  mov     rcx, [rcx+28h]; int
0x180009ab1  call    WPP_RECORDER_SF_sq
0x180009ab6  jmp     loc_18000985A
0x180009abb  mov     [rbp+arg_0], 0
0x180009ac3  lea     rax, WPP_RECORDER_INITIALIZED
0x180009aca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009ad1  jnz     loc_180009C81
0x180009ad7  mov     rdx, [rbp+arg_18]
0x180009adb  test    rdx, rdx
0x180009ade  jz      short loc_180009AE3
0x180009ae0  mov     edx, [rdx+34h]; unsigned int
0x180009ae3  lea     r8, [rbp+arg_0]; struct _AEP_ENTRY **
0x180009ae7  mov     rcx, rsi; unsigned __int16 *
0x180009aea  call    ?CreateAepEntry@@YAJPEBGKPEAPEAU_AEP_ENTRY@@@Z; CreateAepEntry(ushort const *,ulong,_AEP_ENTRY * *)
0x180009aef  mov     r14d, eax
0x180009af2  test    eax, eax
0x180009af4  jns     loc_180009BEF
0x180009afa  mov     rbx, [rbp+arg_0]
0x180009afe  jmp     loc_180009994
0x180009b03  mov     rax, [r13+88h]
0x180009b0a  test    [rax+28h], r12b
0x180009b0e  jz      loc_18000998D
0x180009b14  cmp     dword ptr [r15+44h], 0
0x180009b19  jz      loc_180009CAD
0x180009b1f  test    edi, edi
0x180009b21  jnz     short loc_180009B34
0x180009b23  cmp     [rbp+Buffer], 0
0x180009b28  jz      loc_18000998D
0x180009b2e  mov     r12d, 2
0x180009b34  lea     r9, [rbp+var_20]
0x180009b38  mov     r8, rbx
0x180009b3b  mov     edx, r12d; char
0x180009b3e  mov     rcx, r13; char
0x180009b41  call    ?MakeResult@CQueryContext@@IEAAJW4_DEV_QUERY_RESULT_ACTION@@PEAU_LIST_ENTRY@@AEAV?$DafDynamicArray@U_DEVPROPCOMPKEY@@@@@Z; CQueryContext::MakeResult(_DEV_QUERY_RESULT_ACTION,_LIST_ENTRY *,DafDynamicArray<_DEVPROPCOMPKEY> &)
0x180009b46  mov     r14d, eax
0x180009b49  jmp     loc_18000998D
0x180009b4e  cmp     dword ptr [rbx+44h], 0
0x180009b52  jnz     loc_18000999D
0x180009b58  lea     rax, WPP_RECORDER_INITIALIZED
0x180009b5f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009b66  jz      loc_180009CB8
0x180009b6c  mov     r9d, 22h ; '"'; int
0x180009b72  mov     [rsp+60h+var_38], rsi; __int64
0x180009b77  lea     rsi, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180009b7e  mov     qword ptr [rsp+60h+bIgnoreCase], rsi; MessageGuid
0x180009b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b8a  mov     rcx, [rcx+28h]; int
0x180009b8e  call    WPP_RECORDER_SF_S
0x180009b93  mov     rax, [rbx]
0x180009b96  cmp     [rax+8], rbx
0x180009b9a  jnz     loc_180009CC4
0x180009ba0  mov     rcx, [rbx+8]
0x180009ba4  cmp     [rcx], rbx
0x180009ba7  jnz     loc_180009CC4
0x180009bad  mov     [rcx], rax
0x180009bb0  mov     [rax+8], rcx
0x180009bb4  mov     rcx, rbx; lpMem
0x180009bb7  call    ?FreeAepEntry@@YAXPEAU_AEP_ENTRY@@@Z; FreeAepEntry(_AEP_ENTRY *)
0x180009bbc  xor     edi, edi
0x180009bbe  jmp     loc_1800099A6
0x180009bd0  mov     rcx, rbx
0x180009bd3  shl     rcx, 5
0x180009bd7  add     rcx, [rbp+Buffer]
0x180009bdb  call    DafDevPropCompKeyFree
0x180009be0  inc     rbx
0x180009be3  cmp     rbx, [rbp+var_10]
0x180009be7  jnb     loc_1800099C4
0x180009bed  jmp     short loc_180009BD0
0x180009bef  mov     rax, [rdi+8]
0x180009bf3  cmp     [rax], rdi
0x180009bf6  jnz     loc_180009CC4
0x180009bfc  mov     rbx, [rbp+arg_0]
0x180009c00  mov     [rbx], rdi
0x180009c03  mov     [rbx+8], rax
0x180009c07  mov     [rax], rbx
0x180009c0a  mov     [rdi+8], rbx
0x180009c0e  mov     edi, r12d
0x180009c11  jmp     loc_18000994E
0x180009c16  mov     eax, edi
0x180009c18  jmp     loc_1800098FC
0x180009c1d  mov     ebx, 80070057h
0x180009c22  mov     r14d, ebx
0x180009c25  lea     rsi, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180009c2c  jmp     loc_1800099AD
0x180009c31  movzx   r14d, ax
0x180009c35  or      r14d, 80070000h
0x180009c3c  jmp     loc_1800098F1
0x180009c41  lea     rax, WPP_RECORDER_INITIALIZED
0x180009c48  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009c4f  jz      loc_18000999F
0x180009c55  mov     r9d, 20h ; ' '; int
0x180009c5b  mov     [rsp+60h+var_38], rsi; __int64
0x180009c60  lea     rsi, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180009c67  mov     qword ptr [rsp+60h+bIgnoreCase], rsi; MessageGuid
0x180009c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c73  mov     rcx, [rcx+28h]; int
0x180009c77  call    WPP_RECORDER_SF_S
0x180009c7c  jmp     loc_1800099A6
0x180009c81  mov     r9d, 21h ; '!'; int
0x180009c87  mov     [rsp+60h+var_38], rsi; __int64
0x180009c8c  lea     rax, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180009c93  mov     qword ptr [rsp+60h+bIgnoreCase], rax; MessageGuid
0x180009c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c9f  mov     rcx, [rcx+28h]; int
0x180009ca3  call    WPP_RECORDER_SF_S
0x180009ca8  jmp     loc_180009AD7
0x180009cad  mov     r12d, 3
0x180009cb3  jmp     loc_180009B34
0x180009cb8  lea     rsi, WPP_b4dce31ccfa43c76a9796458bae109f6_Traceguids
0x180009cbf  jmp     loc_180009B93
0x180009cc4  mov     ecx, 3
0x180009cc9  int     29h; Win8: RtlFailFast(ecx)
0x180009ccb  mov     r9d, 23h ; '#'; int
0x180009cd1  mov     dword ptr [rsp+60h+var_28], r14d; char
0x180009cd6  mov     qword ptr [rsp+60h+var_30], r13; char
0x180009cdb  mov     qword ptr [rsp+60h+bIgnoreCase], rsi; MessageGuid
0x180009ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ce7  mov     rcx, [rcx+28h]; int
0x180009ceb  call    WPP_RECORDER_SF_sqd
0x180009cf0  jmp     loc_1800099D8
```
