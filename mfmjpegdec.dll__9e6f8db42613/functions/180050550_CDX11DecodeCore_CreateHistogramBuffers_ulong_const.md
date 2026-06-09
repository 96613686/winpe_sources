# CDX11DecodeCore::CreateHistogramBuffers(ulong const &)

- ea: `0x180050550`
- end: `0x1800506f8`
- name: `?CreateHistogramBuffers@CDX11DecodeCore@@MEAAJAEBK@Z`
- size: `424`
- prototype: `__int64 __fastcall(CDX11DecodeCore *__hidden this, const unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180024220`
- `0x18003a54c`
- `0x18003a628`
- `0x180044d78`
- `0x18004a11c`
- `0x18004e4a4`
- `0x180050550`
- `0x180052320`
- `0x1800526c4`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall CDX11DecodeCore::CreateHistogramBuffers(CDX11DecodeCore *this, const unsigned int *a2)
{
  unsigned __int64 v2; // rdi
  __int64 v5; // rax
  bool v6; // cf
  unsigned __int64 v7; // rax
  unsigned __int64 *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // ecx
  __int64 i; // r14
  __int64 v14; // rsi
  __int64 *v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int128 *, _QWORD, __int64 *); // rdi
  __int64 result; // rax
  __int64 v18; // [rsp+40h] [rbp-58h] BYREF
  __int128 v19; // [rsp+48h] [rbp-50h] BYREF
  __int64 v20; // [rsp+58h] [rbp-40h]

  v2 = *a2;
  v20 = 0;
  v19 = 0;
  v5 = 8 * v2;
  if ( !is_mul_ok(v2, 8u) )
    v5 = -1;
  v6 = __CFADD__(v5, 8);
  v7 = v5 + 8;
  if ( v6 )
    v7 = -1;
  v8 = (unsigned __int64 *)operator new[](v7);
  if ( v8 )
  {
    v9 = v8 + 1;
    *v8 = v2;
    `eh vector constructor iterator'(
      v8 + 1,
      8u,
      (unsigned int)v2,
      Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>::ComPtr<ID3D11VideoDecoderOutputView>,
      (void (*)(void *))Microsoft::WRL::ComPtr<ID3D11VideoDevice2>::~ComPtr<ID3D11VideoDevice2>);
  }
  else
  {
    v9 = 0;
  }
  v10 = *((_QWORD *)this + 51);
  v18 = 0;
  *((_QWORD *)this + 51) = v9;
  if ( v10 )
    wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>();
  wistd::unique_ptr<Microsoft::WRL::ComPtr<ID3D11Buffer> [0],wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11Buffer> [0]>>::reset(&v18);
  if ( *((_QWORD *)this + 51) )
  {
    v11 = *((_DWORD *)this + 100);
    v12 = *((_DWORD *)this + 83);
    DWORD2(v19) = 8;
    LODWORD(v20) = v12;
    LODWORD(v19) = 4 * v11 + 256;
    if ( g_wppLevels )
      WPP_SF_dddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids,
        (unsigned int)(4 * v11 + 256),
        v11,
        v12,
        this);
    for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
    {
      v14 = *((_QWORD *)this + 6);
      v15 = (__int64 *)(*((_QWORD *)this + 51) + 8 * i);
      v16 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64 *))(*(_QWORD *)v14 + 24LL);
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(v15);
      result = v16(v14, &v19, 0, v15);
      if ( (_DWORD)result )
        return result;
    }
    return 0;
  }
  else
  {
    if ( g_wppLevels )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, this);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180050550  mov     [rsp+arg_10], rbx
0x180050555  push    rbp
0x180050556  push    rsi
0x180050557  push    rdi
0x180050558  push    r14
0x18005055a  push    r15
0x18005055c  sub     rsp, 70h
0x180050560  mov     rax, cs:__security_cookie
0x180050567  xor     rax, rsp
0x18005056a  mov     [rsp+98h+var_38], rax
0x18005056f  mov     edi, [rdx]
0x180050571  xor     eax, eax
0x180050573  mov     [rsp+98h+var_40], rax
0x180050578  mov     rbp, rcx
0x18005057b  mov     r15, rdx
0x18005057e  xorps   xmm0, xmm0
0x180050581  movups  [rsp+98h+var_50], xmm0
0x180050586  lea     esi, [rax+8]
0x180050589  lea     rcx, [rsi-9]
0x18005058d  mov     eax, esi
0x18005058f  mul     rdi
0x180050592  cmovb   rax, rcx
0x180050596  add     rax, rsi
0x180050599  cmovb   rax, rcx
0x18005059d  mov     rcx, rax; unsigned __int64
0x1800505a0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800505a5  test    rax, rax
0x1800505a8  jz      short loc_1800505D3
0x1800505aa  lea     rbx, [rax+8]
0x1800505ae  mov     [rax], rdi
0x1800505b1  lea     rax, ??1?$ComPtr@UID3D11VideoDevice2@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<ID3D11VideoDevice2>::~ComPtr<ID3D11VideoDevice2>(void)
0x1800505b8  mov     rcx, rbx; void *
0x1800505bb  lea     r9, ??0?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x1800505c2  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x1800505c7  mov     r8d, edi; unsigned __int64
0x1800505ca  mov     edx, esi; unsigned __int64
0x1800505cc  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800505d1  jmp     short loc_1800505D5
0x1800505d3  xor     ebx, ebx
0x1800505d5  mov     rdx, [rbp+198h]
0x1800505dc  mov     [rsp+98h+var_58], 0
0x1800505e5  mov     [rbp+198h], rbx
0x1800505ec  test    rdx, rdx
0x1800505ef  jz      short loc_1800505F6
0x1800505f1  call    ??$?RV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@Z; wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>(Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> *)
0x1800505f6  lea     rcx, [rsp+98h+var_58]
0x1800505fb  call    ?reset@?$unique_ptr@$$BY0A@V?$ComPtr@UID3D11Buffer@@@WRL@Microsoft@@U?$default_delete@$$BY0A@V?$ComPtr@UID3D11Buffer@@@WRL@Microsoft@@@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<Microsoft::WRL::ComPtr<ID3D11Buffer> [0],wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11Buffer> [0]>>::reset(std::nullptr_t)
0x180050600  cmp     qword ptr [rbp+198h], 0
0x180050608  jz      loc_1800506AA
0x18005060e  mov     eax, [rbp+190h]
0x180050614  mov     ecx, [rbp+14Ch]
0x18005061a  mov     dword ptr [rsp+98h+var_50+8], esi
0x18005061e  mov     dword ptr [rsp+98h+var_40], ecx
0x180050622  lea     r9d, ds:100h[rax*4]
0x18005062a  mov     dword ptr [rsp+98h+var_50], r9d
0x18005062f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050636  jb      short loc_180050661
0x180050638  mov     [rsp+98h+var_68], rbp
0x18005063d  lea     r8, WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids
0x180050644  mov     [rsp+98h+var_70], ecx
0x180050648  mov     edx, 35h ; '5'
0x18005064d  mov     rcx, cs:WPP_GLOBAL_Control
0x180050654  mov     dword ptr [rsp+98h+var_78], eax
0x180050658  mov     rcx, [rcx+10h]
0x18005065c  call    WPP_SF_dddq
0x180050661  xor     r14d, r14d
0x180050664  cmp     r14d, [r15]
0x180050667  jnb     short loc_1800506A6
0x180050669  mov     rsi, [rbp+30h]
0x18005066d  mov     rdx, [rbp+198h]
0x180050674  mov     rax, [rsi]
0x180050677  lea     rbx, [rdx+r14*8]
0x18005067b  mov     rcx, rbx
0x18005067e  mov     rdi, [rax+18h]
0x180050682  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180050687  mov     r9, rbx
0x18005068a  lea     rdx, [rsp+98h+var_50]
0x18005068f  xor     r8d, r8d
0x180050692  mov     rcx, rsi
0x180050695  mov     rax, rdi
0x180050698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005069d  test    eax, eax
0x18005069f  jnz     short loc_1800506D7
0x1800506a1  inc     r14d
0x1800506a4  jmp     short loc_180050664
0x1800506a6  xor     eax, eax
0x1800506a8  jmp     short loc_1800506D7
0x1800506aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800506b1  jb      short loc_1800506D2
0x1800506b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800506ba  lea     r8, WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids
0x1800506c1  mov     edx, 34h ; '4'
0x1800506c6  mov     r9, rbp
0x1800506c9  mov     rcx, [rcx+10h]
0x1800506cd  call    WPP_SF_q
0x1800506d2  mov     eax, 8007000Eh
0x1800506d7  mov     rcx, [rsp+98h+var_38]
0x1800506dc  xor     rcx, rsp; StackCookie
0x1800506df  call    __security_check_cookie
0x1800506e4  mov     rbx, [rsp+98h+arg_10]
0x1800506ec  add     rsp, 70h
0x1800506f0  pop     r15
0x1800506f2  pop     r14
0x1800506f4  pop     rdi
0x1800506f5  pop     rsi
0x1800506f6  pop     rbp
0x1800506f7  retn
```
