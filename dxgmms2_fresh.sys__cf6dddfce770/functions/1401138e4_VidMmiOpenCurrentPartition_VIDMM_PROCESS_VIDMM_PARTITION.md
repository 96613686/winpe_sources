# VidMmiOpenCurrentPartition(VIDMM_PROCESS *,VIDMM_PARTITION * *)

- ea: `0x1401138e4`
- end: `0x140113d8f`
- name: `?VidMmiOpenCurrentPartition@@YAJPEAVVIDMM_PROCESS@@PEAPEAUVIDMM_PARTITION@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(struct VIDMM_PROCESS *, struct VIDMM_PARTITION **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140128f3c`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002bf50`
- `0x1400490bc`
- `0x140058f50`
- `0x140059380`
- `0x1400b996c`
- `0x1400ca75c`
- `0x1401138e4`
- `0x140113d98`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140113971`
- `ntoskrnl!RtlInitUnicodeString` at `0x140113971`
- `ntoskrnl!ZwManagePartition` at `0x140113a26`
- `ntoskrnl!ZwManagePartition` at `0x140113a26`
- `ntoskrnl!ObCloseHandle` at `0x140113d4e`
- `ntoskrnl!ObCloseHandle` at `0x140113d4e`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140113caf`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140113caf`
- `ntoskrnl!PsPartitionType` at `0x140113bc5`
- `ntoskrnl!ZwOpenPartition` at `0x1401139ad`
- `ntoskrnl!ZwOpenPartition` at `0x1401139ad`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140113beb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140113beb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140113a9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140113a9f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140113ab2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140113ab2`
- `watchdog!WdLogSingleEntry0` at `0x140113b6f`
- `watchdog!WdLogSingleEntry0` at `0x140113b9d`
- `watchdog!WdLogSingleEntry0` at `0x140113cf6`
- `watchdog!WdLogSingleEntry0` at `0x140113b6f`
- `watchdog!WdLogSingleEntry0` at `0x140113b9d`
- `watchdog!WdLogSingleEntry0` at `0x140113cf6`
- `watchdog!WdLogSingleEntry1` at `0x1401139cf`
- `watchdog!WdLogSingleEntry1` at `0x140113a44`
- `watchdog!WdLogSingleEntry1` at `0x140113c06`
- `watchdog!WdLogSingleEntry1` at `0x1401139cf`
- `watchdog!WdLogSingleEntry1` at `0x140113a44`
- `watchdog!WdLogSingleEntry1` at `0x140113c06`

## string_xrefs

- `0x1401139e0`: `Failed to open graphics partition handle. Status=0x%.8x`

## pseudocode

```c
__int64 __fastcall VidMmiOpenCurrentPartition(struct VIDMM_PROCESS *a1, struct VIDMM_PARTITION **a2)
{
  __int64 v3; // r14
  int v4; // eax
  int v5; // r15d
  __int64 v6; // rbx
  int v7; // ecx
  int v8; // r8d
  int v9; // eax
  __int64 v10; // rsi
  struct _RTL_BALANCED_NODE *v11; // rdi
  int v12; // ecx
  int v13; // r8d
  void *v14; // r12
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  struct _RTL_BALANCED_NODE *v19; // rax
  NTSTATUS v20; // eax
  int v21; // ecx
  int v22; // r8d
  unsigned int v23; // edx
  unsigned int v24; // eax
  void *Right_low; // r15
  struct _RTL_BALANCED_NODE *v26; // rbx
  struct _RTL_BALANCED_NODE *v27; // rax
  int v28; // ecx
  int v29; // r8d
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+70h] [rbp-90h]
  struct VIDMM_PARTITION **v36; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int128 v40; // [rsp+B0h] [rbp-50h]
  _QWORD v41[31]; // [rsp+C0h] [rbp-40h] BYREF

  v36 = a2;
  v3 = -1;
  memset(v41, 0, sizeof(v41));
  if ( *(_BYTE *)(*((_QWORD *)a1 + 10) + 574LL) )
  {
    Handle = 0;
    DestinationString = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    RtlInitUnicodeString(&DestinationString, L"\\GLOBAL??\\MemoryPartitionGraphics");
    LODWORD(v38) = 48;
    *(_QWORD *)&v39 = &DestinationString;
    *((_QWORD *)&v38 + 1) = 0;
    DWORD2(v39) = 64;
    v40 = 0;
    v4 = ZwOpenPartition(&Handle, 2031619, &v38);
    if ( v4 >= 0 )
    {
      v3 = (__int64)Handle;
      v5 = 1;
      goto LABEL_6;
    }
    v6 = v4;
    WdLogSingleEntry1(1, v4);
    WdLogGlobalForLineNumber = 162;
    DxgkLogInternalTriageEvent(
      v7,
      0x40000,
      v8,
      (unsigned int)L"Failed to open graphics partition handle. Status=0x%.8x",
      v6,
      0,
      0,
      0);
  }
  v5 = 0;
