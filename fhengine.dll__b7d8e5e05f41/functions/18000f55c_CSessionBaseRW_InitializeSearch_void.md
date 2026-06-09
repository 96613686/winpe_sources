# CSessionBaseRW::InitializeSearch(void)

- ea: `0x18000f55c`
- end: `0x18000f722`
- name: `?InitializeSearch@CSessionBaseRW@@IEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f728`
- `0x18000fc88`

## callees

- `0x180007818`
- `0x18000f55c`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f5be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f666`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f5be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f666`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::InitializeSearch(LPVOID *this)
{
  HRESULT Instance; // ebx
  char *v3; // rbp
  __int64 *v4; // rsi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rsi
  LPVOID *ppv; // rdi
  int v11; // [rsp+40h] [rbp-58h] BYREF
  __int128 v12; // [rsp+48h] [rbp-50h] BYREF
  __int128 v13; // [rsp+58h] [rbp-40h] BYREF

  Instance = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  v3 = (char *)(this + 32);
  if ( !this[32] )
  {
    v4 = (__int64 *)(this + 29);
    Instance = CoCreateInstance(
                 &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
                 0,
                 0x15u,
                 &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
                 this + 29);
    if ( Instance >= 0 )
    {
      v7 = *v4;
      v8 = this + 30;
      Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v7 + 80LL))(
                   v7,
                   L"SystemIndex",
                   (char *)this + 240);
      if ( Instance >= 0 )
      {
        ppv = this + 31;
        Instance = CoCreateInstance(
                     &GUID_a7aa4814_7479_4047_bc99_32e757c8b850,
                     0,
                     0x17u,
                     &GUID_b5702e61_e75c_4b64_82a1_6cb4f832fccf,
                     ppv);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, LPVOID, GUID *, char *, __int128 *, __int128 *, int *))(*(_QWORD *)*v8 + 168LL))(
                       *v8,
                       *ppv,
                       &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef58,
                       v3,
                       &v13,
                       &v12,
                       &v11);
          if ( Instance < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 176;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 175;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 174;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 173;
LABEL_18:
        WPP_SF_d(v5[2], v6, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, (unsigned int)Instance);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000f55c  push    rbx
0x18000f55e  push    rbp
0x18000f55f  push    rsi
0x18000f560  push    rdi
0x18000f561  sub     rsp, 78h
0x18000f565  mov     rax, cs:__security_cookie
0x18000f56c  xor     rax, rsp
0x18000f56f  mov     [rsp+98h+var_30], rax
0x18000f574  mov     rdi, rcx
0x18000f577  xor     ebx, ebx
0x18000f579  xorps   xmm0, xmm0
0x18000f57c  movups  [rsp+98h+var_40], xmm0
0x18000f581  xorps   xmm1, xmm1
0x18000f584  movups  [rsp+98h+var_50], xmm1
0x18000f589  mov     [rsp+98h+var_58], ebx
0x18000f58d  lea     rbp, [rcx+100h]
0x18000f594  cmp     [rbp+0], rbx
0x18000f598  jnz     loc_18000F70A
0x18000f59e  lea     rsi, [rcx+0E8h]
0x18000f5a5  mov     [rsp+98h+ppv], rsi; ppv
0x18000f5aa  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18000f5b1  xor     edx, edx; pUnkOuter
0x18000f5b3  lea     r8d, [rbx+15h]; dwClsContext
0x18000f5b7  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18000f5be  call    cs:__imp_CoCreateInstance
0x18000f5c4  mov     ebx, eax
0x18000f5c6  test    eax, eax
0x18000f5c8  jns     short loc_18000F5F5
0x18000f5ca  lea     rax, WPP_GLOBAL_Control
0x18000f5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5d8  cmp     rcx, rax
0x18000f5db  jz      loc_18000F70A
0x18000f5e1  test    byte ptr [rcx+1Ch], 1
0x18000f5e5  jz      loc_18000F70A
0x18000f5eb  mov     edx, 0ADh
0x18000f5f0  jmp     loc_18000F6F7
0x18000f5f5  mov     rcx, [rsi]
0x18000f5f8  lea     rsi, [rdi+0F0h]
0x18000f5ff  mov     rax, [rcx]
0x18000f602  mov     r8, rsi
0x18000f605  lea     rdx, aSystemindex; "SystemIndex"
0x18000f60c  mov     rax, [rax+50h]
0x18000f610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f615  mov     ebx, eax
0x18000f617  test    eax, eax
0x18000f619  jns     short loc_18000F646
0x18000f61b  lea     rax, WPP_GLOBAL_Control
0x18000f622  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f629  cmp     rcx, rax
0x18000f62c  jz      loc_18000F70A
0x18000f632  test    byte ptr [rcx+1Ch], 1
0x18000f636  jz      loc_18000F70A
0x18000f63c  mov     edx, 0AEh
0x18000f641  jmp     loc_18000F6F7
0x18000f646  add     rdi, 0F8h
0x18000f64d  mov     [rsp+98h+ppv], rdi; ppv
0x18000f652  lea     r9, _GUID_b5702e61_e75c_4b64_82a1_6cb4f832fccf; riid
0x18000f659  xor     edx, edx; pUnkOuter
0x18000f65b  lea     r8d, [rdx+17h]; dwClsContext
0x18000f65f  lea     rcx, _GUID_a7aa4814_7479_4047_bc99_32e757c8b850; rclsid
0x18000f666  call    cs:__imp_CoCreateInstance
0x18000f66c  mov     ebx, eax
0x18000f66e  test    eax, eax
0x18000f670  jns     short loc_18000F696
0x18000f672  lea     rax, WPP_GLOBAL_Control
0x18000f679  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f680  cmp     rcx, rax
0x18000f683  jz      loc_18000F70A
0x18000f689  test    byte ptr [rcx+1Ch], 1
0x18000f68d  jz      short loc_18000F70A
0x18000f68f  mov     edx, 0AFh
0x18000f694  jmp     short loc_18000F6F7
0x18000f696  mov     rcx, [rsi]
0x18000f699  mov     rax, [rcx]
0x18000f69c  lea     rdx, [rsp+98h+var_58]
0x18000f6a1  mov     [rsp+98h+var_68], rdx
0x18000f6a6  lea     rdx, [rsp+98h+var_50]
0x18000f6ab  mov     [rsp+98h+var_70], rdx
0x18000f6b0  lea     rdx, [rsp+98h+var_40]
0x18000f6b5  mov     [rsp+98h+ppv], rdx
0x18000f6ba  mov     r9, rbp
0x18000f6bd  lea     r8, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef58
0x18000f6c4  mov     rdx, [rdi]
0x18000f6c7  mov     rax, [rax+0A8h]
0x18000f6ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d3  mov     ebx, eax
0x18000f6d5  test    eax, eax
0x18000f6d7  jns     short loc_18000F70A
0x18000f6d9  lea     rax, WPP_GLOBAL_Control
0x18000f6e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6e7  cmp     rcx, rax
0x18000f6ea  jz      short loc_18000F70A
0x18000f6ec  test    byte ptr [rcx+1Ch], 1
0x18000f6f0  jz      short loc_18000F70A
0x18000f6f2  mov     edx, 0B0h
0x18000f6f7  mov     r9d, ebx
0x18000f6fa  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000f701  mov     rcx, [rcx+10h]
0x18000f705  call    WPP_SF_d
0x18000f70a  mov     eax, ebx
0x18000f70c  mov     rcx, [rsp+98h+var_30]
0x18000f711  xor     rcx, rsp; StackCookie
0x18000f714  call    __security_check_cookie
0x18000f719  add     rsp, 78h
0x18000f71d  pop     rdi
0x18000f71e  pop     rsi
0x18000f71f  pop     rbp
0x18000f720  pop     rbx
0x18000f721  retn
```
