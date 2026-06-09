# CLoggedOnUsers::LogonRemotePowerShellSession(ulong,void *)

- ea: `0x1800c3cf0`
- end: `0x1800c3f31`
- name: `?LogonRemotePowerShellSession@CLoggedOnUsers@@QEAAJKPEAX@Z`
- size: `577`
- prototype: `__int64 __fastcall(CLoggedOnUsers *__hidden this, DWORD dwProcessId, void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800950e4`
- `0x1800afe74`
- `0x1800c2b1c`

## callees

- `0x180006640`
- `0x18007f860`
- `0x18009c008`
- `0x18009c770`
- `0x1800c1bbc`
- `0x1800c234c`
- `0x1800c3cf0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c3db6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c3db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dd2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800c3d2f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800c3d2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLoggedOnUsers::LogonRemotePowerShellSession(CLoggedOnUsers *this, DWORD dwProcessId, void *a3)
{
  HANDLE v4; // rax
  void *v5; // rbx
  unsigned int LastError; // eax
  unsigned int v7; // eax
  void *v8; // rax
  int v9; // eax
  __int64 result; // rax
  const ComError *v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-148h] BYREF
  void *v13; // [rsp+38h] [rbp-140h] BYREF
  const ComError *v14; // [rsp+40h] [rbp-138h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-128h] BYREF
  __int128 v16; // [rsp+58h] [rbp-120h]
  unsigned int v17; // [rsp+68h] [rbp-110h]
  int v18; // [rsp+6Ch] [rbp-10Ch]
  int v19; // [rsp+70h] [rbp-108h]
  void **v20; // [rsp+B0h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+B8h] [rbp-C0h]
  unsigned int v22; // [rsp+C8h] [rbp-B0h]
  int v23; // [rsp+CCh] [rbp-ACh]
  int v24; // [rsp+D0h] [rbp-A8h]
  void **v25; // [rsp+110h] [rbp-68h] BYREF
  __int128 v26; // [rsp+118h] [rbp-60h]
  int v27; // [rsp+128h] [rbp-50h]
  int v28; // [rsp+12Ch] [rbp-4Ch]
  int v29; // [rsp+130h] [rbp-48h]
  void *TokenHandle; // [rsp+190h] [rbp+18h] BYREF
  __int64 v31; // [rsp+198h] [rbp+20h] BYREF

  TokenHandle = 0;
  v12 = 0;
  v31 = 0;
  v4 = OpenProcess(0x101000u, 0, dwProcessId);
  try
  {
    v5 = v4;
    if ( !v4 )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v16 = 0;
      pExceptionObject = &ComError::`vftable';
      v17 = LastError;
      v18 = 367;
      v19 = 1;
      throw (ComError *)&pExceptionObject;
    }
    auto_HANDLE<0>::operator=(&v31, v4);
    if ( !OpenProcessToken(v5, 0xAu, &TokenHandle) )
    {
      if ( (int)GetLastError() > 0 )
        v7 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v7 = GetLastError();
      v21 = 0;
      v20 = &ComError::`vftable';
      v22 = v7;
      v23 = 373;
      v24 = 1;
      throw (ComError *)&v20;
    }
    auto_HANDLE<0>::operator=(&v12, TokenHandle);
    v8 = operator new(0x60u);
    v13 = v8;
    if ( v8 )
      RemotePowerShellSession::RemotePowerShellSession(v8, TokenHandle, v5);
    v31 = 0;
    v13 = 0;
    v9 = CLoggedOnUsers::LogonUserSession<unsigned long,RemotePowerShellSession>(
           this,
           (__int64)this + 64,
           (__int64)this + 88);
    if ( v9 < 0 )
    {
      v26 = 0;
      v25 = &ComError::`vftable';
      v27 = v9;
      v28 = 399;
      v29 = 1;
      throw (ComError *)&v25;
    }
    std::unique_ptr<EventLoggingCallbackWrapperContext>::~unique_ptr<EventLoggingCallbackWrapperContext>(&v13);
    auto_HANDLE<0>::~auto_HANDLE<0>(&v31);
    auto_HANDLE<0>::~auto_HANDLE<0>(&v12);
    result = 0;
  }
  catch ( const ComError *v14 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v11 = v14;
    }
    else
    {
      v11 = v14;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_2e76040e1cc638e8a403f6497772f07e_Traceguids,
        *((unsigned int *)v11 + 6),
        *((_DWORD *)v11 + 7));
    }
    LODWORD(TokenHandle) = *((_DWORD *)v11 + 6);
    return (unsigned int)TokenHandle;
  }
  return result;
}

