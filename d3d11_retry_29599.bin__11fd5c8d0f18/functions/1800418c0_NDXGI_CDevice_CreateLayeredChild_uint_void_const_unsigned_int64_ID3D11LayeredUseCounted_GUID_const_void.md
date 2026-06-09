# NDXGI::CDevice::CreateLayeredChild(uint,void const *,unsigned __int64,ID3D11LayeredUseCounted *,_GUID const &,void * *)

- ea: `0x1800418c0`
- end: `0x180041bae`
- name: `?CreateLayeredChild@CDevice@NDXGI@@QEAAJIPEBX_KPEAUID3D11LayeredUseCounted@@AEBU_GUID@@PEAPEAX@Z`
- size: `750`
- prototype: `int(NDXGI::CDevice *__hidden this, unsigned int, const void *, unsigned __int64, struct ID3D11LayeredUseCounted *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800418b0`

## callees

- `0x180022400`
- `0x1800418c0`
- `0x180041bc0`
- `0x180041d80`
- `0x180042390`
- `0x18004251c`
- `0x18004266c`
- `0x180056230`
- `0x1800a7328`
- `0x1800aa990`
- `0x1800aa9a8`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800419f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800419f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800419ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800419ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041a36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041a36`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NDXGI::CDevice::CreateLayeredChild(
        NDXGI::CDevice *this,
        unsigned int a2,
        _QWORD *a3,
        size_t a4,
        struct ID3D11LayeredUseCounted *a5,
        const struct _GUID *a6,
        void **a7)
{
  __int64 v12; // rdi
  char **v13; // r15
  __int64 v14; // rax
  char *v15; // rax
  struct ID3D11LayeredUseCounted *v16; // r15
  _QWORD *v17; // rdi
  int Interface; // eax
  int v19; // eax
  int v20; // eax
  struct ID3D11LayeredUseCounted *v21; // rdx
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h]
  NDXGI::CDevice *v28; // [rsp+58h] [rbp-B0h]
  __int64 v29; // [rsp+70h] [rbp-98h]
  size_t v30; // [rsp+80h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-78h]
  int v33; // [rsp+A8h] [rbp-60h]
  size_t v34; // [rsp+B0h] [rbp-58h]
  char *v35; // [rsp+B8h] [rbp-50h]
  struct ID3D11LayeredUseCounted *v36; // [rsp+C0h] [rbp-48h]
  _QWORD *v37; // [rsp+D0h] [rbp-38h]
  DWORD CurrentThreadId; // [rsp+118h] [rbp+10h] BYREF
  _QWORD *v39; // [rsp+120h] [rbp+18h] BYREF

  if ( a2 != 4 )
  {
    if ( a2 != 5 )
    {
      switch ( a2 )
      {
        case 0u:
        case 1u:
        case 2u:
        case 3u:
          v12 = 208;
          if ( !*((_BYTE *)this + 1986) )
            v12 = 176;
          memset_0(&v25, 0, 0x88u);
          v25 = a2;
          memcpy_0(&v26, a3, a4);
          v26 += v12;
          v27 -= v12;
          v28 = this;
          v34 = a4;
          v13 = 0;
          AcquireSRWLockShared((PSRWLOCK)this + 197);
          CurrentThreadId = GetCurrentThreadId();
          v14 = std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
                  (char *)this + 1584,
                  &v39,
                  &CurrentThreadId);
          if ( *(_QWORD *)v14 != *((_QWORD *)this + 199) )
            v13 = *(char ***)(*(_QWORD *)v14 + 24LL);
          if ( this != (NDXGI::CDevice *)-1576LL )
            ReleaseSRWLockShared((PSRWLOCK)this + 197);
          if ( !v13 )
            goto LABEL_17;
          if ( a2 == 2 )
          {
            v19 = *((_DWORD *)v13 + 2);
            if ( (v19 & 1) != 0 )
            {
              LODWORD(v32) = v19 | v32;
              v20 = v33;
              if ( *((_DWORD *)v13 + 3) )
                v20 = *((_DWORD *)v13 + 3);
              v33 = v20;
            }
          }
          v15 = *v13;
          if ( !*v13 )
LABEL_17:
            v15 = (char *)this + 40;
          v35 = v15;
          v16 = a5;
          v36 = a5;
          v17 = (_QWORD *)*a3;
          if ( *((_BYTE *)this + 1986) )
          {
            CLayeredObject<NDXGIOn12::CResource>::CreateInstance(
              (struct NDXGI::CResource::TConstructorArgs *)&v25,
              (__int64)a7);
          }
          else
          {
            v39 = (_QWORD *)*a3;
            *v17 = &CLayeredObject<NDXGI::CResource>::`vftable';
            NDXGI::CResource::CResource(
              (NDXGI::CResource *)(v17 + 1),
              (const struct NDXGI::CResource::TConstructorArgs *)&v25);
            v17[1] = &CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `CD3D11LayeredChild<ID3D11DeviceChild,NDXGI::CDevice,64>'};
            v17[6] = &CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIResource1'};
            v17[9] = &CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGISurface2'};
            v17[10] = &CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIKeyedMutex'};
            v17[11] = &CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIResourceDWM'};
            v17[2] = v16;
            v37 = v17 + 1;
            NDXGI::CResource::FinalConstruct(
              (NDXGI::CResource *)(v17 + 1),
              (const struct NDXGI::CResource::TConstructorArgs *)&v25);
            Interface = CLayeredObject<NDXGI::CResource>::QueryInterface(v17, a6, a7);
            ThrowFailure(Interface);
          }
          return 0;
        default:
          return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7), a2);
      }
    }
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7), a2);
  }
  if ( *(_DWORD *)(a3[6] + 4LL) != 1
    && *(_DWORD *)(a3[6] + 4LL) != 2
    && *(_DWORD *)(a3[6] + 4LL) != 4
    && *(_DWORD *)(a3[6] + 4LL) != 6
    && *(_DWORD *)(a3[6] + 4LL) != 11 )
  {
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7), a2);
  }
  memset_0(&v25, 0, 0x58u);
  v25 = a2;
  memcpy_0(&v26, a3, a4);
  v26 += 72;
  v27 -= 72;
  v28 = this;
  v30 = a4;
  v31 = v29;
  v21 = a5;
  v32 = (__int64)a5;
  v22 = (_QWORD *)*a3;
  v39 = v22;
  *v22 = &CLayeredObject<NDXGI::CSurfaceView>::`vftable';
  v23 = v31;
  v22[3] = v28;
  v22[4] = 0;
  v22[5] = 0;
  v22[7] = v23;
  v22[8] = 0;
  v22[1] = &CLayeredObject<NDXGI::CSurfaceView>::CContainedObject::`vftable'{for `CD3D11LayeredChild<ID3D11DeviceChild,NDXGI::CDevice,64>'};
  v22[6] = &CLayeredObject<NDXGI::CSurfaceView>::CContainedObject::`vftable'{for `IDXGISurface'};
  v22[2] = v21;
  v37 = v22 + 1;
  NDXGI::CDeviceChild<IDXGISurface,IUnknown>::FinalConstruct((_DWORD)v22 + 8, v25, (unsigned int)&v26, v30, v32);
  v24 = CLayeredObject<NDXGI::CSurfaceView>::QueryInterface(v22, a6, a7);
  ThrowFailure(v24);
  return 0;
}

