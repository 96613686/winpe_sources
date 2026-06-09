# AppContainerRegistrationHelper::LogSuccess(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)

- ea: `0x18000c250`
- end: `0x18000c438`
- name: `?LogSuccess@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z`
- size: `488`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d610`
- `0x18000d980`
- `0x18000e650`
- `0x18000ea1c`
- `0x180015da0`
- `0x1800162d0`

## callees

- `0x18000c250`
- `0x18001b948`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18000c2c4`
- `ntdll!EtwEventRegister` at `0x18000c2c4`
- `ntdll!EtwEventWrite` at `0x18000c2fe`
- `ntdll!EtwEventWrite` at `0x18000c2fe`
- `ntdll!EtwEventUnregister` at `0x18000c30f`
- `ntdll!EtwEventUnregister` at `0x18000c30f`
- `ntdll!EtwEventWriteTransfer` at `0x18000c403`
- `ntdll!EtwEventWriteTransfer` at `0x18000c403`

## pseudocode

```c
void __fastcall AppContainerRegistrationHelper::LogSuccess(
        const struct _EVENT_DESCRIPTOR *a1,
        unsigned __int16 *a2,
        const struct _GUID *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 *v6; // rdi
  bool v8; // zf
  unsigned int v9; // eax
  unsigned int v10; // r8d
  int v11; // ebx
  unsigned int v12; // [rsp+20h] [rbp-98h]
  unsigned int v13; // [rsp+30h] [rbp-88h]
  __int64 v14; // [rsp+38h] [rbp-80h] BYREF
  _DWORD v15[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v16; // [rsp+48h] [rbp-70h]
  const unsigned __int16 *v17; // [rsp+50h] [rbp-68h] BYREF
  int v18; // [rsp+58h] [rbp-60h]
  int v19; // [rsp+5Ch] [rbp-5Ch]
  int *v20; // [rsp+60h] [rbp-58h] BYREF
  int v21; // [rsp+68h] [rbp-50h]
  int v22; // [rsp+6Ch] [rbp-4Ch]
  int *v23; // [rsp+70h] [rbp-48h]
  __int64 v24; // [rsp+78h] [rbp-40h]
  __int64 *v25; // [rsp+80h] [rbp-38h]
  int v26; // [rsp+88h] [rbp-30h]
  int v27; // [rsp+8Ch] [rbp-2Ch]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = -1;
  v14 = 0;
  v4 = -1;
  v6 = (__int64 *)a2;
  do
    v8 = a2[++v4] == 0;
  while ( !v8 );
  v17 = a2;
  v18 = 2 * v4 + 2;
  v19 = 0;
  v9 = EtwEventRegister(AppModelRuntimeProviderId, 0, 0, &v14);
  if ( v9 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x6E, v10, (const char *)v9, v12);
  }
  else
  {
    EtwEventWrite(v14, a1, 1, &v17);
    EtwEventUnregister(v14);
  }
  if ( a3 && (unsigned int)dword_180031038 > 5 )
  {
    if ( v6 )
    {
      do
        v8 = *((_WORD *)v6 + ++v3) == 0;
      while ( !v8 );
      v11 = 2 * v3 + 2;
    }
    else
    {
      v6 = &qword_180026E50;
      v11 = 2;
    }
    v15[1] = 5;
    v20 = off_180031040;
    v25 = v6;
    v26 = v11;
    v27 = 0;
    v15[0] = 184549376;
    v16 = 0;
    v21 = *(unsigned __int16 *)off_180031040;
    v23 = &dword_18002B09C;
    v22 = 2;
    v24 = 0x10000001BLL;
    v13 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_180031058, v15, a3, 0, 3, &v20, v13);
  }
}

```

## disassembly

