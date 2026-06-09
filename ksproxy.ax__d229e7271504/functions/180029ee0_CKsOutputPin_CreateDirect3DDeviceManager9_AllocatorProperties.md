# CKsOutputPin::CreateDirect3DDeviceManager9(_AllocatorProperties *)

- ea: `0x180029ee0`
- end: `0x18002a318`
- name: `?CreateDirect3DDeviceManager9@CKsOutputPin@@UEAAJPEAU_AllocatorProperties@@@Z`
- size: `1080`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, struct _AllocatorProperties *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002b58`
- `0x18001eb24`
- `0x18001f620`
- `0x18001ffb0`
- `0x180025860`
- `0x180029ee0`
- `0x180035c90`
- `0x180045010`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x18002a11a`
- `USER32!GetDesktopWindow` at `0x18002a144`
- `USER32!GetDesktopWindow` at `0x18002a11a`
- `USER32!GetDesktopWindow` at `0x18002a144`
- `d3d9!Direct3DCreate9Ex` at `0x180029fa6`
- `d3d9!Direct3DCreate9Ex` at `0x180029fa6`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::CreateDirect3DDeviceManager9(CKsOutputPin *this, struct _AllocatorProperties *a2)
{
  void **p_m_IoThreadSemaphore; // rsi
  void *m_IoThreadSemaphore; // rcx
  int PresentationParametersFromMediaType; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  signed int cbBuffer; // ebx
  struct CMediaType *v12; // rax
  unsigned int m_IoThreadHandle; // r15d
  int v14; // edi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, HWND, int, _DWORD *, _QWORD, __int64 *); // rbx
  HWND v16; // rax
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+6Ch] [rbp-94h] BYREF
  _DWORD v24[8]; // [rsp+70h] [rbp-90h] BYREF
  HWND DesktopWindow; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  int v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+ACh] [rbp-54h]
  _BYTE v29[28]; // [rsp+B0h] [rbp-50h] BYREF
  int v30; // [rsp+CCh] [rbp-34h]

  v18 = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids);
  memset_0(v24, 0, 0x40u);
  memset_0(v29, 0, 0x130u);
  p_m_IoThreadSemaphore = &this->m_IoThreadSemaphore;
  v19 = 0;
  m_IoThreadSemaphore = this->m_IoThreadSemaphore;
  v20 = 0;
  if ( m_IoThreadSemaphore )
  {
    *p_m_IoThreadSemaphore = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)m_IoThreadSemaphore + 16LL))(m_IoThreadSemaphore);
  }
  PresentationParametersFromMediaType = Direct3DCreate9Ex(31, &v18);
  v7 = PresentationParametersFromMediaType;
  if ( PresentationParametersFromMediaType < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v9 = 61;
LABEL_10:
      v10 = (unsigned int)PresentationParametersFromMediaType;
LABEL_39:
      WPP_SF_d(v8[2], v9, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, v10);
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  cbBuffer = a2->cbBuffer;
  if ( cbBuffer <= 0 )
  {
    v7 = -2147467259;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_41;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids);
    goto LABEL_40;
  }
  v12 = (struct CMediaType *)((__int64 (__fastcall *)(CKsOutputPin *))this->BreakConnect)(this);
  PresentationParametersFromMediaType = GetPresentationParametersFromMediaType(v12, cbBuffer, &v19, &v20, &v23, &v22);
  v7 = PresentationParametersFromMediaType;
  if ( PresentationParametersFromMediaType >= 0 )
  {
    memset_0(v24, 0, 0x40u);
    m_IoThreadHandle = (unsigned int)this->m_IoThreadHandle;
    if ( m_IoThreadHandle == -1 )
      m_IoThreadHandle = 0;
    PresentationParametersFromMediaType = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v18 + 112LL))(
                                            v18,
                                            m_IoThreadHandle,
                                            1,
                                            v29);
    v7 = PresentationParametersFromMediaType;
    if ( PresentationParametersFromMediaType < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 64;
        goto LABEL_10;
      }
      goto LABEL_41;
    }
    v24[0] = v19;
    v14 = v30 & 0x10000;
    v24[1] = v20;
    v24[3] = 1;
    v26 = 1;
    v24[6] = 1;
    v24[2] = 0;
    DesktopWindow = GetDesktopWindow();
    v28 = 0;
    v27 = 16;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, HWND, int, _DWORD *, _QWORD, __int64 *))(*(_QWORD *)v18 + 160LL);
    v16 = GetDesktopWindow();
    PresentationParametersFromMediaType = v15(v18, m_IoThreadHandle, 1, v16, v14 != 0 ? 70 : 38, v24, 0, &v21);
    v7 = PresentationParametersFromMediaType;
    if ( PresentationParametersFromMediaType < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 65;
        goto LABEL_10;
      }
      goto LABEL_41;
    }
    PresentationParametersFromMediaType = CreateDXVA2DeviceManager(
                                            (struct IDirect3DDeviceManager9 **)&this->m_IoThreadSemaphore,
                                            &this->m_IoThreadId);
    v7 = PresentationParametersFromMediaType;
    if ( PresentationParametersFromMediaType < 0 )
    {
      *p_m_IoThreadSemaphore = 0;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 66;
        goto LABEL_10;
      }
      goto LABEL_41;
    }
    v7 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)*p_m_IoThreadSemaphore + 24LL))(
           *p_m_IoThreadSemaphore,
           v21,
           this->m_IoThreadId);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( *p_m_IoThreadSemaphore )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)*p_m_IoThreadSemaphore + 16LL))(*p_m_IoThreadSemaphore);
        *p_m_IoThreadSemaphore = 0;
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 67;
        v10 = v7;
        goto LABEL_39;
      }
      goto LABEL_41;
    }
