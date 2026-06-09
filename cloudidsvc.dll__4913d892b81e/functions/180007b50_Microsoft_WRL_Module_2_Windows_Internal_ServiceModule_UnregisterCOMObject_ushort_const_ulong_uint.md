# Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180007b50`
- end: `0x180007b93`
- name: `?UnregisterCOMObject@?$Module@$01VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180007b73`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180007b73`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::UnregisterCOMObject(
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
0x180007b50  push    rbx
0x180007b52  push    rbp
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  sub     rsp, 28h
0x180007b59  xor     eax, eax
0x180007b5b  xor     ebx, ebx
0x180007b5d  mov     ebp, r9d
0x180007b60  mov     rsi, r8
0x180007b63  test    r9d, r9d
0x180007b66  jz      short loc_180007B8A
0x180007b68  test    eax, eax
0x180007b6a  js      short loc_180007B8A
0x180007b6c  mov     ecx, [rsi+rbx*4]; dwRegister
0x180007b6f  test    ecx, ecx
0x180007b71  jz      short loc_180007B84
0x180007b73  call    cs:__imp_CoRevokeClassObject
0x180007b79  test    eax, eax
0x180007b7b  js      short loc_180007B84
0x180007b7d  mov     dword ptr [rsi+rbx*4], 0
0x180007b84  inc     ebx
0x180007b86  cmp     ebx, ebp
0x180007b88  jb      short loc_180007B68
0x180007b8a  add     rsp, 28h
0x180007b8e  pop     rdi
0x180007b8f  pop     rsi
0x180007b90  pop     rbp
0x180007b91  pop     rbx
0x180007b92  retn
```
