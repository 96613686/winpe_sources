# DAS::DevnodeManagment::Interface::Create(HSWDEVICE__ *,_GUID *,ushort const *,ulong,_DEVPROPERTY * const,int,IAepDevnodeInterface * *)

- ea: `0x18005db8c`
- end: `0x18005dd0c`
- name: `?Create@Interface@DevnodeManagment@DAS@@SAJPEAUHSWDEVICE__@@PEAU_GUID@@PEBGKQEAU_DEVPROPERTY@@HPEAPEAUIAepDevnodeInterface@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(struct HSWDEVICE__ *, struct _GUID *, const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *const, int, struct IAepDevnodeInterface **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005df90`

## callees

- `0x180025db4`
- `0x1800263f4`
- `0x18002a948`
- `0x18002e0bc`
- `0x18005db8c`
- `0x180082010`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18005dc03`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x18005dc03`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18005dc43`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18005dc43`

## string_xrefs

- `0x18005dbcd`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005dc5a`: `onecore\base\devices\association\service\lib\devnode.cpp`
- `0x18005dcb3`: `onecore\base\devices\association\service\lib\devnode.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::Interface::Create(
        struct HSWDEVICE__ *a1,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct _DEVPROPERTY *const a5,
        int a6,
        struct IAepDevnodeInterface **a7)
{
  _QWORD *v11; // rbx
  __int64 result; // rax
  __int64 v13; // rdi
  int v14; // eax
  unsigned int v15; // edi
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // edi
  int v19; // [rsp+20h] [rbp-68h]
  _QWORD *v20; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v21[64]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Microsoft::WRL::Details::Make<DAS::DevnodeManagment::Interface,>(&v20);
  v11 = v20;
  if ( v20 )
  {
    v20[3] = a1;
    v13 = v11[2];
    if ( v13 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v21);
      SwMemFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v21);
    }
    v11[2] = 0;
    v14 = SwDeviceInterfaceRegister(a1, a2, a3, a4);
    try
    {
      v15 = v14;
      if ( v14 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IAepDevnodeInterface **))*v11)(
                v11,
                &GUID_c5d18807_0060_4364_8405_0ae39a57f2e0,
                a7);
        v18 = v17;
        if ( v17 >= 0 )
        {
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x42,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
            (const char *)(unsigned int)v17,
            (int)a5);
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
          result = v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
          (const char *)(unsigned int)v14,
          (int)a5);
        if ( v11 )
          (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
        result = v15;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x45,
                             (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
                             v16);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnode.cpp",
      (const char *)0x8007000ELL,
      v19);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005db8c  push    rbx
