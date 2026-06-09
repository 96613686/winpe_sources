# LkmdTelCreateReport

- ea: `0x140846598`
- end: `0x1408467e5`
- name: `LkmdTelCreateReport`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1407f36ec`

## callees

- `0x14020fe90`
- `0x140394820`
- `0x1403f4ae8`
- `0x14053b3d0`
- `0x1406d9d70`
- `0x1406f4880`
- `0x140846598`
- `0x1408468c8`
- `0x140bae320`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x1408466a9`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x1408466a9`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x1408466f2`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x1408466f2`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x14084671e`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x14084671e`

## string_xrefs

- `0x1408466bf`: `LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n`

## pseudocode

```c
wchar_t *__fastcall LkmdTelCreateReport(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  wchar_t *PoolWithTag; // rax
  wchar_t *v9; // rbx
  wchar_t *v10; // rsi
  PVOID v11; // rax
  PVOID v12; // rdi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v17; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&ContextRecord, 0, sizeof(ContextRecord));
  v19 = 0;
  v18 = 0;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x74614454u);
  v9 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset_0(PoolWithTag, 0, 0x88u);
    v10 = v9;
LABEL_5:
    v11 = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x40000u, 0x74614454u);
    v12 = v11;
    if ( ExPoolZeroingNativelySupported || !v11 )
    {
      *(_QWORD *)v9 = v11;
      if ( !v11 )
      {
LABEL_12:
        if ( *(_QWORD *)v9 )
          ((void (*)(void))LkmdTelpFreeMem)();
        LkmdTelpFreeMem(v9);
        v10 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      memset_0(v11, 0, 0x40000u);
      *(_QWORD *)v9 = v12;
    }
    if ( RtlStringCbPrintfW(v9 + 52, 0x20u, L"%ws", L"WHEA") >= 0 )
    {
      v18 = 1;
      v13 = WerLiveKernelCreateReport(v9 + 52, &v18, &v19);
      if ( v13 >= 0 )
      {
        if ( v18 )
        {
          *((_QWORD *)v9 + 12) = v19;
          RtlCaptureContext(&ContextRecord);
          v17 = KeCapturePersistentThreadState(&ContextRecord, 0, 292, a3, a4, a5, a6, *(_QWORD *)v9);
          if ( v17 )
          {
            *((_DWORD *)v9 + 2) = v17;
            return v10;
          }
        }
        else
        {
          DbgPrintEx(5u, 1u, "LKMDTEL: WerPolicy is WerLiveKernelPolicyNoDump, no dump is allowed.\n");
        }
      }
      else
      {
        DbgPrintEx(5u, 0, "LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n", v13);
      }
    }
    goto LABEL_12;
  }
  v10 = PoolWithTag;
  if ( PoolWithTag )
    goto LABEL_5;
LABEL_15:
  if ( v19 )
  {
    v14 = WerLiveKernelCancelReport();
    if ( v14 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v14);
    v15 = WerLiveKernelCloseHandle(v19);
    if ( v15 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v15);
  }
  return v10;
}

