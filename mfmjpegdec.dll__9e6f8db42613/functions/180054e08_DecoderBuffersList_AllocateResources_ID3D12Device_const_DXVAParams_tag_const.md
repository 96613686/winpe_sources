# DecoderBuffersList::AllocateResources(ID3D12Device * const,DXVAParams_tag const *)

- ea: `0x180054e08`
- end: `0x180055072`
- name: `?AllocateResources@DecoderBuffersList@@QEAAJQEAUID3D12Device@@PEBUDXVAParams_tag@@@Z`
- size: `618`
- prototype: `int(DecoderBuffersList *__hidden this, struct ID3D12Device *const, const struct DXVAParams_tag *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048ac4`

## callees

- `0x180020598`
- `0x18003a54c`
- `0x18003f138`
- `0x1800432d8`
- `0x18004aa94`
- `0x18004b30c`
- `0x180054cf4`
- `0x180054e08`
- `0x180055464`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054e49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180054e49`

## string_xrefs

- `0x180054fcb`: `DXVA Command Allocator`

## pseudocode

```c
__int64 __fastcall DecoderBuffersList::AllocateResources(
        DecoderBuffersList *this,
        struct ID3D12Device *const a2,
        const struct DXVAParams_tag *a3)
{
  _QWORD *v3; // rbx
  HANDLE EventW; // rax
  unsigned int BitstreamBuffer; // ebx
  unsigned int v9; // r14d
  __int64 v10; // rax
  int v11; // ecx
  DecoderBuffersList *v12; // rcx
  __int64 v13; // r15
  int v14; // eax
  int v15; // eax
  char *v16; // r13
  char *v17; // r15
  HRESULT (__stdcall *CreateCommandAllocator)(ID3D12Device *, D3D12_COMMAND_LIST_TYPE, const IID *const, void **); // rbx
  HRESULT (__stdcall *CreateFence)(ID3D12Device *, UINT64, D3D12_FENCE_FLAGS, const IID *const, void **); // rdi
  _QWORD v21[3]; // [rsp+30h] [rbp-18h] BYREF
  void *v22; // [rsp+90h] [rbp+48h] BYREF

  v3 = (_QWORD *)((char *)this + 600);
  if ( ((*((_QWORD *)this + 75) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_6;
  EventW = CreateEventW(0, 1, 0, 0);
  v21[0] = EventW;
  if ( v3 != v21 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3,
      EventW);
    v21[0] = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v21);
  if ( *v3 )
  {
LABEL_6:
    v9 = 0;
    v10 = 0;
    if ( *(_DWORD *)this )
    {
      while ( 1 )
      {
        v11 = *((_DWORD *)a3 + 20);
        if ( v11 )
        {
          v22 = operator new[]((unsigned int)(v11 + 8));
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
            (char *)this + 72 * v9 + 72,
            &v22);
          wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(&v22);
          v10 = v9;
        }
        v12 = (DecoderBuffersList *)*((unsigned int *)a3 + 16);
        v13 = 9 * v10;
        if ( (_DWORD)v12 )
        {
          v22 = operator new[]((unsigned int)((_DWORD)v12 + 8));
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
            (char *)this + 8 * v13 + 64,
            &v22);
          wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(&v22);
        }
        v14 = *((_DWORD *)a3 + 4);
        if ( v14 )
        {
          v22 = operator new[]((unsigned int)(v14 + 8));
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
            (char *)this + 8 * v13 + 48,
            &v22);
          wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(&v22);
        }
        v15 = *((_DWORD *)a3 + 8);
        if ( v15 )
        {
          v22 = operator new[]((unsigned int)(v15 + 8));
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
            (char *)this + 8 * v13 + 56,
            &v22);
          wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(&v22);
          v12 = (DecoderBuffersList *)*((unsigned int *)a3 + 8);
          *((_QWORD *)this + 9 * v9 + 10) = v12;
        }
        v16 = (char *)this + 72 * v9;
        BitstreamBuffer = DecoderBuffersList::AllocateBitstreamBuffer(
                            v12,
                            a2,
                            *((unsigned int *)a3 + 12),
                            (struct _DecoderBuffers *)(v16 + 24));
        if ( BitstreamBuffer )
          break;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16 + 32);
        *((_QWORD *)this + 9 * v9 + 5) = 0;
        v17 = (char *)this + 72 * v9;
        CreateCommandAllocator = a2->lpVtbl->CreateCommandAllocator;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17 + 32);
        BitstreamBuffer = ((__int64 (__fastcall *)(struct ID3D12Device *const, __int64, GUID *, char *))CreateCommandAllocator)(
                            a2,
                            4,
                            &GUID_6102dee4_af59_4b09_b999_b44d73f09b24,
                            v17 + 32);
        if ( BitstreamBuffer )
          break;
        (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)v17 + 4) + 48LL))(
          *((_QWORD *)v17 + 4),
          L"DXVA Command Allocator");
        v10 = ++v9;
        if ( v9 >= *(_DWORD *)this )
          goto LABEL_18;
      }
    }
    else
    {
LABEL_18:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 8);
      CreateFence = a2->lpVtbl->CreateFence;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 8);
      BitstreamBuffer = ((__int64 (__fastcall *)(struct ID3D12Device *const, _QWORD, _QWORD, GUID *, char *))CreateFence)(
                          a2,
                          0,
                          0,
                          &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76,
                          (char *)this + 8);
      if ( !BitstreamBuffer )
        *((_QWORD *)this + 2) = 0;
    }
  }
  else
  {
    BitstreamBuffer = -2147024890;
  }
  if ( g_wppLevels )
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids,
      BitstreamBuffer,
      this);
  return BitstreamBuffer;
}

