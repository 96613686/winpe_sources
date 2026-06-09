# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SetupAdvertisementFilter(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)

- ea: `0x180030650`
- end: `0x180030927`
- name: `?SetupAdvertisementFilter@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18002cfcc`

## callees

- `0x1800120b8`
- `0x180012384`
- `0x18002c9b8`
- `0x18002ddec`
- `0x180030650`
- `0x180030c38`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003089c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003089c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SetupAdvertisementFilter(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this,
        __int64 *a2,
        __int64 a3)
{
  __int64 *v3; // rbx
  char v5; // si
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  int v10; // edx
  int v11; // r8d
  int v12; // ebx
  _BYTE *v13; // rcx
  int v14; // eax
  bool v15; // cf
  bool v16; // zf
  int v17; // eax
  bool v18; // cf
  _QWORD v20[12]; // [rsp+60h] [rbp-9h] BYREF
  int v21; // [rsp+D0h] [rbp+67h] BYREF
  int v22; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+E0h] [rbp+77h] BYREF
  char *v24; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = a2;
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = v3[1];
  if ( v6 )
    _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
  v7 = v3[1];
  v8 = *v3;
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  *(_QWORD *)this = v8;
  *((_QWORD *)this + 1) = v7;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64 *, __int64))v9)(v9, a2, a3);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  *((_DWORD *)this + 34) = 5023;
  v24 = (char *)this + 88;
  v23 = *((_QWORD *)this + 16);
  v22 = 45;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v20[0] = this;
  v20[1] = &v23;
  v20[2] = &v22;
  v20[3] = &v24;
  v20[4] = &v21;
  v21 = wil::ResultFromException__lambda_fe7b844e9001a84485ac6c4cb501e51d___(v20, a2, a3);
  v12 = v21;
  if ( v21 >= 0 )
    goto LABEL_29;
  v13 = WPP_GLOBAL_Control;
  LOBYTE(v10) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v12 = v21;
LABEL_29:
    v13 = WPP_GLOBAL_Control;
  }
  v14 = 0;
  if ( v12 )
    v15 = v13[25] < 2u;
  else
    v15 = v13[25] < 5u;
  LOBYTE(v10) = v13 != (_BYTE *)&WPP_GLOBAL_Control && (LOBYTE(v14) = !v15, v14);
  if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v13 + 2), v10, v11, *((_QWORD *)v13 + 5));
    v13 = WPP_GLOBAL_Control;
    v12 = v21;
  }
  v16 = v12 == 0;
  if ( v12 < 0 )
  {
    SetEvent(*((HANDLE *)this + 15));
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(this);
    v13 = WPP_GLOBAL_Control;
    v16 = v12 == 0;
  }
  v17 = 0;
  if ( v16 )
    v18 = v13[25] < 5u;
  else
    v18 = v13[25] < 2u;
  if ( v13 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v17) = !v18, !v17) )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = v5;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v13 + 2), v10, v11, *((_QWORD *)v13 + 5));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180030650  push    rbp
