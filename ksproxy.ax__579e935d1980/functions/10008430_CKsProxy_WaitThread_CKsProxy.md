# CKsProxy::WaitThread(CKsProxy *)

- ea: `0x10008430`
- end: `0x10008636`
- name: `?WaitThread@CKsProxy@@SGKPAV1@@Z`
- size: `518`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10008430`
- `0x1001f3b0`
- `0x10030c17`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10008580`
- `KERNEL32!GetLastError` at `0x10008580`
- `KERNEL32!SetEvent` at `0x10008620`
- `KERNEL32!SetEvent` at `0x10008620`
- `KERNEL32!CreateEventW` at `0x10008570`
- `KERNEL32!CreateEventW` at `0x10008570`
- `KERNEL32!CloseHandle` at `0x100084e5`
- `KERNEL32!CloseHandle` at `0x10008604`
- `KERNEL32!CloseHandle` at `0x100084e5`
- `KERNEL32!CloseHandle` at `0x10008604`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x10008453`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x10008453`

## pseudocode

```c
ULONG __stdcall CKsProxy::WaitThread(PVOID Parameter)
{
  int v1; // eax
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // esi
  int v5; // eax
  unsigned int v6; // eax
  HANDLE EventW; // eax
  signed int LastError; // eax
  unsigned int v9; // ecx
  int v10; // edi
  DWORD BytesReturned; // [esp+Ch] [ebp-2Ch] BYREF
  int OutBuffer; // [esp+10h] [ebp-28h] BYREF
  HANDLE hObject; // [esp+14h] [ebp-24h]
  int v15; // [esp+18h] [ebp-20h]
  int v16; // [esp+1Ch] [ebp-1Ch]
  GUID InBuffer; // [esp+20h] [ebp-18h] BYREF
  int v18; // [esp+30h] [ebp-8h]
  int v19; // [esp+34h] [ebp-4h]

  while ( 1 )
  {
    while ( WaitForMultipleObjectsEx(*((_DWORD *)Parameter + 79), *((const HANDLE **)Parameter + 77), 0, 0xFFFFFFFF, 0) )
    {
      if ( ++*((_DWORD *)Parameter + 83) == *((_DWORD *)Parameter + 79) - 1 )
        CBaseFilter::NotifyEvent((CBaseFilter *)Parameter, 1, 0, 0);
    }
    v1 = *((_DWORD *)Parameter + 81);
    if ( !v1 )
      return 0;
    v2 = v1 - 1;
    if ( v2 )
    {
      if ( v2 == 1 )
      {
        v3 = *((_DWORD *)Parameter + 79);
        v4 = 1;
        if ( v3 > 1 )
        {
          while ( *(_DWORD *)(*((_DWORD *)Parameter + 78) + 4 * v4) != *((_DWORD *)Parameter + 82) )
          {
            if ( ++v4 >= v3 )
              goto LABEL_24;
          }
          BytesReturned = 0;
          *((_DWORD *)Parameter + 79) = v3 - 1;
          v5 = *((_DWORD *)Parameter + 77);
          if ( *(_DWORD *)(v5 + 4 * v4) )
          {
            CloseHandle(*(HANDLE *)(v5 + 4 * v4));
            *(_DWORD *)(*((_DWORD *)Parameter + 77) + 4 * v4) = 0;
          }
          KsSynchronousDeviceControl(
            *(HANDLE *)(*((_DWORD *)Parameter + 78) + 4 * v4),
            0x2F000Bu,
            0,
            0,
            0,
            0,
            &BytesReturned);
          v6 = *((_DWORD *)Parameter + 79);
          if ( v4 < v6 )
          {
            *(_DWORD *)(*((_DWORD *)Parameter + 77) + 4 * v4) = *(_DWORD *)(*((_DWORD *)Parameter + 77) + 4 * v6);
            *(_DWORD *)(*((_DWORD *)Parameter + 78) + 4 * v4) = *(_DWORD *)(*((_DWORD *)Parameter + 78)
                                                                          + 4 * *((_DWORD *)Parameter + 79));
          }
        }
      }
    }
    else
    {
      BytesReturned = 0;
      OutBuffer = 1;
      InBuffer = _GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
      v18 = 4;
      v19 = 1;
      EventW = CreateEventW(0, 0, 0, 0);
      hObject = EventW;
      if ( EventW )
      {
        *(_DWORD *)(*((_DWORD *)Parameter + 77) + 4 * *((_DWORD *)Parameter + 79)) = EventW;
        v15 = 0;
        v16 = 0;
        v10 = KsSynchronousDeviceControl(
                *((HANDLE *)Parameter + 82),
                0x2F0007u,
                &InBuffer,
                0x18u,
                &OutBuffer,
                0x10u,
                &BytesReturned);
        if ( v10 < 0 )
        {
          if ( hObject )
          {
            CloseHandle(hObject);
            hObject = 0;
          }
        }
        else
        {
          *(_DWORD *)(*((_DWORD *)Parameter + 78) + 4 * (*((_DWORD *)Parameter + 79))++) = *((_DWORD *)Parameter + 82);
        }
        *((_DWORD *)Parameter + 82) = v10;
      }
      else
      {
        LastError = GetLastError();
        v9 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v9 = LastError;
        *((_DWORD *)Parameter + 82) = v9;
      }
    }
LABEL_24:
    SetEvent(*((HANDLE *)Parameter + 80));
  }
}

```

