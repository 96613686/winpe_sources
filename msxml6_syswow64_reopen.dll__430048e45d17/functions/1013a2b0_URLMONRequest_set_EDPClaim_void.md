# URLMONRequest::set_EDPClaim(void)

- ea: `0x1013a2b0`
- end: `0x1013a42f`
- name: `?set_EDPClaim@URLMONRequest@@UAEJXZ`
- size: `383`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x10067b20`
- `0x1013a2b0`
- `0x1016b757`
- `0x1016b770`
- `0x1016bcc5`
- `0x10180006`
- `0x101809e7`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1013a36c`
- `ntdll!RtlNtStatusToDosError` at `0x1013a36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a30d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a30d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013a2fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013a2fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013a303`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013a303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013a3f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013a3f3`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::set_EDPClaim(URLMONRequest *this)
{
  HANDLE CurrentThread; // eax
  signed int LastError; // eax
  signed int v4; // edi
  int v5; // eax
  int EnterpriseId; // esi
  char v7; // al
  ULONG v8; // eax
  _UNICODE_STRING *v9; // esi
  _SUBJECT Subject; // [esp+4h] [ebp-10h] BYREF
  URLMONRequest *v12; // [esp+8h] [ebp-Ch]
  _UNICODE_STRING *pClaim; // [esp+Ch] [ebp-8h] BYREF
  void *hThreadToken; // [esp+10h] [ebp-4h] BYREF

  v12 = this;
  hThreadToken = 0;
  pClaim = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x49u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  this->Lock(this);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &hThreadToken) )
  {
    v5 = (int)hThreadToken;
    if ( !hThreadToken )
      v5 = -6;
    Subject.TokenHandle = (void *)v5;
    EnterpriseId = GetEnterpriseId(&Subject, &pClaim);
    v7 = byte_10185760[0];
    if ( (byte_10185760[0] & 8) != 0 )
    {
      WPP_SF_q(0x403u, 0x4Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, EnterpriseId);
      v7 = byte_10185760[0];
    }
    if ( EnterpriseId >= 0 )
    {
      v9 = pClaim;
      if ( !pClaim || !pClaim->Length || !pClaim->MaximumLength || !pClaim->Buffer )
      {
        v4 = -2147467259;
        goto CleanUp_523;
      }
      if ( (v7 & 8) != 0 )
        WPP_SF_S(0x403u, 0x4Bu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, pClaim->Buffer);
      v8 = SecureString::init(&this->_ssEDPClaim, v9->Buffer, v9->Length >> 1);
    }
    else
    {
      v8 = RtlNtStatusToDosError(EnterpriseId);
    }
    v4 = v8;
    goto CleanUp_523;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
CleanUp_523:
  v12->Unlock(v12);
  if ( pClaim )
    EnterpriseContextLibMemFree(pClaim);
  if ( hThreadToken )
  {
    CloseHandle(hThreadToken);
    hThreadToken = 0;
  }
  if ( (byte_10185760[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x4Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1013a2b0  mov     edi, edi
0x1013a2b2  push    ebp
0x1013a2b3  mov     ebp, esp
0x1013a2b5  sub     esp, 10h
0x1013a2b8  push    edi
0x1013a2b9  xor     eax, eax
0x1013a2bb  mov     edi, this
0x1013a2bd  mov     [ebp+var_C], edi
0x1013a2c0  mov     [ebp+hThreadToken], eax
0x1013a2c3  mov     [ebp+pClaim], eax
0x1013a2c6  test    byte_10185760, 8; __annotation("TMF:",
0x1013a2cd  jz      short loc_1013A2E2
0x1013a2cf  push    edi; _a1
0x1013a2d0  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a2d5  push    49h ; 'I'
0x1013a2d7  pop     edx; id
0x1013a2d8  mov     this, 403h; LevelKeyword
0x1013a2dd  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a2e2  mov     eax, [edi]
0x1013a2e4  push    esi
0x1013a2e5  mov     esi, [eax+7Ch]
0x1013a2e8  mov     this, esi; this
0x1013a2ea  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a2f0  mov     this, edi
0x1013a2f2  call    esi
0x1013a2f4  lea     eax, [ebp+hThreadToken]
0x1013a2f7  push    eax; TokenHandle
0x1013a2f8  push    1; OpenAsSelf
0x1013a2fa  push    8; DesiredAccess
0x1013a2fc  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x1013a302  push    eax; ThreadHandle
0x1013a303  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x1013a309  test    eax, eax
0x1013a30b  jnz     short loc_1013A32B
0x1013a30d  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a313  mov     edi, eax
0x1013a315  test    edi, edi
0x1013a317  jle     CleanUp_523
0x1013a31d  movzx   edi, di
0x1013a320  or      edi, 80070000h
0x1013a326  jmp     CleanUp_523
0x1013a32b  mov     eax, [ebp+hThreadToken]
0x1013a32e  lea     edx, [ebp+pClaim]; EnterpriseId
0x1013a331  push    0FFFFFFFAh
0x1013a333  pop     this
0x1013a334  test    eax, eax
0x1013a336  cmovz   eax, this
0x1013a339  lea     this, [ebp+Subject]; Subject
0x1013a33c  mov     [ebp+Subject.TokenHandle], eax
0x1013a33f  call    _GetEnterpriseId@8; GetEnterpriseId(x,x)
0x1013a344  mov     esi, eax
0x1013a346  mov     al, byte_10185760; __annotation("TMF:",
0x1013a34b  test    al, 8
0x1013a34d  jz      short loc_1013A367
0x1013a34f  push    esi; _a1
0x1013a350  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a355  push    4Ah ; 'J'
0x1013a357  pop     edx; id
0x1013a358  mov     this, 403h; LevelKeyword
0x1013a35d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a362  mov     al, byte_10185760
0x1013a367  test    esi, esi
0x1013a369  jns     short loc_1013A376
0x1013a36b  push    esi; Status
0x1013a36c  call    ds:__imp__RtlNtStatusToDosError@4; RtlNtStatusToDosError(x)
0x1013a372  mov     edi, eax
0x1013a374  jmp     short CleanUp_523
0x1013a376  mov     esi, [ebp+pClaim]
0x1013a379  test    esi, esi
0x1013a37b  jz      short loc_1013A3BE
0x1013a37d  xor     this, this
0x1013a37f  cmp     [esi], cx
0x1013a382  jz      short loc_1013A3BE
0x1013a384  cmp     [esi+2], cx
0x1013a388  jz      short loc_1013A3BE
0x1013a38a  cmp     [esi+4], this
0x1013a38d  jz      short loc_1013A3BE
0x1013a38f  test    al, 8; __annotation("TMF:",
0x1013a391  jz      short loc_1013A3A8
0x1013a393  push    dword ptr [esi+4]; _a1
0x1013a396  mov     this, 403h; LevelKeyword
0x1013a39b  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a3a0  push    4Bh ; 'K'
0x1013a3a2  pop     edx; id
0x1013a3a3  call    _WPP_SF_S@16; WPP_SF_S(x,x,x,x)
0x1013a3a8  movzx   eax, word ptr [esi]
0x1013a3ab  lea     this, [edi+190h]; this
0x1013a3b1  shr     eax, 1
0x1013a3b3  push    eax; cch
0x1013a3b4  push    dword ptr [esi+4]; pwsz
0x1013a3b7  call    ?init@SecureString@@QAEJPBGK@Z; SecureString::init(ushort const *,ulong)
0x1013a3bc  jmp     short loc_1013A372
0x1013a3be  mov     edi, 80004005h
0x1013a3c3  mov     eax, [ebp+var_C]
0x1013a3c6  mov     eax, [eax]
0x1013a3c8  mov     esi, [eax+80h]
0x1013a3ce  mov     this, esi; this
0x1013a3d0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a3d6  mov     this, [ebp+var_C]
0x1013a3d9  call    esi
0x1013a3db  mov     eax, [ebp+pClaim]
0x1013a3de  pop     esi
0x1013a3df  test    eax, eax
0x1013a3e1  jz      short loc_1013A3EA
0x1013a3e3  mov     this, eax; Memory
0x1013a3e5  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1013a3ea  cmp     [ebp+hThreadToken], 0
0x1013a3ee  jz      short loc_1013A400
0x1013a3f0  push    [ebp+hThreadToken]; hObject
0x1013a3f3  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1013a3f9  mov     [ebp+hThreadToken], 0
0x1013a400  mov     this, edi; __annotation("TMF:",
0x1013a402  sar     this, 1Fh
0x1013a405  mov     eax, this
0x1013a407  shl     eax, 4
0x1013a40a  test    byte_10185760[eax], 8
0x1013a411  jz      short loc_1013A42A
0x1013a413  push    edi; _a1
0x1013a414  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a419  add     this, 2
0x1013a41c  shl     this, 9
0x1013a41f  push    4Ch ; 'L'
0x1013a421  or      this, 3; LevelKeyword
0x1013a424  pop     edx; id
0x1013a425  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a42a  mov     eax, edi
0x1013a42c  pop     edi
0x1013a42d  leave
0x1013a42e  retn
```
