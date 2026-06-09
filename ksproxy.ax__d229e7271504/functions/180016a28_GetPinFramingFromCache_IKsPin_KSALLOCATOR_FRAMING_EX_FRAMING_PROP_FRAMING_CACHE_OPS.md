# GetPinFramingFromCache(IKsPin *,KSALLOCATOR_FRAMING_EX * *,FRAMING_PROP *,FRAMING_CACHE_OPS)

- ea: `0x180016a28`
- end: `0x180016ddc`
- name: `?GetPinFramingFromCache@@YAHPEAUIKsPin@@PEAPEAUKSALLOCATOR_FRAMING_EX@@PEAW4FRAMING_PROP@@W4FRAMING_CACHE_OPS@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(struct IKsPin *, struct KSALLOCATOR_FRAMING_EX **, enum FRAMING_PROP *, enum FRAMING_CACHE_OPS)`
- caller_count: `16`
- callee_count: `11`
- tags: ``

## callers

- `0x1800165a0`
- `0x180018adc`
- `0x18001de40`
- `0x1800280d0`
- `0x180033074`
- `0x180033570`
- `0x1800341fc`
- `0x180034694`
- `0x180034b18`
- `0x180036960`
- `0x180036dbc`
- `0x180038150`
- `0x18003890c`
- `0x180038f1c`
- `0x1800394c0`
- `0x1800399ac`

## callees

- `0x180010b54`
- `0x180014950`
- `0x180016a28`
- `0x18001f1d0`
- `0x18001f620`
- `0x180037c00`
- `0x180037c5c`
- `0x180038050`
- `0x18003ab5c`
- `0x18003b3ec`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall GetPinFramingFromCache(
        struct IKsPin *a1,
        struct KSALLOCATOR_FRAMING_EX **a2,
        enum FRAMING_PROP *a3,
        enum FRAMING_CACHE_OPS a4)
{
  IKsPin_vtbl *v5; // rax
  struct KSALLOCATOR_FRAMING_EX **v6; // rsi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rax
  enum FRAMING_CACHE_OPS v8; // r14d
  unsigned int v10; // ebx
  void *v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rbx
  int v15; // eax
  int v16; // r8d
  struct KSALLOCATOR_FRAMING_EX *v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  struct KSALLOCATOR_FRAMING_EX *v20; // rax
  unsigned int CountItems; // edi
  unsigned int Flags; // esi
  unsigned int FileAlignment; // r14d
  unsigned int MaxFrameSize; // r15d
  unsigned int Frames; // r12d
  __int64 v26; // rbx
  int v27; // eax
  int v28; // r8d
  __int64 v30; // [rsp+50h] [rbp-29h] BYREF
  __int64 v31; // [rsp+58h] [rbp-21h] BYREF
  enum FRAMING_CACHE_OPS v32; // [rsp+60h] [rbp-19h]
  struct KSALLOCATOR_FRAMING_EX **v33; // [rsp+68h] [rbp-11h]
  struct KSALLOCATOR_FRAMING v34; // [rsp+70h] [rbp-9h] BYREF

