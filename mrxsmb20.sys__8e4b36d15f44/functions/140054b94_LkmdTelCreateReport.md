# LkmdTelCreateReport

- ea: `0x140054b94`
- end: `0x140054e21`
- name: `LkmdTelCreateReport`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140028000`

## callees

- `0x140036df0`
- `0x140037120`
- `0x1400375c0`
- `0x140054b94`
- `0x140054f20`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054bfa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054c45`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054bfa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054c45`
- `ntoskrnl!RtlCaptureContext` at `0x140054dc6`
- `ntoskrnl!RtlCaptureContext` at `0x140054dc6`
- `ntoskrnl!DbgPrintEx` at `0x140054cd8`
- `ntoskrnl!DbgPrintEx` at `0x140054d27`
- `ntoskrnl!DbgPrintEx` at `0x140054d5a`
- `ntoskrnl!DbgPrintEx` at `0x140054da7`
- `ntoskrnl!DbgPrintEx` at `0x140054cd8`
- `ntoskrnl!DbgPrintEx` at `0x140054d27`
- `ntoskrnl!DbgPrintEx` at `0x140054d5a`
- `ntoskrnl!DbgPrintEx` at `0x140054da7`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x140054e05`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x140054e05`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140054d38`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140054d38`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140054cb5`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCreateReport` at `0x140054cb5`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140054d05`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140054d05`

## string_xrefs

- `0x140054ccb`: `LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n`

## pseudocode

```c
wchar_t *__fastcall LkmdTelCreateReport(__int64 a1, __int64 a2, __int64 a3)
{
  wchar_t *PoolWithTag; // rax
  wchar_t *v5; // rbx
  wchar_t *v6; // rsi
  PVOID v7; // rax
  PVOID v8; // rdi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // eax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  CONTEXT ContextRecord; // [rsp+50h] [rbp-B0h] BYREF

  memset(&ContextRecord, 0, sizeof(ContextRecord));
  v15 = 0;
  v14 = 0;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x74614454u);
  v5 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
  {
    memset(PoolWithTag, 0, 0x88u);
    v6 = v5;
LABEL_5:
    v7 = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x40000u, 0x74614454u);
    v8 = v7;
    if ( ExPoolZeroingNativelySupported || !v7 )
    {
      *(_QWORD *)v5 = v7;
      if ( !v7 )
      {
LABEL_12:
        if ( *(_QWORD *)v5 )
          ((void (*)(void))LkmdTelpFreeMem)();
        LkmdTelpFreeMem(v5);
        v6 = 0;
        goto LABEL_15;
      }
    }
    else
    {
      memset(v7, 0, 0x40000u);
      *(_QWORD *)v5 = v8;
    }
    if ( RtlStringCbPrintfW(v5 + 52, 0x20u, L"%ws", L"SMB2ClientReqVF") >= 0 )
    {
      v14 = 1;
      v9 = WerLiveKernelCreateReport(v5 + 52, &v14, &v15);
      if ( v9 >= 0 )
      {
        if ( v14 )
        {
          *((_QWORD *)v5 + 12) = v15;
          RtlCaptureContext(&ContextRecord);
          v13 = KeCapturePersistentThreadState(&ContextRecord, 0, 510, a3, 0, 0, 0, *(_QWORD *)v5);
          if ( v13 )
          {
            *((_DWORD *)v5 + 2) = v13;
            return v6;
          }
        }
        else
        {
          DbgPrintEx(5u, 1u, "LKMDTEL: WerPolicy is WerLiveKernelPolicyNoDump, no dump is allowed.\n");
        }
      }
      else
      {
        DbgPrintEx(5u, 0, "LKMDTEL: WerLiveKernelCreateReport failed with status 0x%X\n", v9);
      }
    }
    goto LABEL_12;
  }
  v6 = PoolWithTag;
  if ( PoolWithTag )
    goto LABEL_5;
LABEL_15:
  if ( v15 )
  {
    v10 = WerLiveKernelCancelReport();
    if ( v10 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v10);
    v11 = WerLiveKernelCloseHandle(v15);
    if ( v11 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: WerLiveCancelReport failed, status 0x%X\n", v11);
  }
  return v6;
}

