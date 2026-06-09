# CDims::p_IsNetConnected(void)

- ea: `0x1800021c0`
- end: `0x180002267`
- name: `?p_IsNetConnected@CDims@@AEAA_NXZ`
- size: `167`
- prototype: `bool __fastcall(CDims *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800078e0`

## callees

- `0x1800021c0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800021e1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800021e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000223b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000223b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000225f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000225f`

## pseudocode

```c
bool __fastcall CDims::p_IsNetConnected(CDims *this)
{
  HRESULT v1; // eax
  char v2; // bl
  CDims *v4; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v4 = this;
  ppv = 0;
  LOWORD(v4) = -1;
  v1 = CoInitializeEx(0, 0);
  if ( v1 >= 0 )
  {
    v2 = 1;
  }
  else
  {
    v2 = 0;
    if ( v1 != -2147417850 )
      goto LABEL_3;
  }
  if ( !CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv) )
    (*(void (__fastcall **)(LPVOID, CDims **))(*(_QWORD *)ppv + 96LL))(ppv, &v4);
  if ( v2 )
    CoUninitialize();
LABEL_3:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (_WORD)v4 == 0xFFFF;
}

```

## disassembly

```asm
0x1800021c0  mov     [rsp+arg_0], rcx
0x1800021c5  push    rbx
0x1800021c6  sub     rsp, 30h
0x1800021ca  mov     [rsp+38h+arg_8], 0
0x1800021d3  mov     eax, 0FFFFFFFFh
0x1800021d8  mov     word ptr [rsp+38h+arg_0], ax
0x1800021dd  xor     edx, edx; dwCoInit
0x1800021df  xor     ecx, ecx; pvReserved
0x1800021e1  call    cs:__imp_CoInitializeEx
0x1800021e7  test    eax, eax
0x1800021e9  jns     short loc_180002219
0x1800021eb  xor     bl, bl
0x1800021ed  cmp     eax, 80010106h
0x1800021f2  jz      short loc_18000221B
0x1800021f4  mov     rcx, [rsp+38h+arg_8]
0x1800021f9  test    rcx, rcx
0x1800021fc  jz      short loc_18000220A
0x1800021fe  mov     rax, [rcx]
0x180002201  mov     rax, [rax+10h]
0x180002205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220a  cmp     word ptr [rsp+38h+arg_0], 0FFFFh
0x180002210  setz    al
0x180002213  add     rsp, 30h
0x180002217  pop     rbx
0x180002218  retn
0x180002219  mov     bl, 1
0x18000221b  lea     rax, [rsp+38h+arg_8]
0x180002220  mov     [rsp+38h+ppv], rax; ppv
0x180002225  lea     r9, IID_INetworkListManager; riid
0x18000222c  xor     edx, edx; pUnkOuter
0x18000222e  mov     r8d, 1; dwClsContext
0x180002234  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000223b  call    cs:__imp_CoCreateInstance
0x180002241  test    eax, eax
0x180002243  jnz     short loc_18000225B
0x180002245  mov     rcx, [rsp+38h+arg_8]
0x18000224a  mov     rax, [rcx]
0x18000224d  lea     rdx, [rsp+38h+arg_0]
0x180002252  mov     rax, [rax+60h]
0x180002256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225b  test    bl, bl
0x18000225d  jz      short loc_1800021F4
0x18000225f  call    cs:__imp_CoUninitialize
0x180002265  jmp     short loc_1800021F4
```
