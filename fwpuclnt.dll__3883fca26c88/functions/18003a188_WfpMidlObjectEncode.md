# WfpMidlObjectEncode

- ea: `0x18003a188`
- end: `0x18003a290`
- name: `WfpMidlObjectEncode`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180039ffc`

## callees

- `0x1800027f0`
- `0x1800034e0`
- `0x180007e38`
- `0x18003a188`
- `0x18004b010`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x18003a25d`
- `RPCRT4!MesHandleFree` at `0x18003a25d`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a1de`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18003a1de`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004a22a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004a22a`

## string_xrefs

- `0x18003a1f3`: `MesEncodeDynBufferHandleCreate`

## pseudocode

```c
__int64 WfpMidlObjectEncode(void (__fastcall *a1)(handle_t, __int64 *), ...)
{
  _DWORD *v1; // rsi
  LPVOID *v2; // r14
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned int v8; // [rsp+20h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-30h] BYREF
  handle_t Handle; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  va_list va; // [rsp+68h] [rbp+10h]
  LPVOID *v13; // [rsp+70h] [rbp+18h]
  _DWORD *v14; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v11 = va_arg(va1, _QWORD);
  v13 = va_arg(va1, LPVOID *);
  v14 = va_arg(va1, _DWORD *);
  v1 = v14;
  v2 = v13;
  lpMem = 0;
  v8 = 0;
  Handle = 0;
  *v13 = 0;
  *v1 = 0;
  v4 = MesEncodeDynBufferHandleCreate((char **)&lpMem, &v8, &Handle);
  if ( v4 )
  {
    v6 = WfpReportSysErrorAsWinError(v5, "MesEncodeDynBufferHandleCreate", v4);
  }
  else
  {
    a1(Handle, (__int64 *)va);
    v6 = 0;
    *v2 = lpMem;
    *v1 = v8;
  }
  if ( v6 )
    FwppDeepFree_GUID(lpMem);
  if ( Handle )
    MesHandleFree(Handle);
  if ( v6 )
    WfpReportError(v6, "WfpMidlObjectEncode");
  return v6;
}

```

## disassembly

```asm
0x18003a188  mov     rax, rsp
0x18003a18b  mov     [rax+8], rsi
0x18003a18f  mov     [rax+20h], r9
0x18003a193  mov     [rax+18h], r8
0x18003a197  mov     [rax+10h], rdx
0x18003a19b  push    rdi
0x18003a19c  push    r14
0x18003a19e  push    r15
0x18003a1a0  sub     rsp, 40h
0x18003a1a4  mov     rsi, r9
0x18003a1a7  mov     r14, r8
0x18003a1aa  mov     r15, rcx
0x18003a1ad  mov     qword ptr [rax-30h], 0
0x18003a1b5  mov     dword ptr [rax-38h], 0
0x18003a1bc  mov     qword ptr [rax-28h], 0
0x18003a1c4  mov     qword ptr [r8], 0
0x18003a1cb  mov     dword ptr [r9], 0
0x18003a1d2  lea     r8, [rax-28h]; pHandle
0x18003a1d6  lea     rdx, [rax-38h]; pEncodedSize
0x18003a1da  lea     rcx, [rax-30h]; pBuffer
0x18003a1de  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18003a1e5  nop     dword ptr [rax+rax+00h]
0x18003a1ea  mov     edi, eax
0x18003a1ec  test    eax, eax
0x18003a1ee  jz      short loc_18003A204
0x18003a1f0  mov     r8d, eax
0x18003a1f3  lea     rdx, aMesencodedynbu_0; "MesEncodeDynBufferHandleCreate"
0x18003a1fa  call    WfpReportSysErrorAsWinError
0x18003a1ff  mov     rdi, rax
0x18003a202  jmp     short loc_18003A244
0x18003a204  lea     rdx, [rsp+58h+arg_8]
0x18003a209  mov     rcx, [rsp+58h+Handle]
0x18003a20e  mov     rax, r15
0x18003a211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a216  jmp     short loc_18003A224
0x18003a218  mov     edi, eax
0x18003a21a  mov     rsi, [rsp+58h+arg_18]
0x18003a21f  mov     r14, [rsp+58h+arg_10]
0x18003a224  test    edi, edi
0x18003a226  jz      short loc_18003A234
0x18003a228  mov     r8d, edi
0x18003a22b  lea     rdx, aWfpMidlEncodeF; "WFP_MIDL_ENCODE_FN"
0x18003a232  jmp     short loc_18003A1FA
0x18003a234  xor     edi, edi
0x18003a236  mov     rax, [rsp+58h+lpMem]
0x18003a23b  mov     [r14], rax
0x18003a23e  mov     eax, [rsp+58h+var_38]
0x18003a242  mov     [rsi], eax
0x18003a244  test    rdi, rdi
0x18003a247  jz      short loc_18003A253
0x18003a249  mov     rcx, [rsp+58h+lpMem]; lpMem
0x18003a24e  call    FwppDeepFree_GUID
0x18003a253  mov     rcx, [rsp+58h+Handle]; Handle
0x18003a258  test    rcx, rcx
0x18003a25b  jz      short loc_18003A269
0x18003a25d  call    cs:__imp_MesHandleFree
0x18003a264  nop     dword ptr [rax+rax+00h]
0x18003a269  test    rdi, rdi
0x18003a26c  jz      short loc_18003A27D
0x18003a26e  lea     rdx, aWfpmidlobjecte; "WfpMidlObjectEncode"
0x18003a275  mov     rcx, rdi
0x18003a278  call    WfpReportError
0x18003a27d  mov     rax, rdi
0x18003a280  mov     rsi, [rsp+58h+arg_0]
0x18003a285  add     rsp, 40h
0x18003a289  pop     r15
0x18003a28b  pop     r14
0x18003a28d  pop     rdi
0x18003a28e  retn
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
