# Pku2uBuildHostAddresses(PKERB_HOST_ADDRESSES * *)

- ea: `0x180010ea4`
- end: `0x180011057`
- name: `?Pku2uBuildHostAddresses@@YAJPEAPEAUPKERB_HOST_ADDRESSES@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct PKERB_HOST_ADDRESSES **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fc70`

## callees

- `0x1800057f0`
- `0x180010ea4`
- `0x180011a20`
- `0x180018870`
- `0x1800210f0`
- `0x180021a54`
- `0x180023ce0`
- `0x180044f8c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010f0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180010f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f30`
- `ntdll!RtlInitUnicodeString` at `0x180010f67`
- `ntdll!RtlInitUnicodeString` at `0x180010f67`

## pseudocode

```c
__int64 __fastcall Pku2uBuildHostAddresses(struct PKERB_HOST_ADDRESSES **a1)
{
  _DWORD *v2; // rdi
  DWORD LastError; // eax
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  basessp::BaseSSP *v6; // rcx
  void *v7; // rax
  __int64 v8; // rbx
  void *v9; // rcx
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  void *Src[2]; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  nSize = 256;
  DestinationString = 0;
  *(_OWORD *)Src = 0;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_145765ada38d35d83bd68130d412160b_Traceguids, LastError);
    }
    goto LABEL_5;
  }
  RtlInitUnicodeString(&DestinationString, Buffer);
  if ( (unsigned int)KerbUnicodeStringToKerbString((struct _STRING *)Src, &DestinationString) )
  {
LABEL_5:
    v4 = -1073741670;
    goto LABEL_13;
  }
  if ( LOWORD(Src[0]) < 0x10u )
  {
    v5 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 0x20u);
    v2 = v5;
    if ( !v5
      || (v6 = Pku2uGlobalBaseSSP,
          v5[2] = 20,
          v5[4] = 16,
          v7 = basessp::BaseSSP::WSTAllocate(v6, 0x10u),
          (*((_QWORD *)v2 + 3) = v7) == 0) )
    {
      v4 = -1073741801;
      goto LABEL_13;
    }
    v8 = LOWORD(Src[0]);
    memcpy_0(v7, Src[1], LOWORD(Src[0]));
    memset_0((void *)(v8 + *((_QWORD *)v2 + 3)), 32, 16 - v8);
    *(_QWORD *)v2 = 0;
  }
  v4 = 0;
  *a1 = (struct PKERB_HOST_ADDRESSES *)v2;
  v2 = 0;
LABEL_13:
  if ( Src[1] )
    Pku2uFree(Src[1]);
  if ( v2 )
  {
    v9 = (void *)*((_QWORD *)v2 + 3);
    if ( v9 )
      Pku2uFree(v9);
    Pku2uFree(v2);
  }
  return v4;
}

```

## disassembly

