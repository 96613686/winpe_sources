# CGatherer::UpdateCatalogSignature(void)

- ea: `0x1800c1be8`
- end: `0x1800c1d96`
- name: `?UpdateCatalogSignature@CGatherer@@QEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18007bee0`
- `0x1800cb940`
- `0x1800f4500`

## callees

- `0x180019bb0`
- `0x180061f78`
- `0x18006a040`
- `0x18006a618`
- `0x1800c1be8`
- `0x1801244c0`
- `0x1801c6a88`
- `0x1801c96b8`
- `0x1801c9724`
- `0x1801c9778`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800c1c2c`
- `RPCRT4!UuidCreate` at `0x1800c1c6b`
- `RPCRT4!UuidCreate` at `0x1800c1c2c`
- `RPCRT4!UuidCreate` at `0x1800c1c6b`
- `RPCRT4!UuidToStringW` at `0x1800c1cb9`
- `RPCRT4!UuidToStringW` at `0x1800c1d07`
- `RPCRT4!UuidToStringW` at `0x1800c1cb9`
- `RPCRT4!UuidToStringW` at `0x1800c1d07`
- `RPCRT4!RpcStringFreeW` at `0x1800c1cf2`
- `RPCRT4!RpcStringFreeW` at `0x1800c1d40`
- `RPCRT4!RpcStringFreeW` at `0x1800c1cf2`
- `RPCRT4!RpcStringFreeW` at `0x1800c1d40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGatherer::UpdateCatalogSignature(char *Context)
{
  CSyncReadWrite *v2; // rsi
  RPC_STATUS v3; // eax
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-69h] BYREF
  RPC_WSTR String[3]; // [rsp+28h] [rbp-61h] BYREF
  _BYTE v9[96]; // [rsp+40h] [rbp-49h] BYREF

  v2 = (CSyncReadWrite *)(Context + 1536);
  String[1] = (RPC_WSTR)(Context + 1536);
  CSyncReadWrite::GetWriteAccess((CSyncReadWrite *)(Context + 1536));
  v3 = UuidCreate((UUID *)Context + 262);
  v4 = v3;
  if ( v3 && v3 != 1739 && v3 != 1824 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_6:
    CSyncReadWrite::ReleaseWriteAccess(v2);
    return v4;
  }
  v5 = UuidCreate((UUID *)Context + 261);
  v4 = v5;
  if ( v5 && v5 != 1739 && v5 != 1824 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_6;
  }
  *((_DWORD *)Context + 502) = 0;
  StringUuid = 0;
  if ( !UuidToStringW((const UUID *)Context + 262, &StringUuid) )
  {
    TLMString<32,32,1024>::TLMString<32,32,1024>(v9, StringUuid);
    CGatherer::SetCatalogResetSignature(Context, v9);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v9);
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  String[0] = 0;
  if ( !UuidToStringW((const UUID *)Context + 261, String) )
  {
    TLMString<32,32,1024>::TLMString<32,32,1024>(v9, String[0]);
    CGatherer::SetCheckPointSignature(Context, v9);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(v9);
  }
  if ( String[0] )
    RpcStringFreeW(String);
  v4 = CGatherer::SetCheckPointNumber((CGatherer *)Context, *((_DWORD *)Context + 502));
  if ( (v4 & 0x80000000) == 0 )
    v4 = CGatherer::PushCatalogStatusChange(Context);
  CSyncReadWrite::ReleaseWriteAccess(v2);
  return v4;
}

