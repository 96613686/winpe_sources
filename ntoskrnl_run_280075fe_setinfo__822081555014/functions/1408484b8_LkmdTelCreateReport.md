# LkmdTelCreateReport

- ea: `0x1408484b8`
- end: `0x140848705`
- name: `LkmdTelCreateReport`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1407f652c`

## callees

- `0x1402a2f90`
- `0x1402e38d0`
- `0x1403887e8`
- `0x140542a90`
- `0x1406dc8c0`
- `0x1406f7380`
- `0x1408484b8`
- `0x1408487e8`
- `0x140bb1320`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x1408485c9`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x1408485c9`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140848612`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140848612`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x14084863e`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x14084863e`

## string_xrefs

- `0x1408485df`: `LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n`

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
0x1408484b8  push    rbp
0x1408484ba  push    rbx
0x1408484bb  push    rsi
0x1408484bc  push    rdi
0x1408484bd  push    r14
0x1408484bf  push    r15
0x1408484c1  lea     rbp, [rsp-438h]
0x1408484c9  sub     rsp, 538h
0x1408484d0  mov     rax, cs:__security_cookie
0x1408484d7  xor     rax, rsp
0x1408484da  mov     [rbp+460h+var_40], rax
0x1408484e1  mov     r15, r8
0x1408484e4  lea     rcx, [rsp+560h+ContextRecord]; void *
0x1408484e9  mov     r8d, 4D0h; Size
0x1408484ef  xor     edx, edx; Val
0x1408484f1  mov     r14, r9
0x1408484f4  call    memset_0
0x1408484f9  mov     edi, 88h
0x1408484fe  mov     [rsp+560h+var_518], 0
0x140848507  mov     edx, edi; NumberOfBytes
0x140848509  mov     [rsp+560h+var_520], 0
0x140848511  mov     r8d, 74614454h; Tag
0x140848517  mov     ecx, 600h; PoolType
0x14084851c  call    ExAllocatePoolWithTag
0x140848521  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140848528  mov     rbx, rax
0x14084852b  jnz     short loc_140848544
0x14084852d  test    rax, rax
0x140848530  jz      short loc_140848544
0x140848532  mov     r8d, edi; Size
0x140848535  xor     edx, edx; Val
0x140848537  mov     rcx, rax; void *
0x14084853a  call    memset_0
0x14084853f  mov     rsi, rbx
0x140848542  jmp     short loc_140848550
0x140848544  mov     rsi, rbx
0x140848547  test    rbx, rbx
0x14084854a  jz      loc_140848608
0x140848550  mov     edx, 40000h; NumberOfBytes
0x140848555  mov     ecx, 600h; PoolType
0x14084855a  mov     r8d, 74614454h; Tag
0x140848560  call    ExAllocatePoolWithTag
0x140848565  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14084856c  mov     rdi, rax
0x14084856f  jnz     short loc_14084858B
0x140848571  test    rax, rax
0x140848574  jz      short loc_14084858B
0x140848576  xor     edx, edx; Val
0x140848578  mov     r8d, 40000h; Size
0x14084857e  mov     rcx, rax; void *
0x140848581  call    memset_0
0x140848586  mov     [rbx], rdi
0x140848589  jmp     short loc_140848593
0x14084858b  mov     [rbx], rdi
0x14084858e  test    rdi, rdi
0x140848591  jz      short loc_1408485F1
0x140848593  lea     r9, aWhea; "WHEA"
0x14084859a  mov     edx, 20h ; ' '; cbDest
0x14084859f  lea     r8, aWs; "%ws"
0x1408485a6  lea     rcx, [rbx+68h]; pszDest
0x1408485aa  call    RtlStringCbPrintfW
0x1408485af  test    eax, eax
0x1408485b1  js      short loc_1408485F1
0x1408485b3  lea     r8, [rsp+560h+var_518]
0x1408485b8  mov     [rsp+560h+var_520], 1
0x1408485c0  lea     rdx, [rsp+560h+var_520]
0x1408485c5  lea     rcx, [rbx+68h]
0x1408485c9  call    cs:__imp_WerLiveKernelCreateReport
0x1408485d0  nop     dword ptr [rax+rax+00h]
0x1408485d5  test    eax, eax
0x1408485d7  jns     loc_140848688
0x1408485dd  xor     edx, edx; Level
0x1408485df  lea     r8, aLkmdtelWerlive_0; "LKMDTEL: WerLiveKernelCreateReport fail"...
0x1408485e6  mov     r9d, eax
0x1408485e9  lea     ecx, [rdx+5]; ComponentId
0x1408485ec  call    DbgPrintEx
0x1408485f1  mov     rcx, [rbx]
0x1408485f4  test    rcx, rcx
0x1408485f7  jz      short loc_1408485FE
0x1408485f9  call    LkmdTelpFreeMem
0x1408485fe  mov     rcx, rbx
0x140848601  call    LkmdTelpFreeMem
0x140848606  xor     esi, esi
0x140848608  mov     rcx, [rsp+560h+var_518]
0x14084860d  test    rcx, rcx
0x140848610  jz      short loc_140848665
0x140848612  call    cs:__imp_WerLiveKernelCancelReport
0x140848619  nop     dword ptr [rax+rax+00h]
0x14084861e  test    eax, eax
0x140848620  jns     short loc_140848639
0x140848622  mov     edx, 1; Level
0x140848627  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x14084862e  mov     r9d, eax
0x140848631  lea     ecx, [rdx+4]; ComponentId
0x140848634  call    DbgPrintEx
0x140848639  mov     rcx, [rsp+560h+var_518]
0x14084863e  call    cs:__imp_WerLiveKernelCloseHandle
0x140848645  nop     dword ptr [rax+rax+00h]
0x14084864a  test    eax, eax
0x14084864c  jns     short loc_140848665
0x14084864e  mov     edx, 1; Level
0x140848653  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x14084865a  mov     r9d, eax
0x14084865d  lea     ecx, [rdx+4]; ComponentId
0x140848660  call    DbgPrintEx
0x140848665  mov     rax, rsi
0x140848668  mov     rcx, [rbp+460h+var_40]
0x14084866f  xor     rcx, rsp; StackCookie
0x140848672  call    __security_check_cookie
0x140848677  add     rsp, 538h
0x14084867e  pop     r15
0x140848680  pop     r14
0x140848682  pop     rdi
0x140848683  pop     rsi
0x140848684  pop     rbx
0x140848685  pop     rbp
0x140848686  retn
0x140848688  cmp     [rsp+560h+var_520], 0
0x14084868d  jnz     short loc_1408486A8
0x14084868f  mov     edx, 1; Level
0x140848694  lea     r8, aLkmdtelWerpoli; "LKMDTEL: WerPolicy is WerLiveKernelPoli"...
0x14084869b  lea     ecx, [rdx+4]; ComponentId
0x14084869e  call    DbgPrintEx
0x1408486a3  jmp     loc_1408485F1
0x1408486a8  mov     rax, [rsp+560h+var_518]
0x1408486ad  lea     rcx, [rsp+560h+ContextRecord]; ContextRecord
0x1408486b2  mov     [rbx+60h], rax
0x1408486b6  call    RtlCaptureContext
0x1408486bb  mov     rax, [rbx]
0x1408486be  lea     rcx, [rsp+560h+ContextRecord]
0x1408486c3  mov     [rsp+560h+var_528], rax
0x1408486c8  mov     r9, r15
0x1408486cb  mov     rax, [rbp+460h+arg_28]
0x1408486d2  xor     edx, edx
0x1408486d4  mov     [rsp+560h+var_530], rax
0x1408486d9  mov     r8d, 124h
0x1408486df  mov     rax, [rbp+460h+arg_20]
0x1408486e6  mov     [rsp+560h+var_538], rax
0x1408486eb  mov     [rsp+560h+var_540], r14
0x1408486f0  call    KeCapturePersistentThreadState
0x1408486f5  test    eax, eax
0x1408486f7  jz      loc_1408485F1
0x1408486fd  mov     [rbx+8], eax
0x140848700  jmp     loc_140848665
```
