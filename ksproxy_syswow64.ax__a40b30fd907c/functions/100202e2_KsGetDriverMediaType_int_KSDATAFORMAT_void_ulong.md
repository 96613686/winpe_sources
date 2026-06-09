# KsGetDriverMediaType(int,KSDATAFORMAT * *,void *,ulong)

- ea: `0x100202e2`
- end: `0x1002051f`
- name: `?KsGetDriverMediaType@@YGJHPAPATKSDATAFORMAT@@PAXK@Z`
- size: `573`
- prototype: `int __userpurge@<eax>(DWORD *@<edx>, int@<ecx>, HANDLE hDevice, union KSDATAFORMAT **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1001e1f8`

## callees

- `0x100063f1`
- `0x1001f3b0`
- `0x1001fbb0`
- `0x100202e2`
- `0x1003a6f2`
- `0x1003a72c`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x10020510`
- `ole32!CoTaskMemFree` at `0x10020510`

## pseudocode

```c
int __userpurge KsGetDriverMediaType@<eax>(
        DWORD *a1@<edx>,
        int a2@<ecx>,
        HANDLE hDevice,
        union KSDATAFORMAT **a4,
        void *a5,
        unsigned int a6)
{
  unsigned int v6; // esi
  int result; // eax
  _DWORD *v8; // edx
  unsigned int v9; // ecx
  char *i; // ebx
  bool v11; // zf
  int v12; // esi
  DWORD v13; // eax
  GUID *v14; // eax
  int v15; // esi
  GUID *v16; // esi
  int v17; // eax
  _DWORD *v18; // edx
  unsigned int v19; // eax
  void *v20; // ebx
  DWORD v21; // edi
  void *v22; // eax
  void *v23; // eax
  void *Block; // [esp+14h] [ebp-14h] BYREF
  DWORD nInBufferSize; // [esp+18h] [ebp-10h]
  void *Src; // [esp+1Ch] [ebp-Ch]
  LPVOID pv; // [esp+20h] [ebp-8h] BYREF
  DWORD BytesReturned; // [esp+24h] [ebp-4h] BYREF

  v6 = a2;
  pv = 0;
  if ( a2 < 0 )
    return -2147024809;
  if ( KsGetMultiplePinFactoryItems(hDevice, (int)a4, 13, &pv) >= 0
    || (result = KsGetMultiplePinFactoryItems(hDevice, (int)a4, 3, &pv), result >= 0) )
  {
    v8 = pv;
    if ( !pv )
      return -2147418113;
    v9 = *((_DWORD *)pv + 1);
    if ( v6 >= v9 )
    {
LABEL_36:
      v15 = 262403;
      goto LABEL_37;
    }
    BytesReturned = 0;
    for ( i = (char *)pv + 8; v6; --v6 )
    {
      if ( (i[4] & 2) != 0 )
      {
        v8[1] = --v9;
        if ( v6 >= v9 )
          goto LABEL_36;
        i += (*(_DWORD *)i + 7) & 0xFFFFFFF8;
      }
      i += (*(_DWORD *)i + 7) & 0xFFFFFFF8;
      v8[1] = --v9;
    }
    v11 = (i[4] & 2) == 0;
    v12 = *(_DWORD *)i;
    v13 = *(_DWORD *)i + 40;
    nInBufferSize = v13;
    if ( v11 )
    {
      Src = 0;
    }
    else
    {
      Src = &i[(v12 + 7) & 0xFFFFFFF8];
      v13 = *(_DWORD *)Src + ((v13 + 7) & 0xFFFFFFF8);
      nInBufferSize = v13;
    }
    v14 = (GUID *)operator new[](v13);
    Block = v14;
    if ( !v14 )
      goto LABEL_17;
    v14[1].Data1 = 4;
    *(_DWORD *)v14[1].Data4 = a4;
    *(_DWORD *)&v14[1].Data2 = 1;
    *v14 = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v16 = v14 + 2;
    *(_DWORD *)&v14[1].Data4[4] = 0;
    v17 = *(_DWORD *)i + 8;
    *(_DWORD *)&v16->Data2 = 1;
    v16->Data1 = v17;
    memcpy(v16->Data4, i, *(_DWORD *)i);
    v18 = Src;
    if ( Src )
    {
      v19 = ((v16->Data1 + 7) & 0xFFFFFFF8) + *(_DWORD *)Src;
      ++*(_DWORD *)&v16->Data2;
      v16->Data1 = v19;
      memcpy((char *)v16 + v19 - *v18, v18, *v18);
    }
    v20 = Block;
    v21 = nInBufferSize;
    v15 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, Block, nInBufferSize, 0, 0, &BytesReturned);
    if ( v15 != -2147024774 )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(0x18u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    v15 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, Block, nInBufferSize, &Block, 4u, &BytesReturned);
    if ( v15 >= 0 )
    {
      v22 = Block;
      BytesReturned = (DWORD)Block;
    }
    else
    {
LABEL_26:
      if ( v15 != -2147024662 )
        goto LABEL_35;
      v22 = (void *)BytesReturned;
    }
    if ( (unsigned int)v22 < 0x40 )
    {
      v15 = -2147418113;
    }
    else
    {
      v23 = operator new[]((unsigned int)v22);
      nInBufferSize = (DWORD)v23;
      if ( !v23 )
      {
        operator delete[](v20);
LABEL_17:
        v15 = -2147024882;
LABEL_37:
        CoTaskMemFree(pv);
        return v15;
      }
      v15 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v20, v21, v23, BytesReturned, &BytesReturned);
      if ( v15 < 0 )
        operator delete[]((void *)nInBufferSize);
      else
        *a1 = nInBufferSize;
    }
