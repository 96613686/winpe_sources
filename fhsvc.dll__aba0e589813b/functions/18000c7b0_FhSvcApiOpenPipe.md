# FhSvcApiOpenPipe

- ea: `0x18000c7b0`
- end: `0x18000ca0d`
- name: `FhSvcApiOpenPipe`
- size: `605`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, HANDLE **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000c7b0`
- `0x18000ca14`
- `0x18000d0a8`
- `0x18000daf0`
- `0x18000dd60`
- `0x18000eb44`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18000c8e5`
- `ADVAPI32!OpenThreadToken` at `0x18000c8e5`
- `KERNEL32!GetLastError` at `0x18000c8ef`
- `KERNEL32!GetLastError` at `0x18000c8ef`
- `KERNEL32!GetCurrentThread` at `0x18000c8d0`
- `KERNEL32!GetCurrentThread` at `0x18000c8d0`
- `RPCRT4!RpcStringFreeW` at `0x18000c9df`
- `RPCRT4!RpcStringFreeW` at `0x18000c9df`
- `RPCRT4!RpcRevertToSelf` at `0x18000c927`
- `RPCRT4!RpcRevertToSelf` at `0x18000c965`
- `RPCRT4!RpcRevertToSelf` at `0x18000c927`
- `RPCRT4!RpcRevertToSelf` at `0x18000c965`
- `RPCRT4!RpcImpersonateClient` at `0x18000c898`
- `RPCRT4!RpcImpersonateClient` at `0x18000c898`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000c7d2`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000c7d2`

## pseudocode

