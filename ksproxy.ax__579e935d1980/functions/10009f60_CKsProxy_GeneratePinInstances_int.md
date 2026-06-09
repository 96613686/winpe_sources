# CKsProxy::GeneratePinInstances(int)

- ea: `0x10009f60`
- end: `0x1000a510`
- name: `?GeneratePinInstances@CKsProxy@@QAGJH@Z`
- size: `1456`
- prototype: `int __cdecl(CKsProxy *__hidden this, int)`
- caller_count: `9`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1000cf60`
- `0x10011c70`
- `0x10012420`
- `0x10012460`
- `0x10015b70`
- `0x10016480`
- `0x100164d0`
- `0x1001b860`
- `0x1001b8e0`

## callees

- `0x10009e22`
- `0x10009eb3`
- `0x10009f60`
- `0x1000a516`
- `0x1000adfd`
- `0x1000aea8`
- `0x10010e48`
- `0x1001a323`
- `0x1001f3b0`
- `0x1002b1aa`
- `0x1002d510`
- `0x1002fea7`
- `0x1002ff6e`
- `0x10030c17`
- `0x1003a6f2`
- `0x1003a6fd`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1000a05f`
- `KERNEL32!CloseHandle` at `0x1000a05f`

## pseudocode

```c
int __fastcall CKsProxy::GeneratePinInstances(unsigned int a1, unsigned int a2, CKsProxy *this)
{
  int result; // eax
  DWORD v5; // eax
  int v6; // esi
  int v7; // eax
  unsigned int v8; // ecx
  CBaseList *v9; // edi
  CBaseList::CNode *v10; // edx
  bool v11; // sf
  CBaseList::CNode **v12; // eax
  unsigned int v13; // esi
  int v14; // edi
  DWORD PinFactoryId; // eax
  unsigned int v16; // ecx
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // edi
  void **v20; // eax
  CBaseList::CNode **v21; // eax
  void **v22; // eax
  CBaseList::CNode **v23; // eax
  int v24; // eax
  bool v25; // zf
  unsigned int (__stdcall *Release)(IUnknown *); // esi
  CKsInputPin *OutputPin; // eax
  CKsInputPin *v28; // eax
  int v29; // edi
  int v30; // ecx
  int v31; // edi
  int v32; // eax
  int v33; // ecx
  void *v34; // [esp-1Ch] [ebp-8Ch]
  void *v35; // [esp-1Ch] [ebp-8Ch]
  struct _GUID v36; // [esp-1Ch] [ebp-8Ch]
  struct _GUID v37; // [esp-18h] [ebp-88h]
  CKsProxy *v38; // [esp+0h] [ebp-70h]
  CKsProxy *v39; // [esp+0h] [ebp-70h]
  CKsProxy *v40; // [esp+0h] [ebp-70h]
  unsigned int *v41; // [esp+4h] [ebp-6Ch]
  struct CBasePin *v42; // [esp+4h] [ebp-6Ch]
  struct CBasePin *v43; // [esp+4h] [ebp-6Ch]
  unsigned int v44; // [esp+Ch] [ebp-64h]
  CBaseList::CNode **v45; // [esp+10h] [ebp-60h]
  unsigned int v46; // [esp+14h] [ebp-5Ch]
  void *Block; // [esp+18h] [ebp-58h] BYREF
  int v48; // [esp+1Ch] [ebp-54h] BYREF
  struct IPin *v49; // [esp+20h] [ebp-50h] BYREF
  DWORD BytesReturned; // [esp+24h] [ebp-4Ch] BYREF
  DWORD v51; // [esp+28h] [ebp-48h]
  CKsProxy *v52; // [esp+2Ch] [ebp-44h] BYREF
  int v53; // [esp+30h] [ebp-40h]
  int v54; // [esp+34h] [ebp-3Ch] BYREF
  DWORD v55; // [esp+38h] [ebp-38h] BYREF
  int v56; // [esp+3Ch] [ebp-34h] BYREF
  unsigned int v57; // [esp+40h] [ebp-30h]
  int v58; // [esp+44h] [ebp-2Ch] BYREF
  unsigned int OutBuffer; // [esp+48h] [ebp-28h] BYREF
  GUID InBuffer; // [esp+50h] [ebp-20h] BYREF
  int v61; // [esp+60h] [ebp-10h]
  int v62; // [esp+64h] [ebp-Ch]
  unsigned int v63; // [esp+68h] [ebp-8h]
  int v64; // [esp+6Ch] [ebp-4h]

  v57 = a2;
  result = CKsProxy::GetPinFactoryCount(v38, v41);
  if ( result < 0 )
    return result;
  v5 = v51;
  v6 = 0;
  v53 = 0;
  if ( !v51 )
    goto LABEL_79;
  do
  {
    BytesReturned = 0;
    v46 = v5 - 1;
    InBuffer = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v63 = v5 - 1;
    v61 = 0;
    v62 = 1;
    v34 = *(void **)(a1 + 220);
    v64 = 0;
    v7 = KsSynchronousDeviceControl(v34, 0x2F0003u, &InBuffer, 0x20u, &OutBuffer, 8u, &BytesReturned);
    v8 = OutBuffer;
    v9 = (CBaseList *)(a1 + 172);
    v10 = 0;
    v11 = v7 < 0;
    v12 = *(CBaseList::CNode ***)(a1 + 172);
    if ( v11 )
      v8 = 0;
    Block = 0;
    v13 = 0;
    OutBuffer = v8;
    if ( v12 )
    {
      while ( 1 )
      {
        v14 = (int)v12[2];
        v45 = (CBaseList::CNode **)v12[1];
        PinFactoryId = CKsProxy::GetPinFactoryId(v39, v42);
        v16 = v13 + 1;
        BytesReturned = PinFactoryId;
        if ( PinFactoryId != v46 )
          v16 = v13;
        v17 = v16;
        v44 = v16;
        if ( CKsProxy::GetPinHandle(v40, v43) )
          goto LABEL_47;
        if ( *(_DWORD *)(a1 + 228) && *(_DWORD *)(a1 + 284) == v14 )
        {
          CloseHandle(*(HANDLE *)(a1 + 228));
          *(_DWORD *)(a1 + 228) = 0;
          v53 = 1;
        }
        if ( BytesReturned == v46 )
        {
          if ( Block )
          {
            v18 = *(_DWORD *)(v14 + 12);
            v55 = v14 + 12;
            (*(void (__thiscall **)(_DWORD, int, int *))(v18 + 36))(*(_DWORD *)(v18 + 36), v14 + 12, &v54);
            if ( v54 )
            {
              if ( v54 == 1 )
              {
                BytesReturned = 0;
                if ( (**(int (__thiscall ***)(_DWORD, DWORD, GUID *, DWORD *))v55)(
                       **(_DWORD **)v55,
                       v55,
                       &_GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed,
                       &BytesReturned) >= 0 )
                {
                  v19 = (*(int (__thiscall **)(_DWORD, DWORD))(*(_DWORD *)BytesReturned + 20))(
                          *(_DWORD *)(*(_DWORD *)BytesReturned + 20),
                          BytesReturned);
                  (*(void (__thiscall **)(_DWORD, DWORD))(*(_DWORD *)BytesReturned + 8))(
                    *(_DWORD *)(*(_DWORD *)BytesReturned + 8),
                    BytesReturned);
                  goto LABEL_19;
                }
              }
              goto LABEL_23;
            }
            v19 = *(_DWORD *)(v14 + 456);
LABEL_19:
            if ( v19 <= 1 )
            {
LABEL_23:
              v21 = v45;
              if ( !v45 )
                v21 = (CBaseList::CNode **)(a1 + 176);
              v14 = CBaseList::RemoveI((CBaseList *)(a1 + 172), *v21);
            }
            else
            {
              v14 = CBaseList::RemoveI((CBaseList *)(a1 + 172), (CBaseList::CNode *)Block);
              v20 = (void **)v45;
              if ( !v45 )
                v20 = (void **)(a1 + 176);
              Block = *v20;
            }
            --v44;
            goto LABEL_35;
          }
          v22 = (void **)v45;
          if ( !v45 )
            v22 = (void **)(a1 + 176);
          v14 = 0;
          Block = *v22;
        }
        else
        {
          if ( BytesReturned < v51 )
          {
            v44 = v17;
            goto LABEL_47;
          }
          v23 = v45;
          if ( !v45 )
            v23 = (CBaseList::CNode **)(a1 + 176);
          CBaseList::RemoveI((CBaseList *)(a1 + 172), *v23);
        }
        v44 = v17;
LABEL_35:
        if ( v14 )
        {
          v24 = *(_DWORD *)(v14 + 12);
          BytesReturned = v14 + 12;
          (*(void (__thiscall **)(_DWORD, int, int *))(v24 + 36))(*(_DWORD *)(v24 + 36), v14 + 12, &v56);
          if ( !v56 )
          {
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 456), 0xFFFFFFFF) )
            {
              (*(void (__thiscall **)(int, int))(*(_DWORD *)v14 + 12))(v14, 1);
              goto LABEL_47;
            }
            goto LABEL_42;
          }
          if ( v56 != 1 )
            goto LABEL_47;
          v48 = 0;
          if ( (**(int (__thiscall ***)(_DWORD, DWORD, GUID *, int *))BytesReturned)(
                 **(_DWORD **)BytesReturned,
                 BytesReturned,
                 &_GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed,
                 &v48) < 0 )
            goto LABEL_47;
          v25 = (*(int (__thiscall **)(_DWORD, int, CKsProxy *))(*(_DWORD *)v48 + 24))(
                  *(_DWORD *)(*(_DWORD *)v48 + 24),
                  v48,
                  v39) == 1;
          Release = v49->Release;
          if ( !v25 )
          {
            ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), struct IPin *))Release)(Release, v49);
LABEL_42:
            DerefPipeFromPin((struct IPin *)v39);
            goto LABEL_47;
          }
          ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), struct IPin *))Release)(Release, v49);
        }
LABEL_47:
        v13 = v44;
        v12 = v45;
        if ( !v45 )
        {
          v8 = OutBuffer;
          v9 = (CBaseList *)(a1 + 172);
          v10 = (CBaseList::CNode *)Block;
          break;
        }
      }
    }
    if ( v13 >= v8 && v8 | v13 || v10 )
    {
      if ( v13 > v8 && v8 && v10 )
      {
        v29 = CBaseList::RemoveI(v9, v10);
        v30 = *(_DWORD *)(v29 + 12);
        BytesReturned = v29 + 12;
        (*(void (__thiscall **)(_DWORD, int, int *))(v30 + 36))(*(_DWORD *)(v30 + 36), v29 + 12, &v58);
        if ( !v58 )
        {
          if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v29 + 456), 0xFFFFFFFF) )
          {
            if ( !v29 )
              goto LABEL_77;
            goto LABEL_75;
          }
          goto LABEL_76;
        }
        if ( v58 == 1 )
        {
          v49 = 0;
          if ( (**(int (__thiscall ***)(_DWORD, DWORD, GUID *, struct IPin **))BytesReturned)(
                 **(_DWORD **)BytesReturned,
                 BytesReturned,
                 &_GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed,
                 &v49) >= 0 )
          {
            if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IPin *, IPin **), struct IPin *, CKsProxy *))v49->ConnectedTo)(
                   v49->ConnectedTo,
                   v49,
                   v39) == 1 )
            {
              (*(void (__thiscall **)(_DWORD, DWORD))(*(_DWORD *)BytesReturned + 8))(
                *(_DWORD *)(*(_DWORD *)BytesReturned + 8),
                BytesReturned);
              goto LABEL_77;
            }
            (*(void (__thiscall **)(_DWORD, DWORD))(*(_DWORD *)BytesReturned + 8))(
              *(_DWORD *)(*(_DWORD *)BytesReturned + 8),
              BytesReturned);
LABEL_76:
            DerefPipeFromPin((struct IPin *)v39);
          }
        }
      }
    }
    else
    {
      Block = 0;
      v55 = 0;
      InBuffer.Data1 = _GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1;
      *(_DWORD *)&InBuffer.Data2 = *(_DWORD *)&_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data2;
      v35 = *(void **)(a1 + 220);
      *(_DWORD *)InBuffer.Data4 = *(_DWORD *)_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data4;
      *(_DWORD *)&InBuffer.Data4[4] = *(_DWORD *)&_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data4[4];
      v61 = 2;
      v62 = 1;
      v63 = v46;
      v64 = 0;
      if ( KsSynchronousDeviceControl(v35, 0x2F0003u, &InBuffer, 0x20u, &v52, 4u, &v55) >= 0
        && CKsProxy::ConstructPinName(v52, (unsigned int)&Block, (enum KSPIN_DATAFLOW)v39, (unsigned __int16 **)v42) >= 0 )
      {
        BytesReturned = 0;
        if ( v52 == (CKsProxy *)1 )
        {
          v28 = (CKsInputPin *)operator new(0x1D0u);
          if ( !v28 )
            goto LABEL_60;
          *(_DWORD *)v36.Data4 = Block;
          *(_DWORD *)&v36.Data4[4] = *(_DWORD *)(a1 + 40);
          *(_QWORD *)&v36.Data1 = __PAIR64__(&BytesReturned, a1);
          OutputPin = CKsInputPin::CKsInputPin(
                        v28,
                        (unsigned __int16 *)&BytesReturned,
                        v46,
                        v36,
                        *(struct CKsProxy **)(a1 + 44),
                        *(int **)(a1 + 48),
                        *(unsigned __int16 **)(a1 + 52));
LABEL_59:
          v29 = (int)OutputPin;
        }
        else
        {
          if ( v52 == (CKsProxy *)2 )
          {
            *(_DWORD *)v37.Data4 = *(_DWORD *)(a1 + 40);
            *(_QWORD *)&v37.Data1 = __PAIR64__(v57, (unsigned int)Block);
            *(_DWORD *)&v37.Data4[4] = *(_DWORD *)(a1 + 44);
            OutputPin = (CKsInputPin *)CreateOutputPin(
                                         (unsigned __int16 *)a1,
                                         (int)&BytesReturned,
                                         v37,
                                         *(struct CKsProxy **)(a1 + 48),
                                         *(int **)(a1 + 52),
                                         (unsigned __int16 *)v39,
                                         (int)v42);
            goto LABEL_59;
          }
LABEL_60:
          v29 = 0;
        }
        operator delete[](Block);
        if ( !v29 )
          goto LABEL_77;
        if ( (BytesReturned & 0x80000000) == 0 )
        {
          CBaseList::AddHeadI((CBaseList *)(a1 + 172), (void *)v29);
          goto LABEL_77;
        }
LABEL_75:
        (*(void (__thiscall **)(int, int))(*(_DWORD *)v29 + 12))(v29, 1);
      }
    }
LABEL_77:
    v5 = v46;
  }
  while ( v46 );
  v6 = v53;
LABEL_79:
  if ( !*(_DWORD *)(a1 + 228) )
    CKsProxy::DetermineClockSource(v39);
  if ( v6 )
    CBaseFilter::NotifyEvent((CBaseFilter *)a1, 81, 0, 0);
  v31 = *(_DWORD *)(a1 + 196);
  while ( v31 )
  {
    v32 = *(_DWORD *)(v31 + 8);
    v31 = *(_DWORD *)(v31 + 4);
    v33 = *(_DWORD *)(v32 + 36);
    if ( v33 )
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v33 + 28))(*(_DWORD *)(*(_DWORD *)v33 + 28), v33);
  }
  return 0;
}

```