0x180030652  push    rbx
0x180030653  push    rsi
0x180030654  push    rdi
0x180030655  push    r12
0x180030657  push    r13
0x180030659  push    r14
0x18003065b  lea     rbp, [rsp-27h]
0x180030660  sub     rsp, 90h
0x180030667  mov     rbx, rdx
0x18003066a  mov     rdi, rcx
0x18003066d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030674  lea     r12, WPP_GLOBAL_Control
0x18003067b  mov     esi, 1
0x180030680  cmp     rcx, r12
0x180030683  jz      short loc_180030690
0x180030685  cmp     byte ptr [rcx+19h], 5
0x180030689  jb      short loc_180030690
0x18003068b  mov     dl, sil
0x18003068e  jmp     short loc_180030692
0x180030690  xor     dl, dl
0x180030692  lea     r13, WPP_RECORDER_INITIALIZED
0x180030699  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800306a0  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x1800306a7  setnz   r8b
0x1800306ab  test    dl, dl
0x1800306ad  jnz     short loc_1800306B4
0x1800306af  test    r8b, r8b
0x1800306b2  jz      short loc_1800306D2
0x1800306b4  mov     r9, [rcx+28h]
0x1800306b8  mov     rcx, [rcx+10h]
0x1800306bc  mov     [rsp+0C0h+var_78], rdi
0x1800306c1  mov     [rsp+0C0h+var_88], r14
0x1800306c6  mov     [rsp+0C0h+var_90], 13h
0x1800306cd  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800306d2  mov     rax, [rbx+8]
0x1800306d6  test    rax, rax
0x1800306d9  jz      short loc_1800306DF
0x1800306db  lock add [rax+8], esi
0x1800306df  mov     rcx, [rbx+8]
0x1800306e3  mov     rax, [rbx]
0x1800306e6  mov     rbx, [rdi+8]
0x1800306ea  mov     [rdi], rax
0x1800306ed  mov     [rdi+8], rcx
0x1800306f1  test    rbx, rbx
0x1800306f4  jz      short loc_180030738
0x1800306f6  or      r14d, 0FFFFFFFFh
0x1800306fa  mov     eax, r14d
0x1800306fd  lock xadd [rbx+8], eax
0x180030702  add     eax, r14d
0x180030705  jnz     short loc_180030731
0x180030707  mov     rax, [rbx]
0x18003070a  mov     rcx, rbx
0x18003070d  mov     rax, [rax]
0x180030710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030715  mov     eax, r14d
0x180030718  lock xadd [rbx+0Ch], eax
0x18003071d  add     eax, r14d
0x180030720  jnz     short loc_180030731
0x180030722  mov     rax, [rbx]
0x180030725  mov     rcx, rbx
0x180030728  mov     rax, [rax+8]
0x18003072c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030731  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030738  lea     rax, [rdi+58h]
0x18003073c  mov     dword ptr [rdi+88h], 139Fh
0x180030746  mov     [rbp+57h+arg_18], rax
0x18003074a  mov     rax, [rdi+80h]
0x180030751  mov     [rbp+57h+arg_10], rax
0x180030755  mov     [rbp+57h+arg_8], 2Dh ; '-'
0x18003075c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030763  cmp     rcx, r12
0x180030766  jz      short loc_180030773
0x180030768  cmp     byte ptr [rcx+19h], 5
0x18003076c  jb      short loc_180030773
0x18003076e  mov     dl, sil
0x180030771  jmp     short loc_180030775
0x180030773  xor     dl, dl
0x180030775  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003077c  setnz   r8b
0x180030780  test    dl, dl
0x180030782  jnz     short loc_180030789
0x180030784  test    r8b, r8b
0x180030787  jz      short loc_1800307A7
0x180030789  mov     r9, [rcx+28h]
0x18003078d  mov     rcx, [rcx+10h]
0x180030791  mov     [rsp+0C0h+var_78], rdi
0x180030796  mov     [rsp+0C0h+var_88], r14
0x18003079b  mov     [rsp+0C0h+var_90], 17h
0x1800307a2  call    WPP_RECORDER_AND_TRACE_SF_si
0x1800307a7  lea     rax, [rbp+57h+arg_10]
0x1800307ab  mov     [rbp+57h+var_60], rdi
0x1800307af  mov     [rbp+57h+var_58], rax
0x1800307b3  lea     rcx, [rbp+57h+var_60]
0x1800307b7  lea     rax, [rbp+57h+arg_8]
0x1800307bb  mov     [rbp+57h+var_50], rax
0x1800307bf  lea     rax, [rbp+57h+arg_18]
0x1800307c3  mov     [rbp+57h+var_48], rax
0x1800307c7  lea     rax, [rbp+57h+arg_0]
0x1800307cb  mov     [rbp+57h+var_40], rax
0x1800307cf  call    wil__ResultFromException__lambda_fe7b844e9001a84485ac6c4cb501e51d___
0x1800307d4  mov     [rbp+57h+arg_0], eax
0x1800307d7  mov     ebx, eax
0x1800307d9  test    eax, eax
0x1800307db  jns     short loc_18003082A
0x1800307dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307e4  cmp     rcx, r12
0x1800307e7  jz      short loc_1800307F4
0x1800307e9  cmp     byte ptr [rcx+19h], 5
0x1800307ed  jb      short loc_1800307F4
0x1800307ef  mov     dl, sil
0x1800307f2  jmp     short loc_1800307F6
0x1800307f4  xor     dl, dl
0x1800307f6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800307fd  setnz   r8b
0x180030801  test    dl, dl
0x180030803  jnz     short loc_18003080A
0x180030805  test    r8b, r8b
0x180030808  jz      short loc_180030831
0x18003080a  mov     r9, [rcx+28h]
0x18003080e  mov     rcx, [rcx+10h]
0x180030812  mov     dword ptr [rsp+0C0h+var_78], eax
0x180030816  mov     [rsp+0C0h+var_88], r14
0x18003081b  mov     [rsp+0C0h+var_90], 18h
0x180030822  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180030827  mov     ebx, [rbp+57h+arg_0]
0x18003082a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030831  xor     eax, eax
0x180030833  test    ebx, ebx
0x180030835  jnz     short loc_18003083D
0x180030837  cmp     byte ptr [rcx+19h], 5
0x18003083b  jmp     short loc_180030841
0x18003083d  cmp     byte ptr [rcx+19h], 2
0x180030841  setnb   al
0x180030844  cmp     rcx, r12
0x180030847  jz      short loc_180030852
0x180030849  test    eax, eax
0x18003084b  jz      short loc_180030852
0x18003084d  mov     dl, sil
0x180030850  jmp     short loc_180030854
0x180030852  xor     dl, dl
0x180030854  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003085b  setnz   r8b
0x18003085f  test    dl, dl
0x180030861  jnz     short loc_180030868
0x180030863  test    r8b, r8b
0x180030866  jz      short loc_180030894
0x180030868  mov     r9, [rcx+28h]
0x18003086c  mov     rcx, [rcx+10h]
0x180030870  mov     [rsp+0C0h+var_70], ebx
0x180030874  mov     [rsp+0C0h+var_78], rdi
0x180030879  mov     [rsp+0C0h+var_88], r14
0x18003087e  mov     [rsp+0C0h+var_90], 19h
0x180030885  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18003088a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030891  mov     ebx, [rbp+57h+arg_0]
0x180030894  test    ebx, ebx
0x180030896  jns     short loc_1800308B9
0x180030898  mov     rcx, [rdi+78h]; hEvent
0x18003089c  call    cs:__imp_SetEvent
0x1800308a3  nop     dword ptr [rax+rax+00h]
0x1800308a8  mov     rcx, rdi; this
0x1800308ab  call    ?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)
0x1800308b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308b7  test    ebx, ebx
0x1800308b9  jnz     short loc_1800308C3
0x1800308bb  xor     eax, eax
0x1800308bd  cmp     byte ptr [rcx+19h], 5
0x1800308c1  jmp     short loc_1800308C9
0x1800308c3  xor     eax, eax
0x1800308c5  cmp     byte ptr [rcx+19h], 2
0x1800308c9  setnb   al
0x1800308cc  cmp     rcx, r12
0x1800308cf  jz      short loc_1800308D5
0x1800308d1  test    eax, eax
0x1800308d3  jnz     short loc_1800308D8
0x1800308d5  xor     sil, sil
0x1800308d8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800308df  setnz   r8b
0x1800308e3  test    sil, sil
0x1800308e6  jnz     short loc_1800308ED
0x1800308e8  test    r8b, r8b
0x1800308eb  jz      short loc_180030912
0x1800308ed  mov     r9, [rcx+28h]
0x1800308f1  mov     dl, sil
0x1800308f4  mov     rcx, [rcx+10h]
0x1800308f8  mov     [rsp+0C0h+var_70], ebx
0x1800308fc  mov     [rsp+0C0h+var_78], rdi
0x180030901  mov     [rsp+0C0h+var_88], r14
0x180030906  mov     [rsp+0C0h+var_90], 14h
0x18003090d  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x180030912  mov     eax, ebx
0x180030914  add     rsp, 90h
0x18003091b  pop     r14
0x18003091d  pop     r13
0x18003091f  pop     r12
0x180030921  pop     rdi
0x180030922  pop     rsi
0x180030923  pop     rbx
0x180030924  pop     rbp
0x180030925  retn
```
