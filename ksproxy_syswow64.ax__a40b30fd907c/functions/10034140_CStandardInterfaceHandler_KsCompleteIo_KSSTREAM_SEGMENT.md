# CStandardInterfaceHandler::KsCompleteIo(_KSSTREAM_SEGMENT *)

- ea: `0x10034140`
- end: `0x100346ed`
- name: `?KsCompleteIo@CStandardInterfaceHandler@@UAGJPAU_KSSTREAM_SEGMENT@@@Z`
- size: `1453`
- prototype: `int(CStandardInterfaceHandler *__hidden this, struct _KSSTREAM_SEGMENT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1000665f`
- `0x1002d510`
- `0x1003396e`
- `0x10034140`
- `0x100346f3`
- `0x10034948`
- `0x100349ae`
- `0x1003a6f2`
- `0x1003af9d`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10034187`
- `KERNEL32!GetLastError` at `0x10034187`
- `KERNEL32!GetOverlappedResult` at `0x1003416f`
- `KERNEL32!GetOverlappedResult` at `0x1003416f`

## pseudocode

```c
int __stdcall CStandardInterfaceHandler::KsCompleteIo(CStandardInterfaceHandler *this, struct _KSSTREAM_SEGMENT *Block)
{
  CStandardInterfaceHandler *v2; // ebx
  char *IoOperation; // esi
  BOOL OverlappedResult; // eax
  bool v5; // cc
  int v6; // ebx
  int v7; // edx
  PVOID *v8; // ecx
  char v9; // al
  unsigned int v10; // eax
  char v11; // al
  unsigned int v12; // eax
  KSIOOPERATION v13; // eax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // ecx
  KSIOOPERATION v15; // ecx
  HRESULT (__stdcall *KsCompleteIoOperation)(IKsDataTypeHandler *, IMediaSample *, void *, KSIOOPERATION, int); // ecx
  HRESULT (__stdcall *KsProcessMediaSamples)(IKsInterfaceHandler *, IKsDataTypeHandler *, IMediaSample **, int *, KSIOOPERATION, _KSSTREAM_SEGMENT **); // ecx
  HRESULT (__stdcall *v18)(IKsInterfaceHandler *, IKsDataTypeHandler *, IMediaSample **, int *, KSIOOPERATION, _KSSTREAM_SEGMENT **); // ecx
  unsigned int (__stdcall *Release)(IUnknown *); // ecx
  bool v20; // zf
  _DWORD *v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // esi
  HRESULT (__stdcall *v24)(IUnknown *, const _GUID *, void **); // ecx
  HRESULT (__stdcall *v25)(IUnknown *, const _GUID *, void **); // ecx
  int v26; // eax
  IKsInterfaceHandler *v27; // ecx
  IKsInterfaceHandler_vtbl *v28; // eax
  _DWORD *v29; // edx
  CD3DSurfaceAllocator *v30; // eax
  int v31; // eax
  CD3DSurfaceAllocator *v32; // eax
  char v33; // al
  CD3DSurfaceAllocator *v34; // edx
  int v35; // eax
  struct IMediaSample *v37; // [esp+5Ch] [ebp-70h]
  char *v38; // [esp+6Ch] [ebp-60h]
  BOOL v39; // [esp+70h] [ebp-5Ch]
  signed int LastError; // [esp+74h] [ebp-58h]
  _DWORD *v41; // [esp+78h] [ebp-54h]
  void *v42; // [esp+78h] [ebp-54h]
  int v43; // [esp+7Ch] [ebp-50h] BYREF
  CD3DSurfaceAllocator *v44; // [esp+80h] [ebp-4Ch]
  int v45; // [esp+84h] [ebp-48h]
  DWORD NumberOfBytesTransferred; // [esp+88h] [ebp-44h] BYREF
  _DWORD v47[2]; // [esp+8Ch] [ebp-40h] BYREF
  unsigned __int64 v48; // [esp+94h] [ebp-38h] BYREF
  _DWORD v49[2]; // [esp+9Ch] [ebp-30h] BYREF
  int v50; // [esp+A4h] [ebp-28h]

  v2 = this;
  IoOperation = (char *)Block[17].IoOperation;
  v38 = IoOperation;
  OverlappedResult = GetOverlappedResult(
                       *(HANDLE *)this->m_ClsID.Data4,
                       (LPOVERLAPPED)&Block[17].CompletionEvent,
                       &NumberOfBytesTransferred,
                       0);
  v39 = OverlappedResult;
  if ( OverlappedResult )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    OverlappedResult = 0;
  }
  v5 = (int)Block[17].KsInterfaceHandler <= 0;
  v45 = 0;
  if ( !v5 )
  {
    v6 = 4;
    while ( OverlappedResult )
    {
LABEL_35:
      v13 = Block[17].IoOperation;
      v44 = (CD3DSurfaceAllocator *)(48 * v45);
      if ( *(_DWORD *)(48 * v45 + v13 + 4) )
      {
        QueryInterface = (&Block->KsInterfaceHandler)[v6]->QueryInterface;
        if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IKsInterfaceHandler *, GUID *, int *))QueryInterface)(
               QueryInterface,
               (&Block->KsInterfaceHandler)[v6],
               &_GUID_36b73884_c2c8_11cf_8b46_00805f6cef60,
               &v43) >= 0 )
        {
          (*(void (__thiscall **)(_DWORD, int, int, _DWORD *))(*(_DWORD *)v43 + 76))(
            *(_DWORD *)(*(_DWORD *)v43 + 76),
            v43,
            12,
            v49);
          v15 = Block[17].IoOperation;
          v49[0] = 12;
          v49[1] = *(_DWORD *)((char *)v44 + v15 + 4);
          v50 |= *(_DWORD *)((_BYTE *)v44 + v15 + 44) & 0x40;
          (*(void (__thiscall **)(_DWORD, int, int, _DWORD *))(*(_DWORD *)v43 + 80))(
            *(_DWORD *)(*(_DWORD *)v43 + 80),
            v43,
            12,
            v49);
          (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v43 + 8))(*(_DWORD *)(*(_DWORD *)v43 + 8), v43);
        }
      }
      if ( Block[17].KsDataTypeHandler )
      {
        KsCompleteIoOperation = Block->KsDataTypeHandler->KsCompleteIoOperation;
        ((void (__thiscall *)(HRESULT (__stdcall *)(IKsDataTypeHandler *, IMediaSample *, void *, KSIOOPERATION, int), IKsDataTypeHandler *, IKsInterfaceHandler *, char *, KSIOOPERATION, bool))KsCompleteIoOperation)(
          KsCompleteIoOperation,
          Block->KsDataTypeHandler,
          (&Block->KsInterfaceHandler)[v6],
          v38,
          Block->IoOperation,
          !v39);
      }
      if ( Block->IoOperation != KsIoOperation_Read )
        goto LABEL_72;
      v44 = 0;
      v41 = 0;
      if ( !v39 )
        goto LABEL_45;
      KsProcessMediaSamples = (&Block->KsInterfaceHandler)[v6]->__vftable[2].KsProcessMediaSamples;
      ((void (__thiscall *)(HRESULT (__stdcall *)(IKsInterfaceHandler *, IKsDataTypeHandler *, IMediaSample **, int *, KSIOOPERATION, _KSSTREAM_SEGMENT **), IKsInterfaceHandler *, int))KsProcessMediaSamples)(
        KsProcessMediaSamples,
        (&Block->KsInterfaceHandler)[v6],
        *((_DWORD *)v38 + 11) & 4);
      v18 = (&Block->KsInterfaceHandler)[v6]->__vftable[1].KsProcessMediaSamples;
      ((void (__thiscall *)(HRESULT (__stdcall *)(IKsInterfaceHandler *, IKsDataTypeHandler *, IMediaSample **, int *, KSIOOPERATION, _KSSTREAM_SEGMENT **), IKsInterfaceHandler *, int))v18)(
        v18,
        (&Block->KsInterfaceHandler)[v6],
        *((_DWORD *)v38 + 11) & 2);
      Release = (&Block->KsInterfaceHandler)[v6]->__vftable[1].Release;
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsInterfaceHandler *, int))Release)(
        Release,
        (&Block->KsInterfaceHandler)[v6],
        *((_DWORD *)v38 + 11) & 1);
      if ( (v38[44] & 0x10) != 0 )
      {
        v20 = (*((_DWORD *)v38 + 11) & 0x100) == 0;
        v21 = v47;
        v22 = *((_DWORD *)v38 + 2);
        v23 = *((_DWORD *)v38 + 3);
        v47[0] = v22;
        v47[1] = v23;
        v41 = v47;
        if ( !v20 )
        {
          v48 = *((_QWORD *)v38 + 3) + __PAIR64__(v23, v22);
          v44 = (CD3DSurfaceAllocator *)&v48;
        }
      }
      else
      {
LABEL_45:
        v21 = 0;
      }
      v24 = (&Block->KsInterfaceHandler)[v6]->__vftable[1].QueryInterface;
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IKsInterfaceHandler *, _DWORD *, CD3DSurfaceAllocator *))v24)(
             v24,
             (&Block->KsInterfaceHandler)[v6],
             v21,
             v44) < 0
        && !v44 )
      {
        v25 = (&Block->KsInterfaceHandler)[v6]->__vftable[1].QueryInterface;
        ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IKsInterfaceHandler *, _DWORD *, _DWORD *))v25)(
          v25,
          (&Block->KsInterfaceHandler)[v6],
          v41,
          v41);
      }
      v26 = IsD3DMediaSample(v37);
      v27 = (&Block->KsInterfaceHandler)[v6];
      v20 = v26 == 0;
      v28 = v27->__vftable;
      if ( v20 )
      {
        v34 = (CD3DSurfaceAllocator *)v28[2].QueryInterface;
        v44 = v34;
        v35 = v39 ? *((_DWORD *)v38 + 9) : 0;
        ((void (__thiscall *)(CD3DSurfaceAllocator *, IKsInterfaceHandler *, int))v44)(v34, v27, v35);
      }
      else
      {
        v29 = (_DWORD *)*((_DWORD *)v38 + 10);
        v30 = (CD3DSurfaceAllocator *)&v28[2];
        v42 = v29;
        v44 = v30;
        if ( v29 )
        {
          v44 = *(CD3DSurfaceAllocator **)v30;
          if ( v39 )
            v31 = v29[4];
          else
            v31 = 0;
          ((void (__thiscall *)(CD3DSurfaceAllocator *, IKsInterfaceHandler *, int))v44)(v44, v27, v31);
          v32 = (CD3DSurfaceAllocator *)VidmemToSysmemBlit(v37);
          v44 = v32;
          if ( (int)v32 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              WPP_SF_q(
                0x10u,
                &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids,
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (char)v32);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                v33 = LastError;
                if ( LastError <= 0 )
                  v33 = LastError;
                WPP_SF_PP(
                  0x11u,
                  (int)WPP_GLOBAL_Control,
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v33,
                  (char)Block[17].CompletionEvent);
              }
              v32 = v44;
            }
            v39 = 0;
            if ( v32 == (CD3DSurfaceAllocator *)-2005530520 || v32 == (CD3DSurfaceAllocator *)-2005530508 )
              RestartGraph(v37);
          }
          memset(v42, 0, 0xA8u);
          *((_DWORD *)v38 + 10) = 0;
        }
        else
        {
          (*(void (__thiscall **)(_DWORD, IKsInterfaceHandler *, _DWORD))v44)(*(_DWORD *)v30, v27, 0);
        }
      }
      if ( v39 )
        (*(void (__thiscall **)(_DWORD, _DWORD, IKsInterfaceHandler *, _DWORD))(**(_DWORD **)&this->m_ClsID.Data2 + 32))(
          *(_DWORD *)(**(_DWORD **)&this->m_ClsID.Data2 + 32),
          *(_DWORD *)&this->m_ClsID.Data2,
          (&Block->KsInterfaceHandler)[v6],
          *((_DWORD *)v38 + 11));
      else
