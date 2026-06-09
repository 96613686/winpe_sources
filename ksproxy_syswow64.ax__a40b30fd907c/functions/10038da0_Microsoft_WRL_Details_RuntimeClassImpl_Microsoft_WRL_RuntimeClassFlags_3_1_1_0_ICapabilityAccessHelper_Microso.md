# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x10038da0`
- end: `0x10038e04`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAGJPAKPAPAU_GUID@@@Z`
- size: `100`
- prototype: `int __stdcall(int, _DWORD *, GUID **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10038da0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10038dba`
- `ole32!CoTaskMemAlloc` at `0x10038dba`

## pseudocode

```c
int __stdcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::GetIids(
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
  v3[1] = _GUID_9afc28bc_2422_4a0c_8b57_87ec171ec5e5;
  v3[2] = _GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 3;
  *a3 = v3;
  return 0;
}

```

## disassembly

```asm
0x10038da0  mov     edi, edi
0x10038da2  push    ebp
0x10038da3  mov     ebp, esp
0x10038da5  mov     eax, [ebp+arg_4]
0x10038da8  push    ebx
0x10038da9  mov     ebx, [ebp+arg_8]
0x10038dac  push    30h ; '0'; cb
0x10038dae  mov     dword ptr [ebx], 0
0x10038db4  mov     dword ptr [eax], 0
0x10038dba  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x10038dc0  test    eax, eax
0x10038dc2  jnz     short loc_10038DCB
0x10038dc4  mov     eax, 8007000Eh
0x10038dc9  jmp     short loc_10038DFF
0x10038dcb  push    esi
0x10038dcc  push    edi
0x10038dcd  mov     edi, eax
0x10038dcf  mov     ecx, [ebp+arg_4]
0x10038dd2  mov     esi, offset __GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x10038dd7  movsd
0x10038dd8  movsd
0x10038dd9  movsd
0x10038dda  movsd
0x10038ddb  mov     esi, offset __GUID_9afc28bc_2422_4a0c_8b57_87ec171ec5e5
0x10038de0  lea     edi, [eax+10h]
0x10038de3  movsd
0x10038de4  movsd
0x10038de5  movsd
0x10038de6  movsd
0x10038de7  mov     esi, offset __GUID_00000038_0000_0000_c000_000000000046
0x10038dec  lea     edi, [eax+20h]
0x10038def  movsd
0x10038df0  movsd
0x10038df1  movsd
0x10038df2  movsd
0x10038df3  mov     dword ptr [ecx], 3
0x10038df9  pop     edi
0x10038dfa  mov     [ebx], eax
0x10038dfc  xor     eax, eax
0x10038dfe  pop     esi
0x10038dff  pop     ebx
0x10038e00  pop     ebp
0x10038e01  retn    0Ch
```
