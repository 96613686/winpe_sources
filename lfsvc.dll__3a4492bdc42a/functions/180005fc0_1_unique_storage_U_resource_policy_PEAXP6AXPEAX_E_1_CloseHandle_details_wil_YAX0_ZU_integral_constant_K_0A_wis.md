# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180005fc0`
- end: `0x180005fd6`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005e1c`
- `0x180005e4c`
- `0x180006090`
- `0x180006308`
- `0x180006498`
- `0x1800097f4`

## callees

- `0x180005fc0`
- `0x180006628`

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
0x180005fc0  sub     rsp, 28h
0x180005fc4  mov     rcx, [rcx]; this
0x180005fc7  test    rcx, rcx
0x180005fca  jz      short loc_180005FD1
0x180005fcc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005fd1  add     rsp, 28h
0x180005fd5  retn
```