LABEL_6:
  HIDWORD(v41[0]) = -1;
  LODWORD(v41[1]) = -1;
  v9 = ZwManagePartition(v3, 0, 0, v41, 248);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 0;
    WdLogSingleEntry1(1, v9);
    WdLogGlobalForLineNumber = 188;
    DxgkLogInternalTriageEvent(
      v12,
      0x40000,
      v13,
      (unsigned int)L"Failed to get partition information from NtManagedPartition. Status=0x%.8x",
      v10,
      0,
      0,
      0);
    goto LABEL_37;
  }
  v14 = (void *)LODWORD(v41[29]);
  v34 = &VIDMM_PARTITION::_PartitionLock;
  v35 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v34, 0);
  v11 = VIDMM_PARTITION::_PartitionTree;
  v35 = 2;
  if ( !VIDMM_PARTITION::_PartitionTree )
    goto LABEL_15;
  do
  {
    v15 = CompareVidMmPartitionById(v14, v11);
    if ( v15 >= 0 )
    {
      if ( v15 <= 0 )
        break;
      v11 = v11->Children[1];
    }
    else
    {
      v11 = v11->Children[0];
    }
  }
  while ( v11 );
  if ( !v11 )
  {
LABEL_15:
    v16 = v41[6] << 12;
    v17 = operator new(120, 1647667542, 256);
    v11 = (struct _RTL_BALANCED_NODE *)v17;
    if ( !v17 )
    {
      _InterlockedIncrement(&dword_1400877F0);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 212;
      DxgkLogInternalTriageEvent(
        v28,
        262145,
        v29,
        (unsigned int)L"Couldn't allocate memory for vidmmpartition.",
        212,
        0,
        0,
        0);
      LODWORD(v10) = -1073741801;
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v33);
      v11 = 0;
      goto LABEL_37;
    }
    *(_DWORD *)(v17 + 32) = (_DWORD)v14;
    *(_QWORD *)(v17 + 24) = 0;
    *(_DWORD *)(v17 + 36) = 0;
    *(_QWORD *)(v17 + 40) = 0;
    *(_QWORD *)(v17 + 56) = 0;
    *(_QWORD *)(v17 + 64) = 0;
    *(_QWORD *)(v17 + 80) = 0;
    *(_QWORD *)(v17 + 88) = 0;
    *(_DWORD *)(v17 + 100) = 0;
    *(_QWORD *)(v17 + 104) = 0;
    *(_DWORD *)(v17 + 72) = 0;
    *(_QWORD *)(v17 + 48) = v16;
    LODWORD(v10) = VIDMM_PARTITION::Initialize_Legacy((VIDMM_PARTITION *)v17);
    if ( (int)v10 < 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 220;
LABEL_23:
      DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v33);
