# InternalDeleteDC

- ea: `0x180031940`
- end: `0x180031c8b`
- name: `InternalDeleteDC`
- size: `843`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x1800315b0`
- `0x180033650`

## callees

- `0x180031940`
- `0x1800383a0`
- `0x18003e758`
- `0x18003e8c0`
- `0x18003e8e0`
- `0x18003e930`
- `0x18003eb04`
- `0x18003fa60`
- `0x1800410a4`
- `0x1800413f0`
- `0x18005b500`
- `0x180063f80`
- `0x1800756cc`
- `0x18008a020`
- `0x1800a8010`

## import_xrefs

- `GDI32!AbortDoc` at `0x1800319a5`
- `GDI32!AbortDoc` at `0x1800319a5`
- `GDI32!bDeleteLDC` at `0x180031c32`
- `GDI32!bDeleteLDC` at `0x180031c32`
- `GDI32!vSetPldc` at `0x180031bab`
- `GDI32!vSetPldc` at `0x180031bab`
- `GDI32!GdiGetEntry` at `0x180031af4`
- `GDI32!GdiGetEntry` at `0x180031af4`
- `GDI32!fpClosePrinter` at `0x180031c51`
- `GDI32!ghICM` at `0x180031b72`
- `GDI32!gW32PID` at `0x180031b2f`
- `GDI32!gCookie` at `0x180031b51`
- `GDI32!gMaxGdiHandleCount` at `0x180031ad2`
- `GDI32!pldcGet` at `0x180031978`
- `GDI32!pldcGet` at `0x180031ab8`
- `GDI32!pldcGet` at `0x180031978`
- `GDI32!pldcGet` at `0x180031ab8`
- `GDI32!GdiSetLastError` at `0x180031aa5`
- `GDI32!GdiSetLastError` at `0x180031aa5`
- `ntdll!RtlFreeHeap` at `0x180031a18`
- `ntdll!RtlFreeHeap` at `0x180031a64`
- `ntdll!RtlFreeHeap` at `0x180031a8e`
- `ntdll!RtlFreeHeap` at `0x180031a18`
- `ntdll!RtlFreeHeap` at `0x180031a64`
- `ntdll!RtlFreeHeap` at `0x180031a8e`
- `ntdll!RtlDecodePointer` at `0x180031c5b`
- `ntdll!RtlDecodePointer` at `0x180031c5b`
- `win32u!NtGdiDeleteObjectApp` at `0x180031bba`
- `win32u!NtGdiDeleteObjectApp` at `0x180031bba`

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
0x180031940  mov     [rsp-38h+arg_10], rbx
0x180031945  push    rbp
0x180031946  push    rsi
0x180031947  push    rdi
0x180031948  push    r12
0x18003194a  push    r13
0x18003194c  push    r14
0x18003194e  push    r15
0x180031950  mov     rbp, rsp
0x180031953  sub     rsp, 60h
0x180031957  xor     r13d, r13d
0x18003195a  mov     eax, ecx
0x18003195c  and     eax, 7F0000h
0x180031961  mov     rdi, rcx
0x180031964  mov     r15d, r13d
0x180031967  mov     esi, eax
0x180031969  lea     r12d, [r13+40h]
0x18003196d  cmp     eax, 10000h
0x180031972  jz      loc_180031AB8
0x180031978  call    cs:__imp_pldcGet
0x18003197f  nop     dword ptr [rax+rax+00h]
0x180031984  mov     rbx, rax
0x180031987  test    rax, rax
0x18003198a  jz      loc_180031AA0
0x180031990  cmp     esi, 660000h
0x180031996  jz      loc_180031AA0
0x18003199c  test    [rax+8], r12b
0x1800319a0  jz      short loc_1800319B1
0x1800319a2  mov     rcx, rdi; hdc
0x1800319a5  call    cs:__imp_AbortDoc
0x1800319ac  nop     dword ptr [rax+rax+00h]
0x1800319b1  cmp     [rbx+30h], r13
0x1800319b5  jz      short loc_180031A00
0x1800319b7  mov     rdx, rbx
0x1800319ba  lea     rcx, [rbp+arg_0]
0x1800319be  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x1800319c3  mov     rdx, [rbx+30h]; void *
0x1800319c7  lea     rcx, [rbp+arg_0]; this
0x1800319cb  mov     [rsp+60h+var_28], r13; void *
0x1800319d0  mov     r9d, 0Ah; int
0x1800319d6  mov     [rsp+60h+var_30], r13d; unsigned int
0x1800319db  mov     r8, rdi; HDC
0x1800319de  mov     [rsp+60h+var_38], r13; void *
0x1800319e3  mov     [rsp+60h+var_40], r13d; unsigned int
0x1800319e8  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x1800319ed  mov     r15, [rbx+30h]
0x1800319f1  lea     rcx, [rbp+arg_0]; this
0x1800319f5  xor     edx, edx; struct _UMPD *
0x1800319f7  mov     [rbx+30h], r13
0x1800319fb  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180031a00  mov     r8, [rbx+18h]; P
0x180031a04  test    r8, r8
0x180031a07  jz      short loc_180031A28
0x180031a09  mov     rcx, gs:60h
0x180031a12  xor     edx, edx; Flags
0x180031a14  mov     rcx, [rcx+30h]; HeapHandle
0x180031a18  call    cs:__imp_RtlFreeHeap
0x180031a1f  nop     dword ptr [rax+rax+00h]
0x180031a24  mov     [rbx+18h], r13
0x180031a28  mov     rcx, [rbx+58h]
0x180031a2c  xor     edx, edx
0x180031a2e  call    vFreeUFIHashTable
0x180031a33  mov     rcx, [rbx+60h]
0x180031a37  xor     edx, edx
0x180031a39  call    vFreeUFIHashTable
0x180031a3e  mov     rcx, [rbx+68h]
0x180031a42  mov     edx, 1
0x180031a47  call    vFreeUFIHashTable
0x180031a4c  mov     r8, [rbx+58h]; P
0x180031a50  test    r8, r8
0x180031a53  jz      short loc_180031A76
0x180031a55  mov     rcx, gs:60h
0x180031a5e  xor     edx, edx; Flags
0x180031a60  mov     rcx, [rcx+30h]; HeapHandle
0x180031a64  call    cs:__imp_RtlFreeHeap
0x180031a6b  nop     dword ptr [rax+rax+00h]
0x180031a70  mov     [rbx+58h], r13
0x180031a74  jmp     short loc_180031AC7
0x180031a76  mov     r8, [rbx+68h]; P
0x180031a7a  test    r8, r8
0x180031a7d  jz      short loc_180031AC7
0x180031a7f  mov     rcx, gs:60h
0x180031a88  xor     edx, edx; Flags
0x180031a8a  mov     rcx, [rcx+30h]; HeapHandle
0x180031a8e  call    cs:__imp_RtlFreeHeap
0x180031a95  nop     dword ptr [rax+rax+00h]
0x180031a9a  mov     [rbx+68h], r13
0x180031a9e  jmp     short loc_180031AC7
0x180031aa0  mov     ecx, 6
0x180031aa5  call    cs:__imp_GdiSetLastError
0x180031aac  nop     dword ptr [rax+rax+00h]
0x180031ab1  xor     eax, eax
0x180031ab3  jmp     loc_180031C72
0x180031ab8  call    cs:__imp_pldcGet
0x180031abf  nop     dword ptr [rax+rax+00h]
0x180031ac4  mov     rbx, rax
0x180031ac7  mov     rcx, rdi
0x180031aca  mov     r14d, r13d
0x180031acd  call    HANDLE_TO_INDEX
0x180031ad2  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180031ad9  cmp     eax, [rcx]
0x180031adb  jnb     loc_180031C6F
0x180031ae1  xor     ecx, ecx
0x180031ae3  lea     rdx, [rbp+var_20]
0x180031ae7  mov     [rbp+var_10], rcx
0x180031aeb  xorps   xmm0, xmm0
0x180031aee  mov     ecx, eax
0x180031af0  movups  [rbp+var_20], xmm0
0x180031af4  call    cs:__imp_GdiGetEntry
0x180031afb  nop     dword ptr [rax+rax+00h]
0x180031b00  test    eax, eax
0x180031b02  js      loc_180031C6F
0x180031b08  cmp     byte ptr [rbp+var_20+0Eh], 1
0x180031b0c  jnz     loc_180031C6F
0x180031b12  movzx   eax, byte ptr [rbp+var_20+0Ch]
0x180031b16  movzx   ecx, byte ptr [rbp+var_20+0Dh]
0x180031b1a  shl     cx, 8
0x180031b1e  or      cx, ax
0x180031b21  mov     eax, edi
0x180031b23  shr     eax, 10h
0x180031b26  cmp     cx, ax
0x180031b29  jnz     loc_180031C6F
0x180031b2f  mov     rax, cs:__imp_gW32PID
0x180031b36  mov     edx, dword ptr [rbp+var_20+8]
0x180031b39  and     edx, 0FFFFFFFEh
0x180031b3c  cmp     edx, [rax]
0x180031b3e  jnz     loc_180031C6F
0x180031b44  mov     rdx, [rbp+var_10]
0x180031b48  test    rdx, rdx
0x180031b4b  jz      loc_180031C6F
0x180031b51  mov     rax, cs:__imp_gCookie
0x180031b58  mov     rsi, [rax]
0x180031b5b  mov     eax, esi
0x180031b5d  and     eax, 3Fh
0x180031b60  sub     r12d, eax
0x180031b63  mov     cl, r12b
0x180031b66  ror     rdx, cl
0x180031b69  xor     rsi, rdx
0x180031b6c  jz      loc_180031C6F
0x180031b72  mov     rax, cs:__imp_ghICM
0x180031b79  cmp     [rax], r13
0x180031b7c  jnz     short loc_180031B87
0x180031b7e  cmp     [rsi+108h], r13
0x180031b85  jz      short loc_180031B95
0x180031b87  xor     r8d, r8d
0x180031b8a  mov     rdx, rsi
0x180031b8d  mov     rcx, rdi
0x180031b90  call    IcmDeleteLocalDC
0x180031b95  cmp     [rsi+160h], r13
0x180031b9c  jz      short loc_180031BA6
0x180031b9e  mov     rcx, rsi; struct _DC_ATTR *
0x180031ba1  call    ?DeleteHDCCFont@@YAXPEAU_DC_ATTR@@@Z; DeleteHDCCFont(_DC_ATTR *)
0x180031ba6  xor     edx, edx
0x180031ba8  mov     rcx, rdi
0x180031bab  call    cs:__imp_vSetPldc
0x180031bb2  nop     dword ptr [rax+rax+00h]
0x180031bb7  mov     rcx, rdi
0x180031bba  call    cs:__imp_NtGdiDeleteObjectApp
0x180031bc1  nop     dword ptr [rax+rax+00h]
0x180031bc6  mov     r14d, eax
0x180031bc9  test    eax, eax
0x180031bcb  jz      short loc_180031C4C
0x180031bcd  test    rbx, rbx
0x180031bd0  jz      short loc_180031C4C
0x180031bd2  mov     rdx, rbx
0x180031bd5  lea     rcx, [rbp+arg_0]
0x180031bd9  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x180031bde  lea     rcx, [rbp+arg_0]
0x180031be2  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x180031be7  test    al, al
0x180031be9  jz      short loc_180031C2F
0x180031beb  lea     rdx, semUMPD
0x180031bf2  lea     rcx, [rbp+arg_8]
0x180031bf6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180031bfb  lea     rcx, [rbp+arg_0]; this
0x180031bff  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180031c04  mov     r8, [rbp+arg_0]
0x180031c08  lock inc dword ptr [r8+2Ch]
0x180031c0d  mov     rcx, rbx; struct _LDC *
0x180031c10  call    ?LdcSetUmpd@@YAXPEAU_LDC@@PEAU_UMPD@@@Z; LdcSetUmpd(_LDC *,_UMPD *)
0x180031c15  mov     r8, r15; void *
0x180031c18  lea     rcx, [rbp+arg_0]; this
0x180031c1c  mov     edx, 1; int
0x180031c21  call    ?UnloadUserModePrinterDriver@@YAHAEAVUmpdPtr@@HPEAX@Z; UnloadUserModePrinterDriver(UmpdPtr &,int,void *)
0x180031c26  lea     rcx, [rbp+arg_8]
0x180031c2a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180031c2f  mov     rcx, rbx
0x180031c32  call    cs:__imp_bDeleteLDC
0x180031c39  nop     dword ptr [rax+rax+00h]
0x180031c3e  xor     edx, edx; struct _UMPD *
0x180031c40  lea     rcx, [rbp+arg_0]; this
0x180031c44  mov     r14d, eax
0x180031c47  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180031c4c  test    r15, r15
0x180031c4f  jz      short loc_180031C6F
0x180031c51  mov     rcx, cs:__imp_fpClosePrinter
0x180031c58  mov     rcx, [rcx]; Pointer
0x180031c5b  call    cs:__imp_RtlDecodePointer
0x180031c62  nop     dword ptr [rax+rax+00h]
0x180031c67  mov     rcx, r15
0x180031c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c6f  mov     eax, r14d
0x180031c72  mov     rbx, [rsp+60h+arg_10]
0x180031c7a  add     rsp, 60h
0x180031c7e  pop     r15
0x180031c80  pop     r14
0x180031c82  pop     r13
0x180031c84  pop     r12
0x180031c86  pop     rdi
0x180031c87  pop     rsi
0x180031c88  pop     rbp
0x180031c89  retn
```
