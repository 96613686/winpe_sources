# KeyguardTelemetryTrackApi(uchar,long)

- ea: `0x18001712c`
- end: `0x1800172af`
- name: `?KeyguardTelemetryTrackApi@@YAXEJ@Z`
- size: `387`
- prototype: `void __fastcall(char, int)`
- caller_count: `24`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800163b0`
- `0x180016ca0`
- `0x180016ec0`
- `0x180041300`
- `0x1800414e0`
- `0x180041670`
- `0x180041850`
- `0x180041aa0`
- `0x180041ca0`
- `0x180041e60`
- `0x180042020`
- `0x180042240`
- `0x180042420`
- `0x180042670`
- `0x180042870`
- `0x180042a00`
- `0x180042c20`
- `0x180042f70`
- `0x180043160`
- `0x1800433f0`
- `0x1800435d0`
- `0x180043800`
- `0x1800439e0`
- `0x180043c00`

## callees

- `0x18001712c`
- `0x18001a1c0`
- `0x18001a358`
- `0x18001b9f0`
- `0x1800240f4`
- `0x1800248ac`
- `0x180028a70`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x180017140`
- `ntdll!RtlDllShutdownInProgress` at `0x180017206`
- `ntdll!RtlDllShutdownInProgress` at `0x180017140`
- `ntdll!RtlDllShutdownInProgress` at `0x180017206`

## pseudocode

```c
void __fastcall KeyguardTelemetryTrackApi(char a1, int a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r8
  int *v8; // rbx
  unsigned int ClientProcessId; // eax
  int **v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  int *v15; // [rsp+50h] [rbp-20h] BYREF
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h] BYREF
  __int64 v18; // [rsp+68h] [rbp-8h] BYREF
  int KGRunningInProdMode; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+38h] BYREF

  if ( !RtlDllShutdownInProgress()
    && dword_180079128
    && (unsigned __int8)tlgKeywordOn(&dword_180079128, 0x800000000000LL, v4, v5) )
  {
    v20 = 2048;
    KGRunningInProdMode = BCryptIsoGetKGRunningInProdMode(&g_keyguardRegistryData);
    v15 = 0;
    v16 = 0;
    v17 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v6,
      (int)byte_18006FCF9,
      v7,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&KGRunningInProdMode,
      (__int64)&v20);
  }
  v8 = &dword_18006B48C;
  ClientProcessId = KGT_GetClientProcessId();
  if ( ClientProcessId )
  {
    v10 = (int **)KGT_AcquireImageFromPid((struct KEYGUARD_TELEMETRY_GLOBAL *)qword_18007A780, ClientProcessId);
    if ( v10 )
    {
      if ( *v10 )
        v8 = *v10;
    }
  }
  if ( !RtlDllShutdownInProgress() && dword_180079160 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180079160, 0x800000000000LL, v11, v12) )
    {
      v17 = 0x2000000;
      v16 = 0x1000000;
      v15 = v8;
      LOBYTE(KGRunningInProdMode) = a1;
      LODWORD(v20) = a2;
      v18 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v13,
        (unsigned __int8 *)&word_18006FC8E,
        v14,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&KGRunningInProdMode,
        &v15,
        (__int64)&v16,
        (__int64)&v17);
    }
  }
}

```

## disassembly

