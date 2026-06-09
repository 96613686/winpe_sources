# CDirectMusicSynthPort7::Initialize(_DMUS_PORTPARAMS8 *)

- ea: `0x1800166f4`
- end: `0x18001688b`
- name: `?Initialize@CDirectMusicSynthPort7@@QEAAJPEAU_DMUS_PORTPARAMS8@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(CDirectMusicSynthPort7 *__hidden this, struct _DMUS_PORTPARAMS8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800111fc`

## callees

- `0x180011884`
- `0x1800118e0`
- `0x1800119a0`
- `0x180012160`
- `0x180016500`
- `0x1800166f4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016749`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016749`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort7::Initialize(CDirectMusicSynthPort7 *this, struct _DMUS_PORTPARAMS8 *a2)
{
  unsigned int v4; // esi
  int v5; // eax
  HRESULT Instance; // ebx
  _QWORD *v7; // r14
  void (__fastcall ***v8)(_QWORD, GUID *, struct IKsControl **); // rcx
  int v9; // eax
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  struct IKsControl *v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = -2147467259;
  v5 = CDirectMusicSynthPort::Initialize(this, a2);
  v11 = 0;
  Instance = v5;
  if ( v5 >= 0 )
  {
    v7 = (_QWORD *)((char *)this + 784);
    Instance = CoCreateInstance(&CLSID_DirectMusicSynthSink, 0, 1u, &IID_IDirectMusicSynthSink, (LPVOID *)this + 98);
    if ( Instance >= 0 )
    {
      v8 = (void (__fastcall ***)(_QWORD, GUID *, struct IKsControl **))*v7;
      v12 = 0;
      (**v8)(v8, &IID_IKsControl, &v12);
      CDirectMusicSynthPort::SetSinkKsControl(this, v12);
      if ( v12 )
        ((void (__fastcall *)(struct IKsControl *))v12->lpVtbl->Release)(v12);
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 52) + 56LL))(
                   *((_QWORD *)this + 52),
                   0,
                   &v11);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 97) + 88LL))(
                     *((_QWORD *)this + 97),
                     v11);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v7 + 32LL))(*v7, v11);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 97) + 112LL))(
                         *((_QWORD *)this + 97),
                         *v7);
            if ( Instance >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(_QWORD, struct _DMUS_PORTPARAMS8 *))(**((_QWORD **)this + 97) + 24LL))(
                     *((_QWORD *)this + 97),
                     a2);
              v4 = v9;
              if ( v9 >= 0 )
              {
                CDirectMusicSynthPort::InitChannelPriorities(this, 1u, *((_DWORD *)this + 114));
                CDirectMusicSynthPort::InitializeVolumeBoost(this);
              }
              else
              {
                Instance = v9;
              }
            }
          }
        }
      }
    }
  }
  CDirectMusicSynthPort7::CacheSinkUsesDSound(this);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  return v4;
}

```

## disassembly

