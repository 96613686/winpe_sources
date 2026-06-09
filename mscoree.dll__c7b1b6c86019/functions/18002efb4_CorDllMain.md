# _CorDllMain

- ea: `0x18002efb4`
- end: `0x18002f1d4`
- name: `_CorDllMain`
- size: `544`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001a90`

## callees

- `0x180003d50`
- `0x1800226f0`
- `0x180029a34`
- `0x18002a600`
- `0x18002a7f4`
- `0x18002a834`
- `0x18002efb4`
- `0x18002f4d4`
- `0x1800393f0`
- `0x18003cc9c`
- `0x18003d3c4`
- `0x18003e0e0`
- `0x18003e128`
- `0x18003e164`
- `0x18003e280`
- `0x180045020`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002f177`
- `KERNEL32!EnterCriticalSection` at `0x18002f177`
- `KERNEL32!LeaveCriticalSection` at `0x18002f1bb`
- `KERNEL32!LeaveCriticalSection` at `0x18002f1bb`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18002f09e`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18002f09e`

## pseudocode

```c
__int64 __fastcall CorDllMain(HINSTANCE a1, unsigned int a2, void *a3)
{
  __int64 v6; // rdx
  int v7; // esi
  int ThunkUseState; // eax
  unsigned int v9; // edi
  struct IMAGE_COR20_HEADER *CorHeader; // rax
  __int64 (__fastcall *RvaData)(HINSTANCE, _QWORD, void *); // rax
  int v12; // ecx
  struct VTableBootstrapThunkChunk **i; // rcx
  struct VTableBootstrapThunkChunk **v14; // rbx
  void *ProcessExecutableHeap; // rax
  _QWORD v17[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v18; // [rsp+30h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-18h]
  char v20; // [rsp+A8h] [rbp+50h] BYREF

  v17[0] = 0;
  v17[1] = 0;
  v19 = 0;
  v18 = 0;
  if ( (int)PEDecoder::Init((PEDecoder *)v17, a1, (bool)a3) < 0 )
    return 0;
  v7 = 0;
  if ( a2 )
  {
    if ( qword_180061DB0 )
      goto LABEL_6;
    ThunkUseState = GetThunkUseState(v6);
    if ( ThunkUseState == 3 )
      return 0;
    if ( ThunkUseState == 2 )
LABEL_6:
      v7 = 1;
    if ( a2 != 1 )
      goto LABEL_17;
    if ( !*(_QWORD *)PEDecoder::CheckFormat(v17, &v20)
      && (unsigned int)PEDecoder::HasNTHeaders((PEDecoder *)v17)
      && (unsigned int)PEDecoder::HasDirectoryEntry((PEDecoder *)v17, 14) )
    {
      if ( (PEDecoder::GetCorHeader((PEDecoder *)v17)->Flags & 1) != 0
        || !(unsigned int)PEDecoder::HasManagedEntryPoint((PEDecoder *)v17)
        && !(unsigned int)PEDecoder::HasNativeEntryPoint((PEDecoder *)v17) )
      {
        DisableThreadLibraryCalls(a1);
      }
      if ( !v7 || (unsigned int)PatchVTableEntriesForDLLAttach((struct PEDecoder *)v17) )
        goto LABEL_17;
    }
    return 0;
  }
LABEL_17:
  v9 = 1;
  if ( (unsigned int)PEDecoder::HasNativeEntryPoint((PEDecoder *)v17) )
  {
    CorHeader = PEDecoder::GetCorHeader((PEDecoder *)v17);
    RvaData = (__int64 (__fastcall *)(HINSTANCE, _QWORD, void *))PEDecoder::GetRvaData(v17, CorHeader->EntryPointToken);
    v9 = RvaData(a1, a2, a3);
  }
  if ( a2 )
  {
    if ( v9 )
    {
      v12 = dword_18005FEB8;
      if ( dword_18005FEB8 == -1 )
      {
        v12 = CLRConfig::GetConfigValue((const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_IJWEntrypointCompatMode) != 0;
        dword_18005FEB8 = v12;
      }
      if ( v12 && (unsigned int)PEDecoder::HasManagedEntryPoint((PEDecoder *)v17) || a2 == 1 && !v7 )
        return (unsigned int)ShellShim_CorDllMainWorker(a1, a2, 0);
    }
  }
  else
  {
    v9 = ShellShim_CorDllMainWorker(a1, 0, a3);
    if ( (PEDecoder::GetCorHeader((PEDecoder *)v17)->Flags & 1) == 0 )
    {
      EnterCriticalSection(&g_chunkLock);
      for ( i = &g_pVTableBootstrapThunkChunkList; ; i = v14 + 2 )
      {
        v14 = (struct VTableBootstrapThunkChunk **)*i;
        if ( !*i )
          break;
        if ( *v14 == (struct VTableBootstrapThunkChunk *)v17[0] )
        {
          *i = v14[2];
          ProcessExecutableHeap = ClrGetProcessExecutableHeap();
          ClrHeapFree(ProcessExecutableHeap, 0, v14);
          break;
        }
      }
      LeaveCriticalSection(&g_chunkLock);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18002efb4  push    rbp
0x18002efb6  push    rbx
0x18002efb7  push    rsi
0x18002efb8  push    rdi
0x18002efb9  push    r14
0x18002efbb  push    r15
0x18002efbd  mov     rbp, rsp
0x18002efc0  sub     rsp, 58h
0x18002efc4  mov     ebx, edx
0x18002efc6  mov     [rbp+var_38], 0
0x18002efce  mov     rdx, rcx; void *
0x18002efd1  mov     [rbp+var_30], 0
0x18002efd9  mov     r14, rcx
0x18002efdc  mov     [rbp+var_18], 0
0x18002efe4  xorps   xmm0, xmm0
0x18002efe7  lea     rcx, [rbp+var_38]; this
0x18002efeb  mov     r15, r8
0x18002efee  movdqu  [rbp+var_28], xmm0
0x18002eff3  call    ?Init@PEDecoder@@QEAAJPEAX_N@Z; PEDecoder::Init(void *,bool)
0x18002eff8  test    eax, eax
0x18002effa  js      loc_18002F1C5
0x18002f000  xor     esi, esi
0x18002f002  test    ebx, ebx
0x18002f004  jz      loc_18002F0B9
0x18002f00a  cmp     cs:qword_180061DB0, rsi
0x18002f011  jnz     short loc_18002F029
0x18002f013  mov     rcx, rdx
0x18002f016  call    ?GetThunkUseState@@YA?AW4ThunkUse@@PEAUHINSTANCE__@@@Z; GetThunkUseState(HINSTANCE__ *)
0x18002f01b  cmp     eax, 3
0x18002f01e  jz      loc_18002F1C5
0x18002f024  cmp     eax, 2
0x18002f027  jnz     short loc_18002F02E
0x18002f029  mov     esi, 1
0x18002f02e  cmp     ebx, 1
0x18002f031  jnz     loc_18002F0B9
0x18002f037  lea     rdx, [rbp+arg_18]
0x18002f03b  lea     rcx, [rbp+var_38]
0x18002f03f  call    ?CheckFormat@PEDecoder@@QEBA?AVCHECK@@XZ; PEDecoder::CheckFormat(void)
0x18002f044  cmp     qword ptr [rax], 0
0x18002f048  jnz     loc_18002F1C5
0x18002f04e  lea     rcx, [rbp+var_38]; this
0x18002f052  call    ?HasNTHeaders@PEDecoder@@QEBAHXZ; PEDecoder::HasNTHeaders(void)
0x18002f057  test    eax, eax
0x18002f059  jz      loc_18002F1C5
0x18002f05f  lea     edx, [rbx+0Dh]; int
0x18002f062  lea     rcx, [rbp+var_38]; this
0x18002f066  call    ?HasDirectoryEntry@PEDecoder@@QEBAHH@Z; PEDecoder::HasDirectoryEntry(int)
0x18002f06b  test    eax, eax
0x18002f06d  jz      loc_18002F1C5
0x18002f073  lea     rcx, [rbp+var_38]; this
0x18002f077  call    ?GetCorHeader@PEDecoder@@QEBAPEAUIMAGE_COR20_HEADER@@XZ; PEDecoder::GetCorHeader(void)
0x18002f07c  test    [rax+10h], bl
0x18002f07f  jnz     short loc_18002F09B
0x18002f081  lea     rcx, [rbp+var_38]; this
0x18002f085  call    ?HasManagedEntryPoint@PEDecoder@@QEBAHXZ; PEDecoder::HasManagedEntryPoint(void)
0x18002f08a  test    eax, eax
0x18002f08c  jnz     short loc_18002F0A4
0x18002f08e  lea     rcx, [rbp+var_38]; this
0x18002f092  call    ?HasNativeEntryPoint@PEDecoder@@QEBAHXZ; PEDecoder::HasNativeEntryPoint(void)
0x18002f097  test    eax, eax
0x18002f099  jnz     short loc_18002F0A4
0x18002f09b  mov     rcx, r14; hLibModule
0x18002f09e  call    cs:__imp_DisableThreadLibraryCalls
0x18002f0a4  test    esi, esi
0x18002f0a6  jz      short loc_18002F0B9
0x18002f0a8  lea     rcx, [rbp+var_38]; this
0x18002f0ac  call    ?PatchVTableEntriesForDLLAttach@@YAHPEAVPEDecoder@@@Z; PatchVTableEntriesForDLLAttach(PEDecoder *)
0x18002f0b1  test    eax, eax
0x18002f0b3  jz      loc_18002F1C5
0x18002f0b9  lea     rcx, [rbp+var_38]; this
0x18002f0bd  mov     edi, 1
0x18002f0c2  call    ?HasNativeEntryPoint@PEDecoder@@QEBAHXZ; PEDecoder::HasNativeEntryPoint(void)
0x18002f0c7  test    eax, eax
0x18002f0c9  jz      short loc_18002F0EF
0x18002f0cb  lea     rcx, [rbp+var_38]; this
0x18002f0cf  call    ?GetCorHeader@PEDecoder@@QEBAPEAUIMAGE_COR20_HEADER@@XZ; PEDecoder::GetCorHeader(void)
0x18002f0d4  lea     rcx, [rbp+var_38]
0x18002f0d8  mov     edx, [rax+14h]
0x18002f0db  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18002f0e0  mov     r8, r15
0x18002f0e3  mov     edx, ebx
0x18002f0e5  mov     rcx, r14
0x18002f0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0ed  mov     edi, eax
0x18002f0ef  test    ebx, ebx
0x18002f0f1  jz      short loc_18002F152
0x18002f0f3  test    edi, edi
0x18002f0f5  jz      loc_18002F1C1
0x18002f0fb  mov     ecx, cs:dword_18005FEB8
0x18002f101  cmp     ecx, 0FFFFFFFFh
0x18002f104  jnz     short loc_18002F11F
0x18002f106  lea     rcx, ?EXTERNAL_IJWEntrypointCompatMode@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18002f10d  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &)
0x18002f112  xor     ecx, ecx
0x18002f114  test    eax, eax
0x18002f116  setnz   cl
0x18002f119  mov     cs:dword_18005FEB8, ecx
0x18002f11f  test    ecx, ecx
0x18002f121  jz      short loc_18002F130
0x18002f123  lea     rcx, [rbp+var_38]; this
0x18002f127  call    ?HasManagedEntryPoint@PEDecoder@@QEBAHXZ; PEDecoder::HasManagedEntryPoint(void)
0x18002f12c  test    eax, eax
0x18002f12e  jnz     short loc_18002F141
0x18002f130  cmp     ebx, 1
0x18002f133  jnz     loc_18002F1C1
0x18002f139  test    esi, esi
0x18002f13b  jnz     loc_18002F1C1
0x18002f141  xor     r8d, r8d; void *
0x18002f144  mov     edx, ebx; unsigned int
0x18002f146  mov     rcx, r14; HINSTANCE
0x18002f149  call    ?ShellShim_CorDllMainWorker@@YAHPEAUHINSTANCE__@@KPEAX@Z; ShellShim_CorDllMainWorker(HINSTANCE__ *,ulong,void *)
0x18002f14e  mov     edi, eax
0x18002f150  jmp     short loc_18002F1C1
0x18002f152  mov     r8, r15; void *
0x18002f155  xor     edx, edx; unsigned int
0x18002f157  mov     rcx, r14; HINSTANCE
0x18002f15a  call    ?ShellShim_CorDllMainWorker@@YAHPEAUHINSTANCE__@@KPEAX@Z; ShellShim_CorDllMainWorker(HINSTANCE__ *,ulong,void *)
0x18002f15f  lea     rcx, [rbp+var_38]; this
0x18002f163  mov     edi, eax
0x18002f165  call    ?GetCorHeader@PEDecoder@@QEBAPEAUIMAGE_COR20_HEADER@@XZ; PEDecoder::GetCorHeader(void)
0x18002f16a  test    byte ptr [rax+10h], 1
0x18002f16e  jnz     short loc_18002F1C1
0x18002f170  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f177  call    cs:__imp_EnterCriticalSection
0x18002f17d  mov     rdx, [rbp+var_38]
0x18002f181  lea     rcx, ?g_pVTableBootstrapThunkChunkList@@3PEAVVTableBootstrapThunkChunk@@EA; VTableBootstrapThunkChunk * g_pVTableBootstrapThunkChunkList
0x18002f188  mov     rbx, [rcx]
0x18002f18b  test    rbx, rbx
0x18002f18e  jz      short loc_18002F1B4
0x18002f190  cmp     [rbx], rdx
0x18002f193  jz      short loc_18002F19B
0x18002f195  lea     rcx, [rbx+10h]
0x18002f199  jmp     short loc_18002F188
0x18002f19b  mov     rax, [rbx+10h]
0x18002f19f  mov     [rcx], rax
0x18002f1a2  call    ?ClrGetProcessExecutableHeap@@YAPEAXXZ; ClrGetProcessExecutableHeap(void)
0x18002f1a7  mov     rcx, rax; void *
0x18002f1aa  mov     r8, rbx; void *
0x18002f1ad  xor     edx, edx; unsigned int
0x18002f1af  call    ?ClrHeapFree@@YAHPEAXK0@Z; ClrHeapFree(void *,ulong,void *)
0x18002f1b4  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f1bb  call    cs:__imp_LeaveCriticalSection
0x18002f1c1  mov     eax, edi
0x18002f1c3  jmp     short loc_18002F1C7
0x18002f1c5  xor     eax, eax
0x18002f1c7  add     rsp, 58h
0x18002f1cb  pop     r15
0x18002f1cd  pop     r14
0x18002f1cf  pop     rdi
0x18002f1d0  pop     rsi
0x18002f1d1  pop     rbx
0x18002f1d2  pop     rbp
0x18002f1d3  retn
```
