# EAPState::initialize(void)

- ea: `0x18001c390`
- end: `0x18001c495`
- name: `?initialize@EAPState@@SAXXZ`
- size: `261`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016bcc`

## callees

- `0x180001f26`
- `0x18001c390`
- `0x18002b4a0`

## import_xrefs

- `iassvcs!IASAllocateUniqueID` at `0x18001c44b`
- `iassvcs!IASAllocateUniqueID` at `0x18001c44b`
- `iassvcs!IASGetHostByName` at `0x18001c3fe`
- `iassvcs!IASGetHostByName` at `0x18001c3fe`
- `KERNEL32!GetComputerNameW` at `0x18001c3e1`
- `KERNEL32!GetComputerNameW` at `0x18001c3e1`
- `WS2_32!FreeAddrInfoW` at `0x18001c445`
- `WS2_32!FreeAddrInfoW` at `0x18001c445`

## pseudocode

```c
void EAPState::initialize(void)
{
  unsigned int v0; // esi
  int v1; // eax
  struct addrinfoW *v2; // rdi
  struct sockaddr *ai_addr; // rax
  __int64 v4; // rdx
  ADDRESS_FAMILY sa_family; // bx
  int v6; // eax
  DWORD v7; // [rsp+20h] [rbp-48h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+28h] [rbp-40h] BYREF
  WCHAR v9[16]; // [rsp+30h] [rbp-38h] BYREF

  dword_180040180 = 0;
  invariant = 0;
  *(_DWORD *)((char *)&invariant + 6) = 16791297;
  v0 = 16;
  v7 = 16;
  xmmword_180040170 = 0;
  if ( GetComputerNameW(v9, &v7) )
  {
    pAddrInfo = 0;
    v1 = IASGetHostByName(v9, &pAddrInfo);
    v2 = pAddrInfo;
    if ( v1 >= 0 )
    {
      ai_addr = pAddrInfo->ai_addr;
      v4 = 8;
      sa_family = ai_addr->sa_family;
      if ( ai_addr->sa_family != 23 )
      {
        v0 = 4;
        v4 = 4;
      }
      memcpy_0((char *)&invariant + 12, (char *)ai_addr + v4, v0);
      *(&invariant + 5) = sa_family;
    }
    if ( v2 )
      FreeAddrInfoW(v2);
  }
  v6 = IASAllocateUniqueID();
  HIBYTE(xmmword_180040170) = v6;
  BYTE12(xmmword_180040170) = HIBYTE(v6);
  BYTE13(xmmword_180040170) = BYTE2(v6);
  BYTE14(xmmword_180040170) = BYTE1(v6);
}

```

## disassembly

```asm
0x18001c390  mov     r11, rsp
0x18001c393  mov     [r11+8], rbx
0x18001c397  mov     [r11+10h], rsi
0x18001c39b  push    rdi
0x18001c39c  sub     rsp, 60h
0x18001c3a0  mov     rax, cs:__security_cookie
0x18001c3a7  xor     rax, rsp
0x18001c3aa  mov     [rsp+68h+var_18], rax
0x18001c3af  xor     eax, eax
0x18001c3b1  lea     rdx, [r11-48h]; nSize
0x18001c3b5  xorps   xmm0, xmm0
0x18001c3b8  mov     cs:dword_180040180, eax
0x18001c3be  movups  cs:?invariant@@3ULayout@EAPState@@A, xmm0; EAPState::Layout invariant
0x18001c3c5  lea     rcx, [r11-38h]; lpBuffer
0x18001c3c9  mov     dword ptr cs:?invariant@@3ULayout@EAPState@@A+6, 1003701h; EAPState::Layout invariant
0x18001c3d3  lea     esi, [rax+10h]
0x18001c3d6  mov     [rsp+68h+var_48], esi
0x18001c3da  movups  cs:xmmword_180040170, xmm0
0x18001c3e1  call    cs:__imp_GetComputerNameW
0x18001c3e7  test    eax, eax
0x18001c3e9  jz      short loc_18001C44B
0x18001c3eb  lea     rdx, [rsp+68h+pAddrInfo]
0x18001c3f0  mov     [rsp+68h+pAddrInfo], 0
0x18001c3f9  lea     rcx, [rsp+68h+var_38]
0x18001c3fe  call    cs:__imp_IASGetHostByName
0x18001c404  mov     rdi, [rsp+68h+pAddrInfo]
0x18001c409  test    eax, eax
0x18001c40b  js      short loc_18001C43D
0x18001c40d  mov     rax, [rdi+20h]
0x18001c411  lea     ecx, [rsi-0Ch]
0x18001c414  lea     edx, [rcx+4]
0x18001c417  movzx   ebx, word ptr [rax]
0x18001c41a  cmp     bx, 17h
0x18001c41e  cmovnz  esi, ecx
0x18001c421  cmovnz  edx, ecx
0x18001c424  add     rdx, rax; Src
0x18001c427  lea     rcx, ?invariant@@3ULayout@EAPState@@A+0Ch; void *
0x18001c42e  mov     r8d, esi; Size
0x18001c431  call    memcpy_0
0x18001c436  mov     word ptr cs:?invariant@@3ULayout@EAPState@@A+0Ah, bx; EAPState::Layout invariant
0x18001c43d  test    rdi, rdi
0x18001c440  jz      short loc_18001C44B
0x18001c442  mov     rcx, rdi; pAddrInfo
0x18001c445  call    cs:__imp_FreeAddrInfoW
0x18001c44b  call    cs:__imp_IASAllocateUniqueID
0x18001c451  mov     ecx, eax
0x18001c453  mov     byte ptr cs:xmmword_180040170+0Fh, al
0x18001c459  shr     ecx, 18h
0x18001c45c  mov     byte ptr cs:xmmword_180040170+0Ch, cl
0x18001c462  mov     ecx, eax
0x18001c464  shr     ecx, 10h
0x18001c467  mov     byte ptr cs:xmmword_180040170+0Dh, cl
0x18001c46d  mov     ecx, eax
0x18001c46f  shr     ecx, 8
0x18001c472  mov     byte ptr cs:xmmword_180040170+0Eh, cl
0x18001c478  mov     rcx, [rsp+68h+var_18]
0x18001c47d  xor     rcx, rsp; StackCookie
0x18001c480  call    __security_check_cookie
0x18001c485  mov     rbx, [rsp+68h+arg_0]
0x18001c48a  mov     rsi, [rsp+68h+arg_8]
0x18001c48f  add     rsp, 60h
0x18001c493  pop     rdi
0x18001c494  retn
```
