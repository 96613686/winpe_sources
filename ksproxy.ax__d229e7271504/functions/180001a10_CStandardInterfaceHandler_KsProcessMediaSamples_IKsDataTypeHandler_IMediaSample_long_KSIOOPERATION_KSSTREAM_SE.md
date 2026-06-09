# CStandardInterfaceHandler::KsProcessMediaSamples(IKsDataTypeHandler *,IMediaSample * *,long *,KSIOOPERATION,_KSSTREAM_SEGMENT * *)

- ea: `0x180001a10`
- end: `0x18000219b`
- name: `?KsProcessMediaSamples@CStandardInterfaceHandler@@UEAAJPEAUIKsDataTypeHandler@@PEAPEAUIMediaSample@@PEAJW4KSIOOPERATION@@PEAPEAU_KSSTREAM_SEGMENT@@@Z`
- size: `1931`
- prototype: `__int64 __fastcall(CStandardInterfaceHandler *this, CStandardInterfaceHandler *, struct IMediaSample **, int *, enum KSIOOPERATION, struct _KSSTREAM_SEGMENT **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001a10`
- `0x1800021a4`
- `0x180002b58`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f210`
- `0x18001ffb0`
- `0x180025860`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001c33`
- `KERNEL32!GetLastError` at `0x180001eb2`
- `KERNEL32!GetLastError` at `0x180001c33`
- `KERNEL32!GetLastError` at `0x180001eb2`
- `KERNEL32!SetEvent` at `0x180001de3`
- `KERNEL32!SetEvent` at `0x18000218a`
- `KERNEL32!SetEvent` at `0x180001de3`
- `KERNEL32!SetEvent` at `0x18000218a`
- `KERNEL32!CreateEventW` at `0x180001a8b`
- `KERNEL32!CreateEventW` at `0x180001a8b`
- `KERNEL32!CloseHandle` at `0x180001b5a`
- `KERNEL32!CloseHandle` at `0x180001e8a`
- `KERNEL32!CloseHandle` at `0x180001b5a`
- `KERNEL32!CloseHandle` at `0x180001e8a`
- `KERNEL32!DeviceIoControl` at `0x180001c1f`
- `KERNEL32!DeviceIoControl` at `0x180001c1f`

## pseudocode