```

## disassembly

```asm
0x140054b94  mov     [rsp-8+arg_0], rbx
0x140054b99  mov     [rsp-8+arg_8], rsi
0x140054b9e  push    rbp
0x140054b9f  push    rdi
0x140054ba0  push    r14
0x140054ba2  lea     rbp, [rsp-430h]
0x140054baa  sub     rsp, 530h
0x140054bb1  mov     rax, cs:__security_cookie
0x140054bb8  xor     rax, rsp
0x140054bbb  mov     [rbp+440h+var_20], rax
0x140054bc2  mov     r14, r8
0x140054bc5  lea     rcx, [rsp+540h+ContextRecord]; void *
0x140054bca  mov     r8d, 4D0h; Size
0x140054bd0  xor     edx, edx; Val
0x140054bd2  call    memset
0x140054bd7  mov     edi, 88h
0x140054bdc  mov     [rsp+540h+var_4F8], 0
0x140054be5  mov     edx, edi; NumberOfBytes
0x140054be7  mov     [rsp+540h+var_500], 0
0x140054bef  mov     r8d, 74614454h; Tag
0x140054bf5  mov     ecx, 600h; PoolType
0x140054bfa  call    cs:__imp_ExAllocatePoolWithTag
0x140054c01  nop     dword ptr [rax+rax+00h]
0x140054c06  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140054c0d  mov     rbx, rax
0x140054c10  jnz     short loc_140054C29
0x140054c12  test    rax, rax
0x140054c15  jz      short loc_140054C29
0x140054c17  mov     r8d, edi; Size
0x140054c1a  xor     edx, edx; Val
0x140054c1c  mov     rcx, rax; void *
0x140054c1f  call    memset
0x140054c24  mov     rsi, rbx
0x140054c27  jmp     short loc_140054C35
0x140054c29  mov     rsi, rbx
0x140054c2c  test    rbx, rbx
0x140054c2f  jz      loc_140054CFB
0x140054c35  mov     edx, 40000h; NumberOfBytes
0x140054c3a  mov     ecx, 600h; PoolType
0x140054c3f  mov     r8d, 74614454h; Tag
0x140054c45  call    cs:__imp_ExAllocatePoolWithTag
0x140054c4c  nop     dword ptr [rax+rax+00h]
0x140054c51  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140054c58  mov     rdi, rax
0x140054c5b  jnz     short loc_140054C77
0x140054c5d  test    rax, rax
0x140054c60  jz      short loc_140054C77
0x140054c62  xor     edx, edx; Val
0x140054c64  mov     r8d, 40000h; Size
0x140054c6a  mov     rcx, rax; void *
0x140054c6d  call    memset
0x140054c72  mov     [rbx], rdi
0x140054c75  jmp     short loc_140054C7F
0x140054c77  mov     [rbx], rdi
0x140054c7a  test    rdi, rdi
0x140054c7d  jz      short loc_140054CE4
0x140054c7f  lea     r9, aSmb2clientreqv; "SMB2ClientReqVF"
0x140054c86  mov     edx, 20h ; ' '; cbDest
0x140054c8b  lea     r8, aWs; "%ws"
0x140054c92  lea     rcx, [rbx+68h]; pszDest
0x140054c96  call    RtlStringCbPrintfW
0x140054c9b  test    eax, eax
0x140054c9d  js      short loc_140054CE4
0x140054c9f  lea     r8, [rsp+540h+var_4F8]
0x140054ca4  mov     [rsp+540h+var_500], 1
0x140054cac  lea     rdx, [rsp+540h+var_500]
0x140054cb1  lea     rcx, [rbx+68h]
0x140054cb5  call    cs:__imp_WerLiveKernelCreateReport
0x140054cbc  nop     dword ptr [rax+rax+00h]
0x140054cc1  test    eax, eax
0x140054cc3  jns     loc_140054D91
0x140054cc9  xor     edx, edx; Level
0x140054ccb  lea     r8, Format; "LKMDTEL: WerLiveKernelCreateReport fail"...
0x140054cd2  mov     r9d, eax
0x140054cd5  lea     ecx, [rdx+5]; ComponentId
0x140054cd8  call    cs:__imp_DbgPrintEx
0x140054cdf  nop     dword ptr [rax+rax+00h]
0x140054ce4  mov     rcx, [rbx]
0x140054ce7  test    rcx, rcx
0x140054cea  jz      short loc_140054CF1
0x140054cec  call    LkmdTelpFreeMem
0x140054cf1  mov     rcx, rbx
0x140054cf4  call    LkmdTelpFreeMem
0x140054cf9  xor     esi, esi
0x140054cfb  mov     rcx, [rsp+540h+var_4F8]
0x140054d00  test    rcx, rcx
0x140054d03  jz      short loc_140054D66
0x140054d05  call    cs:__imp_WerLiveKernelCancelReport
0x140054d0c  nop     dword ptr [rax+rax+00h]
0x140054d11  test    eax, eax
0x140054d13  jns     short loc_140054D33
0x140054d15  mov     edx, 1; Level
0x140054d1a  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x140054d21  mov     r9d, eax
0x140054d24  lea     ecx, [rdx+4]; ComponentId
0x140054d27  call    cs:__imp_DbgPrintEx
0x140054d2e  nop     dword ptr [rax+rax+00h]
0x140054d33  mov     rcx, [rsp+540h+var_4F8]
0x140054d38  call    cs:__imp_WerLiveKernelCloseHandle
0x140054d3f  nop     dword ptr [rax+rax+00h]
0x140054d44  test    eax, eax
0x140054d46  jns     short loc_140054D66
0x140054d48  mov     edx, 1; Level
0x140054d4d  lea     r8, aLkmdtelWerlive; "LKMDTEL: WerLiveCancelReport failed, st"...
0x140054d54  mov     r9d, eax
0x140054d57  lea     ecx, [rdx+4]; ComponentId
0x140054d5a  call    cs:__imp_DbgPrintEx
0x140054d61  nop     dword ptr [rax+rax+00h]
0x140054d66  mov     rax, rsi
0x140054d69  mov     rcx, [rbp+440h+var_20]
0x140054d70  xor     rcx, rsp; StackCookie
0x140054d73  call    __security_check_cookie
0x140054d78  lea     r11, [rsp+540h+var_10]
0x140054d80  mov     rbx, [r11+20h]
0x140054d84  mov     rsi, [r11+28h]
0x140054d88  mov     rsp, r11
0x140054d8b  pop     r14
0x140054d8d  pop     rdi
0x140054d8e  pop     rbp
0x140054d8f  retn
0x140054d91  cmp     [rsp+540h+var_500], 0
0x140054d96  jnz     short loc_140054DB8
0x140054d98  mov     edx, 1; Level
0x140054d9d  lea     r8, aLkmdtelWerpoli; "LKMDTEL: WerPolicy is WerLiveKernelPoli"...
0x140054da4  lea     ecx, [rdx+4]; ComponentId
0x140054da7  call    cs:__imp_DbgPrintEx
0x140054dae  nop     dword ptr [rax+rax+00h]
0x140054db3  jmp     loc_140054CE4
0x140054db8  mov     rax, [rsp+540h+var_4F8]
0x140054dbd  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x140054dc2  mov     [rbx+60h], rax
0x140054dc6  call    cs:__imp_RtlCaptureContext
0x140054dcd  nop     dword ptr [rax+rax+00h]
0x140054dd2  mov     rax, [rbx]
0x140054dd5  lea     rcx, [rsp+540h+ContextRecord]
0x140054dda  mov     [rsp+540h+var_508], rax
0x140054ddf  mov     r9, r14
0x140054de2  mov     [rsp+540h+var_510], 0
0x140054deb  xor     edx, edx
0x140054ded  mov     [rsp+540h+var_518], 0
0x140054df6  mov     r8d, 1FEh
0x140054dfc  mov     [rsp+540h+var_520], 0
0x140054e05  call    cs:__imp_KeCapturePersistentThreadState
0x140054e0c  nop     dword ptr [rax+rax+00h]
0x140054e11  test    eax, eax
0x140054e13  jz      loc_140054CE4
0x140054e19  mov     [rbx+8], eax
0x140054e1c  jmp     loc_140054D66
```