```

## disassembly

```asm
0x140846598  push    rbp
0x14084659a  push    rbx
0x14084659b  push    rsi
0x14084659c  push    rdi
0x14084659d  push    r14
0x14084659f  push    r15
0x1408465a1  lea     rbp, [rsp-438h]
0x1408465a9  sub     rsp, 538h
0x1408465b0  mov     rax, cs:__security_cookie
0x1408465b7  xor     rax, rsp
0x1408465ba  mov     [rbp+460h+var_40], rax
0x1408465c1  mov     r15, r8
0x1408465c4  lea     rcx, [rsp+560h+ContextRecord]; void *
0x1408465c9  mov     r8d, 4D0h; Size
0x1408465cf  xor     edx, edx; Val
0x1408465d1  mov     r14, r9
0x1408465d4  call    memset_0
0x1408465d9  mov     edi, 88h
0x1408465de  mov     [rsp+560h+var_518], 0
0x1408465e7  mov     edx, edi; NumberOfBytes
0x1408465e9  mov     [rsp+560h+var_520], 0
0x1408465f1  mov     r8d, 74614454h; Tag
0x1408465f7  mov     ecx, 600h; PoolType
0x1408465fc  call    ExAllocatePoolWithTag
0x140846601  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140846608  mov     rbx, rax
0x14084660b  jnz     short loc_140846624
0x14084660d  test    rax, rax
0x140846610  jz      short loc_140846624
0x140846612  mov     r8d, edi; Size
0x140846615  xor     edx, edx; Val
0x140846617  mov     rcx, rax; void *
0x14084661a  call    memset_0
0x14084661f  mov     rsi, rbx
0x140846622  jmp     short loc_140846630
0x140846624  mov     rsi, rbx
0x140846627  test    rbx, rbx
0x14084662a  jz      loc_1408466E8
0x140846630  mov     edx, 40000h; NumberOfBytes
0x140846635  mov     ecx, 600h; PoolType
0x14084663a  mov     r8d, 74614454h; Tag
0x140846640  call    ExAllocatePoolWithTag
0x140846645  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14084664c  mov     rdi, rax
0x14084664f  jnz     short loc_14084666B
0x140846651  test    rax, rax
0x140846654  jz      short loc_14084666B
0x140846656  xor     edx, edx; Val
0x140846658  mov     r8d, 40000h; Size
0x14084665e  mov     rcx, rax; void *
0x140846661  call    memset_0
0x140846666  mov     [rbx], rdi
0x140846669  jmp     short loc_140846673
0x14084666b  mov     [rbx], rdi
0x14084666e  test    rdi, rdi
0x140846671  jz      short loc_1408466D1
0x140846673  lea     r9, aWhea; "WHEA"
0x14084667a  mov     edx, 20h ; ' '; cbDest
0x14084667f  lea     r8, aWs; "%ws"
0x140846686  lea     rcx, [rbx+68h]; pszDest
0x14084668a  call    RtlStringCbPrintfW
0x14084668f  test    eax, eax
0x140846691  js      short loc_1408466D1
0x140846693  lea     r8, [rsp+560h+var_518]
0x140846698  mov     [rsp+560h+var_520], 1
0x1408466a0  lea     rdx, [rsp+560h+var_520]
0x1408466a5  lea     rcx, [rbx+68h]
0x1408466a9  call    cs:__imp_WerLiveKernelCreateReport
0x1408466b0  nop     dword ptr [rax+rax+00h]
0x1408466b5  test    eax, eax
0x1408466b7  jns     loc_140846768
0x1408466bd  xor     edx, edx; Level
0x1408466bf  lea     r8, aLkmdtelWerlive_0; "LKMDTEL: WerLiveKernelCreateReport fail"...
0x1408466c6  mov     r9d, eax
0x1408466c9  lea     ecx, [rdx+5]; ComponentId
0x1408466cc  call    DbgPrintEx
0x1408466d1  mov     rcx, [rbx]
0x1408466d4  test    rcx, rcx
0x1408466d7  jz      short loc_1408466DE
0x1408466d9  call    LkmdTelpFreeMem
0x1408466de  mov     rcx, rbx
0x1408466e1  call    LkmdTelpFreeMem
0x1408466e6  xor     esi, esi
0x1408466e8  mov     rcx, [rsp+560h+var_518]
0x1408466ed  test    rcx, rcx
0x1408466f0  jz      short loc_140846745
0x1408466f2  call    cs:__imp_WerLiveKernelCancelReport
0x1408466f9  nop     dword ptr [rax+rax+00h]
0x1408466fe  test    eax, eax
0x140846700  jns     short loc_140846719
0x140846702  mov     edx, 1; Level
0x140846707  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x14084670e  mov     r9d, eax
0x140846711  lea     ecx, [rdx+4]; ComponentId
0x140846714  call    DbgPrintEx
0x140846719  mov     rcx, [rsp+560h+var_518]
0x14084671e  call    cs:__imp_WerLiveKernelCloseHandle
0x140846725  nop     dword ptr [rax+rax+00h]
0x14084672a  test    eax, eax
0x14084672c  jns     short loc_140846745
0x14084672e  mov     edx, 1; Level
0x140846733  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x14084673a  mov     r9d, eax
0x14084673d  lea     ecx, [rdx+4]; ComponentId
0x140846740  call    DbgPrintEx
0x140846745  mov     rax, rsi
0x140846748  mov     rcx, [rbp+460h+var_40]
0x14084674f  xor     rcx, rsp; StackCookie
0x140846752  call    __security_check_cookie
0x140846757  add     rsp, 538h
0x14084675e  pop     r15
0x140846760  pop     r14
0x140846762  pop     rdi
0x140846763  pop     rsi
0x140846764  pop     rbx
0x140846765  pop     rbp
0x140846766  retn
0x140846768  cmp     [rsp+560h+var_520], 0
0x14084676d  jnz     short loc_140846788
0x14084676f  mov     edx, 1; Level
0x140846774  lea     r8, aLkmdtelWerpoli; "LKMDTEL: WerPolicy is WerLiveKernelPoli"...
0x14084677b  lea     ecx, [rdx+4]; ComponentId
0x14084677e  call    DbgPrintEx
0x140846783  jmp     loc_1408466D1
0x140846788  mov     rax, [rsp+560h+var_518]
0x14084678d  lea     rcx, [rsp+560h+ContextRecord]; ContextRecord
0x140846792  mov     [rbx+60h], rax
0x140846796  call    RtlCaptureContext
0x14084679b  mov     rax, [rbx]
0x14084679e  lea     rcx, [rsp+560h+ContextRecord]
0x1408467a3  mov     [rsp+560h+var_528], rax
0x1408467a8  mov     r9, r15
0x1408467ab  mov     rax, [rbp+460h+arg_28]
0x1408467b2  xor     edx, edx
0x1408467b4  mov     [rsp+560h+var_530], rax
0x1408467b9  mov     r8d, 124h
0x1408467bf  mov     rax, [rbp+460h+arg_20]
0x1408467c6  mov     [rsp+560h+var_538], rax
0x1408467cb  mov     [rsp+560h+var_540], r14
0x1408467d0  call    KeCapturePersistentThreadState
0x1408467d5  test    eax, eax
0x1408467d7  jz      loc_1408466D1
0x1408467dd  mov     [rbx+8], eax
0x1408467e0  jmp     loc_140846745
```