```c
__int64 __fastcall CStandardInterfaceHandler::KsProcessMediaSamples(
        CStandardInterfaceHandler *this,
        CStandardInterfaceHandler *a2,
        struct IMediaSample **a3,
        int *a4,
        enum KSIOOPERATION a5,
        struct _KSSTREAM_SEGMENT **a6)
{
  struct _KSSTREAM_SEGMENT **v6; // r13
  CStandardInterfaceHandler **v10; // rax
  CStandardInterfaceHandler **v11; // rbx
  CStandardInterfaceHandler *EventW; // rax
  CStandardInterfaceHandler *v13; // rdx
  unsigned int *v14; // r15
  int v15; // ecx
  unsigned __int64 nOutBufferSize; // r12
  CStandardInterfaceHandler *v17; // rax
  CStandardInterfaceHandler *v18; // rcx
  __int64 result; // rax
  CStandardInterfaceHandler *v20; // rdi
  int i; // eax
  DWORD v22; // edx
  signed int v23; // eax
  unsigned int v24; // edi
  bool v25; // zf
  struct _KSSTREAM_SEGMENT **v26; // r10
  unsigned int v27; // ecx
  __int64 v28; // rax
  int v29; // edx
  struct IMediaSample **v30; // rcx
  struct IMediaSample *v31; // rcx
  struct IMediaSample *v32; // rcx
  CStandardInterfaceHandler *v33; // rcx
  signed int LastError; // eax
  unsigned int v35; // edi
  int v36; // ecx
  int v37; // eax
  struct VRAM_SURFACE_INFO *v38; // rax
  __int64 v39; // rdi
  __int64 v40; // r12
  CStandardInterfaceHandler *v41; // rcx
  __int64 v42; // rdi
  __int64 j; // r12
  int v44; // [rsp+40h] [rbp-49h]
  struct VRAM_SURFACE_INFO *v45; // [rsp+48h] [rbp-41h] BYREF
  __int128 v46; // [rsp+50h] [rbp-39h] BYREF
  __int128 v47; // [rsp+60h] [rbp-29h] BYREF
  __int128 v48; // [rsp+70h] [rbp-19h]
  __int128 v49; // [rsp+80h] [rbp-9h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+7h] BYREF
  struct IMediaSample **v51; // [rsp+98h] [rbp+Fh]
  __int64 v52; // [rsp+A0h] [rbp+17h]

  v6 = a6;
  BytesReturned = 0;
  *a6 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v10 = (CStandardInterfaceHandler **)operator new(0x250u);
  v11 = v10;
  if ( !v10 )
  {
    *a4 = 0;
    return 2147942414LL;
  }
  if ( *a4 > 64 )
  {
    *a4 = 0;
    operator delete(v10, 0x250u);
    return 2147942487LL;
  }
  EventW = (CStandardInterfaceHandler *)CreateEventW(0, 1, 0, 0);
  v11[3] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v35 = LastError;
    if ( LastError > 0 )
      v35 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids, v35);
    *a4 = 0;
    operator delete(v11, 0x250u);
    return v35;
  }
  this->NonDelegatingAddRef(this);
  v11[1] = a2;
  v13 = this;
  *((_DWORD *)v11 + 4) = a5;
  if ( this == (CStandardInterfaceHandler *)24 )
    v13 = 0;
  v14 = (unsigned int *)v11 + 137;
  *v11 = v13;
  if ( a2 )
  {
    ((void (__fastcall *)(CStandardInterfaceHandler *, char *))a2->CUnknown::INonDelegatingUnknown::__vftable[1].NonDelegatingRelease)(
      a2,
      (char *)v11 + 548);
    if ( *v14 )
    {
      v11[1]->NonDelegatingAddRef(v11[1]);
      v15 = *v14;
    }
    else
    {
      v11[1] = 0;
      v15 = 0;
    }
  }
  else
  {
    *v14 = 0;
    v15 = 0;
  }
  *((_DWORD *)v11 + 136) = *a4;
  nOutBufferSize = (unsigned int)(*a4 * (v15 + 56));
  v17 = (CStandardInterfaceHandler *)operator new[](nOutBufferSize);
  v11[69] = v17;
  if ( !v17 )
  {
    v18 = v11[1];
    if ( v18 )
      v18->NonDelegatingRelease(v18);
    this->NonDelegatingRelease(this);
    CloseHandle(v11[3]);
    operator delete(v11, 0x250u);
    result = 2147942414LL;
    *a4 = 0;
    return result;
  }
  memset_0(v17, 0, nOutBufferSize);
  v20 = v11[69];
  for ( i = 0; ; i = v44 + 1 )
  {
    v44 = i;
    if ( i >= *a4 )
    {
      v11[73] = v11[3];
      (*((void (__fastcall **)(IKsInterfaceHandler_vtbl *))this->QueryInterface + 13))(this->IKsInterfaceHandler::IUnknown::__vftable);
      v22 = 3112979;
      if ( a5 )
        v22 = 3096599;
      if ( DeviceIoControl(
             *(HANDLE *)&this->m_ClsID.Data1,
             v22,
             0,
             0,
             v11[69],
             nOutBufferSize,
             &BytesReturned,
             (LPOVERLAPPED)(v11 + 70)) )
      {
        SetEvent(v11[73]);
      }
      else
      {
        v23 = GetLastError();
        v24 = v23;
        if ( v23 > 0 )
          v24 = (unsigned __int16)v23 | 0x80070000;
        if ( v24 != -2147023899 )
        {
          SetEvent(v11[73]);
          goto LABEL_22;
        }
      }
      v24 = 0;
LABEL_22:
      *v6 = (struct _KSSTREAM_SEGMENT *)v11;
      return v24;
    }
    v25 = *v14 == 0;
    v52 = i;
    v26 = (struct _KSSTREAM_SEGMENT **)(8LL * i);
    a6 = v26;
    if ( !v25 )
    {
      ((void (__fastcall *)(CStandardInterfaceHandler *, _QWORD, CStandardInterfaceHandler *, _QWORD))v11[1]->CUnknown::INonDelegatingUnknown::__vftable[1].NonDelegatingAddRef)(
        v11[1],
        *(struct IMediaSample **)((char *)a3 + (_QWORD)v26),
        v20,
        *((unsigned int *)v11 + 4));
      v26 = a6;
    }
    v45 = 0;
    v51 = (struct IMediaSample **)((char *)a3 + (_QWORD)v26);
    a6 = *(struct _KSSTREAM_SEGMENT ***)((char *)a3 + (_QWORD)v26);
    if ( ((__int64 (__fastcall *)(struct _KSSTREAM_SEGMENT **, GUID *, struct VRAM_SURFACE_INFO **))(*a6)->KsInterfaceHandler)(
           a6,
           &GUID_36b73884_c2c8_11cf_8b46_00805f6cef60,
           &v45) >= 0 )
      break;
    *(_QWORD *)&v46 = 64;
    LODWORD(v48) = 0;
    DWORD2(v46) = 0;
    if ( !((unsigned int (__fastcall *)(struct _KSSTREAM_SEGMENT **))(*a6)[3].CompletionEvent)(a6) )
      DWORD2(v46) |= 4u;
    if ( !((unsigned int (__fastcall *)(struct _KSSTREAM_SEGMENT **))(*a6)[2].KsDataTypeHandler)(a6) )
      DWORD2(v46) |= 2u;
    if ( !((unsigned int (__fastcall *)(struct _KSSTREAM_SEGMENT **))(*a6)[1].CompletionEvent)(a6) )
      DWORD2(v46) |= 1u;
    if ( ((int (__fastcall *)(struct _KSSTREAM_SEGMENT **, __int128 *, char *))(*a6)[1].KsDataTypeHandler)(
           a6,
           &v47,
           (char *)&v47 + 8) < 0 )
    {
      v47 = 0;
    }
    else
    {
      v36 = DWORD2(v46) | 0x10;
      DWORD2(v46) |= 0x10u;
      if ( *((_QWORD *)&v47 + 1) != (_QWORD)v47 )
        DWORD2(v46) = v36 | 0x100;
    }
    ((void (__fastcall *)(struct _KSSTREAM_SEGMENT **, __int128 *))(*a6)->CompletionEvent)(a6, &v49);
    HIDWORD(v46) = ((__int64 (__fastcall *)(struct _KSSTREAM_SEGMENT **))(*a6)[2].CompletionEvent)(a6);
    v37 = ((__int64 (__fastcall *)(struct _KSSTREAM_SEGMENT **))(*a6)[1].KsInterfaceHandler)(a6);
    v27 = DWORD2(v46);
    DWORD2(v49) = v37;
LABEL_31:
    LODWORD(v20->m_KsPinEx) = v27;
    v30 = v51;
    LODWORD(v20->CUnknown::INonDelegatingUnknown::__vftable) = *v14 + 56;
    HIDWORD(v20->CUnknown::INonDelegatingUnknown::__vftable) = DWORD1(v46);
    v20->m_pUnknown = (IUnknown *const)v47;
    v20->m_cRef = 1;
    *((_DWORD *)&v20->m_cRef + 1) = 1;
    v20->IKsInterfaceHandler::IUnknown::__vftable = (IKsInterfaceHandler_vtbl *)(*((_QWORD *)&v47 + 1) - v47);
    *(_QWORD *)v20->m_ClsID.Data4 = v49;
    v20->m_ClsID.Data1 = DWORD2(v49);
    v31 = *v30;
    a6 = 0;
    if ( v31->QueryInterface(v31, &GUID_68961e68_832b_41ea_bc91_63593f3e70e3, (void **)&a6) >= 0 )
    {
      if ( a6 )
        (*(void (__fastcall **)(struct _KSSTREAM_SEGMENT **))&(*a6)->IoOperation)(a6);
      v45 = 0;
      LODWORD(a6) = GetVramSurfaceInfo(*v51, &v45);
      if ( (int)a6 < 0 )
      {
        if ( v44 )
        {
          v42 = (__int64)v20 - 56 - *v14;
          for ( j = (unsigned int)(v44 - 1); (int)j >= 0; j = (unsigned int)(j - 1) )
          {
            ((void (__fastcall *)(CStandardInterfaceHandler *, CStandardInterfaceHandler *, __int64, _QWORD, int))v11[1]->~CStandardInterfaceHandler)(
              v11[1],
              v11[j + 4],
              v42,
              *((unsigned int *)v11 + 4),
              1);
            v42 += -56LL - *v14;
          }
        }
        operator delete(v11[69], 0x38u);
        v33 = v11[1];
        if ( v33 )
          v33->NonDelegatingRelease(v33);
        goto LABEL_46;
      }
      v38 = v45;
      LODWORD(v20->m_KsPinEx) |= 0xC00u;
      *(_QWORD *)v20->m_ClsID.Data4 = v38;
      v20->m_ClsID.Data1 = 168;
    }
    if ( a5 == KsIoOperation_Write )
      *(_DWORD *)&v20->m_ClsID.Data2 = HIDWORD(v46);
    v32 = *v51;
    v11[v52 + 4] = (CStandardInterfaceHandler *)*v51;
    if ( !*((_DWORD *)v11 + 4) )
      v32->AddRef(v32);
    v20 = (CStandardInterfaceHandler *)((char *)v20 + *v14 + 56);
  }
  LODWORD(a6) = (*(__int64 (__fastcall **)(struct VRAM_SURFACE_INFO *, __int64, __int128 *))(v45->hSurface + 152))(
                  v45,
                  64,
                  &v46);
  (*(void (__fastcall **)(struct VRAM_SURFACE_INFO *))(v45->hSurface + 16))(v45);
  v27 = DWORD2(v46) & 0xFFFFFFF7;
  DWORD2(v46) = v27;
  if ( (v27 & 0x10) != 0 )
  {
    v28 = v47;
  }
  else
  {
    v28 = 0;
    *(_QWORD *)&v47 = 0;
  }
  if ( (v27 & 0x100) == 0 )
    *((_QWORD *)&v47 + 1) = v28;
  v29 = (int)a6;
  if ( (int)a6 >= 0 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids);
    v29 = (int)a6;
  }
  if ( v44 && (v39 = (__int64)v20 - 56 - *v14, v40 = (unsigned int)(v44 - 1), (int)v40 >= 0) )
  {
    do
    {
      ((void (__fastcall *)(CStandardInterfaceHandler *, CStandardInterfaceHandler *, __int64, _QWORD, int))v11[1]->~CStandardInterfaceHandler)(
        v11[1],
        v11[v40 + 4],
        v39,
        *((unsigned int *)v11 + 4),
        1);
      v39 += -56LL - *v14;
      v40 = (unsigned int)(v40 - 1);
    }
    while ( (int)v40 >= 0 );
  }
  else
  {
    LODWORD(a6) = v29;
  }
  operator delete(v11[69], 0x38u);
  v41 = v11[1];
  if ( v41 )
    v41->NonDelegatingRelease(v41);
LABEL_46:
  this->NonDelegatingRelease(this);
  CloseHandle(v11[3]);
  operator delete(v11, 0x250u);
  result = (unsigned int)a6;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x180001a10  mov     [rsp-8+arg_8], rbx
0x180001a15  mov     [rsp-8+arg_18], rsi
0x180001a1a  mov     [rsp-8+arg_10], r8
0x180001a1f  push    rbp
0x180001a20  push    rdi
0x180001a21  push    r12
0x180001a23  push    r13
0x180001a25  push    r14
0x180001a27  lea     rbp, [rsp-27h]
0x180001a2c  sub     rsp, 0B0h
0x180001a33  mov     r13, [rbp+47h+arg_28]
0x180001a37  xorps   xmm0, xmm0
0x180001a3a  mov     rsi, rcx
0x180001a3d  xor     r12d, r12d
0x180001a40  mov     ecx, 250h; Size
0x180001a45  mov     [rbp+47h+BytesReturned], r12d
0x180001a49  mov     r14, r9
0x180001a4c  mov     rdi, rdx
0x180001a4f  mov     [r13+0], r12
0x180001a53  movups  [rbp+47h+var_80], xmm0
0x180001a57  movups  [rbp+47h+var_70], xmm0
0x180001a5b  movups  [rbp+47h+var_60], xmm0
0x180001a5f  movups  [rbp+47h+var_50], xmm0
0x180001a63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a68  mov     rbx, rax
0x180001a6b  test    rax, rax
0x180001a6e  jz      loc_180001DFF
0x180001a74  cmp     dword ptr [r14], 40h ; '@'
0x180001a78  jg      loc_180001F0F
0x180001a7e  xor     r9d, r9d; lpName
0x180001a81  xor     r8d, r8d; bInitialState
0x180001a84  mov     edx, 1; bManualReset
0x180001a89  xor     ecx, ecx; lpEventAttributes
0x180001a8b  call    cs:__imp_CreateEventW
0x180001a92  nop     dword ptr [rax+rax+00h]
0x180001a97  mov     [rbx+18h], rax
0x180001a9b  test    rax, rax
0x180001a9e  jz      loc_180001EB2
0x180001aa4  mov     rax, [rsi]
0x180001aa7  mov     rcx, rsi
0x180001aaa  mov     [rsp+0D0h+arg_0], r15
0x180001ab2  mov     rax, [rax+8]
0x180001ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001abb  mov     eax, [rbp+47h+arg_20]
0x180001abe  lea     rcx, [rsi-18h]
0x180001ac2  test    rcx, rcx
0x180001ac5  mov     [rbx+8], rdi
0x180001ac9  mov     rdx, rsi
0x180001acc  mov     [rbx+10h], eax
0x180001acf  cmovz   rdx, r12
0x180001ad3  lea     r15, [rbx+224h]
0x180001ada  mov     [rbx], rdx
0x180001add  test    rdi, rdi
0x180001ae0  jz      loc_180001DF4
0x180001ae6  mov     rax, [rdi]
0x180001ae9  mov     rdx, r15
0x180001aec  mov     rcx, rdi
0x180001aef  mov     rax, [rax+30h]
0x180001af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af8  cmp     [r15], r12d
0x180001afb  jz      loc_180001E0C
0x180001b01  mov     rcx, [rbx+8]
0x180001b05  mov     rax, [rcx]
0x180001b08  mov     rax, [rax+8]
0x180001b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b11  mov     ecx, [r15]
0x180001b14  mov     eax, [r14]
0x180001b17  mov     [rbx+220h], eax
0x180001b1d  lea     eax, [rcx+38h]
0x180001b20  imul    eax, [r14]
0x180001b24  mov     ecx, eax; unsigned __int64
0x180001b26  mov     r12d, eax
0x180001b29  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001b2e  mov     [rbx+228h], rax
0x180001b35  test    rax, rax
0x180001b38  jnz     short loc_180001BA4
0x180001b3a  mov     rcx, [rbx+8]
0x180001b3e  test    rcx, rcx
0x180001b41  jnz     loc_180001F29
0x180001b47  mov     rax, [rsi]
0x180001b4a  mov     rcx, rsi
0x180001b4d  mov     rax, [rax+10h]
0x180001b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b56  mov     rcx, [rbx+18h]; hObject
0x180001b5a  call    cs:__imp_CloseHandle
0x180001b61  nop     dword ptr [rax+rax+00h]
0x180001b66  mov     edx, 250h; unsigned __int64
0x180001b6b  mov     rcx, rbx; void *
0x180001b6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001b73  mov     eax, 8007000Eh
0x180001b78  mov     dword ptr [r14], 0
0x180001b7f  mov     r15, [rsp+0D0h+arg_0]
0x180001b87  lea     r11, [rsp+0D0h+var_20]
0x180001b8f  mov     rbx, [r11+38h]
0x180001b93  mov     rsi, [r11+48h]
0x180001b97  mov     rsp, r11
0x180001b9a  pop     r14
0x180001b9c  pop     r13
0x180001b9e  pop     r12
0x180001ba0  pop     rdi
0x180001ba1  pop     rbp
0x180001ba2  retn
0x180001ba4  mov     r8, r12; Size
0x180001ba7  xor     edx, edx; Val
0x180001ba9  mov     rcx, rax; void *
0x180001bac  call    memset_0
0x180001bb1  mov     rdi, [rbx+228h]
0x180001bb8  xor     eax, eax
0x180001bba  mov     [rbp+47h+var_90], eax
0x180001bbd  cmp     eax, [r14]
0x180001bc0  jl      loc_180001C67
0x180001bc6  mov     rax, [rbx+18h]
0x180001bca  lea     rdi, [rbx+230h]
0x180001bd1  mov     [rdi+18h], rax
0x180001bd5  mov     rcx, [rsi+18h]
0x180001bd9  mov     rax, [rcx]
0x180001bdc  mov     rax, [rax+68h]
0x180001be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be5  cmp     [rbp+47h+arg_20], 0
0x180001be9  mov     edx, 2F8013h
0x180001bee  mov     rcx, [rsi+20h]; hDevice
0x180001bf2  mov     eax, 2F4017h
0x180001bf7  cmovnz  edx, eax; dwIoControlCode
0x180001bfa  mov     [rsp+0D0h+lpOverlapped], rdi; lpOverlapped
0x180001bff  lea     rax, [rbp+47h+BytesReturned]
0x180001c03  xor     r9d, r9d; nInBufferSize
0x180001c06  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180001c0b  xor     r8d, r8d; lpInBuffer
0x180001c0e  mov     rax, [rbx+228h]
0x180001c15  mov     [rsp+0D0h+nOutBufferSize], r12d; nOutBufferSize
0x180001c1a  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x180001c1f  call    cs:__imp_DeviceIoControl
0x180001c26  nop     dword ptr [rax+rax+00h]
0x180001c2b  test    eax, eax
0x180001c2d  jnz     loc_180001DDC
0x180001c33  call    cs:__imp_GetLastError
0x180001c3a  nop     dword ptr [rax+rax+00h]
0x180001c3f  mov     edi, eax
0x180001c41  test    eax, eax
0x180001c43  jle     short loc_180001C4E
0x180001c45  movzx   edi, ax
0x180001c48  or      edi, 80070000h
0x180001c4e  cmp     edi, 800703E5h
0x180001c54  jnz     loc_180002183
0x180001c5a  xor     edi, edi
0x180001c5c  mov     [r13+0], rbx
0x180001c60  mov     eax, edi
0x180001c62  jmp     loc_180001B7F
0x180001c67  cmp     dword ptr [r15], 0
0x180001c6b  cdqe
0x180001c6d  mov     [rbp+47h+var_30], rax
0x180001c71  lea     r10, ds:0[rax*8]
0x180001c79  mov     [rbp+47h+arg_28], r10
0x180001c7d  jz      short loc_180001CA2
0x180001c7f  mov     rcx, [rbx+8]
0x180001c83  mov     r8, rdi
0x180001c86  mov     rdx, [rbp+47h+arg_10]
0x180001c8a  mov     r9d, [rbx+10h]
0x180001c8e  mov     rax, [rcx]
0x180001c91  mov     rdx, [r10+rdx]
0x180001c95  mov     rax, [rax+28h]
0x180001c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9e  mov     r10, [rbp+47h+arg_28]
0x180001ca2  mov     rax, [rbp+47h+arg_10]
0x180001ca6  lea     r8, [rbp+47h+var_88]
0x180001caa  add     rax, r10
0x180001cad  mov     [rbp+47h+var_88], 0
0x180001cb5  mov     [rbp+47h+var_38], rax
0x180001cb9  lea     rdx, _GUID_36b73884_c2c8_11cf_8b46_00805f6cef60
0x180001cc0  mov     rcx, [rax]
0x180001cc3  mov     [rbp+47h+arg_28], rcx
0x180001cc7  mov     rax, [rcx]
0x180001cca  mov     rax, [rax]
0x180001ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd2  test    eax, eax
0x180001cd4  js      loc_180001F3A
0x180001cda  mov     rcx, [rbp+47h+var_88]
0x180001cde  lea     r8, [rbp+47h+var_80]
0x180001ce2  mov     edx, 40h ; '@'
0x180001ce7  mov     rax, [rcx]
0x180001cea  mov     rax, [rax+98h]
0x180001cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cf6  mov     rcx, [rbp+47h+var_88]
0x180001cfa  mov     dword ptr [rbp+47h+arg_28], eax
0x180001cfd  mov     rax, [rcx]
0x180001d00  mov     rax, [rax+10h]
0x180001d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d09  mov     ecx, dword ptr [rbp+47h+var_80+8]
0x180001d0c  and     ecx, 0FFFFFFF7h
0x180001d0f  mov     dword ptr [rbp+47h+var_80+8], ecx
0x180001d12  test    cl, 10h
0x180001d15  jnz     loc_180001E18
0x180001d1b  xor     eax, eax
0x180001d1d  mov     qword ptr [rbp+47h+var_70], rax
0x180001d21  bt      ecx, 8
0x180001d25  jb      short loc_180001D2B
0x180001d27  mov     qword ptr [rbp+47h+var_70+8], rax
0x180001d2b  mov     edx, dword ptr [rbp+47h+arg_28]
0x180001d2e  test    edx, edx
0x180001d30  js      loc_18000206F
0x180001d36  mov     [rdi+30h], ecx
0x180001d39  lea     r8, [rbp+47h+arg_28]
0x180001d3d  mov     eax, [r15]
0x180001d40  lea     rdx, _GUID_68961e68_832b_41ea_bc91_63593f3e70e3
0x180001d47  mov     rcx, [rbp+47h+var_38]
0x180001d4b  add     eax, 38h ; '8'
0x180001d4e  mov     [rdi], eax
0x180001d50  mov     eax, dword ptr [rbp+47h+var_80+4]
0x180001d53  mov     [rdi+4], eax
0x180001d56  mov     rax, qword ptr [rbp+47h+var_70]
0x180001d5a  mov     [rdi+8], rax
0x180001d5e  mov     dword ptr [rdi+10h], 1
0x180001d65  mov     dword ptr [rdi+14h], 1
0x180001d6c  mov     rax, qword ptr [rbp+47h+var_70+8]
0x180001d70  sub     rax, qword ptr [rbp+47h+var_70]
0x180001d74  mov     [rdi+18h], rax
0x180001d78  mov     rax, qword ptr [rbp+47h+var_50]
0x180001d7c  mov     [rdi+28h], rax
0x180001d80  mov     eax, dword ptr [rbp+47h+var_50+8]
0x180001d83  mov     [rdi+20h], eax
0x180001d86  mov     rcx, [rcx]
0x180001d89  mov     [rbp+47h+arg_28], 0
0x180001d91  mov     rax, [rcx]
0x180001d94  mov     rax, [rax]
0x180001d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d9c  test    eax, eax
0x180001d9e  jns     loc_18000201A
0x180001da4  cmp     [rbp+47h+arg_20], 0
0x180001da8  jz      loc_180002053
0x180001dae  mov     rax, [rbp+47h+var_38]
0x180001db2  mov     rcx, [rax]
0x180001db5  mov     rax, [rbp+47h+var_30]
0x180001db9  mov     [rbx+rax*8+20h], rcx
0x180001dbe  cmp     dword ptr [rbx+10h], 0
0x180001dc2  jz      loc_18000205E
0x180001dc8  mov     eax, [r15]
0x180001dcb  add     rax, 38h ; '8'
0x180001dcf  add     rdi, rax
0x180001dd2  mov     eax, [rbp+47h+var_90]
0x180001dd5  inc     eax
0x180001dd7  jmp     loc_180001BBA
0x180001ddc  mov     rcx, [rbx+248h]; hEvent
0x180001de3  call    cs:__imp_SetEvent
0x180001dea  nop     dword ptr [rax+rax+00h]
0x180001def  jmp     loc_180001C5A
0x180001df4  mov     [r15], r12d
0x180001df7  mov     ecx, r12d
0x180001dfa  jmp     loc_180001B14
0x180001dff  mov     [r14], r12d
0x180001e02  mov     eax, 8007000Eh
0x180001e07  jmp     loc_180001B87
0x180001e0c  mov     [rbx+8], r12
0x180001e10  mov     ecx, r12d
0x180001e13  jmp     loc_180001B14
0x180001e18  mov     rax, qword ptr [rbp+47h+var_70]
0x180001e1c  jmp     loc_180001D21
0x180001e21  mov     rax, [rbp+47h+var_38]
0x180001e25  lea     rdx, [rbp+47h+var_88]; struct VRAM_SURFACE_INFO **
0x180001e29  mov     [rbp+47h+var_88], 0
0x180001e31  mov     rcx, [rax]; struct IMediaSample *
0x180001e34  call    ?GetVramSurfaceInfo@@YAJPEAUIMediaSample@@PEAPEAUVRAM_SURFACE_INFO@@@Z; GetVramSurfaceInfo(IMediaSample *,VRAM_SURFACE_INFO * *)
0x180001e39  mov     dword ptr [rbp+47h+arg_28], eax
0x180001e3c  test    eax, eax
0x180001e3e  jns     loc_180002038
0x180001e44  mov     r12d, [rbp+47h+var_90]
0x180001e48  test    r12d, r12d
0x180001e4b  jnz     loc_18000212A
0x180001e51  mov     rcx, [rbx+228h]; void *
0x180001e58  mov     edx, 38h ; '8'; unsigned __int64
0x180001e5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001e62  mov     rcx, [rbx+8]
0x180001e66  test    rcx, rcx
0x180001e69  jz      short loc_180001E77
0x180001e6b  mov     rax, [rcx]
0x180001e6e  mov     rax, [rax+10h]
0x180001e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e77  mov     rax, [rsi]
0x180001e7a  mov     rax, [rax+10h]
0x180001e7e  mov     rcx, rsi
0x180001e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e86  mov     rcx, [rbx+18h]; hObject
0x180001e8a  call    cs:__imp_CloseHandle
0x180001e91  nop     dword ptr [rax+rax+00h]
0x180001e96  mov     edx, 250h; unsigned __int64
0x180001e9b  mov     rcx, rbx; void *
0x180001e9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001ea3  mov     eax, dword ptr [rbp+47h+arg_28]
0x180001ea6  mov     dword ptr [r14], 0
0x180001ead  jmp     loc_180001B7F
0x180001eb2  call    cs:__imp_GetLastError
0x180001eb9  nop     dword ptr [rax+rax+00h]
0x180001ebe  mov     edi, eax
0x180001ec0  test    eax, eax
0x180001ec2  jle     short loc_180001ECD
0x180001ec4  movzx   edi, ax
0x180001ec7  or      edi, 80070000h
0x180001ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ed4  lea     rax, WPP_GLOBAL_Control
0x180001edb  cmp     rcx, rax
0x180001ede  jz      short loc_180001EF8
  ... truncated ...
```