```asm
0x1800166f4  mov     [rsp+arg_0], rbx
0x1800166f9  mov     [rsp+arg_8], rbp
0x1800166fe  push    rsi
0x1800166ff  push    rdi
0x180016700  push    r14
0x180016702  sub     rsp, 30h
0x180016706  mov     rbp, rdx
0x180016709  mov     rdi, rcx
0x18001670c  mov     esi, 80004005h
0x180016711  call    ?Initialize@CDirectMusicSynthPort@@IEAAJPEAU_DMUS_PORTPARAMS8@@@Z; CDirectMusicSynthPort::Initialize(_DMUS_PORTPARAMS8 *)
0x180016716  mov     [rsp+48h+arg_10], 0
0x18001671f  mov     ebx, eax
0x180016721  test    eax, eax
0x180016723  js      loc_180016853
0x180016729  xor     edx, edx; pUnkOuter
0x18001672b  lea     r14, [rdi+310h]
0x180016732  lea     r9, IID_IDirectMusicSynthSink; riid
0x180016739  mov     [rsp+48h+ppv], r14; ppv
0x18001673e  lea     rcx, CLSID_DirectMusicSynthSink; rclsid
0x180016745  lea     r8d, [rdx+1]; dwClsContext
0x180016749  call    cs:__imp_CoCreateInstance
0x18001674f  mov     ebx, eax
0x180016751  test    eax, eax
0x180016753  js      loc_180016853
0x180016759  mov     rcx, [r14]
0x18001675c  lea     r8, [rsp+48h+arg_18]
0x180016761  mov     [rsp+48h+arg_18], 0
0x18001676a  lea     rdx, IID_IKsControl
0x180016771  mov     rax, [rcx]
0x180016774  mov     rax, [rax]
0x180016777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001677c  mov     rdx, [rsp+48h+arg_18]; struct IKsControl *
0x180016781  mov     rcx, rdi; this
0x180016784  call    ?SetSinkKsControl@CDirectMusicSynthPort@@IEAAXPEAUIKsControl@@@Z; CDirectMusicSynthPort::SetSinkKsControl(IKsControl *)
0x180016789  mov     rcx, [rsp+48h+arg_18]
0x18001678e  test    rcx, rcx
0x180016791  jz      short loc_18001679F
0x180016793  mov     rax, [rcx]
0x180016796  mov     rax, [rax+10h]
0x18001679a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001679f  mov     rcx, [rdi+1A0h]
0x1800167a6  lea     r8, [rsp+48h+arg_10]
0x1800167ab  xor     edx, edx
0x1800167ad  mov     rax, [rcx]
0x1800167b0  mov     rax, [rax+38h]
0x1800167b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167b9  mov     ebx, eax
0x1800167bb  test    eax, eax
0x1800167bd  js      loc_180016853
0x1800167c3  mov     rcx, [rdi+308h]
0x1800167ca  mov     rdx, [rsp+48h+arg_10]
0x1800167cf  mov     rax, [rcx]
0x1800167d2  mov     rax, [rax+58h]
0x1800167d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167db  mov     ebx, eax
0x1800167dd  test    eax, eax
0x1800167df  js      short loc_180016853
0x1800167e1  mov     rcx, [r14]
0x1800167e4  mov     rdx, [rsp+48h+arg_10]
0x1800167e9  mov     rax, [rcx]
0x1800167ec  mov     rax, [rax+20h]
0x1800167f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f5  mov     ebx, eax
0x1800167f7  test    eax, eax
0x1800167f9  js      short loc_180016853
0x1800167fb  mov     rcx, [rdi+308h]
0x180016802  mov     rdx, [r14]
0x180016805  mov     rax, [rcx]
0x180016808  mov     rax, [rax+70h]
0x18001680c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016811  mov     ebx, eax
0x180016813  test    eax, eax
0x180016815  js      short loc_180016853
0x180016817  mov     rcx, [rdi+308h]
0x18001681e  mov     rdx, rbp
0x180016821  mov     rax, [rcx]
0x180016824  mov     rax, [rax+18h]
0x180016828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682d  mov     esi, eax
0x18001682f  test    eax, eax
0x180016831  jns     short loc_180016837
0x180016833  mov     ebx, eax
0x180016835  jmp     short loc_180016853
0x180016837  mov     r8d, [rdi+1C8h]; unsigned int
0x18001683e  mov     edx, 1; unsigned int
0x180016843  mov     rcx, rdi; this
0x180016846  call    ?InitChannelPriorities@CDirectMusicSynthPort@@IEAAXII@Z; CDirectMusicSynthPort::InitChannelPriorities(uint,uint)
0x18001684b  mov     rcx, rdi; this
0x18001684e  call    ?InitializeVolumeBoost@CDirectMusicSynthPort@@IEAAXXZ; CDirectMusicSynthPort::InitializeVolumeBoost(void)
0x180016853  mov     rcx, rdi; this
0x180016856  call    ?CacheSinkUsesDSound@CDirectMusicSynthPort7@@AEAAXXZ; CDirectMusicSynthPort7::CacheSinkUsesDSound(void)
0x18001685b  mov     rcx, [rsp+48h+arg_10]
0x180016860  test    rcx, rcx
0x180016863  jz      short loc_180016871
0x180016865  mov     rax, [rcx]
0x180016868  mov     rax, [rax+10h]
0x18001686c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016871  mov     rbp, [rsp+48h+arg_8]
0x180016876  test    ebx, ebx
0x180016878  cmovs   esi, ebx
0x18001687b  mov     rbx, [rsp+48h+arg_0]
0x180016880  mov     eax, esi
0x180016882  add     rsp, 30h
0x180016886  pop     r14
0x180016888  pop     rdi
0x180016889  pop     rsi
0x18001688a  retn
```