```asm
0x180010ea4  mov     [rsp-8+arg_8], rbx
0x180010ea9  mov     [rsp-8+arg_10], rsi
0x180010eae  push    rbp
0x180010eaf  push    rdi
0x180010eb0  push    r14
0x180010eb2  lea     rbp, [rsp-160h]
0x180010eba  sub     rsp, 260h
0x180010ec1  mov     rax, cs:__security_cookie
0x180010ec8  xor     rax, rsp
0x180010ecb  mov     [rbp+170h+var_20], rax
0x180010ed2  mov     r14, rcx
0x180010ed5  xor     edx, edx; Val
0x180010ed7  lea     rcx, [rsp+270h+Buffer]; void *
0x180010edc  mov     r8d, 200h; Size
0x180010ee2  xor     edi, edi
0x180010ee4  call    memset_0
0x180010ee9  xorps   xmm0, xmm0
0x180010eec  mov     [rsp+270h+nSize], 100h
0x180010ef4  xorps   xmm1, xmm1
0x180010ef7  lea     r8, [rsp+270h+nSize]; nSize
0x180010efc  lea     rdx, [rsp+270h+Buffer]; lpBuffer
0x180010f01  xor     ecx, ecx; NameType
0x180010f03  movups  xmmword ptr [rsp+270h+DestinationString.Length], xmm0
0x180010f08  movups  xmmword ptr [rsp+270h+Src], xmm1
0x180010f0d  call    cs:__imp_GetComputerNameExW
0x180010f13  test    eax, eax
0x180010f15  jnz     short loc_180010F5D
0x180010f17  mov     rax, cs:WPP_GLOBAL_Control
0x180010f1e  lea     rcx, WPP_GLOBAL_Control
0x180010f25  cmp     rax, rcx
0x180010f28  jz      short loc_180010F53
0x180010f2a  test    byte ptr [rax+1Ch], 2
0x180010f2e  jz      short loc_180010F53
0x180010f30  call    cs:__imp_GetLastError
0x180010f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f3d  lea     edx, [rdi+0Dh]
0x180010f40  mov     r9d, eax
0x180010f43  lea     r8, WPP_145765ada38d35d83bd68130d412160b_Traceguids
0x180010f4a  mov     rcx, [rcx+10h]
0x180010f4e  call    WPP_SF_d
0x180010f53  mov     ebx, 0C000009Ah
0x180010f58  jmp     loc_180011004
0x180010f5d  lea     rdx, [rsp+270h+Buffer]; SourceString
0x180010f62  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x180010f67  call    cs:__imp_RtlInitUnicodeString
0x180010f6d  lea     rdx, [rsp+270h+DestinationString]; struct _UNICODE_STRING *
0x180010f72  lea     rcx, [rsp+270h+Src]; struct _STRING *
0x180010f77  call    ?KerbUnicodeStringToKerbString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z; KerbUnicodeStringToKerbString(_STRING *,_UNICODE_STRING *)
0x180010f7c  test    eax, eax
0x180010f7e  jnz     short loc_180010F53
0x180010f80  lea     esi, [rax+10h]
0x180010f83  cmp     word ptr [rsp+270h+Src], si
0x180010f88  jnb     short loc_180010FFD
0x180010f8a  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180010f91  lea     edx, [rax+20h]; unsigned __int64
0x180010f94  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180010f99  mov     rdi, rax
0x180010f9c  test    rax, rax
0x180010f9f  jnz     short loc_180010FA8
0x180010fa1  mov     ebx, 0C0000017h
0x180010fa6  jmp     short loc_180011004
0x180010fa8  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180010faf  mov     rdx, rsi; unsigned __int64
0x180010fb2  mov     dword ptr [rax+8], 14h
0x180010fb9  mov     [rax+10h], esi
0x180010fbc  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180010fc1  mov     [rdi+18h], rax
0x180010fc5  test    rax, rax
0x180010fc8  jz      short loc_180010FA1
0x180010fca  movzx   ebx, word ptr [rsp+270h+Src]
0x180010fcf  mov     rcx, rax; void *
0x180010fd2  mov     rdx, [rsp+270h+Src+8]; Src
0x180010fd7  mov     r8d, ebx; Size
0x180010fda  call    memcpy_0
0x180010fdf  mov     rcx, [rdi+18h]
0x180010fe3  sub     rsi, rbx
0x180010fe6  add     rcx, rbx; void *
0x180010fe9  mov     r8, rsi; Size
0x180010fec  mov     edx, 20h ; ' '; Val
0x180010ff1  call    memset_0
0x180010ff6  mov     qword ptr [rdi], 0
0x180010ffd  xor     ebx, ebx
0x180010fff  mov     [r14], rdi
0x180011002  xor     edi, edi
0x180011004  mov     rcx, [rsp+270h+Src+8]; void *
0x180011009  test    rcx, rcx
0x18001100c  jz      short loc_180011013
0x18001100e  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180011013  test    rdi, rdi
0x180011016  jz      short loc_18001102E
0x180011018  mov     rcx, [rdi+18h]; void *
0x18001101c  test    rcx, rcx
0x18001101f  jz      short loc_180011026
0x180011021  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180011026  mov     rcx, rdi; void *
0x180011029  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18001102e  mov     eax, ebx
0x180011030  mov     rcx, [rbp+170h+var_20]
0x180011037  xor     rcx, rsp; StackCookie
0x18001103a  call    __security_check_cookie
0x18001103f  lea     r11, [rsp+270h+var_10]
0x180011047  mov     rbx, [r11+28h]
0x18001104b  mov     rsi, [r11+30h]
0x18001104f  mov     rsp, r11
0x180011052  pop     r14
0x180011054  pop     rdi
0x180011055  pop     rbp
0x180011056  retn
```
