# URLMONRequest::set_EDPClaim(void)

- ea: `0x180159c50`
- end: `0x180159e2b`
- name: `?set_EDPClaim@URLMONRequest@@UEAAJXZ`
- size: `475`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800bc418`
- `0x180159c50`
- `0x180175bf0`
- `0x180175c10`
- `0x180185008`
- `0x1801850e0`
- `0x180186018`
- `0x180188010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180159d39`
- `ntdll!RtlNtStatusToDosError` at `0x180159d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180159cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180159cc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180159cbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180159cbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180159ca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180159ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180159dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180159dc8`

## pseudocode

```c
__int64 __fastcall URLMONRequest::set_EDPClaim(URLMONRequest *this)
{
  _UNICODE_STRING *v2; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v5; // edi
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
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
    v8 = xmmword_1801F6C20;
    if ( (xmmword_1801F6C20 & 8) != 0 )
    {
      WPP_SF_d(0x403u, 0x4Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, EnterpriseId);
      v8 = xmmword_1801F6C20;
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
0x180159c50  mov     [rsp+arg_18], rbx
0x180159c55  push    rsi
0x180159c56  push    rdi
0x180159c57  push    r14
0x180159c59  sub     rsp, 20h
0x180159c5d  xor     r14d, r14d
0x180159c60  mov     rsi, this
0x180159c63  mov     ebx, r14d
0x180159c66  mov     [rsp+38h+hThreadToken], r14
0x180159c6b  mov     [rsp+38h+pClaim], rbx
0x180159c70  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180159c77  mov     edi, 403h
0x180159c7c  jz      short loc_180159C93
0x180159c7e  lea     edx, [r14+49h]; id
0x180159c82  mov     ecx, edi; LevelKeyword
0x180159c84  mov     r9, rsi; _a1
0x180159c87  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159c8e  call    WPP_SF_q
0x180159c93  mov     rax, [rsi]
0x180159c96  mov     this, rsi
0x180159c99  mov     rax, [rax+0F8h]
0x180159ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159ca5  call    cs:__imp_GetCurrentThread
0x180159cab  mov     edx, 8; DesiredAccess
0x180159cb0  lea     r9, [rsp+38h+hThreadToken]; TokenHandle
0x180159cb5  mov     this, rax; ThreadHandle
0x180159cb8  lea     r8d, [rdx-7]; OpenAsSelf
0x180159cbc  call    cs:__imp_OpenThreadToken
0x180159cc2  test    eax, eax
0x180159cc4  jnz     short loc_180159CE4
0x180159cc6  call    cs:__imp_GetLastError
0x180159ccc  mov     edi, eax
0x180159cce  test    eax, eax
0x180159cd0  jle     $CleanUp_554
0x180159cd6  movzx   edi, ax
0x180159cd9  or      edi, 80070000h
0x180159cdf  jmp     $CleanUp_554
0x180159ce4  mov     rax, [rsp+38h+hThreadToken]
0x180159ce9  lea     rdx, [rsp+38h+pClaim]; EnterpriseId
0x180159cee  test    rax, rax
0x180159cf1  mov     this, 0FFFFFFFFFFFFFFFAh
0x180159cf8  cmovz   rax, this
0x180159cfc  lea     this, [rsp+38h+Subject]; Subject
0x180159d01  mov     [rsp+38h+Subject.TokenHandle], rax
0x180159d06  call    GetEnterpriseId
0x180159d0b  mov     ebx, eax
0x180159d0d  mov     al, byte ptr cs:xmmword_1801F6C20; __annotation("TMF:",
0x180159d13  test    al, 8
0x180159d15  jz      short loc_180159D33
0x180159d17  mov     edx, 4Ah ; 'J'; id
0x180159d1c  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159d23  mov     ecx, edi; LevelKeyword
0x180159d25  mov     r9d, ebx; _a1
0x180159d28  call    WPP_SF_d
0x180159d2d  mov     al, byte ptr cs:xmmword_1801F6C20
0x180159d33  test    ebx, ebx
0x180159d35  jns     short loc_180159D48
0x180159d37  mov     ecx, ebx; Status
0x180159d39  call    cs:__imp_RtlNtStatusToDosError
0x180159d3f  mov     rbx, [rsp+38h+pClaim]
0x180159d44  mov     edi, eax
0x180159d46  jmp     short $CleanUp_554
0x180159d48  mov     rbx, [rsp+38h+pClaim]
0x180159d4d  test    rbx, rbx
0x180159d50  jz      short loc_180159D9A
0x180159d52  cmp     [rbx], r14w
0x180159d56  jz      short loc_180159D9A
0x180159d58  cmp     [rbx+2], r14w
0x180159d5d  jz      short loc_180159D9A
0x180159d5f  mov     r9, [rbx+8]; _a1
0x180159d63  test    r9, r9
0x180159d66  jz      short loc_180159D9A
0x180159d68  test    al, 8; __annotation("TMF:",
0x180159d6a  jz      short loc_180159D7F
0x180159d6c  mov     edx, 4Bh ; 'K'; id
0x180159d71  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159d78  mov     ecx, edi; LevelKeyword
0x180159d7a  call    WPP_SF_S
0x180159d7f  movzx   r8d, word ptr [rbx]
0x180159d83  lea     this, [rsi+288h]; this
0x180159d8a  mov     rdx, [rbx+8]; pwsz
0x180159d8e  shr     r8d, 1; cch
0x180159d91  call    ?init@SecureString@@QEAAJPEBGK@Z; SecureString::init(ushort const *,ulong)
0x180159d96  mov     edi, eax
0x180159d98  jmp     short $CleanUp_554
0x180159d9a  mov     edi, 80004005h
0x180159d9f  mov     rax, [rsi]
0x180159da2  mov     this, rsi
0x180159da5  mov     rax, [rax+100h]
0x180159dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159db1  test    rbx, rbx
0x180159db4  jz      short loc_180159DBE
0x180159db6  mov     this, rbx; Memory
0x180159db9  call    EnterpriseContextLibMemFree
0x180159dbe  mov     this, [rsp+38h+hThreadToken]; hObject
0x180159dc3  test    this, this
0x180159dc6  jz      short loc_180159DD3
0x180159dc8  call    cs:__imp_CloseHandle
0x180159dce  mov     [rsp+38h+hThreadToken], r14
0x180159dd3  mov     r9d, edi; __annotation("TMF:",
0x180159dd6  sar     r9d, 1Fh
0x180159dda  lea     eax, ds:4[r9*2]
0x180159de2  movsxd  this, eax
0x180159de5  lea     rax, g_rgFastWppLevelEnabledFlags
0x180159dec  test    byte ptr [rax+this*8], 8
0x180159df0  jz      short loc_180159E1B
0x180159df2  add     r9w, 2
0x180159df7  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159dfe  movzx   ecx, r9w
0x180159e02  mov     eax, 200h
0x180159e07  imul    ecx, eax
0x180159e0a  mov     edx, 4Ch ; 'L'; id
0x180159e0f  mov     r9d, edi; _a1
0x180159e12  or      cx, 3; LevelKeyword
0x180159e16  call    WPP_SF_d
0x180159e1b  mov     rbx, [rsp+38h+arg_18]
0x180159e20  mov     eax, edi
0x180159e22  add     rsp, 20h
0x180159e26  pop     r14
0x180159e28  pop     rdi
0x180159e29  pop     rsi
0x180159e2a  retn
```
