# IntersectKsFormat(void *,ulong,KSDATAFORMAT *,KSDATAFORMAT * *)

- ea: `0x1001e8ef`
- end: `0x1001ec0e`
- name: `?IntersectKsFormat@@YGJPAXKPATKSDATAFORMAT@@PAPAT1@@Z`
- size: `799`
- prototype: `int __stdcall(void *, unsigned int, union KSDATAFORMAT *, union KSDATAFORMAT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x1001ec14`

## callees

- `0x100063f1`
- `0x1001e5ad`
- `0x1001e8ef`
- `0x1001f3b0`
- `0x1001fbb0`
- `0x1003a6f2`
- `0x1003a72c`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001eb47`
- `ole32!CoTaskMemAlloc` at `0x1001eb47`
- `ole32!CoTaskMemFree` at `0x1001ebb6`
- `ole32!CoTaskMemFree` at `0x1001ebef`
- `ole32!CoTaskMemFree` at `0x1001ebb6`
- `ole32!CoTaskMemFree` at `0x1001ebef`

## pseudocode

```c
int __userpurge IntersectKsFormat@<eax>(
        int a1@<edx>,
        void *a2@<ecx>,
        _DWORD *a3,
        _DWORD *a4,
        union KSDATAFORMAT *a5,
        union KSDATAFORMAT **a6)
{
  int v7; // ecx
  int v8; // eax
  int i; // ecx
  _DWORD *v10; // edi
  int result; // eax
  _DWORD *v12; // ebx
  unsigned int v13; // ecx
  bool v14; // cc
  _DWORD *v15; // eax
  _DWORD *v16; // ebx
  _DWORD *v17; // edi
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  int v21; // eax
  SIZE_T v22; // eax
  void *v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // esi
  union KSDATAFORMAT *v27; // [esp+0h] [ebp-48h]
  union KSDATAFORMAT *v28; // [esp+4h] [ebp-44h]
  DWORD BytesReturned; // [esp+10h] [ebp-38h] BYREF
  LPVOID pv; // [esp+14h] [ebp-34h] BYREF
  int v31; // [esp+18h] [ebp-30h]
  int v32; // [esp+1Ch] [ebp-2Ch]
  int v33; // [esp+20h] [ebp-28h]
  HANDLE hDevice; // [esp+24h] [ebp-24h]
  void *Src; // [esp+28h] [ebp-20h]
  int v36; // [esp+2Ch] [ebp-1Ch]
  const GUID *v37; // [esp+30h] [ebp-18h]
  int v38; // [esp+34h] [ebp-14h]
  int v39; // [esp+38h] [ebp-10h]
  int v40; // [esp+3Ch] [ebp-Ch]
  void *v41; // [esp+40h] [ebp-8h]
  SIZE_T cb; // [esp+44h] [ebp-4h] BYREF

