# PerfpExceptionFilter(ulong,_EXCEPTION_POINTERS const *,EXT_OBJECT *,ulong)

- ea: `0x1800119fc`
- end: `0x180011ace`
- name: `?PerfpExceptionFilter@@YAKKPEBU_EXCEPTION_POINTERS@@PEAUEXT_OBJECT@@K@Z`
- size: `210`
- prototype: `unsigned int __fastcall(unsigned int, const struct _EXCEPTION_POINTERS *, struct EXT_OBJECT *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011d10`
- `0x18001335c`
- `0x1800136b0`

## callees

- `0x18000b0e8`
- `0x18000c134`
- `0x1800119fc`
- `0x180012ec4`

## pseudocode

```c
__int64 __fastcall PerfpExceptionFilter(
        unsigned int a1,
        const struct _EXCEPTION_POINTERS *a2,
        struct EXT_OBJECT *a3,
        int a4)
{
  __int64 v4; // rsi
  PVOID ExceptionAddress; // rdi
  __int64 v8; // rcx
  __int64 *v9; // rdx

  v4 = a1;
  if ( a1 != -1073741571 )
  {
    if ( a2 && a2->ExceptionRecord )
      ExceptionAddress = a2->ExceptionRecord->ExceptionAddress;
    else
      ExceptionAddress = 0;
    if ( !(unsigned int)PerfpThrottleError(a4, *((HKEY *)a3 + 13), (struct ERROR_LOG *)((char *)a3 + 488)) )
      goto LABEL_17;
    if ( a4 == 1009 )
    {
      if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
      {
        v9 = PERFLIB_OPEN_PROC_EXCEPTION;
        goto LABEL_16;
      }
    }
    else
    {
      if ( a4 != 1010 )
      {
        if ( a4 != 1011 || (Microsoft_Windows_PerflibEnableBits & 2) == 0 )
          goto LABEL_17;
        v9 = PERFLIB_CLOSE_PROC_EXCEPTION;
        goto LABEL_16;
      }
      if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
      {
        v9 = PERFLIB_COLLECT_PROC_EXCEPTION;
LABEL_16:
        McTemplateU0zzqp_EtwEventWriteTransfer(
          v8,
          (__int64)v9,
          *((const wchar_t **)a3 + 12),
          *((const wchar_t **)a3 + 49),
          v4,
          (char)ExceptionAddress);
      }
    }
LABEL_17:
    DisablePerfLibrary(a3, 1, a4, v4, (unsigned __int64)ExceptionAddress);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800119fc  push    rbx
0x1800119fe  push    rbp
0x1800119ff  push    rsi
0x180011a00  push    rdi
0x180011a01  sub     rsp, 38h
0x180011a05  mov     esi, ecx
0x180011a07  mov     ebp, r9d
0x180011a0a  mov     rbx, r8
0x180011a0d  cmp     ecx, 0C00000FDh
0x180011a13  jz      loc_180011AC0
0x180011a19  test    rdx, rdx
0x180011a1c  jz      short loc_180011A2C
0x180011a1e  mov     rdi, [rdx]
0x180011a21  test    rdi, rdi
0x180011a24  jz      short loc_180011A2C
0x180011a26  mov     rdi, [rdi+10h]
0x180011a2a  jmp     short loc_180011A2E
0x180011a2c  xor     edi, edi
0x180011a2e  mov     rdx, [rbx+68h]; HKEY
0x180011a32  add     r8, 1E8h; struct ERROR_LOG *
0x180011a39  mov     ecx, ebp; unsigned int
0x180011a3b  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180011a40  test    eax, eax
0x180011a42  jz      short loc_180011AA4
0x180011a44  mov     eax, ebp
0x180011a46  sub     eax, 3F1h
0x180011a4b  jz      short loc_180011A7B
0x180011a4d  sub     eax, 1
0x180011a50  jz      short loc_180011A69
0x180011a52  cmp     eax, 1
0x180011a55  jnz     short loc_180011AA4
0x180011a57  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180011a5e  jz      short loc_180011AA4
0x180011a60  lea     rdx, PERFLIB_CLOSE_PROC_EXCEPTION
0x180011a67  jmp     short loc_180011A8B
0x180011a69  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180011a70  jz      short loc_180011AA4
0x180011a72  lea     rdx, PERFLIB_COLLECT_PROC_EXCEPTION
0x180011a79  jmp     short loc_180011A8B
0x180011a7b  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180011a82  jz      short loc_180011AA4
0x180011a84  lea     rdx, PERFLIB_OPEN_PROC_EXCEPTION
0x180011a8b  mov     r9, [rbx+188h]
0x180011a92  mov     r8, [rbx+60h]
0x180011a96  mov     [rsp+58h+var_30], rdi
0x180011a9b  mov     dword ptr [rsp+58h+var_38], esi
0x180011a9f  call    McTemplateU0zzqp_EtwEventWriteTransfer
0x180011aa4  mov     r9, rsi; unsigned __int64
0x180011aa7  mov     [rsp+58h+var_38], rdi; unsigned __int64
0x180011aac  mov     r8d, ebp; unsigned int
0x180011aaf  mov     edx, 1; unsigned int
0x180011ab4  mov     rcx, rbx; struct EXT_OBJECT *
0x180011ab7  call    ?DisablePerfLibrary@@YAXPEAUEXT_OBJECT@@KK_K1@Z; DisablePerfLibrary(EXT_OBJECT *,ulong,ulong,unsigned __int64,unsigned __int64)
0x180011abc  xor     eax, eax
0x180011abe  jmp     short loc_180011AC5
0x180011ac0  mov     eax, 1
0x180011ac5  add     rsp, 38h
0x180011ac9  pop     rdi
0x180011aca  pop     rsi
0x180011acb  pop     rbp
0x180011acc  pop     rbx
0x180011acd  retn
```
