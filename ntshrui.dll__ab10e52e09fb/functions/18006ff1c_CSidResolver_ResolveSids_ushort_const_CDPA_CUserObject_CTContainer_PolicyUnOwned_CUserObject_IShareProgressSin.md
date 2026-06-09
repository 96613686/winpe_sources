# CSidResolver::_ResolveSids(ushort const *,CDPA<CUserObject,CTContainer_PolicyUnOwned<CUserObject>> &,IShareProgressSink *)

- ea: `0x18006ff1c`
- end: `0x180070194`
- name: `?_ResolveSids@CSidResolver@@IEAAJPEBGAEAV?$CDPA@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@PEAUIShareProgressSink@@@Z`
- size: `632`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006f2b8`
- `0x18006ff1c`

## callees

- `0x18000f720`
- `0x180011e3c`
- `0x1800120e0`
- `0x18001d1dc`
- `0x18001d9a0`
- `0x1800645f4`
- `0x1800646ec`
- `0x18006f6a4`
- `0x18006faac`
- `0x18006fb34`
- `0x18006ff1c`
- `0x18007019c`
- `0x18007429c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070144`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007015b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007015b`
- `ntdll!RtlCreateUnicodeString` at `0x18006fff9`
- `ntdll!RtlCreateUnicodeString` at `0x18006fff9`
- `ntdll!RtlFreeUnicodeString` at `0x180070152`
- `ntdll!RtlFreeUnicodeString` at `0x180070152`
- `KERNEL32!lstrcmpiW` at `0x180070122`
- `KERNEL32!lstrcmpiW` at `0x180070122`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800700d3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800700dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800700d3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800700dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSidResolver::_ResolveSids(
        CSidResolver *a1,
        const WCHAR *a2,
        HDPA *a3,
        struct IShareProgressSink *a4)
{
  signed int DomainDcName; // edi
  HDPA v7; // rsi
  void **v8; // r12
  struct _UNICODE_STRING *p_DestinationString; // rcx
  __int64 i; // r14
  struct _UNICODE_STRING **Ptr; // rax
  struct _LSA_UNICODE_STRING *v12; // r14
  BOOLEAN v13; // al
  int v14; // eax
  CSidResolver *v15; // rcx
  CSidResolver *v16; // rcx
  struct IShareProgressSink *v17; // rsi
  INT_PTR v18; // rbx
  INT_PTR v19; // r12
  struct _DPA *v20; // rcx
  PVOID v21; // rax
  int appended; // eax
  struct CUserObject *v23; // rax
  CSidResolver *v24; // rcx
  WCHAR *v25; // rbx
  HDPA hdpaNew; // [rsp+30h] [rbp-40h] BYREF
  PVOID Buffer; // [rsp+38h] [rbp-38h] BYREF
  PVOID v29; // [rsp+40h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp-28h] BYREF
  INT_PTR v31; // [rsp+50h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF

