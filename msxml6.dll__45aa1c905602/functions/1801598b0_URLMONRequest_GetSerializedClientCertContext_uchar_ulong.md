# URLMONRequest::GetSerializedClientCertContext(uchar * *,ulong *)

- ea: `0x1801598b0`
- end: `0x180159a37`
- name: `?GetSerializedClientCertContext@URLMONRequest@@MEAAJPEAPEAEPEAK@Z`
- size: `391`
- prototype: `HRESULT __fastcall(URLMONRequest *this, unsigned __int8 **ppbClientCert, unsigned int *pcbClientCert)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1801598b0`
- `0x18015b670`
- `0x18017c1d8`
- `0x180189008`
- `0x180189994`
- `0x180189fd8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180159950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180159950`

## pseudocode

```c
__int64 __fastcall URLMONRequest::GetSerializedClientCertContext(
        URLMONRequest *this,
        unsigned __int8 **ppbClientCert,
        unsigned int *pcbClientCert)
{
  int v6; // ebx
  unsigned int cbClientCert; // eax
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbp

  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_qqq(0x403u, 0xB1u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, ppbClientCert, pcbClientCert);
  this->Lock(this);
  v6 = URLMONRequest::_OnClientCert(this);
  if ( v6 < 0 )
    goto $CleanUp_520;
  if ( !ppbClientCert || (*ppbClientCert = 0, !pcbClientCert) )
  {
    v6 = -2147467261;
$CleanUp_520:
    this->Unlock(this);
    goto LABEL_15;
  }
  *pcbClientCert = 0;
  cbClientCert = this->_cbClientCert;
  if ( !cbClientCert || !this->_pbClientCert )
  {
    v6 = -2147467259;
    goto $CleanUp_520;
  }
  v8 = (unsigned __int8 *)CoTaskMemAlloc(cbClientCert);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    goto $CleanUp_520;
  }
  memcpy_0(v8, this->_pbClientCert, this->_cbClientCert);
  *ppbClientCert = v9;
  *pcbClientCert = this->_cbClientCert;
  this->Unlock(this);
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_qd(0x403u, 0xB2u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, *ppbClientCert, *pcbClientCert);
LABEL_15:
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v6 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v6 >> 31) + 2) << 9) | 3, 0xB3u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801598b0  push    rbx
0x1801598b2  push    rbp
0x1801598b3  push    rsi
0x1801598b4  push    rdi
0x1801598b5  push    r14
0x1801598b7  sub     rsp, 30h
0x1801598bb  mov     r14, pcbClientCert
0x1801598be  mov     rsi, ppbClientCert
0x1801598c1  mov     rdi, this
0x1801598c4  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x1801598cb  jz      short loc_1801598F0
0x1801598cd  mov     [rsp+58h+_a3], pcbClientCert; _a3
0x1801598d2  mov     edx, 0B1h; id
0x1801598d7  lea     pcbClientCert, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801598de  mov     [rsp+58h+_a2], rsi; _a2
0x1801598e3  mov     ecx, 403h; LevelKeyword
0x1801598e8  mov     r9, rdi; _a1
0x1801598eb  call    WPP_SF_qqq
0x1801598f0  mov     rax, [rdi]
0x1801598f3  mov     this, rdi
0x1801598f6  mov     rax, [rax+0F8h]
0x1801598fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159902  mov     this, rdi; this
0x180159905  call    ?_OnClientCert@URLMONRequest@@IEAAJXZ; URLMONRequest::_OnClientCert(void)
0x18015990a  mov     ebx, eax
0x18015990c  test    eax, eax
0x18015990e  js      $CleanUp_520
0x180159914  test    rsi, rsi
0x180159917  jnz     short loc_180159923
0x180159919  mov     ebx, 80004003h
0x18015991e  jmp     $CleanUp_520
0x180159923  mov     qword ptr [rsi], 0
0x18015992a  test    r14, r14
0x18015992d  jz      short loc_180159919
0x18015992f  mov     dword ptr [r14], 0
0x180159936  mov     eax, [rdi+1D8h]
0x18015993c  test    eax, eax
0x18015993e  jz      loc_1801599CA
0x180159944  cmp     qword ptr [rdi+1E0h], 0
0x18015994c  jz      short loc_1801599CA
0x18015994e  mov     ecx, eax; cb
0x180159950  call    cs:__imp_CoTaskMemAlloc
0x180159957  nop     dword ptr [rax+rax+00h]
0x18015995c  mov     rbp, rax
0x18015995f  test    rax, rax
0x180159962  jnz     short loc_18015996B
0x180159964  mov     ebx, 8007000Eh
0x180159969  jmp     short $CleanUp_520
0x18015996b  mov     r8d, [rdi+1D8h]; Size
0x180159972  mov     this, rbp; void *
0x180159975  mov     ppbClientCert, [rdi+1E0h]; Src
0x18015997c  call    memcpy_0
0x180159981  mov     [rsi], rbp
0x180159984  mov     this, rdi
0x180159987  mov     eax, [rdi+1D8h]
0x18015998d  mov     [r14], eax
0x180159990  mov     rax, [rdi]
0x180159993  mov     rax, [rax+100h]
0x18015999a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015999f  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x1801599a6  jz      short loc_1801599E1
0x1801599a8  mov     eax, [r14]
0x1801599ab  lea     pcbClientCert, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801599b2  mov     r9, [rsi]; _a1
0x1801599b5  mov     edx, 0B2h; id
0x1801599ba  mov     ecx, 403h; LevelKeyword
0x1801599bf  mov     dword ptr [rsp+58h+_a2], eax; _a2
0x1801599c3  call    WPP_SF_qd
0x1801599c8  jmp     short loc_1801599E1
0x1801599ca  mov     ebx, 80004005h
0x1801599cf  mov     rax, [rdi]
0x1801599d2  mov     this, rdi
0x1801599d5  mov     rax, [rax+100h]
0x1801599dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801599e1  mov     r9d, ebx; __annotation("TMF:",
0x1801599e4  sar     r9d, 1Fh
0x1801599e8  lea     eax, ds:4[r9*2]
0x1801599f0  movsxd  this, eax
0x1801599f3  lea     rax, g_rgFastWppLevelEnabledFlags
0x1801599fa  test    byte ptr [rax+this*8], 8
0x1801599fe  jz      short loc_180159A29
0x180159a00  add     r9w, 2
0x180159a05  lea     pcbClientCert, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180159a0c  movzx   ecx, r9w
0x180159a10  mov     eax, 200h
0x180159a15  imul    ecx, eax
0x180159a18  mov     edx, 0B3h; id
0x180159a1d  mov     r9d, ebx; _a1
0x180159a20  or      cx, 3; LevelKeyword
0x180159a24  call    WPP_SF_d
0x180159a29  mov     eax, ebx
0x180159a2b  add     rsp, 30h
0x180159a2f  pop     r14
0x180159a31  pop     rdi
0x180159a32  pop     rsi
0x180159a33  pop     rbp
0x180159a34  pop     rbx
0x180159a35  retn
```
