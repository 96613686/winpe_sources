# InternalDeleteDC

- ea: `0x180028550`
- end: `0x180028852`
- name: `InternalDeleteDC`
- size: `770`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x180028200`
- `0x180029e20`

## callees

- `0x180028550`
- `0x180032570`
- `0x180041ae0`
- `0x180041b00`
- `0x1800449c8`
- `0x180044b18`
- `0x180044b38`
- `0x180044b88`
- `0x180044d48`
- `0x180045c08`
- `0x1800564bc`
- `0x18005f9a0`
- `0x1800710c4`
- `0x180084e88`
- `0x1800a5010`

## import_xrefs

- `GDI32!AbortDoc` at `0x1800285af`
- `GDI32!AbortDoc` at `0x1800285af`
- `GDI32!bDeleteLDC` at `0x180028806`
- `GDI32!bDeleteLDC` at `0x180028806`
- `GDI32!vSetPldc` at `0x18002878b`
- `GDI32!vSetPldc` at `0x18002878b`
- `GDI32!GdiGetEntry` at `0x1800286da`
- `GDI32!GdiGetEntry` at `0x1800286da`
- `GDI32!fpClosePrinter` at `0x18002881f`
- `GDI32!ghICM` at `0x180028752`
- `GDI32!gW32PID` at `0x18002870f`
- `GDI32!gCookie` at `0x180028731`
- `GDI32!gMaxGdiHandleCount` at `0x1800286b8`
- `GDI32!pldcGet` at `0x180028588`
- `GDI32!pldcGet` at `0x1800286a4`
- `GDI32!pldcGet` at `0x180028588`
- `GDI32!pldcGet` at `0x1800286a4`
- `GDI32!GdiSetLastError` at `0x180028697`
- `GDI32!GdiSetLastError` at `0x180028697`
- `ntdll!RtlFreeHeap` at `0x18002861c`
- `ntdll!RtlFreeHeap` at `0x180028662`
- `ntdll!RtlFreeHeap` at `0x180028686`
- `ntdll!RtlFreeHeap` at `0x18002861c`
- `ntdll!RtlFreeHeap` at `0x180028662`
- `ntdll!RtlFreeHeap` at `0x180028686`
- `ntdll!RtlDecodePointer` at `0x180028829`
- `ntdll!RtlDecodePointer` at `0x180028829`
- `win32u!NtGdiDeleteObjectApp` at `0x180028794`
- `win32u!NtGdiDeleteObjectApp` at `0x180028794`

## pseudocode

```c
__int64 __fastcall InternalDeleteDC(HDC a1)
{
  void *v2; // r15
  unsigned int v3; // esi
  __int64 v4; // rax
  __int64 v5; // rbx
  void *v6; // r8
  void *v7; // r8
  void *v8; // r8
  unsigned int v10; // r14d
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rsi
  struct _UMPD *v14; // rdx
  void (__fastcall *v15)(void *); // rax
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+A0h] [rbp+40h] BYREF
  char v19; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  v3 = (unsigned int)a1 & 0x7F0000;
  if ( ((unsigned int)a1 & 0x7F0000) == 0x10000 )
  {
    v5 = pldcGet(a1);
  }
  else
  {
    v4 = pldcGet(a1);
    v5 = v4;
    if ( !v4 || v3 == 6684672 )
    {
      GdiSetLastError(6);
      return 0;
    }
    if ( (*(_BYTE *)(v4 + 8) & 0x40) != 0 )
      AbortDoc(a1);
    if ( *(_QWORD *)(v5 + 48) )
    {
      LdcGetUmpd(&v18, v5);
      DocumentEventEx((struct UmpdPtr *)&v18, *(void **)(v5 + 48), a1, 10, 0, 0, 0, 0);
      v2 = *(void **)(v5 + 48);
      *(_QWORD *)(v5 + 48) = 0;
      UmpdPtr::reset((UmpdPtr *)&v18, 0);
    }
    v6 = *(void **)(v5 + 24);
    if ( v6 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      *(_QWORD *)(v5 + 24) = 0;
    }
    vFreeUFIHashTable(*(_QWORD *)(v5 + 88), 0);
    vFreeUFIHashTable(*(_QWORD *)(v5 + 96), 0);
    vFreeUFIHashTable(*(_QWORD *)(v5 + 104), 1);
    v7 = *(void **)(v5 + 88);
    if ( v7 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      *(_QWORD *)(v5 + 88) = 0;
    }
    else
    {
      v8 = *(void **)(v5 + 104);
      if ( v8 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        *(_QWORD *)(v5 + 104) = 0;
      }
    }
  }
  v10 = 0;
  v11 = HANDLE_TO_INDEX(a1);
  if ( v11 < gMaxGdiHandleCount )
  {
    v17 = 0;
    v16 = 0;
    if ( (int)GdiGetEntry(v11, &v16) >= 0
      && BYTE14(v16) == 1
      && WORD6(v16) == WORD1(a1)
      && (DWORD2(v16) & 0xFFFFFFFE) == gW32PID )
    {
      if ( v17 )
      {
        v12 = __ROR8__(v17, 64 - (gCookie & 0x3Fu));
        v13 = v12 ^ gCookie;
        if ( v12 != gCookie )
        {
          if ( ghICM || *(_QWORD *)((v12 ^ gCookie) + 0x108) )
            IcmDeleteLocalDC(a1, v12 ^ gCookie, 0);
          if ( *(_QWORD *)(v13 + 352) )
            DeleteHDCCFont((struct _DC_ATTR *)v13);
          vSetPldc(a1, 0);
          v10 = NtGdiDeleteObjectApp(a1);
          if ( v10 && v5 )
          {
            LdcGetUmpd(&v18, v5);
            if ( (unsigned __int8)UmpdPtr::operator bool(&v18) )
            {
              wil::EnterCriticalSection(&v19, &semUMPD);
              UmpdPtr::assert((UmpdPtr *)&v18);
              _InterlockedIncrement((volatile signed __int32 *)(v18 + 44));
              LdcSetUmpd((struct _LDC *)v5, v14);
              UnloadUserModePrinterDriver((struct UmpdPtr *)&v18, 1, v2);
              wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
            }
            v10 = bDeleteLDC(v5);
            UmpdPtr::reset((UmpdPtr *)&v18, 0);
          }
          if ( v2 )
          {
            v15 = (void (__fastcall *)(void *))RtlDecodePointer(fpClosePrinter);
            v15(v2);
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180028550  mov     [rsp-38h+arg_10], rbx
0x180028555  push    rbp
0x180028556  push    rsi
0x180028557  push    rdi
0x180028558  push    r12
0x18002855a  push    r13
0x18002855c  push    r14
0x18002855e  push    r15
0x180028560  mov     rbp, rsp
0x180028563  sub     rsp, 60h
0x180028567  xor     r13d, r13d
0x18002856a  mov     eax, ecx
0x18002856c  and     eax, 7F0000h
0x180028571  mov     rdi, rcx
0x180028574  mov     r15d, r13d
0x180028577  mov     esi, eax
0x180028579  lea     r12d, [r13+40h]
0x18002857d  cmp     eax, 10000h
0x180028582  jz      loc_1800286A4
0x180028588  call    cs:__imp_pldcGet
0x18002858e  mov     rbx, rax
0x180028591  test    rax, rax
0x180028594  jz      loc_180028692
0x18002859a  cmp     esi, 660000h
0x1800285a0  jz      loc_180028692
0x1800285a6  test    [rax+8], r12b
0x1800285aa  jz      short loc_1800285B5
0x1800285ac  mov     rcx, rdi; hdc
0x1800285af  call    cs:__imp_AbortDoc
0x1800285b5  cmp     [rbx+30h], r13
0x1800285b9  jz      short loc_180028604
0x1800285bb  mov     rdx, rbx
0x1800285be  lea     rcx, [rbp+arg_0]
0x1800285c2  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x1800285c7  mov     rdx, [rbx+30h]; void *
0x1800285cb  lea     rcx, [rbp+arg_0]; this
0x1800285cf  mov     [rsp+60h+var_28], r13; void *
0x1800285d4  mov     r9d, 0Ah; int
0x1800285da  mov     [rsp+60h+var_30], r13d; unsigned int
0x1800285df  mov     r8, rdi; HDC
0x1800285e2  mov     [rsp+60h+var_38], r13; void *
0x1800285e7  mov     [rsp+60h+var_40], r13d; unsigned int
0x1800285ec  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x1800285f1  mov     r15, [rbx+30h]
0x1800285f5  lea     rcx, [rbp+arg_0]; this
0x1800285f9  xor     edx, edx; struct _UMPD *
0x1800285fb  mov     [rbx+30h], r13
0x1800285ff  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180028604  mov     r8, [rbx+18h]; P
0x180028608  test    r8, r8
0x18002860b  jz      short loc_180028626
0x18002860d  mov     rcx, gs:60h
0x180028616  xor     edx, edx; Flags
0x180028618  mov     rcx, [rcx+30h]; HeapHandle
0x18002861c  call    cs:__imp_RtlFreeHeap
0x180028622  mov     [rbx+18h], r13
0x180028626  mov     rcx, [rbx+58h]
0x18002862a  xor     edx, edx
0x18002862c  call    vFreeUFIHashTable
0x180028631  mov     rcx, [rbx+60h]
0x180028635  xor     edx, edx
0x180028637  call    vFreeUFIHashTable
0x18002863c  mov     rcx, [rbx+68h]
0x180028640  mov     edx, 1
0x180028645  call    vFreeUFIHashTable
0x18002864a  mov     r8, [rbx+58h]; P
0x18002864e  test    r8, r8
0x180028651  jz      short loc_18002866E
0x180028653  mov     rcx, gs:60h
0x18002865c  xor     edx, edx; Flags
0x18002865e  mov     rcx, [rcx+30h]; HeapHandle
0x180028662  call    cs:__imp_RtlFreeHeap
0x180028668  mov     [rbx+58h], r13
0x18002866c  jmp     short loc_1800286AD
0x18002866e  mov     r8, [rbx+68h]; P
0x180028672  test    r8, r8
0x180028675  jz      short loc_1800286AD
0x180028677  mov     rcx, gs:60h
0x180028680  xor     edx, edx; Flags
0x180028682  mov     rcx, [rcx+30h]; HeapHandle
0x180028686  call    cs:__imp_RtlFreeHeap
0x18002868c  mov     [rbx+68h], r13
0x180028690  jmp     short loc_1800286AD
0x180028692  mov     ecx, 6
0x180028697  call    cs:__imp_GdiSetLastError
0x18002869d  xor     eax, eax
0x18002869f  jmp     loc_18002883A
0x1800286a4  call    cs:__imp_pldcGet
0x1800286aa  mov     rbx, rax
0x1800286ad  mov     rcx, rdi
0x1800286b0  mov     r14d, r13d
0x1800286b3  call    HANDLE_TO_INDEX
0x1800286b8  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x1800286bf  cmp     eax, [rcx]
0x1800286c1  jnb     loc_180028837
0x1800286c7  xor     ecx, ecx
0x1800286c9  lea     rdx, [rbp+var_20]
0x1800286cd  mov     [rbp+var_10], rcx
0x1800286d1  xorps   xmm0, xmm0
0x1800286d4  mov     ecx, eax
0x1800286d6  movups  [rbp+var_20], xmm0
0x1800286da  call    cs:__imp_GdiGetEntry
0x1800286e0  test    eax, eax
0x1800286e2  js      loc_180028837
0x1800286e8  cmp     byte ptr [rbp+var_20+0Eh], 1
0x1800286ec  jnz     loc_180028837
0x1800286f2  movzx   eax, byte ptr [rbp+var_20+0Ch]
0x1800286f6  movzx   ecx, byte ptr [rbp+var_20+0Dh]
0x1800286fa  shl     cx, 8
0x1800286fe  or      cx, ax
0x180028701  mov     eax, edi
0x180028703  shr     eax, 10h
0x180028706  cmp     cx, ax
0x180028709  jnz     loc_180028837
0x18002870f  mov     rax, cs:__imp_gW32PID
0x180028716  mov     edx, dword ptr [rbp+var_20+8]
0x180028719  and     edx, 0FFFFFFFEh
0x18002871c  cmp     edx, [rax]
0x18002871e  jnz     loc_180028837
0x180028724  mov     rdx, [rbp+var_10]
0x180028728  test    rdx, rdx
0x18002872b  jz      loc_180028837
0x180028731  mov     rax, cs:__imp_gCookie
0x180028738  mov     rsi, [rax]
0x18002873b  mov     eax, esi
0x18002873d  and     eax, 3Fh
0x180028740  sub     r12d, eax
0x180028743  mov     cl, r12b
0x180028746  ror     rdx, cl
0x180028749  xor     rsi, rdx
0x18002874c  jz      loc_180028837
0x180028752  mov     rax, cs:__imp_ghICM
0x180028759  cmp     [rax], r13
0x18002875c  jnz     short loc_180028767
0x18002875e  cmp     [rsi+108h], r13
0x180028765  jz      short loc_180028775
0x180028767  xor     r8d, r8d
0x18002876a  mov     rdx, rsi
0x18002876d  mov     rcx, rdi
0x180028770  call    IcmDeleteLocalDC
0x180028775  cmp     [rsi+160h], r13
0x18002877c  jz      short loc_180028786
0x18002877e  mov     rcx, rsi; struct _DC_ATTR *
0x180028781  call    ?DeleteHDCCFont@@YAXPEAU_DC_ATTR@@@Z; DeleteHDCCFont(_DC_ATTR *)
0x180028786  xor     edx, edx
0x180028788  mov     rcx, rdi
0x18002878b  call    cs:__imp_vSetPldc
0x180028791  mov     rcx, rdi
0x180028794  call    cs:__imp_NtGdiDeleteObjectApp
0x18002879a  mov     r14d, eax
0x18002879d  test    eax, eax
0x18002879f  jz      short loc_18002881A
0x1800287a1  test    rbx, rbx
0x1800287a4  jz      short loc_18002881A
0x1800287a6  mov     rdx, rbx
0x1800287a9  lea     rcx, [rbp+arg_0]
0x1800287ad  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x1800287b2  lea     rcx, [rbp+arg_0]
0x1800287b6  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x1800287bb  test    al, al
0x1800287bd  jz      short loc_180028803
0x1800287bf  lea     rdx, semUMPD
0x1800287c6  lea     rcx, [rbp+arg_8]
0x1800287ca  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800287cf  lea     rcx, [rbp+arg_0]; this
0x1800287d3  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800287d8  mov     r8, [rbp+arg_0]
0x1800287dc  lock inc dword ptr [r8+2Ch]
0x1800287e1  mov     rcx, rbx; struct _LDC *
0x1800287e4  call    ?LdcSetUmpd@@YAXPEAU_LDC@@PEAU_UMPD@@@Z; LdcSetUmpd(_LDC *,_UMPD *)
0x1800287e9  mov     r8, r15; void *
0x1800287ec  lea     rcx, [rbp+arg_0]; this
0x1800287f0  mov     edx, 1; int
0x1800287f5  call    ?UnloadUserModePrinterDriver@@YAHAEAVUmpdPtr@@HPEAX@Z; UnloadUserModePrinterDriver(UmpdPtr &,int,void *)
0x1800287fa  lea     rcx, [rbp+arg_8]
0x1800287fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180028803  mov     rcx, rbx
0x180028806  call    cs:__imp_bDeleteLDC
0x18002880c  xor     edx, edx; struct _UMPD *
0x18002880e  lea     rcx, [rbp+arg_0]; this
0x180028812  mov     r14d, eax
0x180028815  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18002881a  test    r15, r15
0x18002881d  jz      short loc_180028837
0x18002881f  mov     rcx, cs:__imp_fpClosePrinter
0x180028826  mov     rcx, [rcx]; Pointer
0x180028829  call    cs:__imp_RtlDecodePointer
0x18002882f  mov     rcx, r15
0x180028832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028837  mov     eax, r14d
0x18002883a  mov     rbx, [rsp+60h+arg_10]
0x180028842  add     rsp, 60h
0x180028846  pop     r15
0x180028848  pop     r14
0x18002884a  pop     r13
0x18002884c  pop     r12
0x18002884e  pop     rdi
0x18002884f  pop     rsi
0x180028850  pop     rbp
0x180028851  retn
```
