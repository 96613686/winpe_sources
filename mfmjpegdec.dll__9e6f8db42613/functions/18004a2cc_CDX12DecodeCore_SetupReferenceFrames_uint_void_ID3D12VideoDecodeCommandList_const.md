# CDX12DecodeCore::SetupReferenceFrames(uint,void *,ID3D12VideoDecodeCommandList * const)

- ea: `0x18004a2cc`
- end: `0x18004a4ba`
- name: `?SetupReferenceFrames@CDX12DecodeCore@@IEAAJIPEAXQEAUID3D12VideoDecodeCommandList@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CDX12DecodeCore *__hidden this, unsigned int, void *, struct ID3D12VideoDecodeCommandList *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004a550`

## callees

- `0x180020598`
- `0x180024220`
- `0x180024bf4`
- `0x18004a2cc`
- `0x18004ab40`
- `0x180070010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDX12DecodeCore::SetupReferenceFrames(
        CDX12DecodeCore *this,
        int a2,
        void *a3,
        struct ID3D12VideoDecodeCommandList *const a4)
{
  int v6; // edi
  unsigned int v8; // ebx
  __int64 i; // r14
  __int64 v10; // r12
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+3Ch] [rbp-C4h]
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  _DWORD v19[40]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[37]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a2;
  v16 = a2;
  v17 = 0;
  v18 = 0;
  memset_0(v19, 0, 0x94u);
  memset(v20, 0, sizeof(v20));
  v15 = 0;
  v8 = (*(__int64 (__fastcall **)(CDX12DecodeCore *, void *, _DWORD *, unsigned int *))(*(_QWORD *)this + 168LL))(
         this,
         a3,
         v19,
         &v15);
  if ( !v8 )
  {
    for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    {
      v10 = (unsigned int)v19[i];
      if ( (_DWORD)v10 != v6 && (unsigned int)v10 < 0x25 && !v20[v10] && *((_QWORD *)this + v10 + 15) )
      {
        _mm_lfence();
        v14 = 0;
        v11 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 13) + 8 * v10);
        v12 = **v11;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        v8 = v12(v11, &GUID_09d0f835_92ff_4e53_8efa_40faa551f233, &v14);
        if ( v8 )
          goto LABEL_14;
        if ( g_wppLevels >= 8u )
          WPP_SF_dqq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            &WPP_658c79110f173b2f2946ffe2569864d0_Traceguids,
            (unsigned int)v10,
            *((_QWORD *)this + v10 + 15),
            this);
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 32LL))(v14, *((_QWORD *)this + 7));
        if ( v8 )
        {
LABEL_14:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
          return v8;
        }
        *((_QWORD *)&v17 + 1) = *((_QWORD *)this + v10 + 15);
        *(_QWORD *)&v18 = *((unsigned int *)this + v10 + 104);
        DWORD2(v18) = 0x10000;
        ((void (__fastcall *)(struct ID3D12VideoDecodeCommandList *const, __int64, __int128 *))a4->lpVtbl->ResourceBarrier)(
          a4,
          1,
          &v17);
        v20[v10] = 1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        v6 = v16;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18004a2cc  mov     [rsp-8+arg_8], rbx
0x18004a2d1  push    rbp
0x18004a2d2  push    rsi
0x18004a2d3  push    rdi
0x18004a2d4  push    r12
0x18004a2d6  push    r13
0x18004a2d8  push    r14
0x18004a2da  push    r15
0x18004a2dc  lea     rbp, [rsp-30h]
0x18004a2e1  sub     rsp, 130h
0x18004a2e8  mov     rax, cs:__security_cookie
0x18004a2ef  xor     rax, rsp
0x18004a2f2  mov     [rbp+60h+var_38], rax
0x18004a2f6  mov     r13, r9
0x18004a2f9  mov     rbx, r8
0x18004a2fc  mov     edi, edx
0x18004a2fe  mov     [rsp+160h+var_124], edx
0x18004a302  mov     r15, rcx
0x18004a305  xorps   xmm0, xmm0
0x18004a308  movups  [rsp+160h+var_120], xmm0
0x18004a30d  movups  [rsp+160h+var_110], xmm0
0x18004a312  xor     edx, edx; Val
0x18004a314  mov     r8d, 94h; Size
0x18004a31a  lea     rcx, [rsp+160h+var_100]; void *
0x18004a31f  call    memset_0
0x18004a324  xorps   xmm0, xmm0
0x18004a327  xor     eax, eax
0x18004a329  movups  [rbp+60h+var_60], xmm0
0x18004a32d  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x18004a331  mov     qword ptr [rbp+60h+var_50+0Dh], rax
0x18004a335  mov     [rsp+160h+var_128], eax
0x18004a339  mov     rax, [r15]
0x18004a33c  lea     r9, [rsp+160h+var_128]
0x18004a341  lea     r8, [rsp+160h+var_100]
0x18004a346  mov     rdx, rbx
0x18004a349  mov     rcx, r15
0x18004a34c  mov     rax, [rax+0A8h]
0x18004a353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a358  mov     ebx, eax
0x18004a35a  test    eax, eax
0x18004a35c  jnz     loc_18004A491
0x18004a362  xor     r14d, r14d
0x18004a365  cmp     r14d, [rsp+160h+var_128]
0x18004a36a  jnb     loc_18004A491
0x18004a370  mov     r12d, [rsp+r14*4+160h+var_100]
0x18004a375  cmp     r12d, edi
0x18004a378  jz      loc_18004A47F
0x18004a37e  cmp     r12d, 25h ; '%'
0x18004a382  jnb     loc_18004A47F
0x18004a388  xor     eax, eax
0x18004a38a  cmp     byte ptr [rbp+r12+60h+var_60], al
0x18004a38f  jnz     loc_18004A47F
0x18004a395  cmp     [r15+r12*8+78h], rax
0x18004a39a  jz      loc_18004A47F
0x18004a3a0  lfence
0x18004a3a3  mov     [rsp+160h+var_130], rax
0x18004a3a8  mov     rax, [r15+68h]
0x18004a3ac  mov     rdi, [rax+r12*8]
0x18004a3b0  mov     rax, [rdi]
0x18004a3b3  mov     rbx, [rax]
0x18004a3b6  lea     rcx, [rsp+160h+var_130]
0x18004a3bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a3c0  lea     r8, [rsp+160h+var_130]
0x18004a3c5  lea     rdx, _GUID_09d0f835_92ff_4e53_8efa_40faa551f233
0x18004a3cc  mov     rcx, rdi
0x18004a3cf  mov     rax, rbx
0x18004a3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3d7  mov     ebx, eax
0x18004a3d9  test    eax, eax
0x18004a3db  jnz     loc_18004A487
0x18004a3e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x18004a3e8  jb      short loc_18004A416
0x18004a3ea  lea     edx, [rax+28h]
0x18004a3ed  mov     [rsp+160h+var_138], r15
0x18004a3f2  mov     rax, [r15+r12*8+78h]
0x18004a3f7  mov     [rsp+160h+var_140], rax
0x18004a3fc  mov     r9d, r12d
0x18004a3ff  lea     r8, WPP_658c79110f173b2f2946ffe2569864d0_Traceguids
0x18004a406  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a40d  mov     rcx, [rcx+10h]
0x18004a411  call    WPP_SF_dqq
0x18004a416  mov     rcx, [rsp+160h+var_130]
0x18004a41b  mov     rax, [rcx]
0x18004a41e  mov     rdx, [r15+38h]
0x18004a422  mov     rax, [rax+20h]
0x18004a426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a42b  mov     ebx, eax
0x18004a42d  test    eax, eax
0x18004a42f  jnz     short loc_18004A487
0x18004a431  mov     rax, [r15+r12*8+78h]
0x18004a436  mov     qword ptr [rsp+160h+var_120+8], rax
0x18004a43b  mov     eax, [r15+r12*4+1A0h]
0x18004a443  mov     dword ptr [rsp+160h+var_110], eax
0x18004a447  mov     dword ptr [rsp+160h+var_110+4], ebx
0x18004a44b  mov     dword ptr [rsp+160h+var_110+8], 10000h
0x18004a453  mov     rax, [r13+0]
0x18004a457  lea     r8, [rsp+160h+var_120]
0x18004a45c  lea     edx, [rbx+1]
0x18004a45f  mov     rcx, r13
0x18004a462  mov     rax, [rax+60h]
0x18004a466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a46b  mov     byte ptr [rbp+r12+60h+var_60], 1
0x18004a471  lea     rcx, [rsp+160h+var_130]
0x18004a476  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a47b  mov     edi, [rsp+160h+var_124]
0x18004a47f  inc     r14d
0x18004a482  jmp     loc_18004A365
0x18004a487  lea     rcx, [rsp+160h+var_130]
0x18004a48c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a491  mov     eax, ebx
0x18004a493  mov     rcx, [rbp+60h+var_38]
0x18004a497  xor     rcx, rsp; StackCookie
0x18004a49a  call    __security_check_cookie
0x18004a49f  mov     rbx, [rsp+160h+arg_8]
0x18004a4a7  add     rsp, 130h
0x18004a4ae  pop     r15
0x18004a4b0  pop     r14
0x18004a4b2  pop     r13
0x18004a4b4  pop     r12
0x18004a4b6  pop     rdi
0x18004a4b7  pop     rsi
0x18004a4b8  pop     rbp
0x18004a4b9  retn
```
