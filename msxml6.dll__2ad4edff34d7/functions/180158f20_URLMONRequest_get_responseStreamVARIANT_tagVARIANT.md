# URLMONRequest::get_responseStreamVARIANT(tagVARIANT *)

- ea: `0x180158f20`
- end: `0x1801590e9`
- name: `?get_responseStreamVARIANT@URLMONRequest@@UEAAJPEAUtagVARIANT@@@Z`
- size: `457`
- prototype: `HRESULT __fastcall(URLMONRequest *this, tagVARIANT *pvarBody)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180158f20`
- `0x180185008`
- `0x1801850e0`
- `0x180185d8c`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180158fea`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180158fea`
- `OLEAUT32!__imp_VariantInit` at `0x180158f8a`
- `OLEAUT32!__imp_VariantInit` at `0x180158f8a`

## pseudocode

```c
__int64 __fastcall URLMONRequest::get_responseStreamVARIANT(URLMONRequest *this, tagVARIANT *pvarBody)
{
  HRESULT v4; // ebx
  State eState; // eax
  IStream *pStm; // [rsp+60h] [rbp+8h] BYREF

  pStm = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
  if ( (xmmword_1801F6C20 & 8) != 0 )
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
0x180158f20  push    rbx
0x180158f22  push    rsi
0x180158f23  push    rdi
0x180158f24  push    r13
0x180158f26  sub     rsp, 38h
0x180158f2a  mov     rsi, pvarBody
0x180158f2d  mov     [rsp+58h+pStm], 0
0x180158f36  mov     rdi, this
0x180158f39  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180158f40  jz      short loc_180158F60
0x180158f42  mov     edx, 84h; id
0x180158f47  mov     [rsp+58h+_a2], rsi; _a2
0x180158f4c  mov     ecx, 403h; LevelKeyword
0x180158f51  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180158f58  mov     r9, rdi; _a1
0x180158f5b  call    WPP_SF_qq
0x180158f60  mov     rax, [rdi]
0x180158f63  mov     this, rdi
0x180158f66  mov     rax, [rax+0F8h]
0x180158f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158f72  mov     r13d, 2
0x180158f78  test    rsi, rsi
0x180158f7b  jnz     short loc_180158F87
0x180158f7d  mov     ebx, 80070057h
0x180158f82  jmp     $CleanUp_545
0x180158f87  mov     this, rsi; pvarg
0x180158f8a  call    cs:__imp_VariantInit
0x180158f90  mov     eax, [rdi+8Ch]
0x180158f96  cmp     eax, r13d
0x180158f99  jl      loc_180159060
0x180158f9f  cmp     dword ptr [rdi+10h], 0
0x180158fa3  jnz     loc_180159060
0x180158fa9  cmp     eax, 5
0x180158fac  jge     short loc_180158FB8
0x180158fae  mov     ebx, 8000000Ah
0x180158fb3  jmp     $CleanUp_545
0x180158fb8  cmp     byte ptr [rdi+197h], 0
0x180158fbf  jz      short loc_180158FCB
0x180158fc1  mov     ebx, 8007139Fh
0x180158fc6  jmp     $CleanUp_545
0x180158fcb  cmp     qword ptr [rdi+180h], 0
0x180158fd3  jnz     short loc_180158FC1
0x180158fd5  xor     ebx, ebx
0x180158fd7  cmp     [rdi+170h], rbx
0x180158fde  jz      short loc_18015903B
0x180158fe0  lea     r8, [rsp+58h+pStm]; ppstm
0x180158fe5  xor     ecx, ecx; hGlobal
0x180158fe7  lea     edx, [rbx+1]; fDeleteOnRelease
0x180158fea  call    cs:__imp_CreateStreamOnHGlobal
0x180158ff0  mov     ebx, eax
0x180158ff2  test    eax, eax
0x180158ff4  js      short $CleanUp_545
0x180158ff6  mov     this, [rdi+170h]
0x180158ffd  xor     r9d, r9d
0x180159000  mov     pvarBody, [rsp+58h+pStm]
0x180159005  or      r8, 0FFFFFFFFFFFFFFFFh
0x180159009  mov     [rsp+58h+_a2], 0
0x180159012  mov     rax, [this]
0x180159015  mov     rax, [rax+38h]
0x180159019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015901e  mov     ebx, eax
0x180159020  test    eax, eax
0x180159022  js      short $CleanUp_545
0x180159024  mov     rax, [rsp+58h+pStm]
0x180159029  mov     [rsi+8], rax
0x18015902d  mov     word ptr [rsi], 0Dh
0x180159032  mov     [rsp+58h+pStm], 0
0x18015903b  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180159042  jz      short $CleanUp_545
0x180159044  mov     r9, [rsi+8]; _a1
0x180159048  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015904f  mov     edx, 85h; id
0x180159054  mov     ecx, 403h; LevelKeyword
0x180159059  call    WPP_SF_q
0x18015905e  jmp     short $CleanUp_545
0x180159060  mov     ebx, 0C00C023Fh
0x180159065  mov     rax, [rdi]
0x180159068  mov     this, rdi
0x18015906b  mov     rax, [rax+100h]
0x180159072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159077  mov     this, [rsp+58h+pStm]
0x18015907c  test    this, this
0x18015907f  jz      short loc_180159096
0x180159081  mov     rax, [this]
0x180159084  mov     rax, [rax+10h]
0x180159088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015908d  mov     [rsp+58h+pStm], 0
0x180159096  mov     r9d, ebx; __annotation("TMF:",
0x180159099  sar     r9d, 1Fh
0x18015909d  lea     eax, ds:4[r9*2]
0x1801590a5  movsxd  this, eax
0x1801590a8  lea     rax, g_rgFastWppLevelEnabledFlags
0x1801590af  test    byte ptr [rax+this*8], 8
0x1801590b3  jz      short loc_1801590DD
0x1801590b5  add     r9w, r13w
0x1801590b9  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801590c0  movzx   ecx, r9w
0x1801590c4  mov     eax, 200h
0x1801590c9  imul    ecx, eax
0x1801590cc  mov     edx, 86h; id
0x1801590d1  mov     r9d, ebx; _a1
0x1801590d4  or      cx, 3; LevelKeyword
0x1801590d8  call    WPP_SF_d
0x1801590dd  mov     eax, ebx
0x1801590df  add     rsp, 38h
0x1801590e3  pop     r13
0x1801590e5  pop     rdi
0x1801590e6  pop     rsi
0x1801590e7  pop     rbx
0x1801590e8  retn
```