  DomainDcName = 0;
  if ( !(unsigned int)CSidResolver::_ShouldCancel(a1, a4) )
  {
    hdpaNew = 0;
    if ( (unsigned int)CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(&hdpaNew, 3) )
    {
      v7 = *a3;
      if ( *a3 )
        LODWORD(v7) = *(_DWORD *)v7;
      v8 = 0;
      SourceString = 0;
      v29 = 0;
      v31 = (int)v7;
      DomainDcName = ULongLongMult((int)v7, 8u, (unsigned __int64 *)&v29);
      if ( DomainDcName >= 0 )
      {
        DomainDcName = CTCoAllocPolicy::Alloc(p_DestinationString, 1u, (unsigned __int64)v29, (void **)&SourceString);
        v8 = (void **)SourceString;
      }
      if ( DomainDcName >= 0 )
      {
        for ( i = 0; (int)i < (int)v7; i = (unsigned int)(i + 1) )
        {
          Ptr = (struct _UNICODE_STRING **)DPA_GetPtr(*a3, (unsigned int)i);
          p_DestinationString = *Ptr;
          v8[i] = *Ptr;
        }
        DestinationString = 0;
        v12 = 0;
        if ( a2 )
        {
          v13 = RtlCreateUnicodeString(&DestinationString, a2);
          p_DestinationString = &DestinationString;
          if ( !v13 )
            p_DestinationString = 0;
          v12 = (struct _LSA_UNICODE_STRING *)p_DestinationString;
        }
        Buffer = 0;
        v29 = 0;
        v14 = CSidResolver::_LookupSids(
                (CSidResolver *)p_DestinationString,
                v12,
                (struct _LSA_TRANSLATED_NAME **)&Buffer,
                (struct _LSA_REFERENCED_DOMAIN_LIST **)&v29,
                (ULONG)v7,
                v8);
        if ( !v14 || v14 == 263 )
        {
          v18 = 0;
          v17 = a4;
          v19 = v31;
          do
          {
            if ( (unsigned int)CSidResolver::_ShouldCancel(v15, a4) || v18 >= v19 )
              break;
            v20 = *a3;
            if ( *((_DWORD *)Buffer + 8 * v18) == 8 )
            {
              v21 = DPA_GetPtr(v20, v18);
              appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(&hdpaNew, v21);
            }
            else
            {
              v23 = (struct CUserObject *)DPA_GetPtr(v20, v18);
              appended = CSidResolver::_FillUserDetails(
                           v24,
                           (struct _LSA_TRANSLATED_NAME *)Buffer + v18,
                           (struct _LSA_REFERENCED_DOMAIN_LIST *)v29,
                           a2,
                           v23);
            }
            DomainDcName = appended;
            ++v18;
          }
          while ( appended >= 0 );
          LsaFreeMemory(Buffer);
          LsaFreeMemory(v29);
          v8 = (void **)SourceString;
        }
        else
        {
          DomainDcName = DPA_Clone(*a3, hdpaNew) == 0 ? 0x8007000E : 0;
          v17 = a4;
        }
        if ( DomainDcName >= 0 )
        {
          if ( hdpaNew )
          {
            if ( *(int *)hdpaNew > 0 )
            {
              SourceString = 0;
              DomainDcName = CSidResolver::_GetDomainDcName(v16, a2, (unsigned __int16 **)&SourceString);
              if ( DomainDcName >= 0 )
              {
                v25 = (WCHAR *)SourceString;
                if ( !a2 || lstrcmpiW(a2, SourceString) )
                  DomainDcName = CSidResolver::_ResolveSids(a1, v25, &hdpaNew, v17);
                LocalFree(v25);
              }
            }
          }
        }
        if ( v12 )
          RtlFreeUnicodeString((PUNICODE_STRING)v12);
        CoTaskMemFree(v8);
      }
      CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::Destroy(&hdpaNew);
    }
    else
    {
      DomainDcName = -2147024882;
    }
    CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::~CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>(&hdpaNew);
  }
  return (unsigned int)DomainDcName;
}