```asm
0x18000c250  mov     [rsp+arg_8], rbx
0x18000c255  mov     [rsp+arg_18], rbp
0x18000c25a  push    rsi
0x18000c25b  push    rdi
0x18000c25c  push    r14
0x18000c25e  sub     rsp, 0A0h
0x18000c265  mov     rax, cs:__security_cookie
0x18000c26c  xor     rax, rsp
0x18000c26f  mov     [rsp+0B8h+var_28], rax
0x18000c277  xor     r14d, r14d
0x18000c27a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c281  mov     [rsp+0B8h+var_80], r14
0x18000c286  mov     rax, rbx
0x18000c289  mov     rbp, r8
0x18000c28c  mov     rdi, rdx
0x18000c28f  mov     rsi, rcx
0x18000c292  cmp     [rdx+rax*2+2], r14w
0x18000c298  lea     rax, [rax+1]
0x18000c29c  jnz     short loc_18000C292
0x18000c29e  lea     eax, ds:2[rax*2]
0x18000c2a5  mov     [rsp+0B8h+var_68], rdi
0x18000c2aa  lea     r9, [rsp+0B8h+var_80]
0x18000c2af  mov     [rsp+0B8h+var_60], eax
0x18000c2b3  xor     r8d, r8d
0x18000c2b6  mov     [rsp+0B8h+var_5C], r14d
0x18000c2bb  xor     edx, edx
0x18000c2bd  lea     rcx, AppModelRuntimeProviderId
0x18000c2c4  call    cs:__imp_EtwEventRegister
0x18000c2cb  nop     dword ptr [rax+rax+00h]
0x18000c2d0  mov     rcx, [rsp+0B8h]; this
0x18000c2d8  test    eax, eax
0x18000c2da  jz      short loc_18000C2EB
0x18000c2dc  mov     r9d, eax; char *
0x18000c2df  mov     edx, 6Eh ; 'n'; void *
0x18000c2e4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000c2e9  jmp     short loc_18000C31B
0x18000c2eb  mov     rcx, [rsp+0B8h+var_80]
0x18000c2f0  lea     r9, [rsp+0B8h+var_68]
0x18000c2f5  mov     r8d, 1
0x18000c2fb  mov     rdx, rsi
0x18000c2fe  call    cs:__imp_EtwEventWrite
0x18000c305  nop     dword ptr [rax+rax+00h]
0x18000c30a  mov     rcx, [rsp+0B8h+var_80]
0x18000c30f  call    cs:__imp_EtwEventUnregister
0x18000c316  nop     dword ptr [rax+rax+00h]
0x18000c31b  test    rbp, rbp
0x18000c31e  jz      loc_18000C40F
0x18000c324  mov     eax, cs:dword_180031038
0x18000c32a  cmp     eax, 5
0x18000c32d  jbe     loc_18000C40F
0x18000c333  test    rdi, rdi
0x18000c336  jz      short loc_18000C355
0x18000c338  nop     dword ptr [rax+rax+00000000h]
0x18000c340  cmp     [rdi+rbx*2+2], r14w
0x18000c346  lea     rbx, [rbx+1]
0x18000c34a  jnz     short loc_18000C340
0x18000c34c  lea     ebx, ds:2[rbx*2]
0x18000c353  jmp     short loc_18000C361
0x18000c355  lea     rdi, qword_180026E50
0x18000c35c  mov     ebx, 2
0x18000c361  movzx   eax, cs:word_18002B092
0x18000c368  lea     rcx, _TraceLoggingMetadata
0x18000c36f  mov     [rsp+0B8h+var_74], eax
0x18000c373  lea     rdx, [rsp+0B8h+var_78]
0x18000c378  mov     rax, cs:off_180031040
0x18000c37f  xor     r9d, r9d
0x18000c382  mov     [rsp+0B8h+var_58], rax
0x18000c387  mov     r8, rbp
0x18000c38a  mov     [rsp+0B8h+var_38], rdi
0x18000c392  mov     [rsp+0B8h+var_30], ebx
0x18000c399  mov     [rsp+0B8h+var_2C], r14d
0x18000c3a1  mov     [rsp+0B8h+var_78], 0B000000h
0x18000c3a9  mov     [rsp+0B8h+var_70], r14
0x18000c3ae  movzx   eax, word ptr [rax]
0x18000c3b1  mov     [rsp+0B8h+var_50], eax
0x18000c3b5  lea     rax, dword_18002B09C
0x18000c3bc  mov     [rsp+0B8h+var_48], rax
0x18000c3c1  lea     rax, _TraceLoggingMetadataEnd
0x18000c3c8  sub     eax, ecx
0x18000c3ca  mov     [rsp+0B8h+var_4C], 2
0x18000c3d2  mov     dword ptr [rsp+0B8h+var_40], 1Bh
0x18000c3da  mov     dword ptr [rsp+0B8h+var_40+4], 1
0x18000c3e2  mov     [rsp+0B8h+var_88], eax
0x18000c3e6  mov     eax, [rsp+0B8h+var_88]
0x18000c3ea  mov     rcx, cs:qword_180031058
0x18000c3f1  lea     rax, [rsp+0B8h+var_58]
0x18000c3f6  mov     [rsp+0B8h+var_90], rax
0x18000c3fb  mov     [rsp+0B8h+var_98], 3
0x18000c403  call    cs:__imp_EtwEventWriteTransfer
0x18000c40a  nop     dword ptr [rax+rax+00h]
0x18000c40f  mov     rcx, [rsp+0B8h+var_28]
0x18000c417  xor     rcx, rsp; StackCookie
0x18000c41a  call    __security_check_cookie
0x18000c41f  lea     r11, [rsp+0B8h+var_18]
0x18000c427  mov     rbx, [r11+28h]
0x18000c42b  mov     rbp, [r11+38h]
0x18000c42f  mov     rsp, r11
0x18000c432  pop     r14
0x18000c434  pop     rdi
0x18000c435  pop     rsi
0x18000c436  retn
```
