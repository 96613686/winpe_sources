# LocationRedirection::BackgroundThreadFunction(void *)

- ea: `0x1400603d0`
- end: `0x14006076b`
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
- `0x1400603d0`
- `0x140060774`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x140060748`
- `USER32!DispatchMessageW` at `0x140060748`
- `USER32!GetMessageW` at `0x14006075b`
- `USER32!GetMessageW` at `0x14006075b`
- `ole32!CoCreateInstance` at `0x14006046b`
- `ole32!CoCreateInstance` at `0x14006046b`

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
0x1400603d0  mov     [rsp+arg_8], rbx
0x1400603d5  mov     [rsp+arg_10], rbp
0x1400603da  push    rsi
0x1400603db  push    rdi
0x1400603dc  push    r14
0x1400603de  sub     rsp, 80h
0x1400603e5  mov     rax, cs:__security_cookie
0x1400603ec  xor     rax, rsp
0x1400603ef  mov     [rsp+98h+var_28], rax
0x1400603f4  mov     rdi, rcx
0x1400603f7  test    rcx, rcx
0x1400603fa  jnz     short loc_14006044E
0x1400603fc  mov     rax, cs:WPP_GLOBAL_Control
0x140060403  lea     rbx, WPP_GLOBAL_Control
0x14006040a  cmp     rax, rbx
0x14006040d  jz      loc_1400606FA
0x140060413  test    byte ptr [rax+1Ch], 1
0x140060417  jz      loc_1400606FA
0x14006041d  cmp     byte ptr [rax+19h], 2
0x140060421  jb      loc_1400606FA
0x140060427  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006042c  mov     rcx, cs:WPP_GLOBAL_Control
0x140060433  lea     edx, [rdi+0Ah]
0x140060436  mov     r9d, eax
0x140060439  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x140060440  mov     rcx, [rcx+10h]
0x140060444  call    WPP_SF_d
0x140060449  jmp     loc_1400606FA
0x14006044e  lea     rsi, [rcx+8]
0x140060452  xor     edx, edx; pUnkOuter
0x140060454  lea     r9, _GUID_ab2ece69_56d9_4f28_b525_de1b0ee44237; riid
0x14006045b  mov     [rsp+98h+ppv], rsi; ppv
0x140060460  lea     rcx, CLSID_Location; rclsid
0x140060467  lea     r8d, [rdx+17h]; dwClsContext
0x14006046b  call    cs:__imp_CoCreateInstance
0x140060471  mov     ebp, eax
0x140060473  test    eax, eax
0x140060475  jns     short loc_1400604CF
0x140060477  mov     rcx, cs:WPP_GLOBAL_Control
0x14006047e  lea     rbx, WPP_GLOBAL_Control
0x140060485  cmp     rcx, rbx
0x140060488  jz      loc_1400606F3
0x14006048e  test    byte ptr [rcx+1Ch], 1
0x140060492  jz      loc_1400606F3
0x140060498  cmp     byte ptr [rcx+19h], 2
0x14006049c  jb      loc_1400606F3
0x1400604a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400604a7  mov     edx, 0Bh
0x1400604ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400604b3  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x1400604ba  mov     r9d, eax
0x1400604bd  mov     dword ptr [rsp+98h+ppv], ebp
0x1400604c1  mov     rcx, [rcx+10h]
0x1400604c5  call    WPP_SF_Dd
0x1400604ca  jmp     loc_1400606F3
0x1400604cf  movups  xmm0, xmmword ptr cs:IID_ILatLongReport.Data1
0x1400604d6  mov     rcx, [rsi]
0x1400604d9  lea     r8, [rsp+98h+var_38]
0x1400604de  mov     r9d, 1
0x1400604e4  mov     dword ptr [rsp+98h+ppv], 0
0x1400604ec  movdqu  [rsp+98h+var_38], xmm0
0x1400604f2  xor     edx, edx
0x1400604f4  mov     rax, [rcx]
0x1400604f7  mov     rax, [rax+58h]
0x1400604fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060500  mov     ebp, eax
0x140060502  test    eax, eax
0x140060504  jns     short loc_140060540
0x140060506  mov     rcx, cs:WPP_GLOBAL_Control
0x14006050d  lea     rbx, WPP_GLOBAL_Control
0x140060514  cmp     rcx, rbx
0x140060517  jz      loc_1400606F3
0x14006051d  test    byte ptr [rcx+1Ch], 1
0x140060521  jz      loc_1400606F3
0x140060527  cmp     byte ptr [rcx+19h], 2
0x14006052b  jb      loc_1400606F3
0x140060531  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060536  mov     edx, 0Ch
0x14006053b  jmp     loc_1400604AC
0x140060540  lea     r14, [rdi+10h]
0x140060544  mov     rcx, r14
0x140060547  call    ?CreateInstance@?$CComObject@VCLocationListener@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CLocationListener>::CreateInstance(ATL::CComObject<CLocationListener> * *)
0x14006054c  mov     ebp, eax
0x14006054e  test    eax, eax
0x140060550  jns     short loc_14006058C
0x140060552  mov     rcx, cs:WPP_GLOBAL_Control
0x140060559  lea     rbx, WPP_GLOBAL_Control
0x140060560  cmp     rcx, rbx
0x140060563  jz      loc_1400606F3
0x140060569  test    byte ptr [rcx+1Ch], 1
0x14006056d  jz      loc_1400606F3
0x140060573  cmp     byte ptr [rcx+19h], 2
0x140060577  jb      loc_1400606F3
0x14006057d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060582  mov     edx, 0Dh
0x140060587  jmp     loc_1400604AC
0x14006058c  mov     rcx, [r14]
0x14006058f  mov     rax, [rcx]
0x140060592  mov     rax, [rax+8]
0x140060596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006059b  mov     rcx, [r14]
0x14006059e  lea     r8, IID_ILatLongReport
0x1400605a5  mov     rax, [rdi+18h]
0x1400605a9  mov     r9d, 3A98h
0x1400605af  mov     [rcx+10h], rax
0x1400605b3  mov     rcx, [rsi]
0x1400605b6  mov     rdx, [r14]
0x1400605b9  mov     rax, [rcx]
0x1400605bc  mov     rax, [rax+18h]
0x1400605c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400605c5  mov     ebp, eax
0x1400605c7  test    eax, eax
0x1400605c9  jns     short loc_140060605
0x1400605cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400605d2  lea     rbx, WPP_GLOBAL_Control
0x1400605d9  cmp     rcx, rbx
0x1400605dc  jz      loc_1400606F3
0x1400605e2  test    byte ptr [rcx+1Ch], 1
0x1400605e6  jz      loc_1400606F3
0x1400605ec  cmp     byte ptr [rcx+19h], 2
0x1400605f0  jb      loc_1400606F3
0x1400605f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400605fb  mov     edx, 0Eh
0x140060600  jmp     loc_1400604AC
0x140060605  mov     rax, cs:WPP_GLOBAL_Control
0x14006060c  lea     rbx, WPP_GLOBAL_Control
0x140060613  cmp     rax, rbx
0x140060616  jz      short loc_140060648
0x140060618  test    byte ptr [rax+1Ch], 1
0x14006061c  jz      short loc_140060648
0x14006061e  cmp     byte ptr [rax+19h], 4
0x140060622  jb      short loc_140060648
0x140060624  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140060629  mov     rcx, cs:WPP_GLOBAL_Control
0x140060630  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x140060637  mov     edx, 0Fh
0x14006063c  mov     r9d, eax
0x14006063f  mov     rcx, [rcx+10h]
0x140060643  call    WPP_SF_d
0x140060648  xorps   xmm0, xmm0
0x14006064b  mov     byte ptr [rdi], 1
0x14006064e  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x140060653  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x140060658  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x14006065d  jmp     loc_14006074E
0x140060662  mov     eax, [rsp+98h+Msg.message]
0x140060666  sub     eax, 8001h
0x14006066b  jz      loc_140060729
0x140060671  sub     eax, 1
0x140060674  jz      loc_140060721
0x14006067a  cmp     eax, 1
0x14006067d  jnz     loc_140060743
0x140060683  cmp     byte ptr [rdi], 0
0x140060686  jz      short loc_1400606F3
0x140060688  mov     rcx, [rsi]
0x14006068b  lea     rdx, IID_ILatLongReport
0x140060692  mov     rax, [rcx]
0x140060695  mov     rax, [rax+20h]
0x140060699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006069e  mov     rcx, [r14]
0x1400606a1  mov     rax, [rcx]
0x1400606a4  mov     rax, [rax+10h]
0x1400606a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400606ad  mov     qword ptr [r14], 0
0x1400606b4  mov     rax, cs:WPP_GLOBAL_Control
0x1400606bb  cmp     rax, rbx
0x1400606be  jz      short loc_1400606F0
0x1400606c0  test    byte ptr [rax+1Ch], 1
0x1400606c4  jz      short loc_1400606F0
0x1400606c6  cmp     byte ptr [rax+19h], 4
0x1400606ca  jb      short loc_1400606F0
0x1400606cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400606d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400606d8  lea     r8, WPP_215a92eace303b4bf5320de9af5768e3_Traceguids
0x1400606df  mov     edx, 10h
0x1400606e4  mov     r9d, eax
0x1400606e7  mov     rcx, [rcx+10h]
0x1400606eb  call    WPP_SF_d
0x1400606f0  mov     byte ptr [rdi], 0
0x1400606f3  mov     dword ptr [rdi+28h], 0
0x1400606fa  xor     eax, eax
0x1400606fc  mov     rcx, [rsp+98h+var_28]
0x140060701  xor     rcx, rsp; StackCookie
0x140060704  call    __security_check_cookie
0x140060709  lea     r11, [rsp+98h+var_18]
0x140060711  mov     rbx, [r11+28h]
0x140060715  mov     rbp, [r11+30h]
0x140060719  mov     rsp, r11
0x14006071c  pop     r14
0x14006071e  pop     rdi
0x14006071f  pop     rsi
0x140060720  retn
0x140060721  mov     r8d, 3A98h
0x140060727  jmp     short loc_14006072D
0x140060729  mov     r8d, [rdi+4]
0x14006072d  mov     rcx, [rsi]
0x140060730  lea     rdx, IID_ILatLongReport
0x140060737  mov     rax, [rcx]
0x14006073a  mov     rax, [rax+40h]
0x14006073e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060743  lea     rcx, [rsp+98h+Msg]; lpMsg
0x140060748  call    cs:__imp_DispatchMessageW
0x14006074e  xor     r9d, r9d; wMsgFilterMax
0x140060751  lea     rcx, [rsp+98h+Msg]; lpMsg
0x140060756  xor     r8d, r8d; wMsgFilterMin
0x140060759  xor     edx, edx; hWnd
0x14006075b  call    cs:__imp_GetMessageW
0x140060761  test    eax, eax
0x140060763  jnz     loc_140060662
0x140060769  jmp     short loc_1400606F3
```
