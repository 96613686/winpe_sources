# URLMONRequest::set_EDPClaim(void)

- ea: `0x18015d3e0`
- end: `0x18015d5da`
- name: `?set_EDPClaim@URLMONRequest@@UEAAJXZ`
- size: `506`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800bda70`
- `0x18015d3e0`
- `0x18017982c`
- `0x180179850`
- `0x180189008`
- `0x1801890e0`
- `0x18018a028`
- `0x18018c010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18015d4db`
- `ntdll!RtlNtStatusToDosError` at `0x18015d4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d462`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18015d452`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18015d452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015d435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18015d435`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015d570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015d570`

## pseudocode

```c
__int64 __fastcall URLMONRequest::set_EDPClaim(URLMONRequest *this)
{
  _UNICODE_STRING *v2; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v5; // edi
  __int64 v6; // rax
  int EnterpriseId; // ebx
  char v8; // al
  ULONG v9; // eax
  wchar_t *Buffer; // r9
  void *hThreadToken; // [rsp+40h] [rbp+8h] BYREF
  _UNICODE_STRING *pClaim; // [rsp+48h] [rbp+10h] BYREF
  _SUBJECT Subject; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  hThreadToken = 0;
  pClaim = 0;
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x49u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  this->Lock(this);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &hThreadToken) )
  {
    v6 = (__int64)hThreadToken;
    if ( !hThreadToken )
      v6 = -6;
    Subject.TokenHandle = (void *)v6;
    EnterpriseId = GetEnterpriseId(&Subject, &pClaim);
    v8 = xmmword_1801FAD20;
    if ( (xmmword_1801FAD20 & 8) != 0 )
    {
      WPP_SF_d(0x403u, 0x4Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, EnterpriseId);
      v8 = xmmword_1801FAD20;
    }
    if ( EnterpriseId >= 0 )
    {
      v2 = pClaim;
      if ( pClaim && pClaim->Length && pClaim->MaximumLength && (Buffer = pClaim->Buffer) != 0 )
      {
        if ( (v8 & 8) != 0 )
          WPP_SF_S(0x403u, 0x4Bu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, Buffer);
        v5 = SecureString::init(&this->_ssEDPClaim, v2->Buffer, v2->Length >> 1);
      }
      else
      {
        v5 = -2147467259;
      }
    }
    else
    {
      v9 = RtlNtStatusToDosError(EnterpriseId);
      v2 = pClaim;
      v5 = v9;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  this->Unlock(this);
  if ( v2 )
    EnterpriseContextLibMemFree(v2);
  if ( hThreadToken )
  {
    CloseHandle(hThreadToken);
    hThreadToken = 0;
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v5 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v5 >> 31) + 2) << 9) | 3, 0x4Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18015d3e0  mov     [rsp+arg_18], rbx
0x18015d3e5  push    rsi
0x18015d3e6  push    rdi
0x18015d3e7  push    r14
0x18015d3e9  sub     rsp, 20h
0x18015d3ed  xor     r14d, r14d
0x18015d3f0  mov     rsi, this
0x18015d3f3  mov     ebx, r14d
0x18015d3f6  mov     [rsp+38h+hThreadToken], r14
0x18015d3fb  mov     [rsp+38h+pClaim], rbx
0x18015d400  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015d407  mov     edi, 403h
0x18015d40c  jz      short loc_18015D423
0x18015d40e  lea     edx, [r14+49h]; id
0x18015d412  mov     ecx, edi; LevelKeyword
0x18015d414  mov     r9, rsi; _a1
0x18015d417  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d41e  call    WPP_SF_q
0x18015d423  mov     rax, [rsi]
0x18015d426  mov     this, rsi
0x18015d429  mov     rax, [rax+0F8h]
0x18015d430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d435  call    cs:__imp_GetCurrentThread
0x18015d43c  nop     dword ptr [rax+rax+00h]
0x18015d441  mov     edx, 8; DesiredAccess
0x18015d446  lea     r9, [rsp+38h+hThreadToken]; TokenHandle
0x18015d44b  mov     this, rax; ThreadHandle
0x18015d44e  lea     r8d, [rdx-7]; OpenAsSelf
0x18015d452  call    cs:__imp_OpenThreadToken
0x18015d459  nop     dword ptr [rax+rax+00h]
0x18015d45e  test    eax, eax
0x18015d460  jnz     short loc_18015D486
0x18015d462  call    cs:__imp_GetLastError
0x18015d469  nop     dword ptr [rax+rax+00h]
0x18015d46e  mov     edi, eax
0x18015d470  test    eax, eax
0x18015d472  jle     $CleanUp_554
0x18015d478  movzx   edi, ax
0x18015d47b  or      edi, 80070000h
0x18015d481  jmp     $CleanUp_554
0x18015d486  mov     rax, [rsp+38h+hThreadToken]
0x18015d48b  lea     rdx, [rsp+38h+pClaim]; EnterpriseId
0x18015d490  test    rax, rax
0x18015d493  mov     this, 0FFFFFFFFFFFFFFFAh
0x18015d49a  cmovz   rax, this
0x18015d49e  lea     this, [rsp+38h+Subject]; Subject
0x18015d4a3  mov     [rsp+38h+Subject.TokenHandle], rax
0x18015d4a8  call    GetEnterpriseId
0x18015d4ad  mov     ebx, eax
0x18015d4af  mov     al, byte ptr cs:xmmword_1801FAD20; __annotation("TMF:",
0x18015d4b5  test    al, 8
0x18015d4b7  jz      short loc_18015D4D5
0x18015d4b9  mov     edx, 4Ah ; 'J'; id
0x18015d4be  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d4c5  mov     ecx, edi; LevelKeyword
0x18015d4c7  mov     r9d, ebx; _a1
0x18015d4ca  call    WPP_SF_d
0x18015d4cf  mov     al, byte ptr cs:xmmword_1801FAD20
0x18015d4d5  test    ebx, ebx
0x18015d4d7  jns     short loc_18015D4F0
0x18015d4d9  mov     ecx, ebx; Status
0x18015d4db  call    cs:__imp_RtlNtStatusToDosError
0x18015d4e2  nop     dword ptr [rax+rax+00h]
0x18015d4e7  mov     rbx, [rsp+38h+pClaim]
0x18015d4ec  mov     edi, eax
0x18015d4ee  jmp     short $CleanUp_554
0x18015d4f0  mov     rbx, [rsp+38h+pClaim]
0x18015d4f5  test    rbx, rbx
0x18015d4f8  jz      short loc_18015D542
0x18015d4fa  cmp     [rbx], r14w
0x18015d4fe  jz      short loc_18015D542
0x18015d500  cmp     [rbx+2], r14w
0x18015d505  jz      short loc_18015D542
0x18015d507  mov     r9, [rbx+8]; _a1
0x18015d50b  test    r9, r9
0x18015d50e  jz      short loc_18015D542
0x18015d510  test    al, 8; __annotation("TMF:",
0x18015d512  jz      short loc_18015D527
0x18015d514  mov     edx, 4Bh ; 'K'; id
0x18015d519  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d520  mov     ecx, edi; LevelKeyword
0x18015d522  call    WPP_SF_S
0x18015d527  movzx   r8d, word ptr [rbx]
0x18015d52b  lea     this, [rsi+288h]; this
0x18015d532  mov     rdx, [rbx+8]; pwsz
0x18015d536  shr     r8d, 1; cch
0x18015d539  call    ?init@SecureString@@QEAAJPEBGK@Z; SecureString::init(ushort const *,ulong)
0x18015d53e  mov     edi, eax
0x18015d540  jmp     short $CleanUp_554
0x18015d542  mov     edi, 80004005h
0x18015d547  mov     rax, [rsi]
0x18015d54a  mov     this, rsi
0x18015d54d  mov     rax, [rax+100h]
0x18015d554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d559  test    rbx, rbx
0x18015d55c  jz      short loc_18015D566
0x18015d55e  mov     this, rbx; Memory
0x18015d561  call    EnterpriseContextLibMemFree
0x18015d566  mov     this, [rsp+38h+hThreadToken]; hObject
0x18015d56b  test    this, this
0x18015d56e  jz      short loc_18015D581
0x18015d570  call    cs:__imp_CloseHandle
0x18015d577  nop     dword ptr [rax+rax+00h]
0x18015d57c  mov     [rsp+38h+hThreadToken], r14
0x18015d581  mov     r9d, edi; __annotation("TMF:",
0x18015d584  sar     r9d, 1Fh
0x18015d588  lea     eax, ds:4[r9*2]
0x18015d590  movsxd  this, eax
0x18015d593  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015d59a  test    byte ptr [rax+this*8], 8
0x18015d59e  jz      short loc_18015D5C9
0x18015d5a0  add     r9w, 2
0x18015d5a5  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015d5ac  movzx   ecx, r9w
0x18015d5b0  mov     eax, 200h
0x18015d5b5  imul    ecx, eax
0x18015d5b8  mov     edx, 4Ch ; 'L'; id
0x18015d5bd  mov     r9d, edi; _a1
0x18015d5c0  or      cx, 3; LevelKeyword
0x18015d5c4  call    WPP_SF_d
0x18015d5c9  mov     rbx, [rsp+38h+arg_18]
0x18015d5ce  mov     eax, edi
0x18015d5d0  add     rsp, 20h
0x18015d5d4  pop     r14
0x18015d5d6  pop     rdi
0x18015d5d7  pop     rsi
0x18015d5d8  retn
```
