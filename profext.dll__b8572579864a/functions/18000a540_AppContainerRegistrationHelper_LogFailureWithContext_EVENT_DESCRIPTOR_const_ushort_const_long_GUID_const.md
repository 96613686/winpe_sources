# AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)

- ea: `0x18000a540`
- end: `0x18000a72b`
- name: `?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z`
- size: `491`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, int, const struct _GUID *)`
- caller_count: `17`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a18c`
- `0x18000a3e4`
- `0x18000d610`
- `0x18000d980`
- `0x18000e430`
- `0x18000e4d0`
- `0x18000e570`
- `0x18000e650`
- `0x18000ea1c`
- `0x18000f214`
- `0x180014750`
- `0x180014bd0`
- `0x1800153b8`
- `0x180015da0`
- `0x180015fe0`
- `0x1800162d0`
- `0x180016554`

## callees

- `0x18000a540`
- `0x18001b948`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18000a5ce`
- `ntdll!EtwEventRegister` at `0x18000a5ce`
- `ntdll!EtwEventWrite` at `0x18000a602`
- `ntdll!EtwEventWrite` at `0x18000a602`
- `ntdll!EtwEventUnregister` at `0x18000a612`
- `ntdll!EtwEventUnregister` at `0x18000a612`
- `ntdll!EtwEventWriteTransfer` at `0x18000a6fb`
- `ntdll!EtwEventWriteTransfer` at `0x18000a6fb`

## pseudocode

```c
void __fastcall AppContainerRegistrationHelper::LogFailureWithContext(
        const struct _EVENT_DESCRIPTOR *a1,
        unsigned __int16 *a2,
        int a3,
        const struct _GUID *a4)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 *v7; // rdi
  bool v9; // zf
  unsigned int v10; // eax
  unsigned int v11; // r8d
  int v12; // ebx
  unsigned int v13; // [rsp+20h] [rbp-69h]
  __int64 v14; // [rsp+30h] [rbp-59h] BYREF
  __int64 v15; // [rsp+38h] [rbp-51h] BYREF
  _DWORD v16[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+48h] [rbp-41h]
  _QWORD v18[3]; // [rsp+50h] [rbp-39h] BYREF
  int v19; // [rsp+68h] [rbp-21h]
  int v20; // [rsp+6Ch] [rbp-1Dh]
  int *v21; // [rsp+70h] [rbp-19h] BYREF
  int v22; // [rsp+78h] [rbp-11h]
  int v23; // [rsp+7Ch] [rbp-Dh]
  char *v24; // [rsp+80h] [rbp-9h]
  int v25; // [rsp+88h] [rbp-1h]
  int v26; // [rsp+8Ch] [rbp+3h]
  __int64 *v27; // [rsp+90h] [rbp+7h]
  int v28; // [rsp+98h] [rbp+Fh]
  int v29; // [rsp+9Ch] [rbp+13h]
  __int64 *v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v33; // [rsp+100h] [rbp+77h] BYREF

  v33 = a3;
  v18[1] = 4;
  v18[0] = &v33;
  v4 = -1;
  v15 = 0;
  v5 = -1;
  v7 = (__int64 *)a2;
  do
    v9 = a2[++v5] == 0;
  while ( !v9 );
  v18[2] = a2;
  v19 = 2 * v5 + 2;
  v20 = 0;
  v10 = EtwEventRegister(AppModelRuntimeProviderId, 0, 0, &v15);
  if ( v10 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0xB1, v11, (const char *)v10, v13);
  }
  else
  {
    EtwEventWrite(v15, a1, 2, v18);
    EtwEventUnregister(v15);
  }
  if ( a4 && (unsigned int)dword_180031038 > 5 )
  {
    LODWORD(v14) = v33;
    v30 = &v14;
    v31 = 4;
    if ( v7 )
    {
      do
        v9 = *((_WORD *)v7 + ++v4) == 0;
      while ( !v9 );
      v12 = 2 * v4 + 2;
    }
    else
    {
      v7 = &qword_180026E50;
      v12 = 2;
    }
    v16[1] = 5;
    v21 = off_180031040;
    v27 = v7;
    v28 = v12;
    v29 = 0;
    v16[0] = 184549376;
    v17 = 0;
    v22 = *(unsigned __int16 *)off_180031040;
    v24 = byte_18002B0C3;
    v23 = 2;
    v25 = 31;
    v26 = 1;
    HIDWORD(v14) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180031058, v16, a4, 0, 4, &v21, v14);
  }
}

