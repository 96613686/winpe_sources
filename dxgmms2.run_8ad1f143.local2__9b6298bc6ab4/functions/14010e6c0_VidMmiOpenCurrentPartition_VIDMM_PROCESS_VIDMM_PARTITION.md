# VidMmiOpenCurrentPartition(VIDMM_PROCESS *,VIDMM_PARTITION * *)

- ea: `0x14010e6c0`
- end: `0x14010eb5b`
- name: `?VidMmiOpenCurrentPartition@@YAJPEAVVIDMM_PROCESS@@PEAPEAUVIDMM_PARTITION@@@Z`
- size: `1179`
- prototype: `__int64 __fastcall(struct VIDMM_PROCESS *, struct VIDMM_PARTITION **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14010e2bc`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002ee90`
- `0x140048b2c`
- `0x140058680`
- `0x140058ac0`
- `0x1400b5f94`
- `0x1400c4da4`
- `0x14010e6c0`
- `0x14010eb64`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14010e74d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010e74d`
- `ntoskrnl!ZwManagePartition` at `0x14010e802`
- `ntoskrnl!ZwManagePartition` at `0x14010e802`
- `ntoskrnl!ObCloseHandle` at `0x14010eb1a`
- `ntoskrnl!ObCloseHandle` at `0x14010eb1a`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14010ea7b`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x14010ea7b`
- `ntoskrnl!ZwOpenPartition` at `0x14010e789`
- `ntoskrnl!ZwOpenPartition` at `0x14010e789`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14010e9b7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14010e9b7`
- `ntoskrnl!PsPartitionType` at `0x14010e991`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e87b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010e87b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e88e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010e88e`
- `watchdog!WdLogSingleEntry0` at `0x14010e93b`
- `watchdog!WdLogSingleEntry0` at `0x14010e969`
- `watchdog!WdLogSingleEntry0` at `0x14010eac2`
- `watchdog!WdLogSingleEntry0` at `0x14010e93b`
- `watchdog!WdLogSingleEntry0` at `0x14010e969`
- `watchdog!WdLogSingleEntry0` at `0x14010eac2`
- `watchdog!WdLogSingleEntry1` at `0x14010e7ab`
- `watchdog!WdLogSingleEntry1` at `0x14010e820`
- `watchdog!WdLogSingleEntry1` at `0x14010e9d2`
- `watchdog!WdLogSingleEntry1` at `0x14010e7ab`
- `watchdog!WdLogSingleEntry1` at `0x14010e820`
- `watchdog!WdLogSingleEntry1` at `0x14010e9d2`

## string_xrefs

