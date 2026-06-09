# URLMONRequest::ApplySetting(TRANSPORT_SETTING_ID const *,ulong,uchar const *,ulong *,uchar * *)

- ea: `0x180158ca0`
- end: `0x180158e84`
- name: `?ApplySetting@URLMONRequest@@UEAAJPEBUTRANSPORT_SETTING_ID@@KPEBEPEAKPEAPEAE@Z`
- size: `484`
- prototype: `HRESULT __fastcall(URLMONRequest *this, const TRANSPORT_SETTING_ID *pSettingId, unsigned int cbIn, const unsigned __int8 *pbValueIn, unsigned int *pcbOut, unsigned __int8 **ppbValueOut)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180084fe4`
- `0x180158ca0`
- `0x18017c1d8`
- `0x180189008`
- `0x180189090`
- `0x1801898b4`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180158e1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180158e1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180158d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180158d9c`

## pseudocode

```c
__int64 __fastcall URLMONRequest::ApplySetting(
        URLMONRequest *this,
        const TRANSPORT_SETTING_ID *pSettingId,
        int cbIn,
        const unsigned __int8 *pbValueIn,
        unsigned int *pcbOut,
        unsigned __int8 **ppbValueOut)
{
  SIZE_T v7; // r12
  const TRANSPORT_SETTING_ID *v10; // rax
  int v11; // ebx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rsi
  unsigned __int16 v14; // cx
  const _GUID *v15; // r8
  TRANSPORT_SETTING_ID v16; // xmm0

  v7 = (unsigned int)cbIn;
  if ( (xmmword_1801FAD20 & 8) != 0 )
  {
    v10 = pSettingId;
    if ( !pSettingId )
      v10 = (const TRANSPORT_SETTING_ID *)&GUID_NULL;
    WPP_SF_q_guid_dqqq(
      0x403u,
      0x61u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      this,
      &v10->Guid,
      cbIn,
      pbValueIn,
      pcbOut,
      ppbValueOut);
  }
  this->Lock(this);
  if ( pcbOut && (*pcbOut = 0, ppbValueOut) )
  {
    *ppbValueOut = 0;
    if ( pSettingId && pbValueIn )
    {
      URLMONRequest::_FreeTransportSettings(this);
      if ( this->_eState == OPENED )
      {
        if ( this->_fAborted || this->_fAbortPending )
        {
          v11 = -2147467260;
        }
        else if ( this->_fMta )
        {
          v12 = (unsigned __int8 *)CoTaskMemAlloc(v7);
          v13 = v12;
          if ( v12 )
          {
            v11 = 0;
            memcpy_0(v12, pbValueIn, v7);
            v16 = *pSettingId;
            this->_cbSetting = v7;
            this->_pbSetting = v13;
            this->_SettingId = v16;
            *(_WORD *)&this->_fDisableUI = 1;
            if ( (BYTE8(xmmword_1801FAD10) & 8) != 0 )
              WPP_SF_ll(v14, 0x62u, v15, 1, 0);
          }
          else
          {
            v11 = -2147024882;
          }
        }
        else
        {
          v11 = -2147417854;
        }
      }
      else
      {
        v11 = -2147019873;
      }
    }
    else
    {
      v11 = -2147024809;
    }
  }
  else
  {
    v11 = -2147467261;
  }
  this->Unlock(this);
  CoTaskMemFree(0);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v11 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(v11 >> 31) + 2) << 9) | 3,
      0x63u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180158ca0  mov     r11, rsp