```

## disassembly

```asm
0x180054e08  push    rbp
0x180054e0a  push    rbx
0x180054e0b  push    rsi
0x180054e0c  push    rdi
0x180054e0d  push    r12
0x180054e0f  push    r13
0x180054e11  push    r14
0x180054e13  push    r15
0x180054e15  mov     rbp, rsp
0x180054e18  sub     rsp, 48h
0x180054e1c  lea     rbx, [rcx+258h]
0x180054e23  xor     r13d, r13d
0x180054e26  mov     rax, [rbx]
0x180054e29  mov     rdi, r8
0x180054e2c  inc     rax
0x180054e2f  mov     r12, rdx
0x180054e32  mov     rsi, rcx
0x180054e35  test    rax, 0FFFFFFFFFFFFFFFEh
0x180054e3b  jnz     short loc_180054E83
0x180054e3d  xor     r9d, r9d; lpName
0x180054e40  lea     edx, [r13+1]; bManualReset
0x180054e44  xor     r8d, r8d; bInitialState
0x180054e47  xor     ecx, ecx; lpEventAttributes
0x180054e49  call    cs:__imp_CreateEventW
0x180054e4f  lea     rcx, [rbp+var_18]
0x180054e53  mov     [rbp+var_18], rax
0x180054e57  cmp     rbx, rcx
0x180054e5a  jz      short loc_180054E6B
0x180054e5c  mov     rdx, rax
0x180054e5f  mov     rcx, rbx
0x180054e62  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180054e67  mov     [rbp+var_18], r13
0x180054e6b  lea     rcx, [rbp+var_18]
0x180054e6f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180054e74  cmp     [rbx], r13
0x180054e77  jnz     short loc_180054E83
0x180054e79  mov     ebx, 80070006h
0x180054e7e  jmp     loc_180055032
0x180054e83  mov     r14d, r13d
0x180054e86  mov     eax, r13d
0x180054e89  cmp     [rsi], r13d
0x180054e8c  jbe     loc_180054FED
0x180054e92  mov     ecx, [rdi+50h]
0x180054e95  mov     ebx, r14d
0x180054e98  test    ecx, ecx
0x180054e9a  jz      short loc_180054EC8
0x180054e9c  add     ecx, 8; unsigned __int64
0x180054e9f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180054ea4  mov     [rbp+arg_0], rax
0x180054ea8  lea     rdx, [rbp+arg_0]
0x180054eac  lea     rax, [rbx+1]
0x180054eb0  lea     rax, [rax+rax*8]
0x180054eb4  lea     rcx, [rsi+rax*8]
0x180054eb8  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180054ebd  lea     rcx, [rbp+arg_0]
0x180054ec1  call    ??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)
0x180054ec6  mov     eax, ebx
0x180054ec8  mov     ecx, [rdi+40h]
0x180054ecb  lea     r15, [rax+rax*8]
0x180054ecf  test    ecx, ecx
0x180054ed1  jz      short loc_180054EF9
0x180054ed3  add     ecx, 8; unsigned __int64
0x180054ed6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180054edb  lea     rcx, [rsi+40h]
0x180054edf  mov     [rbp+arg_0], rax
0x180054ee3  lea     rcx, [rcx+r15*8]
0x180054ee7  lea     rdx, [rbp+arg_0]
0x180054eeb  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180054ef0  lea     rcx, [rbp+arg_0]
0x180054ef4  call    ??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)
0x180054ef9  mov     eax, [rdi+10h]
0x180054efc  test    eax, eax
0x180054efe  jz      short loc_180054F26
0x180054f00  lea     ecx, [rax+8]; unsigned __int64
0x180054f03  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180054f08  lea     rcx, [rsi+30h]
0x180054f0c  mov     [rbp+arg_0], rax
0x180054f10  lea     rcx, [rcx+r15*8]
0x180054f14  lea     rdx, [rbp+arg_0]
0x180054f18  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180054f1d  lea     rcx, [rbp+arg_0]
0x180054f21  call    ??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)
0x180054f26  mov     eax, [rdi+20h]
0x180054f29  test    eax, eax
0x180054f2b  jz      short loc_180054F5F
0x180054f2d  lea     ecx, [rax+8]; unsigned __int64
0x180054f30  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180054f35  lea     rcx, [rsi+38h]
0x180054f39  mov     [rbp+arg_0], rax
0x180054f3d  lea     rcx, [rcx+r15*8]
0x180054f41  lea     rdx, [rbp+arg_0]
0x180054f45  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180054f4a  lea     rcx, [rbp+arg_0]
0x180054f4e  call    ??1?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>::~unique_ptr<_GUID [0],wistd::default_delete<_GUID [0]>>(void)
0x180054f53  mov     ecx, [rdi+20h]; this
0x180054f56  lea     rax, [rbx+rbx*8]
0x180054f5a  mov     [rsi+rax*8+50h], rcx
0x180054f5f  mov     r8d, [rdi+30h]; unsigned __int64
0x180054f63  lea     r15, [rbx+rbx*8]
0x180054f67  lea     r13, [rsi+r15*8]
0x180054f6b  mov     rdx, r12; struct ID3D12Device *
0x180054f6e  lea     r9, [r13+18h]; struct _DecoderBuffers *
0x180054f72  call    ?AllocateBitstreamBuffer@DecoderBuffersList@@AEAAJQEAUID3D12Device@@_KAEAU_DecoderBuffers@@@Z; DecoderBuffersList::AllocateBitstreamBuffer(ID3D12Device * const,unsigned __int64,_DecoderBuffers &)
0x180054f77  mov     ebx, eax
0x180054f79  test    eax, eax
0x180054f7b  jnz     loc_180055032
0x180054f81  lea     rcx, [r13+20h]
0x180054f85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054f8a  xor     r13d, r13d
0x180054f8d  mov     [rsi+r15*8+28h], r13
0x180054f92  lea     r15, [rsi+r15*8]
0x180054f96  mov     rax, [r12]
0x180054f9a  lea     rcx, [r15+20h]
0x180054f9e  mov     rbx, [rax+48h]
0x180054fa2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054fa7  lea     r9, [r15+20h]
0x180054fab  mov     rcx, r12
0x180054fae  lea     r8, _GUID_6102dee4_af59_4b09_b999_b44d73f09b24
0x180054fb5  mov     rax, rbx
0x180054fb8  lea     edx, [r13+4]
0x180054fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fc1  mov     ebx, eax
0x180054fc3  test    eax, eax
0x180054fc5  jnz     short loc_180055032
0x180054fc7  mov     rcx, [r15+20h]
0x180054fcb  lea     rdx, aDxvaCommandAll; "DXVA Command Allocator"
0x180054fd2  mov     rax, [rcx]
0x180054fd5  mov     rax, [rax+30h]
0x180054fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fde  inc     r14d
0x180054fe1  mov     eax, r14d
0x180054fe4  cmp     r14d, [rsi]
0x180054fe7  jb      loc_180054E92
0x180054fed  lea     rbx, [rsi+8]
0x180054ff1  mov     rcx, rbx
0x180054ff4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054ff9  mov     rax, [r12]
0x180054ffd  mov     rcx, rbx
0x180055000  mov     rdi, [rax+120h]
0x180055007  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005500c  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x180055013  mov     [rsp+48h+var_28], rbx
0x180055018  xor     r8d, r8d
0x18005501b  xor     edx, edx
0x18005501d  mov     rcx, r12
0x180055020  mov     rax, rdi
0x180055023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055028  mov     ebx, eax
0x18005502a  test    eax, eax
0x18005502c  jnz     short loc_180055032
0x18005502e  mov     [rsi+10h], r13
0x180055032  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055039  jb      short loc_18005505F
0x18005503b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055042  lea     r8, WPP_ae6695e45de23f37da500d01f36f53ae_Traceguids
0x180055049  mov     edx, 12h
0x18005504e  mov     [rsp+48h+var_28], rsi
0x180055053  mov     r9d, ebx
0x180055056  mov     rcx, [rcx+10h]
0x18005505a  call    WPP_SF_dq
0x18005505f  mov     eax, ebx
0x180055061  add     rsp, 48h
0x180055065  pop     r15
0x180055067  pop     r14
0x180055069  pop     r13
0x18005506b  pop     r12
0x18005506d  pop     rdi
0x18005506e  pop     rsi
0x18005506f  pop     rbx
0x180055070  pop     rbp
0x180055071  retn
```