## disassembly

```asm
0x10008430  mov     edi, edi
0x10008432  push    ebp
0x10008433  mov     ebp, esp
0x10008435  and     esp, 0FFFFFFF8h
0x10008438  sub     esp, 2Ch
0x1000843b  push    ebx
0x1000843c  mov     ebx, [ebp+Parameter]
0x1000843f  push    esi
0x10008440  push    edi
0x10008441  xor     edi, edi
0x10008443  push    edi; bAlertable
0x10008444  push    0FFFFFFFFh; dwMilliseconds
0x10008446  push    edi; bWaitAll
0x10008447  push    dword ptr [ebx+134h]; lpHandles
0x1000844d  push    dword ptr [ebx+13Ch]; nCount
0x10008453  call    ds:__imp__WaitForMultipleObjectsEx@20; WaitForMultipleObjectsEx(x,x,x,x,x)
0x10008459  test    eax, eax
0x1000845b  jz      short loc_1000847F
0x1000845d  inc     dword ptr [ebx+14Ch]
0x10008463  mov     eax, [ebx+13Ch]
0x10008469  dec     eax
0x1000846a  cmp     [ebx+14Ch], eax
0x10008470  jnz     short loc_10008443
0x10008472  push    edi; int
0x10008473  push    edi; int
0x10008474  push    1; int
0x10008476  mov     ecx, ebx; this
0x10008478  call    ?NotifyEvent@CBaseFilter@@QAEJJJJ@Z; CBaseFilter::NotifyEvent(long,long,long)
0x1000847d  jmp     short loc_10008443
0x1000847f  mov     eax, [ebx+144h]
0x10008485  sub     eax, edi
0x10008487  jz      loc_1000862B
0x1000848d  sub     eax, 1
0x10008490  jz      loc_10008541
0x10008496  sub     eax, 1
0x10008499  jnz     loc_1000861A
0x1000849f  mov     eax, [ebx+13Ch]
0x100084a5  xor     esi, esi
0x100084a7  inc     esi
0x100084a8  cmp     eax, esi
0x100084aa  jbe     loc_1000861A
0x100084b0  mov     ecx, [ebx+148h]
0x100084b6  mov     edx, [ebx+138h]
0x100084bc  cmp     [edx+esi*4], ecx
0x100084bf  jz      short loc_100084CB
0x100084c1  inc     esi
0x100084c2  cmp     esi, eax
0x100084c4  jb      short loc_100084BC
0x100084c6  jmp     loc_1000861A
0x100084cb  dec     eax
0x100084cc  mov     [esp+38h+BytesReturned], edi
0x100084d0  mov     [ebx+13Ch], eax
0x100084d6  mov     eax, [ebx+134h]
0x100084dc  cmp     dword ptr [eax+esi*4], 0
0x100084e0  jz      short loc_100084F4
0x100084e2  push    dword ptr [eax+esi*4]; hObject
0x100084e5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100084eb  mov     eax, [ebx+134h]
0x100084f1  mov     [eax+esi*4], edi
0x100084f4  lea     eax, [esp+38h+BytesReturned]
0x100084f8  push    eax; lpBytesReturned
0x100084f9  mov     eax, [ebx+138h]
0x100084ff  push    edi; nOutBufferSize
0x10008500  push    edi; lpOutBuffer
0x10008501  push    edi; nInBufferSize
0x10008502  push    edi; lpInBuffer
0x10008503  push    2F000Bh; dwIoControlCode
0x10008508  push    dword ptr [eax+esi*4]; hDevice
0x1000850b  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10008510  mov     eax, [ebx+13Ch]
0x10008516  cmp     esi, eax
0x10008518  jnb     loc_1000861A
0x1000851e  mov     ecx, [ebx+134h]
0x10008524  mov     eax, [ecx+eax*4]
0x10008527  mov     [ecx+esi*4], eax
0x1000852a  mov     ecx, [ebx+138h]
0x10008530  mov     eax, [ebx+13Ch]
0x10008536  mov     eax, [ecx+eax*4]
0x10008539  mov     [ecx+esi*4], eax
0x1000853c  jmp     loc_1000861A
0x10008541  mov     [esp+38h+BytesReturned], edi
0x10008545  mov     esi, offset __GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000
0x1000854a  lea     edi, [esp+38h+InBuffer]
0x1000854e  mov     [esp+38h+OutBuffer], 1
0x10008556  movsd
0x10008557  movsd
0x10008558  movsd
0x10008559  movsd
0x1000855a  xor     edi, edi
0x1000855c  mov     [esp+38h+var_8], 4
0x10008564  push    edi; lpName
0x10008565  push    edi; bInitialState
0x10008566  push    edi; bManualReset
0x10008567  push    edi; lpEventAttributes
0x10008568  mov     [esp+48h+var_4], 1
0x10008570  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10008576  mov     edx, eax
0x10008578  mov     [esp+38h+hObject], edx
0x1000857c  test    edx, edx
0x1000857e  jnz     short loc_1000859C
0x10008580  call    ds:__imp__GetLastError@0; GetLastError()
0x10008586  movzx   ecx, ax
0x10008589  or      ecx, 80070000h
0x1000858f  test    eax, eax
0x10008591  cmovle  ecx, eax
0x10008594  mov     [ebx+148h], ecx
0x1000859a  jmp     short loc_1000861A
0x1000859c  mov     eax, [ebx+134h]
0x100085a2  mov     ecx, [ebx+13Ch]
0x100085a8  mov     [eax+ecx*4], edx
0x100085ab  lea     eax, [esp+38h+BytesReturned]
0x100085af  push    eax; lpBytesReturned
0x100085b0  push    10h; nOutBufferSize
0x100085b2  lea     eax, [esp+40h+OutBuffer]
0x100085b6  mov     [esp+40h+var_20], edi
0x100085ba  push    eax; lpOutBuffer
0x100085bb  push    18h; nInBufferSize
0x100085bd  lea     eax, [esp+48h+InBuffer]
0x100085c1  mov     [esp+48h+var_1C], edi
0x100085c5  push    eax; lpInBuffer
0x100085c6  push    2F0007h; dwIoControlCode
0x100085cb  push    dword ptr [ebx+148h]; hDevice
0x100085d1  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x100085d6  mov     edi, eax
0x100085d8  test    edi, edi
0x100085da  js      short loc_100085F9
0x100085dc  mov     esi, [ebx+13Ch]
0x100085e2  mov     edx, [ebx+138h]
0x100085e8  mov     ecx, [ebx+148h]
0x100085ee  mov     [edx+esi*4], ecx
0x100085f1  inc     dword ptr [ebx+13Ch]
0x100085f7  jmp     short loc_10008612
0x100085f9  cmp     [esp+38h+hObject], 0
0x100085fe  jz      short loc_10008612
0x10008600  push    [esp+38h+hObject]; hObject
0x10008604  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000860a  mov     [esp+38h+hObject], 0
0x10008612  mov     [ebx+148h], edi
0x10008618  xor     edi, edi
0x1000861a  push    dword ptr [ebx+140h]; hEvent
0x10008620  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10008626  jmp     loc_10008443
0x1000862b  pop     edi
0x1000862c  pop     esi
0x1000862d  xor     eax, eax
0x1000862f  pop     ebx
0x10008630  mov     esp, ebp
0x10008632  pop     ebp
0x10008633  retn    4
```