LABEL_35:
      VIDMM_PARTITION::`scalar deleting destructor'((VIDMM_PARTITION *)v11, v23);
      v11 = 0;
      goto LABEL_37;
    }
    LODWORD(v10) = VIDMM_GLOBAL::InitializePartitionForAllAdapters((struct VIDMM_PARTITION *)v11);
    if ( (int)v10 < 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 227;
      goto LABEL_23;
    }
    v19 = 0;
    if ( v3 != -1 )
    {
      Object = 0;
      v20 = ObReferenceObjectByHandle((HANDLE)v3, 0, PsPartitionType, 0, &Object, 0);
      v10 = v20;
      if ( v20 < 0 )
      {
        WdLogSingleEntry1(1, v20);
        WdLogGlobalForLineNumber = 237;
        DxgkLogInternalTriageEvent(
          v21,
          0x40000,
          v22,
          (unsigned int)L"Failed to reference partition object, Status=0x%.8x",
          v10,
          0,
          0,
          0);
        goto LABEL_23;
      }
      v19 = (struct _RTL_BALANCED_NODE *)Object;
    }
    v11[1].Children[0] = v19;
    v24 = v5 | (__int64)v11[3].Children[0] & 0xFFFFFFFE;
    Right_low = (void *)LODWORD(v11[1].Right);
    LODWORD(v11[3].Children[0]) = v24;
    v26 = VIDMM_PARTITION::_PartitionTree;
    if ( VIDMM_PARTITION::_PartitionTree )
    {
      while ( 1 )
      {
        if ( (int)CompareVidMmPartitionById(Right_low, v26) < 0 )
        {
          v27 = v26->Children[0];
          if ( !v26->Children[0] )
            break;
        }
        else
        {
          v27 = v26->Children[1];
          if ( !v27 )
          {
            LOBYTE(v18) = 1;
            goto LABEL_32;
          }
        }
        v26 = v27;
      }
    }
    LOBYTE(v18) = 0;
LABEL_32:
    RtlAvlInsertNodeEx(&VIDMM_PARTITION::_PartitionTree, v26, v18, v11);
  }
  _InterlockedIncrement((volatile signed __int32 *)&v11[1].Right + 1);
  DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK((DXGAUTOEXPUSHLOCK *)v33);
  *((_QWORD *)a1 + 44) = v3;
  if ( (int)v10 >= 0 )
    goto LABEL_39;
  if ( v11 )
    goto LABEL_35;
LABEL_37:
  if ( v3 != -1 )
    ObCloseHandle((HANDLE)v3, 0);
LABEL_39:
  *v36 = (struct VIDMM_PARTITION *)v11;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1401138e4  mov     [rsp-8+arg_10], rbx
0x1401138e9  push    rbp
0x1401138ea  push    rsi
0x1401138eb  push    rdi
0x1401138ec  push    r12
0x1401138ee  push    r13
0x1401138f0  push    r14
0x1401138f2  push    r15
0x1401138f4  lea     rbp, [rsp-0C0h]
0x1401138fc  sub     rsp, 1C0h
0x140113903  mov     rax, cs:__security_cookie
0x14011390a  xor     rax, rsp
0x14011390d  mov     [rbp+0F0h+var_38], rax
0x140113914  mov     [rsp+1F0h+var_178], rdx
0x140113919  mov     r13, rcx
0x14011391c  mov     esi, 0F8h
0x140113921  lea     rcx, [rbp+0F0h+var_130]; void *
0x140113925  mov     r8d, esi; Size
0x140113928  xor     edx, edx; Val
0x14011392a  or      r14, 0FFFFFFFFFFFFFFFFh
0x14011392e  call    memset
0x140113933  mov     rax, [r13+50h]
0x140113937  lea     edi, [r14+2]
0x14011393b  xor     r12d, r12d
0x14011393e  cmp     [rax+23Eh], r12b
0x140113945  jz      loc_140113A0A
0x14011394b  xorps   xmm1, xmm1
0x14011394e  mov     [rsp+1F0h+Handle], r12
0x140113953  xorps   xmm0, xmm0
0x140113956  lea     rdx, SourceString; "\\GLOBAL??\\MemoryPartitionGraphics"
0x14011395d  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x140113961  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x140113965  movups  [rbp+0F0h+var_160], xmm1
0x140113969  movups  [rbp+0F0h+var_150], xmm1
0x14011396d  movups  [rbp+0F0h+var_140], xmm1
0x140113971  call    cs:__imp_RtlInitUnicodeString
0x140113978  nop     dword ptr [rax+rax+00h]
0x14011397d  lea     rax, [rbp+0F0h+DestinationString]
0x140113981  mov     dword ptr [rbp+0F0h+var_160], 30h ; '0'
0x140113988  xorps   xmm0, xmm0
0x14011398b  mov     qword ptr [rbp+0F0h+var_150], rax
0x14011398f  lea     r8, [rbp+0F0h+var_160]
0x140113993  mov     qword ptr [rbp+0F0h+var_160+8], r12
0x140113997  mov     edx, 1F0003h
0x14011399c  mov     dword ptr [rbp+0F0h+var_150+8], 40h ; '@'
0x1401139a3  lea     rcx, [rsp+1F0h+Handle]
0x1401139a8  movdqu  [rbp+0F0h+var_140], xmm0
0x1401139ad  call    cs:__imp_ZwOpenPartition
0x1401139b4  nop     dword ptr [rax+rax+00h]
0x1401139b9  test    eax, eax
0x1401139bb  js      short loc_1401139C7
0x1401139bd  mov     r14, [rsp+1F0h+Handle]
0x1401139c2  mov     r15d, edi
0x1401139c5  jmp     short loc_140113A0D
0x1401139c7  movsxd  rbx, eax
0x1401139ca  mov     ecx, edi
0x1401139cc  mov     rdx, rbx
0x1401139cf  call    cs:__imp_WdLogSingleEntry1
0x1401139d6  nop     dword ptr [rax+rax+00h]
0x1401139db  mov     [rsp+1F0h+var_1B8], r12
0x1401139e0  lea     r9, aFailedToOpenGr; "Failed to open graphics partition handl"...
0x1401139e7  mov     [rsp+1F0h+var_1C0], r12
0x1401139ec  mov     edx, 40000h
0x1401139f1  mov     [rsp+1F0h+HandleInformation], r12
0x1401139f6  mov     [rsp+1F0h+Object], rbx
0x1401139fb  mov     cs:WdLogGlobalForLineNumber, 0A2h
0x140113a05  call    DxgkLogInternalTriageEvent
0x140113a0a  mov     r15d, r12d
0x140113a0d  or      eax, 0FFFFFFFFh
0x140113a10  mov     dword ptr [rsp+1F0h+Object], esi
0x140113a14  lea     r9, [rbp+0F0h+var_130]
0x140113a18  mov     [rbp+0F0h+var_12C], eax
0x140113a1b  xor     r8d, r8d
0x140113a1e  mov     [rbp+0F0h+var_128], eax
0x140113a21  xor     edx, edx
0x140113a23  mov     rcx, r14
0x140113a26  call    cs:__imp_ZwManagePartition
0x140113a2d  nop     dword ptr [rax+rax+00h]
0x140113a32  movsxd  rsi, eax
0x140113a35  test    eax, eax
0x140113a37  jns     short loc_140113A84
0x140113a39  mov     rdi, r12
0x140113a3c  mov     rdx, rsi
0x140113a3f  mov     ecx, 1
0x140113a44  call    cs:__imp_WdLogSingleEntry1
0x140113a4b  nop     dword ptr [rax+rax+00h]
0x140113a50  mov     [rsp+1F0h+var_1B8], r12
0x140113a55  lea     r9, aFailedToGetPar_0; "Failed to get partition information fro"...
0x140113a5c  mov     [rsp+1F0h+var_1C0], r12
0x140113a61  mov     edx, 40000h
0x140113a66  mov     [rsp+1F0h+HandleInformation], r12
0x140113a6b  mov     [rsp+1F0h+Object], rsi
0x140113a70  mov     cs:WdLogGlobalForLineNumber, 0BCh
0x140113a7a  call    DxgkLogInternalTriageEvent
0x140113a7f  jmp     loc_140113D43
0x140113a84  mov     r12d, dword ptr [rbp+0F0h+var_48]
0x140113a8b  lea     rax, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x140113a92  mov     [rsp+1F0h+var_188], rax
0x140113a97  mov     [rsp+1F0h+var_180], 0
0x140113a9f  call    cs:__imp_KeEnterCriticalRegion
0x140113aa6  nop     dword ptr [rax+rax+00h]
0x140113aab  mov     rcx, [rsp+1F0h+var_188]
0x140113ab0  xor     edx, edx
0x140113ab2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140113ab9  nop     dword ptr [rax+rax+00h]
0x140113abe  mov     rdi, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140113ac5  mov     [rsp+1F0h+var_180], 2
0x140113acd  test    rdi, rdi
0x140113ad0  jz      short loc_140113AFE
0x140113ad2  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x140113ad5  mov     rcx, r12; void *
0x140113ad8  call    ?CompareVidMmPartitionById@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; CompareVidMmPartitionById(void *,_RTL_BALANCED_NODE *)
0x140113add  test    eax, eax
0x140113adf  jns     short loc_140113AE6
0x140113ae1  mov     rdi, [rdi]
0x140113ae4  jmp     short loc_140113AEC
0x140113ae6  jle     short loc_140113AF1
0x140113ae8  mov     rdi, [rdi+8]
0x140113aec  test    rdi, rdi
0x140113aef  jnz     short loc_140113AD2
0x140113af1  test    rdi, rdi
0x140113af4  jz      short loc_140113AFE
0x140113af6  xor     r12d, r12d
0x140113af9  jmp     loc_140113CBB
0x140113afe  mov     rbx, [rbp+0F0h+var_100]
0x140113b02  mov     edx, 62356956h
0x140113b07  mov     ecx, 78h ; 'x'
0x140113b0c  shl     rbx, 0Ch
0x140113b10  mov     r8d, 100h
0x140113b16  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140113b1b  xor     esi, esi
0x140113b1d  mov     rdi, rax
0x140113b20  test    rax, rax
0x140113b23  jz      loc_140113CEA
0x140113b29  mov     [rax+20h], r12d
0x140113b2d  mov     rcx, rax; this
0x140113b30  xor     r12d, r12d
0x140113b33  mov     [rax+18h], rsi
0x140113b37  mov     [rax+24h], r12d
0x140113b3b  mov     [rax+28h], r12
0x140113b3f  mov     [rax+38h], r12
0x140113b43  mov     [rax+40h], r12
0x140113b47  mov     [rax+50h], r12
0x140113b4b  mov     [rax+58h], r12
0x140113b4f  mov     [rax+64h], r12d
0x140113b53  mov     [rax+68h], r12
0x140113b57  mov     [rax+48h], r12d
0x140113b5b  mov     [rax+30h], rbx
0x140113b5f  call    ?Initialize_Legacy@VIDMM_PARTITION@@QEAAJXZ; VIDMM_PARTITION::Initialize_Legacy(void)
0x140113b64  mov     esi, eax
0x140113b66  test    eax, eax
0x140113b68  jns     short loc_140113B8A
0x140113b6a  lea     ecx, [r12+3]
0x140113b6f  call    cs:__imp_WdLogSingleEntry0
0x140113b76  nop     dword ptr [rax+rax+00h]
0x140113b7b  mov     cs:WdLogGlobalForLineNumber, 0DCh
0x140113b85  jmp     loc_140113C41
0x140113b8a  mov     rcx, rdi; struct VIDMM_PARTITION *
0x140113b8d  call    ?InitializePartitionForAllAdapters@VIDMM_GLOBAL@@SAJPEAUVIDMM_PARTITION@@@Z; VIDMM_GLOBAL::InitializePartitionForAllAdapters(VIDMM_PARTITION *)
0x140113b92  mov     esi, eax
0x140113b94  test    eax, eax
0x140113b96  jns     short loc_140113BB8
0x140113b98  mov     ecx, 3
0x140113b9d  call    cs:__imp_WdLogSingleEntry0
0x140113ba4  nop     dword ptr [rax+rax+00h]
0x140113ba9  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x140113bb3  jmp     loc_140113C41
0x140113bb8  mov     rax, r12
0x140113bbb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140113bbf  jz      loc_140113C55
0x140113bc5  mov     r8, cs:__imp_PsPartitionType
0x140113bcc  lea     rax, [rsp+1F0h+var_198]
0x140113bd1  mov     [rsp+1F0h+HandleInformation], r12; HandleInformation
0x140113bd6  xor     r9d, r9d; AccessMode
0x140113bd9  xor     edx, edx; DesiredAccess
0x140113bdb  mov     [rsp+1F0h+var_198], r12
0x140113be0  mov     rcx, r14; Handle
0x140113be3  mov     [rsp+1F0h+Object], rax; Object
0x140113be8  mov     r8, [r8]; ObjectType
0x140113beb  call    cs:__imp_ObReferenceObjectByHandle
0x140113bf2  nop     dword ptr [rax+rax+00h]
0x140113bf7  movsxd  rsi, eax
0x140113bfa  test    eax, eax
0x140113bfc  jns     short loc_140113C50
0x140113bfe  mov     rdx, rsi
0x140113c01  mov     ecx, 1
0x140113c06  call    cs:__imp_WdLogSingleEntry1
0x140113c0d  nop     dword ptr [rax+rax+00h]
0x140113c12  mov     [rsp+1F0h+var_1B8], r12
0x140113c17  lea     r9, aFailedToRefere_0; "Failed to reference partition object, S"...
0x140113c1e  mov     [rsp+1F0h+var_1C0], r12
0x140113c23  mov     edx, 40000h
0x140113c28  mov     [rsp+1F0h+HandleInformation], r12
0x140113c2d  mov     [rsp+1F0h+Object], rsi
0x140113c32  mov     cs:WdLogGlobalForLineNumber, 0EDh
0x140113c3c  call    DxgkLogInternalTriageEvent
0x140113c41  lea     rcx, [rsp+1F0h+var_190]; this
0x140113c46  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x140113c4b  jmp     loc_140113CDD
0x140113c50  mov     rax, [rsp+1F0h+var_198]
0x140113c55  mov     [rdi+18h], rax
0x140113c59  mov     eax, [rdi+48h]
0x140113c5c  and     eax, 0FFFFFFFEh
0x140113c5f  or      eax, r15d
0x140113c62  mov     r15d, [rdi+20h]
0x140113c66  mov     [rdi+48h], eax
0x140113c69  mov     rbx, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140113c70  test    rbx, rbx
0x140113c73  jz      short loc_140113C9F
0x140113c75  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x140113c78  mov     rcx, r15; void *
0x140113c7b  call    ?CompareVidMmPartitionById@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; CompareVidMmPartitionById(void *,_RTL_BALANCED_NODE *)
0x140113c80  test    eax, eax
0x140113c82  js      short loc_140113C92
0x140113c84  mov     rax, [rbx+8]
0x140113c88  test    rax, rax
0x140113c8b  jnz     short loc_140113C9A
0x140113c8d  mov     r8b, 1
0x140113c90  jmp     short loc_140113CA2
0x140113c92  mov     rax, [rbx]
0x140113c95  test    rax, rax
0x140113c98  jz      short loc_140113C9F
0x140113c9a  mov     rbx, rax
0x140113c9d  jmp     short loc_140113C75
0x140113c9f  mov     r8b, r12b
0x140113ca2  mov     r9, rdi
0x140113ca5  lea     rcx, ?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x140113cac  mov     rdx, rbx
0x140113caf  call    cs:__imp_RtlAvlInsertNodeEx
0x140113cb6  nop     dword ptr [rax+rax+00h]
0x140113cbb  lock inc dword ptr [rdi+24h]
0x140113cbf  lea     rcx, [rsp+1F0h+var_190]; this
0x140113cc4  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x140113cc9  mov     [r13+160h], r14
0x140113cd0  test    esi, esi
0x140113cd2  jns     loc_140113D5A
0x140113cd8  test    rdi, rdi
0x140113cdb  jz      short loc_140113D43
0x140113cdd  mov     rcx, rdi; this
0x140113ce0  call    ??_GVIDMM_PARTITION@@QEAAPEAXI@Z; VIDMM_PARTITION::`scalar deleting destructor'(uint)
0x140113ce5  mov     rdi, r12
0x140113ce8  jmp     short loc_140113D43
0x140113cea  lock inc cs:dword_1400877F0
0x140113cf1  mov     ecx, 6
0x140113cf6  call    cs:__imp_WdLogSingleEntry0
0x140113cfd  nop     dword ptr [rax+rax+00h]
0x140113d02  mov     [rsp+1F0h+var_1B8], rsi
0x140113d07  lea     r9, aCouldnTAllocat_61; "Couldn't allocate memory for vidmmparti"...
0x140113d0e  mov     eax, 0D4h
0x140113d13  mov     [rsp+1F0h+var_1C0], rsi
0x140113d18  mov     [rsp+1F0h+HandleInformation], rsi
0x140113d1d  mov     edx, 40001h
0x140113d22  mov     cs:WdLogGlobalForLineNumber, eax
0x140113d28  mov     [rsp+1F0h+Object], rax
0x140113d2d  call    DxgkLogInternalTriageEvent
0x140113d32  lea     rcx, [rsp+1F0h+var_190]; this
0x140113d37  mov     esi, 0C0000017h
0x140113d3c  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x140113d41  xor     edi, edi
0x140113d43  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140113d47  jz      short loc_140113D5A
0x140113d49  xor     edx, edx; PreviousMode
0x140113d4b  mov     rcx, r14; Handle
0x140113d4e  call    cs:__imp_ObCloseHandle
0x140113d55  nop     dword ptr [rax+rax+00h]
0x140113d5a  mov     rax, [rsp+1F0h+var_178]
0x140113d5f  mov     [rax], rdi
0x140113d62  mov     eax, esi
0x140113d64  mov     rcx, [rbp+0F0h+var_38]
0x140113d6b  xor     rcx, rsp; StackCookie
0x140113d6e  call    __security_check_cookie
0x140113d73  mov     rbx, [rsp+1F0h+arg_10]
0x140113d7b  add     rsp, 1C0h
0x140113d82  pop     r15
0x140113d84  pop     r14
0x140113d86  pop     r13
0x140113d88  pop     r12
0x140113d8a  pop     rdi
0x140113d8b  pop     rsi
0x140113d8c  pop     rbp
0x140113d8d  retn
```
