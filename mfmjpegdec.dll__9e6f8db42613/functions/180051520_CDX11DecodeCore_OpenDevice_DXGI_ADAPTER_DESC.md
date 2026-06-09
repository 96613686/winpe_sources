# CDX11DecodeCore::OpenDevice(DXGI_ADAPTER_DESC *)

- ea: `0x180051520`
- end: `0x1800518d6`
- name: `?OpenDevice@CDX11DecodeCore@@IEAAJPEAUDXGI_ADAPTER_DESC@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(CDX11DecodeCore *__hidden this, struct DXGI_ADAPTER_DESC *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180050aa0`

## callees

- `0x180024220`
- `0x180024bf4`
- `0x180044d78`
- `0x18004a11c`
- `0x18004aa94`
- `0x180051520`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDX11DecodeCore::OpenDevice(CDX11DecodeCore *this, struct DXGI_ADAPTER_DESC *a2)
{
  __int64 v3; // rcx
  unsigned int v4; // ebx
  _QWORD *v5; // r14
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, GUID *, char *); // rbx
  __int64 (__fastcall ****v8)(__int64, GUID *, __int64 *); // r15
  __int64 (__fastcall ***v9)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall ***v11)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(__int64, GUID *, __int64 *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, char *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[304]; // [rsp+50h] [rbp-B0h] BYREF

  v16 = 0;
  v18 = 0;
  v17 = 0;
  memset_0(v20, 0, sizeof(v20));
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    v5 = (_QWORD *)((char *)this + 40);
    if ( !*((_QWORD *)this + 5) || (v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3), *v5 = 0, !v4) )
    {
      if ( g_wppLevels )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, this);
      v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 3) + 48LL))(
             *((_QWORD *)this + 3),
             (char *)this + 40);
      if ( !v4 )
      {
        if ( g_wppLevels )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, this);
        v6 = *((_QWORD *)this + 3);
        v7 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, char *))(*(_QWORD *)v6 + 32LL);
        v8 = (__int64 (__fastcall ****)(__int64, GUID *, __int64 *))((char *)this + 48);
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)this + 6);
        v4 = v7(v6, *v5, &IID_ID3D11Device, (char *)this + 48);
        if ( !v4 )
        {
          if ( g_wppLevels )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, this);
          v9 = *v8;
          v10 = (**v8)[40];
          Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v16);
          ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64 (__fastcall ****)(_QWORD, GUID *, char *)))v10)(
            v9,
            &v16);
          if ( v16 )
          {
            Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)this + 34);
            v4 = (**v16)(v16, &IID_ID3D11VideoContext, (char *)this + 272);
            if ( !v4 )
            {
              Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)this + 35);
              v4 = (**v16)(v16, &IID_ID3D11VideoContext1, (char *)this + 280);
              if ( !v4 )
              {
                Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)this + 36);
                (**v16)(v16, &IID_ID3D11VideoContext3, (char *)this + 288);
                if ( g_wppLevels )
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    13,
                    &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids,
                    this);
                v11 = *v8;
                v12 = ***v8;
                Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v18);
                v4 = v12((__int64)v11, &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c, &v18);
                if ( !v4 )
                {
                  v13 = v18;
                  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 56LL);
                  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v17);
                  v4 = v14(v13, &v17);
                  if ( !v4 )
                  {
                    v4 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v17 + 64LL))(v17, v20);
                    if ( !v4 )
                    {
                      *((_BYTE *)this + 392) = 0;
                      v19 = 0;
                      if ( ((int (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64, __int64 *, __int64))(**v8)[33])(
                             *v8,
                             20,
                             &v19,
                             8) >= 0 )
                        *((_BYTE *)this + 392) = (_DWORD)v19 != v4;
                      if ( g_wppLevels >= 8u )
                        WPP_SF_dq(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          14,
                          &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids,
                          *((unsigned __int8 *)this + 392),
                          this);
                    }
                  }
                }
              }
            }
          }
          else
          {
            v4 = -2147467261;
          }
        }
      }
    }
    if ( g_wppLevels )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids, v4, this);
  }
  else
  {
    v4 = -2147467259;
  }
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease((__int64 *)&v16);
  return v4;
}

