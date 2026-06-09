# CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)

- ea: `0x10017be0`
- end: `0x10017e4e`
- name: `?GetStreamCaps@CKsOutputPin@@UAGJHPAPAU_AMMediaType@@PAE@Z`
- size: `622`
- prototype: `int(CKsOutputPin *__hidden this, int, struct _AMMediaType **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1001c710`
- `0x1001e1f8`

## callees

- `0x10017be0`
- `0x1001fbb0`
- `0x1001ff00`
- `0x1001ffa0`
- `0x1002d510`
- `0x100302a7`
- `0x1003b5e4`
- `0x1003bcec`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10017c34`
- `ole32!CoTaskMemAlloc` at `0x10017c34`
- `ole32!CoTaskMemFree` at `0x10017e29`
- `ole32!CoTaskMemFree` at `0x10017e29`

## pseudocode

```c
int __stdcall CKsOutputPin::GetStreamCaps(
        CKsOutputPin *this,
        unsigned int a2,
        struct _AMMediaType **a3,
        unsigned __int8 *a4)
{
  int bTemporalCompression; // edi
  void *v5; // eax
  int result; // eax
  unsigned int v7; // ebx
  struct _AMMediaType *v8; // eax
  int v9; // edi
  void *v10; // eax
  int v11; // edi
  void *v12; // eax
  int v13; // edi
  void *v14; // eax
  char *v15; // esi
  CMediaType *v16; // edi
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  _DWORD *v23; // edx
  struct _AMMediaType *v24; // [esp+4h] [ebp-18h]
  LPVOID pv; // [esp+10h] [ebp-Ch] BYREF
  char *v26; // [esp+14h] [ebp-8h]
  int MediaType; // [esp+18h] [ebp-4h] BYREF

  bTemporalCompression = this->m_mt.bTemporalCompression;
  v5 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12))(
                 *(_DWORD *)(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12),
                 this[-1].m_PropagatingAcquire + 108);
  result = KsGetMediaTypeCount(v5, bTemporalCompression, (int)&MediaType);
  if ( result >= 0 )
  {
    v7 = a2;
    if ( a2 < MediaType )
    {
      v8 = (struct _AMMediaType *)CoTaskMemAlloc(0x48u);
      *a3 = v8;
      if ( v8 )
      {
        memset((void *)v8, 0, sizeof(struct _AMMediaType));
        v9 = this->m_mt.bTemporalCompression;
        v10 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12))(
                        *(_DWORD *)(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12),
                        this[-1].m_PropagatingAcquire + 108);
        MediaType = KsGetMediaType(a2, (CMediaType *)*a3, v10, v9);
        if ( MediaType < 0
          || (v11 = this->m_mt.bTemporalCompression,
              v12 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12))(
                              *(_DWORD *)(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12),
                              this[-1].m_PropagatingAcquire + 108),
              KsGetMultiplePinFactoryItems(v12, v11, 13, &pv) < 0)
          && (v13 = this->m_mt.bTemporalCompression,
              v14 = (void *)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12))(
                              *(_DWORD *)(*(_DWORD *)(this[-1].m_PropagatingAcquire + 108) + 12),
                              this[-1].m_PropagatingAcquire + 108),
              MediaType = KsGetMultiplePinFactoryItems(v14, v13, 3, &pv),
              MediaType < 0) )
        {
          DeleteMediaType(v24);
          *a3 = 0;
        }
        else
        {
          v15 = (char *)pv + 8;
          v26 = (char *)pv + 8;
          if ( a2 )
          {
            do
            {
              --v7;
              if ( (v15[4] & 2) != 0 )
              {
                --v7;
                v15 += (*(_DWORD *)v15 + 7) & 0xFFFFFFF8;
              }
              v15 += (*(_DWORD *)v15 + 7) & 0xFFFFFFF8;
            }
            while ( v7 );
            v26 = v15;
          }
          v16 = (CMediaType *)*a3;
          if ( !memcmp(*a3, &MEDIATYPE_Video, 0x10u) )
          {
            v17 = 0;
            while ( *(&v16->formattype.Data1 + v17) == *(&_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1 + v17) )
            {
              if ( ++v17 == 4 )
              {
LABEL_30:
                qmemcpy(a4, v15 + 80, 0x80u);
                goto LABEL_39;
              }
            }
            v18 = 0;
            while ( *(&v16->formattype.Data1 + v18) == *(&_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1 + v18) )
            {
              if ( ++v18 == 4 )
                goto LABEL_30;
            }
            v19 = 0;
            while ( *(&v16->formattype.Data1 + v19) == *(&_GUID_05589f82_c356_11ce_bf01_00aa0055595a.Data1 + v19) )
            {
              if ( ++v19 == 4 )
                goto LABEL_30;
            }
            v20 = 0;
            while ( *(&v16->formattype.Data1 + v20) == *(&_GUID_e06d80e3_db46_11cf_b4d1_00805f6cbbea.Data1 + v20) )
            {
              if ( ++v20 == 4 )
                goto LABEL_30;
            }
          }
          v21 = 0;
          while ( *(&v16->majortype.Data1 + v21) == *(&MEDIATYPE_Audio.Data1 + v21) )
          {
            if ( ++v21 == 4 )
            {
              v22 = 0;
              while ( *(&v16->formattype.Data1 + v22) == *(&_GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data1 + v22) )
              {
                if ( ++v22 == 4 )
                {
                  v23 = v26;
                  *(GUID *)a4 = MEDIATYPE_Audio;
                  *((_DWORD *)a4 + 4) = 1;
                  *((_DWORD *)a4 + 5) = v23[16];
                  *((_DWORD *)a4 + 6) = 1;
                  *((_DWORD *)a4 + 7) = v23[17];
                  *((_DWORD *)a4 + 8) = v23[18];
                  *((_DWORD *)a4 + 9) = 1;
                  *((_DWORD *)a4 + 10) = v23[19];
                  *((_DWORD *)a4 + 11) = v23[20];
                  *((_DWORD *)a4 + 12) = 1;
                  goto LABEL_39;
                }
              }
              break;
            }
          }
          *(GUID *)a4 = _GUID_00000000_0000_0000_0000_000000000000;
LABEL_39:
          CoTaskMemFree(pv);
        }
        return MediaType;
      }
      else
      {
        return -2147024882;
      }
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10017be0  mov     edi, edi
0x10017be2  push    ebp
0x10017be3  mov     ebp, esp
0x10017be5  and     esp, 0FFFFFFF8h
0x10017be8  mov     eax, [ebp+this]
0x10017beb  sub     esp, 0Ch
0x10017bee  push    ebx
0x10017bef  push    esi
0x10017bf0  push    edi; struct _AMMediaType *
0x10017bf1  mov     edi, [eax+58h]
0x10017bf4  mov     eax, [eax-104h]
0x10017bfa  add     eax, 6Ch ; 'l'
0x10017bfd  push    eax
0x10017bfe  mov     ecx, [eax]
0x10017c00  mov     esi, [ecx+0Ch]
0x10017c03  mov     ecx, esi; this
0x10017c05  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10017c0b  call    esi
0x10017c0d  lea     ecx, [esp+18h+var_4]
0x10017c11  push    ecx; int
0x10017c12  push    edi; int
0x10017c13  push    eax; hDevice
0x10017c14  call    _KsGetMediaTypeCount@12; KsGetMediaTypeCount(x,x,x)
0x10017c19  test    eax, eax
0x10017c1b  js      loc_10017E45
0x10017c21  mov     ebx, [ebp+arg_4]
0x10017c24  cmp     ebx, [esp+18h+var_4]
0x10017c28  jb      short loc_10017C32
0x10017c2a  xor     eax, eax
0x10017c2c  inc     eax
0x10017c2d  jmp     loc_10017E45
0x10017c32  push    48h ; 'H'; cb
0x10017c34  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10017c3a  mov     ecx, [ebp+arg_8]
0x10017c3d  mov     [ecx], eax
0x10017c3f  test    eax, eax
0x10017c41  jnz     short loc_10017C4D
0x10017c43  mov     eax, 8007000Eh
0x10017c48  jmp     loc_10017E45
0x10017c4d  push    48h ; 'H'; Size
0x10017c4f  push    0; Val
0x10017c51  push    eax; void *
0x10017c52  call    _memset
0x10017c57  mov     eax, [ebp+this]
0x10017c5a  add     esp, 0Ch
0x10017c5d  mov     edi, [eax+58h]
0x10017c60  mov     eax, [eax-104h]
0x10017c66  add     eax, 6Ch ; 'l'
0x10017c69  push    eax
0x10017c6a  mov     ecx, [eax]
0x10017c6c  mov     esi, [ecx+0Ch]
0x10017c6f  mov     ecx, esi; this
0x10017c71  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10017c77  call    esi
0x10017c79  push    edi; int
0x10017c7a  push    eax; hDevice
0x10017c7b  mov     eax, [ebp+arg_8]
0x10017c7e  push    dword ptr [eax]; CMediaType *
0x10017c80  push    ebx; int
0x10017c81  call    _KsGetMediaType@16; KsGetMediaType(x,x,x,x)
0x10017c86  mov     esi, eax
0x10017c88  mov     [esp+18h+var_4], esi
0x10017c8c  test    esi, esi
0x10017c8e  js      loc_10017E31
0x10017c94  mov     eax, [ebp+this]
0x10017c97  mov     ecx, [eax-104h]
0x10017c9d  mov     edi, [eax+58h]
0x10017ca0  add     ecx, 6Ch ; 'l'
0x10017ca3  push    ecx
0x10017ca4  mov     edx, [ecx]
0x10017ca6  mov     esi, [edx+0Ch]
0x10017ca9  mov     ecx, esi; this
0x10017cab  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10017cb1  call    esi
0x10017cb3  lea     ecx, [esp+18h+pv]
0x10017cb7  push    ecx; int
0x10017cb8  push    0Dh; int
0x10017cba  push    edi; int
0x10017cbb  push    eax; hDevice
0x10017cbc  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x10017cc1  test    eax, eax
0x10017cc3  jns     short loc_10017CFE
0x10017cc5  mov     eax, [ebp+this]
0x10017cc8  mov     edi, [eax+58h]
0x10017ccb  mov     eax, [eax-104h]
0x10017cd1  add     eax, 6Ch ; 'l'
0x10017cd4  push    eax
0x10017cd5  mov     ecx, [eax]
0x10017cd7  mov     esi, [ecx+0Ch]
0x10017cda  mov     ecx, esi; this
0x10017cdc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10017ce2  call    esi
0x10017ce4  lea     ecx, [esp+18h+pv]
0x10017ce8  push    ecx; int
0x10017ce9  push    3; int
0x10017ceb  push    edi; int
0x10017cec  push    eax; hDevice
0x10017ced  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x10017cf2  mov     [esp+18h+var_4], eax
0x10017cf6  test    eax, eax
0x10017cf8  js      loc_10017E31
0x10017cfe  mov     esi, [esp+18h+pv]
0x10017d02  add     esi, 8
0x10017d05  mov     [esp+18h+var_8], esi
0x10017d09  test    ebx, ebx
0x10017d0b  jz      short loc_10017D31
0x10017d0d  dec     ebx
0x10017d0e  test    byte ptr [esi+4], 2
0x10017d12  jz      short loc_10017D1F
0x10017d14  mov     eax, [esi]
0x10017d16  dec     ebx
0x10017d17  add     eax, 7
0x10017d1a  and     eax, 0FFFFFFF8h
0x10017d1d  add     esi, eax
0x10017d1f  mov     eax, [esi]
0x10017d21  add     eax, 7
0x10017d24  and     eax, 0FFFFFFF8h
0x10017d27  add     esi, eax
0x10017d29  test    ebx, ebx
0x10017d2b  jnz     short loc_10017D0D
0x10017d2d  mov     [esp+18h+var_8], esi
0x10017d31  mov     eax, [ebp+arg_8]
0x10017d34  push    10h; Size
0x10017d36  push    offset _MEDIATYPE_Video; Buf2
0x10017d3b  mov     edi, [eax]
0x10017d3d  push    edi; Buf1
0x10017d3e  call    _memcmp
0x10017d43  add     esp, 0Ch
0x10017d46  push    4
0x10017d48  pop     edx
0x10017d49  test    eax, eax
0x10017d4b  jnz     short loc_10017DB4
0x10017d4d  mov     ebx, offset __GUID_05589f80_c356_11ce_bf01_00aa0055595a
0x10017d52  xor     ecx, ecx
0x10017d54  mov     eax, [edi+ecx*4+2Ch]
0x10017d58  cmp     eax, [ebx+ecx*4]
0x10017d5b  jnz     short loc_10017D64
0x10017d5d  inc     ecx
0x10017d5e  cmp     ecx, edx
0x10017d60  jnz     short loc_10017D54
0x10017d62  jmp     short loc_10017DA7
0x10017d64  mov     ebx, offset __GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba
0x10017d69  xor     ecx, ecx
0x10017d6b  mov     eax, [edi+ecx*4+2Ch]
0x10017d6f  cmp     eax, [ebx+ecx*4]
0x10017d72  jnz     short loc_10017D7B
0x10017d74  inc     ecx
0x10017d75  cmp     ecx, edx
0x10017d77  jnz     short loc_10017D6B
0x10017d79  jmp     short loc_10017DA7
0x10017d7b  mov     ebx, offset __GUID_05589f82_c356_11ce_bf01_00aa0055595a
0x10017d80  xor     ecx, ecx
0x10017d82  mov     eax, [edi+ecx*4+2Ch]
0x10017d86  cmp     eax, [ebx+ecx*4]
0x10017d89  jnz     short loc_10017D92
0x10017d8b  inc     ecx
0x10017d8c  cmp     ecx, edx
0x10017d8e  jnz     short loc_10017D82
0x10017d90  jmp     short loc_10017DA7
0x10017d92  mov     ebx, offset __GUID_e06d80e3_db46_11cf_b4d1_00805f6cbbea
0x10017d97  xor     ecx, ecx
0x10017d99  mov     eax, [edi+ecx*4+2Ch]
0x10017d9d  cmp     eax, [ebx+ecx*4]
0x10017da0  jnz     short loc_10017DB4
0x10017da2  inc     ecx
0x10017da3  cmp     ecx, edx
0x10017da5  jnz     short loc_10017D99
0x10017da7  mov     edi, [ebp+arg_C]
0x10017daa  add     esi, 50h ; 'P'
0x10017dad  push    20h ; ' '
0x10017daf  pop     ecx
0x10017db0  rep movsd
0x10017db2  jmp     short loc_10017E25
0x10017db4  mov     esi, offset _MEDIATYPE_Audio
0x10017db9  xor     ecx, ecx
0x10017dbb  mov     eax, [edi+ecx*4]
0x10017dbe  cmp     eax, [esi+ecx*4]
0x10017dc1  jnz     short loc_10017E19
0x10017dc3  inc     ecx
0x10017dc4  cmp     ecx, edx
0x10017dc6  jnz     short loc_10017DBB
0x10017dc8  mov     ebx, offset __GUID_05589f81_c356_11ce_bf01_00aa0055595a
0x10017dcd  xor     ecx, ecx
0x10017dcf  mov     eax, [edi+ecx*4+2Ch]
0x10017dd3  cmp     eax, [ebx+ecx*4]
0x10017dd6  jnz     short loc_10017E19
0x10017dd8  inc     ecx
0x10017dd9  cmp     ecx, edx
0x10017ddb  jnz     short loc_10017DCF
0x10017ddd  mov     ecx, [ebp+arg_C]
0x10017de0  mov     edi, ecx
0x10017de2  mov     edx, [esp+18h+var_8]
0x10017de6  movsd
0x10017de7  movsd
0x10017de8  movsd
0x10017de9  movsd
0x10017dea  xor     esi, esi
0x10017dec  inc     esi
0x10017ded  mov     [ecx+10h], esi
0x10017df0  mov     eax, [edx+40h]
0x10017df3  mov     [ecx+14h], eax
0x10017df6  mov     [ecx+18h], esi
0x10017df9  mov     eax, [edx+44h]
0x10017dfc  mov     [ecx+1Ch], eax
0x10017dff  mov     eax, [edx+48h]
0x10017e02  mov     [ecx+20h], eax
0x10017e05  mov     [ecx+24h], esi
0x10017e08  mov     eax, [edx+4Ch]
0x10017e0b  mov     [ecx+28h], eax
0x10017e0e  mov     eax, [edx+50h]
0x10017e11  mov     [ecx+2Ch], eax
0x10017e14  mov     [ecx+30h], esi
0x10017e17  jmp     short loc_10017E25
0x10017e19  mov     edi, [ebp+arg_C]
0x10017e1c  mov     esi, offset __GUID_00000000_0000_0000_0000_000000000000
0x10017e21  movsd
0x10017e22  movsd
0x10017e23  movsd
0x10017e24  movsd
0x10017e25  push    [esp+18h+pv]; pv
0x10017e29  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10017e2f  jmp     short loc_10017E41
0x10017e31  mov     ebx, [ebp+arg_8]
0x10017e34  mov     ecx, [ebx]
0x10017e36  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x10017e3b  mov     dword ptr [ebx], 0
0x10017e41  mov     eax, [esp+18h+var_4]
0x10017e45  pop     edi
0x10017e46  pop     esi
0x10017e47  pop     ebx
0x10017e48  mov     esp, ebp
0x10017e4a  pop     ebp
0x10017e4b  retn    10h
```