```

## disassembly

```asm
0x1800c3cf0  mov     rax, rsp
0x1800c3cf3  mov     [rax+8], rbx
0x1800c3cf7  mov     [rax+10h], rsi
0x1800c3cfb  mov     [rax+18h], r8
0x1800c3cff  push    rdi
0x1800c3d00  sub     rsp, 170h
0x1800c3d07  mov     edi, edx
0x1800c3d09  mov     rsi, rcx
0x1800c3d0c  mov     qword ptr [rax+18h], 0
0x1800c3d14  mov     [rsp+178h+var_148], 0
0x1800c3d1d  mov     qword ptr [rax+20h], 0
0x1800c3d25  mov     r8d, edx; dwProcessId
0x1800c3d28  xor     edx, edx; bInheritHandle
0x1800c3d2a  mov     ecx, 101000h; dwDesiredAccess
0x1800c3d2f  call    cs:__imp_OpenProcess
0x1800c3d35  mov     rbx, rax
0x1800c3d38  test    rax, rax
0x1800c3d3b  jnz     short loc_1800C3D96
0x1800c3d3d  call    cs:__imp_GetLastError
0x1800c3d43  test    eax, eax
0x1800c3d45  jg      short loc_1800C3D4F
0x1800c3d47  call    cs:__imp_GetLastError
0x1800c3d4d  jmp     short loc_1800C3D5D
0x1800c3d4f  call    cs:__imp_GetLastError
0x1800c3d55  movzx   eax, ax
0x1800c3d58  or      eax, 80070000h
0x1800c3d5d  xorps   xmm0, xmm0
0x1800c3d60  movups  [rsp+178h+var_120], xmm0
0x1800c3d65  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3d6c  mov     [rsp+178h+pExceptionObject], rcx
0x1800c3d71  mov     [rsp+178h+var_110], eax
0x1800c3d75  mov     [rsp+178h+var_10C], 16Fh
0x1800c3d7d  mov     [rsp+178h+var_108], 1
0x1800c3d85  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3d8c  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x1800c3d91  call    _CxxThrowException_0
0x1800c3d96  mov     rdx, rbx
0x1800c3d99  lea     rcx, [rsp+178h+arg_18]
0x1800c3da1  call    ??4?$auto_HANDLE@$0A@@@QEAAAEAV0@PEAX@Z; auto_HANDLE<0>::operator=(void *)
0x1800c3da6  lea     r8, [rsp+178h+TokenHandle]; TokenHandle
0x1800c3dae  mov     edx, 0Ah; DesiredAccess
0x1800c3db3  mov     rcx, rbx; ProcessHandle
0x1800c3db6  call    cs:__imp_OpenProcessToken
0x1800c3dbc  test    eax, eax
0x1800c3dbe  jnz     short loc_1800C3E2B
0x1800c3dc0  call    cs:__imp_GetLastError
0x1800c3dc6  test    eax, eax
0x1800c3dc8  jg      short loc_1800C3DD2
0x1800c3dca  call    cs:__imp_GetLastError
0x1800c3dd0  jmp     short loc_1800C3DE0
0x1800c3dd2  call    cs:__imp_GetLastError
0x1800c3dd8  movzx   eax, ax
0x1800c3ddb  or      eax, 80070000h
0x1800c3de0  xorps   xmm0, xmm0
0x1800c3de3  movups  [rsp+178h+var_C0], xmm0
0x1800c3deb  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3df2  mov     [rsp+178h+var_C8], rcx
0x1800c3dfa  mov     [rsp+178h+var_B0], eax
0x1800c3e01  mov     [rsp+178h+var_AC], 175h
0x1800c3e0c  mov     [rsp+178h+var_A8], 1
0x1800c3e17  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3e1e  lea     rcx, [rsp+178h+var_C8]; pExceptionObject
0x1800c3e26  call    _CxxThrowException_0
0x1800c3e2b  mov     rdx, [rsp+178h+TokenHandle]
0x1800c3e33  lea     rcx, [rsp+178h+var_148]
0x1800c3e38  call    ??4?$auto_HANDLE@$0A@@@QEAAAEAV0@PEAX@Z; auto_HANDLE<0>::operator=(void *)
0x1800c3e3d  mov     ecx, 60h ; '`'; dwBytes
0x1800c3e42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c3e47  mov     [rsp+178h+var_140], rax
0x1800c3e4c  test    rax, rax
0x1800c3e4f  jz      short loc_1800C3E69
0x1800c3e51  mov     r8, rbx; void *
0x1800c3e54  mov     rdx, [rsp+178h+TokenHandle]; void *
0x1800c3e5c  mov     rcx, rax; Context
0x1800c3e5f  call    ??0RemotePowerShellSession@@QEAA@PEAX0@Z; RemotePowerShellSession::RemotePowerShellSession(void *,void *)
0x1800c3e64  mov     rdx, rax
0x1800c3e67  jmp     short loc_1800C3E6B
0x1800c3e69  xor     edx, edx
0x1800c3e6b  mov     [rsp+178h+arg_18], 0
0x1800c3e77  mov     [rsp+178h+var_140], 0
0x1800c3e80  lea     rax, [rsi+58h]
0x1800c3e84  lea     rcx, [rsi+40h]
0x1800c3e88  mov     [rsp+178h+var_150], rax; __int64
0x1800c3e8d  mov     [rsp+178h+var_158], rcx; __int64
0x1800c3e92  mov     r9d, edi
0x1800c3e95  mov     rcx, rsi; this
0x1800c3e98  call    ??$LogonUserSession@KVRemotePowerShellSession@@@CLoggedOnUsers@@QEAAJPEAVRemotePowerShellSession@@W4UserSessionType@@KAEAV?$CUserSessionMap@KVRemotePowerShellSession@@@@AEAV?$CUserList@VRemotePowerShellSession@@@@@Z; CLoggedOnUsers::LogonUserSession<ulong,RemotePowerShellSession>(RemotePowerShellSession *,UserSessionType,ulong,CUserSessionMap<ulong,RemotePowerShellSession> &,CUserList<RemotePowerShellSession> &)
0x1800c3e9d  test    eax, eax
0x1800c3e9f  jns     short loc_1800C3EED
0x1800c3ea1  xorps   xmm0, xmm0
0x1800c3ea4  movups  [rsp+178h+var_60], xmm0
0x1800c3eac  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800c3eb3  mov     [rsp+178h+var_68], rcx
0x1800c3ebb  mov     [rsp+178h+var_50], eax
0x1800c3ec2  mov     [rsp+178h+var_4C], 18Fh
0x1800c3ecd  mov     [rsp+178h+var_48], 1
0x1800c3ed8  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800c3edf  lea     rcx, [rsp+178h+var_68]; pExceptionObject
0x1800c3ee7  call    _CxxThrowException_0
0x1800c3eed  lea     rcx, [rsp+178h+var_140]
0x1800c3ef2  call    ??1?$unique_ptr@UEventLoggingCallbackWrapperContext@@U?$default_delete@UEventLoggingCallbackWrapperContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<EventLoggingCallbackWrapperContext>::~unique_ptr<EventLoggingCallbackWrapperContext>(void)
0x1800c3ef7  nop
0x1800c3ef8  lea     rcx, [rsp+178h+arg_18]
0x1800c3f00  call    ??1?$auto_HANDLE@$0A@@@QEAA@XZ; auto_HANDLE<0>::~auto_HANDLE<0>(void)
0x1800c3f05  nop
0x1800c3f06  lea     rcx, [rsp+178h+var_148]
0x1800c3f0b  call    ??1?$auto_HANDLE@$0A@@@QEAA@XZ; auto_HANDLE<0>::~auto_HANDLE<0>(void)
0x1800c3f10  xor     eax, eax
0x1800c3f12  jmp     short loc_1800C3F1B
0x1800c3f14  mov     eax, dword ptr [rsp+178h+TokenHandle]
0x1800c3f1b  lea     r11, [rsp+178h+var_8]
0x1800c3f23  mov     rbx, [r11+10h]
0x1800c3f27  mov     rsi, [r11+18h]
0x1800c3f2b  mov     rsp, r11
0x1800c3f2e  pop     rdi
0x1800c3f2f  retn
```
