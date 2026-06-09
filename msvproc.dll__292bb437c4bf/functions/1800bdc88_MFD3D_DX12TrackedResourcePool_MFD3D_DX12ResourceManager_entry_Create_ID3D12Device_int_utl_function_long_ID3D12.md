# MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::Create(ID3D12Device *,int,utl::function<long (ID3D12Device *,MFD3D::DX12ResourceManager::_entry &)>,bool)

- ea: `0x1800bdc88`
- end: `0x1800bde24`
- name: `?Create@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@QEAAJPEAUID3D12Device@@HV?$function@$$A6AJPEAUID3D12Device@@AEAU_entry@DX12ResourceManager@MFD3D@@@Z@utl@@_N@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800bdf10`

## callees

- `0x180053c48`
- `0x180054140`
- `0x180055670`
- `0x1800596a0`
- `0x1800663c0`
- `0x1800bdb98`
- `0x1800bdbec`
- `0x1800bdc3c`
- `0x1800bdc88`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdd95`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdd95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bddc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bddc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::Create(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        void (__fastcall ***a4)(_QWORD))
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
    (**a4)(a4);
    return 2147549183LL;
  }
  else
  {
    v15[0] = operator new[](0x40u);
    v15[1] = 8;
    v8 = a1 + 1;
    wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&int CloseHandle(void *)>,unsigned __int64>::operator=(
      a1 + 1,
      v15);
    wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&int CloseHandle(void *)>,unsigned __int64>::reset(v15);
    if ( !a1[1] )
      goto LABEL_17;
    v9 = operator new[](0x148u);
    if ( v9 )
    {
      *v9 = 8;
      v10 = v9 + 1;
      `eh vector constructor iterator'(
        v9 + 1,
        0x28u,
        8u,
        MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator::_allocator,
        MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator::~_allocator);
    }
    else
    {
      v10 = 0;
    }
    v11 = *a1;
    *a1 = (__int64)v10;
    if ( v11 )
      wistd::default_delete<MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator [0]>::operator()<MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator>();
    if ( *a1 )
    {
      utl::function<long (ID3D12Device *,MFD3D::DX12ResourceManager::_entry &)>::operator=(a1 + 4, a4);
      Microsoft::WRL::ComPtr<ID3D12Device>::operator=(a1 + 8, a2);
      *((_DWORD *)a1 + 6) = 1;
      v12 = 0;
      while ( 1 )
      {
        *(_QWORD *)(*v8 + 8 * v12) = CreateEventW(0, 1, 1, 0);
        if ( !*(_QWORD *)(*v8 + 8 * v12) )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (int)v12 >= 8 )
        {
          *((_DWORD *)a1 + 7) = 8;
          (**a4)(a4);
          return 0;
        }
      }
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      (**a4)(a4);
      return v14;
    }
    else
    {
LABEL_17:
      (**a4)(a4);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x1800bdc88  mov     [rsp+arg_10], rbx
0x1800bdc8d  push    rbp
0x1800bdc8e  push    rsi
0x1800bdc8f  push    rdi
0x1800bdc90  push    r12
0x1800bdc92  push    r14
0x1800bdc94  sub     rsp, 50h
0x1800bdc98  mov     rax, cs:__security_cookie
0x1800bdc9f  xor     rax, rsp
0x1800bdca2  mov     [rsp+78h+var_30], rax
0x1800bdca7  mov     rbx, r9
0x1800bdcaa  mov     rbp, rdx
0x1800bdcad  mov     rdi, rcx
0x1800bdcb0  mov     [rsp+78h+var_38], rbx
0x1800bdcb5  cmp     dword ptr [rcx+1Ch], 0
0x1800bdcb9  jz      short loc_1800BDCD3
0x1800bdcbb  mov     rax, [r9]
0x1800bdcbe  mov     rcx, rbx
0x1800bdcc1  mov     rax, [rax]
0x1800bdcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdcc9  mov     eax, 8000FFFFh
0x1800bdcce  jmp     loc_1800BDE03
0x1800bdcd3  mov     ecx, 40h ; '@'; unsigned __int64
0x1800bdcd8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bdcdd  mov     [rsp+78h+var_48], rax
0x1800bdce2  mov     r12d, 8
0x1800bdce8  mov     [rsp+78h+var_40], r12
0x1800bdced  lea     r14, [rdi+8]
0x1800bdcf1  lea     rdx, [rsp+78h+var_48]
0x1800bdcf6  mov     rcx, r14
0x1800bdcf9  call    ??4?$unique_any_array_ptr@PEAXU?$default_delete@$$BY0A@PEAX@wistd@@U?$function_deleter@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@wil@@_K@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64>::operator=(wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64> &&)
0x1800bdcfe  lea     rcx, [rsp+78h+var_48]
0x1800bdd03  call    ?reset@?$unique_any_array_ptr@PEAXU?$default_delete@$$BY0A@PEAX@wistd@@U?$function_deleter@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wistd::default_delete<void * [0]>,wil::function_deleter<int (*)(void *),&CloseHandle(void *)>,unsigned __int64>::reset(void)
0x1800bdd08  cmp     qword ptr [r14], 0
0x1800bdd0c  jz      loc_1800BDDF0
0x1800bdd12  mov     ecx, 148h; unsigned __int64
0x1800bdd17  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bdd1c  test    rax, rax
0x1800bdd1f  jz      short loc_1800BDD4D
0x1800bdd21  mov     [rax], r12
0x1800bdd24  lea     rsi, [rax+8]
0x1800bdd28  lea     rax, ??1_allocator@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@QEAA@XZ; MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator::~_allocator(void)
0x1800bdd2f  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800bdd34  lea     r9, ??0_allocator@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@QEAA@XZ; void (*)(void *)
0x1800bdd3b  mov     r8d, r12d; unsigned __int64
0x1800bdd3e  lea     edx, [r12+20h]; unsigned __int64
0x1800bdd43  mov     rcx, rsi; void *
0x1800bdd46  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800bdd4b  jmp     short loc_1800BDD4F
0x1800bdd4d  xor     esi, esi
0x1800bdd4f  mov     rdx, [rdi]
0x1800bdd52  mov     [rdi], rsi
0x1800bdd55  test    rdx, rdx
0x1800bdd58  jz      short loc_1800BDD5F
0x1800bdd5a  call    ??$?RU_allocator@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@@?$default_delete@$$BY0A@U_allocator@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@@wistd@@QEBAXPEAU_allocator@?$DX12TrackedResourcePool@U_entry@DX12ResourceManager@MFD3D@@@MFD3D@@@Z; wistd::default_delete<MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator [0]>::operator()<MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator>(MFD3D::DX12TrackedResourcePool<MFD3D::DX12ResourceManager::_entry>::_allocator *)
0x1800bdd5f  cmp     qword ptr [rdi], 0
0x1800bdd63  jz      loc_1800BDDF0
0x1800bdd69  lea     rcx, [rdi+20h]
0x1800bdd6d  mov     rdx, rbx
0x1800bdd70  call    ??4?$function@$$A6AJPEAUID3D12Device@@AEAU_entry@DX12ResourceManager@MFD3D@@@Z@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::function<long (ID3D12Device *,MFD3D::DX12ResourceManager::_entry &)>::operator=(utl::function<long (ID3D12Device *,MFD3D::DX12ResourceManager::_entry &)> &&)
0x1800bdd75  lea     rcx, [rdi+40h]
0x1800bdd79  mov     rdx, rbp
0x1800bdd7c  call    ??4?$ComPtr@UID3D12Device@@@WRL@Microsoft@@QEAAAEAV012@PEAUID3D12Device@@@Z; Microsoft::WRL::ComPtr<ID3D12Device>::operator=(ID3D12Device *)
0x1800bdd81  mov     ebp, 1
0x1800bdd86  mov     [rdi+18h], ebp
0x1800bdd89  xor     esi, esi
0x1800bdd8b  xor     r9d, r9d; lpName
0x1800bdd8e  mov     r8d, ebp; bInitialState
0x1800bdd91  mov     edx, ebp; bManualReset
0x1800bdd93  xor     ecx, ecx; lpEventAttributes
0x1800bdd95  call    cs:__imp_CreateEventW
0x1800bdd9b  mov     rcx, [r14]
0x1800bdd9e  mov     [rcx+rsi*8], rax
0x1800bdda2  mov     rax, [r14]
0x1800bdda5  cmp     qword ptr [rax+rsi*8], 0
0x1800bddaa  jz      short loc_1800BDDC9
0x1800bddac  add     esi, ebp
0x1800bddae  cmp     esi, r12d
0x1800bddb1  jl      short loc_1800BDD8B
0x1800bddb3  mov     [rdi+1Ch], r12d
0x1800bddb7  mov     rax, [rbx]
0x1800bddba  mov     rcx, rbx
0x1800bddbd  mov     rax, [rax]
0x1800bddc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bddc5  xor     eax, eax
0x1800bddc7  jmp     short loc_1800BDE03
0x1800bddc9  call    cs:__imp_GetLastError
0x1800bddcf  mov     edi, eax
0x1800bddd1  test    eax, eax
0x1800bddd3  jle     short loc_1800BDDDE
0x1800bddd5  movzx   edi, ax
0x1800bddd8  or      edi, 80070000h
0x1800bddde  mov     rcx, [rbx]
0x1800bdde1  mov     rax, [rcx]
0x1800bdde4  mov     rcx, rbx
0x1800bdde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bddec  mov     eax, edi
0x1800bddee  jmp     short loc_1800BDE03
0x1800bddf0  mov     rax, [rbx]
0x1800bddf3  mov     rcx, rbx
0x1800bddf6  mov     rax, [rax]
0x1800bddf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bddfe  mov     eax, 8007000Eh
0x1800bde03  mov     rcx, [rsp+78h+var_30]
0x1800bde08  xor     rcx, rsp; StackCookie
0x1800bde0b  call    __security_check_cookie
0x1800bde10  mov     rbx, [rsp+78h+arg_10]
0x1800bde18  add     rsp, 50h
0x1800bde1c  pop     r14
0x1800bde1e  pop     r12
0x1800bde20  pop     rdi
0x1800bde21  pop     rsi
0x1800bde22  pop     rbp
0x1800bde23  retn
```
