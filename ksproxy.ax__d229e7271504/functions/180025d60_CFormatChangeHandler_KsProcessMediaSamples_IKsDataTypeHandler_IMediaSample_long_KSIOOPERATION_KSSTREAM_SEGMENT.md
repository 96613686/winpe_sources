# CFormatChangeHandler::KsProcessMediaSamples(IKsDataTypeHandler *,IMediaSample * *,long *,KSIOOPERATION,_KSSTREAM_SEGMENT * *)

- ea: `0x180025d60`
- end: `0x180026035`
- name: `?KsProcessMediaSamples@CFormatChangeHandler@@UEAAJPEAUIKsDataTypeHandler@@PEAPEAUIMediaSample@@PEAJW4KSIOOPERATION@@PEAPEAU_KSSTREAM_SEGMENT@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(CFormatChangeHandler *__hidden this, struct IKsDataTypeHandler *, struct IMediaSample **, int *, enum KSIOOPERATION, struct _KSSTREAM_SEGMENT **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002b58`
- `0x18001bbf8`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001ffb0`
- `0x180025d60`
- `0x18003e22c`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025e69`
- `KERNEL32!GetLastError` at `0x180025fcf`
- `KERNEL32!GetLastError` at `0x180025e69`
- `KERNEL32!GetLastError` at `0x180025fcf`
- `KERNEL32!SetEvent` at `0x180025ff6`
- `KERNEL32!SetEvent` at `0x180026008`
- `KERNEL32!SetEvent` at `0x180025ff6`
- `KERNEL32!SetEvent` at `0x180026008`
- `KERNEL32!CreateEventW` at `0x180025e54`
- `KERNEL32!CreateEventW` at `0x180025e54`
- `KERNEL32!DeviceIoControl` at `0x180025fbf`
- `KERNEL32!DeviceIoControl` at `0x180025fbf`
- `ole32!CoTaskMemFree` at `0x180025e23`
- `ole32!CoTaskMemFree` at `0x180025eba`
- `ole32!CoTaskMemFree` at `0x180025e23`
- `ole32!CoTaskMemFree` at `0x180025eba`

## pseudocode