  v33 = a2;
  v5 = a1->__vftable;
  v6 = a2;
  v32 = a4;
  v31 = 0;
  QueryInterface = v5->QueryInterface;
  v8 = a4;
  v30 = 0;
  memset(&v34, 0, sizeof(v34));
  if ( QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v30) >= 0 )
  {
    v10 = 1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64, struct KSALLOCATOR_FRAMING_EX **, enum FRAMING_PROP *, _QWORD))(*(_QWORD *)v30 + 24LL))(
        v30,
        v6,
        a3,
        (unsigned int)v8);
      if ( *a3 )
        return v10;
    }
    if ( a1->QueryInterface(a1, &GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1, (void **)&v31) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v31 )
      {
        v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
        if ( (int)GetAllocatorFramingEx((char *)v11, v6) >= 0 )
        {
          *a3 = FramingProp_Ex;
          SetDefaultFramingExItems(*v6);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_24:
            if ( *a3 != FramingProp_None )
              ValidateFramingEx(*v6);
            goto LABEL_26;
          }
          v20 = *v6;
          CountItems = (*v6)->CountItems;
          Flags = (*v6)->FramingItem[0].Flags;
          FileAlignment = v20->FramingItem[0].FileAlignment;
          MaxFrameSize = v20->FramingItem[0].FramingRange.Range.MaxFrameSize;
          Frames = v20->FramingItem[0].Frames;
          v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
          v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 104LL))(v30);
          WPP_SF_SSdddDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            132,
            v28,
            v27,
            v26,
            Frames,
            MaxFrameSize,
            FileAlignment,
            Flags,
            CountItems);
          v6 = v33;
          v8 = v32;
        }
        else
        {
          if ( GetAllocatorFraming(v11, &v34) >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
              v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 104LL))(v30);
              WPP_SF_SSdddDd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                130,
                v16,
                v15,
                v14,
                v34.Frames,
                v34.FrameSize,
                v34.FramePitch,
                v34.OptionsFlags,
                v34.PoolType);
              v10 = 1;
            }
            *a3 = FramingProp_Old;
            v17 = (struct KSALLOCATOR_FRAMING_EX *)operator new(0x70u);
            *v6 = v17;
            if ( !v17 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
                v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 104LL))(v30);
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  131,
                  (unsigned int)&WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
                  v19,
                  v18);
              }
              return 0;
            }
            GetFramingExFromFraming(v17, &v34);
            goto LABEL_24;
          }
          *a3 = FramingProp_None;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_26:
            if ( v8 )
              (*(void (__fastcall **)(__int64, struct KSALLOCATOR_FRAMING_EX *, enum FRAMING_PROP *, __int64))(*(_QWORD *)v30 + 32LL))(
                v30,
                *v6,
                a3,
                2);
            (*(void (__fastcall **)(__int64, struct KSALLOCATOR_FRAMING_EX *, enum FRAMING_PROP *, __int64))(*(_QWORD *)v30 + 32LL))(
              v30,
              *v6,
              a3,
              1);
            return v10;
          }
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 96LL))(v30);
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 104LL))(v30);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            (unsigned int)&WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
            v13,
            v12);
        }
        v10 = 1;
        goto LABEL_24;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016a28  push    rbp
