# GetArchitecture

- ea: `0x18001da88`
- end: `0x18001dba5`
- name: `GetArchitecture`
- size: `285`
- prototype: `HRESULT __stdcall(VM_SAVED_STATE_DUMP_HANDLE VmSavedStateDumpHandle, UINT32 VpId, VIRTUAL_PROCESSOR_ARCH *Architecture)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016990`
- `0x18001e3c0`
- `0x180020574`

## callees

- `0x180007944`
- `0x18001da88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dab1`
- `WINSPOOL!GetPrinterDataW` at `0x18001db2b`
- `WINSPOOL!GetPrinterDataW` at `0x18001db2b`
- `WINSPOOL!OpenPrinterW` at `0x18001dafa`
- `WINSPOOL!OpenPrinterW` at `0x18001dafa`
- `WINSPOOL!ClosePrinter` at `0x18001db4f`
- `WINSPOOL!ClosePrinter` at `0x18001db4f`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HRESULT __stdcall GetArchitecture(
        VM_SAVED_STATE_DUMP_HANDLE VmSavedStateDumpHandle,
        UINT32 VpId,
        VIRTUAL_PROCESSOR_ARCH *Architecture)
{
  BYTE *v4; // rbx
  HRESULT v5; // esi
  HANDLE v6; // rcx
  __int64 v7; // r11
  const unsigned __int16 *v8; // r8
  HANDLE phPrinter; // [rsp+30h] [rbp-20h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+38h] [rbp-18h] BYREF
  DWORD pType; // [rsp+78h] [rbp+28h] BYREF
  DWORD pcbNeeded; // [rsp+88h] [rbp+38h] BYREF

  v4 = *(BYTE **)&VpId;
  v5 = 0;
  if ( *(_QWORD *)&VpId )
  {
    **(_WORD **)&VpId = 0;
    if ( VmSavedStateDumpHandle && *(_WORD *)VmSavedStateDumpHandle )
    {
      phPrinter = 0;
      pcbNeeded = 0;
      pType = 1;
      *(_OWORD *)&pDefault.pDatatype = 0;
      *(_QWORD *)&pDefault.DesiredAccess = 131074;
      if ( OpenPrinterW((LPWSTR)VmSavedStateDumpHandle, &phPrinter, &pDefault) )
      {
        if ( GetPrinterDataW(phPrinter, (LPWSTR)L"Architecture", &pType, v4, 2 * *Architecture, &pcbNeeded)
          || pType != 1 )
        {
          *(_WORD *)v4 = 0;
        }
        else
        {
          v5 = 1;
        }
        v6 = phPrinter;
        *Architecture = pcbNeeded >> 1;
        ClosePrinter(v6);
      }
    }
    else
    {
      v7 = -1;
      v8 = (const unsigned __int16 *)PlatformEnv[MyPlatform];
      do
        ++v7;
      while ( v8[v7] );
      if ( (unsigned int)v7 <= *Architecture )
      {
        StringCchCopyW(*(unsigned __int16 **)&VpId, *(unsigned int *)Architecture, v8);
        v5 = 1;
      }
      *Architecture = v7;
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  return v5;
}

```

## disassembly

```asm
0x18001da88  mov     [rsp-18h+arg_0], rbx
0x18001da8d  mov     [rsp-18h+arg_10], rsi
0x18001da92  push    rbp
0x18001da93  push    rdi
0x18001da94  push    r14
0x18001da96  mov     rbp, rsp
0x18001da99  sub     rsp, 50h
0x18001da9d  xor     r14d, r14d
0x18001daa0  mov     rdi, r8
0x18001daa3  mov     rbx, rdx
0x18001daa6  mov     esi, r14d
0x18001daa9  test    rdx, rdx
0x18001daac  jnz     short loc_18001DABC
0x18001daae  lea     ecx, [rdx+57h]; dwErrCode
0x18001dab1  call    cs:__imp_SetLastError
0x18001dab7  jmp     loc_18001DB8E
0x18001dabc  mov     [rdx], r14w
0x18001dac0  test    rcx, rcx
0x18001dac3  jz      loc_18001DB57
0x18001dac9  cmp     [rcx], r14w
0x18001dacd  jz      loc_18001DB57
0x18001dad3  xorps   xmm0, xmm0
0x18001dad6  mov     [rbp+phPrinter], r14
0x18001dada  lea     r8, [rbp+pDefault]; pDefault
0x18001dade  mov     [rbp+arg_18], r14d
0x18001dae2  lea     rdx, [rbp+phPrinter]; phPrinter
0x18001dae6  mov     [rbp+pType], 1
0x18001daed  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18001daf2  mov     qword ptr [rbp+pDefault.DesiredAccess], 20002h
0x18001dafa  call    cs:__imp_OpenPrinterW
0x18001db00  test    eax, eax
0x18001db02  jz      loc_18001DB8E
0x18001db08  mov     eax, [rdi]
0x18001db0a  lea     rcx, [rbp+arg_18]
0x18001db0e  mov     [rsp+50h+pcbNeeded], rcx; pcbNeeded
0x18001db13  lea     r8, [rbp+pType]; pType
0x18001db17  mov     rcx, [rbp+phPrinter]; hPrinter
0x18001db1b  lea     rdx, aArchitecture; "Architecture"
0x18001db22  add     eax, eax
0x18001db24  mov     r9, rbx; pData
0x18001db27  mov     [rsp+50h+nSize], eax; nSize
0x18001db2b  call    cs:__imp_GetPrinterDataW
0x18001db31  test    eax, eax
0x18001db33  jnz     short loc_18001DB40
0x18001db35  cmp     [rbp+pType], 1
0x18001db39  jnz     short loc_18001DB40
0x18001db3b  lea     esi, [rax+1]
0x18001db3e  jmp     short loc_18001DB44
0x18001db40  mov     [rbx], r14w
0x18001db44  mov     eax, [rbp+arg_18]
0x18001db47  mov     rcx, [rbp+phPrinter]; hPrinter
0x18001db4b  shr     eax, 1
0x18001db4d  mov     [rdi], eax
0x18001db4f  call    cs:__imp_ClosePrinter
0x18001db55  jmp     short loc_18001DB8E
0x18001db57  movsxd  rax, cs:MyPlatform
0x18001db5e  lea     r8, PlatformEnv
0x18001db65  or      r11, 0FFFFFFFFFFFFFFFFh
0x18001db69  mov     r8, [r8+rax*8]; unsigned __int16 *
0x18001db6d  inc     r11
0x18001db70  cmp     [r8+r11*2], r14w
0x18001db75  jnz     short loc_18001DB6D
0x18001db77  cmp     r11d, [rdi]
0x18001db7a  ja      short loc_18001DB8B
0x18001db7c  mov     edx, [rdi]; unsigned __int64
0x18001db7e  mov     rcx, rbx; unsigned __int16 *
0x18001db81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001db86  mov     esi, 1
0x18001db8b  mov     [rdi], r11d
0x18001db8e  lea     r11, [rsp+50h+var_s0]
0x18001db93  mov     eax, esi
0x18001db95  mov     rbx, [r11+20h]
0x18001db99  mov     rsi, [r11+30h]
0x18001db9d  mov     rsp, r11
0x18001dba0  pop     r14
0x18001dba2  pop     rdi
0x18001dba3  pop     rbp
0x18001dba4  retn
```
