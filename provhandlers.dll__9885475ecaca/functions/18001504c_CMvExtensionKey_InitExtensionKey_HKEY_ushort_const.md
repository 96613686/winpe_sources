# CMvExtensionKey::InitExtensionKey(HKEY__ *,ushort const *)

- ea: `0x18001504c`
- end: `0x180015269`
- name: `?InitExtensionKey@CMvExtensionKey@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `541`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800145f8`

## callees

- `0x18000108c`
- `0x1800017c4`
- `0x1800041a4`
- `0x18001504c`
- `0x1800153b4`
- `0x18001576c`
- `0x180037aa8`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001509e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001509e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015122`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001518d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015122`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001518d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMvExtensionKey::InitExtensionKey(HKEY *this, HKEY hKey, const unsigned __int16 *a3)
{
  LSTATUS v6; // eax
  signed int BasicSettings; // ebx
  bool v8; // cc
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  const WCHAR *v14; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-21h] BYREF
  int v16; // [rsp+40h] [rbp-19h]
  char v17; // [rsp+44h] [rbp-15h]
  GUID ActivityId; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp+Fh] BYREF
  const WCHAR **v20; // [rsp+88h] [rbp+2Fh]
  __int64 v21; // [rsp+90h] [rbp+37h]

  hKeya = 0;
  v16 = 0;
  v17 = 0;
  if ( (unsigned int)dword_180052170 <= 4 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v16 = 1;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v14 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)byte_1800495A5,
      (__int64)&ActivityId,
      0,
      &v14);
  }
  v6 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &hKeya);
  BasicSettings = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_7;
  BasicSettings = CMvExtensionKey::ReadBasicSettings((CMvExtensionKey *)this, hKeya, a3);
  if ( BasicSettings >= 0 )
  {
    BasicSettings = CMvExtensionKey::ReadProvisionStates((CMvExtensionKey *)this, hKeya);
    if ( BasicSettings >= 0 )
    {
      if ( this[78] )
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
      v6 = RegOpenKeyExW(hKeya, L"Keys", 0, 0x20019u, this + 78);
      BasicSettings = v6;
      v8 = v6 <= 0;
      if ( v6 )
      {
LABEL_7:
        if ( !v8 )
          BasicSettings = (unsigned __int16)v6 | 0x80070000;
      }
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( BasicSettings < 0 && (unsigned int)dword_180052170 > 2 )
  {
    v14 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_180052170,
      (__int64)&word_1800495D6,
      (__int64)&ActivityId,
      0,
      &v14);
  }
  v16 = 2;
  if ( (unsigned int)dword_180052170 > 4 )
  {
    LODWORD(v14) = BasicSettings;
    v20 = &v14;
    v21 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180052170, byte_18004952B, &ActivityId, 0, 3, v19);
  }
  if ( v16 == 1 )
  {
    v16 = 2;
    _tlgWriteActivityAutoStop<0,4>((unsigned int *)&dword_180052170, (__int64)&ActivityId);
  }
  return (unsigned int)BasicSettings;
}

