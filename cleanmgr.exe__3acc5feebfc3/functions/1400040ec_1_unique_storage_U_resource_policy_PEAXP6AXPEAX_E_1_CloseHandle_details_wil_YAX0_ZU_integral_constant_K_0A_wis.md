# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x1400040ec`
- end: `0x140004102`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003f5c`
- `0x140004164`
- `0x140004238`
- `0x1400061a0`
- `0x140006d58`
- `0x140007260`

## callees

- `0x1400040ec`
- `0x1400043b4`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::CloseHandle(v2, a2);
}

```

## disassembly

```asm
0x1400040ec  sub     rsp, 28h
0x1400040f0  mov     rcx, [rcx]; this
0x1400040f3  test    rcx, rcx
0x1400040f6  jz      short loc_1400040FD
0x1400040f8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400040fd  add     rsp, 28h
0x140004101  retn
```
