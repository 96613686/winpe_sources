# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180005a98`
- end: `0x180005aae`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005ca8`
- `0x180005e10`
- `0x1800085d4`
- `0x180008654`

## callees

- `0x180005a98`
- `0x1800086e4`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::ReleaseMutex(v2, a2);
}

```

## disassembly

```asm
0x180005a98  sub     rsp, 28h
0x180005a9c  mov     rcx, [rcx]; this
0x180005a9f  test    rcx, rcx
0x180005aa2  jz      short loc_180005AA9
0x180005aa4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180005aa9  add     rsp, 28h
0x180005aad  retn
```
