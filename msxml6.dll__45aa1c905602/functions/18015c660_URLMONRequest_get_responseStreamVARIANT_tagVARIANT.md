# URLMONRequest::get_responseStreamVARIANT(tagVARIANT *)

- ea: `0x18015c660`
- end: `0x18015c836`
- name: `?get_responseStreamVARIANT@URLMONRequest@@UEAAJPEAUtagVARIANT@@@Z`
- size: `470`
- prototype: `HRESULT __fastcall(URLMONRequest *this, tagVARIANT *pvarBody)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18015c660`
- `0x180189008`
- `0x1801890e0`
- `0x180189d98`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015c730`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015c730`
- `OLEAUT32!__imp_VariantInit` at `0x18015c6ca`
- `OLEAUT32!__imp_VariantInit` at `0x18015c6ca`

## pseudocode

```c
__int64 __fastcall URLMONRequest::get_responseStreamVARIANT(URLMONRequest *this, tagVARIANT *pvarBody)
{
  HRESULT v4; // ebx
  State eState; // eax
  IStream *pStm; // [rsp+60h] [rbp+8h] BYREF

  pStm = 0;
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_qq(0x403u, 0x84u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, this, pvarBody);
  this->Lock(this);
  if ( !pvarBody )
  {
    v4 = -2147024809;
    goto $CleanUp_545;
  }
  VariantInit(pvarBody);
  eState = this->_eState;
  if ( eState < SENDING || this->_fUserAbort )
  {
    v4 = -1072954817;
    goto $CleanUp_545;
  }
  if ( eState < RESPONSE )
  {
    v4 = -2147483638;
    goto $CleanUp_545;
  }
  if ( this->_fStreamBeforeComplete || this->_pstrmCustom )
  {
    v4 = -2147019873;
    goto $CleanUp_545;
  }
  v4 = 0;
  if ( this->_pstrmResponse )
  {
    v4 = CreateStreamOnHGlobal(0, 1, &pStm);
    if ( v4 < 0 )
      goto $CleanUp_545;
    v4 = ((__int64 (__fastcall *)(IStream *, IStream *, __int64, _QWORD, _QWORD))this->_pstrmResponse->CopyTo)(
           this->_pstrmResponse,
           pStm,
           -1,
           0,
           0);
    if ( v4 < 0 )
      goto $CleanUp_545;
    pvarBody->llVal = (__int64)pStm;
    pvarBody->vt = 13;
    pStm = 0;
  }
  if ( (xmmword_1801FAD20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x85u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, pvarBody->decVal.Lo64);
$CleanUp_545:
  this->Unlock(this);
  if ( pStm )
  {
    pStm->Release(pStm);
    pStm = 0;
  }
  if ( (g_rgFastWppLevelEnabledFlags[2 * (v4 >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d((((unsigned __int16)(v4 >> 31) + 2) << 9) | 3, 0x86u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18015c660  push    rbx
0x18015c662  push    rsi
0x18015c663  push    rdi
0x18015c664  push    r13
0x18015c666  sub     rsp, 38h
0x18015c66a  mov     rsi, pvarBody
0x18015c66d  mov     [rsp+58h+pStm], 0
0x18015c676  mov     rdi, this
0x18015c679  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015c680  jz      short loc_18015C6A0
0x18015c682  mov     edx, 84h; id
0x18015c687  mov     [rsp+58h+_a2], rsi; _a2
0x18015c68c  mov     ecx, 403h; LevelKeyword
0x18015c691  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015c698  mov     r9, rdi; _a1
0x18015c69b  call    WPP_SF_qq
0x18015c6a0  mov     rax, [rdi]
0x18015c6a3  mov     this, rdi
0x18015c6a6  mov     rax, [rax+0F8h]
0x18015c6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c6b2  mov     r13d, 2
0x18015c6b8  test    rsi, rsi
0x18015c6bb  jnz     short loc_18015C6C7
0x18015c6bd  mov     ebx, 80070057h
0x18015c6c2  jmp     $CleanUp_545
0x18015c6c7  mov     this, rsi; pvarg
0x18015c6ca  call    cs:__imp_VariantInit
0x18015c6d1  nop     dword ptr [rax+rax+00h]
0x18015c6d6  mov     eax, [rdi+8Ch]
0x18015c6dc  cmp     eax, r13d
0x18015c6df  jl      loc_18015C7AC
0x18015c6e5  cmp     dword ptr [rdi+10h], 0
0x18015c6e9  jnz     loc_18015C7AC
0x18015c6ef  cmp     eax, 5
0x18015c6f2  jge     short loc_18015C6FE
0x18015c6f4  mov     ebx, 8000000Ah
0x18015c6f9  jmp     $CleanUp_545
0x18015c6fe  cmp     byte ptr [rdi+197h], 0
0x18015c705  jz      short loc_18015C711
0x18015c707  mov     ebx, 8007139Fh
0x18015c70c  jmp     $CleanUp_545
0x18015c711  cmp     qword ptr [rdi+180h], 0
0x18015c719  jnz     short loc_18015C707
0x18015c71b  xor     ebx, ebx
0x18015c71d  cmp     [rdi+170h], rbx
0x18015c724  jz      short loc_18015C787
0x18015c726  lea     r8, [rsp+58h+pStm]; ppstm
0x18015c72b  xor     ecx, ecx; hGlobal
0x18015c72d  lea     edx, [rbx+1]; fDeleteOnRelease
0x18015c730  call    cs:__imp_CreateStreamOnHGlobal
0x18015c737  nop     dword ptr [rax+rax+00h]
0x18015c73c  mov     ebx, eax
0x18015c73e  test    eax, eax
0x18015c740  js      short $CleanUp_545
0x18015c742  mov     this, [rdi+170h]
0x18015c749  xor     r9d, r9d
0x18015c74c  mov     pvarBody, [rsp+58h+pStm]
0x18015c751  or      r8, 0FFFFFFFFFFFFFFFFh
0x18015c755  mov     [rsp+58h+_a2], 0
0x18015c75e  mov     rax, [this]
0x18015c761  mov     rax, [rax+38h]
0x18015c765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c76a  mov     ebx, eax
0x18015c76c  test    eax, eax
0x18015c76e  js      short $CleanUp_545
0x18015c770  mov     rax, [rsp+58h+pStm]
0x18015c775  mov     [rsi+8], rax
0x18015c779  mov     word ptr [rsi], 0Dh
0x18015c77e  mov     [rsp+58h+pStm], 0
0x18015c787  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015c78e  jz      short $CleanUp_545
0x18015c790  mov     r9, [rsi+8]; _a1
0x18015c794  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015c79b  mov     edx, 85h; id
0x18015c7a0  mov     ecx, 403h; LevelKeyword
0x18015c7a5  call    WPP_SF_q
0x18015c7aa  jmp     short $CleanUp_545
0x18015c7ac  mov     ebx, 0C00C023Fh
0x18015c7b1  mov     rax, [rdi]
0x18015c7b4  mov     this, rdi
0x18015c7b7  mov     rax, [rax+100h]
0x18015c7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c7c3  mov     this, [rsp+58h+pStm]
0x18015c7c8  test    this, this
0x18015c7cb  jz      short loc_18015C7E2
0x18015c7cd  mov     rax, [this]
0x18015c7d0  mov     rax, [rax+10h]
0x18015c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c7d9  mov     [rsp+58h+pStm], 0
0x18015c7e2  mov     r9d, ebx; __annotation("TMF:",
0x18015c7e5  sar     r9d, 1Fh
0x18015c7e9  lea     eax, ds:4[r9*2]
0x18015c7f1  movsxd  this, eax
0x18015c7f4  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015c7fb  test    byte ptr [rax+this*8], 8
0x18015c7ff  jz      short loc_18015C829
0x18015c801  add     r9w, r13w
0x18015c805  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015c80c  movzx   ecx, r9w
0x18015c810  mov     eax, 200h
0x18015c815  imul    ecx, eax
0x18015c818  mov     edx, 86h; id
0x18015c81d  mov     r9d, ebx; _a1
0x18015c820  or      cx, 3; LevelKeyword
0x18015c824  call    WPP_SF_d
0x18015c829  mov     eax, ebx
0x18015c82b  add     rsp, 38h
0x18015c82f  pop     r13
0x18015c831  pop     rdi
0x18015c832  pop     rsi
0x18015c833  pop     rbx
0x18015c834  retn
```
