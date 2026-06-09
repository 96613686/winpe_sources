# GetNetType(ushort const *,ulong *)

- ea: `0x1800030d0`
- end: `0x1800031e8`
- name: `?GetNetType@@YAHPEBGPEAK@Z`
- size: `280`
- prototype: `__int64 __fastcall(WCHAR *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001f10`

## callees

- `0x1800030d0`
- `0x180005721`
- `0x180005750`

## import_xrefs

- `MPR!WNetGetResourceInformationW` at `0x180003151`
- `MPR!WNetGetResourceInformationW` at `0x180003151`
- `MPR!WNetGetNetworkInformationW` at `0x18000319e`
- `MPR!WNetGetNetworkInformationW` at `0x18000319e`

## pseudocode

```c
__int64 __fastcall GetNetType(WCHAR *a1, unsigned int *a2)
{
  __int64 result; // rax
  DWORD cbBuffer; // [rsp+20h] [rbp-298h] BYREF
  LPWSTR lpSystem; // [rsp+28h] [rbp-290h] BYREF
  _NETRESOURCEW NetResource; // [rsp+30h] [rbp-288h] BYREF
  _BYTE Buffer[40]; // [rsp+60h] [rbp-258h] BYREF
  LPCWSTR lpProvider; // [rsp+88h] [rbp-230h]
  _NETINFOSTRUCT NetInfoStruct; // [rsp+270h] [rbp-48h] BYREF

  NetResource.dwScope = 0;
  *(_OWORD *)&NetResource.dwDisplayType = 0;
  *(_OWORD *)&NetResource.lpComment = 0;
  memset_0(Buffer, 0, 0x208u);
  cbBuffer = 520;
  lpSystem = 0;
  NetResource.lpRemoteName = a1;
  NetResource.dwType = 1;
  if ( WNetGetResourceInformationW(&NetResource, Buffer, &cbBuffer, &lpSystem) )
    return 0;
  if ( !lpProvider )
    return 0;
  memset(&NetInfoStruct, 0, sizeof(NetInfoStruct));
  NetInfoStruct.cbStructure = 40;
  if ( WNetGetNetworkInformationW(lpProvider, &NetInfoStruct) )
    return 0;
  result = 1;
  *a2 = NetInfoStruct.wNetType << 16;
  return result;
}

```

## disassembly

```asm
0x1800030d0  mov     [rsp+arg_10], rbx
0x1800030d5  push    rbp
0x1800030d6  push    rsi
0x1800030d7  push    rdi
0x1800030d8  sub     rsp, 2A0h
0x1800030df  mov     rax, cs:__security_cookie
0x1800030e6  xor     rax, rsp
0x1800030e9  mov     [rsp+2B8h+var_20], rax
0x1800030f1  mov     rsi, rdx
0x1800030f4  mov     rdi, rcx
0x1800030f7  xor     ebp, ebp
0x1800030f9  lea     rcx, [rsp+2B8h+Buffer]; void *
0x1800030fe  xorps   xmm0, xmm0
0x180003101  mov     [rsp+2B8h+NetResource.dwScope], ebp
0x180003105  xorps   xmm1, xmm1
0x180003108  xor     edx, edx; Val
0x18000310a  mov     r8d, 208h; Size
0x180003110  mov     ebx, ebp
0x180003112  movdqu  xmmword ptr [rsp+2B8h+NetResource.dwDisplayType], xmm0
0x180003118  movdqu  xmmword ptr [rsp+2B8h+NetResource.lpComment], xmm1
0x18000311e  call    memset_0
0x180003123  lea     r9, [rsp+2B8h+lpSystem]; lplpSystem
0x180003128  mov     [rsp+2B8h+cbBuffer], 208h
0x180003130  lea     r8, [rsp+2B8h+cbBuffer]; lpcbBuffer
0x180003135  mov     [rsp+2B8h+lpSystem], rbp
0x18000313a  lea     rdx, [rsp+2B8h+Buffer]; lpBuffer
0x18000313f  mov     [rsp+2B8h+NetResource.lpRemoteName], rdi
0x180003144  lea     rcx, [rsp+2B8h+NetResource]; lpNetResource
0x180003149  mov     [rsp+2B8h+NetResource.dwType], 1
0x180003151  call    cs:__imp_WNetGetResourceInformationW
0x180003158  nop     dword ptr [rax+rax+00h]
0x18000315d  test    eax, eax
0x18000315f  jnz     short loc_1800031C2
0x180003161  mov     rcx, [rsp+2B8h+lpProvider]; lpProvider
0x180003169  test    rcx, rcx
0x18000316c  jz      short loc_1800031C2
0x18000316e  xor     edx, edx
0x180003170  xorps   xmm0, xmm0
0x180003173  mov     qword ptr [rsp+2B8h+NetInfoStruct.dwDrives], rdx
0x18000317b  lea     rdx, [rsp+2B8h+NetInfoStruct]; lpNetInfoStruct
0x180003183  movups  xmmword ptr [rsp+2B8h+NetInfoStruct.cbStructure], xmm0
0x18000318b  mov     [rsp+2B8h+NetInfoStruct.cbStructure], 28h ; '('
0x180003196  movups  xmmword ptr [rsp+2B8h+NetInfoStruct.dwHandle], xmm0
0x18000319e  call    cs:__imp_WNetGetNetworkInformationW
0x1800031a5  nop     dword ptr [rax+rax+00h]
0x1800031aa  test    eax, eax
0x1800031ac  jnz     short loc_1800031C2
0x1800031ae  movzx   ecx, [rsp+2B8h+NetInfoStruct.wNetType]
0x1800031b6  mov     eax, 1
0x1800031bb  shl     ecx, 10h
0x1800031be  mov     [rsi], ecx
0x1800031c0  jmp     short loc_1800031C4
0x1800031c2  mov     eax, ebx
0x1800031c4  mov     rcx, [rsp+2B8h+var_20]
0x1800031cc  xor     rcx, rsp; StackCookie
0x1800031cf  call    __security_check_cookie
0x1800031d4  mov     rbx, [rsp+2B8h+arg_10]
0x1800031dc  add     rsp, 2A0h
0x1800031e3  pop     rdi
0x1800031e4  pop     rsi
0x1800031e5  pop     rbp
0x1800031e6  retn
```