```

## disassembly

```asm
0x18006ff1c  mov     [rsp-38h+arg_8], rbx
0x18006ff21  mov     [rsp-38h+arg_18], r9
0x18006ff26  mov     [rsp-38h+arg_0], rcx
0x18006ff2b  push    rbp
0x18006ff2c  push    rsi
0x18006ff2d  push    rdi
0x18006ff2e  push    r12
0x18006ff30  push    r13
0x18006ff32  push    r14
0x18006ff34  push    r15
0x18006ff36  mov     rbp, rsp
0x18006ff39  sub     rsp, 70h
0x18006ff3d  mov     r13, r8
0x18006ff40  mov     r15, rdx
0x18006ff43  xor     edi, edi
0x18006ff45  mov     rdx, r9; struct IShareProgressSink *
0x18006ff48  call    ?_ShouldCancel@CSidResolver@@IEAAHPEAUIShareProgressSink@@@Z; CSidResolver::_ShouldCancel(IShareProgressSink *)
0x18006ff4d  test    eax, eax
0x18006ff4f  jnz     loc_18007017A
0x18006ff55  mov     [rbp+hdpaNew], rdi
0x18006ff59  lea     edx, [rdi+3]
0x18006ff5c  lea     rcx, [rbp+hdpaNew]
0x18006ff60  call    ?Create@?$CDPA_Base@UIUnknown@@V?$CTContainer_PolicyRelease@UIUnknown@@@@@@QEAAHH@Z; CDPA_Base<IUnknown,CTContainer_PolicyRelease<IUnknown>>::Create(int)
0x18006ff65  test    eax, eax
0x18006ff67  jz      loc_18007016C
0x18006ff6d  mov     rsi, [r13+0]
0x18006ff71  test    rsi, rsi
0x18006ff74  jz      short loc_18006FF78
0x18006ff76  mov     esi, [rsi]
0x18006ff78  xor     r12d, r12d
0x18006ff7b  mov     [rbp+SourceString], r12
0x18006ff7f  mov     [rbp+var_30], r12
0x18006ff83  movsxd  rax, esi
0x18006ff86  mov     [rbp+var_20], rax
0x18006ff8a  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18006ff8e  lea     edx, [r12+8]; unsigned __int64
0x18006ff93  mov     rcx, rax; unsigned __int64
0x18006ff96  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006ff9b  mov     edi, eax
0x18006ff9d  test    eax, eax
0x18006ff9f  js      short loc_18006FFB9
0x18006ffa1  lea     r9, [rbp+SourceString]; void **
0x18006ffa5  mov     r8, [rbp+var_30]; unsigned __int64
0x18006ffa9  lea     edx, [r12+1]; unsigned int
0x18006ffae  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18006ffb3  mov     edi, eax
0x18006ffb5  mov     r12, [rbp+SourceString]
0x18006ffb9  test    edi, edi
0x18006ffbb  js      loc_180070161
0x18006ffc1  xor     r14d, r14d
0x18006ffc4  test    esi, esi
0x18006ffc6  jle     short loc_18006FFE3
0x18006ffc8  mov     edx, r14d; i
0x18006ffcb  mov     rcx, [r13+0]; hdpa
0x18006ffcf  call    DPA_GetPtr
0x18006ffd4  mov     rcx, [rax]
0x18006ffd7  mov     [r12+r14*8], rcx
0x18006ffdb  inc     r14d
0x18006ffde  cmp     r14d, esi
0x18006ffe1  jl      short loc_18006FFC8
0x18006ffe3  xorps   xmm0, xmm0
0x18006ffe6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006ffea  xor     r14d, r14d
0x18006ffed  test    r15, r15
0x18006fff0  jz      short loc_18007000C
0x18006fff2  mov     rdx, r15; SourceString
0x18006fff5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006fff9  call    cs:__imp_RtlCreateUnicodeString
0x18006ffff  lea     rcx, [rbp+DestinationString]
0x180070003  test    al, al
0x180070005  cmovz   rcx, r14; this
0x180070009  mov     r14, rcx
0x18007000c  mov     [rbp+Buffer], 0
0x180070014  mov     [rbp+var_30], 0
0x18007001c  mov     [rsp+70h+var_48], r12; void **
0x180070021  mov     dword ptr [rsp+70h+var_50], esi; unsigned int
0x180070025  lea     r9, [rbp+var_30]; struct _LSA_REFERENCED_DOMAIN_LIST **
0x180070029  lea     r8, [rbp+Buffer]; struct _LSA_TRANSLATED_NAME **
0x18007002d  mov     rdx, r14; struct _UNICODE_STRING *
0x180070030  call    ?_LookupSids@CSidResolver@@AEAAJPEAU_UNICODE_STRING@@PEAPEAU_LSA_TRANSLATED_NAME@@PEAPEAU_LSA_REFERENCED_DOMAIN_LIST@@KPEAPEAX@Z; CSidResolver::_LookupSids(_UNICODE_STRING *,_LSA_TRANSLATED_NAME * *,_LSA_REFERENCED_DOMAIN_LIST * *,ulong,void * *)
0x180070035  test    eax, eax
0x180070037  jz      short loc_180070063
0x180070039  cmp     eax, 107h
0x18007003e  jz      short loc_180070063
0x180070040  mov     rdx, [rbp+hdpaNew]; hdpaNew
0x180070044  mov     rcx, [r13+0]; hdpa
0x180070048  call    DPA_Clone
0x18007004d  neg     rax
0x180070050  sbb     edi, edi
0x180070052  not     edi
0x180070054  and     edi, 8007000Eh
0x18007005a  mov     rsi, [rbp+arg_18]
0x18007005e  jmp     loc_1800700E7
0x180070063  xor     ebx, ebx
0x180070065  mov     rsi, [rbp+arg_18]
0x180070069  mov     r12, [rbp+var_20]
0x18007006d  mov     rdx, rsi; struct IShareProgressSink *
0x180070070  call    ?_ShouldCancel@CSidResolver@@IEAAHPEAUIShareProgressSink@@@Z; CSidResolver::_ShouldCancel(IShareProgressSink *)
0x180070075  test    eax, eax
0x180070077  jnz     short loc_1800700CF
0x180070079  cmp     rbx, r12
0x18007007c  jge     short loc_1800700CF
0x18007007e  mov     rdi, rbx
0x180070081  shl     rdi, 5
0x180070085  mov     rax, [rbp+Buffer]
0x180070089  mov     rdx, rbx; i
0x18007008c  mov     rcx, [r13+0]; hdpa
0x180070090  cmp     dword ptr [rdi+rax], 8
0x180070094  jnz     short loc_1800700A9
0x180070096  call    DPA_GetPtr
0x18007009b  mov     rdx, rax
0x18007009e  lea     rcx, [rbp+hdpaNew]
0x1800700a2  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x1800700a7  jmp     short loc_1800700C6
0x1800700a9  call    DPA_GetPtr
0x1800700ae  mov     rdx, [rbp+Buffer]
0x1800700b2  add     rdx, rdi; struct _LSA_TRANSLATED_NAME *
0x1800700b5  mov     [rsp+70h+var_50], rax; struct CUserObject *
0x1800700ba  mov     r9, r15; unsigned __int16 *
0x1800700bd  mov     r8, [rbp+var_30]; struct _LSA_REFERENCED_DOMAIN_LIST *
0x1800700c1  call    ?_FillUserDetails@CSidResolver@@IEAAJPEAU_LSA_TRANSLATED_NAME@@PEAU_LSA_REFERENCED_DOMAIN_LIST@@PEBGPEAVCUserObject@@@Z; CSidResolver::_FillUserDetails(_LSA_TRANSLATED_NAME *,_LSA_REFERENCED_DOMAIN_LIST *,ushort const *,CUserObject *)
0x1800700c6  mov     edi, eax
0x1800700c8  inc     rbx
0x1800700cb  test    eax, eax
0x1800700cd  jns     short loc_18007006D
0x1800700cf  mov     rcx, [rbp+Buffer]; Buffer
0x1800700d3  call    cs:__imp_LsaFreeMemory
0x1800700d9  mov     rcx, [rbp+var_30]; Buffer
0x1800700dd  call    cs:__imp_LsaFreeMemory
0x1800700e3  mov     r12, [rbp+SourceString]
0x1800700e7  test    edi, edi
0x1800700e9  js      short loc_18007014A
0x1800700eb  mov     rax, [rbp+hdpaNew]
0x1800700ef  test    rax, rax
0x1800700f2  jz      short loc_18007014A
0x1800700f4  cmp     dword ptr [rax], 0
0x1800700f7  jle     short loc_18007014A
0x1800700f9  mov     [rbp+SourceString], 0
0x180070101  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x180070105  mov     rdx, r15; unsigned __int16 *
0x180070108  call    ?_GetDomainDcName@CSidResolver@@IEAAJPEBGPEAPEAG@Z; CSidResolver::_GetDomainDcName(ushort const *,ushort * *)
0x18007010d  mov     edi, eax
0x18007010f  test    eax, eax
0x180070111  js      short loc_18007014A
0x180070113  mov     rbx, [rbp+SourceString]
0x180070117  test    r15, r15
0x18007011a  jz      short loc_18007012C
0x18007011c  mov     rdx, rbx; lpString2
0x18007011f  mov     rcx, r15; lpString1
0x180070122  call    cs:__imp_lstrcmpiW
0x180070128  test    eax, eax
0x18007012a  jz      short loc_180070141
0x18007012c  mov     r9, rsi
0x18007012f  lea     r8, [rbp+hdpaNew]
0x180070133  mov     rdx, rbx
0x180070136  mov     rcx, [rbp+arg_0]
0x18007013a  call    ?_ResolveSids@CSidResolver@@IEAAJPEBGAEAV?$CDPA@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@PEAUIShareProgressSink@@@Z; CSidResolver::_ResolveSids(ushort const *,CDPA<CUserObject,CTContainer_PolicyUnOwned<CUserObject>> &,IShareProgressSink *)
0x18007013f  mov     edi, eax
0x180070141  mov     rcx, rbx; hMem
0x180070144  call    cs:__imp_LocalFree
0x18007014a  test    r14, r14
0x18007014d  jz      short loc_180070158
0x18007014f  mov     rcx, r14; UnicodeString
0x180070152  call    cs:__imp_RtlFreeUnicodeString
0x180070158  mov     rcx, r12; pv
0x18007015b  call    cs:__imp_CoTaskMemFree
0x180070161  lea     rcx, [rbp+hdpaNew]
0x180070165  call    ?Destroy@?$CDPA_Base@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@QEAAHXZ; CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::Destroy(void)
0x18007016a  jmp     short loc_180070171
0x18007016c  mov     edi, 8007000Eh
0x180070171  lea     rcx, [rbp+hdpaNew]
0x180070175  call    ??1?$CDPA_Base@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@QEAA@XZ; CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::~CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>(void)
0x18007017a  mov     eax, edi
0x18007017c  mov     rbx, [rsp+70h+arg_8]
0x180070184  add     rsp, 70h
0x180070188  pop     r15
0x18007018a  pop     r14
0x18007018c  pop     r13
0x18007018e  pop     r12
0x180070190  pop     rdi
0x180070191  pop     rsi
0x180070192  pop     rbp
0x180070193  retn
```
