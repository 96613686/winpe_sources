# URLMONRequest::set_EDPClaim(void)

- ea: `0x1013a1a0`
- end: `0x1013a31f`
- name: `?set_EDPClaim@URLMONRequest@@UAEJXZ`
- size: `383`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x10067bc0`
- `0x1013a1a0`
- `0x1016b667`
- `0x1016b680`
- `0x1016bbd5`
- `0x10180006`
- `0x101809e7`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1013a25c`
- `ntdll!RtlNtStatusToDosError` at `0x1013a25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013a1fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013a1ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1013a1ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013a1f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1013a1f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013a2e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1013a2e3`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
    v7 = byte_101857A0[0];
    if ( (byte_101857A0[0] & 8) != 0 )
    {
      WPP_SF_q(0x403u, 0x4Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, EnterpriseId);
      v7 = byte_101857A0[0];
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
  if ( (byte_101857A0[16 * (v4 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x4Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1013a1a0  mov     edi, edi
0x1013a1a2  push    ebp
0x1013a1a3  mov     ebp, esp
0x1013a1a5  sub     esp, 10h
0x1013a1a8  push    edi
0x1013a1a9  xor     eax, eax
0x1013a1ab  mov     edi, this
0x1013a1ad  mov     [ebp+var_C], edi
0x1013a1b0  mov     [ebp+hThreadToken], eax
0x1013a1b3  mov     [ebp+pClaim], eax
0x1013a1b6  test    byte_101857A0, 8; __annotation("TMF:",
0x1013a1bd  jz      short loc_1013A1D2
0x1013a1bf  push    edi; _a1
0x1013a1c0  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a1c5  push    49h ; 'I'
0x1013a1c7  pop     edx; id
0x1013a1c8  mov     this, 403h; LevelKeyword
0x1013a1cd  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a1d2  mov     eax, [edi]
0x1013a1d4  push    esi
0x1013a1d5  mov     esi, [eax+7Ch]
0x1013a1d8  mov     this, esi; this
0x1013a1da  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a1e0  mov     this, edi
0x1013a1e2  call    esi
0x1013a1e4  lea     eax, [ebp+hThreadToken]
0x1013a1e7  push    eax; TokenHandle
0x1013a1e8  push    1; OpenAsSelf
0x1013a1ea  push    8; DesiredAccess
0x1013a1ec  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x1013a1f2  push    eax; ThreadHandle
0x1013a1f3  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x1013a1f9  test    eax, eax
0x1013a1fb  jnz     short loc_1013A21B
0x1013a1fd  call    ds:__imp__GetLastError@0; GetLastError()
0x1013a203  mov     edi, eax
0x1013a205  test    edi, edi
0x1013a207  jle     CleanUp_523
0x1013a20d  movzx   edi, di
0x1013a210  or      edi, 80070000h
0x1013a216  jmp     CleanUp_523
0x1013a21b  mov     eax, [ebp+hThreadToken]
0x1013a21e  lea     edx, [ebp+pClaim]; EnterpriseId
0x1013a221  push    0FFFFFFFAh
0x1013a223  pop     this
0x1013a224  test    eax, eax
0x1013a226  cmovz   eax, this
0x1013a229  lea     this, [ebp+Subject]; Subject
0x1013a22c  mov     [ebp+Subject.TokenHandle], eax
0x1013a22f  call    _GetEnterpriseId@8; GetEnterpriseId(x,x)
0x1013a234  mov     esi, eax
0x1013a236  mov     al, byte_101857A0; __annotation("TMF:",
0x1013a23b  test    al, 8
0x1013a23d  jz      short loc_1013A257
0x1013a23f  push    esi; _a1
0x1013a240  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a245  push    4Ah ; 'J'
0x1013a247  pop     edx; id
0x1013a248  mov     this, 403h; LevelKeyword
0x1013a24d  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a252  mov     al, byte_101857A0
0x1013a257  test    esi, esi
0x1013a259  jns     short loc_1013A266
0x1013a25b  push    esi; Status
0x1013a25c  call    ds:__imp__RtlNtStatusToDosError@4; RtlNtStatusToDosError(x)
0x1013a262  mov     edi, eax
0x1013a264  jmp     short CleanUp_523
0x1013a266  mov     esi, [ebp+pClaim]
0x1013a269  test    esi, esi
0x1013a26b  jz      short loc_1013A2AE
0x1013a26d  xor     this, this
0x1013a26f  cmp     [esi], cx
0x1013a272  jz      short loc_1013A2AE
0x1013a274  cmp     [esi+2], cx
0x1013a278  jz      short loc_1013A2AE
0x1013a27a  cmp     [esi+4], this
0x1013a27d  jz      short loc_1013A2AE
0x1013a27f  test    al, 8; __annotation("TMF:",
0x1013a281  jz      short loc_1013A298
0x1013a283  push    dword ptr [esi+4]; _a1
0x1013a286  mov     this, 403h; LevelKeyword
0x1013a28b  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a290  push    4Bh ; 'K'
0x1013a292  pop     edx; id
0x1013a293  call    _WPP_SF_S@16; WPP_SF_S(x,x,x,x)
0x1013a298  movzx   eax, word ptr [esi]
0x1013a29b  lea     this, [edi+190h]; this
0x1013a2a1  shr     eax, 1
0x1013a2a3  push    eax; cch
0x1013a2a4  push    dword ptr [esi+4]; pwsz
0x1013a2a7  call    ?init@SecureString@@QAEJPBGK@Z; SecureString::init(ushort const *,ulong)
0x1013a2ac  jmp     short loc_1013A262
0x1013a2ae  mov     edi, 80004005h
0x1013a2b3  mov     eax, [ebp+var_C]
0x1013a2b6  mov     eax, [eax]
0x1013a2b8  mov     esi, [eax+80h]
0x1013a2be  mov     this, esi; this
0x1013a2c0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013a2c6  mov     this, [ebp+var_C]
0x1013a2c9  call    esi
0x1013a2cb  mov     eax, [ebp+pClaim]
0x1013a2ce  pop     esi
0x1013a2cf  test    eax, eax
0x1013a2d1  jz      short loc_1013A2DA
0x1013a2d3  mov     this, eax; Memory
0x1013a2d5  call    _EnterpriseContextLibMemFree@4; EnterpriseContextLibMemFree(x)
0x1013a2da  cmp     [ebp+hThreadToken], 0
0x1013a2de  jz      short loc_1013A2F0
0x1013a2e0  push    [ebp+hThreadToken]; hObject
0x1013a2e3  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1013a2e9  mov     [ebp+hThreadToken], 0
0x1013a2f0  mov     this, edi; __annotation("TMF:",
0x1013a2f2  sar     this, 1Fh
0x1013a2f5  mov     eax, this
0x1013a2f7  shl     eax, 4
0x1013a2fa  test    byte_101857A0[eax], 8
0x1013a301  jz      short loc_1013A31A
0x1013a303  push    edi; _a1
0x1013a304  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013a309  add     this, 2
0x1013a30c  shl     this, 9
0x1013a30f  push    4Ch ; 'L'
0x1013a311  or      this, 3; LevelKeyword
0x1013a314  pop     edx; id
0x1013a315  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013a31a  mov     eax, edi
0x1013a31c  pop     edi
0x1013a31d  leave
0x1013a31e  retn
```
