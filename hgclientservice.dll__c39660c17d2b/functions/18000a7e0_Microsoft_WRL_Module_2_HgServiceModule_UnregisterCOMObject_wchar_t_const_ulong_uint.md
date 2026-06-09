# Microsoft::WRL::Module<2,HgServiceModule>::UnregisterCOMObject(wchar_t const *,ulong *,uint)

- ea: `0x18000a7e0`
- end: `0x18000a823`
- name: `?UnregisterCOMObject@?$Module@$01VHgServiceModule@@@WRL@Microsoft@@UEAAJPEB_WPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a7e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000a803`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18000a803`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,HgServiceModule>::UnregisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT result; // eax
  __int64 i; // rbx
  DWORD v8; // ecx

  result = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( result < 0 )
      break;
    v8 = *(_DWORD *)(a3 + 4 * i);
    if ( v8 )
    {
      result = CoRevokeClassObject(v8);
      if ( result >= 0 )
        *(_DWORD *)(a3 + 4 * i) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a7e0  push    rbx
0x18000a7e2  push    rbp
0x18000a7e3  push    rsi
0x18000a7e4  push    rdi
0x18000a7e5  sub     rsp, 28h
0x18000a7e9  xor     eax, eax
0x18000a7eb  xor     ebx, ebx
0x18000a7ed  mov     ebp, r9d
0x18000a7f0  mov     rsi, r8
0x18000a7f3  test    r9d, r9d
0x18000a7f6  jz      short loc_18000A81A
0x18000a7f8  test    eax, eax
0x18000a7fa  js      short loc_18000A81A
0x18000a7fc  mov     ecx, [rsi+rbx*4]; dwRegister
0x18000a7ff  test    ecx, ecx
0x18000a801  jz      short loc_18000A814
0x18000a803  call    cs:__imp_CoRevokeClassObject
0x18000a809  test    eax, eax
0x18000a80b  js      short loc_18000A814
0x18000a80d  mov     dword ptr [rsi+rbx*4], 0
0x18000a814  inc     ebx
0x18000a816  cmp     ebx, ebp
0x18000a818  jb      short loc_18000A7F8
0x18000a81a  add     rsp, 28h
0x18000a81e  pop     rdi
0x18000a81f  pop     rsi
0x18000a820  pop     rbp
0x18000a821  pop     rbx
0x18000a822  retn
```
