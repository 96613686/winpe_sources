# CKsProxy::CheckMediaType(IUnknown *,ulong,CMediaType const *)

- ea: `0x1000af81`
- end: `0x1000b1e5`
- name: `?CheckMediaType@CKsProxy@@QAGJPAUIUnknown@@KPBVCMediaType@@@Z`
- size: `612`
- prototype: `int(CKsProxy *__hidden this, struct IUnknown *, unsigned int, const struct CMediaType *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x10012260`
- `0x100163a0`
- `0x1001b560`

## callees

- `0x10006415`
- `0x1000af42`
- `0x1000af81`
- `0x1001f1b0`
- `0x10021aad`
- `0x1002d510`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1000b1cd`
- `ole32!CoTaskMemFree` at `0x1000b1cd`

## pseudocode

```c
int __userpurge CKsProxy::CheckMediaType@<eax>(
        IUnknown *a1@<edx>,
        int a2@<ecx>,
        CKsProxy *this,
        struct IUnknown *a4,
        unsigned int a5,
        const struct CMediaType *a6)
{
  int PinFactoryDataRanges; // ebx
  IUnknown_vtbl *v9; // ecx
  _DWORD *v10; // eax
  int v11; // edi
  char *v12; // esi
  int i; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  _DWORD *v19; // edx
  struct IKsDataTypeHandler **v21; // [esp+0h] [ebp-20h]
  unsigned int v22; // [esp+0h] [ebp-20h]
  struct IUnknown **v23; // [esp+4h] [ebp-1Ch]
  void **v24; // [esp+4h] [ebp-1Ch]
  LPVOID pv; // [esp+Ch] [ebp-14h] BYREF
  int v26; // [esp+10h] [ebp-10h] BYREF
  int v27; // [esp+14h] [ebp-Ch] BYREF
  int v28; // [esp+18h] [ebp-8h] BYREF
  LPVOID ppv; // [esp+1Ch] [ebp-4h] BYREF

  pv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      0x15u,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(a2 + 60));
  if ( !a4 || !a1 )
    return -2147467261;
  OpenDataHandler(a1, (int)a4, (const struct CMediaType *)&v26, &ppv, v21, v23);
  if ( v26 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      0x16u,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(a2 + 60));
  PinFactoryDataRanges = CKsProxy::GetPinFactoryDataRanges((CKsProxy *)&pv, v22, v24);
  if ( PinFactoryDataRanges >= 0 )
  {
    if ( v26 )
    {
      PinFactoryDataRanges = (*(int (__thiscall **)(_DWORD, int, LPVOID))(*(_DWORD *)v26 + 16))(
                               *(_DWORD *)(*(_DWORD *)v26 + 16),
                               v26,
                               pv);
      if ( PinFactoryDataRanges == 1 )
        PinFactoryDataRanges = -2147467259;
      if ( ppv )
        (*(void (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)ppv + 8))(*(_DWORD *)(*(_DWORD *)ppv + 8), ppv);
    }
    else
    {
      v9 = a4[15].__vftable;
      if ( v9
        && (*(int (__thiscall **)(_DWORD, IUnknown_vtbl *, GUID *, int *))v9->QueryInterface)(
             *(_DWORD *)v9->QueryInterface,
             v9,
             &_GUID_d559999a_a4c3_11d2_876a_00a0c9223196,
             &v27) >= 0 )
      {
        (*(void (__thiscall **)(_DWORD, int, int *))(*(_DWORD *)v27 + 12))(*(_DWORD *)(*(_DWORD *)v27 + 12), v27, &v28);
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v27 + 8))(*(_DWORD *)(*(_DWORD *)v27 + 8), v27);
      }
      else
      {
        v28 = 0;
      }
      v10 = pv;
      PinFactoryDataRanges = -2147467259;
      v11 = *((_DWORD *)pv + 1);
      v12 = (char *)pv + 8;
      if ( v11 )
      {
        while ( 2 )
        {
          v10[1] = --v11;
          for ( i = 0; i != 4; ++i )
          {
            if ( *(_DWORD *)&v12[4 * i + 16] != *(&_GUID_00000000_0000_0000_0000_000000000000.Data1 + i) )
            {
              v14 = 0;
              while ( a4[v14].__vftable == *(IUnknown_vtbl **)&v12[4 * v14 + 16] )
              {
                if ( ++v14 == 4 )
                {
                  v15 = 0;
                  while ( *(_DWORD *)&v12[4 * v15 + 32] == *(&_GUID_00000000_0000_0000_0000_000000000000.Data1 + v15) )
                  {
                    if ( ++v15 == 4 )
                      goto LABEL_42;
                  }
                  v16 = 0;
                  while ( a4[v16 + 4].__vftable == *(IUnknown_vtbl **)&v12[4 * v16 + 32] )
                  {
                    if ( ++v16 == 4 )
                    {
                      v17 = 0;
                      while ( *(_DWORD *)&v12[4 * v17 + 48] == *(&_GUID_00000000_0000_0000_0000_000000000000.Data1 + v17) )
                      {
                        if ( ++v17 == 4 )
                          goto LABEL_42;
                      }
                      v18 = 0;
                      while ( a4[v18 + 11].__vftable == *(IUnknown_vtbl **)&v12[4 * v18 + 48] )
                      {
                        if ( ++v18 == 4 )
                          goto LABEL_42;
                      }
                      goto LABEL_43;
                    }
                  }
                  goto LABEL_43;
                }
              }
              goto LABEL_43;
            }
          }
LABEL_42:
          if ( (int)KsResolveRequiredAttributes(v12, v28) >= 0 )
          {
            PinFactoryDataRanges = 0;
            goto LABEL_51;
          }
LABEL_43:
          v19 = pv;
          if ( (v12[4] & 2) != 0 )
          {
            v12 += (*(_DWORD *)v12 + 7) & 0xFFFFFFF8;
            *((_DWORD *)pv + 1) = --v11;
          }
          v12 += (*(_DWORD *)v12 + 7) & 0xFFFFFFF8;
          if ( v11 )
          {
            v10 = pv;
            continue;
          }
          break;
        }
      }
      else
      {
        v19 = pv;
      }
      v19[1] = -1;
    }