```c
__int64 __fastcall FhSvcApiOpenPipe(RPC_BINDING_HANDLE BindingHandle, HANDLE **a2)
{
  int v4; // eax
  int v5; // r8d
  PVOID *v6; // rcx
  HANDLE *v7; // rax
  HANDLE *v8; // rdi
  RPC_STATUS v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v15; // eax
  __int64 v16; // r9
  RPC_STATUS v17; // eax
  RPC_WSTR StringBinding; // [rsp+78h] [rbp+10h] BYREF

  StringBinding = 0;
  v4 = RpcBindingToStringBindingW(BindingHandle, &StringBinding);
  if ( !v4 )
  {
LABEL_7:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_efece49b8938379c060169b7945fb4b7_Traceguids,
      (unsigned int)v4);
    goto LABEL_7;
  }
LABEL_8:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_qS((unsigned int)v6[2], 27, v5, (_DWORD)BindingHandle, (__int64)StringBinding);
LABEL_11:
  *a2 = 0;
  v7 = (HANDLE *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[1] = 0;
    v7[2] = 0;
    *(_OWORD *)v7 = 0;
    *((_OWORD *)v7 + 1) = 0;
    *a2 = v7;
    _InterlockedIncrement(&dword_1800199E8);
    v9 = RpcImpersonateClient(BindingHandle);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 29;
LABEL_37:
        v16 = v10;
LABEL_38:
        WPP_SF_d(v11[2], v12, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, v16);
      }
    }
    else
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xCu, 1, v8) )
      {
        v10 = 0;
        v17 = RpcRevertToSelf();
        if ( v17 )
        {
          v10 = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 31;
            goto LABEL_37;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, v10);
        v15 = RpcRevertToSelf();
        if ( v15 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            if ( v15 > 0 )
              v15 = (unsigned __int16)v15 | 0x80070000;
            v12 = 32;
            v16 = (unsigned int)v15;
            goto LABEL_38;
          }
        }
      }
    }
  }
  else
  {
    v10 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, "pipeContext");
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( (v10 & 0x80000000) != 0 && *a2 )
  {
    FHSVC_PIPE_HANDLE_rundown();
    *a2 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18000c7b0  push    rbx
0x18000c7b2  push    rsi
0x18000c7b3  push    rdi
0x18000c7b4  push    r12
0x18000c7b6  push    r13
0x18000c7b8  push    r15
0x18000c7ba  sub     rsp, 38h
0x18000c7be  mov     rsi, rdx
0x18000c7c1  mov     [rsp+68h+StringBinding], 0
0x18000c7ca  lea     rdx, [rsp+68h+StringBinding]; StringBinding
0x18000c7cf  mov     rbx, rcx
0x18000c7d2  call    cs:__imp_RpcBindingToStringBindingW
0x18000c7d8  mov     r12d, 80070000h
0x18000c7de  lea     r13, WPP_efece49b8938379c060169b7945fb4b7_Traceguids
0x18000c7e5  lea     r15, WPP_GLOBAL_Control
0x18000c7ec  test    eax, eax
0x18000c7ee  jz      short loc_18000C820
0x18000c7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7f7  cmp     rcx, r15
0x18000c7fa  jz      short loc_18000C84D
0x18000c7fc  test    byte ptr [rcx+1Ch], 1
0x18000c800  jz      short loc_18000C827
0x18000c802  test    eax, eax
0x18000c804  jle     short loc_18000C80C
0x18000c806  movzx   eax, ax
0x18000c809  or      eax, r12d
0x18000c80c  mov     rcx, [rcx+10h]
0x18000c810  mov     edx, 1Ah
0x18000c815  mov     r9d, eax
0x18000c818  mov     r8, r13
0x18000c81b  call    WPP_SF_d
0x18000c820  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c827  cmp     rcx, r15
0x18000c82a  jz      short loc_18000C84D
0x18000c82c  test    byte ptr [rcx+1Ch], 8
0x18000c830  jz      short loc_18000C84D
0x18000c832  mov     rax, [rsp+68h+StringBinding]
0x18000c837  mov     edx, 1Bh
0x18000c83c  mov     rcx, [rcx+10h]
0x18000c840  mov     r9, rbx
0x18000c843  mov     [rsp+68h+var_48], rax
0x18000c848  call    WPP_SF_qS
0x18000c84d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c854  mov     qword ptr [rsi], 0
0x18000c85b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c860  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c865  mov     rdi, rax
0x18000c868  test    rax, rax
0x18000c86b  jz      loc_18000C9A3
0x18000c871  mov     qword ptr [rax+8], 0
0x18000c879  xorps   xmm0, xmm0
0x18000c87c  mov     qword ptr [rax+10h], 0
0x18000c884  movups  xmmword ptr [rax], xmm0
0x18000c887  movups  xmmword ptr [rax+10h], xmm0
0x18000c88b  mov     [rsi], rax
0x18000c88e  lock inc cs:dword_1800199E8
0x18000c895  mov     rcx, rbx; BindingHandle
0x18000c898  call    cs:__imp_RpcImpersonateClient
0x18000c89e  mov     ebx, eax
0x18000c8a0  test    eax, eax
0x18000c8a2  jz      short loc_18000C8D0
0x18000c8a4  jle     short loc_18000C8AC
0x18000c8a6  movzx   ebx, ax
0x18000c8a9  or      ebx, r12d
0x18000c8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8b3  cmp     rcx, r15
0x18000c8b6  jz      loc_18000C9D2
0x18000c8bc  test    byte ptr [rcx+1Ch], 1
0x18000c8c0  jz      loc_18000C9D2
0x18000c8c6  mov     edx, 1Dh
0x18000c8cb  jmp     loc_18000C992
0x18000c8d0  call    cs:__imp_GetCurrentThread
0x18000c8d6  mov     edx, 0Ch; DesiredAccess
0x18000c8db  mov     r9, rdi; TokenHandle
0x18000c8de  mov     rcx, rax; ThreadHandle
0x18000c8e1  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18000c8e5  call    cs:__imp_OpenThreadToken
0x18000c8eb  test    eax, eax
0x18000c8ed  jnz     short loc_18000C963
0x18000c8ef  call    cs:__imp_GetLastError
0x18000c8f5  mov     ebx, eax
0x18000c8f7  test    eax, eax
0x18000c8f9  jle     short loc_18000C901
0x18000c8fb  movzx   ebx, ax
0x18000c8fe  or      ebx, r12d
0x18000c901  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c908  cmp     rcx, r15
0x18000c90b  jz      short loc_18000C927
0x18000c90d  test    byte ptr [rcx+1Ch], 1
0x18000c911  jz      short loc_18000C927
0x18000c913  mov     rcx, [rcx+10h]
0x18000c917  mov     edx, 1Eh
0x18000c91c  mov     r9d, ebx
0x18000c91f  mov     r8, r13
0x18000c922  call    WPP_SF_d
0x18000c927  call    cs:__imp_RpcRevertToSelf
0x18000c92d  test    eax, eax
0x18000c92f  jz      loc_18000C9D2
0x18000c935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c93c  cmp     rcx, r15
0x18000c93f  jz      loc_18000C9D2
0x18000c945  test    byte ptr [rcx+1Ch], 1
0x18000c949  jz      loc_18000C9D2
0x18000c94f  test    eax, eax
0x18000c951  jle     short loc_18000C959
0x18000c953  movzx   eax, ax
0x18000c956  or      eax, r12d
0x18000c959  mov     edx, 20h ; ' '
0x18000c95e  mov     r9d, eax
0x18000c961  jmp     short loc_18000C995
0x18000c963  xor     ebx, ebx
0x18000c965  call    cs:__imp_RpcRevertToSelf
0x18000c96b  test    eax, eax
0x18000c96d  jz      short loc_18000C9D2
0x18000c96f  jg      short loc_18000C975
0x18000c971  mov     ebx, eax
0x18000c973  jmp     short loc_18000C97B
0x18000c975  movzx   ebx, ax
0x18000c978  or      ebx, r12d
0x18000c97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c982  cmp     rcx, r15
0x18000c985  jz      short loc_18000C9D2
0x18000c987  test    byte ptr [rcx+1Ch], 1
0x18000c98b  jz      short loc_18000C9D2
0x18000c98d  mov     edx, 1Fh
0x18000c992  mov     r9d, ebx
0x18000c995  mov     rcx, [rcx+10h]
0x18000c999  mov     r8, r13
0x18000c99c  call    WPP_SF_d
0x18000c9a1  jmp     short loc_18000C9D2
0x18000c9a3  mov     ebx, 8007000Eh
0x18000c9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9af  cmp     rcx, r15
0x18000c9b2  jz      short loc_18000C9D2
0x18000c9b4  test    byte ptr [rcx+1Ch], 1
0x18000c9b8  jz      short loc_18000C9D2
0x18000c9ba  mov     rcx, [rcx+10h]
0x18000c9be  lea     r9, aPipecontext; "pipeContext"
0x18000c9c5  mov     edx, 1Ch
0x18000c9ca  mov     r8, r13
0x18000c9cd  call    WPP_SF_s
0x18000c9d2  cmp     [rsp+68h+StringBinding], 0
0x18000c9d8  jz      short loc_18000C9E5
0x18000c9da  lea     rcx, [rsp+68h+StringBinding]; String
0x18000c9df  call    cs:__imp_RpcStringFreeW
0x18000c9e5  test    ebx, ebx
0x18000c9e7  jns     short loc_18000C9FD
0x18000c9e9  mov     rcx, [rsi]
0x18000c9ec  test    rcx, rcx
0x18000c9ef  jz      short loc_18000C9FD
0x18000c9f1  call    FHSVC_PIPE_HANDLE_rundown
0x18000c9f6  mov     qword ptr [rsi], 0
0x18000c9fd  mov     eax, ebx
0x18000c9ff  add     rsp, 38h
0x18000ca03  pop     r15
0x18000ca05  pop     r13
0x18000ca07  pop     r12
0x18000ca09  pop     rdi
0x18000ca0a  pop     rsi
0x18000ca0b  pop     rbx
0x18000ca0c  retn
```
