# SetOneXAuthCredsInfo

- ea: `0x18001bdb0`
- end: `0x18001be82`
- name: `SetOneXAuthCredsInfo`
- size: `210`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800230c0`
- `0x180028cb8`
- `0x180029668`

## callees

- `0x18001bdb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bdda`
- `MobileNetworking!FreeMemory` at `0x18001be04`
- `MobileNetworking!FreeMemory` at `0x18001be34`
- `MobileNetworking!FreeMemory` at `0x18001be60`
- `MobileNetworking!FreeMemory` at `0x18001be04`
- `MobileNetworking!FreeMemory` at `0x18001be34`
- `MobileNetworking!FreeMemory` at `0x18001be60`

## string_xrefs

- `0x18001bdfa`: `SetUserTokenInfo`

## pseudocode

```c
__int64 __fastcall SetOneXAuthCredsInfo(__int64 a1, int a2, __int64 a3, __int64 a4, int a5, __int64 a6, __int64 a7)
{
  void *v8; // rcx
  bool v11; // zf
  __int64 result; // rax

  *(_DWORD *)(a1 + 444) = a2;
  v8 = *(void **)(a1 + 456);
  if ( v8 )
    CloseHandle(v8);
  *(_QWORD *)(a1 + 456) = a3;
  if ( *(_QWORD *)(a1 + 464) )
    FreeMemory(a1 + 464, "SetUserTokenInfo", 147);
  *(_QWORD *)(a1 + 464) = a4;
  v11 = *(_QWORD *)(a1 + 472) == 0;
  *(_DWORD *)(a1 + 448) = a5;
  if ( !v11 )
    FreeMemory(a1 + 472, "SetUserName", 156);
  v11 = *(_QWORD *)(a1 + 480) == 0;
  *(_QWORD *)(a1 + 472) = a6;
  if ( !v11 )
    FreeMemory(a1 + 480, "SetDomainName", 170);
  result = a7;
  *(_QWORD *)(a1 + 480) = a7;
  return result;
}

```

## disassembly

```asm
0x18001bdb0  mov     [rsp+arg_0], rbx
0x18001bdb5  mov     [rsp+arg_8], rsi
0x18001bdba  push    rdi
0x18001bdbb  sub     rsp, 20h
0x18001bdbf  mov     rbx, rcx
0x18001bdc2  mov     [rcx+1BCh], edx
0x18001bdc8  mov     rcx, [rcx+1C8h]; hObject
0x18001bdcf  mov     rsi, r9
0x18001bdd2  mov     rdi, r8
0x18001bdd5  test    rcx, rcx
0x18001bdd8  jz      short loc_18001BDE0
0x18001bdda  call    cs:__imp_CloseHandle
0x18001bde0  mov     [rbx+1C8h], rdi
0x18001bde7  lea     rdi, [rbx+1D0h]
0x18001bdee  cmp     qword ptr [rdi], 0
0x18001bdf2  jz      short loc_18001BE0A
0x18001bdf4  mov     r8d, 93h
0x18001bdfa  lea     rdx, aSetusertokenin; "SetUserTokenInfo"
0x18001be01  mov     rcx, rdi
0x18001be04  call    cs:__imp_FreeMemory
0x18001be0a  mov     eax, [rsp+28h+arg_20]
0x18001be0e  mov     [rdi], rsi
0x18001be11  lea     rdi, [rbx+1D8h]
0x18001be18  cmp     qword ptr [rdi], 0
0x18001be1c  mov     [rbx+1C0h], eax
0x18001be22  jz      short loc_18001BE3A
0x18001be24  mov     r8d, 9Ch
0x18001be2a  lea     rdx, aSetusername; "SetUserName"
0x18001be31  mov     rcx, rdi
0x18001be34  call    cs:__imp_FreeMemory
0x18001be3a  cmp     qword ptr [rbx+1E0h], 0
0x18001be42  mov     rax, [rsp+28h+arg_28]
0x18001be47  mov     [rdi], rax
0x18001be4a  jz      short loc_18001BE66
0x18001be4c  mov     r8d, 0AAh
0x18001be52  lea     rdx, aSetdomainname; "SetDomainName"
0x18001be59  lea     rcx, [rbx+1E0h]
0x18001be60  call    cs:__imp_FreeMemory
0x18001be66  mov     rax, [rsp+28h+arg_30]
0x18001be6b  mov     rsi, [rsp+28h+arg_8]
0x18001be70  mov     [rbx+1E0h], rax
0x18001be77  mov     rbx, [rsp+28h+arg_0]
0x18001be7c  add     rsp, 20h
0x18001be80  pop     rdi
0x18001be81  retn
```
