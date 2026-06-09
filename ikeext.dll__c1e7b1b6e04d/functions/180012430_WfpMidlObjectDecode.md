# WfpMidlObjectDecode

- ea: `0x180012430`
- end: `0x18001251d`
- name: `WfpMidlObjectDecode`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006910`
- `0x180012150`

## callees

- `0x1800061ec`
- `0x180010db0`
- `0x180012430`
- `0x180016534`
- `0x180119010`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180012463`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180012463`
- `RPCRT4!I_RpcExceptionFilter` at `0x18011805e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18011805e`
- `RPCRT4!MesHandleFree` at `0x180012504`
- `RPCRT4!MesHandleFree` at `0x180012504`

## string_xrefs

- `0x1800124c2`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectDecode(
        void (__fastcall *a1)(handle_t, _QWORD *),
        char *a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  handle_t pHandle; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+28h] [rbp-30h] BYREF

  v6 = 0;
  v12[0] = 0;
  pHandle = 0;
  *a4 = 0;
  v7 = MesDecodeBufferHandleCreate(a2, a3, &pHandle);
  if ( v7 )
  {
    v6 = WfpReportSysErrorAsWinError(v8, "MesDecodeBufferHandleCreate", v7, 1);
  }
  else
  {
    a1(pHandle, v12);
    if ( v12[0] )
      *a4 = v12[0];
    else
      v6 = WfpReportSysErrorAsNtStatus(v9, "WfpMidlObjectDecode", 3221225495LL);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  if ( v6 )
    WfpReportError(v6, "WfpMidlObjectDecode");
  return v6;
}

```

## disassembly

```asm
0x180012430  mov     [rsp+arg_18], r9
0x180012435  push    rbx
0x180012436  push    rsi
0x180012437  push    rdi
0x180012438  push    r14
0x18001243a  sub     rsp, 38h
0x18001243e  mov     rdi, r9
0x180012441  mov     eax, r8d
0x180012444  mov     r10, rdx
0x180012447  mov     r14, rcx
0x18001244a  xor     ebx, ebx
0x18001244c  mov     [rsp+58h+var_30], rbx
0x180012451  mov     [rsp+58h+pHandle], rbx
0x180012456  mov     [r9], rbx
0x180012459  lea     r8, [rsp+58h+pHandle]; pHandle
0x18001245e  mov     edx, eax; BufferSize
0x180012460  mov     rcx, r10; Buffer
0x180012463  call    cs:__imp_MesDecodeBufferHandleCreate
0x180012469  mov     esi, eax
0x18001246b  test    eax, eax
0x18001246d  jnz     short loc_1800124B9
0x18001246f  lea     rdx, [rsp+58h+var_30]
0x180012474  mov     rcx, [rsp+58h+pHandle]
0x180012479  mov     rax, r14
0x18001247c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012481  jmp     short loc_18001248C
0x180012483  mov     esi, eax
0x180012485  xor     ebx, ebx
0x180012487  mov     rdi, [rsp+58h+arg_18]
0x18001248c  test    esi, esi
0x18001248e  jnz     short loc_1800124D3
0x180012490  mov     rax, [rsp+58h+var_30]
0x180012495  test    rax, rax
0x180012498  jz      short loc_1800124ED
0x18001249a  mov     [rdi], rax
0x18001249d  mov     rcx, [rsp+58h+pHandle]; Handle
0x1800124a2  test    rcx, rcx
0x1800124a5  jnz     short loc_180012504
0x1800124a7  test    rbx, rbx
0x1800124aa  jnz     short loc_18001250C
0x1800124ac  mov     rax, rbx
0x1800124af  add     rsp, 38h
0x1800124b3  pop     r14
0x1800124b5  pop     rdi
0x1800124b6  pop     rsi
0x1800124b7  pop     rbx
0x1800124b8  retn
0x1800124b9  mov     r9d, 1
0x1800124bf  mov     r8d, eax
0x1800124c2  lea     rdx, aMesdecodebuffe; "MesDecodeBufferHandleCreate"
0x1800124c9  call    WfpReportSysErrorAsWinError
0x1800124ce  mov     rbx, rax
0x1800124d1  jmp     short loc_18001249D
0x1800124d3  mov     r9d, 1
0x1800124d9  mov     r8d, esi
0x1800124dc  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x1800124e3  call    WfpReportSysErrorAsWinError
0x1800124e8  mov     rbx, rax
0x1800124eb  jmp     short loc_18001249D
0x1800124ed  mov     r8d, 0C0000017h
0x1800124f3  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x1800124fa  call    WfpReportSysErrorAsNtStatus
0x1800124ff  mov     rbx, rax
0x180012502  jmp     short loc_18001249D
0x180012504  call    cs:__imp_MesHandleFree
0x18001250a  jmp     short loc_1800124A7
0x18001250c  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x180012513  mov     rcx, rbx
0x180012516  call    WfpReportError
0x18001251b  jmp     short loc_1800124AC
0x180118050  push    rbp
0x180118052  sub     rsp, 20h
0x180118056  mov     rbp, rdx
0x180118059  mov     rcx, [rcx]
0x18011805c  mov     ecx, [rcx]; ExceptionCode
0x18011805e  call    cs:__imp_I_RpcExceptionFilter
0x180118064  nop
0x180118065  add     rsp, 20h
0x180118069  pop     rbp
0x18011806a  retn
```