LABEL_40:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v9 = 63;
    goto LABEL_10;
  }
LABEL_41:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v18 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v21 = 0;
  }
  if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 3u )
    WPP_SF_d(v8[2], 68, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180029ee0  mov     [rsp-8+arg_10], rbx
0x180029ee5  mov     [rsp-8+arg_18], rsi
0x180029eea  push    rbp
0x180029eeb  push    rdi
0x180029eec  push    r12
0x180029eee  push    r14
0x180029ef0  push    r15
0x180029ef2  lea     rbp, [rsp-0F0h]
0x180029efa  sub     rsp, 1F0h
0x180029f01  mov     rax, cs:__security_cookie
0x180029f08  xor     rax, rsp
0x180029f0b  mov     [rbp+110h+var_30], rax
0x180029f12  xor     r12d, r12d
0x180029f15  mov     rdi, rdx
0x180029f18  mov     [rsp+210h+var_1C0], r12
0x180029f1d  mov     r14, rcx
0x180029f20  mov     [rsp+210h+var_1B0], r12
0x180029f25  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f2c  lea     r15, WPP_GLOBAL_Control
0x180029f33  cmp     rcx, r15
0x180029f36  jz      short loc_180029F53
0x180029f38  cmp     byte ptr [rcx+19h], 3
0x180029f3c  jb      short loc_180029F53
0x180029f3e  mov     rcx, [rcx+10h]
0x180029f42  lea     edx, [r12+3Ch]
0x180029f47  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x180029f4e  call    WPP_SF_
0x180029f53  xor     edx, edx; Val
0x180029f55  lea     rcx, [rsp+210h+var_1A0]; void *
0x180029f5a  lea     r8d, [rdx+40h]; Size
0x180029f5e  call    memset_0
0x180029f63  xor     edx, edx; Val
0x180029f65  lea     rcx, [rbp+110h+var_160]; void *
0x180029f69  mov     r8d, 130h; Size
0x180029f6f  call    memset_0
0x180029f74  lea     rsi, [r14+220h]
0x180029f7b  mov     [rsp+210h+var_1B8], r12d
0x180029f80  mov     rcx, [rsi]
0x180029f83  mov     [rsp+210h+var_1B4], r12d
0x180029f88  test    rcx, rcx
0x180029f8b  jz      short loc_180029F9C
0x180029f8d  mov     [rsi], r12
0x180029f90  mov     rax, [rcx]
0x180029f93  mov     rax, [rax+10h]
0x180029f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f9c  lea     rdx, [rsp+210h+var_1C0]
0x180029fa1  mov     ecx, 1Fh
0x180029fa6  call    cs:__imp_Direct3DCreate9Ex
0x180029fad  nop     dword ptr [rax+rax+00h]
0x180029fb2  mov     ebx, eax
0x180029fb4  test    eax, eax
0x180029fb6  jns     short loc_180029FDF
0x180029fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fbf  cmp     rcx, r15
0x180029fc2  jz      loc_18002A27D
0x180029fc8  cmp     byte ptr [rcx+19h], 3
0x180029fcc  jb      loc_18002A27D
0x180029fd2  mov     edx, 3Dh ; '='
0x180029fd7  mov     r9d, eax
0x180029fda  jmp     loc_18002A25D
0x180029fdf  mov     ebx, [rdi+4]
0x180029fe2  test    ebx, ebx
0x180029fe4  jg      short loc_18002A01F
0x180029fe6  mov     ebx, 80004005h
0x180029feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ff2  cmp     rcx, r15
0x180029ff5  jz      loc_18002A27D
0x180029ffb  cmp     byte ptr [rcx+19h], 3
0x180029fff  jb      loc_18002A27D
0x18002a005  mov     rcx, [rcx+10h]
0x18002a009  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x18002a010  mov     edx, 3Eh ; '>'
0x18002a015  call    WPP_SF_
0x18002a01a  jmp     loc_18002A276
0x18002a01f  mov     rax, [r14]
0x18002a022  mov     rcx, r14
0x18002a025  mov     rax, [rax+58h]
0x18002a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a02e  lea     rcx, [rsp+210h+var_1A8]
0x18002a033  mov     edx, ebx; unsigned int
0x18002a035  mov     [rsp+210h+var_1E8], rcx; int *
0x18002a03a  lea     r9, [rsp+210h+var_1B4]; unsigned int *
0x18002a03f  lea     rcx, [rsp+210h+var_1A4]
0x18002a044  mov     [rsp+210h+var_1F0], rcx; unsigned int *
0x18002a049  lea     r8, [rsp+210h+var_1B8]; unsigned int *
0x18002a04e  mov     rcx, rax; struct CMediaType *
0x18002a051  call    ?GetPresentationParametersFromMediaType@@YAJPEAVCMediaType@@KPEAK11PEAH@Z; GetPresentationParametersFromMediaType(CMediaType *,ulong,ulong *,ulong *,ulong *,int *)
0x18002a056  mov     ebx, eax
0x18002a058  test    eax, eax
0x18002a05a  jns     short loc_18002A080
0x18002a05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a063  cmp     rcx, r15
0x18002a066  jz      loc_18002A27D
0x18002a06c  cmp     byte ptr [rcx+19h], 3
0x18002a070  jb      loc_18002A27D
0x18002a076  mov     edx, 3Fh ; '?'
0x18002a07b  jmp     loc_180029FD7
0x18002a080  mov     edi, 40h ; '@'
0x18002a085  lea     rcx, [rsp+210h+var_1A0]; void *
0x18002a08a  mov     r8d, edi; Size
0x18002a08d  xor     edx, edx; Val
0x18002a08f  call    memset_0
0x18002a094  mov     r15d, [r14+218h]
0x18002a09b  lea     r9, [rbp+110h+var_160]
0x18002a09f  mov     rcx, [rsp+210h+var_1C0]
0x18002a0a4  lea     r8d, [rdi-3Fh]
0x18002a0a8  cmp     r15d, 0FFFFFFFFh
0x18002a0ac  cmovz   r15d, r12d
0x18002a0b0  mov     rax, [rcx]
0x18002a0b3  mov     edx, r15d
0x18002a0b6  mov     rax, [rax+70h]
0x18002a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0bf  mov     ebx, eax
0x18002a0c1  test    eax, eax
0x18002a0c3  jns     short loc_18002A0ED
0x18002a0c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0cc  lea     r15, WPP_GLOBAL_Control
0x18002a0d3  cmp     rcx, r15
0x18002a0d6  jz      loc_18002A27D
0x18002a0dc  cmp     byte ptr [rcx+19h], 3
0x18002a0e0  jb      loc_18002A27D
0x18002a0e6  mov     edx, edi
0x18002a0e8  jmp     loc_180029FD7
0x18002a0ed  mov     eax, [rsp+210h+var_1B8]
0x18002a0f1  mov     ecx, 1
0x18002a0f6  mov     edi, [rbp+110h+var_144]
0x18002a0f9  mov     [rsp+210h+var_1A0], eax
0x18002a0fd  and     edi, 10000h
0x18002a103  mov     eax, [rsp+210h+var_1B4]
0x18002a107  mov     [rsp+210h+var_19C], eax
0x18002a10b  mov     [rsp+210h+var_194], ecx
0x18002a10f  mov     [rbp+110h+var_178], ecx
0x18002a112  mov     [rbp+110h+var_188], ecx
0x18002a115  mov     [rsp+210h+var_198], r12d
0x18002a11a  call    cs:__imp_GetDesktopWindow
0x18002a121  nop     dword ptr [rax+rax+00h]
0x18002a126  mov     [rbp+110h+var_180], rax
0x18002a12a  mov     rax, [rsp+210h+var_1C0]
0x18002a12f  mov     [rbp+110h+var_164], r12d
0x18002a133  mov     [rbp+110h+var_16C], 10h
0x18002a13a  mov     rcx, [rax]
0x18002a13d  mov     rbx, [rcx+0A0h]
0x18002a144  call    cs:__imp_GetDesktopWindow
0x18002a14b  nop     dword ptr [rax+rax+00h]
0x18002a150  lea     rdx, [rsp+210h+var_1B0]
0x18002a155  neg     edi
0x18002a157  mov     [rsp+210h+var_1D8], rdx
0x18002a15c  mov     r9, rax
0x18002a15f  sbb     ecx, ecx
0x18002a161  mov     [rsp+210h+var_1E0], r12
0x18002a166  and     ecx, 20h
0x18002a169  lea     rdx, [rsp+210h+var_1A0]
0x18002a16e  add     ecx, 26h ; '&'
0x18002a171  mov     [rsp+210h+var_1E8], rdx
0x18002a176  mov     dword ptr [rsp+210h+var_1F0], ecx
0x18002a17a  mov     r8d, 1
0x18002a180  mov     rcx, [rsp+210h+var_1C0]
0x18002a185  mov     edx, r15d
0x18002a188  mov     rax, rbx
0x18002a18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a190  mov     ebx, eax
0x18002a192  test    eax, eax
0x18002a194  jns     short loc_18002A1C1
0x18002a196  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a19d  lea     r15, WPP_GLOBAL_Control
0x18002a1a4  cmp     rcx, r15
0x18002a1a7  jz      loc_18002A27D
0x18002a1ad  cmp     byte ptr [rcx+19h], 3
0x18002a1b1  jb      loc_18002A27D
0x18002a1b7  mov     edx, 41h ; 'A'
0x18002a1bc  jmp     loc_180029FD7
0x18002a1c1  lea     rdx, [r14+228h]; unsigned int *
0x18002a1c8  mov     rcx, rsi; struct IDirect3DDeviceManager9 **
0x18002a1cb  call    ?CreateDXVA2DeviceManager@@YAJPEAPEAUIDirect3DDeviceManager9@@PEAI@Z; CreateDXVA2DeviceManager(IDirect3DDeviceManager9 * *,uint *)
0x18002a1d0  mov     ebx, eax
0x18002a1d2  test    eax, eax
0x18002a1d4  jns     short loc_18002A204
0x18002a1d6  mov     [rsi], r12
0x18002a1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1e0  lea     r15, WPP_GLOBAL_Control
0x18002a1e7  cmp     rcx, r15
0x18002a1ea  jz      loc_18002A27D
0x18002a1f0  cmp     byte ptr [rcx+19h], 3
0x18002a1f4  jb      loc_18002A27D
0x18002a1fa  mov     edx, 42h ; 'B'
0x18002a1ff  jmp     loc_180029FD7
0x18002a204  mov     rcx, [rsi]
0x18002a207  mov     r8d, [r14+228h]
0x18002a20e  mov     rdx, [rsp+210h+var_1B0]
0x18002a213  mov     rax, [rcx]
0x18002a216  mov     rax, [rax+18h]
0x18002a21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a21f  mov     ebx, eax
0x18002a221  test    eax, eax
0x18002a223  jns     short loc_18002A26F
0x18002a225  mov     rcx, [rsi]
0x18002a228  test    rcx, rcx
0x18002a22b  jz      short loc_18002A23C
0x18002a22d  mov     rax, [rcx]
0x18002a230  mov     rax, [rax+10h]
0x18002a234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a239  mov     [rsi], r12
0x18002a23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a243  lea     r15, WPP_GLOBAL_Control
0x18002a24a  cmp     rcx, r15
0x18002a24d  jz      short loc_18002A27D
0x18002a24f  cmp     byte ptr [rcx+19h], 3
0x18002a253  jb      short loc_18002A27D
0x18002a255  mov     edx, 43h ; 'C'
0x18002a25a  mov     r9d, ebx
0x18002a25d  mov     rcx, [rcx+10h]
0x18002a261  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x18002a268  call    WPP_SF_d
0x18002a26d  jmp     short loc_18002A276
0x18002a26f  lea     r15, WPP_GLOBAL_Control
0x18002a276  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a27d  mov     rdx, [rsp+210h+var_1C0]
0x18002a282  test    rdx, rdx
0x18002a285  jz      short loc_18002A2A2
0x18002a287  mov     rax, [rdx]
0x18002a28a  mov     rcx, rdx
0x18002a28d  mov     rax, [rax+10h]
0x18002a291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a296  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a29d  mov     [rsp+210h+var_1C0], r12
0x18002a2a2  mov     rdx, [rsp+210h+var_1B0]
0x18002a2a7  test    rdx, rdx
0x18002a2aa  jz      short loc_18002A2C7
0x18002a2ac  mov     rax, [rdx]
0x18002a2af  mov     rcx, rdx
0x18002a2b2  mov     rax, [rax+10h]
0x18002a2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2c2  mov     [rsp+210h+var_1B0], r12
0x18002a2c7  cmp     rcx, r15
0x18002a2ca  jz      short loc_18002A2EA
0x18002a2cc  cmp     byte ptr [rcx+19h], 3
0x18002a2d0  jb      short loc_18002A2EA
0x18002a2d2  mov     rcx, [rcx+10h]
0x18002a2d6  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x18002a2dd  mov     edx, 44h ; 'D'
0x18002a2e2  mov     r9d, ebx
0x18002a2e5  call    WPP_SF_d
0x18002a2ea  mov     eax, ebx
0x18002a2ec  mov     rcx, [rbp+110h+var_30]
0x18002a2f3  xor     rcx, rsp; StackCookie
0x18002a2f6  call    __security_check_cookie
0x18002a2fb  lea     r11, [rsp+210h+var_20]
0x18002a303  mov     rbx, [r11+40h]
0x18002a307  mov     rsi, [r11+48h]
0x18002a30b  mov     rsp, r11
0x18002a30e  pop     r15
0x18002a310  pop     r14
0x18002a312  pop     r12
0x18002a314  pop     rdi
0x18002a315  pop     rbp
0x18002a316  retn
```
