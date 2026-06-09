# CTouchHandleAnimationController::InitAnimationComponents(void)

- ea: `0x1802041cc`
- end: `0x18020432a`
- name: `?InitAnimationComponents@CTouchHandleAnimationController@@QEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(CTouchHandleAnimationController *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18020146c`

## callees

- `0x1802041cc`
- `0x18027f010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1802041e2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x1802041e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180204217`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020424a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020427d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180204217`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020424a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18020427d`

## pseudocode

```c
__int64 __fastcall CTouchHandleAnimationController::InitAnimationComponents(CTouchHandleAnimationController *this)
{
  HRESULT Instance; // ebx
  _QWORD *v3; // rsi
  _QWORD *v4; // r14
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF

  Instance = 0;
  v3 = (_QWORD *)((char *)this + 16);
  *((_DWORD *)this + 16) = RegisterWindowMessageW(L"RichEdit_TouchSelectionHandle_Animation");
  if ( !*v3 )
  {
    Instance = CoCreateInstance(
                 &CLSID_UIAnimationManager2,
                 0,
                 1u,
                 &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1,
                 (LPVOID *)this + 2);
    if ( Instance >= 0 )
    {
      v4 = (_QWORD *)((char *)this + 24);
      Instance = CoCreateInstance(
                   &CLSID_UIAnimationTimer,
                   0,
                   1u,
                   &GUID_6b0efad1_a053_41d6_9085_33a689144665,
                   (LPVOID *)this + 3);
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_UIAnimationTransitionLibrary2,
                     0,
                     1u,
                     &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a,
                     (LPVOID *)this + 4);
        if ( Instance >= 0 )
        {
          v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v3;
          v7 = 0;
          Instance = (**v5)(v5, &IID_IUIAnimationTimerUpdateHandler, &v7);
          if ( Instance >= 0 )
          {
            if ( !v7
              || (Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v4 + 24LL))(*v4, v7, 1),
                  Instance >= 0) )
            {
              Instance = (*(__int64 (__fastcall **)(_QWORD, CTouchHandleAnimationController *))(*(_QWORD *)*v4 + 32LL))(
                           *v4,
                           this);
              if ( Instance >= 0 )
                return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(*(_QWORD *)*v3 + 136LL))(
                                       *v3,
                                       ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                                       0);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1802041cc  push    rbx
0x1802041ce  push    rsi
0x1802041cf  push    rdi
0x1802041d0  push    r14
0x1802041d2  sub     rsp, 38h
0x1802041d6  mov     rdi, rcx
0x1802041d9  xor     ebx, ebx
0x1802041db  lea     rcx, aRicheditTouchs; "RichEdit_TouchSelectionHandle_Animation"
0x1802041e2  call    cs:__imp_RegisterWindowMessageW
0x1802041e9  nop     dword ptr [rax+rax+00h]
0x1802041ee  lea     rsi, [rdi+10h]
0x1802041f2  mov     [rdi+40h], eax
0x1802041f5  cmp     [rsi], rbx
0x1802041f8  jnz     loc_18020431D
0x1802041fe  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x180204205  mov     [rsp+58h+ppv], rsi; ppv
0x18020420a  xor     edx, edx; pUnkOuter
0x18020420c  lea     r8d, [rbx+1]; dwClsContext
0x180204210  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x180204217  call    cs:__imp_CoCreateInstance
0x18020421e  nop     dword ptr [rax+rax+00h]
0x180204223  mov     ebx, eax
0x180204225  test    eax, eax
0x180204227  js      loc_18020431D
0x18020422d  xor     edx, edx; pUnkOuter
0x18020422f  lea     r14, [rdi+18h]
0x180204233  lea     r9, _GUID_6b0efad1_a053_41d6_9085_33a689144665; riid
0x18020423a  mov     [rsp+58h+ppv], r14; ppv
0x18020423f  lea     rcx, CLSID_UIAnimationTimer; rclsid
0x180204246  lea     r8d, [rdx+1]; dwClsContext
0x18020424a  call    cs:__imp_CoCreateInstance
0x180204251  nop     dword ptr [rax+rax+00h]
0x180204256  mov     ebx, eax
0x180204258  test    eax, eax
0x18020425a  js      loc_18020431D
0x180204260  xor     edx, edx; pUnkOuter
0x180204262  lea     rax, [rdi+20h]
0x180204266  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x18020426d  mov     [rsp+58h+ppv], rax; ppv
0x180204272  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x180204279  lea     r8d, [rdx+1]; dwClsContext
0x18020427d  call    cs:__imp_CoCreateInstance
0x180204284  nop     dword ptr [rax+rax+00h]
0x180204289  mov     ebx, eax
0x18020428b  test    eax, eax
0x18020428d  js      loc_18020431D
0x180204293  mov     rcx, [rsi]
0x180204296  lea     r8, [rsp+58h+arg_0]
0x18020429b  mov     [rsp+58h+arg_0], 0
0x1802042a4  lea     rdx, IID_IUIAnimationTimerUpdateHandler
0x1802042ab  mov     rax, [rcx]
0x1802042ae  mov     rax, [rax]
0x1802042b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802042b6  mov     ebx, eax
0x1802042b8  test    eax, eax
0x1802042ba  js      short loc_18020431D
0x1802042bc  mov     rdx, [rsp+58h+arg_0]
0x1802042c1  test    rdx, rdx
0x1802042c4  jz      short loc_1802042E1
0x1802042c6  mov     rcx, [r14]
0x1802042c9  mov     r8d, 1
0x1802042cf  mov     rax, [rcx]
0x1802042d2  mov     rax, [rax+18h]
0x1802042d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802042db  mov     ebx, eax
0x1802042dd  test    eax, eax
0x1802042df  js      short loc_18020431D
0x1802042e1  mov     rcx, [r14]
0x1802042e4  mov     rdx, rdi
0x1802042e7  mov     rax, [rcx]
0x1802042ea  mov     rax, [rax+20h]
0x1802042ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802042f3  mov     ebx, eax
0x1802042f5  test    eax, eax
0x1802042f7  js      short loc_18020431D
0x1802042f9  mov     rcx, [rsi]
0x1802042fc  lea     rax, [rdi+8]
0x180204300  neg     rdi
0x180204303  sbb     rdx, rdx
0x180204306  xor     r8d, r8d
0x180204309  mov     r9, [rcx]
0x18020430c  and     rdx, rax
0x18020430f  mov     rax, [r9+88h]
0x180204316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020431b  mov     ebx, eax
0x18020431d  mov     eax, ebx
0x18020431f  add     rsp, 38h
0x180204323  pop     r14
0x180204325  pop     rdi
0x180204326  pop     rsi
0x180204327  pop     rbx
0x180204328  retn
```