## disassembly

```asm
0x10009f60  mov     edi, edi
0x10009f62  push    ebp
0x10009f63  mov     ebp, esp
0x10009f65  and     esp, 0FFFFFFF8h
0x10009f68  sub     esp, 64h
0x10009f6b  push    ebx
0x10009f6c  push    esi; int
0x10009f6d  mov     [esp+6Ch+var_30], edx
0x10009f71  mov     ebx, ecx
0x10009f73  push    edi; this
0x10009f74  lea     edx, [esp+70h+var_48]
0x10009f78  call    ?GetPinFactoryCount@CKsProxy@@QAGJPAK@Z; CKsProxy::GetPinFactoryCount(ulong *)
0x10009f7d  test    eax, eax
0x10009f7f  js      loc_1000A509
0x10009f85  mov     eax, [esp+70h+var_48]
0x10009f89  xor     esi, esi
0x10009f8b  mov     [esp+70h+var_40], esi
0x10009f8f  test    eax, eax
0x10009f91  jz      loc_1000A4BD
0x10009f97  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x10009f9c  mov     [esp+70h+BytesReturned], 0
0x10009fa4  lea     edi, [esp+70h+InBuffer]
0x10009fa8  dec     eax
0x10009fa9  mov     [esp+70h+var_5C], eax
0x10009fad  movsd
0x10009fae  movsd
0x10009faf  movsd
0x10009fb0  movsd
0x10009fb1  mov     [esp+70h+var_8], eax
0x10009fb5  lea     eax, [esp+70h+BytesReturned]
0x10009fb9  push    eax; lpBytesReturned
0x10009fba  push    8; nOutBufferSize
0x10009fbc  lea     eax, [esp+78h+OutBuffer]
0x10009fc0  mov     [esp+78h+var_10], 0
0x10009fc8  push    eax; lpOutBuffer
0x10009fc9  push    20h ; ' '; nInBufferSize
0x10009fcb  lea     eax, [esp+80h+InBuffer]
0x10009fcf  mov     [esp+80h+var_C], 1
0x10009fd7  push    eax; lpInBuffer
0x10009fd8  push    2F0003h; dwIoControlCode
0x10009fdd  push    dword ptr [ebx+0DCh]; hDevice
0x10009fe3  mov     [esp+8Ch+var_4], 0
0x10009fee  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10009ff3  mov     ecx, [esp+70h+OutBuffer]
0x10009ff7  lea     edi, [ebx+0ACh]
0x10009ffd  xor     edx, edx
0x10009fff  test    eax, eax
0x1000a001  mov     eax, [edi]
0x1000a003  cmovs   ecx, edx
0x1000a006  mov     [esp+70h+Block], edx
0x1000a00a  xor     esi, esi
0x1000a00c  mov     [esp+70h+OutBuffer], ecx
0x1000a010  test    eax, eax
0x1000a012  jz      loc_1000A28D
0x1000a018  mov     edi, [eax+8]
0x1000a01b  mov     edx, edi
0x1000a01d  mov     eax, [eax+4]
0x1000a020  mov     [esp+70h+var_60], eax
0x1000a024  call    ?GetPinFactoryId@CKsProxy@@QAGKPAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x1000a029  cmp     eax, [esp+70h+var_5C]
0x1000a02d  lea     ecx, [esi+1]
0x1000a030  mov     edx, edi
0x1000a032  mov     [esp+70h+BytesReturned], eax
0x1000a036  cmovnz  ecx, esi
0x1000a039  mov     esi, ecx
0x1000a03b  mov     [esp+70h+var_64], esi
0x1000a03f  call    ?GetPinHandle@CKsProxy@@QAGPAXPAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x1000a044  test    eax, eax
0x1000a046  jnz     loc_1000A26C
0x1000a04c  mov     eax, [ebx+0E4h]
0x1000a052  test    eax, eax
0x1000a054  jz      short loc_1000A077
0x1000a056  cmp     [ebx+11Ch], edi
0x1000a05c  jnz     short loc_1000A077
0x1000a05e  push    eax; hObject
0x1000a05f  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000a065  mov     dword ptr [ebx+0E4h], 0
0x1000a06f  mov     [esp+70h+var_40], 1
0x1000a077  mov     eax, [esp+70h+BytesReturned]
0x1000a07b  cmp     eax, [esp+70h+var_5C]
0x1000a07f  jnz     loc_1000A17C
0x1000a085  cmp     [esp+70h+Block], 0
0x1000a08a  jz      loc_1000A164
0x1000a090  lea     ecx, [edi+0Ch]
0x1000a093  mov     eax, [ecx]
0x1000a095  lea     edx, [esp+70h+var_3C]
0x1000a099  push    edx
0x1000a09a  mov     [esp+74h+var_38], ecx
0x1000a09e  push    ecx
0x1000a09f  mov     esi, [eax+24h]
0x1000a0a2  mov     ecx, esi; this
0x1000a0a4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a0aa  call    esi
0x1000a0ac  mov     eax, [esp+70h+var_3C]
0x1000a0b0  sub     eax, 0
0x1000a0b3  jz      short loc_1000A10F
0x1000a0b5  sub     eax, 1
0x1000a0b8  jnz     loc_1000A141
0x1000a0be  mov     ecx, [esp+70h+var_38]
0x1000a0c2  mov     [esp+70h+BytesReturned], eax
0x1000a0c6  mov     eax, [ecx]
0x1000a0c8  mov     esi, [eax]
0x1000a0ca  lea     eax, [esp+70h+BytesReturned]
0x1000a0ce  push    eax
0x1000a0cf  push    offset __GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed
0x1000a0d4  push    ecx
0x1000a0d5  mov     ecx, esi; this
0x1000a0d7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a0dd  call    esi
0x1000a0df  test    eax, eax
0x1000a0e1  js      short loc_1000A141
0x1000a0e3  mov     eax, [esp+70h+BytesReturned]
0x1000a0e7  push    eax
0x1000a0e8  mov     ecx, [eax]
0x1000a0ea  mov     esi, [ecx+14h]
0x1000a0ed  mov     ecx, esi; this
0x1000a0ef  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a0f5  call    esi
0x1000a0f7  mov     ecx, [esp+70h+BytesReturned]
0x1000a0fb  mov     edi, eax
0x1000a0fd  push    ecx
0x1000a0fe  mov     edx, [ecx]
0x1000a100  mov     esi, [edx+8]
0x1000a103  mov     ecx, esi; this
0x1000a105  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a10b  call    esi
0x1000a10d  jmp     short loc_1000A115
0x1000a10f  mov     edi, [edi+1C8h]
0x1000a115  cmp     edi, 1
0x1000a118  jbe     short loc_1000A141
0x1000a11a  push    [esp+70h+Block]; struct __POSITION *
0x1000a11e  lea     ecx, [ebx+0ACh]; this
0x1000a124  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1000a129  mov     edi, eax
0x1000a12b  mov     eax, [esp+70h+var_60]
0x1000a12f  test    eax, eax
0x1000a131  jnz     short loc_1000A139
0x1000a133  lea     eax, [ebx+0B0h]
0x1000a139  mov     eax, [eax]
0x1000a13b  mov     [esp+70h+Block], eax
0x1000a13f  jmp     short loc_1000A15E
0x1000a141  mov     eax, [esp+70h+var_60]
0x1000a145  test    eax, eax
0x1000a147  jnz     short loc_1000A14F
0x1000a149  lea     eax, [ebx+0B0h]
0x1000a14f  push    dword ptr [eax]; struct __POSITION *
0x1000a151  lea     ecx, [ebx+0ACh]; this
0x1000a157  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1000a15c  mov     edi, eax
0x1000a15e  dec     [esp+70h+var_64]
0x1000a162  jmp     short loc_1000A1A5
0x1000a164  mov     eax, [esp+70h+var_60]
0x1000a168  test    eax, eax
0x1000a16a  jnz     short loc_1000A172
0x1000a16c  lea     eax, [ebx+0B0h]
0x1000a172  mov     eax, [eax]
0x1000a174  xor     edi, edi
0x1000a176  mov     [esp+70h+Block], eax
0x1000a17a  jmp     short loc_1000A1A1
0x1000a17c  cmp     eax, [esp+70h+var_48]
0x1000a180  jb      loc_1000A268
0x1000a186  mov     eax, [esp+70h+var_60]
0x1000a18a  test    eax, eax
0x1000a18c  jnz     short loc_1000A194
0x1000a18e  lea     eax, [ebx+0B0h]
0x1000a194  push    dword ptr [eax]; struct __POSITION *
0x1000a196  lea     ecx, [ebx+0ACh]; this
0x1000a19c  call    ?RemoveI@CBaseList@@IAEPAXPAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1000a1a1  mov     [esp+70h+var_64], esi
0x1000a1a5  test    edi, edi
0x1000a1a7  jz      loc_1000A26C
0x1000a1ad  lea     ecx, [edi+0Ch]
0x1000a1b0  mov     eax, [ecx]
0x1000a1b2  lea     edx, [esp+70h+var_34]
0x1000a1b6  push    edx
0x1000a1b7  mov     [esp+74h+BytesReturned], ecx
0x1000a1bb  push    ecx
0x1000a1bc  mov     esi, [eax+24h]
0x1000a1bf  mov     ecx, esi; this
0x1000a1c1  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a1c7  call    esi
0x1000a1c9  mov     eax, [esp+70h+var_34]
0x1000a1cd  sub     eax, 0
0x1000a1d0  jz      short loc_1000A240
0x1000a1d2  sub     eax, 1
0x1000a1d5  jnz     loc_1000A26C
0x1000a1db  mov     edi, [esp+70h+BytesReturned]
0x1000a1df  mov     [esp+70h+var_54], eax
0x1000a1e3  mov     eax, [edi]
0x1000a1e5  mov     esi, [eax]
0x1000a1e7  lea     eax, [esp+70h+var_54]
0x1000a1eb  push    eax
0x1000a1ec  push    offset __GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed
0x1000a1f1  push    edi
0x1000a1f2  mov     ecx, esi; this
0x1000a1f4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a1fa  call    esi
0x1000a1fc  test    eax, eax
0x1000a1fe  js      short loc_1000A26C
0x1000a200  mov     eax, [esp+70h+var_54]
0x1000a204  push    eax
0x1000a205  mov     ecx, [eax]
0x1000a207  mov     esi, [ecx+18h]
0x1000a20a  mov     ecx, esi; this
0x1000a20c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a212  call    esi
0x1000a214  cmp     eax, 1
0x1000a217  mov     eax, [esp+6Ch+var_50]
0x1000a21b  push    eax; struct IPin *
0x1000a21c  mov     ecx, [eax]
0x1000a21e  mov     esi, [ecx+8]
0x1000a221  mov     ecx, esi; this
0x1000a223  jnz     short loc_1000A22F
0x1000a225  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a22b  call    esi
0x1000a22d  jmp     short loc_1000A26C
0x1000a22f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a235  call    esi
0x1000a237  mov     ecx, edi
0x1000a239  call    ?DerefPipeFromPin@@YGHPAUIPin@@@Z; DerefPipeFromPin(IPin *)
0x1000a23e  jmp     short loc_1000A26C
0x1000a240  or      eax, 0FFFFFFFFh
0x1000a243  lock xadd [edi+1C8h], eax
0x1000a24b  jnz     short loc_1000A262
0x1000a24d  mov     eax, [edi]
0x1000a24f  push    1
0x1000a251  mov     esi, [eax+0Ch]
0x1000a254  mov     ecx, esi; this
0x1000a256  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000a25c  mov     ecx, edi
0x1000a25e  call    esi
0x1000a260  jmp     short loc_1000A26C
0x1000a262  mov     ecx, [esp+70h+BytesReturned]
0x1000a266  jmp     short loc_1000A239
0x1000a268  mov     [esp+70h+var_64], esi
0x1000a26c  cmp     [esp+70h+var_60], 0
0x1000a271  mov     esi, [esp+70h+var_64]
0x1000a275  mov     eax, [esp+70h+var_60]
0x1000a279  jnz     loc_1000A018
0x1000a27f  mov     ecx, [esp+70h+OutBuffer]
0x1000a283  lea     edi, [ebx+0ACh]
0x1000a289  mov     edx, [esp+70h+Block]
0x1000a28d  cmp     esi, ecx
0x1000a28f  jb      short loc_1000A29B
0x1000a291  mov     eax, esi
0x1000a293  or      eax, ecx
0x1000a295  jnz     loc_1000A3C2
0x1000a29b  test    edx, edx
0x1000a29d  jnz     loc_1000A3C2
0x1000a2a3  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x1000a2a8  mov     [esp+70h+Block], edx
0x1000a2ac  lea     edi, [esp+70h+InBuffer]
0x1000a2b0  mov     [esp+70h+var_38], edx
0x1000a2b4  lea     eax, [esp+70h+var_38]
0x1000a2b8  push    eax; lpBytesReturned
0x1000a2b9  movsd
0x1000a2ba  lea     eax, [esp+74h+var_44]
0x1000a2be  push    4; nOutBufferSize
0x1000a2c0  push    eax; struct CKsProxy *
0x1000a2c1  push    20h ; ' '; nInBufferSize
0x1000a2c3  movsd
0x1000a2c4  lea     eax, [esp+80h+InBuffer]
0x1000a2c8  push    eax; lpInBuffer
0x1000a2c9  push    2F0003h; dwIoControlCode
0x1000a2ce  push    dword ptr [ebx+0DCh]; hDevice
0x1000a2d4  movsd
0x1000a2d5  movsd
0x1000a2d6  mov     esi, [esp+8Ch+var_5C]
0x1000a2da  mov     [esp+8Ch+var_10], 2
0x1000a2e2  mov     [esp+8Ch+var_C], 1
0x1000a2ed  mov     [esp+8Ch+var_8], esi
0x1000a2f4  mov     [esp+8Ch+var_4], edx
0x1000a2fb  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1000a300  test    eax, eax
0x1000a302  js      loc_1000A4AD
0x1000a308  lea     eax, [esp+70h+Block]
0x1000a30c  mov     edx, esi
0x1000a30e  push    eax; int *
0x1000a30f  push    [esp+74h+var_44]; int *
0x1000a313  mov     ecx, ebx
0x1000a315  call    ?ConstructPinName@CKsProxy@@QAGJKW4KSPIN_DATAFLOW@@PAPAG@Z; CKsProxy::ConstructPinName(ulong,KSPIN_DATAFLOW,ushort * *)
0x1000a31a  test    eax, eax
0x1000a31c  js      loc_1000A4AD
0x1000a322  mov     eax, [esp+70h+var_44]
0x1000a326  mov     [esp+70h+BytesReturned], 0
0x1000a32e  sub     eax, 1
0x1000a331  jz      short loc_1000A35D
0x1000a333  sub     eax, 1
0x1000a336  jnz     short loc_1000A392
0x1000a338  mov     edx, [esp+70h+var_5C]
0x1000a33c  lea     esi, [ebx+28h]
0x1000a33f  sub     esp, 10h
0x1000a342  lea     eax, [esp+80h+BytesReturned]
0x1000a346  mov     edi, esp
0x1000a348  push    [esp+80h+var_30]
0x1000a34c  movsd
0x1000a34d  push    [esp+84h+Block]; struct _GUID
0x1000a351  push    eax; int
0x1000a352  movsd
0x1000a353  push    ebx; unsigned __int16 *
  ... truncated ...
```
