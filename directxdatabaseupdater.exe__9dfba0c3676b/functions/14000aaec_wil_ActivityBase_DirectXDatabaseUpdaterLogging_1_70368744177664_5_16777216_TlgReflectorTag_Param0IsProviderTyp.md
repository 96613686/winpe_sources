# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)

- ea: `0x14000aaec`
- end: `0x14000ab45`
- name: `?SetStopResult@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z`
- size: `89`
- prototype: `bool __fastcall(__int64, int, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140006b80`
- `0x14000b5fc`

## callees

- `0x140003ab8`
- `0x14000aaec`
- `0x14000d6a8`

## pseudocode

```c
bool __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
0x14000aaec  sub     rsp, 0C8h
0x14000aaf3  mov     eax, [rcx+0F8h]
0x14000aaf9  cmp     eax, 1
0x14000aafc  jge     short loc_14000AB1B
0x14000aafe  xor     edx, edx; Val
0x14000ab00  mov     r8d, 98h; Size
0x14000ab06  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000ab0b  call    memset_0
0x14000ab10  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000ab15  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000ab1b  cmp     dword ptr [rcx+48h], 0
0x14000ab1f  jl      short loc_14000AB26
0x14000ab21  mov     [rcx+48h], edx
0x14000ab24  jmp     short loc_14000AB29
0x14000ab26  mov     edx, [rcx+48h]
0x14000ab29  test    r8, r8
0x14000ab2c  jz      short loc_14000AB31
0x14000ab2e  mov     [r8], edx
0x14000ab31  sub     eax, 1
0x14000ab34  mov     [rcx+0F8h], eax
0x14000ab3a  setz    al
0x14000ab3d  add     rsp, 0C8h
0x14000ab44  retn
```