LABEL_51:
    CoTaskMemFree(pv);
  }
  return PinFactoryDataRanges;
}

```

## disassembly

```asm
0x1000af81  mov     edi, edi
0x1000af83  push    ebp
0x1000af84  mov     ebp, esp
0x1000af86  and     esp, 0FFFFFFF8h
0x1000af89  sub     esp, 14h
0x1000af8c  push    ebx
0x1000af8d  push    esi; void **
0x1000af8e  push    edi; unsigned int
0x1000af8f  mov     edi, edx
0x1000af91  mov     [esp+20h+pv], 0
0x1000af99  mov     esi, ecx
0x1000af9b  mov     eax, _WPP_GLOBAL_Control
0x1000afa0  mov     ebx, offset _WPP_GLOBAL_Control
0x1000afa5  cmp     eax, ebx
0x1000afa7  jz      short loc_1000AFC5
0x1000afa9  cmp     byte ptr [eax+19h], 2
0x1000afad  jb      short loc_1000AFC5
0x1000afaf  push    dword ptr [esi+3Ch]; int
0x1000afb2  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000afb7  push    dword ptr [eax+14h]
0x1000afba  push    dword ptr [eax+10h]; LoggerHandle
0x1000afbd  push    15h
0x1000afbf  pop     ecx; MessageNumber
0x1000afc0  call    _WPP_SF_S@20; WPP_SF_S(x,x,x,x,x)
0x1000afc5  mov     eax, [ebp+arg_4]
0x1000afc8  test    eax, eax
0x1000afca  jz      loc_1000B1D7
0x1000afd0  test    edi, edi
0x1000afd2  jz      loc_1000B1D7
0x1000afd8  lea     ecx, [esp+20h+ppv]
0x1000afdc  mov     edx, edi
0x1000afde  push    ecx; ppv
0x1000afdf  lea     ecx, [esp+24h+var_10]
0x1000afe3  push    ecx; struct CMediaType *
0x1000afe4  mov     ecx, eax
0x1000afe6  call    ?OpenDataHandler@@YGXPBVCMediaType@@PAUIUnknown@@PAPAUIKsDataTypeHandler@@PAPAU2@@Z; OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)
0x1000afeb  cmp     [esp+20h+var_10], 0
0x1000aff0  jz      short loc_1000B017
0x1000aff2  mov     eax, _WPP_GLOBAL_Control
0x1000aff7  cmp     eax, ebx
0x1000aff9  jz      short loc_1000B017
0x1000affb  cmp     byte ptr [eax+19h], 2
0x1000afff  jb      short loc_1000B017
0x1000b001  push    dword ptr [esi+3Ch]; int
0x1000b004  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000b009  push    dword ptr [eax+14h]
0x1000b00c  push    dword ptr [eax+10h]; LoggerHandle
0x1000b00f  push    16h
0x1000b011  pop     ecx; MessageNumber
0x1000b012  call    _WPP_SF_S@20; WPP_SF_S(x,x,x,x,x)
0x1000b017  mov     edx, [ebp+this]
0x1000b01a  lea     eax, [esp+20h+pv]
0x1000b01e  push    eax; this
0x1000b01f  mov     ecx, esi
0x1000b021  call    ?GetPinFactoryDataRanges@CKsProxy@@QAGJKPAPAX@Z; CKsProxy::GetPinFactoryDataRanges(ulong,void * *)
0x1000b026  mov     ebx, eax
0x1000b028  test    ebx, ebx
0x1000b02a  js      loc_1000B1D3
0x1000b030  mov     ecx, [esp+20h+var_10]
0x1000b034  test    ecx, ecx
0x1000b036  jz      short loc_1000B07B
0x1000b038  mov     eax, [ecx]
0x1000b03a  mov     edx, [esp+20h+pv]
0x1000b03e  push    edx
0x1000b03f  push    ecx
0x1000b040  mov     esi, [eax+10h]
0x1000b043  mov     ecx, esi; this
0x1000b045  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000b04b  call    esi
0x1000b04d  mov     ecx, [esp+20h+ppv]
0x1000b051  mov     ebx, eax
0x1000b053  cmp     ebx, 1
0x1000b056  mov     eax, 80004005h
0x1000b05b  cmovz   ebx, eax
0x1000b05e  test    ecx, ecx
0x1000b060  jz      loc_1000B1C9
0x1000b066  mov     eax, [ecx]
0x1000b068  push    ecx
0x1000b069  mov     esi, [eax+8]
0x1000b06c  mov     ecx, esi; this
0x1000b06e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000b074  call    esi
0x1000b076  jmp     loc_1000B1C9
0x1000b07b  mov     ecx, [ebp+arg_4]
0x1000b07e  mov     ecx, [ecx+3Ch]
0x1000b081  test    ecx, ecx
0x1000b083  jz      short loc_1000B0D1
0x1000b085  mov     eax, [ecx]
0x1000b087  mov     esi, [eax]
0x1000b089  lea     eax, [esp+20h+var_C]
0x1000b08d  push    eax
0x1000b08e  push    offset __GUID_d559999a_a4c3_11d2_876a_00a0c9223196
0x1000b093  push    ecx
0x1000b094  mov     ecx, esi; this
0x1000b096  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000b09c  call    esi
0x1000b09e  test    eax, eax
0x1000b0a0  js      short loc_1000B0D1
0x1000b0a2  mov     eax, [esp+20h+var_C]
0x1000b0a6  lea     edx, [esp+20h+var_8]
0x1000b0aa  push    edx
0x1000b0ab  push    eax
0x1000b0ac  mov     ecx, [eax]
0x1000b0ae  mov     esi, [ecx+0Ch]
0x1000b0b1  mov     ecx, esi; this
0x1000b0b3  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000b0b9  call    esi
0x1000b0bb  mov     eax, [esp+20h+var_C]
0x1000b0bf  push    eax
0x1000b0c0  mov     ecx, [eax]
0x1000b0c2  mov     esi, [ecx+8]
0x1000b0c5  mov     ecx, esi; this
0x1000b0c7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000b0cd  call    esi
0x1000b0cf  jmp     short loc_1000B0D9
0x1000b0d1  mov     [esp+20h+var_8], 0
0x1000b0d9  mov     eax, [esp+20h+pv]
0x1000b0dd  mov     ebx, 80004005h
0x1000b0e2  mov     edi, [eax+4]
0x1000b0e5  lea     esi, [eax+8]
0x1000b0e8  test    edi, edi
0x1000b0ea  jz      loc_1000B1BF
0x1000b0f0  dec     edi
0x1000b0f1  mov     edx, offset __GUID_00000000_0000_0000_0000_000000000000
0x1000b0f6  mov     [eax+4], edi
0x1000b0f9  xor     ecx, ecx
0x1000b0fb  mov     eax, [esi+ecx*4+10h]
0x1000b0ff  cmp     eax, [edx+ecx*4]
0x1000b102  jnz     short loc_1000B10C
0x1000b104  inc     ecx
0x1000b105  cmp     ecx, 4
0x1000b108  jnz     short loc_1000B0FB
0x1000b10a  jmp     short loc_1000B17A
0x1000b10c  mov     edx, [ebp+arg_4]
0x1000b10f  xor     ecx, ecx
0x1000b111  mov     eax, [edx+ecx*4]
0x1000b114  cmp     eax, [esi+ecx*4+10h]
0x1000b118  jnz     short loc_1000B188
0x1000b11a  inc     ecx
0x1000b11b  cmp     ecx, 4
0x1000b11e  jnz     short loc_1000B111
0x1000b120  xor     ecx, ecx
0x1000b122  mov     eax, [esi+ecx*4+20h]
0x1000b126  mov     edx, offset __GUID_00000000_0000_0000_0000_000000000000
0x1000b12b  cmp     eax, [edx+ecx*4]
0x1000b12e  mov     edx, [ebp+arg_4]
0x1000b131  jnz     short loc_1000B13B
0x1000b133  inc     ecx
0x1000b134  cmp     ecx, 4
0x1000b137  jnz     short loc_1000B122
0x1000b139  jmp     short loc_1000B17A
0x1000b13b  xor     ecx, ecx
0x1000b13d  mov     eax, [edx+ecx*4+10h]
0x1000b141  cmp     eax, [esi+ecx*4+20h]
0x1000b145  jnz     short loc_1000B188
0x1000b147  inc     ecx
0x1000b148  cmp     ecx, 4
0x1000b14b  jnz     short loc_1000B13D
0x1000b14d  xor     ecx, ecx
0x1000b14f  mov     eax, [esi+ecx*4+30h]
0x1000b153  mov     edx, offset __GUID_00000000_0000_0000_0000_000000000000
0x1000b158  cmp     eax, [edx+ecx*4]
0x1000b15b  mov     edx, [ebp+arg_4]
0x1000b15e  jnz     short loc_1000B168
0x1000b160  inc     ecx
0x1000b161  cmp     ecx, 4
0x1000b164  jnz     short loc_1000B14F
0x1000b166  jmp     short loc_1000B17A
0x1000b168  xor     ecx, ecx
0x1000b16a  mov     eax, [edx+ecx*4+2Ch]
0x1000b16e  cmp     eax, [esi+ecx*4+30h]
0x1000b172  jnz     short loc_1000B188
0x1000b174  inc     ecx
0x1000b175  cmp     ecx, 4
0x1000b178  jnz     short loc_1000B16A
0x1000b17a  push    [esp+20h+var_8]
0x1000b17e  push    esi
0x1000b17f  call    _KsResolveRequiredAttributes@8; KsResolveRequiredAttributes(x,x)
0x1000b184  test    eax, eax
0x1000b186  jns     short loc_1000B1B7
0x1000b188  test    byte ptr [esi+4], 2
0x1000b18c  mov     edx, [esp+20h+pv]
0x1000b190  jz      short loc_1000B1A0
0x1000b192  mov     eax, [esi]
0x1000b194  add     eax, 7
0x1000b197  and     eax, 0FFFFFFF8h
0x1000b19a  add     esi, eax
0x1000b19c  dec     edi
0x1000b19d  mov     [edx+4], edi
0x1000b1a0  mov     eax, [esi]
0x1000b1a2  add     eax, 7
0x1000b1a5  and     eax, 0FFFFFFF8h
0x1000b1a8  add     esi, eax
0x1000b1aa  test    edi, edi
0x1000b1ac  jz      short loc_1000B1BB
0x1000b1ae  mov     eax, [esp+20h+pv]
0x1000b1b2  jmp     loc_1000B0F0
0x1000b1b7  xor     ebx, ebx
0x1000b1b9  jmp     short loc_1000B1C9
0x1000b1bb  xor     edi, edi
0x1000b1bd  jmp     short loc_1000B1C3
0x1000b1bf  mov     edx, [esp+20h+pv]
0x1000b1c3  lea     eax, [edi-1]
0x1000b1c6  mov     [edx+4], eax
0x1000b1c9  push    [esp+20h+pv]; pv
0x1000b1cd  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1000b1d3  mov     eax, ebx
0x1000b1d5  jmp     short loc_1000B1DC
0x1000b1d7  mov     eax, 80004003h
0x1000b1dc  pop     edi
0x1000b1dd  pop     esi
0x1000b1de  pop     ebx
0x1000b1df  mov     esp, ebp
0x1000b1e1  pop     ebp
0x1000b1e2  retn    8
```
