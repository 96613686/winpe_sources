# XMLHttp2::_Send(ISequentialStream *,unsigned __int64)

- ea: `0x1010472e`
- end: `0x1010484b`
- name: `?_Send@XMLHttp2@@AAGJPAUISequentialStream@@_K@Z`
- size: `285`
- prototype: `HRESULT __userpurge@<eax>(XMLHttp2 *this@<ecx>, ISequentialStream *pBody@<edx>, unsigned __int64 cbBody)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x101034f0`

## callees

- `0x10067bc0`
- `0x1010472e`
- `0x1012ff93`
- `0x10180006`
- `0x10180880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10104783`

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
  if ( (byte_101857A0[0] & 2) != 0 )
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
  if ( (byte_101857A0[16 * (v6 >> 31)] & 2) != 0 )
    WPP_SF_q((((unsigned __int16)(v6 >> 31) + 2) << 9) | 1, 0x8Cu, WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1010472e  mov     edi, edi
0x10104730  push    ebp
0x10104731  mov     ebp, esp
0x10104733  and     esp, 0FFFFFFF8h
0x10104736  sub     esp, 1Ch
0x10104739  push    ebx
0x1010473a  push    esi
0x1010473b  push    edi; TraceGuid
0x1010473c  xor     eax, eax
0x1010473e  mov     [esp+28h+pUploadStream], 0
0x10104746  lea     edi, [esp+28h+varBody]
0x1010474a  mov     esi, pBody
0x1010474c  stosd
0x1010474d  mov     ebx, this
0x1010474f  mov     [esp+28h+var_14], esi
0x10104753  stosd
0x10104754  stosd
0x10104755  stosd
0x10104756  test    byte_101857A0, 2; __annotation("TMF:",
0x1010475d  mov     edi, dword ptr [ebp+cbBody+4]
0x10104760  jz      short loc_1010476E
0x10104762  push    edi; id
0x10104763  push    dword ptr [ebp+cbBody]; LevelKeyword
0x10104766  push    esi; _a3
0x10104767  push    ebx; _a2
0x10104768  push    this; _a1
0x10104769  call    _WPP_SF_qqI@28; WPP_SF_qqI(x,x,x,x,x,x,x)
0x1010476e  xor     eax, eax
0x10104770  inc     eax
0x10104771  test    edi, edi
0x10104773  jnz     short loc_101047EF
0x10104775  cmp     dword ptr [ebp+cbBody], 0FFFFFFFFh
0x10104779  jnb     short loc_101047EF
0x1010477b  cmp     [ebx+1Ch], edi
0x1010477e  jz      short loc_1010479B
0x10104780  mov     esi, [ebx+1Ch]
0x10104783  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10104789  cmp     esi, eax
0x1010478b  jz      short loc_10104794
0x1010478d  mov     edi, 8001010Eh
0x10104792  jmp     short CleanUp_380
0x10104794  mov     esi, [esp+28h+var_14]
0x10104798  xor     eax, eax
0x1010479a  inc     eax
0x1010479b  test    esi, esi
0x1010479d  jnz     short loc_101047A6
0x1010479f  mov     word ptr [esp+28h+varBody.___u0], ax
0x101047a4  jmp     short loc_101047CB
0x101047a6  push    edi
0x101047a7  push    dword ptr [ebp+cbBody]; cbSize
0x101047aa  lea     pBody, [esp+30h+pUploadStream]; ppStream
0x101047ae  mov     this, esi; pStream
0x101047b0  call    ?CreateInstance@URLMONUploadStream@@SGJPAUISequentialStream@@_KPAPAUIStream@@@Z; URLMONUploadStream::CreateInstance(ISequentialStream *,unsigned __int64,IStream * *)
0x101047b5  mov     edi, eax
0x101047b7  test    edi, edi
0x101047b9  js      short CleanUp_380
0x101047bb  push    0Dh
0x101047bd  pop     eax
0x101047be  mov     word ptr [esp+28h+varBody.___u0], ax
0x101047c3  mov     eax, [esp+28h+pUploadStream]
0x101047c7  mov     dword ptr [esp+28h+varBody.___u0+8], eax
0x101047cb  mov     this, [ebx+18h]
0x101047ce  lea     esi, [esp+28h+varBody]
0x101047d2  sub     esp, 10h
0x101047d5  mov     edi, esp
0x101047d7  mov     eax, [this]
0x101047d9  push    this
0x101047da  movsd
0x101047db  mov     ebx, [eax+2Ch]
0x101047de  mov     this, ebx; this
0x101047e0  movsd
0x101047e1  movsd
0x101047e2  movsd
0x101047e3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101047e9  call    ebx
0x101047eb  mov     edi, eax
0x101047ed  jmp     short CleanUp_380
0x101047ef  mov     edi, 80070057h
0x101047f4  mov     this, [esp+28h+pUploadStream]
0x101047f8  test    this, this
0x101047fa  jz      short loc_10104814
0x101047fc  mov     eax, [this]
0x101047fe  push    this
0x101047ff  mov     esi, [eax+8]
0x10104802  mov     this, esi; this
0x10104804  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1010480a  call    esi
0x1010480c  mov     [esp+28h+pUploadStream], 0
0x10104814  mov     this, edi; __annotation("TMF:",
0x10104816  sar     this, 1Fh
0x10104819  mov     eax, this
0x1010481b  shl     eax, 4
0x1010481e  test    byte_101857A0[eax], 2
0x10104825  jz      short loc_10104840
0x10104827  add     this, 2
0x1010482a  mov     pBody, 8Ch; id
0x1010482f  push    edi; _a1
0x10104830  shl     this, 9
0x10104833  push    offset _WPP_7a110e3763e83a129bbaaf2a4db4a2b3_Traceguids; TraceGuid
0x10104838  or      this, 1; LevelKeyword
0x1010483b  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10104840  mov     eax, edi
0x10104842  pop     edi
0x10104843  pop     esi
0x10104844  pop     ebx
0x10104845  mov     esp, ebp
0x10104847  pop     ebp
0x10104848  retn    8
```
