# std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS *,Microsoft::HostGuardian::Client::RtlDestroyProcessParameters_deleter>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS *,Microsoft::HostGuardian::Client::RtlDestroyProcessParameters_deleter>(void)

- ea: `0x180012724`
- end: `0x18001273b`
- name: `??1?$unique_ptr@PEAU_RTL_USER_PROCESS_PARAMETERS@@URtlDestroyProcessParameters_deleter@Client@HostGuardian@Microsoft@@@std@@QEAA@XZ`
- size: `23`
- prototype: `NTSTATUS __fastcall(struct _RTL_USER_PROCESS_PARAMETERS **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001667c`

## callees

- `0x180012724`

## import_xrefs

- `ntdll!RtlDestroyProcessParameters` at `0x180012730`
- `ntdll!RtlDestroyProcessParameters` at `0x180012730`

## pseudocode

```c
NTSTATUS __fastcall std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS *,Microsoft::HostGuardian::Client::RtlDestroyProcessParameters_deleter>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS *,Microsoft::HostGuardian::Client::RtlDestroyProcessParameters_deleter>(
        struct _RTL_USER_PROCESS_PARAMETERS **a1)
{
  struct _RTL_USER_PROCESS_PARAMETERS *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return RtlDestroyProcessParameters(v1);
  return result;
}

```

## disassembly

```asm
0x180012724  sub     rsp, 28h
0x180012728  mov     rcx, [rcx]; ProcessParameters
0x18001272b  test    rcx, rcx
0x18001272e  jz      short loc_180012736
0x180012730  call    cs:__imp_RtlDestroyProcessParameters
0x180012736  add     rsp, 28h
0x18001273a  retn
```
