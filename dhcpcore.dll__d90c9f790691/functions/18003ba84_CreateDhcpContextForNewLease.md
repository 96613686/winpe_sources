# CreateDhcpContextForNewLease

- ea: `0x18003ba84`
- end: `0x18003bcca`
- name: `CreateDhcpContextForNewLease`
- size: `582`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int *, int, __int64, int, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003c064`
- `0x18003c9d8`

## callees

- `0x180002534`
- `0x1800077ac`
- `0x18000f3e0`
- `0x180012b90`
- `0x1800188bc`
- `0x18003b988`
- `0x18003ba84`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `WS2_32!__imp_inet_addr` at `0x18003bbb0`
- `WS2_32!__imp_inet_addr` at `0x18003bbc3`
- `WS2_32!__imp_inet_addr` at `0x18003bbb0`
- `WS2_32!__imp_inet_addr` at `0x18003bbc3`

## pseudocode

```c
__int64 __fastcall CreateDhcpContextForNewLease(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3,
        int a4,
        __int64 a5,
        int a6,
        void *Src,
        size_t Size)
{
  unsigned int DhcpContext; // eax
  __int64 v12; // rbx
  unsigned int ClientId; // edi
  int Seed; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  _QWORD v19[9]; // [rsp+20h] [rbp-48h] BYREF

  v19[0] = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 13, WPP_c84194e7b785338e3b207dae288fd792_Traceguids);
  *a1 = 0;
  DhcpContext = CreateDhcpContext(v19, Size);
  v12 = v19[0];
  ClientId = DhcpContext;
  if ( !DhcpContext )
  {
    *(_BYTE *)(v19[0] + 84LL) = 1;
    *(_DWORD *)(v12 + 96) = Size;
    *(_DWORD *)(v12 + 16) = 1;
    memcpy_0(*(void **)(v12 + 88), Src, (unsigned int)Size);
    *(_DWORD *)(v12 + 840) = 0;
    *(_DWORD *)(v12 + 120) = 0;
    *(_DWORD *)(v12 + 124) = DhcpDefaultSubnetMask(0);
    *(_DWORD *)(v12 + 128) = -1;
    *(_DWORD *)(v12 + 132) = a4;
    *(_DWORD *)(v12 + 440) = 0;
    *(_QWORD *)(v12 + 448) = 0;
    *(_QWORD *)(v12 + 456) = 0;
    *(_QWORD *)(v12 + 464) = 0;
    *(_QWORD *)(v12 + 472) = 0;
    *(_DWORD *)(v12 + 844) = 1;
    *(_QWORD *)(v12 + 848) = 1;
    *(_DWORD *)(v12 + 580) = 0;
    *(_DWORD *)(v12 + 776) = 0;
    *(_DWORD *)(v12 + 784) = 0;
    *(_DWORD *)(v12 + 788) = 0;
    *(_DWORD *)(v12 + 792) = 1;
    *(_DWORD *)(v12 + 796) = 0;
    *(_DWORD *)(v12 + 800) = 0;
    *(_DWORD *)(v12 + 784) = 1;
    *(_DWORD *)(v12 + 816) = 1;
    *(_DWORD *)(v12 + 416) = 0;
    *(_DWORD *)(v12 + 420) = inet_addr("169.254.0.0");
    *(_DWORD *)(v12 + 424) = inet_addr("255.255.0.0");
    Seed = GetSeed();
    LOBYTE(v15) = 1;
    *(_DWORD *)(v12 + 428) = Seed;
    v16 = a5 + 4;
    *(_QWORD *)(v12 + 704) = v12 + 696;
    *(_QWORD *)(v12 + 696) = v12 + 696;
    if ( !a6 )
      v16 = 0;
    *(_QWORD *)(v12 + 688) = v12 + 680;
    *(_QWORD *)(v12 + 680) = v12 + 680;
    *(_QWORD *)(v12 + 720) = v12 + 712;
    *(_QWORD *)(v12 + 712) = v12 + 712;
    *(_QWORD *)(v12 + 736) = v16;
    v17 = *a3;
    *(_DWORD *)(v12 + 744) = a6;
    ClientId = DhcpMakeClientId(v15, v17, (char *)a3 + 5, v12 + 432);
    if ( !ClientId )
    {
      *(_QWORD *)(v12 + 56) = 0;
      *(_QWORD *)(v12 + 72) = -1;
      *(_QWORD *)(v12 + 64) = -1;
      if ( g_fUseIpv6OnlyPreferred )
        *(_DWORD *)(v12 + 2168) = DhcpIsIpv6OnlyPreferred();
      *a1 = v12;
      v12 = 0;
    }
  }
  if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 16), 0xFFFFFFFF) == 1 )
    DhcpDestroyContextEx(v12);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 14, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, ClientId);
  return ClientId;
}