  v7 = 0;
  v36 = a1;
  hDevice = a2;
  pv = 0;
  v41 = 0;
  v31 = 0;
  while ( 1 )
  {
    v8 = a3[v7 + 12];
    v37 = &FORMAT_VideoInfo2;
    if ( v8 != *(&FORMAT_VideoInfo.Data1 + v7) )
      break;
    if ( ++v7 == 4 )
    {
      v32 = a3[29];
      v33 = a3[30];
      goto LABEL_9;
    }
  }
  for ( i = 0; i != 4; ++i )
  {
    if ( a3[i + 12] != *(&v37->Data1 + i) )
      return -2147024809;
  }
  v32 = a3[35];
  v33 = a3[36];
LABEL_9:
  v38 = a3[26];
  v39 = a3[27];
  if ( KsGetMultiplePinFactoryItems(a2, a1, 13, (int)&pv) >= 0 && (v10 = pv) != 0
    || (result = KsGetMultiplePinFactoryItems(a2, v36, 3, (int)&pv), result >= 0) && (v10 = pv) != 0 )
  {
    v12 = v10 + 2;
    v13 = 0;
    Src = v10 + 2;
    v40 = 0;
    while ( 1 )
    {
      if ( v13 >= v10[1] )
      {
LABEL_41:
        CoTaskMemFree(v10);
        if ( !v31 )
          return -2147467259;
        *a4 = v41;
        return 0;
      }
      v14 = *v12 <= 0xF4240u;
      BytesReturned = 0;
      if ( !v14 )
      {
        v26 = -2147024809;
        goto LABEL_46;
      }
      if ( IsFormatInRange(v27, v28) >= 0 )
        break;
LABEL_40:
      v13 = v40 + 1;
      v12 = (_DWORD *)((char *)v12 + ((*v12 + 7) & 0xFFFFFFF8));
      ++v40;
      Src = v12;
      if ( v31 )
        goto LABEL_41;
    }
    v15 = operator new[](*v12 + 40);
    v16 = v15;
    if ( !v15 )
    {
      v26 = -2147024882;
      goto LABEL_46;
    }
    v15[6] = v36;
    v15[4] = 4;
    v15[7] = 0;
    v15[5] = 1;
    *(GUID *)v15 = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v17 = Src;
    v18 = *(_DWORD *)Src + 8;
    v16[9] = 1;
    v16[8] = v18;
    memcpy(v16 + 10, v17, *v17);
    v19 = 0;
    while ( a3[v19 + 12] == *(&FORMAT_VideoInfo.Data1 + v19) )
    {
      if ( ++v19 == 4 )
      {
        v16[75] = v32;
        v16[76] = v33;
LABEL_26:
        v16[72] = v38;
        v16[73] = v39;
        goto LABEL_27;
      }
    }
    v20 = 0;
    while ( a3[v20 + 12] == *(&v37->Data1 + v20) )
    {
      if ( ++v20 == 4 )
      {
        v16[81] = v32;
        v16[82] = v33;
        goto LABEL_26;
      }
    }
LABEL_27:
    v21 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v16, *v17 + 40, 0, 0, &BytesReturned);
    if ( v21 != -2147024774 )
      goto LABEL_32;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_(0x33u, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    v21 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v16, *v17 + 40, &cb, 4u, &BytesReturned);
    if ( v21 >= 0 )
    {
      v22 = cb;
      BytesReturned = cb;
    }
    else
    {
LABEL_32:
      if ( v21 != -2147024662 )
      {
LABEL_39:
        operator delete[](v16);
        v10 = pv;
        v12 = Src;
        goto LABEL_40;
      }
      v22 = BytesReturned;
    }
    if ( v22 >= 0x40 )
    {
      v23 = CoTaskMemAlloc(v22);
      v41 = v23;
      if ( !v23 )
      {
        operator delete[](v16);
        v10 = pv;
        v26 = -2147024882;
LABEL_46:
        CoTaskMemFree(v10);
        return v26;
      }
      v24 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, v16, *v17 + 40, v23, BytesReturned, &BytesReturned);
      v25 = v31;
      if ( v24 >= 0 )
        v25 = 1;
      v31 = v25;
    }
    goto LABEL_39;
  }
  return result;
}