```

## disassembly

```asm
0x180051520  mov     [rsp-8+arg_8], rbx
0x180051525  mov     [rsp-8+arg_10], rsi
0x18005152a  push    rbp
0x18005152b  push    rdi
0x18005152c  push    r13
0x18005152e  push    r14
0x180051530  push    r15
0x180051532  lea     rbp, [rsp-90h]
0x18005153a  sub     rsp, 190h
0x180051541  mov     rax, cs:__security_cookie
0x180051548  xor     rax, rsp
0x18005154b  mov     [rbp+0B0h+var_30], rax
0x180051552  mov     rsi, rcx
0x180051555  mov     [rsp+1B0h+var_180], 0
0x18005155e  mov     [rsp+1B0h+var_170], 0
0x180051567  mov     [rsp+1B0h+var_178], 0
0x180051570  xor     edx, edx; Val
0x180051572  mov     r8d, 130h; Size
0x180051578  lea     rcx, [rsp+1B0h+var_160]; void *
0x18005157d  call    memset_0
0x180051582  mov     rcx, [rsi+18h]
0x180051586  test    rcx, rcx
0x180051589  jnz     short loc_180051595
0x18005158b  mov     ebx, 80004005h
0x180051590  jmp     loc_180051889
0x180051595  lea     r14, [rsi+28h]
0x180051599  mov     rdx, [r14]
0x18005159c  lea     r13, WPP_aec28197ab9b3fb808bb48be54c28540_Traceguids
0x1800515a3  test    rdx, rdx
0x1800515a6  jz      short loc_1800515C5
0x1800515a8  mov     rax, [rcx]
0x1800515ab  mov     rax, [rax+18h]
0x1800515af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515b4  mov     ebx, eax
0x1800515b6  mov     qword ptr [r14], 0
0x1800515bd  test    eax, eax
0x1800515bf  jnz     loc_18005185F
0x1800515c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800515cc  jb      short loc_1800515E9
0x1800515ce  mov     edx, 0Ah
0x1800515d3  mov     r9, rsi
0x1800515d6  mov     r8, r13
0x1800515d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800515e0  mov     rcx, [rcx+10h]
0x1800515e4  call    WPP_SF_q
0x1800515e9  mov     rcx, [rsi+18h]
0x1800515ed  mov     rax, [rcx]
0x1800515f0  mov     rdx, r14
0x1800515f3  mov     rax, [rax+30h]
0x1800515f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515fc  mov     ebx, eax
0x1800515fe  test    eax, eax
0x180051600  jnz     loc_18005185F
0x180051606  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005160d  jb      short loc_180051628
0x18005160f  lea     edx, [rax+0Bh]
0x180051612  mov     r9, rsi
0x180051615  mov     r8, r13
0x180051618  mov     rcx, cs:WPP_GLOBAL_Control
0x18005161f  mov     rcx, [rcx+10h]
0x180051623  call    WPP_SF_q
0x180051628  mov     rdi, [rsi+18h]
0x18005162c  mov     rax, [rdi]
0x18005162f  mov     rbx, [rax+20h]
0x180051633  lea     r15, [rsi+30h]
0x180051637  mov     rcx, r15
0x18005163a  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005163f  mov     r9, r15
0x180051642  lea     r8, IID_ID3D11Device
0x180051649  mov     rdx, [r14]
0x18005164c  mov     rcx, rdi
0x18005164f  mov     rax, rbx
0x180051652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051657  mov     ebx, eax
0x180051659  test    eax, eax
0x18005165b  jnz     loc_18005185F
0x180051661  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051668  jb      short loc_180051683
0x18005166a  lea     edx, [rax+0Ch]
0x18005166d  mov     r9, rsi
0x180051670  mov     r8, r13
0x180051673  mov     rcx, cs:WPP_GLOBAL_Control
0x18005167a  mov     rcx, [rcx+10h]
0x18005167e  call    WPP_SF_q
0x180051683  mov     rdi, [r15]
0x180051686  mov     rax, [rdi]
0x180051689  mov     rbx, [rax+140h]
0x180051690  lea     rcx, [rsp+1B0h+var_180]
0x180051695  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005169a  lea     rdx, [rsp+1B0h+var_180]
0x18005169f  mov     rcx, rdi
0x1800516a2  mov     rax, rbx
0x1800516a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516aa  cmp     [rsp+1B0h+var_180], 0
0x1800516b0  jnz     short loc_1800516BC
0x1800516b2  mov     ebx, 80004003h
0x1800516b7  jmp     loc_18005185F
0x1800516bc  lea     rbx, [rsi+110h]
0x1800516c3  mov     rcx, rbx
0x1800516c6  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800516cb  nop
0x1800516cc  mov     rcx, [rsp+1B0h+var_180]
0x1800516d1  mov     rax, [rcx]
0x1800516d4  mov     r8, rbx
0x1800516d7  lea     rdx, IID_ID3D11VideoContext
0x1800516de  mov     rax, [rax]
0x1800516e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516e6  mov     ebx, eax
0x1800516e8  test    eax, eax
0x1800516ea  jnz     loc_18005185F
0x1800516f0  lea     rbx, [rsi+118h]
0x1800516f7  mov     rcx, rbx
0x1800516fa  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800516ff  nop
0x180051700  mov     rcx, [rsp+1B0h+var_180]
0x180051705  mov     rax, [rcx]
0x180051708  mov     r8, rbx
0x18005170b  lea     rdx, IID_ID3D11VideoContext1
0x180051712  mov     rax, [rax]
0x180051715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005171a  mov     ebx, eax
0x18005171c  test    eax, eax
0x18005171e  jnz     loc_18005185F
0x180051724  lea     rbx, [rsi+120h]
0x18005172b  mov     rcx, rbx
0x18005172e  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180051733  nop
0x180051734  mov     rcx, [rsp+1B0h+var_180]
0x180051739  mov     rax, [rcx]
0x18005173c  mov     r8, rbx
0x18005173f  lea     rdx, IID_ID3D11VideoContext3
0x180051746  mov     rax, [rax]
0x180051749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005174e  nop
0x18005174f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051756  jb      short loc_180051773
0x180051758  mov     edx, 0Dh
0x18005175d  mov     r9, rsi
0x180051760  mov     r8, r13
0x180051763  mov     rcx, cs:WPP_GLOBAL_Control
0x18005176a  mov     rcx, [rcx+10h]
0x18005176e  call    WPP_SF_q
0x180051773  mov     rdi, [r15]
0x180051776  mov     rax, [rdi]
0x180051779  mov     rbx, [rax]
0x18005177c  lea     rcx, [rsp+1B0h+var_170]
0x180051781  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180051786  lea     r8, [rsp+1B0h+var_170]
0x18005178b  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x180051792  mov     rcx, rdi
0x180051795  mov     rax, rbx
0x180051798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005179d  mov     ebx, eax
0x18005179f  test    eax, eax
0x1800517a1  jnz     loc_18005185F
0x1800517a7  mov     rdi, [rsp+1B0h+var_170]
0x1800517ac  mov     rax, [rdi]
0x1800517af  mov     rbx, [rax+38h]
0x1800517b3  lea     rcx, [rsp+1B0h+var_178]
0x1800517b8  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800517bd  lea     rdx, [rsp+1B0h+var_178]
0x1800517c2  mov     rcx, rdi
0x1800517c5  mov     rax, rbx
0x1800517c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517cd  mov     ebx, eax
0x1800517cf  test    eax, eax
0x1800517d1  jnz     loc_18005185F
0x1800517d7  mov     rcx, [rsp+1B0h+var_178]
0x1800517dc  mov     rax, [rcx]
0x1800517df  lea     rdx, [rsp+1B0h+var_160]
0x1800517e4  mov     rax, [rax+40h]
0x1800517e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517ed  mov     ebx, eax
0x1800517ef  test    eax, eax
0x1800517f1  jnz     short loc_18005185F
0x1800517f3  mov     [rsi+188h], al
0x1800517f9  mov     [rsp+1B0h+var_168], 0
0x180051802  mov     rcx, [r15]
0x180051805  mov     rax, [rcx]
0x180051808  lea     r9d, [rbx+8]
0x18005180c  lea     r8, [rsp+1B0h+var_168]
0x180051811  lea     edx, [rbx+14h]
0x180051814  mov     rax, [rax+108h]
0x18005181b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051820  test    eax, eax
0x180051822  js      short loc_180051831
0x180051824  cmp     dword ptr [rsp+1B0h+var_168], ebx
0x180051828  setnz   al
0x18005182b  mov     [rsi+188h], al
0x180051831  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180051838  jb      short loc_18005185F
0x18005183a  movzx   r9d, byte ptr [rsi+188h]
0x180051842  mov     edx, 0Eh
0x180051847  mov     [rsp+1B0h+var_190], rsi
0x18005184c  mov     r8, r13
0x18005184f  mov     rcx, cs:WPP_GLOBAL_Control
0x180051856  mov     rcx, [rcx+10h]
0x18005185a  call    WPP_SF_dq
0x18005185f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051866  jb      short loc_180051889
0x180051868  mov     edx, 0Fh
0x18005186d  mov     [rsp+1B0h+var_190], rsi
0x180051872  mov     r9d, ebx
0x180051875  mov     r8, r13
0x180051878  mov     rcx, cs:WPP_GLOBAL_Control
0x18005187f  mov     rcx, [rcx+10h]
0x180051883  call    WPP_SF_dq
0x180051888  nop
0x180051889  lea     rcx, [rsp+1B0h+var_178]
0x18005188e  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180051893  nop
0x180051894  lea     rcx, [rsp+1B0h+var_170]
0x180051899  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18005189e  nop
0x18005189f  lea     rcx, [rsp+1B0h+var_180]
0x1800518a4  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800518a9  mov     eax, ebx
0x1800518ab  mov     rcx, [rbp+0B0h+var_30]
0x1800518b2  xor     rcx, rsp; StackCookie
0x1800518b5  call    __security_check_cookie
0x1800518ba  lea     r11, [rsp+1B0h+var_20]
0x1800518c2  mov     rbx, [r11+38h]
0x1800518c6  mov     rsi, [r11+40h]
0x1800518ca  mov     rsp, r11
0x1800518cd  pop     r15
0x1800518cf  pop     r14
0x1800518d1  pop     r13
0x1800518d3  pop     rdi
0x1800518d4  pop     rbp
0x1800518d5  retn
```
