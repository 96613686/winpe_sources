# WfpMidlObjectDecode

- ea: `0x14001cbdc`
- end: `0x14001ccd6`
- name: `WfpMidlObjectDecode`
- size: `250`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c560`
- `0x140047dc0`
- `0x1400612d0`
- `0x140061360`
- `0x1400614d0`
- `0x140061c50`
- `0x140061ca0`
- `0x140061cf0`
- `0x140061d40`
- `0x140061d90`
- `0x140061de0`
- `0x1400aa060`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14001cbdc`
- `0x140050ce0`
- `0x140078080`

## import_xrefs

- `msrpc!I_RpcExceptionFilter` at `0x1400789fb`
- `msrpc!I_RpcExceptionFilter` at `0x1400789fb`
- `msrpc!MesHandleFree` at `0x14001cc66`
- `msrpc!MesHandleFree` at `0x14001cc66`
- `msrpc!MesDecodeBufferHandleCreate` at `0x14001cc1c`
- `msrpc!MesDecodeBufferHandleCreate` at `0x14001cc1c`

## string_xrefs

- `0x14001cc8e`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectDecode(
        void (__fastcall *a1)(__int64, __int64 *),
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+28h] [rbp-10h] BYREF

  v13 = 0;
  v12 = 0;
  *a4 = 0;
  v6 = MesDecodeBufferHandleCreate(a2, a3, &v12);
  if ( v6 )
  {
    v11 = WfpReportSysErrorAsWinError(v7, "MesDecodeBufferHandleCreate", v6);
  }
  else
  {
    a1(v12, &v13);
    if ( v13 )
    {
      v9 = 0;
      *a4 = v13;
      goto LABEL_4;
    }
    v11 = WfpReportSysErrorAsNtStatus(v8, "WfpMidlObjectDecode", 3221225495LL, 1);
  }
  v9 = v11;
LABEL_4:
  if ( v12 )
    MesHandleFree();
  if ( v9 )
    WfpReportError(v9, "WfpMidlObjectDecode");
  return v9;
}

```

## disassembly

```asm
0x14001cbdc  mov     r11, rsp
0x14001cbdf  mov     [r11+8], rbx
0x14001cbe3  mov     [r11+10h], rsi
0x14001cbe7  mov     [r11+20h], r9
0x14001cbeb  push    rdi
0x14001cbec  sub     rsp, 30h
0x14001cbf0  mov     rdi, r9
0x14001cbf3  mov     eax, r8d
0x14001cbf6  mov     r10, rdx
0x14001cbf9  mov     rsi, rcx
0x14001cbfc  mov     qword ptr [r11-10h], 0
0x14001cc04  mov     qword ptr [r11-18h], 0
0x14001cc0c  mov     qword ptr [r9], 0
0x14001cc13  lea     r8, [r11-18h]
0x14001cc17  mov     edx, eax
0x14001cc19  mov     rcx, r10
0x14001cc1c  call    cs:__imp_MesDecodeBufferHandleCreate
0x14001cc23  nop     dword ptr [rax+rax+00h]
0x14001cc28  mov     ebx, eax
0x14001cc2a  test    eax, eax
0x14001cc2c  jnz     short loc_14001CC8B
0x14001cc2e  lea     rdx, [rsp+38h+var_10]
0x14001cc33  mov     rcx, [rsp+38h+var_18]
0x14001cc38  mov     rax, rsi
0x14001cc3b  call    _guard_dispatch_icall
0x14001cc40  jmp     short loc_14001CC49
0x14001cc42  mov     ebx, eax
0x14001cc44  mov     rdi, [rsp+38h+arg_18]
0x14001cc49  test    ebx, ebx
0x14001cc4b  jnz     short loc_14001CC9F
0x14001cc4d  mov     rax, [rsp+38h+var_10]
0x14001cc52  test    rax, rax
0x14001cc55  jz      short loc_14001CCAB
0x14001cc57  xor     ebx, ebx
0x14001cc59  mov     [rdi], rax
0x14001cc5c  mov     rcx, [rsp+38h+var_18]
0x14001cc61  test    rcx, rcx
0x14001cc64  jz      short loc_14001CC72
0x14001cc66  call    cs:__imp_MesHandleFree
0x14001cc6d  nop     dword ptr [rax+rax+00h]
0x14001cc72  test    rbx, rbx
0x14001cc75  jnz     short loc_14001CCC5
0x14001cc77  mov     rax, rbx
0x14001cc7a  mov     rbx, [rsp+38h+arg_0]
0x14001cc7f  mov     rsi, [rsp+38h+arg_8]
0x14001cc84  add     rsp, 30h
0x14001cc88  pop     rdi
0x14001cc89  retn
0x14001cc8b  mov     r8d, eax
0x14001cc8e  lea     rdx, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x14001cc95  call    WfpReportSysErrorAsWinError
0x14001cc9a  mov     rbx, rax
0x14001cc9d  jmp     short loc_14001CC5C
0x14001cc9f  mov     r8d, ebx
0x14001cca2  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x14001cca9  jmp     short loc_14001CC95
0x14001ccab  mov     r9d, 1
0x14001ccb1  mov     r8d, 0C0000017h
0x14001ccb7  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x14001ccbe  call    WfpReportSysErrorAsNtStatus
0x14001ccc3  jmp     short loc_14001CC9A
0x14001ccc5  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x14001cccc  mov     rcx, rbx
0x14001cccf  call    WfpReportError
0x14001ccd4  jmp     short loc_14001CC77
0x1400789ed  push    rbp
0x1400789ef  sub     rsp, 20h
0x1400789f3  mov     rbp, rdx
0x1400789f6  mov     rcx, [rcx]
0x1400789f9  mov     ecx, [rcx]; ExceptionCode
0x1400789fb  call    cs:__imp_I_RpcExceptionFilter
0x140078a02  nop     dword ptr [rax+rax+00h]
0x140078a07  nop
0x140078a08  add     rsp, 20h
0x140078a0c  pop     rbp
0x140078a0d  retn
```
