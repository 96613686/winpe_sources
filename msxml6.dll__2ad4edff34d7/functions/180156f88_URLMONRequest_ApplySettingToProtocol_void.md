# URLMONRequest::_ApplySettingToProtocol(void)

- ea: `0x180156f88`
- end: `0x18015718c`
- name: `?_ApplySettingToProtocol@URLMONRequest@@IEAAJXZ`
- size: `516`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180093060`

## callees

- `0x180156e34`
- `0x180156f88`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180157030`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180157030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180157042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015712b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015712b`

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
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
0x180156f88  push    rbx
0x180156f8a  push    rsi
0x180156f8b  push    rdi
0x180156f8c  sub     rsp, 40h
0x180156f90  xor     edi, edi
0x180156f92  mov     rbx, this
0x180156f95  mov     [rsp+58h+pTransportSettings], rdi
0x180156f9a  mov     [rsp+58h+cbTemp], edi
0x180156f9e  mov     [rsp+58h+pbTemp], rdi
0x180156fa3  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180156faa  jz      short loc_180156FC3
0x180156fac  lea     edx, [rdi+68h]; id
0x180156faf  mov     ecx, 403h; LevelKeyword
0x180156fb4  mov     r9, rbx; _a1
0x180156fb7  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180156fbe  call    WPP_SF_q
0x180156fc3  mov     rax, [rbx]
0x180156fc6  mov     this, rbx
0x180156fc9  mov     rax, [rax+0F8h]
0x180156fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156fd5  cmp     [rbx+0B8h], rdi
0x180156fdc  jz      $CleanUp_526
0x180156fe2  cmp     [rbx+204h], edi
0x180156fe8  jz      $CleanUp_526
0x180156fee  cmp     [rbx+208h], rdi
0x180156ff5  jz      $CleanUp_526
0x180156ffb  lea     rsi, [rbx+1F4h]
0x180157002  mov     rax, [rsi]
0x180157005  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18015700c  jnz     short loc_180157019
0x18015700e  mov     rax, [rsi+8]
0x180157012  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180157019  test    rax, rax
0x18015701c  jz      $CleanUp_526
0x180157022  xor     edx, edx; lpName
0x180157024  xor     ecx, ecx; lpEventAttributes
0x180157026  mov     r9d, 1F0003h; dwDesiredAccess
0x18015702c  lea     r8d, [rdx+1]; dwFlags
0x180157030  call    cs:__imp_CreateEventExW
0x180157036  mov     [rbx+228h], rax
0x18015703d  test    rax, rax
0x180157040  jnz     short loc_180157060
0x180157042  call    cs:__imp_GetLastError
0x180157048  mov     edi, eax
0x18015704a  test    eax, eax
0x18015704c  jle     $CleanUp_526
0x180157052  movzx   edi, ax
0x180157055  or      edi, 80070000h
0x18015705b  jmp     $CleanUp_526
0x180157060  mov     this, [rbx+0B8h]
0x180157067  lea     r8, [rsp+58h+pTransportSettings]
0x18015706c  lea     rdx, IID_INetworkTransportSettings
0x180157073  mov     rax, [this]
0x180157076  mov     rax, [rax]
0x180157079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015707e  mov     edi, eax
0x180157080  test    eax, eax
0x180157082  js      short loc_1801570BC
0x180157084  mov     this, [rsp+58h+pTransportSettings]
0x180157089  lea     rdx, [rsp+58h+pbTemp]
0x18015708e  mov     r9, [rbx+208h]
0x180157095  mov     r8d, [rbx+204h]
0x18015709c  mov     [rsp+58h+var_30], rdx
0x1801570a1  lea     rdx, [rsp+58h+cbTemp]
0x1801570a6  mov     rax, [this]
0x1801570a9  mov     [rsp+58h+var_38], rdx
0x1801570ae  mov     rdx, rsi
0x1801570b1  mov     rax, [rax+18h]
0x1801570b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801570ba  mov     edi, eax
0x1801570bc  lea     eax, [rdi+7FFFBFFFh]
0x1801570c2  cmp     eax, 1
0x1801570c5  ja      short $CleanUp_526
0x1801570c7  mov     rax, [rbx]
0x1801570ca  mov     this, rbx
0x1801570cd  mov     rax, [rax+100h]
0x1801570d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801570d9  mov     edx, edi; hr
0x1801570db  mov     this, rbx; this
0x1801570de  call    ?_AbortBadPushRequest@URLMONRequest@@IEAAXJ@Z; URLMONRequest::_AbortBadPushRequest(long)
0x1801570e3  mov     rax, [rbx]
0x1801570e6  mov     this, rbx
0x1801570e9  mov     rax, [rax+0F8h]
0x1801570f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801570f5  mov     rax, [rbx]
0x1801570f8  mov     this, rbx
0x1801570fb  mov     rax, [rax+100h]
0x180157102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157107  mov     this, [rsp+58h+pTransportSettings]
0x18015710c  test    this, this
0x18015710f  jz      short loc_180157126
0x180157111  mov     rax, [this]
0x180157114  mov     rax, [rax+10h]
0x180157118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015711d  mov     [rsp+58h+pTransportSettings], 0
0x180157126  mov     this, [rsp+58h+pbTemp]; pv
0x18015712b  call    cs:__imp_CoTaskMemFree
0x180157131  mov     [rsp+58h+pbTemp], 0
0x18015713a  mov     r9d, edi; __annotation("TMF:",
0x18015713d  sar     r9d, 1Fh
0x180157141  lea     eax, ds:4[r9*2]
0x180157149  movsxd  this, eax
0x18015714c  lea     rax, g_rgFastWppLevelEnabledFlags
0x180157153  test    byte ptr [rax+this*8], 8
0x180157157  jz      short loc_180157182
0x180157159  add     r9w, 2
0x18015715e  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180157165  movzx   ecx, r9w
0x180157169  mov     eax, 200h
0x18015716e  imul    ecx, eax
0x180157171  mov     edx, 69h ; 'i'; id
0x180157176  mov     r9d, edi; _a1
0x180157179  or      cx, 3; LevelKeyword
0x18015717d  call    WPP_SF_d
0x180157182  mov     eax, edi
0x180157184  add     rsp, 40h
0x180157188  pop     rdi
0x180157189  pop     rsi
0x18015718a  pop     rbx
0x18015718b  retn
```