```c
__int64 __fastcall CFormatChangeHandler::KsProcessMediaSamples(
        CFormatChangeHandler *this,
        struct IKsDataTypeHandler *a2,
        struct IMediaSample **a3,
        int *a4,
        enum KSIOOPERATION a5,
        struct _KSSTREAM_SEGMENT **a6)
{
  IMediaSample *v7; // rcx
  IMediaSample_vtbl *v10; // rax
  __int64 result; // rax
  unsigned int v12; // ebx
  struct _KSSTREAM_SEGMENT **v13; // rsi
  unsigned __int64 *v14; // rax
  unsigned __int64 *v15; // rdi
  void *v16; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  void *v19; // rcx
  unsigned int v20; // eax
  IMediaSample *v21; // rcx
  signed int v22; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  struct _AMMediaType *v25; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-18h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+B0h] [rbp+40h] BYREF

  v25 = 0;
  v7 = *a3;
  v26 = 0;
  v27 = 0;
  BytesReturned = 0;
  v10 = v7->__vftable;
  pv = 0;
  v28 = 0;
  result = ((__int64 (__fastcall *)(IMediaSample *, struct _AMMediaType **))v10->GetMediaType)(v7, &v25);
  if ( (int)result >= 0 )
  {
    if ( !v25 )
      return 0;
    v12 = InitializeDataFormat((const struct CMediaType *)v25, 0, &pv, &v28);
    DeleteMediaType(v25);
    if ( (v12 & 0x80000000) != 0 )
      return v12;
    v13 = a6;
    *a6 = 0;
    v14 = (unsigned __int64 *)operator new(0x80u);
    v15 = v14;
    if ( !v14 )
    {
      v16 = pv;
      *a4 = 0;
      CoTaskMemFree(v16);
      return 2147942414LL;
    }
    memset_0(v14, 0, 0x80u);
    EventW = CreateEventW(0, 1, 0, 0);
    v15[3] = (unsigned __int64)EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8fe1a91cda903b952c19ad77e9d7b80c_Traceguids, v12);
      v19 = pv;
      *a4 = 0;
      CoTaskMemFree(v19);
      operator delete(v15, 0x80u);
      return v12;
    }
    this->NonDelegatingAddRef(this);
    *((_DWORD *)v15 + 11) = 0;
    *((_DWORD *)v15 + 22) = 8;
    *((_DWORD *)v15 + 10) = 56;
    *((_DWORD *)v15 + 4) = a5;
    *v15 = (unsigned __int64)this & -(__int64)(this != (CFormatChangeHandler *)24);
    if ( !(*a3)->GetTime(*a3, (__int64 *)&v26, &v27) )
    {
      *((_DWORD *)v15 + 22) |= 0x110u;
      v15[6] = v26;
      *((_DWORD *)v15 + 14) = 1;
      *((_DWORD *)v15 + 15) = 1;
      v15[8] = v27 - v26;
    }
    v15[10] = (unsigned __int64)pv;
    v20 = v28;
    *((_DWORD *)v15 + 18) = v28;
    *((_DWORD *)v15 + 19) = v20;
    v21 = *a3;
    v15[4] = (unsigned __int64)*a3;
    v21->AddRef(v21);
    v15[15] = v15[3];
    this->m_pUnknown->CUnknown::__vftable[4].AddRef(this->m_pUnknown);
    if ( DeviceIoControl(
           *(HANDLE *)&this->m_cRef,
           0x2F8013u,
           0,
           0,
           v15 + 5,
           0x38u,
           &BytesReturned,
           (LPOVERLAPPED)v15 + 3) )
    {
      SetEvent((HANDLE)v15[15]);
    }
    else
    {
      v22 = GetLastError();
      v12 = v22;
      if ( v22 > 0 )
        v12 = (unsigned __int16)v22 | 0x80070000;
      if ( v12 != -2147023899 )
      {
        SetEvent((HANDLE)v15[15]);
LABEL_22:
        *v13 = (struct _KSSTREAM_SEGMENT *)v15;
        return v12;
      }
    }
    v12 = 0;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x180025d60  mov     [rsp-28h+arg_0], rbx
0x180025d65  mov     [rsp-28h+arg_8], rsi
0x180025d6a  push    rbp
0x180025d6b  push    rdi
0x180025d6c  push    r12
0x180025d6e  push    r14
0x180025d70  push    r15
0x180025d72  mov     rbp, rsp
0x180025d75  sub     rsp, 70h
0x180025d79  mov     r15, rcx
0x180025d7c  mov     [rbp+var_20], 0
0x180025d84  mov     rcx, [r8]
0x180025d87  lea     rdx, [rbp+var_20]
0x180025d8b  mov     [rbp+var_18], 0
0x180025d93  mov     r14, r9
0x180025d96  mov     [rbp+var_10], 0
0x180025d9e  mov     r12, r8
0x180025da1  mov     [rbp+BytesReturned], 0
0x180025da8  mov     rax, [rcx]
0x180025dab  mov     [rbp+pv], 0
0x180025db3  mov     [rbp+arg_10], 0
0x180025dba  mov     rax, [rax+68h]
0x180025dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dc3  test    eax, eax
0x180025dc5  js      loc_18002601B
0x180025dcb  mov     rcx, [rbp+var_20]; struct CMediaType *
0x180025dcf  test    rcx, rcx
0x180025dd2  jnz     short loc_180025DDB
0x180025dd4  xor     eax, eax
0x180025dd6  jmp     loc_18002601B
0x180025ddb  lea     r9, [rbp+arg_10]; unsigned int *
0x180025ddf  xor     edx, edx; unsigned int
0x180025de1  lea     r8, [rbp+pv]; void **
0x180025de5  call    ?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z; InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)
0x180025dea  mov     rcx, [rbp+var_20]; pv
0x180025dee  mov     ebx, eax
0x180025df0  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180025df5  test    ebx, ebx
0x180025df7  js      loc_180026019
0x180025dfd  mov     rsi, [rbp+arg_28]
0x180025e01  mov     ebx, 80h
0x180025e06  mov     ecx, ebx; Size
0x180025e08  mov     qword ptr [rsi], 0
0x180025e0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025e14  mov     rdi, rax
0x180025e17  test    rax, rax
0x180025e1a  jnz     short loc_180025E39
0x180025e1c  mov     rcx, [rbp+pv]; pv
0x180025e20  mov     [r14], eax
0x180025e23  call    cs:__imp_CoTaskMemFree
0x180025e2a  nop     dword ptr [rax+rax+00h]
0x180025e2f  mov     eax, 8007000Eh
0x180025e34  jmp     loc_18002601B
0x180025e39  mov     r8, rbx; Size
0x180025e3c  xor     edx, edx; Val
0x180025e3e  mov     rcx, rdi; void *
0x180025e41  call    memset_0
0x180025e46  xor     r9d, r9d; lpName
0x180025e49  xor     r8d, r8d; bInitialState
0x180025e4c  xor     ecx, ecx; lpEventAttributes
0x180025e4e  lea     ebx, [r9+1]
0x180025e52  mov     edx, ebx; bManualReset
0x180025e54  call    cs:__imp_CreateEventW
0x180025e5b  nop     dword ptr [rax+rax+00h]
0x180025e60  mov     [rdi+18h], rax
0x180025e64  test    rax, rax
0x180025e67  jnz     short loc_180025ED8
0x180025e69  call    cs:__imp_GetLastError
0x180025e70  nop     dword ptr [rax+rax+00h]
0x180025e75  mov     ebx, eax
0x180025e77  test    eax, eax
0x180025e79  jle     short loc_180025E84
0x180025e7b  movzx   ebx, ax
0x180025e7e  or      ebx, 80070000h
0x180025e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e8b  lea     rax, WPP_GLOBAL_Control
0x180025e92  cmp     rcx, rax
0x180025e95  jz      short loc_180025EAF
0x180025e97  mov     rcx, [rcx+10h]
0x180025e9b  lea     r8, WPP_8fe1a91cda903b952c19ad77e9d7b80c_Traceguids
0x180025ea2  mov     edx, 0Ah
0x180025ea7  mov     r9d, ebx
0x180025eaa  call    WPP_SF_d
0x180025eaf  mov     rcx, [rbp+pv]; pv
0x180025eb3  mov     dword ptr [r14], 0
0x180025eba  call    cs:__imp_CoTaskMemFree
0x180025ec1  nop     dword ptr [rax+rax+00h]
0x180025ec6  mov     edx, 80h; unsigned __int64
0x180025ecb  mov     rcx, rdi; void *
0x180025ece  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025ed3  jmp     loc_180026019
0x180025ed8  mov     rax, [r15]
0x180025edb  mov     rcx, r15
0x180025ede  mov     rax, [rax+8]
0x180025ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ee7  mov     dword ptr [rdi+2Ch], 0
0x180025eee  lea     r14, [rdi+28h]
0x180025ef2  mov     dword ptr [r14+30h], 8
0x180025efa  lea     rax, [r15-18h]
0x180025efe  neg     rax
0x180025f01  mov     dword ptr [r14], 38h ; '8'
0x180025f08  mov     eax, [rbp+arg_20]
0x180025f0b  lea     r8, [rbp+var_10]
0x180025f0f  mov     [rdi+10h], eax
0x180025f12  lea     rdx, [rbp+var_18]
0x180025f16  sbb     rcx, rcx
0x180025f19  and     rcx, r15
0x180025f1c  mov     [rdi], rcx
0x180025f1f  mov     rcx, [r12]
0x180025f23  mov     rax, [rcx]
0x180025f26  mov     rax, [rax+28h]
0x180025f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f2f  test    eax, eax
0x180025f31  jnz     short loc_180025F54
0x180025f33  or      dword ptr [rdi+58h], 110h
0x180025f3a  mov     rax, [rbp+var_18]
0x180025f3e  mov     [rdi+30h], rax
0x180025f42  mov     [rdi+38h], ebx
0x180025f45  mov     [rdi+3Ch], ebx
0x180025f48  mov     rax, [rbp+var_10]
0x180025f4c  sub     rax, [rbp+var_18]
0x180025f50  mov     [rdi+40h], rax
0x180025f54  mov     rax, [rbp+pv]
0x180025f58  mov     [rdi+50h], rax
0x180025f5c  mov     eax, [rbp+arg_10]
0x180025f5f  mov     [rdi+48h], eax
0x180025f62  mov     [rdi+4Ch], eax
0x180025f65  mov     rcx, [r12]
0x180025f69  mov     [rdi+20h], rcx
0x180025f6d  mov     rax, [rcx]
0x180025f70  mov     rax, [rax+8]
0x180025f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f79  mov     rax, [rdi+18h]
0x180025f7d  lea     rbx, [rdi+60h]
0x180025f81  mov     [rbx+18h], rax
0x180025f85  mov     rcx, [r15+8]
0x180025f89  mov     rax, [rcx]
0x180025f8c  mov     rax, [rax+68h]
0x180025f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f95  mov     rcx, [r15+10h]; hDevice
0x180025f99  lea     rax, [rbp+BytesReturned]
0x180025f9d  mov     [rsp+70h+lpOverlapped], rbx; lpOverlapped
0x180025fa2  xor     r9d, r9d; nInBufferSize
0x180025fa5  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180025faa  xor     r8d, r8d; lpInBuffer
0x180025fad  mov     [rsp+70h+nOutBufferSize], 38h ; '8'; nOutBufferSize
0x180025fb5  mov     edx, 2F8013h; dwIoControlCode
0x180025fba  mov     [rsp+70h+lpOutBuffer], r14; lpOutBuffer
0x180025fbf  call    cs:__imp_DeviceIoControl
0x180025fc6  nop     dword ptr [rax+rax+00h]
0x180025fcb  test    eax, eax
0x180025fcd  jnz     short loc_180026004
0x180025fcf  call    cs:__imp_GetLastError
0x180025fd6  nop     dword ptr [rax+rax+00h]
0x180025fdb  mov     ebx, eax
0x180025fdd  test    eax, eax
0x180025fdf  jle     short loc_180025FEA
0x180025fe1  movzx   ebx, ax
0x180025fe4  or      ebx, 80070000h
0x180025fea  cmp     ebx, 800703E5h
0x180025ff0  jz      short loc_180026014
0x180025ff2  mov     rcx, [rdi+78h]; hEvent
0x180025ff6  call    cs:__imp_SetEvent
0x180025ffd  nop     dword ptr [rax+rax+00h]
0x180026002  jmp     short loc_180026016
0x180026004  mov     rcx, [rdi+78h]; hEvent
0x180026008  call    cs:__imp_SetEvent
0x18002600f  nop     dword ptr [rax+rax+00h]
0x180026014  xor     ebx, ebx
0x180026016  mov     [rsi], rdi
0x180026019  mov     eax, ebx
0x18002601b  lea     r11, [rsp+70h+var_s0]
0x180026020  mov     rbx, [r11+30h]
0x180026024  mov     rsi, [r11+38h]
0x180026028  mov     rsp, r11
0x18002602b  pop     r15
0x18002602d  pop     r14
0x18002602f  pop     r12
0x180026031  pop     rdi
0x180026032  pop     rbp
0x180026033  retn
```
