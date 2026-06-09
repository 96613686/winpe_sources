# LocationRedirection::BackgroundThreadFunction(void *)

- ea: `0x14005e260`
- end: `0x14005e5fb`
- name: `?BackgroundThreadFunction@LocationRedirection@@CAKPEAX@Z`
- size: `923`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14005e260`
- `0x14005e604`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x14005e5d8`
- `USER32!DispatchMessageW` at `0x14005e5d8`
- `USER32!GetMessageW` at `0x14005e5eb`
- `USER32!GetMessageW` at `0x14005e5eb`
- `ole32!CoCreateInstance` at `0x14005e2fb`
- `ole32!CoCreateInstance` at `0x14005e2fb`

## pseudocode

```c
__int64 __fastcall LocationRedirection::BackgroundThreadFunction(LPVOID *Parameter)
{
  unsigned int v2; // eax
  _QWORD *v3; // rsi
  HRESULT Instance; // ebp
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v12; // r8
  MSG Msg; // [rsp+30h] [rbp-68h] BYREF
  GUID v14; // [rsp+60h] [rbp-38h] BYREF

  if ( Parameter )
  {
    v3 = Parameter + 1;
    Instance = CoCreateInstance(&CLSID_Location, 0, 0x17u, &GUID_ab2ece69_56d9_4f28_b525_de1b0ee44237, Parameter + 1);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 11;
LABEL_11:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        WPP_215a92eace303b4bf5320de9af5768e3_Traceguids,
        CurrentThreadActivityIdPrefix,
        Instance);
LABEL_41:
      *((_DWORD *)Parameter + 10) = 0;
      return 0;
    }
    v7 = *v3;
    v14 = IID_ILatLongReport;
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64, _DWORD))(*(_QWORD *)v7 + 88LL))(
                 v7,
                 0,
                 &v14,
                 1,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 12;
      goto LABEL_11;
    }
    v8 = Parameter + 2;
    Instance = ATL::CComObject<CLocationListener>::CreateInstance(Parameter + 2);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 13;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    *(_QWORD *)(*v8 + 16LL) = Parameter[3];
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64))(*(_QWORD *)*v3 + 24LL))(
                 *v3,
                 *v8,
                 &IID_ILatLongReport,
                 15000);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 14;
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids, v9);
    }
    *(_BYTE *)Parameter = 1;
    memset(&Msg, 0, sizeof(Msg));
    while ( 1 )
    {
      if ( !GetMessageW(&Msg, 0, 0, 0) )
        goto LABEL_41;
      if ( Msg.message == 32769 )
        break;
      if ( Msg.message == 32770 )
      {
        v12 = 15000;
LABEL_45:
        (*(void (__fastcall **)(_QWORD, GUID *, __int64))(*(_QWORD *)*v3 + 64LL))(*v3, &IID_ILatLongReport, v12);
        goto LABEL_46;
      }
      if ( Msg.message == 32771 )
      {
        if ( *(_BYTE *)Parameter )
        {
          (*(void (__fastcall **)(_QWORD, GUID *))(*(_QWORD *)*v3 + 32LL))(*v3, &IID_ILatLongReport);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
          *v8 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v10 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids, v10);
          }
          *(_BYTE *)Parameter = 0;
        }
        goto LABEL_41;
      }
LABEL_46:
      DispatchMessageW(&Msg);
    }
    v12 = *((unsigned int *)Parameter + 1);
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v2 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14005e260  mov     [rsp+arg_8], rbx
0x14005e265  mov     [rsp+arg_10], rbp
0x14005e26a  push    rsi
0x14005e26b  push    rdi
0x14005e26c  push    r14
0x14005e26e  sub     rsp, 80h
0x14005e275  mov     rax, cs:__security_cookie
0x14005e27c  xor     rax, rsp
0x14005e27f  mov     [rsp+98h+var_28], rax
0x14005e284  mov     rdi, rcx
0x14005e287  test    rcx, rcx
0x14005e28a  jnz     short loc_14005E2DE
0x14005e28c  mov     rax, cs:WPP_GLOBAL_Control
0x14005e293  lea     rbx, WPP_GLOBAL_Control
0x14005e29a  cmp     rax, rbx
0x14005e29d  jz      loc_14005E58A
0x14005e2a3  test    byte ptr [rax+1Ch], 1
0x14005e2a7  jz      loc_14005E58A
0x14005e2ad  cmp     byte ptr [rax+19h], 2
0x14005e2b1  jb      loc_14005E58A
0x14005e2b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e2c3  lea     edx, [rdi+0Ah]
0x14005e2c6  mov     r9d, eax
0x14005e2c9  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x14005e2d0  mov     rcx, [rcx+10h]
0x14005e2d4  call    WPP_SF_d
0x14005e2d9  jmp     loc_14005E58A
0x14005e2de  lea     rsi, [rcx+8]
0x14005e2e2  xor     edx, edx; pUnkOuter
0x14005e2e4  lea     r9, _GUID_ab2ece69_56d9_4f28_b525_de1b0ee44237; riid
0x14005e2eb  mov     [rsp+98h+ppv], rsi; ppv
0x14005e2f0  lea     rcx, CLSID_Location; rclsid
0x14005e2f7  lea     r8d, [rdx+17h]; dwClsContext
0x14005e2fb  call    cs:__imp_CoCreateInstance
0x14005e301  mov     ebp, eax
0x14005e303  test    eax, eax
0x14005e305  jns     short loc_14005E35F
0x14005e307  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e30e  lea     rbx, WPP_GLOBAL_Control
0x14005e315  cmp     rcx, rbx
0x14005e318  jz      loc_14005E583
0x14005e31e  test    byte ptr [rcx+1Ch], 1
0x14005e322  jz      loc_14005E583
0x14005e328  cmp     byte ptr [rcx+19h], 2
0x14005e32c  jb      loc_14005E583
0x14005e332  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e337  mov     edx, 0Bh
0x14005e33c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e343  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x14005e34a  mov     r9d, eax
0x14005e34d  mov     dword ptr [rsp+98h+ppv], ebp
0x14005e351  mov     rcx, [rcx+10h]
0x14005e355  call    WPP_SF_Dd
0x14005e35a  jmp     loc_14005E583
0x14005e35f  movups  xmm0, xmmword ptr cs:IID_ILatLongReport.Data1
0x14005e366  mov     rcx, [rsi]
0x14005e369  lea     r8, [rsp+98h+var_38]
0x14005e36e  mov     r9d, 1
0x14005e374  mov     dword ptr [rsp+98h+ppv], 0
0x14005e37c  movdqu  [rsp+98h+var_38], xmm0
0x14005e382  xor     edx, edx
0x14005e384  mov     rax, [rcx]
0x14005e387  mov     rax, [rax+58h]
0x14005e38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e390  mov     ebp, eax
0x14005e392  test    eax, eax
0x14005e394  jns     short loc_14005E3D0
0x14005e396  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e39d  lea     rbx, WPP_GLOBAL_Control
0x14005e3a4  cmp     rcx, rbx
0x14005e3a7  jz      loc_14005E583
0x14005e3ad  test    byte ptr [rcx+1Ch], 1
0x14005e3b1  jz      loc_14005E583
0x14005e3b7  cmp     byte ptr [rcx+19h], 2
0x14005e3bb  jb      loc_14005E583
0x14005e3c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e3c6  mov     edx, 0Ch
0x14005e3cb  jmp     loc_14005E33C
0x14005e3d0  lea     r14, [rdi+10h]
0x14005e3d4  mov     rcx, r14
0x14005e3d7  call    ?CreateInstance@?$CComObject@VCLocationListener@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CLocationListener>::CreateInstance(ATL::CComObject<CLocationListener> * *)
0x14005e3dc  mov     ebp, eax
0x14005e3de  test    eax, eax
0x14005e3e0  jns     short loc_14005E41C
0x14005e3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e3e9  lea     rbx, WPP_GLOBAL_Control
0x14005e3f0  cmp     rcx, rbx
0x14005e3f3  jz      loc_14005E583
0x14005e3f9  test    byte ptr [rcx+1Ch], 1
0x14005e3fd  jz      loc_14005E583
0x14005e403  cmp     byte ptr [rcx+19h], 2
0x14005e407  jb      loc_14005E583
0x14005e40d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e412  mov     edx, 0Dh
0x14005e417  jmp     loc_14005E33C
0x14005e41c  mov     rcx, [r14]
0x14005e41f  mov     rax, [rcx]
0x14005e422  mov     rax, [rax+8]
0x14005e426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e42b  mov     rcx, [r14]
0x14005e42e  lea     r8, IID_ILatLongReport
0x14005e435  mov     rax, [rdi+18h]
0x14005e439  mov     r9d, 3A98h
0x14005e43f  mov     [rcx+10h], rax
0x14005e443  mov     rcx, [rsi]
0x14005e446  mov     rdx, [r14]
0x14005e449  mov     rax, [rcx]
0x14005e44c  mov     rax, [rax+18h]
0x14005e450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e455  mov     ebp, eax
0x14005e457  test    eax, eax
0x14005e459  jns     short loc_14005E495
0x14005e45b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e462  lea     rbx, WPP_GLOBAL_Control
0x14005e469  cmp     rcx, rbx
0x14005e46c  jz      loc_14005E583
0x14005e472  test    byte ptr [rcx+1Ch], 1
0x14005e476  jz      loc_14005E583
0x14005e47c  cmp     byte ptr [rcx+19h], 2
0x14005e480  jb      loc_14005E583
0x14005e486  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e48b  mov     edx, 0Eh
0x14005e490  jmp     loc_14005E33C
0x14005e495  mov     rax, cs:WPP_GLOBAL_Control
0x14005e49c  lea     rbx, WPP_GLOBAL_Control
0x14005e4a3  cmp     rax, rbx
0x14005e4a6  jz      short loc_14005E4D8
0x14005e4a8  test    byte ptr [rax+1Ch], 1
0x14005e4ac  jz      short loc_14005E4D8
0x14005e4ae  cmp     byte ptr [rax+19h], 4
0x14005e4b2  jb      short loc_14005E4D8
0x14005e4b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e4c0  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x14005e4c7  mov     edx, 0Fh
0x14005e4cc  mov     r9d, eax
0x14005e4cf  mov     rcx, [rcx+10h]
0x14005e4d3  call    WPP_SF_d
0x14005e4d8  xorps   xmm0, xmm0
0x14005e4db  mov     byte ptr [rdi], 1
0x14005e4de  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x14005e4e3  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x14005e4e8  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x14005e4ed  jmp     loc_14005E5DE
0x14005e4f2  mov     eax, [rsp+98h+Msg.message]
0x14005e4f6  sub     eax, 8001h
0x14005e4fb  jz      loc_14005E5B9
0x14005e501  sub     eax, 1
0x14005e504  jz      loc_14005E5B1
0x14005e50a  cmp     eax, 1
0x14005e50d  jnz     loc_14005E5D3
0x14005e513  cmp     byte ptr [rdi], 0
0x14005e516  jz      short loc_14005E583
0x14005e518  mov     rcx, [rsi]
0x14005e51b  lea     rdx, IID_ILatLongReport
0x14005e522  mov     rax, [rcx]
0x14005e525  mov     rax, [rax+20h]
0x14005e529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e52e  mov     rcx, [r14]
0x14005e531  mov     rax, [rcx]
0x14005e534  mov     rax, [rax+10h]
0x14005e538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e53d  mov     qword ptr [r14], 0
0x14005e544  mov     rax, cs:WPP_GLOBAL_Control
0x14005e54b  cmp     rax, rbx
0x14005e54e  jz      short loc_14005E580
0x14005e550  test    byte ptr [rax+1Ch], 1
0x14005e554  jz      short loc_14005E580
0x14005e556  cmp     byte ptr [rax+19h], 4
0x14005e55a  jb      short loc_14005E580
0x14005e55c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e561  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e568  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x14005e56f  mov     edx, 10h
0x14005e574  mov     r9d, eax
0x14005e577  mov     rcx, [rcx+10h]
0x14005e57b  call    WPP_SF_d
0x14005e580  mov     byte ptr [rdi], 0
0x14005e583  mov     dword ptr [rdi+28h], 0
0x14005e58a  xor     eax, eax
0x14005e58c  mov     rcx, [rsp+98h+var_28]
0x14005e591  xor     rcx, rsp; StackCookie
0x14005e594  call    __security_check_cookie
0x14005e599  lea     r11, [rsp+98h+var_18]
0x14005e5a1  mov     rbx, [r11+28h]
0x14005e5a5  mov     rbp, [r11+30h]
0x14005e5a9  mov     rsp, r11
0x14005e5ac  pop     r14
0x14005e5ae  pop     rdi
0x14005e5af  pop     rsi
0x14005e5b0  retn
0x14005e5b1  mov     r8d, 3A98h
0x14005e5b7  jmp     short loc_14005E5BD
0x14005e5b9  mov     r8d, [rdi+4]
0x14005e5bd  mov     rcx, [rsi]
0x14005e5c0  lea     rdx, IID_ILatLongReport
0x14005e5c7  mov     rax, [rcx]
0x14005e5ca  mov     rax, [rax+40h]
0x14005e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e5d3  lea     rcx, [rsp+98h+Msg]; lpMsg
0x14005e5d8  call    cs:__imp_DispatchMessageW
0x14005e5de  xor     r9d, r9d; wMsgFilterMax
0x14005e5e1  lea     rcx, [rsp+98h+Msg]; lpMsg
0x14005e5e6  xor     r8d, r8d; wMsgFilterMin
0x14005e5e9  xor     edx, edx; hWnd
0x14005e5eb  call    cs:__imp_GetMessageW
0x14005e5f1  test    eax, eax
0x14005e5f3  jnz     loc_14005E4F2
0x14005e5f9  jmp     short loc_14005E583
```
