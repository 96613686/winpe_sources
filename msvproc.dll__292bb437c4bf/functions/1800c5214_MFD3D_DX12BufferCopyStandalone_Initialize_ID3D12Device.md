# MFD3D::DX12BufferCopyStandalone::Initialize(ID3D12Device *)

- ea: `0x1800c5214`
- end: `0x1800c53e6`
- name: `?Initialize@DX12BufferCopyStandalone@MFD3D@@QEAAJPEAUID3D12Device@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(MFD3D::DX12BufferCopyStandalone *__hidden this, struct ID3D12Device *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c29d0`
- `0x1800c4e30`

## callees

- `0x180054140`
- `0x1800c3788`
- `0x1800c5214`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c5395`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c5395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c53ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c53ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall MFD3D::DX12BufferCopyStandalone::Initialize(
        MFD3D::DX12BufferCopyStandalone *this,
        struct ID3D12Device *a2)
{
  signed int result; // eax
  HRESULT (__stdcall *CreateCommandAllocator)(ID3D12Device *, D3D12_COMMAND_LIST_TYPE, const IID *const, void **); // rbp
  _QWORD *v6; // rsi
  __int64 v7; // rcx
  HRESULT (__stdcall *CreateCommandList)(ID3D12Device *, UINT, D3D12_COMMAND_LIST_TYPE, ID3D12CommandAllocator *, ID3D12PipelineState *, const IID *const, void **); // rbp
  __int64 v9; // rcx
  HRESULT (__stdcall *CreateFence)(ID3D12Device *, UINT64, D3D12_FENCE_FLAGS, const IID *const, void **); // rbp
  __int64 v11; // rcx
  HRESULT (__stdcall *CreateCommandQueue)(ID3D12Device *, const D3D12_COMMAND_QUEUE_DESC *, const IID *const, void **); // rsi
  __int64 v13; // rcx
  HANDLE EventW; // rax
  __int128 v15; // [rsp+40h] [rbp-38h] BYREF

  v15 = 0;
  if ( !a2 )
    return -2147024809;
  LODWORD(v15) = 3;
  CreateCommandAllocator = a2->lpVtbl->CreateCommandAllocator;
  v6 = (_QWORD *)((char *)this + 8);
  v7 = *((_QWORD *)this + 1);
  *v6 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  result = ((__int64 (__fastcall *)(struct ID3D12Device *, __int64, GUID *, _QWORD *))CreateCommandAllocator)(
             a2,
             3,
             &GUID_6102dee4_af59_4b09_b999_b44d73f09b24,
             v6);
  if ( result >= 0 )
  {
    CreateCommandList = a2->lpVtbl->CreateCommandList;
    v9 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    result = ((__int64 (__fastcall *)(struct ID3D12Device *, _QWORD, __int64, _QWORD, _QWORD, GUID *, char *))CreateCommandList)(
               a2,
               0,
               3,
               *v6,
               0,
               &GUID_5b160d0f_ac1b_4185_8ba8_b3ae42a5a455,
               (char *)this + 16);
    if ( result >= 0 )
    {
      CreateFence = a2->lpVtbl->CreateFence;
      v11 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      result = ((__int64 (__fastcall *)(struct ID3D12Device *, _QWORD, _QWORD, GUID *, char *))CreateFence)(
                 a2,
                 0,
                 0,
                 &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76,
                 (char *)this + 24);
      if ( result >= 0 )
      {
        CreateCommandQueue = a2->lpVtbl->CreateCommandQueue;
        v13 = *(_QWORD *)this;
        *(_QWORD *)this = 0;
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        result = ((__int64 (__fastcall *)(struct ID3D12Device *, __int128 *, GUID *, MFD3D::DX12BufferCopyStandalone *))CreateCommandQueue)(
                   a2,
                   &v15,
                   &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
                   this);
        if ( result >= 0 )
        {
          EventW = CreateEventW(0, 0, 0, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            (char *)this + 48,
            EventW);
          if ( *((_QWORD *)this + 6) )
          {
            return 0;
          }
          else
          {
            result = GetLastError();
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c5214  mov     [rsp+arg_10], rbx
0x1800c5219  mov     [rsp+arg_18], rbp
0x1800c521e  push    rsi
0x1800c521f  push    rdi
0x1800c5220  push    r14
0x1800c5222  sub     rsp, 60h
0x1800c5226  mov     rax, cs:__security_cookie
0x1800c522d  xor     rax, rsp
0x1800c5230  mov     [rsp+78h+var_28], rax
0x1800c5235  mov     rbx, rdx
0x1800c5238  mov     rdi, rcx
0x1800c523b  xorps   xmm0, xmm0
0x1800c523e  movups  [rsp+78h+var_38], xmm0
0x1800c5243  test    rdx, rdx
0x1800c5246  jnz     short loc_1800C5252
0x1800c5248  mov     eax, 80070057h
0x1800c524d  jmp     loc_1800C53C4
0x1800c5252  mov     dword ptr [rsp+78h+var_38], 3
0x1800c525a  mov     rax, [rdx]
0x1800c525d  mov     rbp, [rax+48h]
0x1800c5261  lea     rsi, [rcx+8]
0x1800c5265  mov     rcx, [rsi]
0x1800c5268  mov     qword ptr [rsi], 0
0x1800c526f  test    rcx, rcx
0x1800c5272  jz      short loc_1800C5281
0x1800c5274  mov     rax, [rcx]
0x1800c5277  mov     rax, [rax+10h]
0x1800c527b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5280  nop
0x1800c5281  mov     r9, rsi
0x1800c5284  lea     r8, _GUID_6102dee4_af59_4b09_b999_b44d73f09b24
0x1800c528b  mov     edx, 3
0x1800c5290  mov     rcx, rbx
0x1800c5293  mov     rax, rbp
0x1800c5296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c529b  test    eax, eax
0x1800c529d  js      loc_1800C53C4
0x1800c52a3  mov     rax, [rbx]
0x1800c52a6  mov     rbp, [rax+60h]
0x1800c52aa  lea     r14, [rdi+10h]
0x1800c52ae  mov     rcx, [r14]
0x1800c52b1  mov     qword ptr [r14], 0
0x1800c52b8  test    rcx, rcx
0x1800c52bb  jz      short loc_1800C52CA
0x1800c52bd  mov     rax, [rcx]
0x1800c52c0  mov     rax, [rax+10h]
0x1800c52c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c52c9  nop
0x1800c52ca  mov     [rsp+78h+var_48], r14
0x1800c52cf  lea     rax, _GUID_5b160d0f_ac1b_4185_8ba8_b3ae42a5a455
0x1800c52d6  mov     [rsp+78h+var_50], rax
0x1800c52db  mov     [rsp+78h+var_58], 0
0x1800c52e4  mov     r9, [rsi]
0x1800c52e7  xor     edx, edx
0x1800c52e9  lea     r8d, [rdx+3]
0x1800c52ed  mov     rcx, rbx
0x1800c52f0  mov     rax, rbp
0x1800c52f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c52f8  test    eax, eax
0x1800c52fa  js      loc_1800C53C4
0x1800c5300  mov     rax, [rbx]
0x1800c5303  mov     rbp, [rax+120h]
0x1800c530a  lea     rsi, [rdi+18h]
0x1800c530e  mov     rcx, [rsi]
0x1800c5311  mov     qword ptr [rsi], 0
0x1800c5318  test    rcx, rcx
0x1800c531b  jz      short loc_1800C532A
0x1800c531d  mov     rax, [rcx]
0x1800c5320  mov     rax, [rax+10h]
0x1800c5324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5329  nop
0x1800c532a  mov     [rsp+78h+var_58], rsi
0x1800c532f  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800c5336  xor     r8d, r8d
0x1800c5339  xor     edx, edx
0x1800c533b  mov     rcx, rbx
0x1800c533e  mov     rax, rbp
0x1800c5341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5346  test    eax, eax
0x1800c5348  js      short loc_1800C53C4
0x1800c534a  mov     rax, [rbx]
0x1800c534d  mov     rsi, [rax+40h]
0x1800c5351  mov     rcx, [rdi]
0x1800c5354  mov     qword ptr [rdi], 0
0x1800c535b  test    rcx, rcx
0x1800c535e  jz      short loc_1800C536D
0x1800c5360  mov     rdx, [rcx]
0x1800c5363  mov     rax, [rdx+10h]
0x1800c5367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c536c  nop
0x1800c536d  mov     r9, rdi
0x1800c5370  lea     r8, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x1800c5377  lea     rdx, [rsp+78h+var_38]
0x1800c537c  mov     rcx, rbx
0x1800c537f  mov     rax, rsi
0x1800c5382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5387  test    eax, eax
0x1800c5389  js      short loc_1800C53C4
0x1800c538b  xor     r9d, r9d; lpName
0x1800c538e  xor     r8d, r8d; bInitialState
0x1800c5391  xor     edx, edx; bManualReset
0x1800c5393  xor     ecx, ecx; lpEventAttributes
0x1800c5395  call    cs:__imp_CreateEventW
0x1800c539b  mov     rdx, rax
0x1800c539e  lea     rcx, [rdi+30h]
0x1800c53a2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c53a7  cmp     qword ptr [rdi+30h], 0
0x1800c53ac  jnz     short loc_1800C53C2
0x1800c53ae  call    cs:__imp_GetLastError
0x1800c53b4  test    eax, eax
0x1800c53b6  jle     short loc_1800C53C4
0x1800c53b8  movzx   eax, ax
0x1800c53bb  or      eax, 80070000h
0x1800c53c0  jmp     short loc_1800C53C4
0x1800c53c2  xor     eax, eax
0x1800c53c4  mov     rcx, [rsp+78h+var_28]
0x1800c53c9  xor     rcx, rsp; StackCookie
0x1800c53cc  call    __security_check_cookie
0x1800c53d1  lea     r11, [rsp+78h+var_18]
0x1800c53d6  mov     rbx, [r11+30h]
0x1800c53da  mov     rbp, [r11+38h]
0x1800c53de  mov     rsp, r11
0x1800c53e1  pop     r14
0x1800c53e3  pop     rdi
0x1800c53e4  pop     rsi
0x1800c53e5  retn
```