- `0x14010e7bc`: `Failed to open graphics partition handle. Status=0x%.8x`

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
  if ( *(_BYTE *)(*((_QWORD *)a1 + 9) + 574LL) )
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
    WdLogGlobalForLineNumber = 164;
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
    WdLogGlobalForLineNumber = 190;
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
    v17 = operator new(80, 1647667542, 256);
    v11 = (struct _RTL_BALANCED_NODE *)v17;
    if ( !v17 )
    {
      _InterlockedIncrement(&dword_140086810);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 214;
      DxgkLogInternalTriageEvent(
        v28,
        262145,
        v29,
        (unsigned int)L"Couldn't allocate memory for vidmmpartition.",
        214,
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
    *(_DWORD *)(v17 + 72) = 0;
    *(_QWORD *)(v17 + 48) = v16;
    LODWORD(v10) = VIDMM_PARTITION::Initialize((VIDMM_PARTITION *)v17);
    if ( (int)v10 < 0 )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 222;
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
      WdLogGlobalForLineNumber = 229;
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
        WdLogGlobalForLineNumber = 239;
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
  *((_QWORD *)a1 + 43) = v3;
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
0x14010e6c0  mov     [rsp-8+arg_10], rbx
0x14010e6c5  push    rbp
0x14010e6c6  push    rsi
0x14010e6c7  push    rdi
0x14010e6c8  push    r12
0x14010e6ca  push    r13
0x14010e6cc  push    r14
0x14010e6ce  push    r15
0x14010e6d0  lea     rbp, [rsp-0C0h]
0x14010e6d8  sub     rsp, 1C0h
0x14010e6df  mov     rax, cs:__security_cookie
0x14010e6e6  xor     rax, rsp
0x14010e6e9  mov     [rbp+0F0h+var_38], rax
0x14010e6f0  mov     [rsp+1F0h+var_178], rdx
0x14010e6f5  mov     r13, rcx
0x14010e6f8  mov     esi, 0F8h
0x14010e6fd  lea     rcx, [rbp+0F0h+var_130]; void *
0x14010e701  mov     r8d, esi; Size
0x14010e704  xor     edx, edx; Val
0x14010e706  or      r14, 0FFFFFFFFFFFFFFFFh
0x14010e70a  call    memset
0x14010e70f  mov     rax, [r13+48h]
0x14010e713  lea     edi, [r14+2]
0x14010e717  xor     r12d, r12d
0x14010e71a  cmp     [rax+23Eh], r12b
0x14010e721  jz      loc_14010E7E6
0x14010e727  xorps   xmm1, xmm1
0x14010e72a  mov     [rsp+1F0h+Handle], r12
0x14010e72f  xorps   xmm0, xmm0
0x14010e732  lea     rdx, aGlobalMemorypa; "\\GLOBAL??\\MemoryPartitionGraphics"
0x14010e739  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x14010e73d  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x14010e741  movups  [rbp+0F0h+var_160], xmm1
0x14010e745  movups  [rbp+0F0h+var_150], xmm1
0x14010e749  movups  [rbp+0F0h+var_140], xmm1
0x14010e74d  call    cs:__imp_RtlInitUnicodeString
0x14010e754  nop     dword ptr [rax+rax+00h]
0x14010e759  lea     rax, [rbp+0F0h+DestinationString]
0x14010e75d  mov     dword ptr [rbp+0F0h+var_160], 30h ; '0'
0x14010e764  xorps   xmm0, xmm0
0x14010e767  mov     qword ptr [rbp+0F0h+var_150], rax
0x14010e76b  lea     r8, [rbp+0F0h+var_160]
0x14010e76f  mov     qword ptr [rbp+0F0h+var_160+8], r12
0x14010e773  mov     edx, 1F0003h
0x14010e778  mov     dword ptr [rbp+0F0h+var_150+8], 40h ; '@'
0x14010e77f  lea     rcx, [rsp+1F0h+Handle]
0x14010e784  movdqu  [rbp+0F0h+var_140], xmm0
0x14010e789  call    cs:__imp_ZwOpenPartition
0x14010e790  nop     dword ptr [rax+rax+00h]
0x14010e795  test    eax, eax
0x14010e797  js      short loc_14010E7A3
0x14010e799  mov     r14, [rsp+1F0h+Handle]
0x14010e79e  mov     r15d, edi
0x14010e7a1  jmp     short loc_14010E7E9
0x14010e7a3  movsxd  rbx, eax
0x14010e7a6  mov     ecx, edi
0x14010e7a8  mov     rdx, rbx
0x14010e7ab  call    cs:__imp_WdLogSingleEntry1
0x14010e7b2  nop     dword ptr [rax+rax+00h]
0x14010e7b7  mov     [rsp+1F0h+var_1B8], r12
0x14010e7bc  lea     r9, aFailedToOpenGr; "Failed to open graphics partition handl"...
0x14010e7c3  mov     [rsp+1F0h+var_1C0], r12
0x14010e7c8  mov     edx, 40000h
0x14010e7cd  mov     [rsp+1F0h+HandleInformation], r12
0x14010e7d2  mov     [rsp+1F0h+Object], rbx
0x14010e7d7  mov     cs:WdLogGlobalForLineNumber, 0A4h
0x14010e7e1  call    DxgkLogInternalTriageEvent
0x14010e7e6  mov     r15d, r12d
0x14010e7e9  or      eax, 0FFFFFFFFh
0x14010e7ec  mov     dword ptr [rsp+1F0h+Object], esi
0x14010e7f0  lea     r9, [rbp+0F0h+var_130]
0x14010e7f4  mov     [rbp+0F0h+var_12C], eax
0x14010e7f7  xor     r8d, r8d
0x14010e7fa  mov     [rbp+0F0h+var_128], eax
0x14010e7fd  xor     edx, edx
0x14010e7ff  mov     rcx, r14
0x14010e802  call    cs:__imp_ZwManagePartition
0x14010e809  nop     dword ptr [rax+rax+00h]
0x14010e80e  movsxd  rsi, eax
0x14010e811  test    eax, eax
0x14010e813  jns     short loc_14010E860
0x14010e815  mov     rdi, r12
0x14010e818  mov     rdx, rsi
0x14010e81b  mov     ecx, 1
0x14010e820  call    cs:__imp_WdLogSingleEntry1
0x14010e827  nop     dword ptr [rax+rax+00h]
0x14010e82c  mov     [rsp+1F0h+var_1B8], r12
0x14010e831  lea     r9, aFailedToGetPar; "Failed to get partition information fro"...
0x14010e838  mov     [rsp+1F0h+var_1C0], r12
0x14010e83d  mov     edx, 40000h
0x14010e842  mov     [rsp+1F0h+HandleInformation], r12
0x14010e847  mov     [rsp+1F0h+Object], rsi
0x14010e84c  mov     cs:WdLogGlobalForLineNumber, 0BEh
0x14010e856  call    DxgkLogInternalTriageEvent
0x14010e85b  jmp     loc_14010EB0F
0x14010e860  mov     r12d, dword ptr [rbp+0F0h+var_48]
0x14010e867  lea     rax, ?_PartitionLock@VIDMM_PARTITION@@2U_EX_PUSH_LOCK@@A; _EX_PUSH_LOCK VIDMM_PARTITION::_PartitionLock
0x14010e86e  mov     [rsp+1F0h+var_188], rax
0x14010e873  mov     [rsp+1F0h+var_180], 0
0x14010e87b  call    cs:__imp_KeEnterCriticalRegion
0x14010e882  nop     dword ptr [rax+rax+00h]
0x14010e887  mov     rcx, [rsp+1F0h+var_188]
0x14010e88c  xor     edx, edx
0x14010e88e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14010e895  nop     dword ptr [rax+rax+00h]
0x14010e89a  mov     rdi, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x14010e8a1  mov     [rsp+1F0h+var_180], 2
0x14010e8a9  test    rdi, rdi
0x14010e8ac  jz      short loc_14010E8DA
0x14010e8ae  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x14010e8b1  mov     rcx, r12; void *
0x14010e8b4  call    ?CompareVidMmPartitionById@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; CompareVidMmPartitionById(void *,_RTL_BALANCED_NODE *)
0x14010e8b9  test    eax, eax
0x14010e8bb  jns     short loc_14010E8C2
0x14010e8bd  mov     rdi, [rdi]
0x14010e8c0  jmp     short loc_14010E8C8
0x14010e8c2  jle     short loc_14010E8CD
0x14010e8c4  mov     rdi, [rdi+8]
0x14010e8c8  test    rdi, rdi
0x14010e8cb  jnz     short loc_14010E8AE
0x14010e8cd  test    rdi, rdi
0x14010e8d0  jz      short loc_14010E8DA
0x14010e8d2  xor     r12d, r12d
0x14010e8d5  jmp     loc_14010EA87
0x14010e8da  mov     rbx, [rbp+0F0h+var_100]
0x14010e8de  mov     edx, 62356956h
0x14010e8e3  mov     ecx, 50h ; 'P'
0x14010e8e8  shl     rbx, 0Ch
0x14010e8ec  mov     r8d, 100h
0x14010e8f2  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14010e8f7  xor     esi, esi
0x14010e8f9  mov     rdi, rax
0x14010e8fc  test    rax, rax
0x14010e8ff  jz      loc_14010EAB6
0x14010e905  mov     [rax+20h], r12d
0x14010e909  mov     rcx, rax; this
0x14010e90c  xor     r12d, r12d
0x14010e90f  mov     [rax+18h], rsi
0x14010e913  mov     [rax+24h], r12d
0x14010e917  mov     [rax+28h], r12
0x14010e91b  mov     [rax+38h], r12
0x14010e91f  mov     [rax+40h], r12
0x14010e923  mov     [rax+48h], r12d
0x14010e927  mov     [rax+30h], rbx
0x14010e92b  call    ?Initialize@VIDMM_PARTITION@@QEAAJXZ; VIDMM_PARTITION::Initialize(void)
0x14010e930  mov     esi, eax
0x14010e932  test    eax, eax
0x14010e934  jns     short loc_14010E956
0x14010e936  lea     ecx, [r12+3]
0x14010e93b  call    cs:__imp_WdLogSingleEntry0
0x14010e942  nop     dword ptr [rax+rax+00h]
0x14010e947  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x14010e951  jmp     loc_14010EA0D
0x14010e956  mov     rcx, rdi; struct VIDMM_PARTITION *
0x14010e959  call    ?InitializePartitionForAllAdapters@VIDMM_GLOBAL@@SAJPEAUVIDMM_PARTITION@@@Z; VIDMM_GLOBAL::InitializePartitionForAllAdapters(VIDMM_PARTITION *)
0x14010e95e  mov     esi, eax
0x14010e960  test    eax, eax
0x14010e962  jns     short loc_14010E984
0x14010e964  mov     ecx, 3
0x14010e969  call    cs:__imp_WdLogSingleEntry0
0x14010e970  nop     dword ptr [rax+rax+00h]
0x14010e975  mov     cs:WdLogGlobalForLineNumber, 0E5h
0x14010e97f  jmp     loc_14010EA0D
0x14010e984  mov     rax, r12
0x14010e987  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14010e98b  jz      loc_14010EA21
0x14010e991  mov     r8, cs:__imp_PsPartitionType
0x14010e998  lea     rax, [rsp+1F0h+var_198]
0x14010e99d  mov     [rsp+1F0h+HandleInformation], r12; HandleInformation
0x14010e9a2  xor     r9d, r9d; AccessMode
0x14010e9a5  xor     edx, edx; DesiredAccess
0x14010e9a7  mov     [rsp+1F0h+var_198], r12
0x14010e9ac  mov     rcx, r14; Handle
0x14010e9af  mov     [rsp+1F0h+Object], rax; Object
0x14010e9b4  mov     r8, [r8]; ObjectType
0x14010e9b7  call    cs:__imp_ObReferenceObjectByHandle
0x14010e9be  nop     dword ptr [rax+rax+00h]
0x14010e9c3  movsxd  rsi, eax
0x14010e9c6  test    eax, eax
0x14010e9c8  jns     short loc_14010EA1C
0x14010e9ca  mov     rdx, rsi
0x14010e9cd  mov     ecx, 1
0x14010e9d2  call    cs:__imp_WdLogSingleEntry1
0x14010e9d9  nop     dword ptr [rax+rax+00h]
0x14010e9de  mov     [rsp+1F0h+var_1B8], r12
0x14010e9e3  lea     r9, aFailedToRefere_0; "Failed to reference partition object, S"...
0x14010e9ea  mov     [rsp+1F0h+var_1C0], r12
0x14010e9ef  mov     edx, 40000h
0x14010e9f4  mov     [rsp+1F0h+HandleInformation], r12
0x14010e9f9  mov     [rsp+1F0h+Object], rsi
0x14010e9fe  mov     cs:WdLogGlobalForLineNumber, 0EFh
0x14010ea08  call    DxgkLogInternalTriageEvent
0x14010ea0d  lea     rcx, [rsp+1F0h+var_190]; this
0x14010ea12  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x14010ea17  jmp     loc_14010EAA9
0x14010ea1c  mov     rax, [rsp+1F0h+var_198]
0x14010ea21  mov     [rdi+18h], rax
0x14010ea25  mov     eax, [rdi+48h]
0x14010ea28  and     eax, 0FFFFFFFEh
0x14010ea2b  or      eax, r15d
0x14010ea2e  mov     r15d, [rdi+20h]
0x14010ea32  mov     [rdi+48h], eax
0x14010ea35  mov     rbx, cs:?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x14010ea3c  test    rbx, rbx
0x14010ea3f  jz      short loc_14010EA6B
0x14010ea41  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x14010ea44  mov     rcx, r15; void *
0x14010ea47  call    ?CompareVidMmPartitionById@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; CompareVidMmPartitionById(void *,_RTL_BALANCED_NODE *)
0x14010ea4c  test    eax, eax
0x14010ea4e  js      short loc_14010EA5E
0x14010ea50  mov     rax, [rbx+8]
0x14010ea54  test    rax, rax
0x14010ea57  jnz     short loc_14010EA66
0x14010ea59  mov     r8b, 1
0x14010ea5c  jmp     short loc_14010EA6E
0x14010ea5e  mov     rax, [rbx]
0x14010ea61  test    rax, rax
0x14010ea64  jz      short loc_14010EA6B
0x14010ea66  mov     rbx, rax
0x14010ea69  jmp     short loc_14010EA41
0x14010ea6b  mov     r8b, r12b
0x14010ea6e  mov     r9, rdi
0x14010ea71  lea     rcx, ?_PartitionTree@VIDMM_PARTITION@@2U_RTL_AVL_TREE@@A; _RTL_AVL_TREE VIDMM_PARTITION::_PartitionTree
0x14010ea78  mov     rdx, rbx
0x14010ea7b  call    cs:__imp_RtlAvlInsertNodeEx
0x14010ea82  nop     dword ptr [rax+rax+00h]
0x14010ea87  lock inc dword ptr [rdi+24h]
0x14010ea8b  lea     rcx, [rsp+1F0h+var_190]; this
0x14010ea90  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x14010ea95  mov     [r13+158h], r14
0x14010ea9c  test    esi, esi
0x14010ea9e  jns     loc_14010EB26
0x14010eaa4  test    rdi, rdi
0x14010eaa7  jz      short loc_14010EB0F
0x14010eaa9  mov     rcx, rdi; this
0x14010eaac  call    ??_GVIDMM_PARTITION@@QEAAPEAXI@Z; VIDMM_PARTITION::`scalar deleting destructor'(uint)
0x14010eab1  mov     rdi, r12
0x14010eab4  jmp     short loc_14010EB0F
0x14010eab6  lock inc cs:dword_140086810
0x14010eabd  mov     ecx, 6
0x14010eac2  call    cs:__imp_WdLogSingleEntry0
0x14010eac9  nop     dword ptr [rax+rax+00h]
0x14010eace  mov     [rsp+1F0h+var_1B8], rsi
0x14010ead3  lea     r9, aCouldnTAllocat_56; "Couldn't allocate memory for vidmmparti"...
0x14010eada  mov     eax, 0D6h
0x14010eadf  mov     [rsp+1F0h+var_1C0], rsi
0x14010eae4  mov     [rsp+1F0h+HandleInformation], rsi
0x14010eae9  mov     edx, 40001h
0x14010eaee  mov     cs:WdLogGlobalForLineNumber, eax
0x14010eaf4  mov     [rsp+1F0h+Object], rax
0x14010eaf9  call    DxgkLogInternalTriageEvent
0x14010eafe  lea     rcx, [rsp+1F0h+var_190]; this
0x14010eb03  mov     esi, 0C0000017h
0x14010eb08  call    ??1DXGAUTOEXPUSHLOCK@@QEAA@XZ; DXGAUTOEXPUSHLOCK::~DXGAUTOEXPUSHLOCK(void)
0x14010eb0d  xor     edi, edi
0x14010eb0f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14010eb13  jz      short loc_14010EB26
0x14010eb15  xor     edx, edx; PreviousMode
0x14010eb17  mov     rcx, r14; Handle
0x14010eb1a  call    cs:__imp_ObCloseHandle
0x14010eb21  nop     dword ptr [rax+rax+00h]
0x14010eb26  mov     rax, [rsp+1F0h+var_178]
0x14010eb2b  mov     [rax], rdi
0x14010eb2e  mov     eax, esi
0x14010eb30  mov     rcx, [rbp+0F0h+var_38]
0x14010eb37  xor     rcx, rsp; StackCookie
0x14010eb3a  call    __security_check_cookie
0x14010eb3f  mov     rbx, [rsp+1F0h+arg_10]
0x14010eb47  add     rsp, 1C0h
0x14010eb4e  pop     r15
0x14010eb50  pop     r14
0x14010eb52  pop     r13
0x14010eb54  pop     r12
0x14010eb56  pop     rdi
0x14010eb57  pop     rsi
0x14010eb58  pop     rbp
0x14010eb59  retn
```