```

## disassembly

```asm
0x1800c1be8  push    rbp
0x1800c1bea  push    rbx
0x1800c1beb  push    rsi
0x1800c1bec  push    rdi
0x1800c1bed  push    r14
0x1800c1bef  push    r15
0x1800c1bf1  lea     rbp, [rsp-2Fh]
0x1800c1bf6  sub     rsp, 0B8h
0x1800c1bfd  mov     rax, cs:__security_cookie
0x1800c1c04  xor     rax, rsp
0x1800c1c07  mov     [rbp+57h+var_40], rax
0x1800c1c0b  mov     rdi, rcx
0x1800c1c0e  lea     rsi, [rcx+600h]
0x1800c1c15  mov     [rbp+57h+var_B0], rsi
0x1800c1c19  mov     rcx, rsi; this
0x1800c1c1c  call    ?GetWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::GetWriteAccess(void)
0x1800c1c21  nop
0x1800c1c22  lea     r15, [rdi+1060h]
0x1800c1c29  mov     rcx, r15; Uuid
0x1800c1c2c  call    cs:__imp_UuidCreate
0x1800c1c32  mov     ebx, eax
0x1800c1c34  test    eax, eax
0x1800c1c36  jz      short loc_1800C1C61
0x1800c1c38  cmp     eax, 6CBh
0x1800c1c3d  jz      short loc_1800C1C61
0x1800c1c3f  cmp     eax, 720h
0x1800c1c44  jz      short loc_1800C1C61
0x1800c1c46  test    eax, eax
0x1800c1c48  jle     short loc_1800C1C53
0x1800c1c4a  movzx   ebx, ax
0x1800c1c4d  or      ebx, 80070000h
0x1800c1c53  mov     rcx, rsi; this
0x1800c1c56  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800c1c5b  nop
0x1800c1c5c  jmp     loc_1800C1D78
0x1800c1c61  lea     r14, [rdi+1050h]
0x1800c1c68  mov     rcx, r14; Uuid
0x1800c1c6b  call    cs:__imp_UuidCreate
0x1800c1c71  mov     ebx, eax
0x1800c1c73  test    eax, eax
0x1800c1c75  jz      short loc_1800C1CA0
0x1800c1c77  cmp     eax, 6CBh
0x1800c1c7c  jz      short loc_1800C1CA0
0x1800c1c7e  cmp     eax, 720h
0x1800c1c83  jz      short loc_1800C1CA0
0x1800c1c85  test    eax, eax
0x1800c1c87  jle     short loc_1800C1C92
0x1800c1c89  movzx   ebx, ax
0x1800c1c8c  or      ebx, 80070000h
0x1800c1c92  mov     rcx, rsi; this
0x1800c1c95  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800c1c9a  nop
0x1800c1c9b  jmp     loc_1800C1D78
0x1800c1ca0  mov     dword ptr [rdi+7D8h], 0
0x1800c1caa  mov     [rbp+57h+StringUuid], 0
0x1800c1cb2  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x1800c1cb6  mov     rcx, r15; Uuid
0x1800c1cb9  call    cs:__imp_UuidToStringW
0x1800c1cbf  test    eax, eax
0x1800c1cc1  jnz     short loc_1800C1CE7
0x1800c1cc3  mov     rdx, [rbp+57h+StringUuid]
0x1800c1cc7  lea     rcx, [rbp+57h+var_A0]
0x1800c1ccb  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800c1cd0  nop
0x1800c1cd1  lea     rdx, [rbp+57h+var_A0]
0x1800c1cd5  mov     rcx, rdi
0x1800c1cd8  call    ?SetCatalogResetSignature@CGatherer@@QEAAJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CGatherer::SetCatalogResetSignature(TLMString<32,32,1024> const &)
0x1800c1cdd  nop
0x1800c1cde  lea     rcx, [rbp+57h+var_A0]
0x1800c1ce2  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800c1ce7  cmp     [rbp+57h+StringUuid], 0
0x1800c1cec  jz      short loc_1800C1CF8
0x1800c1cee  lea     rcx, [rbp+57h+StringUuid]; String
0x1800c1cf2  call    cs:__imp_RpcStringFreeW
0x1800c1cf8  mov     [rbp+57h+String], 0
0x1800c1d00  lea     rdx, [rbp+57h+String]; StringUuid
0x1800c1d04  mov     rcx, r14; Uuid
0x1800c1d07  call    cs:__imp_UuidToStringW
0x1800c1d0d  test    eax, eax
0x1800c1d0f  jnz     short loc_1800C1D35
0x1800c1d11  mov     rdx, [rbp+57h+String]
0x1800c1d15  lea     rcx, [rbp+57h+var_A0]
0x1800c1d19  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800c1d1e  nop
0x1800c1d1f  lea     rdx, [rbp+57h+var_A0]
0x1800c1d23  mov     rcx, rdi
0x1800c1d26  call    ?SetCheckPointSignature@CGatherer@@QEAAJAEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; CGatherer::SetCheckPointSignature(TLMString<32,32,1024> const &)
0x1800c1d2b  nop
0x1800c1d2c  lea     rcx, [rbp+57h+var_A0]
0x1800c1d30  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x1800c1d35  cmp     [rbp+57h+String], 0
0x1800c1d3a  jz      short loc_1800C1D46
0x1800c1d3c  lea     rcx, [rbp+57h+String]; String
0x1800c1d40  call    cs:__imp_RpcStringFreeW
0x1800c1d46  mov     edx, [rdi+7D8h]; unsigned int
0x1800c1d4c  mov     rcx, rdi; this
0x1800c1d4f  call    ?SetCheckPointNumber@CGatherer@@QEAAJK@Z; CGatherer::SetCheckPointNumber(ulong)
0x1800c1d54  mov     ebx, eax
0x1800c1d56  test    eax, eax
0x1800c1d58  jns     short loc_1800C1D65
0x1800c1d5a  mov     rcx, rsi; this
0x1800c1d5d  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800c1d62  nop
0x1800c1d63  jmp     short loc_1800C1D78
0x1800c1d65  mov     rcx, rdi; Context
0x1800c1d68  call    ?PushCatalogStatusChange@CGatherer@@AEAAJXZ; CGatherer::PushCatalogStatusChange(void)
0x1800c1d6d  mov     ebx, eax
0x1800c1d6f  mov     rcx, rsi; this
0x1800c1d72  call    ?ReleaseWriteAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseWriteAccess(void)
0x1800c1d77  nop
0x1800c1d78  mov     eax, ebx
0x1800c1d7a  mov     rcx, [rbp+57h+var_40]
0x1800c1d7e  xor     rcx, rsp; StackCookie
0x1800c1d81  call    __security_check_cookie
0x1800c1d86  add     rsp, 0B8h
0x1800c1d8d  pop     r15
0x1800c1d8f  pop     r14
0x1800c1d91  pop     rdi
0x1800c1d92  pop     rsi
0x1800c1d93  pop     rbx
0x1800c1d94  pop     rbp
0x1800c1d95  retn
```