0x180016a2a  push    rbx
0x180016a2b  push    rsi
0x180016a2c  push    rdi
0x180016a2d  push    r12
0x180016a2f  push    r13
0x180016a31  push    r14
0x180016a33  push    r15
0x180016a35  lea     rbp, [rsp-1Fh]
0x180016a3a  sub     rsp, 98h
0x180016a41  mov     rax, cs:__security_cookie
0x180016a48  xor     rax, rsp
0x180016a4b  mov     [rbp+57h+var_48], rax
0x180016a4f  xor     eax, eax
0x180016a51  mov     [rbp+57h+var_68], rdx
0x180016a55  mov     qword ptr [rbp+57h+var_60.___u4], rax
0x180016a59  mov     r13, r8
0x180016a5c  mov     rax, [rcx]
0x180016a5f  lea     r8, [rbp+57h+var_80]
0x180016a63  mov     rsi, rdx
0x180016a66  mov     [rbp+57h+var_70], r9d
0x180016a6a  xor     r15d, r15d
0x180016a6d  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x180016a74  xorps   xmm0, xmm0
0x180016a77  mov     [rbp+57h+var_78], r15
0x180016a7b  mov     rax, [rax]
0x180016a7e  mov     r14d, r9d
0x180016a81  mov     rdi, rcx
0x180016a84  mov     [rbp+57h+var_80], r15
0x180016a88  movups  xmmword ptr [rbp+57h+var_60.___u0], xmm0
0x180016a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a91  test    eax, eax
0x180016a93  js      loc_180016DB9
0x180016a99  mov     rcx, [rbp+57h+var_80]
0x180016a9d  lea     ebx, [r15+1]
0x180016aa1  mov     rax, [rcx]
0x180016aa4  mov     rax, [rax+10h]
0x180016aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aad  test    r14d, r14d
0x180016ab0  jz      short loc_180016AD5
0x180016ab2  mov     rcx, [rbp+57h+var_80]
0x180016ab6  mov     r9d, r14d
0x180016ab9  mov     r8, r13
0x180016abc  mov     rdx, rsi
0x180016abf  mov     rax, [rcx]
0x180016ac2  mov     rax, [rax+18h]
0x180016ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016acb  cmp     [r13+0], r15d
0x180016acf  jnz     loc_180016DB5
0x180016ad5  mov     rax, [rdi]
0x180016ad8  lea     r8, [rbp+57h+var_78]
0x180016adc  lea     rdx, _GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x180016ae3  mov     rcx, rdi
0x180016ae6  mov     rax, [rax]
0x180016ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aee  test    eax, eax
0x180016af0  js      loc_180016DB9
0x180016af6  mov     rcx, [rbp+57h+var_78]
0x180016afa  mov     rax, [rcx]
0x180016afd  mov     rax, [rax+10h]
0x180016b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b06  mov     rcx, [rbp+57h+var_78]
0x180016b0a  test    rcx, rcx
0x180016b0d  jz      loc_180016DB9
0x180016b13  mov     rax, [rcx]
0x180016b16  mov     rax, [rax+18h]
0x180016b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b1f  mov     rdx, rsi; struct KSALLOCATOR_FRAMING_EX **
0x180016b22  mov     rcx, rax; hFile
0x180016b25  mov     rdi, rax
0x180016b28  call    ?GetAllocatorFramingEx@@YAJPEAXPEAPEAUKSALLOCATOR_FRAMING_EX@@@Z; GetAllocatorFramingEx(void *,KSALLOCATOR_FRAMING_EX * *)
0x180016b2d  test    eax, eax
0x180016b2f  jns     loc_180016CC3
0x180016b35  lea     rdx, [rbp+57h+var_60]; struct KSALLOCATOR_FRAMING *
0x180016b39  mov     rcx, rdi; void *
0x180016b3c  call    ?GetAllocatorFraming@@YAJPEAXPEAUKSALLOCATOR_FRAMING@@@Z; GetAllocatorFraming(void *,KSALLOCATOR_FRAMING *)
0x180016b41  test    eax, eax
0x180016b43  jns     short loc_180016BB6
0x180016b45  mov     [r13+0], ebx
0x180016b49  mov     rax, cs:WPP_GLOBAL_Control
0x180016b50  lea     rdi, WPP_GLOBAL_Control
0x180016b57  cmp     rax, rdi
0x180016b5a  jz      loc_180016D72
0x180016b60  cmp     byte ptr [rax+19h], 2
0x180016b64  jb      loc_180016D72
0x180016b6a  mov     rcx, [rbp+57h+var_80]
0x180016b6e  mov     rax, [rcx]
0x180016b71  mov     rax, [rax+60h]
0x180016b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b7a  mov     rcx, [rbp+57h+var_80]
0x180016b7e  mov     rbx, rax
0x180016b81  mov     rdx, [rcx]
0x180016b84  mov     rax, [rdx+68h]
0x180016b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b94  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180016b9b  mov     edx, 81h
0x180016ba0  mov     [rsp+0D0h+var_B0], rbx
0x180016ba5  mov     r9, rax
0x180016ba8  mov     rcx, [rcx+10h]
0x180016bac  call    WPP_SF_SS
0x180016bb1  jmp     loc_180016D5F
0x180016bb6  mov     rax, cs:WPP_GLOBAL_Control
0x180016bbd  lea     rdi, WPP_GLOBAL_Control
0x180016bc4  cmp     rax, rdi
0x180016bc7  jz      short loc_180016C37
0x180016bc9  cmp     byte ptr [rax+19h], 2
0x180016bcd  jb      short loc_180016C37
0x180016bcf  mov     rcx, [rbp+57h+var_80]
0x180016bd3  mov     rax, [rcx]
0x180016bd6  mov     rax, [rax+60h]
0x180016bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bdf  mov     rcx, [rbp+57h+var_80]
0x180016be3  mov     rbx, rax
0x180016be6  mov     rdx, [rcx]
0x180016be9  mov     rax, [rdx+68h]
0x180016bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bf2  mov     ecx, [rbp+57h+var_60.PoolType]
0x180016bf5  mov     edx, 82h
0x180016bfa  mov     [rsp+0D0h+var_88], ecx
0x180016bfe  mov     r9, rax
0x180016c01  mov     ecx, dword ptr [rbp+57h+var_60.___u0]
0x180016c04  mov     [rsp+0D0h+var_90], ecx
0x180016c08  mov     ecx, dword ptr [rbp+57h+var_60.___u4]
0x180016c0b  mov     [rsp+0D0h+var_98], ecx
0x180016c0f  mov     ecx, [rbp+57h+var_60.FrameSize]
0x180016c12  mov     [rsp+0D0h+var_A0], ecx
0x180016c16  mov     ecx, [rbp+57h+var_60.Frames]
0x180016c19  mov     [rsp+0D0h+var_A8], ecx
0x180016c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c24  mov     [rsp+0D0h+var_B0], rbx
0x180016c29  mov     rcx, [rcx+10h]
0x180016c2d  call    WPP_SF_SSdddDd
0x180016c32  mov     ebx, 1
0x180016c37  mov     ecx, 70h ; 'p'; Size
0x180016c3c  mov     dword ptr [r13+0], 2
0x180016c44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016c49  mov     [rsi], rax
0x180016c4c  test    rax, rax
0x180016c4f  jnz     short loc_180016CB2
0x180016c51  mov     rax, cs:WPP_GLOBAL_Control
0x180016c58  cmp     rax, rdi
0x180016c5b  jz      short loc_180016CAA
0x180016c5d  cmp     byte ptr [rax+19h], 2
0x180016c61  jb      short loc_180016CAA
0x180016c63  mov     rcx, [rbp+57h+var_80]
0x180016c67  mov     rax, [rcx]
0x180016c6a  mov     rax, [rax+60h]
0x180016c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c73  mov     rcx, [rbp+57h+var_80]
0x180016c77  mov     rbx, rax
0x180016c7a  mov     rdx, [rcx]
0x180016c7d  mov     rax, [rdx+68h]
0x180016c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c8d  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180016c94  mov     edx, 83h
0x180016c99  mov     [rsp+0D0h+var_B0], rbx
0x180016c9e  mov     r9, rax
0x180016ca1  mov     rcx, [rcx+10h]
0x180016ca5  call    WPP_SF_SS
0x180016caa  mov     ebx, r15d
0x180016cad  jmp     loc_180016DB5
0x180016cb2  lea     rdx, [rbp+57h+var_60]; struct KSALLOCATOR_FRAMING *
0x180016cb6  mov     rcx, rax; struct KSALLOCATOR_FRAMING_EX *
0x180016cb9  call    ?GetFramingExFromFraming@@YAHPEAUKSALLOCATOR_FRAMING_EX@@PEAUKSALLOCATOR_FRAMING@@@Z; GetFramingExFromFraming(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING *)
0x180016cbe  jmp     loc_180016D64
0x180016cc3  mov     dword ptr [r13+0], 3
0x180016ccb  mov     rcx, [rsi]; struct KSALLOCATOR_FRAMING_EX *
0x180016cce  call    ?SetDefaultFramingExItems@@YAXPEAUKSALLOCATOR_FRAMING_EX@@@Z; SetDefaultFramingExItems(KSALLOCATOR_FRAMING_EX *)
0x180016cd3  mov     rax, cs:WPP_GLOBAL_Control
0x180016cda  lea     rdi, WPP_GLOBAL_Control
0x180016ce1  cmp     rax, rdi
0x180016ce4  jz      short loc_180016D64
0x180016ce6  cmp     byte ptr [rax+19h], 2
0x180016cea  jb      short loc_180016D64
0x180016cec  mov     rax, [rsi]
0x180016cef  mov     rcx, [rbp+57h+var_80]
0x180016cf3  mov     edi, [rax]
0x180016cf5  mov     esi, [rax+40h]
0x180016cf8  mov     r14d, [rax+48h]
0x180016cfc  mov     r15d, [rax+60h]
0x180016d00  mov     r12d, [rax+44h]
0x180016d04  mov     rax, [rcx]
0x180016d07  mov     rax, [rax+60h]
0x180016d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d10  mov     rcx, [rbp+57h+var_80]
0x180016d14  mov     rbx, rax
0x180016d17  mov     rdx, [rcx]
0x180016d1a  mov     rax, [rdx+68h]
0x180016d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d2a  mov     edx, 84h
0x180016d2f  mov     [rsp+0D0h+var_88], edi
0x180016d33  mov     r9, rax
0x180016d36  mov     [rsp+0D0h+var_90], esi
0x180016d3a  mov     [rsp+0D0h+var_98], r14d
0x180016d3f  mov     rcx, [rcx+10h]
0x180016d43  mov     [rsp+0D0h+var_A0], r15d
0x180016d48  mov     [rsp+0D0h+var_A8], r12d
0x180016d4d  mov     [rsp+0D0h+var_B0], rbx
0x180016d52  call    WPP_SF_SSdddDd
0x180016d57  mov     rsi, [rbp+57h+var_68]
0x180016d5b  mov     r14d, [rbp+57h+var_70]
0x180016d5f  mov     ebx, 1
0x180016d64  cmp     [r13+0], ebx
0x180016d68  jz      short loc_180016D72
0x180016d6a  mov     rcx, [rsi]; struct KSALLOCATOR_FRAMING_EX *
0x180016d6d  call    ?ValidateFramingEx@@YAXPEAUKSALLOCATOR_FRAMING_EX@@@Z; ValidateFramingEx(KSALLOCATOR_FRAMING_EX *)
0x180016d72  mov     rcx, [rbp+57h+var_80]
0x180016d76  mov     r8, r13
0x180016d79  test    r14d, r14d
0x180016d7c  jz      short loc_180016DA3
0x180016d7e  mov     rax, [rcx]
0x180016d81  mov     r9d, 2
0x180016d87  mov     rdx, [rsi]
0x180016d8a  mov     rax, [rax+20h]
0x180016d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d93  mov     rcx, [rbp+57h+var_80]
0x180016d97  mov     r8, r13
0x180016d9a  mov     rax, [rcx]
0x180016d9d  mov     rax, [rax+20h]
0x180016da1  jmp     short loc_180016DAA
0x180016da3  mov     rdx, [rcx]
0x180016da6  mov     rax, [rdx+20h]
0x180016daa  mov     rdx, [rsi]
0x180016dad  mov     r9d, ebx
0x180016db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016db5  mov     eax, ebx
0x180016db7  jmp     short loc_180016DBB
0x180016db9  xor     eax, eax
0x180016dbb  mov     rcx, [rbp+57h+var_48]
0x180016dbf  xor     rcx, rsp; StackCookie
0x180016dc2  call    __security_check_cookie
0x180016dc7  add     rsp, 98h
0x180016dce  pop     r15
0x180016dd0  pop     r14
0x180016dd2  pop     r13
0x180016dd4  pop     r12
0x180016dd6  pop     rdi
0x180016dd7  pop     rsi
0x180016dd8  pop     rbx
0x180016dd9  pop     rbp
0x180016dda  retn
```
