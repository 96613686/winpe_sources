# CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo_(PluginDeactivatationStart *,ushort const *,ulong,bool,ushort,int,int,unsigned __int64,uint)

- ea: `0x14000fd68`
- end: `0x14000fe83`
- name: `?LogPluginsDeactivatationStartInfo_@CleanupMgrTelemetry@@QEAAXPEAUPluginDeactivatationStart@@PEBGK_NGHH_KI@Z`
- size: `283`
- prototype: `void __fastcall(CleanupMgrTelemetry *this, struct PluginDeactivatationStart *, const unsigned __int16 *, int, bool, unsigned __int16, int, int, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000efac`

## callees

- `0x1400019bc`
- `0x140002330`
- `0x14000e15c`
- `0x14000fd68`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::LogPluginsDeactivatationStartInfo_(
        CleanupMgrTelemetry *this,
        struct PluginDeactivatationStart *a2,
        const unsigned __int16 *a3,
        int a4,
        bool a5,
        unsigned __int16 a6,
        int a7,
        int a8,
        unsigned __int64 a9,
        unsigned int a10)
{
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r10
  unsigned __int16 v18[2]; // [rsp+80h] [rbp-49h] BYREF
  int v19; // [rsp+84h] [rbp-45h] BYREF
  int v20; // [rsp+88h] [rbp-41h] BYREF
  int v21; // [rsp+8Ch] [rbp-3Dh] BYREF
  unsigned int v22; // [rsp+90h] [rbp-39h] BYREF
  unsigned __int64 v23; // [rsp+98h] [rbp-31h] BYREF
  const WCHAR *v24; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-21h] BYREF
  struct PluginDeactivatationStart *v26; // [rsp+B0h] [rbp-19h] BYREF
  int v27; // [rsp+B8h] [rbp-11h]
  unsigned __int16 *v28; // [rsp+C0h] [rbp-9h] BYREF
  int v29; // [rsp+C8h] [rbp-1h]
  CleanupMgrTelemetry *v30; // [rsp+100h] [rbp+37h] BYREF

  v30 = this;
  v13 = g_hProvider::Provider();
  if ( *(_DWORD *)v13 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL, v14) )
    {
      v28 = &a6;
      v23 = a9;
      LOBYTE(v30) = a5;
      v19 = a8;
      v20 = a7;
      v22 = a10;
      v18[0] = a6;
      v26 = a2;
      v27 = 200 * a6;
      v29 = 2;
      v21 = a4;
      v24 = a3;
      v25 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v17,
        (__int64)&byte_14001C1CF,
        v15,
        v16,
        (__int64)&v25,
        (__int64)&v22,
        &v24,
        (__int64)&v21,
        (__int64)v18,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v23,
        (__int64 *)&v28,
        (__int64 *)&v26);
    }
  }
}

```

## disassembly

```asm
0x14000fd68  mov     [rsp-8+arg_0], rcx
0x14000fd6d  push    rbp
0x14000fd6e  push    rbx
0x14000fd6f  push    rsi
0x14000fd70  push    rdi
0x14000fd71  lea     rbp, [rsp-0Fh]
0x14000fd76  sub     rsp, 0D8h
0x14000fd7d  mov     ebx, r9d
0x14000fd80  mov     rdi, r8
0x14000fd83  mov     rsi, rdx
0x14000fd86  call    ?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ; g_hProvider::Provider(void)
0x14000fd8b  mov     r10, rax
0x14000fd8e  mov     ecx, [rax]
0x14000fd90  test    ecx, ecx
0x14000fd92  jz      loc_14000FE77
0x14000fd98  mov     rdx, 400000000000h
0x14000fda2  mov     rcx, rax
0x14000fda5  call    _tlgKeywordOn
0x14000fdaa  test    al, al
0x14000fdac  jz      loc_14000FE77
0x14000fdb2  movzx   edx, [rbp+27h+arg_28]
0x14000fdb6  lea     rax, [rbp+27h+arg_28]
0x14000fdba  mov     [rbp+27h+var_30], rax
0x14000fdbe  mov     rax, [rbp+27h+arg_40]
0x14000fdc2  mov     [rbp+27h+var_58], rax
0x14000fdc6  mov     al, [rbp+27h+arg_20]
0x14000fdc9  mov     byte ptr [rbp+27h+arg_0], al
0x14000fdcc  mov     eax, [rbp+27h+arg_38]
0x14000fdcf  mov     [rbp+27h+var_6C], eax
0x14000fdd2  mov     eax, [rbp+27h+arg_30]
0x14000fdd5  mov     [rbp+27h+var_68], eax
0x14000fdd8  mov     eax, [rbp+27h+arg_48]
0x14000fddb  mov     [rbp+27h+var_60], eax
0x14000fdde  lea     rax, [rbp+27h+var_40]
0x14000fde2  mov     [rsp+0F0h+var_80], rax
0x14000fde7  lea     rax, [rbp+27h+var_30]
0x14000fdeb  mov     [rsp+0F0h+var_88], rax
0x14000fdf0  lea     rax, [rbp+27h+var_58]
0x14000fdf4  mov     [rsp+0F0h+var_90], rax
0x14000fdf9  lea     rax, [rbp+27h+arg_0]
0x14000fdfd  mov     [rsp+0F0h+var_98], rax
0x14000fe02  lea     rax, [rbp+27h+var_6C]
0x14000fe06  mov     [rsp+0F0h+var_A0], rax
0x14000fe0b  lea     rax, [rbp+27h+var_68]
0x14000fe0f  mov     [rsp+0F0h+var_A8], rax
0x14000fe14  lea     rax, [rbp+27h+var_70]
0x14000fe18  mov     [rsp+0F0h+var_B0], rax
0x14000fe1d  lea     rax, [rbp+27h+var_64]
0x14000fe21  mov     [rsp+0F0h+var_B8], rax
0x14000fe26  lea     rax, [rbp+27h+var_50]
0x14000fe2a  mov     [rsp+0F0h+var_C0], rax
0x14000fe2f  lea     rax, [rbp+27h+var_60]
0x14000fe33  imul    ecx, edx, 0C8h
0x14000fe39  mov     [rsp+0F0h+var_C8], rax
0x14000fe3e  lea     rax, [rbp+27h+var_48]
0x14000fe42  mov     [rbp+27h+var_70], dx
0x14000fe46  lea     rdx, byte_14001C1CF
0x14000fe4d  mov     [rsp+0F0h+var_D0], rax
0x14000fe52  mov     [rbp+27h+var_40], rsi
0x14000fe56  mov     [rbp+27h+var_38], ecx
0x14000fe59  mov     rcx, r10
0x14000fe5c  mov     [rbp+27h+var_28], 2
0x14000fe63  mov     [rbp+27h+var_64], ebx
0x14000fe66  mov     [rbp+27h+var_50], rdi
0x14000fe6a  mov     [rbp+27h+var_48], 1000000h
0x14000fe72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$01@@U2@U2@U?$_tlgWrapperByVal@$00@@U1@U_tlgWrapperPtrSize@@U6@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$01@@44AEBU?$_tlgWrapperByVal@$00@@3AEBU_tlgWrapperPtrSize@@8@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperPtrSize const &)
0x14000fe77  add     rsp, 0D8h
0x14000fe7e  pop     rdi
0x14000fe7f  pop     rsi
0x14000fe80  pop     rbx
0x14000fe81  pop     rbp
0x14000fe82  retn
```