```

## disassembly

```asm
0x1001e8ef  mov     edi, edi
0x1001e8f1  push    ebp
0x1001e8f2  mov     ebp, esp
0x1001e8f4  and     esp, 0FFFFFFF8h
0x1001e8f7  sub     esp, 3Ch
0x1001e8fa  push    ebx
0x1001e8fb  push    esi; union KSDATAFORMAT *
0x1001e8fc  mov     esi, [ebp+arg_0]
0x1001e8ff  mov     ebx, ecx
0x1001e901  xor     ecx, ecx
0x1001e903  mov     [esp+44h+var_1C], edx
0x1001e907  push    edi; union KSDATAFORMAT *
0x1001e908  mov     [esp+48h+hDevice], ebx
0x1001e90c  mov     edi, offset _FORMAT_VideoInfo
0x1001e911  mov     [esp+48h+pv], 0
0x1001e919  mov     [esp+48h+var_8], ecx
0x1001e91d  mov     [esp+48h+var_30], ecx
0x1001e921  mov     eax, [esi+ecx*4+30h]
0x1001e925  mov     [esp+48h+var_18], offset _FORMAT_VideoInfo2
0x1001e92d  cmp     eax, [edi+ecx*4]
0x1001e930  jnz     short loc_1001E948
0x1001e932  inc     ecx
0x1001e933  cmp     ecx, 4
0x1001e936  jnz     short loc_1001E921
0x1001e938  mov     edi, [esi+74h]
0x1001e93b  mov     [esp+48h+var_2C], edi
0x1001e93f  mov     edi, [esi+78h]
0x1001e942  mov     [esp+48h+var_28], edi
0x1001e946  jmp     short loc_1001E975
0x1001e948  mov     edi, [esp+48h+var_18]
0x1001e94c  xor     ecx, ecx
0x1001e94e  mov     eax, [esi+ecx*4+30h]
0x1001e952  cmp     eax, [edi+ecx*4]
0x1001e955  jnz     loc_1001EC00
0x1001e95b  inc     ecx
0x1001e95c  cmp     ecx, 4
0x1001e95f  jnz     short loc_1001E94E
0x1001e961  mov     eax, [esi+8Ch]
0x1001e967  mov     [esp+48h+var_2C], eax
0x1001e96b  mov     eax, [esi+90h]
0x1001e971  mov     [esp+48h+var_28], eax
0x1001e975  mov     eax, [esi+68h]
0x1001e978  mov     [esp+48h+var_14], eax
0x1001e97c  mov     eax, [esi+6Ch]
0x1001e97f  mov     [esp+48h+var_10], eax
0x1001e983  lea     eax, [esp+48h+pv]
0x1001e987  push    eax; int
0x1001e988  push    0Dh; int
0x1001e98a  push    edx; int
0x1001e98b  push    ebx; hDevice
0x1001e98c  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001e991  test    eax, eax
0x1001e993  js      short loc_1001E99D
0x1001e995  mov     edi, [esp+48h+pv]
0x1001e999  test    edi, edi
0x1001e99b  jnz     short loc_1001E9C2
0x1001e99d  lea     eax, [esp+48h+pv]
0x1001e9a1  push    eax; int
0x1001e9a2  push    3; int
0x1001e9a4  push    [esp+50h+var_1C]; int
0x1001e9a8  push    ebx; hDevice
0x1001e9a9  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001e9ae  test    eax, eax
0x1001e9b0  js      loc_1001EC05
0x1001e9b6  mov     edi, [esp+48h+pv]
0x1001e9ba  test    edi, edi
0x1001e9bc  jz      loc_1001EC05
0x1001e9c2  lea     ebx, [edi+8]
0x1001e9c5  xor     ecx, ecx
0x1001e9c7  mov     [esp+48h+Src], ebx
0x1001e9cb  mov     [esp+48h+var_C], ecx
0x1001e9cf  cmp     ecx, [edi+4]
0x1001e9d2  jnb     loc_1001EBB5
0x1001e9d8  cmp     dword ptr [ebx], 0F4240h
0x1001e9de  mov     [esp+48h+BytesReturned], 0
0x1001e9e6  ja      loc_1001EBE9
0x1001e9ec  mov     edx, esi
0x1001e9ee  mov     ecx, ebx
0x1001e9f0  call    ?IsFormatInRange@@YGJPATKSDATAFORMAT@@0@Z; IsFormatInRange(KSDATAFORMAT *,KSDATAFORMAT *)
0x1001e9f5  test    eax, eax
0x1001e9f7  js      loc_1001EB93
0x1001e9fd  mov     eax, [ebx]
0x1001e9ff  add     eax, 28h ; '('
0x1001ea02  push    eax; unsigned int
0x1001ea03  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1001ea08  mov     ebx, eax
0x1001ea0a  pop     ecx
0x1001ea0b  test    ebx, ebx
0x1001ea0d  jz      loc_1001EBE2
0x1001ea13  mov     eax, [esp+48h+var_1C]
0x1001ea17  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x1001ea1c  mov     edi, ebx
0x1001ea1e  mov     [ebx+18h], eax
0x1001ea21  xor     ecx, ecx
0x1001ea23  mov     dword ptr [ebx+10h], 4
0x1001ea2a  inc     ecx
0x1001ea2b  mov     dword ptr [ebx+1Ch], 0
0x1001ea32  mov     [ebx+14h], ecx
0x1001ea35  movsd
0x1001ea36  movsd
0x1001ea37  movsd
0x1001ea38  movsd
0x1001ea39  mov     edi, [esp+48h+Src]
0x1001ea3d  mov     eax, [edi]
0x1001ea3f  add     eax, 8
0x1001ea42  mov     [ebx+24h], ecx
0x1001ea45  mov     [ebx+20h], eax
0x1001ea48  lea     eax, [ebx+28h]
0x1001ea4b  push    dword ptr [edi]; Size
0x1001ea4d  push    edi; Src
0x1001ea4e  push    eax; void *
0x1001ea4f  call    _memcpy
0x1001ea54  mov     esi, [ebp+arg_0]
0x1001ea57  add     esp, 0Ch
0x1001ea5a  xor     ecx, ecx
0x1001ea5c  mov     edx, offset _FORMAT_VideoInfo
0x1001ea61  mov     eax, [esi+ecx*4+30h]
0x1001ea65  cmp     eax, [edx+ecx*4]
0x1001ea68  jnz     short loc_1001EA86
0x1001ea6a  inc     ecx
0x1001ea6b  cmp     ecx, 4
0x1001ea6e  jnz     short loc_1001EA61
0x1001ea70  mov     eax, [esp+48h+var_2C]
0x1001ea74  mov     [ebx+12Ch], eax
0x1001ea7a  mov     eax, [esp+48h+var_28]
0x1001ea7e  mov     [ebx+130h], eax
0x1001ea84  jmp     short loc_1001EAAF
0x1001ea86  mov     edx, [esp+48h+var_18]
0x1001ea8a  xor     ecx, ecx
0x1001ea8c  mov     eax, [esi+ecx*4+30h]
0x1001ea90  cmp     eax, [edx+ecx*4]
0x1001ea93  jnz     short loc_1001EAC3
0x1001ea95  inc     ecx
0x1001ea96  cmp     ecx, 4
0x1001ea99  jnz     short loc_1001EA8C
0x1001ea9b  mov     eax, [esp+48h+var_2C]
0x1001ea9f  mov     [ebx+144h], eax
0x1001eaa5  mov     eax, [esp+48h+var_28]
0x1001eaa9  mov     [ebx+148h], eax
0x1001eaaf  mov     eax, [esp+48h+var_14]
0x1001eab3  mov     [ebx+120h], eax
0x1001eab9  mov     eax, [esp+48h+var_10]
0x1001eabd  mov     [ebx+124h], eax
0x1001eac3  lea     eax, [esp+48h+BytesReturned]
0x1001eac7  push    eax; lpBytesReturned
0x1001eac8  mov     eax, [edi]
0x1001eaca  push    0; nOutBufferSize
0x1001eacc  push    0; lpOutBuffer
0x1001eace  add     eax, 28h ; '('
0x1001ead1  push    eax; nInBufferSize
0x1001ead2  push    ebx; lpInBuffer
0x1001ead3  push    2F0003h; dwIoControlCode
0x1001ead8  push    [esp+60h+hDevice]; hDevice
0x1001eadc  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001eae1  cmp     eax, 8007007Ah
0x1001eae6  jnz     short loc_1001EB36
0x1001eae8  mov     eax, _WPP_GLOBAL_Control
0x1001eaed  cmp     eax, offset _WPP_GLOBAL_Control
0x1001eaf2  jz      short loc_1001EB07
0x1001eaf4  push    dword ptr [eax+14h]
0x1001eaf7  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001eafc  push    dword ptr [eax+10h]; LoggerHandle
0x1001eaff  push    33h ; '3'
0x1001eb01  pop     ecx; MessageNumber
0x1001eb02  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1001eb07  lea     eax, [esp+48h+BytesReturned]
0x1001eb0b  push    eax; lpBytesReturned
0x1001eb0c  push    4; nOutBufferSize
0x1001eb0e  lea     eax, [esp+50h+cb]
0x1001eb12  push    eax; lpOutBuffer
0x1001eb13  mov     eax, [edi]
0x1001eb15  add     eax, 28h ; '('
0x1001eb18  push    eax; nInBufferSize
0x1001eb19  push    ebx; lpInBuffer
0x1001eb1a  push    2F0003h; dwIoControlCode
0x1001eb1f  push    [esp+60h+hDevice]; hDevice
0x1001eb23  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001eb28  test    eax, eax
0x1001eb2a  js      short loc_1001EB36
0x1001eb2c  mov     eax, [esp+48h+cb]
0x1001eb30  mov     [esp+48h+BytesReturned], eax
0x1001eb34  jmp     short loc_1001EB41
0x1001eb36  cmp     eax, 800700EAh
0x1001eb3b  jnz     short loc_1001EB84
0x1001eb3d  mov     eax, [esp+48h+BytesReturned]
0x1001eb41  cmp     eax, 40h ; '@'
0x1001eb44  jb      short loc_1001EB84
0x1001eb46  push    eax; cb
0x1001eb47  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001eb4d  mov     [esp+48h+var_8], eax
0x1001eb51  test    eax, eax
0x1001eb53  jz      short loc_1001EBD0
0x1001eb55  lea     ecx, [esp+48h+BytesReturned]
0x1001eb59  push    ecx; lpBytesReturned
0x1001eb5a  push    [esp+4Ch+BytesReturned]; nOutBufferSize
0x1001eb5e  mov     ecx, [edi]
0x1001eb60  push    eax; lpOutBuffer
0x1001eb61  add     ecx, 28h ; '('
0x1001eb64  push    ecx; nInBufferSize
0x1001eb65  push    ebx; lpInBuffer
0x1001eb66  push    2F0003h; dwIoControlCode
0x1001eb6b  push    [esp+60h+hDevice]; hDevice
0x1001eb6f  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001eb74  mov     ecx, [esp+48h+var_30]
0x1001eb78  test    eax, eax
0x1001eb7a  push    1
0x1001eb7c  pop     eax
0x1001eb7d  cmovns  ecx, eax
0x1001eb80  mov     [esp+48h+var_30], ecx
0x1001eb84  push    ebx; Block
0x1001eb85  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001eb8a  mov     edi, [esp+4Ch+pv]
0x1001eb8e  mov     ebx, [esp+4Ch+Src]
0x1001eb92  pop     ecx
0x1001eb93  mov     eax, [ebx]
0x1001eb95  mov     ecx, [esp+48h+var_C]
0x1001eb99  add     eax, 7
0x1001eb9c  and     eax, 0FFFFFFF8h
0x1001eb9f  inc     ecx
0x1001eba0  add     ebx, eax
0x1001eba2  mov     [esp+48h+var_C], ecx
0x1001eba6  cmp     [esp+48h+var_30], 0
0x1001ebab  mov     [esp+48h+Src], ebx
0x1001ebaf  jz      loc_1001E9CF
0x1001ebb5  push    edi; pv
0x1001ebb6  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ebbc  cmp     [esp+48h+var_30], 0
0x1001ebc1  jz      short loc_1001EBF9
0x1001ebc3  mov     eax, [ebp+arg_4]
0x1001ebc6  mov     ecx, [esp+48h+var_8]
0x1001ebca  mov     [eax], ecx
0x1001ebcc  xor     eax, eax
0x1001ebce  jmp     short loc_1001EC05
0x1001ebd0  push    ebx; Block
0x1001ebd1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001ebd6  mov     edi, [esp+4Ch+pv]
0x1001ebda  mov     esi, 8007000Eh
0x1001ebdf  pop     ecx
0x1001ebe0  jmp     short loc_1001EBEE
0x1001ebe2  mov     esi, 8007000Eh
0x1001ebe7  jmp     short loc_1001EBEE
0x1001ebe9  mov     esi, 80070057h
0x1001ebee  push    edi; pv
0x1001ebef  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ebf5  mov     eax, esi
0x1001ebf7  jmp     short loc_1001EC05
0x1001ebf9  mov     eax, 80004005h
0x1001ebfe  jmp     short loc_1001EC05
0x1001ec00  mov     eax, 80070057h
0x1001ec05  pop     edi
0x1001ec06  pop     esi
0x1001ec07  pop     ebx
0x1001ec08  mov     esp, ebp
0x1001ec0a  pop     ebp
0x1001ec0b  retn    8
```
