# EapHost::Peer::Host::IdentityResponse(EapHost::Peer::PeerSession &)

- ea: `0x180026a4c`
- end: `0x180026b9c`
- name: `?IdentityResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800294c8`

## callees

- `0x1800072cc`
- `0x180009844`
- `0x18001d19c`
- `0x18001d308`
- `0x180026a4c`
- `0x180030080`
- `0x1800300fc`
- `0x180030294`
- `0x1800310e4`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x180026ac4`
- `ntdll!WinSqmSetDWORD` at `0x180026ac4`

## string_xrefs

- `0x180026a80`: `System\CurrentControlSet\Services\EapHost\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall EapHost::Peer::Host::IdentityResponse(__int64 a1, __int64 *a2, __int64 a3)
{
  char *v5; // rdi
  unsigned int v6; // ebx
  _WORD *v7; // rcx
  unsigned __int64 v8; // rax
  wchar_t *v9; // rcx
  __int64 v10; // rcx
  char *v11; // r8
  char *Src; // rax
  char v13; // r8
  __int64 v14; // rcx
  HKEY v16[3]; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+70h] [rbp+8h] BYREF
  int v18; // [rsp+74h] [rbp+Ch]
  char *v19; // [rsp+80h] [rbp+18h]

  v18 = HIDWORD(a1);
  v5 = 0;
  v19 = 0;
  v6 = 65001;
  v17 = 0;
  RegistryKey::RegistryKey(
    (RegistryKey *)v16,
    (HKEY)a2,
    L"System\\CurrentControlSet\\Services\\EapHost\\Configuration",
    1);
  if ( !(unsigned int)RegistryKey::QueryValue(v16, L"IdentityEncodingFormat", &v17) && v17 == 1 )
    v6 = 0;
  WinSqmSetDWORD(0, 6743, v6 == 0);
  if ( (*(_BYTE *)(a3 + 128) & 0x40) == 0 )
  {
    v7 = *(_WORD **)(a3 + 312);
    if ( v7 )
    {
      if ( *v7 )
      {
        v8 = std::_WChar_traits<wchar_t>::length(v7);
        ConvertWideCharToMultiByte(v6, v9, v8);
        v5 = v19;
      }
    }
  }
  v10 = *(_QWORD *)(a3 + 304);
  if ( *(_BYTE *)(v10 + 4) == 0xFE )
  {
    v11 = `BasicSimpleString<char>::EmptyString'::`2'::empty;
    if ( v5 )
      v11 = v5;
    EapHost::Packet::CreateExpandedIdentityResponse(a2, *(_BYTE *)(v10 + 1), v11);
  }
  else
  {
    Src = `BasicSimpleString<char>::EmptyString'::`2'::empty;
    if ( v5 )
      Src = v5;
    v13 = *(_BYTE *)(v10 + 1);
    if ( Src )
    {
      v14 = -1;
      do
        ++v14;
      while ( Src[v14] );
    }
    else
    {
      LOWORD(v14) = 0;
    }
    EapHost::Packet::CreateInstance(a2, 2, v13, v14 + 5, 1, Src);
  }
  RegistryKey::Clear(v16);
  HeapAllocator::Free(v5);
  return a2;
}

