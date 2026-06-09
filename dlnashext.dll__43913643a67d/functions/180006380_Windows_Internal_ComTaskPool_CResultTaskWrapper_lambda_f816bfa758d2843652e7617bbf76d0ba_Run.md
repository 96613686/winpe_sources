# Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f816bfa758d2843652e7617bbf76d0ba___::Run

- ea: `0x180006380`
- end: `0x180006533`
- name: `Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f816bfa758d2843652e7617bbf76d0ba___::Run`
- size: `435`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180005f60`
- `0x180006380`
- `0x180006540`
- `0x180006590`
- `0x180011930`
- `0x180012a4c`
- `0x180024fd8`
- `0x180035010`

## import_xrefs

- `ext-ms-win-casting-device-l1-1-0!GetPlatformSpecificDeviceController` at `0x1800063d1`
- `ext-ms-win-casting-device-l1-1-0!GetPlatformSpecificDeviceController` at `0x1800063d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::CResultTaskWrapper__lambda_f816bfa758d2843652e7617bbf76d0ba___::Run(
        __int64 a1)
{
  const unsigned __int16 *v2; // rdx
  _DWORD *v3; // rbx
  __int64 v4; // rbp
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64); // rsi
  __int64 v7; // rbx
  HSTRING *v8; // rax
  _DWORD *v9; // rsi
  __int64 v10; // r14
  __int64 (__fastcall *v11)(__int64, __int64 *); // rsi
  __int64 *v12; // rbx
  __int64 v13; // r8
  __int64 result; // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF

  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 16) + 248LL) )
  {
    if ( (unsigned __int8)IsGetMediaServerFromUniqueDeviceNameAsyncPresent() )
    {
      v15 = 0;
      v3 = *(_DWORD **)(a1 + 24);
      *v3 = GetPlatformSpecificDeviceController(1, &v15);
      if ( **(int **)(a1 + 24) >= 0 )
      {
        v4 = *(_QWORD *)(a1 + 16);
        v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
        v6 = **v15;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)(v4 + 248));
        **(_DWORD **)(a1 + 24) = v6(v5, &GUID_4feeb26d_50a7_402b_896a_be95064d6bff, v4 + 248);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v15);
    }
    else
    {
      v7 = *(_QWORD *)(a1 + 16);
      v8 = Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[41])v2);
      v9 = *(_DWORD **)(a1 + 24);
      *v9 = Windows::Foundation::ActivateInstance<Windows::Media::Streaming::IDeviceController>(*v8, v7 + 248);
    }
  }
  if ( **(int **)(a1 + 24) >= 0 )
  {
    **(_BYTE **)(a1 + 32) = 1;
    ++*(_DWORD *)(*(_QWORD *)(a1 + 16) + 240LL);
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 248LL);
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL);
    v12 = *(__int64 **)(a1 + 40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v12);
    **(_DWORD **)(a1 + 24) = v11(v10, v12);
    if ( **(int **)(a1 + 24) >= 0 )
    {
      **(_DWORD **)(a1 + 24) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(***(_QWORD ***)(a1 + 40) + 56LL))(
                                 **(_QWORD **)(a1 + 40),
                                 *(_QWORD *)(a1 + 48));
      if ( **(int **)(a1 + 24) < 0 )
      {
        **(_DWORD **)(a1 + 48) = 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          **(unsigned int **)(a1 + 48),
          v13,
          *(_QWORD *)(a1 + 16),
          **(_DWORD **)(a1 + 48));
      }
    }
  }
  result = **(unsigned int **)(a1 + 24);
  **(_DWORD **)(a1 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x180006380  push    rbx
0x180006382  push    rbp
0x180006383  push    rsi
0x180006384  push    rdi
0x180006385  push    r14
0x180006387  push    r15
0x180006389  sub     rsp, 68h
0x18000638d  mov     rax, cs:__security_cookie
0x180006394  xor     rax, rsp
0x180006397  mov     [rsp+98h+var_40], rax
0x18000639c  mov     rdi, rcx
0x18000639f  mov     rax, [rcx+10h]
0x1800063a3  cmp     qword ptr [rax+0F8h], 0
0x1800063ab  jnz     loc_18000644C
0x1800063b1  call    IsGetMediaServerFromUniqueDeviceNameAsyncPresent
0x1800063b6  test    al, al
0x1800063b8  jz      short loc_180006429
0x1800063ba  mov     [rsp+98h+var_68], 0
0x1800063c3  mov     rbx, [rdi+18h]
0x1800063c7  lea     rdx, [rsp+98h+var_68]
0x1800063cc  mov     ecx, 1
0x1800063d1  call    cs:__imp_GetPlatformSpecificDeviceController
0x1800063d7  mov     [rbx], eax
0x1800063d9  mov     rax, [rdi+18h]
0x1800063dd  cmp     dword ptr [rax], 0
0x1800063e0  jl      short loc_18000641D
0x1800063e2  mov     rbp, [rdi+10h]
0x1800063e6  mov     rbx, [rsp+98h+var_68]
0x1800063eb  mov     rax, [rbx]
0x1800063ee  mov     rsi, [rax]
0x1800063f1  lea     rcx, [rbp+0F8h]
0x1800063f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800063fd  lea     r8, [rbp+0F8h]
0x180006404  lea     rdx, _GUID_4feeb26d_50a7_402b_896a_be95064d6bff
0x18000640b  mov     rcx, rbx
0x18000640e  mov     rax, rsi
0x180006411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006416  nop
0x180006417  mov     rcx, [rdi+18h]
0x18000641b  mov     [rcx], eax
0x18000641d  lea     rcx, [rsp+98h+var_68]
0x180006422  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006427  jmp     short loc_18000644C
0x180006429  mov     rbx, [rdi+10h]
0x18000642d  lea     rcx, [rsp+98h+string]; string
0x180006432  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x180006437  mov     rsi, [rdi+18h]
0x18000643b  lea     rdx, [rbx+0F8h]
0x180006442  mov     rcx, [rax]
0x180006445  call    ??$ActivateInstance@UIDeviceController@Streaming@Media@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIDeviceController@Streaming@Media@1@@Z; Windows::Foundation::ActivateInstance<Windows::Media::Streaming::IDeviceController>(HSTRING__ *,Windows::Media::Streaming::IDeviceController * *)
0x18000644a  mov     [rsi], eax
0x18000644c  mov     rax, [rdi+18h]
0x180006450  cmp     dword ptr [rax], 0
0x180006453  jl      loc_18000650D
0x180006459  mov     rax, [rdi+20h]
0x18000645d  mov     byte ptr [rax], 1
0x180006460  mov     rax, [rdi+10h]
0x180006464  inc     dword ptr [rax+0F0h]
0x18000646a  mov     rax, [rdi+10h]
0x18000646e  mov     r14, [rax+0F8h]
0x180006475  mov     rax, [r14]
0x180006478  mov     rsi, [rax+30h]
0x18000647c  mov     rbx, [rdi+28h]
0x180006480  mov     rcx, rbx
0x180006483  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180006488  mov     rdx, rbx
0x18000648b  mov     rcx, r14
0x18000648e  mov     rax, rsi
0x180006491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006496  mov     rcx, [rdi+18h]
0x18000649a  mov     [rcx], eax
0x18000649c  mov     rax, [rdi+18h]
0x1800064a0  cmp     dword ptr [rax], 0
0x1800064a3  jl      short loc_18000650D
0x1800064a5  mov     rax, [rdi+28h]
0x1800064a9  mov     rcx, [rax]
0x1800064ac  mov     rax, [rcx]
0x1800064af  mov     rdx, [rdi+30h]
0x1800064b3  mov     rax, [rax+38h]
0x1800064b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064bc  mov     rcx, [rdi+18h]
0x1800064c0  mov     [rcx], eax
0x1800064c2  mov     rax, [rdi+18h]
0x1800064c6  cmp     dword ptr [rax], 0
0x1800064c9  jl      short loc_180006503
0x1800064cb  lea     rax, WPP_GLOBAL_Control
0x1800064d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064d9  cmp     rcx, rax
0x1800064dc  jz      short loc_18000650D
0x1800064de  test    byte ptr [rcx+1Ch], 40h
0x1800064e2  jz      short loc_18000650D
0x1800064e4  cmp     byte ptr [rcx+19h], 4
0x1800064e8  jb      short loc_18000650D
0x1800064ea  mov     rax, [rdi+30h]
0x1800064ee  mov     edx, [rax]
0x1800064f0  mov     [rsp+98h+var_78], edx
0x1800064f4  mov     r9, [rdi+10h]
0x1800064f8  mov     rcx, [rcx+10h]
0x1800064fc  call    WPP_SF_qD
0x180006501  jmp     short loc_18000650D
0x180006503  mov     rax, [rdi+30h]
0x180006507  mov     dword ptr [rax], 0
0x18000650d  mov     rax, [rdi+18h]
0x180006511  mov     rcx, [rdi+38h]
0x180006515  mov     eax, [rax]
0x180006517  mov     [rcx], eax
0x180006519  mov     rcx, [rsp+98h+var_40]
0x18000651e  xor     rcx, rsp; StackCookie
0x180006521  call    __security_check_cookie
0x180006526  add     rsp, 68h
0x18000652a  pop     r15
0x18000652c  pop     r14
0x18000652e  pop     rdi
0x18000652f  pop     rsi
0x180006530  pop     rbp
0x180006531  pop     rbx
0x180006532  retn
```