```

## disassembly

```asm
0x1800418c0  mov     [rsp+arg_0], rbx
0x1800418c5  push    rsi
0x1800418c6  push    rdi
0x1800418c7  push    r12
0x1800418c9  push    r14
0x1800418cb  push    r15
0x1800418cd  sub     rsp, 0E0h
0x1800418d4  mov     r15, r9
0x1800418d7  mov     rsi, r8
0x1800418da  movsxd  rbx, edx
0x1800418dd  mov     r14, rcx
0x1800418e0  cmp     ebx, 4
0x1800418e3  jz      short loc_18004190A
0x1800418e5  cmp     ebx, 5
0x1800418e8  jz      short def_180041908; jumptable 0000000180041908 default case, cases 4-25
0x1800418ea  cmp     ebx, 19h; switch 26 cases
0x1800418ed  ja      short def_180041908; jumptable 0000000180041908 default case, cases 4-25
0x1800418ef  lea     rdx, __ImageBase
0x1800418f6  movzx   eax, ds:(byte_180041B94 - 180000000h)[rdx+rbx]
0x1800418fe  mov     ecx, ds:(jpt_180041908 - 180000000h)[rdx+rax*4]
0x180041905  add     rcx, rdx
0x180041908  jmp     rcx; switch jump
0x18004190a  mov     rcx, [r8+30h]
0x18004190e  mov     edx, [rcx+4]
0x180041911  sub     edx, 1
0x180041914  jz      loc_1800EA7FC
0x18004191a  sub     edx, 1
0x18004191d  jz      loc_1800EA7FC
0x180041923  sub     edx, 2
0x180041926  jz      loc_1800EA7FC
0x18004192c  sub     edx, 2
0x18004192f  jz      loc_1800EA7FC
0x180041935  cmp     edx, 5
0x180041938  jz      loc_1800EA7FC
0x18004193e  mov     rcx, [r14+38h]; jumptable 0000000180041908 default case, cases 4-25
0x180041942  mov     rax, [rcx]
0x180041945  mov     rdx, [rsp+108h+arg_30]
0x18004194d  mov     [rsp+108h+var_D8], rdx
0x180041952  mov     rdx, [rsp+108h+arg_28]
0x18004195a  mov     [rsp+108h+var_E0], rdx
0x18004195f  mov     rdx, [rsp+108h+arg_20]
0x180041967  mov     [rsp+108h+var_E8], rdx
0x18004196c  mov     edx, ebx
0x18004196e  mov     rax, [rax+48h]
0x180041972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041977  nop
0x180041978  mov     rbx, [rsp+108h+arg_0]
0x180041980  add     rsp, 0E0h
0x180041987  pop     r15
0x180041989  pop     r14
0x18004198b  pop     r12
0x18004198d  pop     rdi
0x18004198e  pop     rsi
0x18004198f  retn
0x180041990  mov     edi, 0D0h; jumptable 0000000180041908 cases 0-3
0x180041995  mov     eax, 0B0h
0x18004199a  cmp     byte ptr [r14+7C2h], 0
0x1800419a2  cmovz   edi, eax
0x1800419a5  xor     edx, edx; Val
0x1800419a7  mov     r8d, 88h; Size
0x1800419ad  lea     rcx, [rsp+108h+var_C8]; void *
0x1800419b2  call    memset_0
0x1800419b7  mov     [rsp+108h+var_C8], ebx
0x1800419bb  mov     r8, r15; Size
0x1800419be  mov     rdx, rsi; Src
0x1800419c1  lea     rcx, [rsp+108h+var_C0]; void *
0x1800419c6  call    memcpy_0
0x1800419cb  add     [rsp+108h+var_C0], rdi
0x1800419d0  sub     [rsp+108h+var_B8], rdi
0x1800419d5  mov     [rsp+108h+var_B0], r14
0x1800419da  mov     [rsp+108h+var_58], r15
0x1800419e2  xor     r15d, r15d
0x1800419e5  lea     r12, [r14+628h]
0x1800419ec  mov     rcx, r12; SRWLock
0x1800419ef  call    cs:__imp_AcquireSRWLockShared
0x1800419f5  call    cs:__imp_GetCurrentThreadId
0x1800419fb  mov     [rsp+108h+arg_8], eax
0x180041a02  lea     r8, [rsp+108h+arg_8]
0x180041a0a  lea     rdx, [rsp+108h+arg_10]
0x180041a12  lea     rcx, [r14+630h]
0x180041a19  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x180041a1e  mov     rcx, [rax]
0x180041a21  cmp     rcx, [r14+638h]
0x180041a28  jz      short loc_180041A2E
0x180041a2a  mov     r15, [rcx+18h]
0x180041a2e  test    r12, r12
0x180041a31  jz      short loc_180041A3C
0x180041a33  mov     rcx, r12; SRWLock
0x180041a36  call    cs:__imp_ReleaseSRWLockShared
0x180041a3c  test    r15, r15
0x180041a3f  jnz     loc_180041B0B
0x180041a45  lea     rax, [r14+28h]
0x180041a49  mov     [rsp+108h+var_50], rax
0x180041a51  mov     r15, [rsp+108h+arg_20]
0x180041a59  mov     [rsp+108h+var_48], r15
0x180041a61  mov     rdi, [rsi]
0x180041a64  cmp     byte ptr [r14+7C2h], 0
0x180041a6c  jnz     loc_180041B29
0x180041a72  mov     [rsp+108h+arg_10], rdi
0x180041a7a  lea     rax, ??_7?$CLayeredObject@VCResource@NDXGI@@@@6B@; const CLayeredObject<NDXGI::CResource>::`vftable'
0x180041a81  mov     [rdi], rax
0x180041a84  lea     rbx, [rdi+8]
0x180041a88  lea     rdx, [rsp+108h+var_C8]; struct NDXGI::CResource::TConstructorArgs *
0x180041a8d  mov     rcx, rbx; this
0x180041a90  call    ??0CResource@NDXGI@@QEAA@AEBUTConstructorArgs@01@@Z; NDXGI::CResource::CResource(NDXGI::CResource::TConstructorArgs const &)
0x180041a95  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCResource@NDXGI@@@@6B?$CD3D11LayeredChild@UID3D11DeviceChild@@VCDevice@NDXGI@@$0EA@@@@; const CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `CD3D11LayeredChild<ID3D11DeviceChild,NDXGI::CDevice,64>'}
0x180041a9c  mov     [rbx], rax
0x180041a9f  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCResource@NDXGI@@@@6BIDXGIResource1@@@; const CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIResource1'}
0x180041aa6  mov     [rbx+28h], rax
0x180041aaa  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCResource@NDXGI@@@@6BIDXGISurface2@@@; const CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGISurface2'}
0x180041ab1  mov     [rbx+40h], rax
0x180041ab5  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCResource@NDXGI@@@@6BIDXGIKeyedMutex@@@; const CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIKeyedMutex'}
0x180041abc  mov     [rbx+48h], rax
0x180041ac0  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCResource@NDXGI@@@@6BIDXGIResourceDWM@@@; const CLayeredObject<NDXGI::CResource>::CContainedObject::`vftable'{for `IDXGIResourceDWM'}
0x180041ac7  mov     [rbx+50h], rax
0x180041acb  mov     [rbx+8], r15
0x180041acf  mov     [rsp+108h+var_38], rbx
0x180041ad7  lea     rdx, [rsp+108h+var_C8]; struct NDXGI::CResource::TConstructorArgs *
0x180041adc  mov     rcx, rbx; this
0x180041adf  call    ?FinalConstruct@CResource@NDXGI@@QEAAXAEBUTConstructorArgs@12@@Z; NDXGI::CResource::FinalConstruct(NDXGI::CResource::TConstructorArgs const &)
0x180041ae4  mov     r8, [rsp+108h+arg_30]
0x180041aec  mov     rdx, [rsp+108h+arg_28]
0x180041af4  mov     rcx, rdi
0x180041af7  call    ?QueryInterface@?$CLayeredObject@VCResource@NDXGI@@@@UEAAJAEBU_GUID@@PEAPEAX@Z; CLayeredObject<NDXGI::CResource>::QueryInterface(_GUID const &,void * *)
0x180041afc  mov     ecx, eax; int
0x180041afe  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180041b03  nop
0x180041b04  xor     eax, eax
0x180041b06  jmp     loc_180041978
0x180041b0b  cmp     ebx, 2
0x180041b0e  jnz     short loc_180041B18
0x180041b10  mov     eax, [r15+8]
0x180041b14  test    al, 1
0x180041b16  jnz     short loc_180041B50
0x180041b18  mov     rax, [r15]
0x180041b1b  test    rax, rax
0x180041b1e  jnz     loc_180041A49
0x180041b24  jmp     loc_180041A45
0x180041b29  mov     rax, [rsp+108h+arg_30]
0x180041b31  mov     [rsp+108h+var_E8], rax; __int64
0x180041b36  mov     r9, [rsp+108h+arg_28]
0x180041b3e  mov     r8, r15
0x180041b41  mov     rdx, rdi
0x180041b44  lea     rcx, [rsp+108h+var_C8]; struct NDXGI::CResource::TConstructorArgs *
0x180041b49  call    ?CreateInstance@?$CLayeredObject@VCResource@NDXGIOn12@@@@SAXAEBUTConstructorArgs@CResource@NDXGI@@PEAX1AEBU_GUID@@PEAPEAX@Z; CLayeredObject<NDXGIOn12::CResource>::CreateInstance(NDXGI::CResource::TConstructorArgs const &,void *,void *,_GUID const &,void * *)
0x180041b4e  jmp     short loc_180041B04
0x180041b50  or      dword ptr [rsp+108h+var_78], eax
0x180041b57  mov     ecx, [r15+0Ch]
0x180041b5b  mov     eax, [rsp+108h+var_60]
0x180041b62  test    ecx, ecx
0x180041b64  cmovnz  eax, ecx
0x180041b67  mov     [rsp+108h+var_60], eax
0x180041b6e  jmp     short loc_180041B18
0x180041b70  mov     eax, 8007000Eh
0x180041b75  jmp     loc_180041978
0x180041b7a  mov     eax, [rsp+108h+arg_8]
0x180041b81  jmp     loc_180041978
0x1800ea7fc  xor     edx, edx; Val
0x1800ea7fe  mov     r8d, 58h ; 'X'; Size
0x1800ea804  lea     rcx, [rsp+108h+var_C8]; void *
0x1800ea809  call    memset_0
0x1800ea80e  mov     [rsp+108h+var_C8], ebx
0x1800ea812  mov     r8, r15; Size
0x1800ea815  mov     rdx, rsi; Src
0x1800ea818  lea     rcx, [rsp+108h+var_C0]; void *
0x1800ea81d  call    memcpy_0
0x1800ea822  add     [rsp+108h+var_C0], 48h ; 'H'
0x1800ea828  sub     [rsp+108h+var_B8], 48h ; 'H'
0x1800ea82e  mov     [rsp+108h+var_B0], r14
0x1800ea833  mov     [rsp+108h+var_88], r15
0x1800ea83b  mov     rax, [rsp+108h+var_98]
0x1800ea840  mov     [rsp+108h+var_80], rax
0x1800ea848  mov     rdx, [rsp+108h+arg_20]
0x1800ea850  mov     [rsp+108h+var_78], rdx
0x1800ea858  mov     rbx, [rsi]
0x1800ea85b  mov     [rsp+108h+arg_10], rbx
0x1800ea863  lea     rax, ??_7?$CLayeredObject@VCSurfaceView@NDXGI@@@@6B@; const CLayeredObject<NDXGI::CSurfaceView>::`vftable'
0x1800ea86a  mov     [rbx], rax
0x1800ea86d  lea     r10, [rbx+8]
0x1800ea871  mov     rcx, [rsp+108h+var_80]
0x1800ea879  mov     rax, [rsp+108h+var_B0]
0x1800ea87e  mov     [r10+10h], rax
0x1800ea882  xor     r15d, r15d
0x1800ea885  mov     [r10+18h], r15
0x1800ea889  mov     [r10+20h], r15
0x1800ea88d  mov     [r10+30h], rcx
0x1800ea891  mov     [r10+38h], r15
0x1800ea895  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCSurfaceView@NDXGI@@@@6B?$CD3D11LayeredChild@UID3D11DeviceChild@@VCDevice@NDXGI@@$0EA@@@@; const CLayeredObject<NDXGI::CSurfaceView>::CContainedObject::`vftable'{for `CD3D11LayeredChild<ID3D11DeviceChild,NDXGI::CDevice,64>'}
0x1800ea89c  mov     [r10], rax
0x1800ea89f  lea     rax, ??_7CContainedObject@?$CLayeredObject@VCSurfaceView@NDXGI@@@@6BIDXGISurface@@@; const CLayeredObject<NDXGI::CSurfaceView>::CContainedObject::`vftable'{for `IDXGISurface'}
0x1800ea8a6  mov     [r10+28h], rax
0x1800ea8aa  mov     [r10+8], rdx
0x1800ea8ae  mov     [rsp+108h+var_38], r10
0x1800ea8b6  mov     rax, [rsp+108h+var_78]
0x1800ea8be  mov     [rsp+108h+var_E8], rax
0x1800ea8c3  mov     r9, [rsp+108h+var_88]
0x1800ea8cb  lea     r8, [rsp+108h+var_C0]
0x1800ea8d0  mov     edx, [rsp+108h+var_C8]
0x1800ea8d4  mov     rcx, r10
0x1800ea8d7  call    ?FinalConstruct@?$CDeviceChild@UIDXGISurface@@UIUnknown@@@NDXGI@@QEAAXW4ED3D11DeviceChildType@@PEBUSLayeredArgs@@_KPEAUID3D11LayeredUseCounted@@@Z; NDXGI::CDeviceChild<IDXGISurface,IUnknown>::FinalConstruct(ED3D11DeviceChildType,SLayeredArgs const *,unsigned __int64,ID3D11LayeredUseCounted *)
0x1800ea8dc  mov     r8, [rsp+108h+arg_30]
0x1800ea8e4  mov     rdx, [rsp+108h+arg_28]
0x1800ea8ec  mov     rcx, rbx
0x1800ea8ef  call    ?QueryInterface@?$CLayeredObject@VCSurfaceView@NDXGI@@@@UEAAJAEBU_GUID@@PEAPEAX@Z; CLayeredObject<NDXGI::CSurfaceView>::QueryInterface(_GUID const &,void * *)
0x1800ea8f4  mov     ecx, eax; int
0x1800ea8f6  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800ea8fb  nop
0x1800ea8fc  jmp     loc_180041B04
```
