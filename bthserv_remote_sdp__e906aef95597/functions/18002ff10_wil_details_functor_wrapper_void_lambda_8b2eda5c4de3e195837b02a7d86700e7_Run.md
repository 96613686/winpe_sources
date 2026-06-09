# wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run

- ea: `0x18002ff10`
- end: `0x180030090`
- name: `wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002dd10`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x180012004`
- `0x1800120b8`
- `0x18002ff10`
- `0x180030f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ff24`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ff24`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002ff4b`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002ff4b`

## string_xrefs

- `0x18002fff7`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18003007b`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_8b2eda5c4de3e195837b02a7d86700e7___::Run(__int64 a1)
{
  unsigned int **v1; // rbx
  int v2; // edx
  int v3; // r8d
  bool v5; // dl
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(unsigned int ***)(a1 + 8);
  ResetEvent(*((HANDLE *)*v1 + 256));
  *v1[1] = DafStartEnumCeremonies(
             *((_QWORD *)*v1 + 255),
             0,
             0,
             Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback,
             *v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    v6 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v6,
      v8);
  }
  *v1[1] = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)*v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v7 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v7,
      v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18002ff10  push    rbx
0x18002ff12  sub     rsp, 50h
0x18002ff16  mov     rbx, [rcx+8]
0x18002ff1a  mov     rcx, [rbx]
0x18002ff1d  mov     rcx, [rcx+800h]; hEvent
0x18002ff24  call    cs:__imp_ResetEvent
0x18002ff2b  nop     dword ptr [rax+rax+00h]
0x18002ff30  mov     rax, [rbx]
0x18002ff33  lea     r9, ?s_EnumCeremoniesCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXKPEBU_CEREMONY@@PEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)
0x18002ff3a  xor     r8d, r8d
0x18002ff3d  mov     qword ptr [rsp+58h+var_38], rax; int
0x18002ff42  xor     edx, edx
0x18002ff44  mov     rcx, [rax+7F8h]
0x18002ff4b  call    cs:__imp_DafStartEnumCeremonies
0x18002ff52  nop     dword ptr [rax+rax+00h]
0x18002ff57  mov     rcx, [rbx+8]
0x18002ff5b  mov     [rcx], eax
0x18002ff5d  mov     rax, [rbx+8]
0x18002ff61  cmp     dword ptr [rax], 0
0x18002ff64  jl      short loc_18002FF8D
0x18002ff66  mov     rcx, [rbx]; this
0x18002ff69  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x18002ff6e  mov     rcx, [rbx+8]
0x18002ff72  mov     [rcx], eax
0x18002ff74  mov     rax, [rbx+8]
0x18002ff78  mov     r9d, [rax]
0x18002ff7b  test    r9d, r9d
0x18002ff7e  js      loc_18003000C
0x18002ff84  xor     eax, eax
0x18002ff86  add     rsp, 50h
0x18002ff8a  pop     rbx
0x18002ff8b  retn
0x18002ff8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff94  lea     rax, WPP_GLOBAL_Control
0x18002ff9b  cmp     rcx, rax
0x18002ff9e  jz      short loc_18002FFAA
0x18002ffa0  cmp     byte ptr [rcx+19h], 2
0x18002ffa4  jb      short loc_18002FFAA
0x18002ffa6  mov     dl, 1
0x18002ffa8  jmp     short loc_18002FFAC
0x18002ffaa  xor     dl, dl
0x18002ffac  lea     rax, WPP_RECORDER_INITIALIZED
0x18002ffb3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002ffba  setnz   r8b
0x18002ffbe  test    dl, dl
0x18002ffc0  jnz     short loc_18002FFC7
0x18002ffc2  test    r8b, r8b
0x18002ffc5  jz      short loc_18002FFE7
0x18002ffc7  mov     r9, [rcx+28h]
0x18002ffcb  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ffd2  mov     rcx, [rcx+10h]
0x18002ffd6  mov     [rsp+58h+var_20], rax
0x18002ffdb  mov     [rsp+58h+var_28], 48h ; 'H'
0x18002ffe2  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002ffe7  mov     rcx, [rbx+8]
0x18002ffeb  mov     ecx, [rcx]
0x18002ffed  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002fff2  mov     rcx, [rsp+58h]; this
0x18002fff7  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002fffe  mov     r9d, eax; char *
0x180030001  mov     edx, 2A1h; void *
0x180030006  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003000c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030013  lea     rax, WPP_GLOBAL_Control
0x18003001a  cmp     rcx, rax
0x18003001d  jz      short loc_180030029
0x18003001f  cmp     byte ptr [rcx+19h], 2
0x180030023  jb      short loc_180030029
0x180030025  mov     dl, 1
0x180030027  jmp     short loc_18003002B
0x180030029  xor     dl, dl
0x18003002b  lea     rax, WPP_RECORDER_INITIALIZED
0x180030032  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180030039  setnz   r8b
0x18003003d  test    dl, dl
0x18003003f  jnz     short loc_180030046
0x180030041  test    r8b, r8b
0x180030044  jz      short loc_18003006B
0x180030046  mov     [rsp+58h+var_10], r9d
0x18003004b  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030052  mov     r9, [rcx+28h]
0x180030056  mov     rcx, [rcx+10h]
0x18003005a  mov     [rsp+58h+var_20], rax
0x18003005f  mov     [rsp+58h+var_28], 49h ; 'I'
0x180030066  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18003006b  mov     rcx, [rbx+8]
0x18003006f  mov     ecx, [rcx]
0x180030071  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180030076  mov     rcx, [rsp+58h]; this
0x18003007b  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x180030082  mov     r9d, eax; char *
0x180030085  mov     edx, 2A8h; void *
0x18003008a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