```

## disassembly

```asm
0x18000a540  mov     [rsp-8+arg_8], rbx
0x18000a545  mov     [rsp-8+arg_10], r8d
0x18000a54a  push    rbp
0x18000a54b  push    rsi
0x18000a54c  push    rdi
0x18000a54d  push    r14
0x18000a54f  push    r15
0x18000a551  lea     rbp, [rsp-37h]
0x18000a556  sub     rsp, 0C0h
0x18000a55d  mov     rax, cs:__security_cookie
0x18000a564  xor     rax, rsp
0x18000a567  mov     [rbp+57h+var_30], rax
0x18000a56b  lea     rax, [rbp+57h+arg_10]
0x18000a56f  mov     [rbp+57h+var_88], 4
0x18000a577  xor     r15d, r15d
0x18000a57a  mov     [rbp+57h+var_90], rax
0x18000a57e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a585  mov     [rbp+57h+var_A8], r15
0x18000a589  mov     rax, rbx
0x18000a58c  mov     r14, r9
0x18000a58f  mov     rdi, rdx
0x18000a592  mov     rsi, rcx
0x18000a595  nop     word ptr [rax+rax+00000000h]
0x18000a5a0  cmp     [rdx+rax*2+2], r15w
0x18000a5a6  lea     rax, [rax+1]
0x18000a5aa  jnz     short loc_18000A5A0
0x18000a5ac  lea     eax, ds:2[rax*2]
0x18000a5b3  mov     [rbp+57h+var_80], rdi
0x18000a5b7  lea     r9, [rbp+57h+var_A8]
0x18000a5bb  mov     [rbp+57h+var_78], eax
0x18000a5be  xor     r8d, r8d
0x18000a5c1  mov     [rbp+57h+var_74], r15d
0x18000a5c5  xor     edx, edx
0x18000a5c7  lea     rcx, AppModelRuntimeProviderId
0x18000a5ce  call    cs:__imp_EtwEventRegister
0x18000a5d5  nop     dword ptr [rax+rax+00h]
0x18000a5da  mov     rcx, [rbp+5Fh]; this
0x18000a5de  test    eax, eax
0x18000a5e0  jz      short loc_18000A5F1
0x18000a5e2  mov     r9d, eax; char *
0x18000a5e5  mov     edx, 0B1h; void *
0x18000a5ea  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000a5ef  jmp     short loc_18000A61E
0x18000a5f1  mov     rcx, [rbp+57h+var_A8]
0x18000a5f5  lea     r9, [rbp+57h+var_90]
0x18000a5f9  mov     r8d, 2
0x18000a5ff  mov     rdx, rsi
0x18000a602  call    cs:__imp_EtwEventWrite
0x18000a609  nop     dword ptr [rax+rax+00h]
0x18000a60e  mov     rcx, [rbp+57h+var_A8]
0x18000a612  call    cs:__imp_EtwEventUnregister
0x18000a619  nop     dword ptr [rax+rax+00h]
0x18000a61e  test    r14, r14
0x18000a621  jz      loc_18000A707
0x18000a627  mov     eax, cs:dword_180031038
0x18000a62d  cmp     eax, 5
0x18000a630  jbe     loc_18000A707
0x18000a636  mov     eax, [rbp+57h+arg_10]
0x18000a639  mov     [rbp+57h+var_B0], eax
0x18000a63c  lea     rax, [rbp+57h+var_B0]
0x18000a640  mov     [rbp+57h+var_40], rax
0x18000a644  mov     [rbp+57h+var_38], 4
0x18000a64c  test    rdi, rdi
0x18000a64f  jz      short loc_18000A666
0x18000a651  cmp     [rdi+rbx*2+2], r15w
0x18000a657  lea     rbx, [rbx+1]
0x18000a65b  jnz     short loc_18000A651
0x18000a65d  lea     ebx, ds:2[rbx*2]
0x18000a664  jmp     short loc_18000A672
0x18000a666  lea     rdi, qword_180026E50
0x18000a66d  mov     ebx, 2
0x18000a672  movzx   eax, cs:word_18002B0B9
0x18000a679  lea     rcx, _TraceLoggingMetadata
0x18000a680  mov     [rbp+57h+var_9C], eax
0x18000a683  lea     rdx, [rbp+57h+var_A0]
0x18000a687  mov     rax, cs:off_180031040
0x18000a68e  xor     r9d, r9d
0x18000a691  mov     [rbp+57h+var_70], rax
0x18000a695  mov     r8, r14
0x18000a698  mov     [rbp+57h+var_50], rdi
0x18000a69c  mov     [rbp+57h+var_48], ebx
0x18000a69f  mov     [rbp+57h+var_44], r15d
0x18000a6a3  mov     [rbp+57h+var_A0], 0B000000h
0x18000a6aa  mov     [rbp+57h+var_98], r15
0x18000a6ae  movzx   eax, word ptr [rax]
0x18000a6b1  mov     [rbp+57h+var_68], eax
0x18000a6b4  lea     rax, byte_18002B0C3
0x18000a6bb  mov     [rbp+57h+var_60], rax
0x18000a6bf  lea     rax, _TraceLoggingMetadataEnd
0x18000a6c6  sub     eax, ecx
0x18000a6c8  mov     [rbp+57h+var_64], 2
0x18000a6cf  mov     [rbp+57h+var_58], 1Fh
0x18000a6d6  mov     [rbp+57h+var_54], 1
0x18000a6dd  mov     [rbp+57h+var_AC], eax
0x18000a6e0  mov     eax, [rbp+57h+var_AC]
0x18000a6e3  mov     rcx, cs:qword_180031058
0x18000a6ea  lea     rax, [rbp+57h+var_70]
0x18000a6ee  mov     [rsp+0E0h+var_B8], rax
0x18000a6f3  mov     [rsp+0E0h+var_C0], 4
0x18000a6fb  call    cs:__imp_EtwEventWriteTransfer
0x18000a702  nop     dword ptr [rax+rax+00h]
0x18000a707  mov     rcx, [rbp+57h+var_30]
0x18000a70b  xor     rcx, rsp; StackCookie
0x18000a70e  call    __security_check_cookie
0x18000a713  mov     rbx, [rsp+0E0h+arg_8]
0x18000a71b  add     rsp, 0C0h
0x18000a722  pop     r15
0x18000a724  pop     r14
0x18000a726  pop     rdi
0x18000a727  pop     rsi
0x18000a728  pop     rbp
0x18000a729  retn
```
