# MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::Create(ID3D12Device *,int,utl::function<long (ID3D12Device *,MFD3D::DX12CommandAllocatorManager::_entry &)>,bool)

- ea: `0x1800be3ec`
- end: `0x1800be5af`
- name: `?Create@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@QEAAJPEAUID3D12Device@@HV?$function@$$A6AJPEAUID3D12Device@@AEAU_entry@DX12CommandAllocatorManager@MFD3D@@@Z@utl@@_N@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800be5b8`

## callees

- `0x180053c48`
- `0x180054140`
- `0x180055670`
- `0x180059620`
- `0x1800663c0`
- `0x1800bdb98`
- `0x1800bdc3c`
- `0x1800be3ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800be520`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800be520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be554`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::Create(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  _QWORD *v8; // r14
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rsi
  signed int LastError; // eax
  unsigned int v14; // edi
  _QWORD v15[3]; // [rsp+30h] [rbp-48h] BYREF

  v15[2] = a4;
  if ( *((_DWORD *)a1 + 7) )
  {
    (*(void (__fastcall **)(__int64 *))*a4)(a4);
    return 2147549183LL;
  }
  else
  {
    v15[0] = operator new[](0x20u);
    v15[1] = 4;
    v8 = a1 + 1;
    wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&int CloseHandle(void *)>,unsigned __int64>::operator=(
      a1 + 1,
      v15);
    wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&int CloseHandle(void *)>,unsigned __int64>::reset(v15);
    if ( !a1[1] )
      goto LABEL_19;
    v9 = operator new[](0xC8u);
    if ( v9 )
    {
      *v9 = 4;
      v10 = v9 + 1;
      `eh vector constructor iterator'(
        v9 + 1,
        0x30u,
        4u,
        MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator::_allocator,
        MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator::~_allocator);
    }
    else
    {
      v10 = 0;
    }
    v11 = *a1;
    *a1 = (__int64)v10;
    if ( v11 )
      wistd::default_delete<MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator [0]>::operator()<MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator>();
    if ( *a1 )
    {
      if ( a1 + 4 != a4 )
      {
        (*(void (__fastcall **)(__int64 *))a1[4])(a1 + 4);
        (*(void (__fastcall **)(__int64 *, __int64 *))(*a4 + 8))(a4, a1 + 4);
        *a4 = (__int64)&utl::_FuncEmpty<long,ID3D12Device *,MFD3D::DX12ResourceManager::_entry &>::`vftable';
      }
      Microsoft::WRL::ComPtr<ID3D12Device>::operator=(a1 + 8, a2);
      *((_DWORD *)a1 + 6) = 1;
      v12 = 0;
      while ( 1 )
      {
        *(_QWORD *)(*v8 + 8 * v12) = CreateEventW(0, 1, 1, 0);
        if ( !*(_QWORD *)(*v8 + 8 * v12) )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (int)v12 >= 4 )
        {
          *((_DWORD *)a1 + 7) = 4;
          (*(void (__fastcall **)(__int64 *))*a4)(a4);
          return 0;
        }
      }
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      (*(void (__fastcall **)(__int64 *))*a4)(a4);
      return v14;
    }
    else
    {
LABEL_19:
      (*(void (__fastcall **)(__int64 *))*a4)(a4);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x1800be3ec  mov     [rsp+arg_10], rbx
0x1800be3f1  push    rbp
0x1800be3f2  push    rsi
0x1800be3f3  push    rdi
0x1800be3f4  push    r12
0x1800be3f6  push    r14
0x1800be3f8  sub     rsp, 50h
0x1800be3fc  mov     rax, cs:__security_cookie
0x1800be403  xor     rax, rsp
0x1800be406  mov     [rsp+78h+var_30], rax
0x1800be40b  mov     rbx, r9
0x1800be40e  mov     rbp, rdx
0x1800be411  mov     rdi, rcx
0x1800be414  mov     [rsp+78h+var_38], rbx
0x1800be419  cmp     dword ptr [rcx+1Ch], 0
0x1800be41d  jz      short loc_1800BE437
0x1800be41f  mov     rax, [r9]
0x1800be422  mov     rcx, rbx
0x1800be425  mov     rax, [rax]
0x1800be428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be42d  mov     eax, 8000FFFFh
0x1800be432  jmp     loc_1800BE58E
0x1800be437  mov     ecx, 20h ; ' '; unsigned __int64
0x1800be43c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800be441  mov     [rsp+78h+var_48], rax
0x1800be446  mov     r12d, 4
0x1800be44c  mov     [rsp+78h+var_40], r12
0x1800be451  lea     r14, [rdi+8]
0x1800be455  lea     rdx, [rsp+78h+var_48]
0x1800be45a  mov     rcx, r14
0x1800be45d  call    ??4?$unique_any_array_ptr@PEAXU?$default_delete@$$BY0A@PEAX@wistd@@U?$function_deleter@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@wil@@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64>::operator=(wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64> &&)
0x1800be462  lea     rcx, [rsp+78h+var_48]
0x1800be467  call    ?reset@?$unique_any_array_ptr@PEAXU?$default_delete@$$BY0A@PEAX@wistd@@U?$function_deleter@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64>::reset(void)
0x1800be46c  cmp     qword ptr [r14], 0
0x1800be470  jz      loc_1800BE57B
0x1800be476  mov     ecx, 0C8h; unsigned __int64
0x1800be47b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800be480  test    rax, rax
0x1800be483  jz      short loc_1800BE4B1
0x1800be485  mov     [rax], r12
0x1800be488  lea     rsi, [rax+8]
0x1800be48c  lea     rax, ??1_allocator@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@QEAA@XZ; MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator::~_allocator(void)
0x1800be493  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800be498  lea     r9, ??0_allocator@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@QEAA@XZ; void (*)(void *)
0x1800be49f  mov     r8d, r12d; unsigned __int64
0x1800be4a2  lea     edx, [r12+2Ch]; unsigned __int64
0x1800be4a7  mov     rcx, rsi; void *
0x1800be4aa  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800be4af  jmp     short loc_1800BE4B3
0x1800be4b1  xor     esi, esi
0x1800be4b3  mov     rdx, [rdi]
0x1800be4b6  mov     [rdi], rsi
0x1800be4b9  test    rdx, rdx
0x1800be4bc  jz      short loc_1800BE4C3
0x1800be4be  call    ??$?RU_allocator@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@@?$default_delete@$$BY0A@U_allocator@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@@wistd@@QEBAXPEAU_allocator@?$DX12TrackedResourcePool@U_entry@DX12CommandAllocatorManager@MFD3D@@@MFD3D@@@Z; wistd::default_delete<MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator [0]>::operator()<MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator>(MFD3D::DX12TrackedResourcePool<MFD3D::DX12CommandAllocatorManager::_entry>::_allocator *)
0x1800be4c3  cmp     qword ptr [rdi], 0
0x1800be4c7  jz      loc_1800BE57B
0x1800be4cd  lea     rsi, [rdi+20h]
0x1800be4d1  cmp     rsi, rbx
0x1800be4d4  jz      short loc_1800BE500
0x1800be4d6  mov     rax, [rsi]
0x1800be4d9  mov     rcx, rsi
0x1800be4dc  mov     rax, [rax]
0x1800be4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be4e4  mov     rax, [rbx]
0x1800be4e7  mov     rdx, rsi
0x1800be4ea  mov     rcx, rbx
0x1800be4ed  mov     rax, [rax+8]
0x1800be4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be4f6  lea     rax, ??_7?$_FuncEmpty@JPEAUID3D12Device@@AEAU_entry@DX12ResourceManager@MFD3D@@@utl@@6B@; const utl::_FuncEmpty<long,ID3D12Device *,MFD3D::DX12ResourceManager::_entry &>::`vftable'
0x1800be4fd  mov     [rbx], rax
0x1800be500  lea     rcx, [rdi+40h]
0x1800be504  mov     rdx, rbp
0x1800be507  call    ??4?$ComPtr@UID3D12Device@@@WRL@Microsoft@@QEAAAEAV012@PEAUID3D12Device@@@Z; Microsoft::WRL::ComPtr<ID3D12Device>::operator=(ID3D12Device *)
0x1800be50c  mov     ebp, 1
0x1800be511  mov     [rdi+18h], ebp
0x1800be514  xor     esi, esi
0x1800be516  xor     r9d, r9d; lpName
0x1800be519  mov     r8d, ebp; bInitialState
0x1800be51c  mov     edx, ebp; bManualReset
0x1800be51e  xor     ecx, ecx; lpEventAttributes
0x1800be520  call    cs:__imp_CreateEventW
0x1800be526  mov     rcx, [r14]
0x1800be529  mov     [rcx+rsi*8], rax
0x1800be52d  mov     rax, [r14]
0x1800be530  cmp     qword ptr [rax+rsi*8], 0
0x1800be535  jz      short loc_1800BE554
0x1800be537  add     esi, ebp
0x1800be539  cmp     esi, r12d
0x1800be53c  jl      short loc_1800BE516
0x1800be53e  mov     [rdi+1Ch], r12d
0x1800be542  mov     rax, [rbx]
0x1800be545  mov     rcx, rbx
0x1800be548  mov     rax, [rax]
0x1800be54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be550  xor     eax, eax
0x1800be552  jmp     short loc_1800BE58E
0x1800be554  call    cs:__imp_GetLastError
0x1800be55a  mov     edi, eax
0x1800be55c  test    eax, eax
0x1800be55e  jle     short loc_1800BE569
0x1800be560  movzx   edi, ax
0x1800be563  or      edi, 80070000h
0x1800be569  mov     rcx, [rbx]
0x1800be56c  mov     rax, [rcx]
0x1800be56f  mov     rcx, rbx
0x1800be572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be577  mov     eax, edi
0x1800be579  jmp     short loc_1800BE58E
0x1800be57b  mov     rax, [rbx]
0x1800be57e  mov     rcx, rbx
0x1800be581  mov     rax, [rax]
0x1800be584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be589  mov     eax, 8007000Eh
0x1800be58e  mov     rcx, [rsp+78h+var_30]
0x1800be593  xor     rcx, rsp; StackCookie
0x1800be596  call    __security_check_cookie
0x1800be59b  mov     rbx, [rsp+78h+arg_10]
0x1800be5a3  add     rsp, 50h
0x1800be5a7  pop     r14
0x1800be5a9  pop     r12
0x1800be5ab  pop     rdi
0x1800be5ac  pop     rsi
0x1800be5ad  pop     rbp
0x1800be5ae  retn
```
