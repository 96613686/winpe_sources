# CFormatChangeHandler::KsProcessMediaSamples(IKsDataTypeHandler *,IMediaSample * *,long *,KSIOOPERATION,_KSSTREAM_SEGMENT * *)

- ea: `0x10010350`
- end: `0x1001057b`
- name: `?KsProcessMediaSamples@CFormatChangeHandler@@UAGJPAUIKsDataTypeHandler@@PAPAUIMediaSample@@PAJW4KSIOOPERATION@@PAPAU_KSSTREAM_SEGMENT@@@Z`
- size: `555`
- prototype: `int(CFormatChangeHandler *__hidden this, struct IKsDataTypeHandler *, struct IMediaSample **, int *, enum KSIOOPERATION, struct _KSSTREAM_SEGMENT **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1000665f`
- `0x10010350`
- `0x1001f6ea`
- `0x1002d510`
- `0x100302a7`
- `0x1003a6fd`
- `0x1003af9d`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100103f9`
- `KERNEL32!GetLastError` at `0x1001053e`
- `KERNEL32!GetLastError` at `0x100103f9`
- `KERNEL32!GetLastError` at `0x1001053e`
- `KERNEL32!SetEvent` at `0x1001055d`
- `KERNEL32!SetEvent` at `0x10010568`
- `KERNEL32!SetEvent` at `0x1001055d`
- `KERNEL32!SetEvent` at `0x10010568`
- `KERNEL32!CreateEventW` at `0x100103ec`
- `KERNEL32!CreateEventW` at `0x100103ec`
- `KERNEL32!DeviceIoControl` at `0x10010534`
- `KERNEL32!DeviceIoControl` at `0x10010534`
- `ole32!CoTaskMemFree` at `0x100103cb`
- `ole32!CoTaskMemFree` at `0x10010439`
- `ole32!CoTaskMemFree` at `0x100103cb`
- `ole32!CoTaskMemFree` at `0x10010439`

## pseudocode

```c
int __userpurge CFormatChangeHandler::KsProcessMediaSamples@<eax>(
        int a1@<ebx>,
        int a2@<edi>,
        CFormatChangeHandler *this,
        struct IKsDataTypeHandler *a4,
        struct IMediaSample **a5,
        int *a6,
        CFormatChangeHandler *a7,
        CFormatChangeHandler ***a8)
{
  int result; // eax
  int v9; // esi
  CFormatChangeHandler **v10; // eax
  CFormatChangeHandler **v11; // edi
  CFormatChangeHandler *EventW; // eax
  signed int LastError; // eax
  unsigned int v14; // esi
  CFormatChangeHandler *v15; // eax
  CFormatChangeHandler *v16; // ecx
  unsigned int v17; // eax
  int v18; // ecx
  signed int v19; // eax
  void *v20; // [esp-Ch] [ebp-30h]
  void *v21; // [esp-Ch] [ebp-30h]
  void **v23; // [esp+0h] [ebp-24h]
  struct _AMMediaType *v24; // [esp+0h] [ebp-24h]
  __int64 v25; // [esp+4h] [ebp-20h] BYREF
  __int64 v26; // [esp+Ch] [ebp-18h] BYREF
  DWORD BytesReturned; // [esp+14h] [ebp-10h] BYREF
  unsigned int v28; // [esp+18h] [ebp-Ch] BYREF
  int v29; // [esp+1Ch] [ebp-8h] BYREF
  LPVOID pv; // [esp+20h] [ebp-4h] BYREF

  result = ((int (__thiscall *)(HRESULT (__stdcall *)(IMediaSample *, _AMMediaType **), _DWORD, int *))(*a5)->GetMediaType)(
             (*a5)->GetMediaType,
             *a5,
             &v29);
  if ( result >= 0 )
  {
    if ( !v29 )
      return 0;
    v9 = InitializeDataFormat((const struct CMediaType *)&pv, (unsigned int)&v28, v23, (unsigned int *)v25);
    DeleteMediaType(v24);
    if ( v9 < 0 )
      return v9;
    *a8 = 0;
    v10 = (CFormatChangeHandler **)operator new(0x60u);
    v11 = v10;
    if ( !v10 )
    {
      v20 = pv;
      *a6 = 0;
      CoTaskMemFree(v20);
      return -2147024882;
    }
    memset(v10, 0, 0x60u);
    EventW = (CFormatChangeHandler *)CreateEventW(0, 1, 0, 0);
    v11[3] = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v14 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v14 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_q(0xAu, &WPP_8fe1a91cda903b952c19ad77e9d7b80c_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v14);
      v21 = pv;
      *a6 = 0;
      CoTaskMemFree(v21);
      operator delete(v11, 0x60u);
      return v14;
    }
    ((void (__thiscall *)(unsigned int (__stdcall *)(struct CFormatChangeHandler *), CFormatChangeHandler *, int, int))this->NonDelegatingAddRef)(
      this->NonDelegatingAddRef,
      this,
      a2,
      a1);
    v15 = this;
    v11[17] = (CFormatChangeHandler *)8;
    v11[6] = (CFormatChangeHandler *)48;
    if ( this == (CFormatChangeHandler *)12 )
      v15 = 0;
    v11[7] = 0;
    *v11 = v15;
    v11[2] = a7;
    if ( !((int (__thiscall *)(HRESULT (__stdcall *)(IMediaSample *, __int64 *, __int64 *), _DWORD, __int64 *, __int64 *))(*a5)->GetTime)(
            (*a5)->GetTime,
            *a5,
            &v26,
            &v25) )
    {
      v11[17] = (CFormatChangeHandler *)((unsigned int)v11[17] | 0x110);
      v16 = (CFormatChangeHandler *)HIDWORD(v26);
      v11[8] = (CFormatChangeHandler *)v26;
      v11[9] = v16;
      v11[10] = (CFormatChangeHandler *)1;
      v11[11] = (CFormatChangeHandler *)1;
      *((_QWORD *)v11 + 6) = v25 - v26;
    }
    v11[16] = (CFormatChangeHandler *)pv;
    v17 = v28;
    v11[14] = (CFormatChangeHandler *)v28;
    v11[15] = (CFormatChangeHandler *)v17;
    v18 = (int)*a5;
    v11[4] = (CFormatChangeHandler *)*a5;
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v18 + 4))(*(_DWORD *)(*(_DWORD *)v18 + 4), v18);
    v11[22] = v11[3];
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *const))this->m_pUnknown->CUnknown::__vftable[4].AddRef)(
      this->m_pUnknown->CUnknown::__vftable[4].AddRef,
      this->m_pUnknown);
    if ( DeviceIoControl(
           (HANDLE)this->m_cRef,
           0x2F8013u,
           0,
           0,
           v11 + 6,
           0x30u,
           &BytesReturned,
           (LPOVERLAPPED)(v11 + 18)) )
    {
      SetEvent(v11[22]);
    }
    else
    {
      v19 = GetLastError();
      v14 = (unsigned __int16)v19 | 0x80070000;
      if ( v19 <= 0 )
        v14 = v19;
      if ( v14 != -2147023899 )
      {
        SetEvent(v11[22]);
LABEL_25:
        *a8 = v11;
        return v14;
      }
    }
    v14 = 0;
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x10010350  mov     edi, edi
0x10010352  push    ebp
0x10010353  mov     ebp, esp
0x10010355  mov     ecx, [ebp+arg_8]
0x10010358  sub     esp, 20h
0x1001035b  mov     ecx, [ecx]
0x1001035d  push    esi; struct _AMMediaType *
0x1001035e  mov     eax, [ecx]
0x10010360  mov     esi, [eax+34h]
0x10010363  lea     eax, [ebp+var_8]
0x10010366  push    eax
0x10010367  push    ecx
0x10010368  mov     ecx, esi; this
0x1001036a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010370  call    esi
0x10010372  test    eax, eax
0x10010374  js      loc_10010576
0x1001037a  mov     ecx, [ebp+var_8]
0x1001037d  test    ecx, ecx
0x1001037f  jnz     short loc_10010388
0x10010381  xor     eax, eax
0x10010383  jmp     loc_10010576
0x10010388  lea     eax, [ebp+var_C]
0x1001038b  xor     edx, edx
0x1001038d  push    eax; unsigned int
0x1001038e  lea     eax, [ebp+pv]
0x10010391  push    eax; struct CMediaType *
0x10010392  call    ?InitializeDataFormat@@YGJPBVCMediaType@@KPAPAXPAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x10010397  mov     ecx, [ebp+var_8]
0x1001039a  mov     esi, eax
0x1001039c  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x100103a1  test    esi, esi
0x100103a3  jns     short loc_100103AC
0x100103a5  mov     eax, esi
0x100103a7  jmp     loc_10010576
0x100103ac  push    ebx
0x100103ad  mov     ebx, [ebp+arg_14]
0x100103b0  xor     esi, esi
0x100103b2  push    edi
0x100103b3  push    60h ; '`'; Size
0x100103b5  mov     [ebx], esi
0x100103b7  call    ??2@YAPAXI@Z; operator new(uint)
0x100103bc  mov     edi, eax
0x100103be  pop     ecx
0x100103bf  test    edi, edi
0x100103c1  jnz     short loc_100103DB
0x100103c3  mov     eax, [ebp+arg_C]
0x100103c6  push    [ebp+pv]; pv
0x100103c9  mov     [eax], esi
0x100103cb  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100103d1  mov     eax, 8007000Eh
0x100103d6  jmp     loc_10010574
0x100103db  push    60h ; '`'; Size
0x100103dd  push    esi; Val
0x100103de  push    edi; void *
0x100103df  call    _memset
0x100103e4  add     esp, 0Ch
0x100103e7  push    esi; lpName
0x100103e8  push    esi; bInitialState
0x100103e9  push    1; bManualReset
0x100103eb  push    esi; lpEventAttributes
0x100103ec  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x100103f2  mov     [edi+0Ch], eax
0x100103f5  test    eax, eax
0x100103f7  jnz     short loc_1001044E
0x100103f9  call    ds:__imp__GetLastError@0; GetLastError()
0x100103ff  movzx   esi, ax
0x10010402  or      esi, 80070000h
0x10010408  test    eax, eax
0x1001040a  cmovle  esi, eax
0x1001040d  mov     eax, _WPP_GLOBAL_Control
0x10010412  cmp     eax, offset _WPP_GLOBAL_Control
0x10010417  jz      short loc_1001042D
0x10010419  push    esi; char
0x1001041a  push    dword ptr [eax+14h]
0x1001041d  mov     edx, offset _WPP_8fe1a91cda903b952c19ad77e9d7b80c_Traceguids; MessageGuid
0x10010422  push    dword ptr [eax+10h]; LoggerHandle
0x10010425  push    0Ah
0x10010427  pop     ecx; MessageNumber
0x10010428  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1001042d  mov     ecx, [ebp+arg_C]
0x10010430  push    [ebp+pv]; pv
0x10010433  mov     dword ptr [ecx], 0
0x10010439  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001043f  push    60h ; '`'; unsigned int
0x10010441  push    edi; Block
0x10010442  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10010447  pop     ecx
0x10010448  pop     ecx
0x10010449  jmp     loc_10010572
0x1001044e  mov     ecx, [ebp+this]
0x10010451  push    ecx
0x10010452  mov     eax, [ecx]
0x10010454  mov     esi, [eax+4]
0x10010457  mov     ecx, esi; this
0x10010459  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001045f  call    esi
0x10010461  mov     eax, [ebp+this]
0x10010464  xor     edx, edx
0x10010466  cmp     eax, 0Ch
0x10010469  mov     dword ptr [edi+44h], 8
0x10010470  mov     dword ptr [edi+18h], 30h ; '0'
0x10010477  cmovz   eax, edx
0x1001047a  mov     [edi+1Ch], edx
0x1001047d  mov     [edi], eax
0x1001047f  mov     eax, [ebp+arg_10]
0x10010482  mov     [edi+8], eax
0x10010485  mov     eax, [ebp+arg_8]
0x10010488  mov     ecx, [eax]
0x1001048a  mov     eax, [ecx]
0x1001048c  mov     esi, [eax+14h]
0x1001048f  lea     eax, [ebp+var_20]
0x10010492  push    eax
0x10010493  lea     eax, [ebp+var_18]
0x10010496  push    eax
0x10010497  push    ecx
0x10010498  mov     ecx, esi; this
0x1001049a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100104a0  call    esi
0x100104a2  test    eax, eax
0x100104a4  jnz     short loc_100104D4
0x100104a6  or      dword ptr [edi+44h], 110h
0x100104ad  mov     eax, dword ptr [ebp+var_18]
0x100104b0  mov     ecx, dword ptr [ebp+var_18+4]
0x100104b3  mov     [edi+20h], eax
0x100104b6  xor     eax, eax
0x100104b8  inc     eax
0x100104b9  mov     [edi+24h], ecx
0x100104bc  mov     [edi+28h], eax
0x100104bf  mov     [edi+2Ch], eax
0x100104c2  mov     ecx, dword ptr [ebp+var_20]
0x100104c5  sub     ecx, dword ptr [ebp+var_18]
0x100104c8  mov     eax, dword ptr [ebp+var_20+4]
0x100104cb  sbb     eax, dword ptr [ebp+var_18+4]
0x100104ce  mov     [edi+30h], ecx
0x100104d1  mov     [edi+34h], eax
0x100104d4  mov     eax, [ebp+pv]
0x100104d7  mov     [edi+40h], eax
0x100104da  mov     eax, [ebp+var_C]
0x100104dd  mov     [edi+38h], eax
0x100104e0  mov     [edi+3Ch], eax
0x100104e3  mov     eax, [ebp+arg_8]
0x100104e6  mov     ecx, [eax]
0x100104e8  mov     [edi+10h], ecx
0x100104eb  push    ecx
0x100104ec  mov     eax, [ecx]
0x100104ee  mov     esi, [eax+4]
0x100104f1  mov     ecx, esi; this
0x100104f3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100104f9  call    esi
0x100104fb  mov     eax, [edi+0Ch]
0x100104fe  mov     [edi+58h], eax
0x10010501  mov     eax, [ebp+this]
0x10010504  mov     eax, [eax+4]
0x10010507  push    eax
0x10010508  mov     ecx, [eax]
0x1001050a  mov     esi, [ecx+34h]
0x1001050d  mov     ecx, esi; this
0x1001050f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010515  call    esi
0x10010517  lea     eax, [edi+48h]
0x1001051a  push    eax; lpOverlapped
0x1001051b  lea     eax, [ebp+BytesReturned]
0x1001051e  push    eax; lpBytesReturned
0x1001051f  push    30h ; '0'; nOutBufferSize
0x10010521  lea     eax, [edi+18h]
0x10010524  push    eax; lpOutBuffer
0x10010525  mov     eax, [ebp+this]
0x10010528  push    0; nInBufferSize
0x1001052a  push    0; lpInBuffer
0x1001052c  push    2F8013h; dwIoControlCode
0x10010531  push    dword ptr [eax+8]; hDevice
0x10010534  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x1001053a  test    eax, eax
0x1001053c  jnz     short loc_10010565
0x1001053e  call    ds:__imp__GetLastError@0; GetLastError()
0x10010544  movzx   esi, ax
0x10010547  or      esi, 80070000h
0x1001054d  test    eax, eax
0x1001054f  cmovle  esi, eax
0x10010552  cmp     esi, 800703E5h
0x10010558  jz      short loc_1001056E
0x1001055a  push    dword ptr [edi+58h]; hEvent
0x1001055d  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10010563  jmp     short loc_10010570
0x10010565  push    dword ptr [edi+58h]; hEvent
0x10010568  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1001056e  xor     esi, esi
0x10010570  mov     [ebx], edi
0x10010572  mov     eax, esi
0x10010574  pop     edi
0x10010575  pop     ebx
0x10010576  pop     esi
0x10010577  leave
0x10010578  retn    18h
```
