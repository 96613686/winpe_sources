# URLMONRequest::ApplySetting(TRANSPORT_SETTING_ID const *,ulong,uchar const *,ulong *,uchar * *)

- ea: `0x180155620`
- end: `0x1801557f3`
- name: `?ApplySetting@URLMONRequest@@UEAAJPEBUTRANSPORT_SETTING_ID@@KPEBEPEAKPEAPEAE@Z`
- size: `467`
- prototype: `__int64 __fastcall(URLMONRequest *this, const TRANSPORT_SETTING_ID *pSettingId, int cbIn, const unsigned __int8 *pbValueIn, unsigned int *pcbOut, unsigned __int8 **ppbValueOut)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800868bc`
- `0x180155620`
- `0x180178528`
- `0x180185008`
- `0x180185090`
- `0x1801858a8`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180155794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180155718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180155718`

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
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
            if ( (BYTE8(xmmword_1801F6C10) & 8) != 0 )
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
0x180155620  mov     r11, rsp
0x180155623  push    rbx
0x180155624  push    rbp
0x180155625  push    rsi
0x180155626  push    rdi
0x180155627  push    r12
0x180155629  push    r14
0x18015562b  push    r15
0x18015562d  sub     rsp, 50h
0x180155631  mov     r15, pbValueIn
0x180155634  mov     r12d, cbIn
0x180155637  mov     rbp, pSettingId
0x18015563a  mov     rdi, this
0x18015563d  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180155644  mov     rbx, [rsp+88h+arg_28]
0x18015564c  mov     rsi, [rsp+88h+arg_20]
0x180155654  jz      short loc_180155694
0x180155656  mov     [r11-48h], rbx
0x18015565a  lea     this, GUID_NULL
0x180155661  mov     [r11-50h], rsi
0x180155665  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015566c  mov     [r11-58h], pbValueIn
0x180155670  test    pSettingId, pSettingId
0x180155673  mov     rax, pSettingId
0x180155676  mov     [r11-60h], r12d
0x18015567a  cmovz   rax, this
0x18015567e  mov     edx, 61h ; 'a'; id
0x180155683  mov     ecx, 403h; LevelKeyword
0x180155688  mov     [r11-68h], rax
0x18015568c  mov     pbValueIn, rdi; _a1
0x18015568f  call    WPP_SF_q_guid_dqqq
0x180155694  mov     rax, [rdi]
0x180155697  mov     this, rdi
0x18015569a  mov     rax, [rax+0F8h]
0x1801556a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801556a6  test    rsi, rsi
0x1801556a9  jnz     short loc_1801556B5
0x1801556ab  mov     ebx, 80004003h
0x1801556b0  jmp     $CleanUp_514
0x1801556b5  mov     dword ptr [rsi], 0
0x1801556bb  test    rbx, rbx
0x1801556be  jz      short loc_1801556AB
0x1801556c0  mov     qword ptr [rbx], 0
0x1801556c7  test    rbp, rbp
0x1801556ca  jnz     short loc_1801556D6
0x1801556cc  mov     ebx, 80070057h
0x1801556d1  jmp     $CleanUp_514
0x1801556d6  test    r15, r15
0x1801556d9  jz      short loc_1801556CC
0x1801556db  mov     this, rdi; this
0x1801556de  call    ?_FreeTransportSettings@URLMONRequest@@IEAAXXZ; URLMONRequest::_FreeTransportSettings(void)
0x1801556e3  cmp     dword ptr [rdi+8Ch], 1
0x1801556ea  jz      short loc_1801556F6
0x1801556ec  mov     ebx, 8007139Fh
0x1801556f1  jmp     $CleanUp_514
0x1801556f6  cmp     byte ptr [rdi+0Eh], 0
0x1801556fa  jnz     short loc_18015577B
0x1801556fc  cmp     dword ptr [rdi+260h], 0
0x180155703  jnz     short loc_18015577B
0x180155705  cmp     dword ptr [rdi+0B0h], 0
0x18015570c  jnz     short loc_180155715
0x18015570e  mov     ebx, 80010102h
0x180155713  jmp     short $CleanUp_514
0x180155715  mov     this, r12; cb
0x180155718  call    cs:__imp_CoTaskMemAlloc
0x18015571e  mov     rsi, rax
0x180155721  test    rax, rax
0x180155724  jnz     short loc_18015572D
0x180155726  mov     ebx, 8007000Eh
0x18015572b  jmp     short $CleanUp_514
0x18015572d  xor     ebx, ebx
0x18015572f  mov     r8, r12; Size
0x180155732  mov     pSettingId, r15; Src
0x180155735  mov     this, rsi; void *
0x180155738  call    memcpy_0
0x18015573d  movups  xmm0, xmmword ptr [rbp+0]
0x180155741  mov     [rdi+204h], r12d
0x180155748  mov     [rdi+208h], rsi
0x18015574f  movdqu  xmmword ptr [rdi+1F4h], xmm0
0x180155757  mov     word ptr [rdi+195h], 1
0x180155760  test    byte ptr cs:xmmword_1801F6C10+8, 8; __annotation("TMF:",
0x180155767  jz      short $CleanUp_514
0x180155769  lea     edx, [rbx+62h]; _a1
0x18015576c  mov     [rsp+88h+id], ebx; id
0x180155770  lea     r9d, [rbx+1]; LevelKeyword
0x180155774  call    WPP_SF_ll
0x180155779  jmp     short $CleanUp_514
0x18015577b  mov     ebx, 80004004h
0x180155780  mov     rax, [rdi]
0x180155783  mov     this, rdi
0x180155786  mov     rax, [rax+100h]
0x18015578d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155792  xor     ecx, ecx; pv
0x180155794  call    cs:__imp_CoTaskMemFree
0x18015579a  mov     r10d, ebx; __annotation("TMF:",
0x18015579d  sar     r10d, 1Fh
0x1801557a1  lea     eax, ds:4[r10*2]
0x1801557a9  movsxd  this, eax
0x1801557ac  lea     rax, g_rgFastWppLevelEnabledFlags
0x1801557b3  test    byte ptr [rax+this*8], 8
0x1801557b7  jz      short loc_1801557E2
0x1801557b9  add     r10w, 2
0x1801557be  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801557c5  movzx   ecx, r10w
0x1801557c9  mov     eax, 200h
0x1801557ce  imul    ecx, eax
0x1801557d1  mov     edx, 63h ; 'c'; id
0x1801557d6  mov     r9d, ebx; _a1
0x1801557d9  or      cx, 3; LevelKeyword
0x1801557dd  call    WPP_SF_d
0x1801557e2  mov     eax, ebx
0x1801557e4  add     rsp, 50h
0x1801557e8  pop     r15
0x1801557ea  pop     r14
0x1801557ec  pop     r12
0x1801557ee  pop     rdi
0x1801557ef  pop     rsi
0x1801557f0  pop     rbp
0x1801557f1  pop     rbx
0x1801557f2  retn
```
