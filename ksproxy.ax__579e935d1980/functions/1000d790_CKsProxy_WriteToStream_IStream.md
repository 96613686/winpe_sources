# CKsProxy::WriteToStream(IStream *)

- ea: `0x1000d790`
- end: `0x1000da0c`
- name: `?WriteToStream@CKsProxy@@UAEJPAUIStream@@@Z`
- size: `636`
- prototype: `int __thiscall(CKsProxy *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x10009f00`
- `0x1000adfd`
- `0x1000aea8`
- `0x1000d790`
- `0x1002d510`
- `0x1003035c`
- `0x1003aba0`

## pseudocode

```c
int __thiscall CKsProxy::WriteToStream(CKsProxy *this, struct IStream *a2)
{
  void *m_FilterHandle; // edx
  int v4; // esi
  IStream_vtbl *v5; // eax
  IStream_vtbl *v6; // eax
  int v7; // eax
  ISpecifyPropertyPages_vtbl *v8; // ebx
  unsigned int (__stdcall *Release)(IUnknown *); // eax
  CKsProxy *v11; // [esp+58h] [ebp-88h]
  unsigned int v12; // [esp+58h] [ebp-88h]
  struct CBasePin *v13; // [esp+5Ch] [ebp-84h]
  enum KSPIN_COMMUNICATION *v14; // [esp+5Ch] [ebp-84h]
  unsigned int v15; // [esp+68h] [ebp-78h] BYREF
  unsigned int v16; // [esp+6Ch] [ebp-74h]
  int PinFactoryId; // [esp+70h] [ebp-70h] BYREF
  unsigned int (__stdcall *v18)(IUnknown *); // [esp+74h] [ebp-6Ch]
  __int64 v19; // [esp+78h] [ebp-68h]
  _DWORD v20[2]; // [esp+80h] [ebp-60h] BYREF
  _DWORD v21[2]; // [esp+88h] [ebp-58h] BYREF
  _BYTE v22[60]; // [esp+90h] [ebp-50h] BYREF
  int v23; // [esp+CCh] [ebp-14h]
  int v24; // [esp+D0h] [ebp-10h]
  int v25; // [esp+D4h] [ebp-Ch]

  m_FilterHandle = this->m_FilterHandle;
  v21[1] = this;
  if ( !m_FilterHandle )
    return -2147418113;
  v4 = (*(int (__thiscall **)(_DWORD, void *, struct IStream *, int))(*(_DWORD *)m_FilterHandle + 24))(
         *(_DWORD *)(*(_DWORD *)m_FilterHandle + 24),
         m_FilterHandle,
         a2,
         1);
  if ( v4 >= 0 )
  {
    v5 = a2->__vftable;
    v19 = 0;
    v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _LARGE_INTEGER, unsigned int, _ULARGE_INTEGER *), struct IStream *, _DWORD, _DWORD, int, _DWORD *))v5->Seek)(
           v5->Seek,
           a2,
           0,
           0,
           1,
           v20);
    if ( v4 >= 0 )
    {
      v6 = a2->__vftable;
      v21[0] = 0;
      v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, const void *, unsigned int, unsigned int *), struct IStream *, _DWORD *, int, _DWORD))v6->Write)(
             v6->Write,
             a2,
             v21,
             4,
             0);
      v8 = this->ISpecifyPropertyPages::IUnknown::__vftable;
      v4 = v7;
      while ( v4 >= 0 )
      {
        if ( !v8 )
        {
          v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _LARGE_INTEGER, unsigned int, _ULARGE_INTEGER *), struct IStream *, _DWORD, _DWORD, int, unsigned int *))a2->Seek)(
                 a2->Seek,
                 a2,
                 v19,
                 HIDWORD(v19),
                 1,
                 &v15);
          if ( v4 >= 0 )
          {
            PinFactoryId = v15 - v20[0] - 4;
            if ( __PAIR64__(v16, v15) )
            {
              v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _LARGE_INTEGER, unsigned int, _ULARGE_INTEGER *), struct IStream *, _DWORD, _DWORD, _DWORD, _DWORD *))a2->Seek)(
                     a2->Seek,
                     a2,
                     v20[0],
                     v20[1],
                     0,
                     v20);
              if ( v4 >= 0 )
              {
                v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, const void *, unsigned int, unsigned int *), struct IStream *, int *, int, _DWORD))a2->Write)(
                       a2->Write,
                       a2,
                       &PinFactoryId,
                       4,
                       0);
                if ( v4 >= 0 )
                  return ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, _LARGE_INTEGER, unsigned int, _ULARGE_INTEGER *), struct IStream *, unsigned int, unsigned int, _DWORD, unsigned int *))a2->Seek)(
                           a2->Seek,
                           a2,
                           v15,
                           v16,
                           0,
                           &v15);
              }
            }
          }
          return v4;
        }
        Release = v8->Release;
        v8 = (ISpecifyPropertyPages_vtbl *)v8->AddRef;
        v18 = Release;
        if ( CKsProxy::GetPinHandle(v11, v13) )
        {
          PinFactoryId = CKsProxy::GetPinFactoryId(v11, v13);
          if ( CKsProxy::GetPinFactoryCommunication((CKsProxy *)&v15, v12, v14) >= 0 && (v15 & 4) != 0 )
          {
            v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, const void *, unsigned int, unsigned int *), struct IStream *, int *, int, _DWORD))a2->Write)(
                   a2->Write,
                   a2,
                   &PinFactoryId,
                   4,
                   0);
            if ( v4 < 0 )
              return v4;
            (*(void (__thiscall **)(_DWORD, int, _BYTE *))(*((_DWORD *)v18 + 3) + 28))(
              *(_DWORD *)(*((_DWORD *)v18 + 3) + 28),
              (int)v18 + 12,
              v22);
            if ( v23 )
            {
              (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v23 + 8))(*(_DWORD *)(*(_DWORD *)v23 + 8), v23);
              v23 = 0;
            }
            v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, const void *, unsigned int, unsigned int *), struct IStream *, _BYTE *, int, _DWORD))a2->Write)(
                   a2->Write,
                   a2,
                   v22,
                   72,
                   0);
            if ( v4 >= 0 && v24 )
              v4 = ((int (__thiscall *)(HRESULT (__stdcall *)(ISequentialStream *, const void *, unsigned int, unsigned int *), struct IStream *, int, int, _DWORD))a2->Write)(
                     a2->Write,
                     a2,
                     v25,
                     v24,
                     0);
            FreeMediaType((int)v22);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1000d790  mov     edi, edi
0x1000d792  push    ebp
0x1000d793  mov     ebp, esp
0x1000d795  and     esp, 0FFFFFFF8h
0x1000d798  sub     esp, 7Ch
0x1000d79b  mov     eax, ___security_cookie
0x1000d7a0  xor     eax, esp
0x1000d7a2  mov     [esp+7Ch+var_4], eax
0x1000d7a6  push    ebx
0x1000d7a7  mov     ebx, ecx
0x1000d7a9  push    esi
0x1000d7aa  push    edi
0x1000d7ab  mov     edi, [ebp+arg_0]
0x1000d7ae  mov     edx, [ebx+0DCh]
0x1000d7b4  mov     [esp+88h+var_54], ebx
0x1000d7b8  test    edx, edx
0x1000d7ba  jz      loc_1000D9EE
0x1000d7c0  mov     eax, [edx]
0x1000d7c2  push    1
0x1000d7c4  push    edi
0x1000d7c5  push    edx
0x1000d7c6  mov     esi, [eax+18h]
0x1000d7c9  mov     ecx, esi; this
0x1000d7cb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d7d1  call    esi
0x1000d7d3  mov     esi, eax
0x1000d7d5  test    esi, esi
0x1000d7d7  js      loc_1000D9F3
0x1000d7dd  mov     eax, [edi]
0x1000d7df  xorps   xmm0, xmm0
0x1000d7e2  movlpd  qword ptr [esp+88h+var_68], xmm0
0x1000d7e8  mov     esi, [eax+14h]
0x1000d7eb  lea     eax, [esp+88h+var_60]
0x1000d7ef  push    eax
0x1000d7f0  push    1
0x1000d7f2  push    [esp+90h+var_64]
0x1000d7f6  mov     ecx, esi; this
0x1000d7f8  push    [esp+94h+var_68]
0x1000d7fc  push    edi
0x1000d7fd  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d803  call    esi
0x1000d805  mov     esi, eax
0x1000d807  test    esi, esi
0x1000d809  js      loc_1000D9F3
0x1000d80f  mov     eax, [edi]
0x1000d811  push    0
0x1000d813  push    4
0x1000d815  mov     [esp+90h+var_58], 0
0x1000d81d  mov     esi, [eax+10h]
0x1000d820  lea     eax, [esp+90h+var_58]
0x1000d824  push    eax
0x1000d825  push    edi
0x1000d826  mov     ecx, esi; this
0x1000d828  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d82e  call    esi
0x1000d830  mov     ebx, [ebx+5Ch]
0x1000d833  mov     esi, eax
0x1000d835  jmp     loc_1000D93B
0x1000d83a  test    ebx, ebx
0x1000d83c  jz      loc_1000D948
0x1000d842  mov     eax, [ebx+8]
0x1000d845  mov     edx, eax
0x1000d847  mov     ebx, [ebx+4]
0x1000d84a  mov     [esp+88h+var_6C], eax
0x1000d84e  call    ?GetPinHandle@CKsProxy@@QAGPAXPAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x1000d853  test    eax, eax
0x1000d855  jz      loc_1000D93B
0x1000d85b  mov     edx, [esp+88h+var_6C]
0x1000d85f  call    ?GetPinFactoryId@CKsProxy@@QAGKPAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x1000d864  lea     ecx, [esp+88h+var_78]
0x1000d868  mov     dword ptr [esp+88h+var_74+4], eax
0x1000d86c  push    ecx; this
0x1000d86d  mov     ecx, [esp+8Ch+var_54]
0x1000d871  mov     edx, eax
0x1000d873  add     ecx, 0FFFFFFB0h
0x1000d876  call    ?GetPinFactoryCommunication@CKsProxy@@QAGJKPAW4KSPIN_COMMUNICATION@@@Z; CKsProxy::GetPinFactoryCommunication(ulong,KSPIN_COMMUNICATION *)
0x1000d87b  test    eax, eax
0x1000d87d  js      loc_1000D93B
0x1000d883  test    byte ptr [esp+88h+var_78], 4
0x1000d888  jz      loc_1000D93B
0x1000d88e  mov     eax, [edi]
0x1000d890  push    0
0x1000d892  push    4
0x1000d894  mov     esi, [eax+10h]
0x1000d897  lea     eax, [esp+90h+var_74+4]
0x1000d89b  push    eax
0x1000d89c  push    edi
0x1000d89d  mov     ecx, esi; this
0x1000d89f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d8a5  call    esi
0x1000d8a7  mov     esi, eax
0x1000d8a9  test    esi, esi
0x1000d8ab  js      loc_1000D9F3
0x1000d8b1  mov     eax, [esp+88h+var_6C]
0x1000d8b5  lea     edx, [esp+88h+var_50]
0x1000d8b9  add     eax, 0Ch
0x1000d8bc  push    edx
0x1000d8bd  push    eax
0x1000d8be  mov     ecx, [eax]
0x1000d8c0  mov     esi, [ecx+1Ch]
0x1000d8c3  mov     ecx, esi; this
0x1000d8c5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d8cb  call    esi
0x1000d8cd  mov     ecx, [esp+88h+var_14]
0x1000d8d1  test    ecx, ecx
0x1000d8d3  jz      short loc_1000D8ED
0x1000d8d5  mov     eax, [ecx]
0x1000d8d7  push    ecx
0x1000d8d8  mov     esi, [eax+8]
0x1000d8db  mov     ecx, esi; this
0x1000d8dd  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d8e3  call    esi
0x1000d8e5  mov     [esp+88h+var_14], 0
0x1000d8ed  mov     eax, [edi]
0x1000d8ef  push    0
0x1000d8f1  push    48h ; 'H'
0x1000d8f3  mov     esi, [eax+10h]
0x1000d8f6  lea     eax, [esp+90h+var_50]
0x1000d8fa  push    eax
0x1000d8fb  push    edi
0x1000d8fc  mov     ecx, esi; this
0x1000d8fe  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d904  call    esi
0x1000d906  mov     esi, eax
0x1000d908  test    esi, esi
0x1000d90a  js      short loc_1000D932
0x1000d90c  cmp     [esp+88h+var_10], 0
0x1000d911  jz      short loc_1000D932
0x1000d913  mov     eax, [edi]
0x1000d915  push    0
0x1000d917  push    [esp+8Ch+var_10]
0x1000d91b  push    [esp+90h+var_C]
0x1000d922  mov     esi, [eax+10h]
0x1000d925  mov     ecx, esi; this
0x1000d927  push    edi
0x1000d928  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d92e  call    esi
0x1000d930  mov     esi, eax
0x1000d932  lea     ecx, [esp+88h+var_50]
0x1000d936  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1000d93b  test    esi, esi
0x1000d93d  jns     loc_1000D83A
0x1000d943  jmp     loc_1000D9F3
0x1000d948  mov     eax, [edi]
0x1000d94a  mov     esi, [eax+14h]
0x1000d94d  lea     eax, [esp+88h+var_78]
0x1000d951  push    eax
0x1000d952  push    1
0x1000d954  push    [esp+90h+var_64]
0x1000d958  mov     ecx, esi; this
0x1000d95a  push    [esp+94h+var_68]
0x1000d95e  push    edi
0x1000d95f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d965  call    esi
0x1000d967  mov     esi, eax
0x1000d969  test    esi, esi
0x1000d96b  js      loc_1000D9F3
0x1000d971  mov     ecx, [esp+88h+var_78]
0x1000d975  mov     eax, ecx
0x1000d977  sub     eax, [esp+88h+var_60]
0x1000d97b  sub     eax, 4
0x1000d97e  or      ecx, dword ptr [esp+88h+var_74]
0x1000d982  mov     dword ptr [esp+88h+var_74+4], eax
0x1000d986  jz      short loc_1000D9F3
0x1000d988  mov     eax, [edi]
0x1000d98a  xor     ebx, ebx
0x1000d98c  mov     esi, [eax+14h]
0x1000d98f  lea     eax, [esp+88h+var_60]
0x1000d993  push    eax
0x1000d994  push    ebx
0x1000d995  push    [esp+90h+var_5C]
0x1000d999  mov     ecx, esi; this
0x1000d99b  push    [esp+94h+var_60]
0x1000d99f  push    edi
0x1000d9a0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d9a6  call    esi
0x1000d9a8  mov     esi, eax
0x1000d9aa  test    esi, esi
0x1000d9ac  js      short loc_1000D9F3
0x1000d9ae  mov     eax, [edi]
0x1000d9b0  push    ebx
0x1000d9b1  push    4
0x1000d9b3  mov     esi, [eax+10h]
0x1000d9b6  lea     eax, [esp+90h+var_74+4]
0x1000d9ba  push    eax
0x1000d9bb  push    edi
0x1000d9bc  mov     ecx, esi; this
0x1000d9be  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d9c4  call    esi
0x1000d9c6  mov     esi, eax
0x1000d9c8  test    esi, esi
0x1000d9ca  js      short loc_1000D9F3
0x1000d9cc  mov     eax, [edi]
0x1000d9ce  mov     esi, [eax+14h]
0x1000d9d1  lea     eax, [esp+88h+var_78]
0x1000d9d5  push    eax
0x1000d9d6  push    ebx
0x1000d9d7  push    dword ptr [esp+90h+var_74]
0x1000d9db  mov     ecx, esi; this
0x1000d9dd  push    [esp+94h+var_78]
0x1000d9e1  push    edi
0x1000d9e2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000d9e8  call    esi
0x1000d9ea  mov     esi, eax
0x1000d9ec  jmp     short loc_1000D9F3
0x1000d9ee  mov     esi, 8000FFFFh
0x1000d9f3  mov     ecx, [esp+88h+var_4]
0x1000d9fa  mov     eax, esi
0x1000d9fc  pop     edi
0x1000d9fd  pop     esi
0x1000d9fe  pop     ebx
0x1000d9ff  xor     ecx, esp; StackCookie
0x1000da01  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000da06  mov     esp, ebp
0x1000da08  pop     ebp
0x1000da09  retn    4
```