LABEL_72:
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsInterfaceHandler *))(&Block->KsInterfaceHandler)[v6]->Release)(
          (&Block->KsInterfaceHandler)[v6]->Release,
          (&Block->KsInterfaceHandler)[v6]);
      IoOperation = (char *)Block[17].KsDataTypeHandler + (unsigned int)(v38 + 48);
      ++v6;
      ++v45;
      OverlappedResult = v39;
      v38 = IoOperation;
      if ( v45 >= (int)Block[17].KsInterfaceHandler )
      {
        v2 = this;
        goto LABEL_75;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_q(0xDu, &WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), (char)Block);
    if ( IsD3DMediaSample(v37) )
    {
      v44 = (CD3DSurfaceAllocator *)*((_DWORD *)IoOperation + 10);
      if ( v44 )
      {
        ((void (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IKsInterfaceHandler *, _DWORD))(&Block->KsInterfaceHandler)[v6]->__vftable[2].QueryInterface)(
          (&Block->KsInterfaceHandler)[v6]->__vftable[2].QueryInterface,
          (&Block->KsInterfaceHandler)[v6],
          0);
        memset(v44, 0, 0xA8u);
        *((_DWORD *)v38 + 10) = 0;
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v9 = LastError;
        if ( LastError <= 0 )
          v9 = LastError;
        WPP_SF_PP(0xEu, v7, *((_QWORD *)WPP_GLOBAL_Control + 2), v9, (char)Block[17].CompletionEvent);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( Block[17].CompletionEvent != (void *)-1073741811 )
      {
        v10 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v10 = LastError;
        if ( v10 != -2147024865 && v10 != -2147024809 && v10 != -2147023112 )
          goto LABEL_27;
      }
      if ( this->m_ClsID.Data4[4] )
        goto LABEL_27;
      if ( RestartGraph(v37) >= 0 )
        this->m_ClsID.Data4[4] = 1;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_27:
    if ( !this->m_ClsID.Data4[4] )
    {
      if ( v8 != &WPP_GLOBAL_Control )
      {
        v11 = LastError;
        if ( LastError <= 0 )
          v11 = LastError;
        WPP_SF_PP(0xFu, LastError, *((_QWORD *)v8 + 2), v11, (char)Block[17].CompletionEvent);
      }
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      (*(void (__thiscall **)(_DWORD, _DWORD, IKsInterfaceHandler *, unsigned int))(**(_DWORD **)&this->m_ClsID.Data2
                                                                                  + 64))(
        *(_DWORD *)(**(_DWORD **)&this->m_ClsID.Data2 + 64),
        *(_DWORD *)&this->m_ClsID.Data2,
        (&Block->KsInterfaceHandler)[v6],
        v12);
    }
    goto LABEL_35;
  }
LABEL_75:
  operator delete[]((void *)Block[17].IoOperation);
  if ( Block[17].KsDataTypeHandler )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsDataTypeHandler *))Block->KsDataTypeHandler->Release)(
      Block->KsDataTypeHandler->Release,
      Block->KsDataTypeHandler);
  (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)&v2->m_ClsID.Data2 + 56))(
    *(_DWORD *)(**(_DWORD **)&v2->m_ClsID.Data2 + 56),
    *(_DWORD *)&v2->m_ClsID.Data2);
  (*(void (__thiscall **)(_DWORD, _DWORD, struct _KSSTREAM_SEGMENT *))(**(_DWORD **)&v2->m_ClsID.Data2 + 36))(
    *(_DWORD *)(**(_DWORD **)&v2->m_ClsID.Data2 + 36),
    *(_DWORD *)&v2->m_ClsID.Data2,
    Block);
  operator delete(Block, 0x130u);
  ((void (__thiscall *)(unsigned int (__stdcall *)(struct CStandardInterfaceHandler *), CStandardInterfaceHandler *))v2->NonDelegatingRelease)(
    v2->NonDelegatingRelease,
    v2);
  return 0;
}