LABEL_35:
    operator delete[](v20);
    goto LABEL_37;
  }
  return result;
}

```

## disassembly

```asm
0x100202e2  mov     edi, edi
0x100202e4  push    ebp
0x100202e5  mov     ebp, esp
0x100202e7  sub     esp, 1Ch
0x100202ea  push    ebx
0x100202eb  push    esi
0x100202ec  push    edi
0x100202ed  mov     esi, ecx
0x100202ef  mov     [ebp+var_18], edx
0x100202f2  xor     edi, edi
0x100202f4  mov     [ebp+pv], edi
0x100202f7  test    esi, esi
0x100202f9  jns     short loc_10020305
0x100202fb  mov     eax, 80070057h
0x10020300  jmp     loc_10020518
0x10020305  mov     ebx, [ebp+arg_4]
0x10020308  lea     eax, [ebp+pv]
0x1002030b  push    eax; int
0x1002030c  push    0Dh; int
0x1002030e  push    ebx; int
0x1002030f  push    [ebp+hDevice]; hDevice
0x10020312  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x10020317  test    eax, eax
0x10020319  jns     short loc_10020332
0x1002031b  lea     eax, [ebp+pv]
0x1002031e  push    eax; int
0x1002031f  push    3; int
0x10020321  push    ebx; int
0x10020322  push    [ebp+hDevice]; hDevice
0x10020325  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1002032a  test    eax, eax
0x1002032c  js      loc_10020518
0x10020332  mov     edx, [ebp+pv]
0x10020335  test    edx, edx
0x10020337  jnz     short loc_10020343
0x10020339  mov     eax, 8000FFFFh
0x1002033e  jmp     loc_10020518
0x10020343  mov     ecx, [edx+4]
0x10020346  cmp     esi, ecx
0x10020348  jnb     loc_10020508
0x1002034e  mov     [ebp+BytesReturned], edi
0x10020351  lea     ebx, [edx+8]
0x10020354  test    esi, esi
0x10020356  jz      short loc_10020387
0x10020358  test    byte ptr [ebx+4], 2
0x1002035c  jz      short loc_10020374
0x1002035e  dec     ecx
0x1002035f  mov     [edx+4], ecx
0x10020362  cmp     esi, ecx
0x10020364  jnb     loc_10020508
0x1002036a  mov     eax, [ebx]
0x1002036c  add     eax, 7
0x1002036f  and     eax, 0FFFFFFF8h
0x10020372  add     ebx, eax
0x10020374  mov     eax, [ebx]
0x10020376  add     eax, 7
0x10020379  and     eax, 0FFFFFFF8h
0x1002037c  add     ebx, eax
0x1002037e  dec     ecx
0x1002037f  mov     [edx+4], ecx
0x10020382  sub     esi, 1
0x10020385  jnz     short loc_10020358
0x10020387  test    byte ptr [ebx+4], 2
0x1002038b  mov     esi, [ebx]
0x1002038d  lea     eax, [esi+28h]
0x10020390  mov     [ebp+nInBufferSize], eax
0x10020393  jz      short loc_100203AD
0x10020395  add     esi, 7
0x10020398  add     eax, 7
0x1002039b  and     esi, 0FFFFFFF8h
0x1002039e  and     eax, 0FFFFFFF8h
0x100203a1  add     esi, ebx
0x100203a3  mov     [ebp+Src], esi
0x100203a6  add     eax, [esi]
0x100203a8  mov     [ebp+nInBufferSize], eax
0x100203ab  jmp     short loc_100203B0
0x100203ad  mov     [ebp+Src], edi
0x100203b0  push    eax; unsigned int
0x100203b1  call    ??_U@YAPAXI@Z; operator new[](uint)
0x100203b6  mov     [ebp+Block], eax
0x100203b9  pop     ecx
0x100203ba  test    eax, eax
0x100203bc  jnz     short loc_100203C8
0x100203be  mov     esi, 8007000Eh
0x100203c3  jmp     loc_1002050D
0x100203c8  mov     ecx, [ebp+arg_4]
0x100203cb  mov     edi, eax
0x100203cd  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x100203d2  mov     dword ptr [eax+10h], 4
0x100203d9  mov     [eax+18h], ecx
0x100203dc  xor     edx, edx
0x100203de  inc     edx
0x100203df  mov     [eax+14h], edx
0x100203e2  movsd
0x100203e3  movsd
0x100203e4  movsd
0x100203e5  movsd
0x100203e6  lea     esi, [eax+20h]
0x100203e9  xor     edi, edi
0x100203eb  mov     [eax+1Ch], edi
0x100203ee  mov     eax, [ebx]
0x100203f0  add     eax, 8
0x100203f3  mov     [esi+4], edx
0x100203f6  mov     [esi], eax
0x100203f8  lea     eax, [esi+8]
0x100203fb  push    dword ptr [ebx]; Size
0x100203fd  push    ebx; Src
0x100203fe  push    eax; void *
0x100203ff  call    _memcpy
0x10020404  mov     edx, [ebp+Src]
0x10020407  add     esp, 0Ch
0x1002040a  test    edx, edx
0x1002040c  jz      short loc_1002042F
0x1002040e  mov     ecx, [esi]
0x10020410  mov     eax, [edx]
0x10020412  add     ecx, 7
0x10020415  and     ecx, 0FFFFFFF8h
0x10020418  add     eax, ecx
0x1002041a  inc     dword ptr [esi+4]
0x1002041d  mov     [esi], eax
0x1002041f  push    dword ptr [edx]; Size
0x10020421  sub     eax, [edx]
0x10020423  push    edx; Src
0x10020424  add     eax, esi
0x10020426  push    eax; void *
0x10020427  call    _memcpy
0x1002042c  add     esp, 0Ch
0x1002042f  mov     ebx, [ebp+Block]
0x10020432  lea     eax, [ebp+BytesReturned]
0x10020435  push    eax; lpBytesReturned
0x10020436  push    edi; nOutBufferSize
0x10020437  push    edi; lpOutBuffer
0x10020438  mov     edi, [ebp+nInBufferSize]
0x1002043b  push    edi; nInBufferSize
0x1002043c  push    ebx; lpInBuffer
0x1002043d  push    2F0003h; dwIoControlCode
0x10020442  push    [ebp+hDevice]; hDevice
0x10020445  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1002044a  mov     esi, eax
0x1002044c  cmp     esi, 8007007Ah
0x10020452  jnz     short loc_100204A0
0x10020454  mov     eax, _WPP_GLOBAL_Control
0x10020459  cmp     eax, offset _WPP_GLOBAL_Control
0x1002045e  jz      short loc_10020479
0x10020460  cmp     byte ptr [eax+19h], 2
0x10020464  jb      short loc_10020479
0x10020466  push    dword ptr [eax+14h]
0x10020469  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002046e  push    dword ptr [eax+10h]; LoggerHandle
0x10020471  push    18h
0x10020473  pop     ecx; MessageNumber
0x10020474  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10020479  lea     eax, [ebp+BytesReturned]
0x1002047c  push    eax; lpBytesReturned
0x1002047d  push    4; nOutBufferSize
0x1002047f  lea     eax, [ebp+Block]
0x10020482  push    eax; lpOutBuffer
0x10020483  push    edi; nInBufferSize
0x10020484  push    ebx; lpInBuffer
0x10020485  push    2F0003h; dwIoControlCode
0x1002048a  push    [ebp+hDevice]; hDevice
0x1002048d  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10020492  mov     esi, eax
0x10020494  test    esi, esi
0x10020496  js      short loc_100204A0
0x10020498  mov     eax, [ebp+Block]
0x1002049b  mov     [ebp+BytesReturned], eax
0x1002049e  jmp     short loc_100204AB
0x100204a0  cmp     esi, 800700EAh
0x100204a6  jnz     short loc_100204FF
0x100204a8  mov     eax, [ebp+BytesReturned]
0x100204ab  cmp     eax, 40h ; '@'
0x100204ae  jb      short loc_100204FA
0x100204b0  push    eax; unsigned int
0x100204b1  call    ??_U@YAPAXI@Z; operator new[](uint)
0x100204b6  mov     [ebp+nInBufferSize], eax
0x100204b9  pop     ecx
0x100204ba  test    eax, eax
0x100204bc  jnz     short loc_100204CA
0x100204be  push    ebx; Block
0x100204bf  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100204c4  pop     ecx
0x100204c5  jmp     loc_100203BE
0x100204ca  lea     ecx, [ebp+BytesReturned]
0x100204cd  push    ecx; lpBytesReturned
0x100204ce  push    [ebp+BytesReturned]; nOutBufferSize
0x100204d1  push    eax; lpOutBuffer
0x100204d2  push    edi; nInBufferSize
0x100204d3  push    ebx; lpInBuffer
0x100204d4  push    2F0003h; dwIoControlCode
0x100204d9  push    [ebp+hDevice]; hDevice
0x100204dc  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x100204e1  mov     esi, eax
0x100204e3  mov     eax, [ebp+nInBufferSize]
0x100204e6  test    esi, esi
0x100204e8  js      short loc_100204F1
0x100204ea  mov     ecx, [ebp+var_18]
0x100204ed  mov     [ecx], eax
0x100204ef  jmp     short loc_100204FF
0x100204f1  push    eax; Block
0x100204f2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100204f7  pop     ecx
0x100204f8  jmp     short loc_100204FF
0x100204fa  mov     esi, 8000FFFFh
0x100204ff  push    ebx; Block
0x10020500  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10020505  pop     ecx
0x10020506  jmp     short loc_1002050D
0x10020508  mov     esi, 40103h
0x1002050d  push    [ebp+pv]; pv
0x10020510  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10020516  mov     eax, esi
0x10020518  pop     edi
0x10020519  pop     esi
0x1002051a  pop     ebx
0x1002051b  leave
0x1002051c  retn    8
```
