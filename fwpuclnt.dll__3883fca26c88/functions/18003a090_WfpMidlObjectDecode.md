# WfpMidlObjectDecode

- ea: `0x18003a090`
- end: `0x18003a182`
- name: `WfpMidlObjectDecode`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180039ffc`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x180011500`
- `0x18003a090`
- `0x18004b010`

## import_xrefs

- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003a0d0`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18003a0d0`
- `RPCRT4!MesHandleFree` at `0x18003a14e`
- `RPCRT4!MesHandleFree` at `0x18003a14e`

## string_xrefs

- `0x18003a0e5`: `MesDecodeBufferHandleCreate`

## pseudocode

```c
__int64 __fastcall WfpMidlObjectDecode(
        void (__fastcall *a1)(handle_t, __int64 *),
        char *a2,
        unsigned int a3,
        _QWORD *a4)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  handle_t Handle; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+28h] [rbp-10h] BYREF

  v13 = 0;
  Handle = 0;
  *a4 = 0;
  v6 = MesDecodeBufferHandleCreate(a2, a3, &Handle);
  if ( v6 )
  {
    v8 = WfpReportSysErrorAsWinError(v7, "MesDecodeBufferHandleCreate", v6);
LABEL_3:
    v9 = v8;
    goto LABEL_7;
  }
  a1(Handle, &v13);
  if ( !v13 )
  {
    v8 = WfpReportSysErrorAsNtStatus(v10, "WfpMidlObjectDecode", 3221225495LL);
    goto LABEL_3;
  }
  v9 = 0;
  *a4 = v13;
LABEL_7:
  if ( Handle )
    MesHandleFree(Handle);
  if ( v9 )
    WfpReportError(v9, "WfpMidlObjectDecode");
  return v9;
}

```

## disassembly

```asm
0x18003a090  mov     r11, rsp
0x18003a093  mov     [r11+8], rbx
0x18003a097  mov     [r11+10h], rsi
0x18003a09b  mov     [r11+20h], r9
0x18003a09f  push    rdi
0x18003a0a0  sub     rsp, 30h
0x18003a0a4  mov     rdi, r9
0x18003a0a7  mov     eax, r8d
0x18003a0aa  mov     r10, rdx
0x18003a0ad  mov     rsi, rcx
0x18003a0b0  mov     qword ptr [r11-10h], 0
0x18003a0b8  mov     qword ptr [r11-18h], 0
0x18003a0c0  mov     qword ptr [r9], 0
0x18003a0c7  lea     r8, [r11-18h]; pHandle
0x18003a0cb  mov     edx, eax; BufferSize
0x18003a0cd  mov     rcx, r10; Buffer
0x18003a0d0  call    cs:__imp_MesDecodeBufferHandleCreate
0x18003a0d7  nop     dword ptr [rax+rax+00h]
0x18003a0dc  mov     ebx, eax
0x18003a0de  test    eax, eax
0x18003a0e0  jz      short loc_18003A0F6
0x18003a0e2  mov     r8d, eax
0x18003a0e5  lea     rdx, aMesdecodebuffe_0; "MesDecodeBufferHandleCreate"
0x18003a0ec  call    WfpReportSysErrorAsWinError
0x18003a0f1  mov     rbx, rax
0x18003a0f4  jmp     short loc_18003A144
0x18003a0f6  lea     rdx, [rsp+38h+var_10]
0x18003a0fb  mov     rcx, [rsp+38h+Handle]
0x18003a100  mov     rax, rsi
0x18003a103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a108  jmp     short loc_18003A111
0x18003a10a  mov     ebx, eax
0x18003a10c  mov     rdi, [rsp+38h+arg_18]
0x18003a111  test    ebx, ebx
0x18003a113  jz      short loc_18003A121
0x18003a115  mov     r8d, ebx
0x18003a118  lea     rdx, aWfpMidlDecodeF; "WFP_MIDL_DECODE_FN"
0x18003a11f  jmp     short loc_18003A0EC
0x18003a121  mov     rax, [rsp+38h+var_10]
0x18003a126  test    rax, rax
0x18003a129  jnz     short loc_18003A13F
0x18003a12b  mov     r8d, 0C0000017h
0x18003a131  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18003a138  call    WfpReportSysErrorAsNtStatus
0x18003a13d  jmp     short loc_18003A0F1
0x18003a13f  xor     ebx, ebx
0x18003a141  mov     [rdi], rax
0x18003a144  mov     rcx, [rsp+38h+Handle]; Handle
0x18003a149  test    rcx, rcx
0x18003a14c  jz      short loc_18003A15A
0x18003a14e  call    cs:__imp_MesHandleFree
0x18003a155  nop     dword ptr [rax+rax+00h]
0x18003a15a  test    rbx, rbx
0x18003a15d  jz      short loc_18003A16E
0x18003a15f  lea     rdx, aWfpmidlobjectd; "WfpMidlObjectDecode"
0x18003a166  mov     rcx, rbx
0x18003a169  call    WfpReportError
0x18003a16e  mov     rax, rbx
0x18003a171  mov     rbx, [rsp+38h+arg_0]
0x18003a176  mov     rsi, [rsp+38h+arg_8]
0x18003a17b  add     rsp, 30h
0x18003a17f  pop     rdi
0x18003a180  retn
0x18004a21c  push    rbp
0x18004a21e  sub     rsp, 20h
0x18004a222  mov     rbp, rdx
0x18004a225  mov     rcx, [rcx]
0x18004a228  mov     ecx, [rcx]; ExceptionCode
0x18004a22a  call    cs:__imp_I_RpcExceptionFilter
0x18004a231  nop     dword ptr [rax+rax+00h]
0x18004a236  nop
0x18004a237  add     rsp, 20h
0x18004a23b  pop     rbp
0x18004a23c  retn
```