```

## disassembly

```asm
0x180026a4c  mov     rax, rsp
0x180026a4f  mov     [rax+10h], rbx
0x180026a53  mov     [rax+20h], rbp
0x180026a57  mov     [rax+8], rcx
0x180026a5b  push    rsi
0x180026a5c  push    rdi
0x180026a5d  push    r14
0x180026a5f  sub     rsp, 50h
0x180026a63  mov     rsi, r8
0x180026a66  mov     rbp, rdx
0x180026a69  xor     r14d, r14d
0x180026a6c  mov     edi, r14d
0x180026a6f  mov     [rax+18h], r14
0x180026a73  mov     ebx, 0FDE9h
0x180026a78  mov     [rax+8], r14d
0x180026a7c  lea     r9d, [r14+1]; unsigned int
0x180026a80  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x180026a87  lea     rcx, [rax-30h]; this
0x180026a8b  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)
0x180026a90  nop
0x180026a91  lea     r8, [rsp+68h+arg_0]
0x180026a96  lea     rdx, aIdentityencodi; "IdentityEncodingFormat"
0x180026a9d  lea     rcx, [rsp+68h+var_30]
0x180026aa2  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x180026aa7  test    eax, eax
0x180026aa9  jnz     short loc_180026AB4
0x180026aab  cmp     [rsp+68h+arg_0], 1
0x180026ab0  cmovz   ebx, r14d
0x180026ab4  mov     r8d, r14d
0x180026ab7  test    ebx, ebx
0x180026ab9  setz    r8b
0x180026abd  mov     edx, 1A57h
0x180026ac2  xor     ecx, ecx
0x180026ac4  call    cs:__imp_WinSqmSetDWORD
0x180026aca  test    byte ptr [rsi+80h], 40h
0x180026ad1  jnz     short loc_180026B07
0x180026ad3  mov     rcx, [rsi+138h]
0x180026ada  test    rcx, rcx
0x180026add  jz      short loc_180026B07
0x180026adf  cmp     [rcx], r14w
0x180026ae3  jz      short loc_180026B07
0x180026ae5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180026aea  lea     r9, [rsp+68h+arg_10]
0x180026af2  mov     r8, rax; unsigned __int64
0x180026af5  mov     rdx, rcx; wchar_t *
0x180026af8  mov     ecx, ebx; unsigned int
0x180026afa  call    ?ConvertWideCharToMultiByte@@YAXIPEB_W_KAEAV?$BasicSimpleString@D@@@Z; ConvertWideCharToMultiByte(uint,wchar_t const *,unsigned __int64,BasicSimpleString<char> &)
0x180026aff  mov     rdi, [rsp+68h+arg_10]
0x180026b07  mov     rcx, [rsi+130h]
0x180026b0e  cmp     byte ptr [rcx+4], 0FEh
0x180026b12  jnz     short loc_180026B2F
0x180026b14  lea     r8, ?empty@?1??EmptyString@?$BasicSimpleString@D@@CAPEBDXZ@4QBDB; char const near * const `BasicSimpleString<char>::EmptyString(void)'::`2'::empty
0x180026b1b  test    rdi, rdi
0x180026b1e  cmovnz  r8, rdi
0x180026b22  mov     dl, [rcx+1]
0x180026b25  mov     rcx, rbp
0x180026b28  call    ?CreateExpandedIdentityResponse@Packet@EapHost@@SA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EPEBD@Z; EapHost::Packet::CreateExpandedIdentityResponse(uchar,char const *)
0x180026b2d  jmp     short loc_180026B71
0x180026b2f  lea     rax, ?empty@?1??EmptyString@?$BasicSimpleString@D@@CAPEBDXZ@4QBDB; char const near * const `BasicSimpleString<char>::EmptyString(void)'::`2'::empty
0x180026b36  test    rdi, rdi
0x180026b39  cmovnz  rax, rdi
0x180026b3d  mov     r8b, [rcx+1]; int
0x180026b41  test    rax, rax
0x180026b44  jnz     short loc_180026B4B
0x180026b46  mov     ecx, r14d
0x180026b49  jmp     short loc_180026B58
0x180026b4b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026b4f  inc     rcx
0x180026b52  cmp     [rax+rcx], r14b
0x180026b56  jnz     short loc_180026B4F
0x180026b58  lea     r9d, [rcx+5]; int
0x180026b5c  mov     [rsp+68h+Src], rax; Src
0x180026b61  mov     [rsp+68h+var_48], 1; char
0x180026b66  mov     dl, 2; int
0x180026b68  mov     rcx, rbp; int
0x180026b6b  call    ?CreateInstance@Packet@EapHost@@CA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EEGEPEBX@Z; EapHost::Packet::CreateInstance(uchar,uchar,ushort,uchar,void const *)
0x180026b70  nop
0x180026b71  lea     rcx, [rsp+68h+var_30]; this
0x180026b76  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180026b7b  nop
0x180026b7c  mov     rcx, rdi; void *
0x180026b7f  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026b84  mov     rax, rbp
0x180026b87  lea     r11, [rsp+68h+var_18]
0x180026b8c  mov     rbx, [r11+28h]
0x180026b90  mov     rbp, [r11+38h]
0x180026b94  mov     rsp, r11
0x180026b97  pop     r14
0x180026b99  pop     rdi
0x180026b9a  pop     rsi
0x180026b9b  retn
```
