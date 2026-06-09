# KsGetMediaType(x,x,x,x)

- ea: `0x1001ffa0`
- end: `0x100202dc`
- name: `_KsGetMediaType@16`
- size: `828`
- prototype: `int __stdcall(int, CMediaType *, HANDLE hDevice, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x100125f0`
- `0x10016700`
- `0x10017be0`
- `0x1001bb90`
- `0x100208f4`

## callees

- `0x100063f1`
- `0x1001f3b0`
- `0x1001fbb0`
- `0x1001ffa0`
- `0x1002d510`
- `0x10030181`
- `0x1003a6f2`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x100202cb`
- `ole32!CoTaskMemFree` at `0x100202cb`

## pseudocode

```c
int __stdcall KsGetMediaType(int a1, CMediaType *a2, HANDLE hDevice, int a4)
{
  unsigned int v4; // esi
  int result; // eax
  _DWORD *v6; // edx
  unsigned int v7; // ecx
  char *v8; // ebx
  bool v9; // zf
  int v10; // esi
  DWORD v11; // eax
  GUID *v12; // eax
  int v13; // ebx
  unsigned int *v14; // edi
  unsigned int *v15; // esi
  int v16; // eax
  _DWORD *v17; // edx
  unsigned int v18; // eax
  DWORD v19; // esi
  DWORD v20; // eax
  void *v21; // eax
  int v22; // eax
  DWORD v23; // ecx
  CMediaType *v24; // edx
  int v25; // eax
  int v26; // eax
  IUnknown *v27; // edx
  void *v28; // ecx
  DWORD BytesReturned; // [esp+Ch] [ebp-14h] BYREF
  DWORD nInBufferSize; // [esp+10h] [ebp-10h] BYREF
  void *Block; // [esp+14h] [ebp-Ch] BYREF
  void *Src; // [esp+18h] [ebp-8h]
  LPVOID pv; // [esp+1Ch] [ebp-4h]

  v4 = a1;
  Block = 0;
  if ( a1 < 0 )
    return -2147024809;
  if ( KsGetMultiplePinFactoryItems(hDevice, a4, 13, &Block) >= 0
    || (result = KsGetMultiplePinFactoryItems(hDevice, a4, 3, &Block), result >= 0) )
  {
    v6 = Block;
    pv = Block;
    if ( !Block )
      return -2147418113;
    v7 = *((_DWORD *)Block + 1);
    if ( a1 >= v7 )
    {
LABEL_49:
      v13 = 262403;
      goto LABEL_50;
    }
    BytesReturned = 0;
    v8 = (char *)Block + 8;
    if ( a1 )
    {
      do
      {
        if ( (v8[4] & 2) != 0 )
        {
          v6[1] = --v7;
          if ( v4 >= v7 )
            goto LABEL_49;
          v8 += (*(_DWORD *)v8 + 7) & 0xFFFFFFF8;
        }
        v8 += (*(_DWORD *)v8 + 7) & 0xFFFFFFF8;
        v6[1] = --v7;
        --v4;
      }
      while ( v4 );
    }
    v9 = (v8[4] & 2) == 0;
    v10 = *(_DWORD *)v8;
    v11 = *(_DWORD *)v8 + 40;
    nInBufferSize = v11;
    if ( v9 )
    {
      Src = 0;
    }
    else
    {
      Src = &v8[(v10 + 7) & 0xFFFFFFF8];
      v11 = *(_DWORD *)Src + ((v11 + 7) & 0xFFFFFFF8);
      nInBufferSize = v11;
    }
    v12 = (GUID *)operator new[](v11);
    Block = v12;
    if ( !v12 )
      goto LABEL_17;
    *v12 = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v14 = (unsigned int *)Block;
    *((_DWORD *)Block + 6) = a4;
    v15 = v14 + 8;
    v14[4] = 4;
    v14[5] = 1;
    v14[7] = 0;
    v16 = *(_DWORD *)v8 + 8;
    v14[9] = 1;
    v14[8] = v16;
    memcpy(v14 + 10, v8, *(_DWORD *)v8);
    v17 = Src;
    if ( Src )
    {
      v18 = ((*v15 + 7) & 0xFFFFFFF8) + *(_DWORD *)Src;
      ++v14[9];
      *v15 = v18;
      memcpy((char *)v15 + v18 - *v17, v17, *v17);
    }
    v19 = nInBufferSize;
    v13 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v14, nInBufferSize, 0, 0, &BytesReturned);
    if ( v13 != -2147024774 )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(0x17u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v14, v19, &nInBufferSize, 4u, &BytesReturned);
    if ( v13 >= 0 )
    {
      v20 = nInBufferSize;
      BytesReturned = nInBufferSize;
    }
    else
    {
LABEL_26:
      if ( v13 != -2147024662 )
        goto LABEL_48;
      v20 = BytesReturned;
    }
    if ( v20 < 0x40 )
    {
      v13 = -2147418113;
    }
    else
    {
      v21 = operator new[](v20);
      nInBufferSize = (DWORD)v21;
      if ( !v21 )
      {
        operator delete[](v14);
LABEL_17:
        v13 = -2147024882;
LABEL_50:
        CoTaskMemFree(pv);
        return v13;
      }
      v22 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v14, v19, v21, BytesReturned, &BytesReturned);
      v23 = nInBufferSize;
      v13 = v22;
      if ( v22 >= 0 )
      {
        if ( *(_DWORD *)nInBufferSize == BytesReturned && *(_DWORD *)nInBufferSize >= 0x40u )
        {
          v24 = a2;
          a2->majortype.Data1 = *(_DWORD *)(nInBufferSize + 16);
          *(_DWORD *)&a2->majortype.Data2 = *(_DWORD *)(v23 + 20);
          *(_QWORD *)a2->majortype.Data4 = *(_QWORD *)(v23 + 24);
          a2->subtype = *(_GUID *)(v23 + 32);
          a2->bTemporalCompression = *(_DWORD *)(v23 + 4) & 1;
          v25 = *(_DWORD *)(v23 + 8);
          if ( v25 )
          {
            a2->lSampleSize = v25;
            v25 = 1;
          }
          a2->bFixedSizeSamples = v25;
          if ( *(_DWORD *)v23 > 0x40u )
          {
            v26 = CMediaType::SetFormat(a2, (unsigned __int8 *)(v23 + 64), *(_DWORD *)v23 - 64);
            v23 = nInBufferSize;
            v24 = a2;
            if ( !v26 )
              v13 = -2147024882;
          }
          v24->formattype.Data1 = *(_DWORD *)(v23 + 48);
          *(_DWORD *)&v24->formattype.Data2 = *(_DWORD *)(v23 + 52);
          *(_DWORD *)v24->formattype.Data4 = *(_DWORD *)(v23 + 56);
          *(_DWORD *)&v24->formattype.Data4[4] = *(_DWORD *)(v23 + 60);
          if ( (*(_BYTE *)(v23 + 4) & 2) != 0 )
          {
            v27 = (IUnknown *)operator new(0xCu);
            if ( v27 )
            {
              v28 = Src;
              v27->__vftable = (IUnknown_vtbl *)&CMediaTypeAttributes::`vftable';
              v27[1].__vftable = 0;
              v27[2].__vftable = (IUnknown_vtbl *)1;
              a2->pUnk = v27;
              v13 = ((int (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *, void *))v27->__vftable[1].AddRef)(
                      v27->__vftable[1].AddRef,
                      v27,
                      v28);
            }
            else
            {
              v13 = -2147024882;
            }
            v23 = nInBufferSize;
          }
          v14 = (unsigned int *)Block;
        }
        else
        {
          v13 = -2147418113;
        }
      }
      operator delete[]((void *)v23);
    }
LABEL_48:
    operator delete[](v14);
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x1001ffa0  mov     edi, edi
0x1001ffa2  push    ebp
0x1001ffa3  mov     ebp, esp
0x1001ffa5  and     esp, 0FFFFFFF8h
0x1001ffa8  sub     esp, 14h
0x1001ffab  push    ebx
0x1001ffac  push    esi
0x1001ffad  mov     esi, [ebp+arg_0]
0x1001ffb0  mov     [esp+1Ch+Block], 0
0x1001ffb8  push    edi
0x1001ffb9  test    esi, esi
0x1001ffbb  jns     short loc_1001FFC7
0x1001ffbd  mov     eax, 80070057h
0x1001ffc2  jmp     loc_100202D3
0x1001ffc7  mov     ebx, [ebp+arg_C]
0x1001ffca  lea     eax, [esp+20h+Block]
0x1001ffce  push    eax; int
0x1001ffcf  push    0Dh; int
0x1001ffd1  push    ebx; int
0x1001ffd2  push    [ebp+hDevice]; hDevice
0x1001ffd5  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001ffda  test    eax, eax
0x1001ffdc  jns     short loc_1001FFF6
0x1001ffde  lea     eax, [esp+20h+Block]
0x1001ffe2  push    eax; int
0x1001ffe3  push    3; int
0x1001ffe5  push    ebx; int
0x1001ffe6  push    [ebp+hDevice]; hDevice
0x1001ffe9  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001ffee  test    eax, eax
0x1001fff0  js      loc_100202D3
0x1001fff6  mov     edx, [esp+20h+Block]
0x1001fffa  mov     [esp+20h+pv], edx
0x1001fffe  test    edx, edx
0x10020000  jnz     short loc_1002000C
0x10020002  mov     eax, 8000FFFFh
0x10020007  jmp     loc_100202D3
0x1002000c  mov     ecx, [edx+4]
0x1002000f  cmp     esi, ecx
0x10020011  jnb     loc_100202C2
0x10020017  mov     [esp+20h+BytesReturned], 0
0x1002001f  lea     ebx, [edx+8]
0x10020022  push    0FFFFFFF8h
0x10020024  pop     edi
0x10020025  test    esi, esi
0x10020027  jz      short loc_10020056
0x10020029  test    byte ptr [ebx+4], 2
0x1002002d  jz      short loc_10020044
0x1002002f  dec     ecx
0x10020030  mov     [edx+4], ecx
0x10020033  cmp     esi, ecx
0x10020035  jnb     loc_100202C2
0x1002003b  mov     eax, [ebx]
0x1002003d  add     eax, 7
0x10020040  and     eax, edi
0x10020042  add     ebx, eax
0x10020044  mov     eax, [ebx]
0x10020046  add     eax, 7
0x10020049  and     eax, edi
0x1002004b  add     ebx, eax
0x1002004d  dec     ecx
0x1002004e  mov     [edx+4], ecx
0x10020051  sub     esi, 1
0x10020054  jnz     short loc_10020029
0x10020056  test    byte ptr [ebx+4], 2
0x1002005a  mov     esi, [ebx]
0x1002005c  lea     eax, [esi+28h]
0x1002005f  mov     [esp+20h+nInBufferSize], eax
0x10020063  jz      short loc_1002007D
0x10020065  add     esi, 7
0x10020068  add     eax, 7
0x1002006b  and     esi, edi
0x1002006d  and     eax, edi
0x1002006f  add     esi, ebx
0x10020071  mov     [esp+20h+Src], esi
0x10020075  add     eax, [esi]
0x10020077  mov     [esp+20h+nInBufferSize], eax
0x1002007b  jmp     short loc_10020083
0x1002007d  xor     ecx, ecx
0x1002007f  mov     [esp+20h+Src], ecx
0x10020083  push    eax; unsigned int
0x10020084  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10020089  mov     [esp+24h+Block], eax
0x1002008d  pop     ecx
0x1002008e  test    eax, eax
0x10020090  jnz     short loc_1002009C
0x10020092  mov     ebx, 8007000Eh
0x10020097  jmp     loc_100202C7
0x1002009c  mov     edi, eax
0x1002009e  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x100200a3  mov     eax, [ebp+arg_C]
0x100200a6  xor     ecx, ecx
0x100200a8  inc     ecx
0x100200a9  movsd
0x100200aa  movsd
0x100200ab  movsd
0x100200ac  movsd
0x100200ad  mov     edi, [esp+20h+Block]
0x100200b1  mov     [edi+18h], eax
0x100200b4  lea     esi, [edi+20h]
0x100200b7  mov     dword ptr [edi+10h], 4
0x100200be  mov     [edi+14h], ecx
0x100200c1  mov     dword ptr [edi+1Ch], 0
0x100200c8  mov     eax, [ebx]
0x100200ca  add     eax, 8
0x100200cd  mov     [esi+4], ecx
0x100200d0  mov     [esi], eax
0x100200d2  lea     eax, [esi+8]
0x100200d5  push    dword ptr [ebx]; Size
0x100200d7  push    ebx; Src
0x100200d8  push    eax; void *
0x100200d9  call    _memcpy
0x100200de  mov     edx, [esp+2Ch+Src]
0x100200e2  add     esp, 0Ch
0x100200e5  test    edx, edx
0x100200e7  jz      short loc_1002010A
0x100200e9  mov     ecx, [esi]
0x100200eb  mov     eax, [edx]
0x100200ed  add     ecx, 7
0x100200f0  and     ecx, 0FFFFFFF8h
0x100200f3  add     eax, ecx
0x100200f5  inc     dword ptr [esi+4]
0x100200f8  mov     [esi], eax
0x100200fa  push    dword ptr [edx]; Size
0x100200fc  sub     eax, [edx]
0x100200fe  push    edx; Src
0x100200ff  add     eax, esi
0x10020101  push    eax; void *
0x10020102  call    _memcpy
0x10020107  add     esp, 0Ch
0x1002010a  mov     esi, [esp+20h+nInBufferSize]
0x1002010e  lea     eax, [esp+20h+BytesReturned]
0x10020112  push    eax; lpBytesReturned
0x10020113  push    0; nOutBufferSize
0x10020115  push    0; lpOutBuffer
0x10020117  push    esi; nInBufferSize
0x10020118  push    edi; lpInBuffer
0x10020119  push    2F0003h; dwIoControlCode
0x1002011e  push    [ebp+hDevice]; hDevice
0x10020121  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10020126  mov     ebx, eax
0x10020128  cmp     ebx, 8007007Ah
0x1002012e  jnz     short loc_10020180
0x10020130  mov     eax, _WPP_GLOBAL_Control
0x10020135  cmp     eax, offset _WPP_GLOBAL_Control
0x1002013a  jz      short loc_10020155
0x1002013c  cmp     byte ptr [eax+19h], 2
0x10020140  jb      short loc_10020155
0x10020142  push    dword ptr [eax+14h]
0x10020145  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002014a  push    dword ptr [eax+10h]; LoggerHandle
0x1002014d  push    17h
0x1002014f  pop     ecx; MessageNumber
0x10020150  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10020155  lea     eax, [esp+20h+BytesReturned]
0x10020159  push    eax; lpBytesReturned
0x1002015a  push    4; nOutBufferSize
0x1002015c  lea     eax, [esp+28h+nInBufferSize]
0x10020160  push    eax; lpOutBuffer
0x10020161  push    esi; nInBufferSize
0x10020162  push    edi; lpInBuffer
0x10020163  push    2F0003h; dwIoControlCode
0x10020168  push    [ebp+hDevice]; hDevice
0x1002016b  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10020170  mov     ebx, eax
0x10020172  test    ebx, ebx
0x10020174  js      short loc_10020180
0x10020176  mov     eax, [esp+20h+nInBufferSize]
0x1002017a  mov     [esp+20h+BytesReturned], eax
0x1002017e  jmp     short loc_10020190
0x10020180  cmp     ebx, 800700EAh
0x10020186  jnz     loc_100202B9
0x1002018c  mov     eax, [esp+20h+BytesReturned]
0x10020190  cmp     eax, 40h ; '@'
0x10020193  jb      loc_100202B4
0x10020199  push    eax; unsigned int
0x1002019a  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002019f  mov     [esp+24h+nInBufferSize], eax
0x100201a3  pop     ecx
0x100201a4  test    eax, eax
0x100201a6  jnz     short loc_100201B4
0x100201a8  push    edi; Block
0x100201a9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100201ae  pop     ecx
0x100201af  jmp     loc_10020092
0x100201b4  lea     ecx, [esp+20h+BytesReturned]
0x100201b8  push    ecx; lpBytesReturned
0x100201b9  push    [esp+24h+BytesReturned]; nOutBufferSize
0x100201bd  push    eax; lpOutBuffer
0x100201be  push    esi; nInBufferSize
0x100201bf  push    edi; lpInBuffer
0x100201c0  push    2F0003h; dwIoControlCode
0x100201c5  push    [ebp+hDevice]; hDevice
0x100201c8  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x100201cd  mov     ecx, [esp+20h+nInBufferSize]
0x100201d1  mov     ebx, eax
0x100201d3  test    ebx, ebx
0x100201d5  js      loc_100202A4
0x100201db  mov     eax, [ecx]
0x100201dd  cmp     eax, [esp+20h+BytesReturned]
0x100201e1  jnz     loc_100202AD
0x100201e7  cmp     eax, 40h ; '@'
0x100201ea  jb      loc_100202AD
0x100201f0  mov     edx, [ebp+arg_4]
0x100201f3  lea     esi, [ecx+10h]
0x100201f6  mov     edi, edx
0x100201f8  movsd
0x100201f9  movsd
0x100201fa  movsd
0x100201fb  movsd
0x100201fc  lea     esi, [ecx+20h]
0x100201ff  lea     edi, [edx+10h]
0x10020202  movsd
0x10020203  movsd
0x10020204  movsd
0x10020205  movsd
0x10020206  mov     eax, [ecx+4]
0x10020209  and     eax, 1
0x1002020c  mov     [edx+24h], eax
0x1002020f  mov     eax, [ecx+8]
0x10020212  test    eax, eax
0x10020214  jz      short loc_1002021C
0x10020216  mov     [edx+28h], eax
0x10020219  xor     eax, eax
0x1002021b  inc     eax
0x1002021c  mov     [edx+20h], eax
0x1002021f  mov     esi, 8007000Eh
0x10020224  mov     eax, [ecx]
0x10020226  cmp     eax, 40h ; '@'
0x10020229  jbe     short loc_10020246
0x1002022b  add     eax, 0FFFFFFC0h
0x1002022e  push    eax; unsigned int
0x1002022f  lea     eax, [ecx+40h]
0x10020232  mov     ecx, edx; this
0x10020234  push    eax; Src
0x10020235  call    ?SetFormat@CMediaType@@QAEHPAEK@Z; CMediaType::SetFormat(uchar *,ulong)
0x1002023a  mov     ecx, [esp+20h+nInBufferSize]
0x1002023e  test    eax, eax
0x10020240  mov     edx, [ebp+arg_4]
0x10020243  cmovz   ebx, esi
0x10020246  lea     esi, [ecx+30h]
0x10020249  lea     edi, [edx+2Ch]
0x1002024c  movsd
0x1002024d  movsd
0x1002024e  movsd
0x1002024f  movsd
0x10020250  test    byte ptr [ecx+4], 2
0x10020254  jz      short loc_100202A0
0x10020256  push    0Ch; Size
0x10020258  call    ??2@YAPAXI@Z; operator new(uint)
0x1002025d  mov     edx, eax
0x1002025f  pop     ecx
0x10020260  test    edx, edx
0x10020262  jz      short loc_10020297
0x10020264  mov     eax, [ebp+arg_4]
0x10020267  mov     ecx, [esp+20h+Src]
0x1002026b  mov     dword ptr [edx], offset ??_7CMediaTypeAttributes@@6B@; const CMediaTypeAttributes::`vftable'
0x10020271  mov     dword ptr [edx+4], 0
0x10020278  mov     dword ptr [edx+8], 1
0x1002027f  mov     [eax+3Ch], edx
0x10020282  mov     eax, [edx]
0x10020284  push    ecx
0x10020285  push    edx
0x10020286  mov     esi, [eax+10h]
0x10020289  mov     ecx, esi; this
0x1002028b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10020291  call    esi
0x10020293  mov     ebx, eax
0x10020295  jmp     short loc_1002029C
0x10020297  mov     ebx, 8007000Eh
0x1002029c  mov     ecx, [esp+20h+nInBufferSize]
0x100202a0  mov     edi, [esp+20h+Block]
0x100202a4  push    ecx; Block
0x100202a5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100202aa  pop     ecx
0x100202ab  jmp     short loc_100202B9
0x100202ad  mov     ebx, 8000FFFFh
0x100202b2  jmp     short loc_100202A4
0x100202b4  mov     ebx, 8000FFFFh
0x100202b9  push    edi; Block
0x100202ba  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100202bf  pop     ecx
0x100202c0  jmp     short loc_100202C7
0x100202c2  mov     ebx, 40103h
0x100202c7  push    [esp+20h+pv]; pv
0x100202cb  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100202d1  mov     eax, ebx
0x100202d3  pop     edi
0x100202d4  pop     esi
0x100202d5  pop     ebx
0x100202d6  mov     esp, ebp
0x100202d8  pop     ebp
0x100202d9  retn    10h
```
