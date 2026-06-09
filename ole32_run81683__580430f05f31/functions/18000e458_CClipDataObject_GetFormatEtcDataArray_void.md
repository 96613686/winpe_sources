# CClipDataObject::GetFormatEtcDataArray(void)

- ea: `0x18000e458`
- end: `0x18000e979`
- name: `?GetFormatEtcDataArray@CClipDataObject@@AEAAJXZ`
- size: `1313`
- prototype: `HRESULT __fastcall(CClipDataObject *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d954`
- `0x18000dcf0`

## callees

- `0x18000b2d4`
- `0x18000d38c`
- `0x18000e458`
- `0x18000e9b4`
- `0x18000ebc8`
- `0x1800405d4`
- `0x180052390`
- `0x180053014`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000e68d`
- `KERNELBASE!Sleep` at `0x18000e68d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e561`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e72a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e561`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e72a`
- `USER32!IsClipboardFormatAvailable` at `0x18000e50a`
- `USER32!IsClipboardFormatAvailable` at `0x18000e51f`
- `USER32!IsClipboardFormatAvailable` at `0x18000e6e4`
- `USER32!IsClipboardFormatAvailable` at `0x18000e50a`
- `USER32!IsClipboardFormatAvailable` at `0x18000e51f`
- `USER32!IsClipboardFormatAvailable` at `0x18000e6e4`
- `USER32!OpenClipboard` at `0x18000e4db`
- `USER32!OpenClipboard` at `0x18000e696`
- `USER32!OpenClipboard` at `0x18000e4db`
- `USER32!OpenClipboard` at `0x18000e696`
- `USER32!CountClipboardFormats` at `0x18000e4fb`
- `USER32!CountClipboardFormats` at `0x18000e4fb`
- `USER32!EnumClipboardFormats` at `0x18000e608`
- `USER32!EnumClipboardFormats` at `0x18000e608`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e4e9`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000e4e9`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetFormatEtcDataArray(CClipDataObject *this)
{
  HWND PrivateClipboardWindow; // rax
  HWND v4; // rbx
  __int64 v5; // rcx
  int v6; // ebx
  int v7; // r15d
  unsigned __int64 v8; // rbx
  FORMATETCDATAARRAY *v9; // rax
  unsigned int v10; // ecx
  FORMATETCDATA *FormatEtcData; // rbx
  unsigned int v12; // esi
  unsigned int v13; // r15d
  UINT v14; // ecx
  unsigned int v15; // ebx
  CClipDataObject::GetFormatEtcDataArray::__l12::SUPPORTED_EDP_ACCESS_DENIED_FORMATS_MAP *v16; // rbx
  unsigned int v17; // esi
  unsigned __int64 v18; // rbx
  FORMATETCDATAARRAY *v19; // rax
  CClipDataObject::GetFormatEtcDataArray::__l12::SUPPORTED_EDP_ACCESS_DENIED_FORMATS_MAP *v20; // r8
  FORMATETCDATA *v21; // rdx
  unsigned __int16 cf; // r9
  __int128 v23; // xmm1
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  OleClipboardLock clipLock; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int16 v28; // [rsp+28h] [rbp-48h]
  int v29; // [rsp+2Ah] [rbp-46h]
  __int16 v30; // [rsp+2Eh] [rbp-42h]
  __int64 v31; // [rsp+30h] [rbp-40h]
  __int128 v32; // [rsp+38h] [rbp-38h]
  CClipDataObject::GetFormatEtcDataArray::__l12::SUPPORTED_EDP_ACCESS_DENIED_FORMATS_MAP rgSupportedEdpAccessDeniedFormats[4]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v34; // [rsp+68h] [rbp-8h] BYREF

  if ( this->m_pFormatEtcDataArray )
    return 0;
  if ( !this->m_fIsEdpAccessDenied )
  {
    clipLock.m_locked = 0;
    PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
    v4 = PrivateClipboardWindow;
    if ( !PrivateClipboardWindow )
      goto LABEL_56;
    if ( !OpenClipboard(PrivateClipboardWindow) )
    {
      Sleep(0);
      if ( !OpenClipboard(v4) )
      {
        v15 = -2147221040;
        goto LABEL_33;
      }
    }
    if ( (unsigned int)EdpGetIsManaged(v5) )
      EdpInlSetCurrentThreadPolicyEvaluation(1);
    clipLock.m_locked = 1;
    v6 = CountClipboardFormats();
    if ( IsClipboardFormatAvailable(g_cfDataObject) )
      --v6;
    v7 = v6 - 1;
    if ( !IsClipboardFormatAvailable(g_cfOlePrivateData) )
      v7 = v6;
    if ( v7 < 0 )
    {
LABEL_56:
      v15 = -2147467259;
      goto LABEL_33;
    }
    v8 = (unsigned int)(48 * v7 + 264);
    if ( v8 >= GetSafeAllocSize() )
    {
      this->m_pFormatEtcDataArray = 0;
    }
    else
    {
      v9 = (FORMATETCDATAARRAY *)HeapAlloc(g_hHeap, 0, (unsigned int)v8);
      this->m_pFormatEtcDataArray = v9;
      if ( v9 )
      {
        memset_0(v9, 0, (unsigned int)v8);
        v10 = g_cfEmbedSource;
        this->m_pFormatEtcDataArray->_dwSig = 0;
        this->m_pFormatEtcDataArray->_dwSize = 48 * v7 + 264;
        this->m_pFormatEtcDataArray->_cRefs = 1;
        this->m_pFormatEtcDataArray->_fIs64BitArray = 1;
        FormatEtcData = this->m_pFormatEtcDataArray->_FormatEtcData;
        if ( CanRetrieveOle2FromOle1(v10) )
        {
          v24 = g_cfObjectDescriptor;
          FormatEtcData->_FormatEtc.cfFormat = g_cfEmbedSource;
          FormatEtcData->_FormatEtc.ptd = 0;
          FormatEtcData->_FormatEtc.lindex = -1;
          FormatEtcData->_FormatEtc.dwAspect = 1;
          FormatEtcData->_FormatEtc.tymed = 13;
          ++FormatEtcData;
          if ( CanRetrieveOle2FromOle1(v24) )
          {
            v12 = 2;
            FormatEtcData->_FormatEtc.cfFormat = g_cfObjectDescriptor;
            FormatEtcData->_FormatEtc.ptd = 0;
            FormatEtcData->_FormatEtc.lindex = -1;
            FormatEtcData->_FormatEtc.dwAspect = 1;
            FormatEtcData->_FormatEtc.tymed = 5;
            ++FormatEtcData;
          }
          else
          {
            v12 = 1;
          }
        }
        else
        {
          v12 = 0;
        }
        if ( CanRetrieveOle2FromOle1(g_cfEmbeddedObject) )
        {
          ++v12;
          v25 = g_cfObjectDescriptor;
          FormatEtcData->_FormatEtc.cfFormat = g_cfEmbeddedObject;
          FormatEtcData->_FormatEtc.ptd = 0;
          FormatEtcData->_FormatEtc.lindex = -1;
          FormatEtcData->_FormatEtc.dwAspect = 1;
          FormatEtcData->_FormatEtc.tymed = 13;
          ++FormatEtcData;
          if ( CanRetrieveOle2FromOle1(v25) )
          {
            ++v12;
            FormatEtcData->_FormatEtc.cfFormat = g_cfObjectDescriptor;
            FormatEtcData->_FormatEtc.ptd = 0;
            FormatEtcData->_FormatEtc.lindex = -1;
            FormatEtcData->_FormatEtc.dwAspect = 1;
            FormatEtcData->_FormatEtc.tymed = 5;
            ++FormatEtcData;
          }
        }
        if ( CanRetrieveOle2FromOle1(g_cfLinkSource) )
        {
          ++v12;
          v26 = g_cfLinkSrcDescriptor;
          FormatEtcData->_FormatEtc.cfFormat = g_cfLinkSource;
          FormatEtcData->_FormatEtc.ptd = 0;
          FormatEtcData->_FormatEtc.lindex = -1;
          FormatEtcData->_FormatEtc.dwAspect = 1;
          FormatEtcData->_FormatEtc.tymed = 5;
          ++FormatEtcData;
          if ( CanRetrieveOle2FromOle1(v26) )
          {
            ++v12;
            FormatEtcData->_FormatEtc.cfFormat = g_cfLinkSrcDescriptor;
            FormatEtcData->_FormatEtc.ptd = 0;
            FormatEtcData->_FormatEtc.lindex = -1;
            FormatEtcData->_FormatEtc.dwAspect = 1;
            FormatEtcData->_FormatEtc.tymed = 5;
            ++FormatEtcData;
          }
        }
        v13 = v12 + v7;
        v14 = 0;
        this->m_pFormatEtcDataArray->_cFormats = v13;
        while ( 1 )
        {
          if ( v12 >= v13 )
          {
            OleClipboardLock::Release(&clipLock);
            return 0;
          }
          FormatEtcData->_FormatEtc.ptd = 0;
          FormatEtcData->_FormatEtc.lindex = -1;
          FormatEtcData->_FormatEtc.dwAspect = 1;
          v14 = EnumClipboardFormats(v14);
          FormatEtcData->_FormatEtc.cfFormat = v14;
          if ( v14 == 2 )
            break;
          switch ( v14 )
          {
            case 3u:
              FormatEtcData->_FormatEtc.tymed = 32;
              break;
            case 9u:
              goto LABEL_30;
            case 0xEu:
              FormatEtcData->_FormatEtc.tymed = 64;
              break;
            default:
              if ( v14 == g_cfEmbedSource || v14 == g_cfEmbeddedObject )
                FormatEtcData->_FormatEtc.tymed = 13;
              else
                FormatEtcData->_FormatEtc.tymed = 5;
              break;
          }
LABEL_28:
          ++FormatEtcData;
          ++v12;
        }
LABEL_30:
        FormatEtcData->_FormatEtc.tymed = 16;
        goto LABEL_28;
      }
    }
    v15 = -2147024882;
LABEL_33:
    OleClipboardLock::Release(&clipLock);
    return v15;
  }
  rgSupportedEdpAccessDeniedFormats[0].cf = 1;
  rgSupportedEdpAccessDeniedFormats[1].cf = 7;
  v16 = rgSupportedEdpAccessDeniedFormats;
  rgSupportedEdpAccessDeniedFormats[0].isOnClipboard = 0;
  rgSupportedEdpAccessDeniedFormats[2].cf = 13;
  v17 = 0;
  rgSupportedEdpAccessDeniedFormats[1].isOnClipboard = 0;
  rgSupportedEdpAccessDeniedFormats[3].cf = 2;
  rgSupportedEdpAccessDeniedFormats[2].isOnClipboard = 0;
  rgSupportedEdpAccessDeniedFormats[3].isOnClipboard = 0;
  do
  {
    if ( IsClipboardFormatAvailable(v16->cf) )
    {
      v16->isOnClipboard = 1;
      ++v17;
    }
    ++v16;
  }
  while ( v16 != (CClipDataObject::GetFormatEtcDataArray::__l12::SUPPORTED_EDP_ACCESS_DENIED_FORMATS_MAP *)&v34 );
  v18 = 48 * v17 + 72;
  if ( v18 >= GetSafeAllocSize() )
  {
    this->m_pFormatEtcDataArray = 0;
  }
  else
  {
    v19 = (FORMATETCDATAARRAY *)HeapAlloc(g_hHeap, 0, (unsigned int)v18);
    this->m_pFormatEtcDataArray = v19;
    if ( v19 )
    {
      memset_0(v19, 0, (unsigned int)v18);
      v20 = rgSupportedEdpAccessDeniedFormats;
      this->m_pFormatEtcDataArray->_dwSig = 0;
      this->m_pFormatEtcDataArray->_dwSize = 48 * v17 + 72;
      this->m_pFormatEtcDataArray->_cRefs = 1;
      this->m_pFormatEtcDataArray->_cFormats = v17;
      this->m_pFormatEtcDataArray->_fIs64BitArray = 1;
      v21 = this->m_pFormatEtcDataArray->_FormatEtcData;
      while ( !v20->isOnClipboard )
      {
LABEL_51:
        if ( ++v20 == (CClipDataObject::GetFormatEtcDataArray::__l12::SUPPORTED_EDP_ACCESS_DENIED_FORMATS_MAP *)&v34 )
          return 0;
      }
      cf = v20->cf;
      if ( v20->cf != 1 )
      {
        if ( v20->cf == 2 )
        {
          *((_QWORD *)&v32 + 1) = 16;
          goto LABEL_49;
        }
        if ( v20->cf != 7 && v20->cf != 13 )
          goto LABEL_50;
      }
      *((_QWORD *)&v32 + 1) = 13;
LABEL_49:
      v28 = cf;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      *(_QWORD *)&v32 = 0xFFFFFFFF00000001uLL;
      v23 = v32;
      *(_OWORD *)&v21->_FormatEtc.cfFormat = cf;
      *(_OWORD *)&v21->_FormatEtc.dwAspect = v23;
      *(_OWORD *)&v21->fSaveOnFlush = 0;
LABEL_50:
      ++v21;
      goto LABEL_51;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000e458  mov     [rsp-28h+arg_8], rbx
0x18000e45d  mov     [rsp-28h+arg_10], rsi
0x18000e462  push    rbp
0x18000e463  push    rdi
0x18000e464  push    r12
0x18000e466  push    r14
0x18000e468  push    r15
0x18000e46a  mov     rbp, rsp
0x18000e46d  sub     rsp, 70h
0x18000e471  mov     rax, cs:__security_cookie
0x18000e478  xor     rax, rsp
0x18000e47b  mov     [rbp+var_8], rax
0x18000e47f  xor     r12d, r12d
0x18000e482  mov     r14, this
0x18000e485  cmp     [this+30h], r12
0x18000e489  jz      short loc_18000E4B2
0x18000e48b  xor     eax, eax
0x18000e48d  mov     this, [rbp+var_8]
0x18000e491  xor     this, rsp; StackCookie
0x18000e494  call    __security_check_cookie
0x18000e499  lea     r11, [rsp+70h+var_s0]
0x18000e49e  mov     rbx, [r11+38h]
0x18000e4a2  mov     rsi, [r11+40h]
0x18000e4a6  mov     rsp, r11
0x18000e4a9  pop     r15
0x18000e4ab  pop     r14
0x18000e4ad  pop     r12
0x18000e4af  pop     rdi
0x18000e4b0  pop     rbp
0x18000e4b1  retn
0x18000e4b2  mov     edi, 1
0x18000e4b7  cmp     [this+45h], r12b
0x18000e4bb  jnz     loc_18000E6AB
0x18000e4c1  mov     ecx, edi; fFlags
0x18000e4c3  mov     [rbp+clipLock.m_locked], r12b
0x18000e4c7  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000e4cc  mov     rbx, rax
0x18000e4cf  test    rax, rax
0x18000e4d2  jz      loc_18000E818
0x18000e4d8  mov     this, rax; hWndNewOwner
0x18000e4db  call    cs:__imp_OpenClipboard
0x18000e4e1  test    eax, eax
0x18000e4e3  jz      loc_18000E68B
0x18000e4e9  call    cs:__imp_EdpGetIsManaged
0x18000e4ef  test    eax, eax
0x18000e4f1  jnz     loc_18000E805
0x18000e4f7  mov     [rbp+clipLock.m_locked], dil
0x18000e4fb  call    cs:__imp_CountClipboardFormats
0x18000e501  movzx   ecx, cs:?g_cfDataObject@@3GA; format
0x18000e508  mov     ebx, eax
0x18000e50a  call    cs:__imp_IsClipboardFormatAvailable
0x18000e510  test    eax, eax
0x18000e512  jnz     loc_18000E811
0x18000e518  movzx   ecx, cs:?g_cfOlePrivateData@@3GA; format
0x18000e51f  call    cs:__imp_IsClipboardFormatAvailable
0x18000e525  test    eax, eax
0x18000e527  lea     r15d, [rbx-1]
0x18000e52b  cmovz   r15d, ebx
0x18000e52f  test    r15d, r15d
0x18000e532  js      loc_18000E818
0x18000e538  lea     esi, [r15+r15*2]
0x18000e53c  shl     esi, 4
0x18000e53f  add     esi, 108h
0x18000e545  mov     ebx, esi
0x18000e547  call    GetSafeAllocSize
0x18000e54c  cmp     rbx, rax
0x18000e54f  jnb     loc_18000E672
0x18000e555  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18000e55c  mov     r8d, ebx; dwBytes
0x18000e55f  xor     edx, edx; dwFlags
0x18000e561  call    cs:__imp_HeapAlloc
0x18000e567  mov     [r14+30h], rax
0x18000e56b  test    rax, rax
0x18000e56e  jz      loc_18000E676
0x18000e574  mov     r8d, ebx; Size
0x18000e577  xor     edx, edx; Val
0x18000e579  mov     this, rax; void *
0x18000e57c  call    memset_0
0x18000e581  mov     rax, [r14+30h]
0x18000e585  movzx   ecx, cs:?g_cfEmbedSource@@3GA; cf
0x18000e58c  mov     [rax], r12d
0x18000e58f  mov     rax, [r14+30h]
0x18000e593  mov     [rax+4], esi
0x18000e596  mov     rax, [r14+30h]
0x18000e59a  mov     [rax+8], edi
0x18000e59d  mov     rax, [r14+30h]
0x18000e5a1  mov     [rax+14h], edi
0x18000e5a4  mov     rbx, [r14+30h]
0x18000e5a8  add     rbx, 18h
0x18000e5ac  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000e5b1  or      r12d, 0FFFFFFFFh
0x18000e5b5  test    eax, eax
0x18000e5b7  jnz     loc_18000E822
0x18000e5bd  xor     esi, esi
0x18000e5bf  movzx   ecx, cs:?g_cfEmbeddedObject@@3GA; cf
0x18000e5c6  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000e5cb  test    eax, eax
0x18000e5cd  jnz     loc_18000E88B
0x18000e5d3  movzx   ecx, cs:?g_cfLinkSource@@3GA; cf
0x18000e5da  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000e5df  test    eax, eax
0x18000e5e1  jnz     loc_18000E8F0
0x18000e5e7  mov     rax, [r14+30h]
0x18000e5eb  add     r15d, esi
0x18000e5ee  xor     ecx, ecx; format
0x18000e5f0  mov     [rax+0Ch], r15d
0x18000e5f4  cmp     esi, r15d
0x18000e5f7  jnb     short loc_18000E65B
0x18000e5f9  mov     qword ptr [rbx+8], 0
0x18000e601  mov     [rbx+14h], r12d
0x18000e605  mov     [rbx+10h], edi
0x18000e608  call    cs:__imp_EnumClipboardFormats
0x18000e60e  mov     ecx, eax
0x18000e610  mov     [rbx], cx
0x18000e613  sub     eax, 2
0x18000e616  jz      short loc_18000E669
0x18000e618  sub     eax, edi
0x18000e61a  jz      loc_18000E96D
0x18000e620  sub     eax, 6
0x18000e623  jz      short loc_18000E669
0x18000e625  cmp     eax, 5
0x18000e628  jz      loc_18000E961
0x18000e62e  movzx   eax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x18000e635  cmp     ecx, eax
0x18000e637  jz      loc_18000E955
0x18000e63d  movzx   eax, cs:?g_cfEmbeddedObject@@3GA; ushort g_cfEmbeddedObject
0x18000e644  cmp     ecx, eax
0x18000e646  jz      loc_18000E955
0x18000e64c  mov     dword ptr [rbx+18h], 5
0x18000e653  add     rbx, 30h ; '0'
0x18000e657  add     esi, edi
0x18000e659  jmp     short loc_18000E5F4
0x18000e65b  lea     this, [rbp+clipLock]; this
0x18000e65f  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000e664  jmp     loc_18000E48B
0x18000e669  mov     dword ptr [rbx+18h], 10h
0x18000e670  jmp     short loc_18000E653
0x18000e672  mov     [r14+30h], r12
0x18000e676  mov     ebx, 8007000Eh
0x18000e67b  lea     this, [rbp+clipLock]; this
0x18000e67f  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000e684  mov     eax, ebx
0x18000e686  jmp     loc_18000E48D
0x18000e68b  xor     ecx, ecx; dwMilliseconds
0x18000e68d  call    cs:__imp_Sleep
0x18000e693  mov     this, rbx; hWndNewOwner
0x18000e696  call    cs:__imp_OpenClipboard
0x18000e69c  test    eax, eax
0x18000e69e  jnz     loc_18000E4E9
0x18000e6a4  mov     ebx, 800401D0h
0x18000e6a9  jmp     short loc_18000E67B
0x18000e6ab  mov     eax, 7
0x18000e6b0  mov     [rbp+rgSupportedEdpAccessDeniedFormats.cf], di
0x18000e6b4  mov     [rbp+rgSupportedEdpAccessDeniedFormats.cf+4], ax
0x18000e6b8  lea     rbx, [rbp+rgSupportedEdpAccessDeniedFormats]
0x18000e6bc  mov     eax, 0Dh
0x18000e6c1  mov     [rbp+rgSupportedEdpAccessDeniedFormats.isOnClipboard], r12b
0x18000e6c5  mov     [rbp+rgSupportedEdpAccessDeniedFormats.cf+8], ax
0x18000e6c9  mov     esi, r12d
0x18000e6cc  mov     eax, 2
0x18000e6d1  mov     [rbp+rgSupportedEdpAccessDeniedFormats.isOnClipboard+4], r12b
0x18000e6d5  mov     [rbp+rgSupportedEdpAccessDeniedFormats.cf+0Ch], ax
0x18000e6d9  mov     [rbp+rgSupportedEdpAccessDeniedFormats.isOnClipboard+8], r12b
0x18000e6dd  mov     [rbp+rgSupportedEdpAccessDeniedFormats.isOnClipboard+0Ch], r12b
0x18000e6e1  movzx   ecx, word ptr [rbx]; format
0x18000e6e4  call    cs:__imp_IsClipboardFormatAvailable
0x18000e6ea  test    eax, eax
0x18000e6ec  jz      short loc_18000E6F4
0x18000e6ee  mov     [rbx+2], dil
0x18000e6f2  add     esi, edi
0x18000e6f4  add     rbx, 4
0x18000e6f8  lea     rax, [rbp+var_8]
0x18000e6fc  cmp     rbx, rax
0x18000e6ff  jnz     short loc_18000E6E1
0x18000e701  lea     r15d, [rsi+rsi*2]
0x18000e705  shl     r15d, 4
0x18000e709  add     r15d, 48h ; 'H'
0x18000e70d  mov     ebx, r15d
0x18000e710  call    GetSafeAllocSize
0x18000e715  cmp     rbx, rax
0x18000e718  jnb     loc_18000E7F7
0x18000e71e  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18000e725  mov     r8d, ebx; dwBytes
0x18000e728  xor     edx, edx; dwFlags
0x18000e72a  call    cs:__imp_HeapAlloc
0x18000e730  mov     [r14+30h], rax
0x18000e734  test    rax, rax
0x18000e737  jz      loc_18000E7FB
0x18000e73d  mov     r8d, ebx; Size
0x18000e740  xor     edx, edx; Val
0x18000e742  mov     this, rax; void *
0x18000e745  call    memset_0
0x18000e74a  mov     rax, [r14+30h]
0x18000e74e  lea     r8, [rbp+rgSupportedEdpAccessDeniedFormats]
0x18000e752  mov     [rax], r12d
0x18000e755  or      r12d, 0FFFFFFFFh
0x18000e759  mov     rax, [r14+30h]
0x18000e75d  mov     [rax+4], r15d
0x18000e761  mov     rax, [r14+30h]
0x18000e765  mov     [rax+8], edi
0x18000e768  mov     rax, [r14+30h]
0x18000e76c  mov     [rax+0Ch], esi
0x18000e76f  mov     rax, [r14+30h]
0x18000e773  mov     [rax+14h], edi
0x18000e776  mov     rdx, [r14+30h]
0x18000e77a  add     rdx, 18h
0x18000e77e  xor     r10d, r10d
0x18000e781  cmp     [r8+2], r10b
0x18000e785  jz      short loc_18000E7DB
0x18000e787  movzx   r9d, word ptr [r8]
0x18000e78b  mov     ecx, r9d
0x18000e78e  sub     ecx, edi
0x18000e790  jz      short loc_18000E7A0
0x18000e792  sub     ecx, edi
0x18000e794  jz      short loc_18000E7ED
0x18000e796  sub     ecx, 5
0x18000e799  jz      short loc_18000E7A0
0x18000e79b  cmp     ecx, 6
0x18000e79e  jnz     short loc_18000E7D7
0x18000e7a0  mov     qword ptr [rbp+var_38+8], 0Dh
0x18000e7a8  xor     eax, eax
0x18000e7aa  mov     word ptr [rbp+var_48], r9w
0x18000e7af  mov     dword ptr [rbp+var_48+2], eax
0x18000e7b2  xorps   xmm2, xmm2
0x18000e7b5  mov     word ptr [rbp+var_48+6], ax
0x18000e7b9  mov     qword ptr [rbp+var_48+8], r10
0x18000e7bd  movups  xmm0, [rbp+var_48]
0x18000e7c1  mov     dword ptr [rbp+var_38], edi
0x18000e7c4  mov     dword ptr [rbp+var_38+4], r12d
0x18000e7c8  movups  xmm1, [rbp+var_38]
0x18000e7cc  movups  xmmword ptr [rdx], xmm0
0x18000e7cf  movups  xmmword ptr [rdx+10h], xmm1
0x18000e7d3  movups  xmmword ptr [rdx+20h], xmm2
0x18000e7d7  add     rdx, 30h ; '0'
0x18000e7db  add     r8, 4
0x18000e7df  lea     rax, [rbp+var_8]
0x18000e7e3  cmp     r8, rax
0x18000e7e6  jnz     short loc_18000E781
0x18000e7e8  jmp     loc_18000E48B
0x18000e7ed  mov     qword ptr [rbp+var_38+8], 10h
0x18000e7f5  jmp     short loc_18000E7A8
0x18000e7f7  mov     [r14+30h], r12
0x18000e7fb  mov     eax, 8007000Eh
0x18000e800  jmp     loc_18000E48D
0x18000e805  mov     ecx, edi; EvaluationDisabled
0x18000e807  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000e80c  jmp     loc_18000E4F7
0x18000e811  dec     ebx
0x18000e813  jmp     loc_18000E518
0x18000e818  mov     ebx, 80004005h
0x18000e81d  jmp     loc_18000E67B
0x18000e822  movzx   eax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x18000e829  movzx   ecx, cs:?g_cfObjectDescriptor@@3GA; cf
0x18000e830  mov     [rbx], ax
0x18000e833  mov     qword ptr [rbx+8], 0
0x18000e83b  mov     [rbx+14h], r12d
0x18000e83f  mov     [rbx+10h], edi
0x18000e842  mov     dword ptr [rbx+18h], 0Dh
0x18000e849  add     rbx, 30h ; '0'
0x18000e84d  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000e852  test    eax, eax
0x18000e854  jz      short loc_18000E884
0x18000e856  movzx   eax, cs:?g_cfObjectDescriptor@@3GA; ushort g_cfObjectDescriptor
0x18000e85d  mov     esi, 2
0x18000e862  mov     [rbx], ax
0x18000e865  mov     qword ptr [rbx+8], 0
0x18000e86d  mov     [rbx+14h], r12d
0x18000e871  mov     [rbx+10h], edi
0x18000e874  mov     dword ptr [rbx+18h], 5
0x18000e87b  add     rbx, 30h ; '0'
0x18000e87f  jmp     loc_18000E5BF
0x18000e884  mov     esi, edi
0x18000e886  jmp     loc_18000E5BF
0x18000e88b  movzx   eax, cs:?g_cfEmbeddedObject@@3GA; ushort g_cfEmbeddedObject
0x18000e892  add     esi, edi
0x18000e894  movzx   ecx, cs:?g_cfObjectDescriptor@@3GA; cf
0x18000e89b  mov     [rbx], ax
0x18000e89e  mov     qword ptr [rbx+8], 0
0x18000e8a6  mov     [rbx+14h], r12d
0x18000e8aa  mov     [rbx+10h], edi
0x18000e8ad  mov     dword ptr [rbx+18h], 0Dh
0x18000e8b4  add     rbx, 30h ; '0'
0x18000e8b8  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000e8bd  test    eax, eax
0x18000e8bf  jz      loc_18000E5D3
0x18000e8c5  movzx   eax, cs:?g_cfObjectDescriptor@@3GA; ushort g_cfObjectDescriptor
0x18000e8cc  add     esi, edi
0x18000e8ce  mov     [rbx], ax
0x18000e8d1  mov     qword ptr [rbx+8], 0
0x18000e8d9  mov     [rbx+14h], r12d
0x18000e8dd  mov     [rbx+10h], edi
0x18000e8e0  mov     dword ptr [rbx+18h], 5
0x18000e8e7  add     rbx, 30h ; '0'
0x18000e8eb  jmp     loc_18000E5D3
0x18000e8f0  movzx   eax, cs:?g_cfLinkSource@@3GA; ushort g_cfLinkSource
0x18000e8f7  add     esi, edi
0x18000e8f9  movzx   ecx, cs:?g_cfLinkSrcDescriptor@@3GA; cf
0x18000e900  mov     [rbx], ax
0x18000e903  mov     qword ptr [rbx+8], 0
0x18000e90b  mov     [rbx+14h], r12d
  ... truncated ...
```