```

## disassembly

```asm
0x18001504c  mov     [rsp-8+arg_18], rbx
0x180015051  push    rbp
0x180015052  push    rsi
0x180015053  push    rdi
0x180015054  lea     rbp, [rsp-47h]
0x180015059  sub     rsp, 0A0h
0x180015060  mov     rax, cs:__security_cookie
0x180015067  xor     rax, rsp
0x18001506a  mov     [rbp+57h+var_18], rax
0x18001506e  mov     rsi, r8
0x180015071  mov     rbx, rdx
0x180015074  mov     rdi, rcx
0x180015077  mov     [rbp+57h+hKey], 0
0x18001507f  mov     [rbp+57h+var_70], 0
0x180015086  mov     [rbp+57h+var_6C], 0
0x18001508a  mov     eax, cs:dword_180052170
0x180015090  cmp     eax, 4
0x180015093  jbe     short loc_1800150A6
0x180015095  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180015099  mov     ecx, 3; ControlCode
0x18001509e  call    cs:__imp_EventActivityIdControl
0x1800150a4  jmp     short loc_1800150AD
0x1800150a6  xorps   xmm0, xmm0
0x1800150a9  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800150ad  mov     [rbp+57h+var_70], 1
0x1800150b4  mov     eax, cs:dword_180052170
0x1800150ba  cmp     eax, 4
0x1800150bd  jbe     short loc_18001510A
0x1800150bf  mov     [rbp+57h+var_80], rsi
0x1800150c3  cmp     [rbp+57h+var_6C], 0
0x1800150c7  jz      short loc_1800150E7
0x1800150c9  cmp     [rbp+57h+var_58], 0
0x1800150cd  jnz     short loc_1800150E1
0x1800150cf  cmp     [rbp+57h+var_54], 0
0x1800150d3  jnz     short loc_1800150E1
0x1800150d5  cmp     [rbp+57h+var_50], 0
0x1800150d9  jnz     short loc_1800150E1
0x1800150db  cmp     [rbp+57h+var_4C], 0
0x1800150df  jz      short loc_1800150E7
0x1800150e1  lea     r9, [rbp+57h+var_58]
0x1800150e5  jmp     short loc_1800150EA
0x1800150e7  xor     r9d, r9d
0x1800150ea  lea     rax, [rbp+57h+var_80]
0x1800150ee  mov     [rsp+0B0h+phkResult], rax
0x1800150f3  lea     r8, [rbp+57h+ActivityId]
0x1800150f7  lea     rdx, byte_1800495A5
0x1800150fe  lea     rcx, dword_180052170
0x180015105  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001510a  lea     rax, [rbp+57h+hKey]
0x18001510e  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180015113  mov     r9d, 20019h; samDesired
0x180015119  xor     r8d, r8d; ulOptions
0x18001511c  mov     rdx, rsi; lpSubKey
0x18001511f  mov     rcx, rbx; hKey
0x180015122  call    cs:__imp_RegOpenKeyExW
0x180015128  mov     ebx, eax
0x18001512a  test    eax, eax
0x18001512c  jz      short loc_18001513B
0x18001512e  jle     short loc_180015199
0x180015130  movzx   ebx, ax
0x180015133  or      ebx, 80070000h
0x180015139  jmp     short loc_180015199
0x18001513b  mov     r8, rsi; unsigned __int16 *
0x18001513e  mov     rdx, [rbp+57h+hKey]; HKEY
0x180015142  mov     rcx, rdi; this
0x180015145  call    ?ReadBasicSettings@CMvExtensionKey@@AEAAJPEAUHKEY__@@PEBG@Z; CMvExtensionKey::ReadBasicSettings(HKEY__ *,ushort const *)
0x18001514a  mov     ebx, eax
0x18001514c  test    eax, eax
0x18001514e  js      short loc_180015199
0x180015150  mov     rdx, [rbp+57h+hKey]; HKEY
0x180015154  mov     rcx, rdi; this
0x180015157  call    ?ReadProvisionStates@CMvExtensionKey@@AEAAJPEAUHKEY__@@@Z; CMvExtensionKey::ReadProvisionStates(HKEY__ *)
0x18001515c  mov     ebx, eax
0x18001515e  test    eax, eax
0x180015160  js      short loc_180015199
0x180015162  lea     rbx, [rdi+270h]
0x180015169  cmp     qword ptr [rbx], 0
0x18001516d  jz      short loc_180015174
0x18001516f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015174  mov     [rsp+0B0h+phkResult], rbx; phkResult
0x180015179  mov     r9d, 20019h; samDesired
0x18001517f  xor     r8d, r8d; ulOptions
0x180015182  lea     rdx, aKeys; "Keys"
0x180015189  mov     rcx, [rbp+57h+hKey]; hKey
0x18001518d  call    cs:__imp_RegOpenKeyExW
0x180015193  mov     ebx, eax
0x180015195  test    eax, eax
0x180015197  jnz     short loc_18001512E
0x180015199  mov     rcx, [rbp+57h+hKey]; hKey
0x18001519d  test    rcx, rcx
0x1800151a0  jz      short loc_1800151A8
0x1800151a2  call    cs:__imp_RegCloseKey
0x1800151a8  mov     edi, 2
0x1800151ad  test    ebx, ebx
0x1800151af  jns     short loc_1800151E2
0x1800151b1  mov     eax, cs:dword_180052170
0x1800151b7  cmp     eax, edi
0x1800151b9  jbe     short loc_1800151E2
0x1800151bb  mov     [rbp+57h+var_80], rsi
0x1800151bf  lea     rax, [rbp+57h+var_80]
0x1800151c3  mov     [rsp+0B0h+phkResult], rax
0x1800151c8  xor     r9d, r9d
0x1800151cb  lea     r8, [rbp+57h+ActivityId]
0x1800151cf  lea     rdx, word_1800495D6
0x1800151d6  lea     rcx, dword_180052170
0x1800151dd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800151e2  mov     [rbp+57h+var_70], edi
0x1800151e5  mov     eax, cs:dword_180052170
0x1800151eb  cmp     eax, 4
0x1800151ee  jbe     short loc_18001522F
0x1800151f0  mov     dword ptr [rbp+57h+var_80], ebx
0x1800151f3  lea     rax, [rbp+57h+var_80]
0x1800151f7  mov     [rbp+57h+var_28], rax
0x1800151fb  mov     [rbp+57h+var_20], 4
0x180015203  lea     rax, [rbp+57h+var_48]
0x180015207  mov     [rsp+0B0h+var_88], rax
0x18001520c  mov     dword ptr [rsp+0B0h+phkResult], 3
0x180015214  xor     r9d, r9d
0x180015217  lea     r8, [rbp+57h+ActivityId]
0x18001521b  lea     rdx, byte_18004952B
0x180015222  lea     rcx, dword_180052170
0x180015229  call    _tlgWriteTransfer_EventWriteTransfer
0x18001522e  nop
0x18001522f  cmp     [rbp+57h+var_70], 1
0x180015233  jnz     short loc_180015248
0x180015235  mov     [rbp+57h+var_70], edi
0x180015238  lea     rdx, [rbp+57h+ActivityId]
0x18001523c  lea     rcx, dword_180052170
0x180015243  call    ??$_tlgWriteActivityAutoStop@$0A@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,4>(_tlgProvider_t const *,_GUID const *)
0x180015248  mov     eax, ebx
0x18001524a  mov     rcx, [rbp+57h+var_18]
0x18001524e  xor     rcx, rsp; StackCookie
0x180015251  call    __security_check_cookie
0x180015256  mov     rbx, [rsp+0B0h+arg_18]
0x18001525e  add     rsp, 0A0h
0x180015265  pop     rdi
0x180015266  pop     rsi
0x180015267  pop     rbp
0x180015268  retn
```