0x18005db8e  push    rsi
0x18005db8f  push    rdi
0x18005db90  push    r12
0x18005db92  push    r13
0x18005db94  push    r14
0x18005db96  push    r15
0x18005db98  sub     rsp, 50h
0x18005db9c  mov     r15d, r9d
0x18005db9f  mov     r12, r8
0x18005dba2  mov     r13, rdx
0x18005dba5  mov     r14, rcx
0x18005dba8  lea     rcx, [rsp+88h+var_48]
0x18005dbad  call    ??$Make@VInterface@DevnodeManagment@DAS@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VInterface@DevnodeManagment@DAS@@@12@XZ; Microsoft::WRL::Details::Make<DAS::DevnodeManagment::Interface,>(void)
0x18005dbb2  nop
0x18005dbb3  mov     rbx, [rsp+88h+var_48]
0x18005dbb8  test    rbx, rbx
0x18005dbbb  jnz     short loc_18005DBE6
0x18005dbbd  mov     rcx, [rsp+88h]; this
0x18005dbc5  mov     ebx, 8007000Eh
0x18005dbca  mov     r9d, ebx; char *
0x18005dbcd  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005dbd4  mov     edx, 38h ; '8'; void *
0x18005dbd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dbde  nop
0x18005dbdf  mov     eax, ebx
0x18005dbe1  jmp     loc_18005DCFB
0x18005dbe6  mov     [rbx+18h], r14
0x18005dbea  lea     rsi, [rbx+10h]
0x18005dbee  mov     rdi, [rsi]
0x18005dbf1  test    rdi, rdi
0x18005dbf4  jz      short loc_18005DC13
0x18005dbf6  lea     rcx, [rsp+88h+var_40]; this
0x18005dbfb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005dc00  mov     rcx, rdi
0x18005dc03  call    cs:__imp_SwMemFree
0x18005dc09  lea     rcx, [rsp+88h+var_40]; this
0x18005dc0e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005dc13  mov     qword ptr [rsi], 0
0x18005dc1a  mov     [rsp+88h+var_58], rsi
0x18005dc1f  mov     eax, [rsp+88h+arg_28]
0x18005dc26  mov     [rsp+88h+var_60], eax
0x18005dc2a  mov     rax, [rsp+88h+arg_20]
0x18005dc32  mov     qword ptr [rsp+88h+var_68], rax; int
0x18005dc37  mov     r9d, r15d
0x18005dc3a  mov     r8, r12
0x18005dc3d  mov     rdx, r13
0x18005dc40  mov     rcx, r14
0x18005dc43  call    cs:__imp_SwDeviceInterfaceRegister
0x18005dc49  mov     edi, eax
0x18005dc4b  test    eax, eax
0x18005dc4d  jns     short loc_18005DC85
0x18005dc4f  mov     rcx, [rsp+88h]; this
0x18005dc57  mov     r9d, eax; char *
0x18005dc5a  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005dc61  mov     edx, 41h ; 'A'; void *
0x18005dc66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dc6b  nop
0x18005dc6c  test    rbx, rbx
0x18005dc6f  jz      short loc_18005DC81
0x18005dc71  mov     rax, [rbx]
0x18005dc74  mov     rcx, rbx
0x18005dc77  mov     rax, [rax+10h]
0x18005dc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc80  nop
0x18005dc81  mov     eax, edi
0x18005dc83  jmp     short loc_18005DCFB
0x18005dc85  mov     rax, [rbx]
0x18005dc88  mov     r8, [rsp+88h+arg_30]
0x18005dc90  lea     rdx, _GUID_c5d18807_0060_4364_8405_0ae39a57f2e0
0x18005dc97  mov     rcx, rbx
0x18005dc9a  mov     rax, [rax]
0x18005dc9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dca2  mov     edi, eax
0x18005dca4  test    eax, eax
0x18005dca6  jns     short loc_18005DCDE
0x18005dca8  mov     rcx, [rsp+88h]; this
0x18005dcb0  mov     r9d, eax; char *
0x18005dcb3  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\association\\se"...
0x18005dcba  mov     edx, 42h ; 'B'; void *
0x18005dcbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dcc4  nop
0x18005dcc5  test    rbx, rbx
0x18005dcc8  jz      short loc_18005DCDA
0x18005dcca  mov     rax, [rbx]
0x18005dccd  mov     rcx, rbx
0x18005dcd0  mov     rax, [rax+10h]
0x18005dcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcd9  nop
0x18005dcda  mov     eax, edi
0x18005dcdc  jmp     short loc_18005DCFB
0x18005dcde  test    rbx, rbx
0x18005dce1  jz      short loc_18005DCF3
0x18005dce3  mov     rax, [rbx]
0x18005dce6  mov     rcx, rbx
0x18005dce9  mov     rax, [rax+10h]
0x18005dced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcf2  nop
0x18005dcf3  xor     eax, eax
0x18005dcf5  jmp     short loc_18005DCFB
0x18005dcf7  mov     eax, dword ptr [rsp+88h+var_48]
0x18005dcfb  add     rsp, 50h
0x18005dcff  pop     r15
0x18005dd01  pop     r14
0x18005dd03  pop     r13
0x18005dd05  pop     r12
0x18005dd07  pop     rdi
0x18005dd08  pop     rsi
0x18005dd09  pop     rbx
0x18005dd0a  retn
```
