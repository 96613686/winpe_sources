# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x10038b30`
- end: `0x10038b94`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioStateMonitorHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGJPAKPAPAU_GUID@@@Z`
- size: `100`
- prototype: `int __stdcall(int, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10038b30`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10038b4a`
- `ole32!CoTaskMemAlloc` at `0x10038b4a`

## pseudocode

```c
int __stdcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::GetIids(
        int a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v3; // eax

  *a3 = 0;
  *a2 = 0;
  v3 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v3 )
    return -2147024882;
  *v3 = _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v3[1] = _GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3;
  v3[2] = _GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v3;
  return 0;
}

```

## disassembly

```asm
0x10038b30  mov     edi, edi
0x10038b32  push    ebp
0x10038b33  mov     ebp, esp
0x10038b35  mov     eax, [ebp+arg_4]
0x10038b38  push    ebx
0x10038b39  mov     ebx, [ebp+arg_8]
0x10038b3c  push    30h ; '0'; cb
0x10038b3e  mov     dword ptr [ebx], 0
0x10038b44  mov     dword ptr [eax], 0
0x10038b4a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10038b50  test    eax, eax
0x10038b52  jnz     short loc_10038B5B
0x10038b54  mov     eax, 8007000Eh
0x10038b59  jmp     short loc_10038B8F
0x10038b5b  push    esi
0x10038b5c  push    edi
0x10038b5d  mov     edi, eax
0x10038b5f  mov     ecx, [ebp+arg_4]
0x10038b62  mov     esi, offset __GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x10038b67  movsd
0x10038b68  movsd
0x10038b69  movsd
0x10038b6a  movsd
0x10038b6b  mov     esi, offset __GUID_91699f56_52b5_4f6c_8e19_4ec35f8818c3
0x10038b70  lea     edi, [eax+10h]
0x10038b73  movsd
0x10038b74  movsd
0x10038b75  movsd
0x10038b76  movsd
0x10038b77  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x10038b7c  lea     edi, [eax+20h]
0x10038b7f  movsd
0x10038b80  movsd
0x10038b81  movsd
0x10038b82  movsd
0x10038b83  mov     dword ptr [ecx], 3
0x10038b89  pop     edi
0x10038b8a  mov     [ebx], eax
0x10038b8c  xor     eax, eax
0x10038b8e  pop     esi
0x10038b8f  pop     ebx
0x10038b90  pop     ebp
0x10038b91  retn    0Ch
```
