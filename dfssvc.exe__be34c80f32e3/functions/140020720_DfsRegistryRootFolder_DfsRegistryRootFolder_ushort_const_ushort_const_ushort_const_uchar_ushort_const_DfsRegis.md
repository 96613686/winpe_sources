# DfsRegistryRootFolder::DfsRegistryRootFolder(ushort const *,ushort const *,ushort const *,uchar,ushort const *,DfsRegistryStore *,ulong *)

- ea: `0x140020720`
- end: `0x140020998`
- name: `??0DfsRegistryRootFolder@@QEAA@PEBG00E0PEAVDfsRegistryStore@@PEAK@Z`
- size: `632`
- prototype: `DfsRegistryRootFolder *(DfsRegistryRootFolder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, const unsigned __int16 *, struct DfsRegistryStore *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140021b80`
- `0x140024610`

## callees

- `0x140006bf0`
- `0x1400117c4`
- `0x140020720`
- `0x140026fdc`
- `0x14004a454`
- `0x1400586a8`
- `0x140058ce0`
- `0x140058db8`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1400208a8`
- `ntdll!RtlCompareUnicodeString` at `0x1400208a8`
- `ntdll!RtlInitUnicodeString` at `0x140020815`
- `ntdll!RtlInitUnicodeString` at `0x140020815`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400207e5`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400207e5`
- `ntdll!RtlNtStatusToDosError` at `0x1400207f3`
- `ntdll!RtlNtStatusToDosError` at `0x1400207f3`
- `RESUTILS!ResUtilEnumResources` at `0x14002084c`
- `RESUTILS!ResUtilEnumResources` at `0x14002084c`

## pseudocode

```c
DfsRegistryRootFolder *__fastcall DfsRegistryRootFolder::DfsRegistryRootFolder(
        DfsRegistryRootFolder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 a5,
        const unsigned __int16 *a6,
        struct DfsRegistryStore *a7,
        unsigned int *a8)
{
  ULONG UnicodeString; // edi
  unsigned int *v11; // rcx
  NTSTATUS inited; // eax
  _WORD *v13; // rax
  _WORD *v14; // rax
  char *v15; // rsi
  char *v16; // r14
  _WORD *v17; // rax
  struct CConfigurationSettings *Instance; // rax
  char *v19; // rcx
  char *p_pParameter; // rdx
  __int64 LocalMachineName; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  __int128 pParameter; // [rsp+50h] [rbp-20h] BYREF
  char *v25; // [rsp+60h] [rbp-10h]

  DfsRootFolder::DfsRootFolder(this, a2, a3, a4, a5, a6, 1179800132, a8);
  UnicodeString = *a8;
  *(_QWORD *)this = &DfsRegistryRootFolder::`vftable';
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 62) = a7;
  if ( a7 )
    _InterlockedIncrement((volatile signed __int32 *)a7 + 2);
  *((_QWORD *)this + 29) |= 1uLL;
  *((_DWORD *)this + 78) = 256;
  *((_DWORD *)this + 55) = 1;
  *((_DWORD *)this + 56) = 2;
  *((_BYTE *)this + 450) = 0;
  if ( UnicodeString )
    goto LABEL_25;
  if ( (unsigned int)DfsIsMachineCluster() )
  {
    DestinationString = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, a3);
    UnicodeString = RtlNtStatusToDosError(inited);
    if ( UnicodeString )
      goto LABEL_25;
    RtlInitUnicodeString((PUNICODE_STRING)this + 27, 0);
    v25 = (char *)this + 432;
    *(_QWORD *)&pParameter = (char *)this + 280;
    *((_QWORD *)&pParameter + 1) = &DestinationString;
    if ( (!ResUtilEnumResources(
             0,
             L"Distributed File System",
             (LPRESOURCE_CALLBACK)ClusterCallBackFunction,
             &pParameter)
       || *((_QWORD *)this + 55))
      && this != (DfsRegistryRootFolder *)-432LL )
    {
      if ( *((_WORD *)this + 216) )
      {
        v13 = (_WORD *)*((_QWORD *)this + 55);
        if ( v13 )
        {
          if ( *v13 )
          {
            *((_BYTE *)this + 450) = 1;
            if ( *(_BYTE *)CConfigurationSettings::_GetInstance(v11) )
            {
              if ( RtlCompareUnicodeString((PCUNICODE_STRING)this + 27, (PCUNICODE_STRING)((char *)this + 136), 1u) )
              {
                pParameter = 0;
                UnicodeString = DfsCreateUnicodeString(&pParameter, (char *)this + 432);
                if ( !UnicodeString )
                {
                  DfsFreeUnicodeString((char *)this + 136);
                  v14 = (_WORD *)((char *)this + 432);
                  v15 = (char *)this + 432;
                  *(_OWORD *)((char *)this + 136) = pParameter;
                  v16 = (char *)this + 432;
LABEL_17:
                  if ( *v14 )
                  {
                    v17 = (_WORD *)*((_QWORD *)this + 55);
                    if ( v17 )
                    {
                      if ( *v17 )
                        goto LABEL_25;
                    }
                  }
                  goto LABEL_20;
                }
              }
            }
          }
        }
      }
    }
  }
  v14 = (_WORD *)((char *)this + 432);
  v15 = (char *)this + 432;
  v16 = (char *)this + 432;
  if ( this != (DfsRegistryRootFolder *)-432LL )
    goto LABEL_17;
LABEL_20:
  if ( a5 )
  {
    Instance = CConfigurationSettings::_GetInstance(v11);
    v19 = v16;
    p_pParameter = (char *)this + (-(__int64)(*(_BYTE *)Instance != 0) & 0xFFFFFFFFFFFFFF70uLL) + 280;
LABEL_24:
    UnicodeString = DfsCreateUnicodeString(v19, p_pParameter);
    goto LABEL_25;
  }
  pParameter = 0;
  LocalMachineName = DfsGetLocalMachineName(3);
  UnicodeString = DfsRtlInitUnicodeStringEx(&pParameter, LocalMachineName);
  if ( !UnicodeString )
  {
    p_pParameter = (char *)&pParameter;
    v19 = v15;
    goto LABEL_24;
  }
LABEL_25:
  *a8 = UnicodeString;
  return this;
}

```

## disassembly

```asm
0x140020720  mov     r11, rsp
0x140020723  mov     [r11+8], rbx
0x140020727  mov     [r11+10h], rsi
0x14002072b  mov     [r11+18h], rdi
0x14002072f  push    rbp
0x140020730  push    r12
0x140020732  push    r13
0x140020734  push    r14
0x140020736  push    r15
0x140020738  mov     rbp, rsp
0x14002073b  sub     rsp, 70h
0x14002073f  mov     rax, [rbp+arg_28]
0x140020743  mov     rsi, r8
0x140020746  mov     r15, [rbp+arg_38]
0x14002074a  mov     rbx, rcx
0x14002074d  mov     r12b, [rbp+arg_20]
0x140020751  mov     [r11-60h], r15
0x140020755  mov     [rsp+70h+var_40], 46525244h
0x14002075d  mov     [r11-70h], rax
0x140020761  mov     [r11-78h], r12b
0x140020765  call    ??0DfsRootFolder@@QEAA@PEBG00E0W4DfsObjectTypeEnumeration@@PEAK@Z; DfsRootFolder::DfsRootFolder(ushort const *,ushort const *,ushort const *,uchar,ushort const *,DfsObjectTypeEnumeration,ulong *)
0x14002076a  mov     edi, [r15]
0x14002076d  lea     rax, ??_7DfsRegistryRootFolder@@6B@; const DfsRegistryRootFolder::`vftable'
0x140020774  xor     r13d, r13d
0x140020777  mov     [rbx], rax
0x14002077a  mov     rax, [rbp+arg_30]
0x14002077e  mov     [rbx+1F8h], r13d
0x140020785  mov     [rbx+1F0h], rax
0x14002078c  test    rax, rax
0x14002078f  jz      short loc_140020795
0x140020791  lock inc dword ptr [rax+8]
0x140020795  or      qword ptr [rbx+0E8h], 1
0x14002079d  mov     dword ptr [rbx+138h], 100h
0x1400207a7  mov     dword ptr [rbx+0DCh], 1
0x1400207b1  mov     dword ptr [rbx+0E0h], 2
0x1400207bb  mov     [rbx+1C2h], r13b
0x1400207c2  test    edi, edi
0x1400207c4  jnz     loc_140020973
0x1400207ca  call    ?DfsIsMachineCluster@@YAHXZ; DfsIsMachineCluster(void)
0x1400207cf  test    eax, eax
0x1400207d1  jz      loc_1400208F1
0x1400207d7  xorps   xmm0, xmm0
0x1400207da  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400207de  mov     rdx, rsi; SourceString
0x1400207e1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400207e5  call    cs:__imp_RtlInitUnicodeStringEx
0x1400207ec  nop     dword ptr [rax+rax+00h]
0x1400207f1  mov     ecx, eax; Status
0x1400207f3  call    cs:__imp_RtlNtStatusToDosError
0x1400207fa  nop     dword ptr [rax+rax+00h]
0x1400207ff  mov     edi, eax
0x140020801  test    eax, eax
0x140020803  jnz     loc_140020973
0x140020809  lea     rsi, [rbx+1B0h]
0x140020810  xor     edx, edx; SourceString
0x140020812  mov     rcx, rsi; DestinationString
0x140020815  call    cs:__imp_RtlInitUnicodeString
0x14002081c  nop     dword ptr [rax+rax+00h]
0x140020821  lea     rcx, [rbx+118h]
0x140020828  mov     [rbp+var_10], rsi
0x14002082c  mov     qword ptr [rbp+pParameter], rcx
0x140020830  lea     rax, [rbp+DestinationString]
0x140020834  xor     ecx, ecx; hSelf
0x140020836  mov     qword ptr [rbp+pParameter+8], rax
0x14002083a  lea     r9, [rbp+pParameter]; pParameter
0x14002083e  lea     r8, ?ClusterCallBackFunction@@YAKPEAU_HRESOURCE@@0PEAX@Z; pResCallBack
0x140020845  lea     rdx, szResTypeName; "Distributed File System"
0x14002084c  call    cs:__imp_ResUtilEnumResources
0x140020853  nop     dword ptr [rax+rax+00h]
0x140020858  test    eax, eax
0x14002085a  jz      short loc_140020866
0x14002085c  cmp     [rsi+8], r13
0x140020860  jz      loc_1400208F1
0x140020866  test    rsi, rsi
0x140020869  jz      loc_1400208F1
0x14002086f  cmp     [rsi], r13w
0x140020873  jz      short loc_1400208F1
0x140020875  mov     rax, [rbx+1B8h]
0x14002087c  test    rax, rax
0x14002087f  jz      short loc_1400208F1
0x140020881  cmp     [rax], r13w
0x140020885  jz      short loc_1400208F1
0x140020887  mov     byte ptr [rbx+1C2h], 1
0x14002088e  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x140020893  cmp     [rax], r13b
0x140020896  jz      short loc_1400208F1
0x140020898  lea     r14, [rbx+88h]
0x14002089f  mov     r8b, 1; CaseInsensitive
0x1400208a2  mov     rdx, r14; String2
0x1400208a5  mov     rcx, rsi; String1
0x1400208a8  call    cs:__imp_RtlCompareUnicodeString
0x1400208af  nop     dword ptr [rax+rax+00h]
0x1400208b4  test    eax, eax
0x1400208b6  jz      short loc_1400208F1
0x1400208b8  xorps   xmm0, xmm0
0x1400208bb  lea     rcx, [rbp+pParameter]
0x1400208bf  mov     rdx, rsi
0x1400208c2  movups  [rbp+pParameter], xmm0
0x1400208c6  call    DfsCreateUnicodeString
0x1400208cb  mov     edi, eax
0x1400208cd  test    eax, eax
0x1400208cf  jnz     short loc_1400208F1
0x1400208d1  mov     rcx, r14
0x1400208d4  call    DfsFreeUnicodeString
0x1400208d9  movups  xmm0, [rbp+pParameter]
0x1400208dd  lea     rax, [rbx+1B0h]
0x1400208e4  mov     rsi, rax
0x1400208e7  movdqu  xmmword ptr [r14], xmm0
0x1400208ec  mov     r14, rax
0x1400208ef  jmp     short loc_140020903
0x1400208f1  lea     rax, [rbx+1B0h]
0x1400208f8  mov     rsi, rax
0x1400208fb  mov     r14, rax
0x1400208fe  test    rax, rax
0x140020901  jz      short loc_14002091B
0x140020903  cmp     [rax], r13w
0x140020907  jz      short loc_14002091B
0x140020909  mov     rax, [rbx+1B8h]
0x140020910  test    rax, rax
0x140020913  jz      short loc_14002091B
0x140020915  cmp     [rax], r13w
0x140020919  jnz     short loc_140020973
0x14002091b  test    r12b, r12b
0x14002091e  jz      short loc_140020942
0x140020920  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x140020925  mov     rcx, r14
0x140020928  mov     dl, [rax]
0x14002092a  neg     dl
0x14002092c  sbb     rdx, rdx
0x14002092f  and     rdx, 0FFFFFFFFFFFFFF70h
0x140020936  add     rdx, 118h
0x14002093d  add     rdx, rbx
0x140020940  jmp     short loc_14002096C
0x140020942  xorps   xmm0, xmm0
0x140020945  mov     ecx, 3
0x14002094a  movups  [rbp+pParameter], xmm0
0x14002094e  call    ?DfsGetLocalMachineName@@YAPEBGW4DFS_HOST_NAME_TYPE@CLocalMachine@@@Z; DfsGetLocalMachineName(CLocalMachine::DFS_HOST_NAME_TYPE)
0x140020953  mov     rdx, rax
0x140020956  lea     rcx, [rbp+pParameter]
0x14002095a  call    DfsRtlInitUnicodeStringEx
0x14002095f  mov     edi, eax
0x140020961  test    eax, eax
0x140020963  jnz     short loc_140020973
0x140020965  lea     rdx, [rbp+pParameter]
0x140020969  mov     rcx, rsi
0x14002096c  call    DfsCreateUnicodeString
0x140020971  mov     edi, eax
0x140020973  lea     r11, [rsp+70h+var_s0]
0x140020978  mov     [r15], edi
0x14002097b  mov     rsi, [r11+38h]
0x14002097f  mov     rax, rbx
0x140020982  mov     rbx, [r11+30h]
0x140020986  mov     rdi, [r11+40h]
0x14002098a  mov     rsp, r11
0x14002098d  pop     r15
0x14002098f  pop     r14
0x140020991  pop     r13
0x140020993  pop     r12
0x140020995  pop     rbp
0x140020996  retn
```
