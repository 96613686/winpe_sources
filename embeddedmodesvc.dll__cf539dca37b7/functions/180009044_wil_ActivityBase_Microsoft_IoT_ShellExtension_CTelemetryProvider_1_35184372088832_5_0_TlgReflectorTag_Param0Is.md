# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)

- ea: `0x180009044`
- end: `0x18000909d`
- name: `?SetStopResult@?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800087b8`
- `0x1800091c4`
- `0x180011454`
- `0x180013b38`

## callees

- `0x1800035a0`
- `0x1800068e8`
- `0x180009044`

## pseudocode

```c
bool __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        __int64 a1,
        int a2,
        _DWORD *a3)
{
  int v3; // eax
  const struct wil::FailureInfo *v4; // rdx
  int v5; // eax
  _BYTE v7[168]; // [rsp+20h] [rbp-A8h] BYREF

  v3 = *(_DWORD *)(a1 + 248);
  if ( v3 < 1 )
  {
    memset_0(v7, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v7, v4);
  }
  if ( *(int *)(a1 + 72) < 0 )
    a2 = *(_DWORD *)(a1 + 72);
  else
    *(_DWORD *)(a1 + 72) = a2;
  if ( a3 )
    *a3 = a2;
  v5 = v3 - 1;
  *(_DWORD *)(a1 + 248) = v5;
  return v5 == 0;
}

```

## disassembly

```asm
0x180009044  sub     rsp, 0C8h
0x18000904b  mov     eax, [rcx+0F8h]
0x180009051  cmp     eax, 1
0x180009054  jge     short loc_180009073
0x180009056  xor     edx, edx; Val
0x180009058  mov     r8d, 98h; Size
0x18000905e  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009063  call    memset_0
0x180009068  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000906d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009073  cmp     dword ptr [rcx+48h], 0
0x180009077  jl      short loc_18000907E
0x180009079  mov     [rcx+48h], edx
0x18000907c  jmp     short loc_180009081
0x18000907e  mov     edx, [rcx+48h]
0x180009081  test    r8, r8
0x180009084  jz      short loc_180009089
0x180009086  mov     [r8], edx
0x180009089  sub     eax, 1
0x18000908c  mov     [rcx+0F8h], eax
0x180009092  setz    al
0x180009095  add     rsp, 0C8h
0x18000909c  retn
```