```

## disassembly

```asm
0x18003ba84  mov     [rsp+arg_8], rbx
0x18003ba89  push    rbp
0x18003ba8a  push    rsi
0x18003ba8b  push    rdi
0x18003ba8c  push    r12
0x18003ba8e  push    r13
0x18003ba90  push    r14
0x18003ba92  push    r15
0x18003ba94  sub     rsp, 30h
0x18003ba98  mov     r12, [rsp+68h+Src]
0x18003baa0  xor     r13d, r13d
0x18003baa3  mov     [rsp+68h+var_48], r13
0x18003baa8  mov     r15d, r9d
0x18003baab  mov     r14, r8
0x18003baae  mov     rsi, rcx
0x18003bab1  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003bab8  jz      short loc_18003BACF
0x18003baba  lea     edx, [r13+0Dh]
0x18003babe  mov     ecx, 404h
0x18003bac3  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003baca  call    WPP_SF_
0x18003bacf  mov     ebp, dword ptr [rsp+68h+Size]
0x18003bad6  lea     rcx, [rsp+68h+var_48]
0x18003badb  mov     edx, ebp
0x18003badd  mov     [rsi], r13
0x18003bae0  call    CreateDhcpContext
0x18003bae5  mov     rbx, [rsp+68h+var_48]
0x18003baea  mov     edi, eax
0x18003baec  test    eax, eax
0x18003baee  jnz     loc_18003BC77
0x18003baf4  lea     edi, [rax+1]
0x18003baf7  mov     r8d, ebp; Size
0x18003bafa  mov     [rbx+54h], dil
0x18003bafe  mov     rdx, r12; Src
0x18003bb01  mov     [rbx+60h], ebp
0x18003bb04  mov     [rbx+10h], edi
0x18003bb07  mov     rcx, [rbx+58h]; void *
0x18003bb0b  call    memcpy_0
0x18003bb10  xor     ecx, ecx
0x18003bb12  mov     [rbx+348h], r13d
0x18003bb19  mov     [rbx+78h], r13d
0x18003bb1d  call    DhcpDefaultSubnetMask
0x18003bb22  mov     [rbx+7Ch], eax
0x18003bb25  lea     rcx, cp; "169.254.0.0"
0x18003bb2c  mov     dword ptr [rbx+80h], 0FFFFFFFFh
0x18003bb36  mov     [rbx+84h], r15d
0x18003bb3d  mov     [rbx+1B8h], r13d
0x18003bb44  mov     [rbx+1C0h], r13
0x18003bb4b  mov     [rbx+1C8h], r13
0x18003bb52  mov     [rbx+1D0h], r13
0x18003bb59  mov     [rbx+1D8h], r13
0x18003bb60  mov     [rbx+34Ch], edi
0x18003bb66  mov     [rbx+350h], rdi
0x18003bb6d  mov     [rbx+244h], r13d
0x18003bb74  mov     [rbx+308h], r13d
0x18003bb7b  mov     [rbx+310h], r13d
0x18003bb82  mov     [rbx+314h], r13d
0x18003bb89  mov     [rbx+318h], edi
0x18003bb8f  mov     [rbx+31Ch], r13d
0x18003bb96  mov     [rbx+320h], r13d
0x18003bb9d  mov     [rbx+310h], edi
0x18003bba3  mov     [rbx+330h], edi
0x18003bba9  mov     [rbx+1A0h], r13d
0x18003bbb0  call    cs:__imp_inet_addr
0x18003bbb6  lea     rcx, a25525500; "255.255.0.0"
0x18003bbbd  mov     [rbx+1A4h], eax
0x18003bbc3  call    cs:__imp_inet_addr
0x18003bbc9  mov     [rbx+1A8h], eax
0x18003bbcf  call    GetSeed
0x18003bbd4  mov     r8d, [rsp+68h+arg_28]
0x18003bbdc  lea     r9, [rbx+1B0h]
0x18003bbe3  mov     rdx, [rsp+68h+arg_20]
0x18003bbeb  mov     cl, dil
0x18003bbee  mov     [rbx+1ACh], eax
0x18003bbf4  add     rdx, 4
0x18003bbf8  lea     rax, [rbx+2B8h]
0x18003bbff  test    r8d, r8d
0x18003bc02  mov     [rax+8], rax
0x18003bc06  mov     [rax], rax
0x18003bc09  cmovz   rdx, r13
0x18003bc0d  lea     rax, [rbx+2A8h]
0x18003bc14  mov     [rax+8], rax
0x18003bc18  mov     [rax], rax
0x18003bc1b  lea     rax, [rbx+2C8h]
0x18003bc22  mov     [rax+8], rax
0x18003bc26  mov     [rax], rax
0x18003bc29  mov     [rbx+2E0h], rdx
0x18003bc30  mov     edx, [r14]
0x18003bc33  mov     [rbx+2E8h], r8d
0x18003bc3a  lea     r8, [r14+5]
0x18003bc3e  call    DhcpMakeClientId
0x18003bc43  mov     edi, eax
0x18003bc45  test    eax, eax
0x18003bc47  jnz     short loc_18003BC77
0x18003bc49  mov     [rbx+38h], r13
0x18003bc4d  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x18003bc55  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18003bc5d  cmp     cs:g_fUseIpv6OnlyPreferred, r13d
0x18003bc64  jz      short loc_18003BC71
0x18003bc66  call    DhcpIsIpv6OnlyPreferred
0x18003bc6b  mov     [rbx+878h], eax
0x18003bc71  mov     [rsi], rbx
0x18003bc74  mov     rbx, r13
0x18003bc77  test    rbx, rbx
0x18003bc7a  jz      short loc_18003BC91
0x18003bc7c  or      eax, 0FFFFFFFFh
0x18003bc7f  lock xadd [rbx+10h], eax
0x18003bc84  cmp     eax, 1
0x18003bc87  jnz     short loc_18003BC91
0x18003bc89  mov     rcx, rbx
0x18003bc8c  call    DhcpDestroyContextEx
0x18003bc91  test    byte ptr cs:xmmword_1800616A0, 10h
0x18003bc98  jz      short loc_18003BCB3
0x18003bc9a  mov     edx, 0Eh
0x18003bc9f  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003bca6  mov     ecx, 404h
0x18003bcab  mov     r9d, edi
0x18003bcae  call    WPP_SF_D
0x18003bcb3  mov     rbx, [rsp+68h+arg_8]
0x18003bcb8  mov     eax, edi
0x18003bcba  add     rsp, 30h
0x18003bcbe  pop     r15
0x18003bcc0  pop     r14
0x18003bcc2  pop     r13
0x18003bcc4  pop     r12
0x18003bcc6  pop     rdi
0x18003bcc7  pop     rsi
0x18003bcc8  pop     rbp
0x18003bcc9  retn
```