0x180158ca3  push    rbx
0x180158ca4  push    rbp
0x180158ca5  push    rsi
0x180158ca6  push    rdi
0x180158ca7  push    r12
0x180158ca9  push    r14
0x180158cab  push    r15
0x180158cad  sub     rsp, 50h
0x180158cb1  mov     r15, pbValueIn
0x180158cb4  mov     r12d, cbIn
0x180158cb7  mov     rbp, pSettingId
0x180158cba  mov     rdi, this
0x180158cbd  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x180158cc4  mov     rbx, [rsp+88h+arg_28]
0x180158ccc  mov     rsi, [rsp+88h+arg_20]
0x180158cd4  jz      short loc_180158D14
0x180158cd6  mov     [r11-48h], rbx
0x180158cda  lea     this, GUID_NULL
0x180158ce1  mov     [r11-50h], rsi
0x180158ce5  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180158cec  mov     [r11-58h], pbValueIn
0x180158cf0  test    pSettingId, pSettingId
0x180158cf3  mov     rax, pSettingId
0x180158cf6  mov     [r11-60h], r12d
0x180158cfa  cmovz   rax, this
0x180158cfe  mov     edx, 61h ; 'a'; id
0x180158d03  mov     ecx, 403h; LevelKeyword
0x180158d08  mov     [r11-68h], rax
0x180158d0c  mov     pbValueIn, rdi; _a1
0x180158d0f  call    WPP_SF_q_guid_dqqq
0x180158d14  mov     rax, [rdi]
0x180158d17  mov     this, rdi
0x180158d1a  mov     rax, [rax+0F8h]
0x180158d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158d26  test    rsi, rsi
0x180158d29  jnz     short loc_180158D35
0x180158d2b  mov     ebx, 80004003h
0x180158d30  jmp     $CleanUp_514
0x180158d35  mov     dword ptr [rsi], 0
0x180158d3b  test    rbx, rbx
0x180158d3e  jz      short loc_180158D2B
0x180158d40  mov     qword ptr [rbx], 0
0x180158d47  test    rbp, rbp
0x180158d4a  jnz     short loc_180158D56
0x180158d4c  mov     ebx, 80070057h
0x180158d51  jmp     $CleanUp_514
0x180158d56  test    r15, r15
0x180158d59  jz      short loc_180158D4C
0x180158d5b  mov     this, rdi; this
0x180158d5e  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x180158d63  cmp     dword ptr [rdi+8Ch], 1
0x180158d6a  jz      short loc_180158D76
0x180158d6c  mov     ebx, 8007139Fh
0x180158d71  jmp     $CleanUp_514
0x180158d76  cmp     byte ptr [rdi+0Eh], 0
0x180158d7a  jnz     loc_180158E05
0x180158d80  cmp     dword ptr [rdi+260h], 0
0x180158d87  jnz     short loc_180158E05
0x180158d89  cmp     dword ptr [rdi+0B0h], 0
0x180158d90  jnz     short loc_180158D99
0x180158d92  mov     ebx, 80010102h
0x180158d97  jmp     short $CleanUp_514
0x180158d99  mov     this, r12; cb
0x180158d9c  call    cs:__imp_CoTaskMemAlloc
0x180158da3  nop     dword ptr [rax+rax+00h]
0x180158da8  mov     rsi, rax
0x180158dab  test    rax, rax
0x180158dae  jnz     short loc_180158DB7
0x180158db0  mov     ebx, 8007000Eh
0x180158db5  jmp     short $CleanUp_514
0x180158db7  xor     ebx, ebx
0x180158db9  mov     r8, r12; Size
0x180158dbc  mov     pSettingId, r15; Src
0x180158dbf  mov     this, rsi; void *
0x180158dc2  call    memcpy_0
0x180158dc7  movups  xmm0, xmmword ptr [rbp+0]
0x180158dcb  mov     [rdi+204h], r12d
0x180158dd2  mov     [rdi+208h], rsi
0x180158dd9  movdqu  xmmword ptr [rdi+1F4h], xmm0
0x180158de1  mov     word ptr [rdi+195h], 1
0x180158dea  test    byte ptr cs:xmmword_1801FAD10+8, 8; __annotation("TMF:",
0x180158df1  jz      short $CleanUp_514
0x180158df3  lea     edx, [rbx+62h]; _a1
0x180158df6  mov     [rsp+88h+id], ebx; id
0x180158dfa  lea     r9d, [rbx+1]; LevelKeyword
0x180158dfe  call    WPP_SF_ll
0x180158e03  jmp     short $CleanUp_514
0x180158e05  mov     ebx, 80004004h
0x180158e0a  mov     rax, [rdi]
0x180158e0d  mov     this, rdi
0x180158e10  mov     rax, [rax+100h]
0x180158e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158e1c  xor     ecx, ecx; pv
0x180158e1e  call    cs:__imp_CoTaskMemFree
0x180158e25  nop     dword ptr [rax+rax+00h]
0x180158e2a  mov     r10d, ebx; __annotation("TMF:",
0x180158e2d  sar     r10d, 1Fh
0x180158e31  lea     eax, ds:4[r10*2]
0x180158e39  movsxd  this, eax
0x180158e3c  lea     rax, g_rgFastWppLevelEnabledFlags
0x180158e43  test    byte ptr [rax+this*8], 8
0x180158e47  jz      short loc_180158E72
0x180158e49  add     r10w, 2
0x180158e4e  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180158e55  movzx   ecx, r10w
0x180158e59  mov     eax, 200h
0x180158e5e  imul    ecx, eax
0x180158e61  mov     edx, 63h ; 'c'; id
0x180158e66  mov     r9d, ebx; _a1
0x180158e69  or      cx, 3; LevelKeyword
0x180158e6d  call    WPP_SF_d
0x180158e72  mov     eax, ebx
0x180158e74  add     rsp, 50h
0x180158e78  pop     r15
0x180158e7a  pop     r14
0x180158e7c  pop     r12
0x180158e7e  pop     rdi
0x180158e7f  pop     rsi
0x180158e80  pop     rbp
0x180158e81  pop     rbx
0x180158e82  retn
```