```

## disassembly

```asm
0x10034140  mov     edi, edi
0x10034142  push    ebp
0x10034143  mov     ebp, esp
0x10034145  and     esp, 0FFFFFFF8h
0x10034148  sub     esp, 64h
0x1003414b  push    ebx
0x1003414c  mov     ebx, [ebp+this]
0x1003414f  lea     ecx, [esp+68h+NumberOfBytesTransferred]
0x10034153  push    esi
0x10034154  push    edi; struct IMediaSample *
0x10034155  mov     edi, [ebp+Block]
0x10034158  push    0; bWait
0x1003415a  push    ecx; lpNumberOfBytesTransferred
0x1003415b  mov     esi, [edi+118h]
0x10034161  lea     eax, [edi+11Ch]
0x10034167  push    eax; lpOverlapped
0x10034168  push    dword ptr [ebx+18h]; hFile
0x1003416b  mov     [esp+80h+var_60], esi
0x1003416f  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x10034175  mov     [esp+70h+var_5C], eax
0x10034179  test    eax, eax
0x1003417b  jz      short loc_10034187
0x1003417d  mov     dword ptr [esp+70h+var_58], 0
0x10034185  jmp     short loc_10034195
0x10034187  call    ds:__imp__GetLastError@0; GetLastError()
0x1003418d  mov     dword ptr [esp+70h+var_58], eax
0x10034191  mov     eax, [esp+70h+var_5C]
0x10034195  cmp     dword ptr [edi+110h], 0
0x1003419c  mov     [esp+70h+var_48], 0
0x100341a4  jle     loc_10034676
0x100341aa  push    4
0x100341ac  pop     ebx
0x100341ad  test    eax, eax
0x100341af  jnz     loc_1003430E
0x100341b5  mov     eax, _WPP_GLOBAL_Control
0x100341ba  cmp     eax, offset _WPP_GLOBAL_Control
0x100341bf  jz      short loc_100341DB
0x100341c1  cmp     byte ptr [eax+19h], 1
0x100341c5  jb      short loc_100341DB
0x100341c7  push    edi; char
0x100341c8  push    dword ptr [eax+14h]
0x100341cb  mov     edx, offset _WPP_79d1fc5633e1321b8c66a7f33f1e4ca1_Traceguids; MessageGuid
0x100341d0  push    dword ptr [eax+10h]; LoggerHandle
0x100341d3  push    0Dh
0x100341d5  pop     ecx; MessageNumber
0x100341d6  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x100341db  mov     ecx, [edi+ebx*4]
0x100341de  call    ?IsD3DMediaSample@@YGHPAUIMediaSample@@@Z; IsD3DMediaSample(IMediaSample *)
0x100341e3  test    eax, eax
0x100341e5  jz      loc_100342AA
0x100341eb  mov     eax, [esi+28h]
0x100341ee  mov     [esp+70h+var_4C], eax
0x100341f2  test    eax, eax
0x100341f4  jz      short loc_10034229
0x100341f6  mov     ecx, [edi+ebx*4]
0x100341f9  push    0
0x100341fb  push    ecx
0x100341fc  mov     eax, [ecx]
0x100341fe  mov     esi, [eax+30h]
0x10034201  mov     ecx, esi; this
0x10034203  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034209  call    esi
0x1003420b  push    0A8h; Size
0x10034210  push    0; Val
0x10034212  push    [esp+78h+var_4C]; void *
0x10034216  call    _memset
0x1003421b  mov     eax, [esp+7Ch+var_60]
0x1003421f  add     esp, 0Ch
0x10034222  mov     dword ptr [eax+28h], 0
0x10034229  mov     ecx, _WPP_GLOBAL_Control
0x1003422f  mov     esi, dword ptr [esp+70h+var_58]
0x10034233  cmp     ecx, offset _WPP_GLOBAL_Control
0x10034239  jz      short loc_10034263
0x1003423b  push    dword ptr [edi+11Ch]; char
0x10034241  movzx   eax, si
0x10034244  or      eax, 80070000h
0x10034249  test    esi, esi
0x1003424b  cmovle  eax, esi
0x1003424e  push    eax; char
0x1003424f  push    dword ptr [ecx+14h]
0x10034252  push    dword ptr [ecx+10h]; LoggerHandle
0x10034255  push    0Eh
0x10034257  pop     ecx; MessageNumber
0x10034258  call    _WPP_SF_PP@24; WPP_SF_PP(x,x,x,x,x,x)
0x1003425d  mov     ecx, _WPP_GLOBAL_Control
0x10034263  cmp     dword ptr [edi+11Ch], 0C000000Dh
0x1003426d  jz      short loc_10034291
0x1003426f  movzx   eax, si
0x10034272  or      eax, 80070000h
0x10034277  test    esi, esi
0x10034279  cmovle  eax, esi
0x1003427c  cmp     eax, 8007001Fh
0x10034281  jz      short loc_10034291
0x10034283  cmp     eax, 80070057h
0x10034288  jz      short loc_10034291
0x1003428a  cmp     eax, 800706F8h
0x1003428f  jnz     short loc_100342B0
0x10034291  mov     esi, [ebp+this]
0x10034294  cmp     byte ptr [esi+1Ch], 0
0x10034298  jnz     short loc_100342B0
0x1003429a  mov     ecx, [edi+ebx*4]
0x1003429d  call    ?RestartGraph@@YGJPAUIMediaSample@@@Z; RestartGraph(IMediaSample *)
0x100342a2  test    eax, eax
0x100342a4  js      short loc_100342AA
0x100342a6  mov     byte ptr [esi+1Ch], 1
0x100342aa  mov     ecx, _WPP_GLOBAL_Control
0x100342b0  mov     esi, [ebp+this]
0x100342b3  cmp     byte ptr [esi+1Ch], 0
0x100342b7  jnz     short loc_1003430E
0x100342b9  cmp     ecx, offset _WPP_GLOBAL_Control
0x100342bf  jz      short loc_100342E7
0x100342c1  mov     edx, dword ptr [esp+70h+var_58]
0x100342c5  push    dword ptr [edi+11Ch]; char
0x100342cb  movzx   eax, dx
0x100342ce  or      eax, 80070000h
0x100342d3  test    edx, edx
0x100342d5  cmovle  eax, edx
0x100342d8  push    eax; char
0x100342d9  push    dword ptr [ecx+14h]
0x100342dc  push    dword ptr [ecx+10h]; LoggerHandle
0x100342df  push    0Fh
0x100342e1  pop     ecx; MessageNumber
0x100342e2  call    _WPP_SF_PP@24; WPP_SF_PP(x,x,x,x,x,x)
0x100342e7  mov     edx, dword ptr [esp+70h+var_58]
0x100342eb  mov     ecx, [esi+14h]
0x100342ee  movzx   eax, dx
0x100342f1  or      eax, 80070000h
0x100342f6  test    edx, edx
0x100342f8  mov     esi, [ecx]
0x100342fa  cmovle  eax, edx
0x100342fd  push    eax
0x100342fe  push    dword ptr [edi+ebx*4]
0x10034301  push    ecx
0x10034302  mov     ecx, [esi+40h]; this
0x10034305  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003430b  call    dword ptr [esi+40h]
0x1003430e  imul    ecx, [esp+70h+var_48], 30h ; '0'
0x10034313  mov     eax, [edi+118h]
0x10034319  mov     [esp+70h+var_4C], ecx
0x1003431d  cmp     dword ptr [ecx+eax+4], 0
0x10034322  jz      loc_100343B5
0x10034328  mov     ecx, [edi+ebx*4]
0x1003432b  mov     eax, [ecx]
0x1003432d  mov     esi, [eax]
0x1003432f  lea     eax, [esp+70h+var_50]
0x10034333  push    eax
0x10034334  push    offset __GUID_36b73884_c2c8_11cf_8b46_00805f6cef60
0x10034339  push    ecx
0x1003433a  mov     ecx, esi; this
0x1003433c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034342  call    esi
0x10034344  test    eax, eax
0x10034346  js      short loc_100343B5
0x10034348  mov     eax, [esp+70h+var_50]
0x1003434c  lea     ecx, [esp+70h+var_30]
0x10034350  push    ecx
0x10034351  push    0Ch
0x10034353  push    eax
0x10034354  mov     esi, [eax]
0x10034356  mov     ecx, [esi+4Ch]; this
0x10034359  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003435f  call    dword ptr [esi+4Ch]
0x10034362  mov     ecx, [edi+118h]
0x10034368  mov     edx, [esp+70h+var_4C]
0x1003436c  mov     [esp+70h+var_30], 0Ch
0x10034374  mov     eax, [ecx+edx+4]
0x10034378  mov     [esp+70h+var_2C], eax
0x1003437c  mov     eax, [ecx+edx+2Ch]
0x10034380  lea     ecx, [esp+70h+var_30]
0x10034384  and     eax, 40h
0x10034387  or      [esp+70h+var_28], eax
0x1003438b  mov     eax, [esp+70h+var_50]
0x1003438f  push    ecx
0x10034390  push    0Ch
0x10034392  push    eax
0x10034393  mov     esi, [eax]
0x10034395  mov     ecx, [esi+50h]; this
0x10034398  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003439e  call    dword ptr [esi+50h]
0x100343a1  mov     eax, [esp+70h+var_50]
0x100343a5  push    eax
0x100343a6  mov     ecx, [eax]
0x100343a8  mov     esi, [ecx+8]
0x100343ab  mov     ecx, esi; this
0x100343ad  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100343b3  call    esi
0x100343b5  cmp     dword ptr [edi+114h], 0
0x100343bc  jz      short loc_100343E4
0x100343be  mov     ecx, [edi+4]
0x100343c1  xor     eax, eax
0x100343c3  cmp     [esp+70h+var_5C], eax
0x100343c7  setz    al
0x100343ca  mov     esi, [ecx]
0x100343cc  push    eax
0x100343cd  push    dword ptr [edi+8]
0x100343d0  push    [esp+78h+var_60]
0x100343d4  push    dword ptr [edi+ebx*4]
0x100343d7  push    ecx
0x100343d8  mov     ecx, [esi+0Ch]; this
0x100343db  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100343e1  call    dword ptr [esi+0Ch]
0x100343e4  cmp     dword ptr [edi+8], 1
0x100343e8  jnz     loc_10034635
0x100343ee  cmp     [esp+70h+var_5C], 0
0x100343f3  mov     [esp+70h+var_4C], 0
0x100343fb  mov     [esp+70h+var_54], 0
0x10034403  jz      loc_100344A3
0x10034409  mov     ecx, [edi+ebx*4]
0x1003440c  mov     eax, [esp+70h+var_60]
0x10034410  mov     esi, [ecx]
0x10034412  mov     eax, [eax+2Ch]
0x10034415  and     eax, 4
0x10034418  push    eax
0x10034419  push    ecx
0x1003441a  mov     ecx, [esi+40h]; this
0x1003441d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034423  call    dword ptr [esi+40h]
0x10034426  mov     ecx, [edi+ebx*4]
0x10034429  mov     eax, [esp+70h+var_60]
0x1003442d  mov     esi, [ecx]
0x1003442f  mov     eax, [eax+2Ch]
0x10034432  and     eax, 2
0x10034435  push    eax
0x10034436  push    ecx
0x10034437  mov     ecx, [esi+28h]; this
0x1003443a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10034440  call    dword ptr [esi+28h]
0x10034443  mov     ecx, [edi+ebx*4]
0x10034446  mov     eax, [esp+70h+var_60]
0x1003444a  mov     esi, [ecx]
0x1003444c  mov     eax, [eax+2Ch]
0x1003444f  and     eax, 1
0x10034452  push    eax
0x10034453  push    ecx
0x10034454  mov     ecx, [esi+20h]; this
0x10034457  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003445d  call    dword ptr [esi+20h]
0x10034460  mov     eax, [esp+70h+var_60]
0x10034464  test    byte ptr [eax+2Ch], 10h
0x10034468  jz      short loc_100344A3
0x1003446a  test    dword ptr [eax+2Ch], 100h
0x10034471  lea     edx, [esp+70h+var_40]
0x10034475  mov     ecx, [eax+8]
0x10034478  mov     esi, [eax+0Ch]
0x1003447b  mov     [esp+70h+var_40], ecx
0x1003447f  mov     [esp+70h+var_3C], esi
0x10034483  mov     [esp+70h+var_54], edx
0x10034487  jz      short loc_100344A7
0x10034489  add     ecx, [eax+18h]
0x1003448c  mov     eax, [eax+1Ch]
0x1003448f  adc     eax, esi
0x10034491  mov     dword ptr [esp+70h+var_38], ecx
0x10034495  mov     dword ptr [esp+70h+var_38+4], eax
0x10034499  lea     eax, [esp+70h+var_38]
0x1003449d  mov     [esp+70h+var_4C], eax
0x100344a1  jmp     short loc_100344A7
0x100344a3  mov     edx, [esp+70h+var_54]
0x100344a7  mov     ecx, [edi+ebx*4]
0x100344aa  push    [esp+70h+var_4C]
0x100344ae  push    edx
0x100344af  mov     eax, [ecx]
0x100344b1  push    ecx
0x100344b2  mov     esi, [eax+18h]
0x100344b5  mov     ecx, esi; this
0x100344b7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100344bd  call    esi
0x100344bf  test    eax, eax
0x100344c1  jns     short loc_100344E3
0x100344c3  cmp     [esp+70h+var_4C], 0
0x100344c8  jnz     short loc_100344E3
0x100344ca  mov     eax, [edi+ebx*4]
0x100344cd  mov     edx, [esp+70h+var_54]
0x100344d1  push    edx
0x100344d2  push    edx
0x100344d3  mov     ecx, [eax]
0x100344d5  push    eax
0x100344d6  mov     esi, [ecx+18h]
0x100344d9  mov     ecx, esi; this
0x100344db  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100344e1  call    esi
0x100344e3  mov     ecx, [edi+ebx*4]
0x100344e6  call    ?IsD3DMediaSample@@YGHPAUIMediaSample@@@Z; IsD3DMediaSample(IMediaSample *)
0x100344eb  mov     ecx, [edi+ebx*4]
0x100344ee  test    eax, eax
0x100344f0  mov     esi, [esp+70h+var_60]
0x100344f4  mov     eax, [ecx]
0x100344f6  jz      loc_100345ED
0x100344fc  mov     edx, [esi+28h]
0x100344ff  add     eax, 30h ; '0'
0x10034502  mov     [esp+70h+var_54], edx
0x10034506  mov     [esp+70h+var_4C], eax
0x1003450a  test    edx, edx
0x1003450c  jz      loc_100345DA
0x10034512  cmp     [esp+70h+var_5C], 0
0x10034517  mov     eax, [eax]
0x10034519  mov     [esp+70h+var_4C], eax
0x1003451d  jz      short loc_10034524
0x1003451f  mov     eax, [edx+10h]
0x10034522  jmp     short loc_10034526
0x10034524  xor     eax, eax
  ... truncated ...
```