```asm
0x18001712c  mov     [rsp-18h+arg_0], rbx
0x180017131  push    rbp
0x180017132  push    rsi
0x180017133  push    rdi
0x180017134  mov     rbp, rsp
0x180017137  sub     rsp, 70h
0x18001713b  mov     edi, edx
0x18001713d  mov     sil, cl
0x180017140  call    cs:__imp_RtlDllShutdownInProgress
0x180017147  nop     dword ptr [rax+rax+00h]
0x18001714c  test    al, al
0x18001714e  jnz     loc_1800171DB
0x180017154  mov     eax, cs:dword_180079128
0x18001715a  test    eax, eax
0x18001715c  jz      short loc_1800171DB
0x18001715e  mov     rdx, 800000000000h
0x180017168  lea     rcx, dword_180079128
0x18001716f  call    _tlgKeywordOn
0x180017174  test    al, al
0x180017176  jz      short loc_1800171DB
0x180017178  lea     rcx, ?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18001717f  mov     [rbp+arg_18], 800h
0x180017187  call    BCryptIsoGetKGRunningInProdMode
0x18001718c  mov     [rbp+arg_10], eax
0x18001718f  lea     r9, [rbp+var_10]
0x180017193  lea     rax, [rbp+arg_18]
0x180017197  mov     [rbp+var_20], 0
0x18001719f  mov     [rsp+70h+var_38], rax
0x1800171a4  lea     rdx, byte_18006FCF9
0x1800171ab  lea     rax, [rbp+arg_10]
0x1800171af  mov     [rbp+var_18], 0
0x1800171b7  mov     [rsp+70h+var_40], rax
0x1800171bc  lea     rax, [rbp+var_20]
0x1800171c0  mov     [rsp+70h+var_48], rax
0x1800171c5  lea     rax, [rbp+var_18]
0x1800171c9  mov     [rsp+70h+var_50], rax
0x1800171ce  mov     [rbp+var_10], 1
0x1800171d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@22AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800171db  lea     rbx, dword_18006B48C
0x1800171e2  call    ?KGT_GetClientProcessId@@YAKXZ; KGT_GetClientProcessId(void)
0x1800171e7  test    eax, eax
0x1800171e9  jz      short loc_180017206
0x1800171eb  mov     edx, eax; unsigned int
0x1800171ed  lea     rcx, qword_18007A780; struct KEYGUARD_TELEMETRY_GLOBAL *
0x1800171f4  call    ?KGT_AcquireImageFromPid@@YAPEAUKEYGUARD_TELEMETRY_IMAGE_T@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@K@Z; KGT_AcquireImageFromPid(KEYGUARD_TELEMETRY_GLOBAL *,ulong)
0x1800171f9  test    rax, rax
0x1800171fc  jz      short loc_180017206
0x1800171fe  cmp     qword ptr [rax], 0
0x180017202  cmovnz  rbx, [rax]
0x180017206  call    cs:__imp_RtlDllShutdownInProgress
0x18001720d  nop     dword ptr [rax+rax+00h]
0x180017212  test    al, al
0x180017214  jnz     loc_18001729E
0x18001721a  mov     eax, cs:dword_180079160
0x180017220  test    eax, eax
0x180017222  jz      short loc_18001729E
0x180017224  mov     rdx, 800000000000h
0x18001722e  lea     rcx, dword_180079160
0x180017235  call    _tlgKeywordOn
0x18001723a  test    al, al
0x18001723c  jz      short loc_18001729E
0x18001723e  lea     rax, [rbp+var_10]
0x180017242  mov     [rbp+var_10], 2000000h
0x18001724a  mov     [rsp+70h+var_30], rax
0x18001724f  lea     r9, [rbp+var_8]
0x180017253  lea     rax, [rbp+var_18]
0x180017257  mov     [rbp+var_18], 1000000h
0x18001725f  mov     [rsp+70h+var_38], rax
0x180017264  lea     rdx, word_18006FC8E
0x18001726b  lea     rax, [rbp+var_20]
0x18001726f  mov     [rbp+var_20], rbx
0x180017273  mov     [rsp+70h+var_40], rax
0x180017278  lea     rax, [rbp+arg_10]
0x18001727c  mov     [rsp+70h+var_48], rax
0x180017281  lea     rax, [rbp+arg_18]
0x180017285  mov     [rsp+70h+var_50], rax
0x18001728a  mov     byte ptr [rbp+arg_10], sil
0x18001728e  mov     dword ptr [rbp+arg_18], edi
0x180017291  mov     [rbp+var_8], 1
0x180017299  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@22@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001729e  mov     rbx, [rsp+70h+arg_0]
0x1800172a6  add     rsp, 70h
0x1800172aa  pop     rdi
0x1800172ab  pop     rsi
0x1800172ac  pop     rbp
0x1800172ad  retn
```
