# URLMONRequest::_ApplySettingToProtocol(void)

- ea: `0x18015a638`
- end: `0x18015a84f`
- name: `?_ApplySettingToProtocol@URLMONRequest@@IEAAJXZ`
- size: `535`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180093030`

## callees

- `0x18015a4e4`
- `0x18015a638`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18015a6e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18015a6e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a6f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015a7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015a7e7`

## pseudocode

```c
__int64 __fastcall URLMONRequest::_ApplySettingToProtocol(URLMONRequest *this)
{
  HRESULT v1; // edi
  __int64 v3; // rax
  HANDLE Event; // rax
  signed int LastError; // eax
  unsigned int cbTemp; // [rsp+60h] [rbp+8h] BYREF
  INetworkTransportSettings *pTransportSettings; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 *pbTemp; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  pTransportSettings = 0;
  cbTemp = 0;
  pbTemp = 0;
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x68u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  this->Lock(this);
  if ( this->_pIInternetProtocol && this->_cbSetting && this->_pbSetting )
  {
    v3 = *(_QWORD *)&this->_SettingId.Guid.Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v3 )
      v3 = *(_QWORD *)this->_SettingId.Guid.Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v3 )
    {
      Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
      this->_hStartComplete = Event;
      if ( Event )
      {
        v1 = this->_pIInternetProtocol->QueryInterface(
               this->_pIInternetProtocol,
               &IID_INetworkTransportSettings,
               (void **)&pTransportSettings);
        if ( v1 >= 0 )
          v1 = pTransportSettings->ApplySetting(
                 pTransportSettings,
                 &this->_SettingId,
                 this->_cbSetting,
                 this->_pbSetting,
                 &cbTemp,
                 &pbTemp);
        if ( (unsigned int)(v1 + 2147467263) <= 1 )
        {
          this->Unlock(this);
          URLMONRequest::_AbortBadPushRequest(this, v1);
          this->Lock(this);
        }
      }
      else
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  this->Unlock(this);
  if ( pTransportSettings )
  {
    pTransportSettings->Release(pTransportSettings);
    pTransportSettings = 0;
  }
  CoTaskMemFree(pbTemp);
  pbTemp = 0;
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v1 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v1 >> 31) + 2) << 9) | 3, 0x69u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18015a638  push    rbx
0x18015a63a  push    rsi
0x18015a63b  push    rdi
0x18015a63c  sub     rsp, 40h
0x18015a640  xor     edi, edi
0x18015a642  mov     rbx, this
0x18015a645  mov     [rsp+58h+pTransportSettings], rdi
0x18015a64a  mov     [rsp+58h+cbTemp], edi
0x18015a64e  mov     [rsp+58h+pbTemp], rdi
0x18015a653  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015a65a  jz      short loc_18015A673
0x18015a65c  lea     edx, [rdi+68h]; id
0x18015a65f  mov     ecx, 403h; LevelKeyword
0x18015a664  mov     r9, rbx; _a1
0x18015a667  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015a66e  call    WPP_SF_q
0x18015a673  mov     rax, [rbx]
0x18015a676  mov     this, rbx
0x18015a679  mov     rax, [rax+0F8h]
0x18015a680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a685  cmp     [rbx+0B8h], rdi
0x18015a68c  jz      $CleanUp_526
0x18015a692  cmp     [rbx+204h], edi
0x18015a698  jz      $CleanUp_526
0x18015a69e  cmp     [rbx+208h], rdi
0x18015a6a5  jz      $CleanUp_526
0x18015a6ab  lea     rsi, [rbx+1F4h]
0x18015a6b2  mov     rax, [rsi]
0x18015a6b5  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18015a6bc  jnz     short loc_18015A6C9
0x18015a6be  mov     rax, [rsi+8]
0x18015a6c2  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18015a6c9  test    rax, rax
0x18015a6cc  jz      $CleanUp_526
0x18015a6d2  xor     edx, edx; lpName
0x18015a6d4  xor     ecx, ecx; lpEventAttributes
0x18015a6d6  mov     r9d, 1F0003h; dwDesiredAccess
0x18015a6dc  lea     r8d, [rdx+1]; dwFlags
0x18015a6e0  call    cs:__imp_CreateEventExW
0x18015a6e7  nop     dword ptr [rax+rax+00h]
0x18015a6ec  mov     [rbx+228h], rax
0x18015a6f3  test    rax, rax
0x18015a6f6  jnz     short loc_18015A71C
0x18015a6f8  call    cs:__imp_GetLastError
0x18015a6ff  nop     dword ptr [rax+rax+00h]
0x18015a704  mov     edi, eax
0x18015a706  test    eax, eax
0x18015a708  jle     $CleanUp_526
0x18015a70e  movzx   edi, ax
0x18015a711  or      edi, 80070000h
0x18015a717  jmp     $CleanUp_526
0x18015a71c  mov     this, [rbx+0B8h]
0x18015a723  lea     r8, [rsp+58h+pTransportSettings]
0x18015a728  lea     rdx, IID_INetworkTransportSettings
0x18015a72f  mov     rax, [this]
0x18015a732  mov     rax, [rax]
0x18015a735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a73a  mov     edi, eax
0x18015a73c  test    eax, eax
0x18015a73e  js      short loc_18015A778
0x18015a740  mov     this, [rsp+58h+pTransportSettings]
0x18015a745  lea     rdx, [rsp+58h+pbTemp]
0x18015a74a  mov     r9, [rbx+208h]
0x18015a751  mov     r8d, [rbx+204h]
0x18015a758  mov     [rsp+58h+var_30], rdx
0x18015a75d  lea     rdx, [rsp+58h+cbTemp]
0x18015a762  mov     rax, [this]
0x18015a765  mov     [rsp+58h+var_38], rdx
0x18015a76a  mov     rdx, rsi
0x18015a76d  mov     rax, [rax+18h]
0x18015a771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a776  mov     edi, eax
0x18015a778  lea     eax, [rdi+7FFFBFFFh]
0x18015a77e  cmp     eax, 1
0x18015a781  ja      short $CleanUp_526
0x18015a783  mov     rax, [rbx]
0x18015a786  mov     this, rbx
0x18015a789  mov     rax, [rax+100h]
0x18015a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a795  mov     edx, edi; hr
0x18015a797  mov     this, rbx; this
0x18015a79a  call    ?_AbortBadPushRequest@URLMONRequest@@IEAAXJ@Z; URLMONRequest::_AbortBadPushRequest(long)
0x18015a79f  mov     rax, [rbx]
0x18015a7a2  mov     this, rbx
0x18015a7a5  mov     rax, [rax+0F8h]
0x18015a7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a7b1  mov     rax, [rbx]
0x18015a7b4  mov     this, rbx
0x18015a7b7  mov     rax, [rax+100h]
0x18015a7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a7c3  mov     this, [rsp+58h+pTransportSettings]
0x18015a7c8  test    this, this
0x18015a7cb  jz      short loc_18015A7E2
0x18015a7cd  mov     rax, [this]
0x18015a7d0  mov     rax, [rax+10h]
0x18015a7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a7d9  mov     [rsp+58h+pTransportSettings], 0
0x18015a7e2  mov     this, [rsp+58h+pbTemp]; pv
0x18015a7e7  call    cs:__imp_CoTaskMemFree
0x18015a7ee  nop     dword ptr [rax+rax+00h]
0x18015a7f3  mov     [rsp+58h+pbTemp], 0
0x18015a7fc  mov     r9d, edi; __annotation("TMF:",
0x18015a7ff  sar     r9d, 1Fh
0x18015a803  lea     eax, ds:4[r9*2]
0x18015a80b  movsxd  this, eax
0x18015a80e  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015a815  test    byte ptr [rax+this*8], 8
0x18015a819  jz      short loc_18015A844
0x18015a81b  add     r9w, 2
0x18015a820  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015a827  movzx   ecx, r9w
0x18015a82b  mov     eax, 200h
0x18015a830  imul    ecx, eax
0x18015a833  mov     edx, 69h ; 'i'; id
0x18015a838  mov     r9d, edi; _a1
0x18015a83b  or      cx, 3; LevelKeyword
0x18015a83f  call    WPP_SF_d
0x18015a844  mov     eax, edi
0x18015a846  add     rsp, 40h
0x18015a84a  pop     rdi
0x18015a84b  pop     rsi
0x18015a84c  pop     rbx
0x18015a84d  retn
```
