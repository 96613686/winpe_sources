# XMLHttp2::_Send(ISequentialStream *,unsigned __int64)

- ea: `0x1010484e`
- end: `0x1010496b`
- name: `?_Send@XMLHttp2@@AAGJPAUISequentialStream@@_K@Z`
- size: `285`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, ISequentialStream *pBody@<edx>, unsigned __int64 cbBody)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10103610`

## callees

- `0x10067b20`
- `0x1010484e`
- `0x101300a3`
- `0x10180006`
- `0x10180880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101048a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101048a3`

## pseudocode

```c
HRESULT __fastcall XMLHttp2::_Send(XMLHttp2 *this, const _GUID *pBody, unsigned __int64 cbBody)
{
  ISequentialStream *v3; // esi
  unsigned int m_dwStaThreadId; // esi
  int v6; // edi
  HRESULT (__stdcall *send)(IXMLHTTPRequest *, tagVARIANT); // ecx
  unsigned __int64 v9; // [esp+0h] [ebp-28h]
  IStream *pUploadStream; // [esp+10h] [ebp-18h] BYREF
  const _GUID *v11; // [esp+14h] [ebp-14h]
  tagVARIANT varBody; // [esp+18h] [ebp-10h] BYREF

  pUploadStream = 0;
  v3 = (ISequentialStream *)pBody;
  memset(&varBody, 0, sizeof(varBody));
  v11 = pBody;
  if ( (byte_10185760[0] & 2) != 0 )
    WPP_SF_qqI(
      (unsigned __int16)this,
      (unsigned __int16)this,
      pBody,
      (const void *)cbBody,
      (const void *)HIDWORD(cbBody),
      v9);
  if ( cbBody >= 0xFFFFFFFF )
  {
    v6 = -2147024809;
  }
  else
  {
    if ( this->m_dwStaThreadId )
    {
      m_dwStaThreadId = this->m_dwStaThreadId;
      if ( m_dwStaThreadId != GetCurrentThreadId() )
      {
        v6 = -2147417842;
        goto CleanUp_380;
      }
      v3 = (ISequentialStream *)v11;
    }
    if ( v3 )
    {
      v6 = URLMONUploadStream::CreateInstance(v3, (unsigned int)cbBody, &pUploadStream);
      if ( v6 < 0 )
        goto CleanUp_380;
      varBody.vt = 13;
      varBody.decVal.Lo32 = (unsigned int)pUploadStream;
    }
    else
    {
      varBody.vt = 1;
    }
    send = this->m_pXMLHttp->send;
    v6 = ((int (__thiscall *)(HRESULT (__stdcall *)(IXMLHTTPRequest *, tagVARIANT), XMLHttp *, _DWORD, unsigned int, unsigned int, unsigned int))send)(
           send,
           this->m_pXMLHttp,
           *(_DWORD *)&varBody.vt,
           varBody.decVal.Hi32,
           varBody.decVal.Lo32,
           varBody.decVal.Mid32);
  }
CleanUp_380:
  if ( pUploadStream )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pUploadStream->Release)(
      pUploadStream->Release,
      pUploadStream);
    pUploadStream = 0;
  }
  if ( (byte_10185760[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x8Cu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1010484e  mov     edi, edi
0x10104850  push    ebp
0x10104851  mov     ebp, esp
0x10104853  and     esp, 0FFFFFFF8h
0x10104856  sub     esp, 1Ch
0x10104859  push    ebx
0x1010485a  push    esi
0x1010485b  push    edi; TraceGuid
0x1010485c  xor     eax, eax
0x1010485e  mov     [esp+28h+pUploadStream], 0
0x10104866  lea     edi, [esp+28h+varBody]
0x1010486a  mov     esi, pBody
0x1010486c  stosd
0x1010486d  mov     ebx, this
0x1010486f  mov     [esp+28h+var_14], esi
0x10104873  stosd
0x10104874  stosd
0x10104875  stosd
0x10104876  test    byte_10185760, 2; __annotation("TMF:",
0x1010487d  mov     edi, dword ptr [ebp+cbBody+4]
0x10104880  jz      short loc_1010488E
0x10104882  push    edi; id
0x10104883  push    dword ptr [ebp+cbBody]; LevelKeyword
0x10104886  push    esi; _a3
0x10104887  push    ebx; _a2
0x10104888  push    this; _a1
0x10104889  call    _WPP_SF_qqI@28; WPP_SF_qqI(x,x,x,x,x,x,x)
0x1010488e  xor     eax, eax
0x10104890  inc     eax
0x10104891  test    edi, edi
0x10104893  jnz     short loc_1010490F
0x10104895  cmp     dword ptr [ebp+cbBody], 0FFFFFFFFh
0x10104899  jnb     short loc_1010490F
0x1010489b  cmp     [ebx+1Ch], edi
0x1010489e  jz      short loc_101048BB
0x101048a0  mov     esi, [ebx+1Ch]
0x101048a3  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x101048a9  cmp     esi, eax
0x101048ab  jz      short loc_101048B4
0x101048ad  mov     edi, 8001010Eh
0x101048b2  jmp     short CleanUp_380
0x101048b4  mov     esi, [esp+28h+var_14]
0x101048b8  xor     eax, eax
0x101048ba  inc     eax
0x101048bb  test    esi, esi
0x101048bd  jnz     short loc_101048C6
0x101048bf  mov     word ptr [esp+28h+varBody.___u0], ax
0x101048c4  jmp     short loc_101048EB
0x101048c6  push    edi
0x101048c7  push    dword ptr [ebp+cbBody]; cbSize
0x101048ca  lea     pBody, [esp+30h+pUploadStream]; ppStream
0x101048ce  mov     this, esi; pStream
0x101048d0  call    ?CreateInstance@URLMONUploadStream@@SGJPAUISequentialStream@@_KPAPAUIStream@@@Z; URLMONUploadStream::CreateInstance(ISequentialStream *,unsigned __int64,IStream * *)
0x101048d5  mov     edi, eax
0x101048d7  test    edi, edi
0x101048d9  js      short CleanUp_380
0x101048db  push    0Dh
0x101048dd  pop     eax
0x101048de  mov     word ptr [esp+28h+varBody.___u0], ax
0x101048e3  mov     eax, [esp+28h+pUploadStream]
0x101048e7  mov     dword ptr [esp+28h+varBody.___u0+8], eax
0x101048eb  mov     this, [ebx+18h]
0x101048ee  lea     esi, [esp+28h+varBody]
0x101048f2  sub     esp, 10h
0x101048f5  mov     edi, esp
0x101048f7  mov     eax, [this]
0x101048f9  push    this
0x101048fa  movsd
0x101048fb  mov     ebx, [eax+2Ch]
0x101048fe  mov     this, ebx; this
0x10104900  movsd
0x10104901  movsd
0x10104902  movsd
0x10104903  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10104909  call    ebx
0x1010490b  mov     edi, eax
0x1010490d  jmp     short CleanUp_380
0x1010490f  mov     edi, 80070057h
0x10104914  mov     this, [esp+28h+pUploadStream]
0x10104918  test    this, this
0x1010491a  jz      short loc_10104934
0x1010491c  mov     eax, [this]
0x1010491e  push    this
0x1010491f  mov     esi, [eax+8]
0x10104922  mov     this, esi; this
0x10104924  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1010492a  call    esi
0x1010492c  mov     [esp+28h+pUploadStream], 0
0x10104934  mov     this, edi; __annotation("TMF:",
0x10104936  sar     this, 1Fh
0x10104939  mov     eax, this
0x1010493b  shl     eax, 4
0x1010493e  test    byte_10185760[eax], 2
0x10104945  jz      short loc_10104960
0x10104947  add     this, 2
0x1010494a  mov     pBody, 8Ch; id
0x1010494f  push    edi; _a1
0x10104950  shl     this, 9
0x10104953  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104958  or      this, 1; LevelKeyword
0x1010495b  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104960  mov     eax, edi
0x10104962  pop     edi
0x10104963  pop     esi
0x10104964  pop     ebx
0x10104965  mov     esp, ebp
0x10104967  pop     ebp
0x10104968  retn    8
```
