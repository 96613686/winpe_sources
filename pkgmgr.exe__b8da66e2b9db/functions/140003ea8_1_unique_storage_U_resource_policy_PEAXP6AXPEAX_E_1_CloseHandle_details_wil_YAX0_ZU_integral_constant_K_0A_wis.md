# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x140003ea8`
- end: `0x140003ebe`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003d40`
- `0x140003f20`
- `0x140003ff8`
- `0x140005f40`
- `0x14000e55c`
- `0x14000e8f4`

## callees

- `0x140003ea8`
- `0x140004164`

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
0x140003ea8  sub     rsp, 28h
0x140003eac  mov     rcx, [rcx]; this
0x140003eaf  test    rcx, rcx
0x140003eb2  jz      short loc_140003EB9
0x140003eb4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140003eb9  add     rsp, 28h
0x140003ebd  retn
```
