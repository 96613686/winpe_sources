# CWinHttpRequest::ReadData(void *,ulong,ulong *)

- ea: `0x180010f30`
- end: `0x180011095`
- name: `?ReadData@CWinHttpRequest@@UEAAHPEAXKPEAK@Z`
- size: `357`
- prototype: `__int64 __fastcall(CWinHttpRequest *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010f30`
- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010f74`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010f90`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010f90`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010fb3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f9a`
- `WINHTTP!WinHttpReadData` at `0x180011052`
- `WINHTTP!WinHttpReadData` at `0x180011052`

## string_xrefs

- `0x180010fc2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWinHttpRequest::ReadData(CWinHttpRequest *this, void *a2, DWORD a3, unsigned int *a4)
{
  __int64 v8; // rbx
  void *v9; // rdi
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // esi
  __int64 v14; // rdi
  void *v15; // rdx
  unsigned int Data; // ebp
  void **pExceptionObject; // [rsp+30h] [rbp-88h] BYREF
  __int128 v19; // [rsp+38h] [rbp-80h]
  int v20; // [rsp+48h] [rbp-70h]
  int v21; // [rsp+4Ch] [rbp-6Ch]
  int v22; // [rsp+50h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  void *TokenHandle; // [rsp+C0h] [rbp+8h] BYREF

  v8 = -1;
  v9 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, v9) )
    {
      v8 = (__int64)TokenHandle;
      goto LABEL_9;
    }
    v12 = 454;
  }
  else
  {
    v12 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v12,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( LastError < 0 )
  {
    v19 = 0;
    pExceptionObject = &ComError::`vftable';
    v20 = LastError;
    v21 = 2160;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
LABEL_9:
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v14 + 8));
  Data = WinHttpReadData(*((HINTERNET *)this + 2), a2, a3, a4);
  if ( v14 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v14 + 8));
  if ( v8 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v8, v15);
  return Data;
}

```

## disassembly

```asm
0x180010f30  mov     [rsp+arg_8], rbx
0x180010f35  mov     [rsp+arg_10], rbp
0x180010f3a  push    rsi
0x180010f3b  push    rdi
0x180010f3c  push    r12
0x180010f3e  push    r14
0x180010f40  push    r15
0x180010f42  sub     rsp, 90h
0x180010f49  mov     r14, r9
0x180010f4c  mov     r15d, r8d
0x180010f4f  mov     r12, rdx
0x180010f52  mov     rbp, rcx
0x180010f55  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180010f5c  mov     [rsp+0B8h+var_98], rbx
0x180010f61  mov     rax, [rcx+8]
0x180010f65  mov     rdi, [rax]
0x180010f68  mov     [rsp+0B8h+TokenHandle], 0
0x180010f74  call    cs:__imp_GetCurrentThread
0x180010f7a  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180010f82  mov     edx, 0F01FFh; DesiredAccess
0x180010f87  mov     r8d, 1; OpenAsSelf
0x180010f8d  mov     rcx, rax; ThreadHandle
0x180010f90  call    cs:__imp_OpenThreadToken
0x180010f96  test    eax, eax
0x180010f98  jnz     short loc_180010FAE
0x180010f9a  call    cs:__imp_GetLastError
0x180010fa0  cmp     eax, 3F0h
0x180010fa5  jz      short loc_180010FAE
0x180010fa7  mov     edx, 1C2h
0x180010fac  jmp     short loc_180010FC2
0x180010fae  mov     rdx, rdi; Token
0x180010fb1  xor     ecx, ecx; Thread
0x180010fb3  call    cs:__imp_SetThreadToken
0x180010fb9  test    eax, eax
0x180010fbb  jnz     short loc_180011026
0x180010fbd  mov     edx, 1C6h; void *
0x180010fc2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010fc9  mov     rcx, [rsp+0B8h]; this
0x180010fd1  lea     rdi, [rsp+0B8h+TokenHandle]
0x180010fd9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010fde  mov     esi, eax
0x180010fe0  mov     rcx, rdi
0x180010fe3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010fe8  test    esi, esi
0x180010fea  jns     short loc_180011033
0x180010fec  xorps   xmm0, xmm0
0x180010fef  movups  [rsp+0B8h+var_80], xmm0
0x180010ff4  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180010ffb  mov     [rsp+0B8h+pExceptionObject], rax
0x180011000  mov     [rsp+0B8h+var_70], esi
0x180011004  mov     [rsp+0B8h+var_6C], 870h
0x18001100c  mov     [rsp+0B8h+var_68], 1
0x180011014  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001101b  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180011020  call    _CxxThrowException_0
0x180011026  mov     rbx, [rsp+0B8h+TokenHandle]
0x18001102e  mov     [rsp+0B8h+var_98], rbx
0x180011033  mov     rdi, [rbp+20h]
0x180011037  test    rdi, rdi
0x18001103a  jz      short loc_180011045
0x18001103c  mov     rcx, [rdi+8]; this
0x180011040  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180011045  mov     r9, r14; lpdwNumberOfBytesRead
0x180011048  mov     r8d, r15d; dwNumberOfBytesToRead
0x18001104b  mov     rdx, r12; lpBuffer
0x18001104e  mov     rcx, [rbp+10h]; hRequest
0x180011052  call    cs:__imp_WinHttpReadData
0x180011058  mov     ebp, eax
0x18001105a  test    rdi, rdi
0x18001105d  jz      short loc_180011069
0x18001105f  mov     rcx, [rdi+8]; this
0x180011063  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180011068  nop
0x180011069  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001106d  jz      short loc_180011077
0x18001106f  mov     rcx, rbx; Token
0x180011072  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180011077  mov     eax, ebp
0x180011079  lea     r11, [rsp+0B8h+var_28]
0x180011081  mov     rbx, [r11+38h]
0x180011085  mov     rbp, [r11+40h]
0x180011089  mov     rsp, r11
0x18001108c  pop     r15
0x18001108e  pop     r14
0x180011090  pop     r12
0x180011092  pop     rdi
0x180011093  pop     rsi
0x180011094  retn
```
