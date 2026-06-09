# EapHost::Peer::Host::IdentityResponse(EapHost::Peer::PeerSession &)

- ea: `0x1800277a8`
- end: `0x1800278ff`
- name: `?IdentityResponse@Host@Peer@EapHost@@AEBA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@AEAVPeerSession@23@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002a2fc`

## callees

- `0x180007564`
- `0x180009c40`
- `0x18001dc6c`
- `0x18001dde0`
- `0x1800277a8`
- `0x180031294`
- `0x180031314`
- `0x1800314c4`
- `0x1800322ac`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x180027820`
- `ntdll!WinSqmSetDWORD` at `0x180027820`

## string_xrefs

- `0x1800277dc`: `System\CurrentControlSet\Services\EapHost\Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall EapHost::Peer::Host::IdentityResponse(__int64 a1, HKEY a2, __int64 a3)
{
  char *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // r8d
  _WORD *v9; // rcx
  unsigned __int64 v10; // rax
  wchar_t *v11; // rcx
  __int64 v12; // rcx
  char *v13; // r8
  char *Src; // rax
  __int64 v15; // rcx
  char v17; // [rsp+20h] [rbp-48h]
  _BYTE v18[24]; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+70h] [rbp+8h] BYREF
  int v20; // [rsp+74h] [rbp+Ch]
  char *v21; // [rsp+80h] [rbp+18h]

  v20 = HIDWORD(a1);
  v5 = 0;
  v21 = 0;
  v6 = 65001;
  v19 = 0;
  RegistryKey::RegistryKey(
    (RegistryKey *)v18,
    a2,
    L"System\\CurrentControlSet\\Services\\EapHost\\Configuration",
    1u,
    v17);
  if ( !(unsigned int)RegistryKey::QueryValue(v18, L"IdentityEncodingFormat", &v19) && v19 == 1 )
    v6 = 0;
  WinSqmSetDWORD(0, 6743, v6 == 0);
  if ( (*(_BYTE *)(a3 + 128) & 0x40) == 0 )
  {
    v9 = *(_WORD **)(a3 + 312);
    if ( v9 )
    {
      if ( *v9 )
      {
        v10 = std::_WChar_traits<wchar_t>::length(v9);
        ConvertWideCharToMultiByte(v6, v11, v10);
        v5 = v21;
      }
    }
  }
  v12 = *(_QWORD *)(a3 + 304);
  if ( *(_BYTE *)(v12 + 4) == 0xFE )
  {
    v13 = `BasicSimpleString<char>::EmptyString'::`2'::empty;
    if ( v5 )
      v13 = v5;
    LOBYTE(v7) = *(_BYTE *)(v12 + 1);
    EapHost::Packet::CreateExpandedIdentityResponse(a2, v7, v13);
  }
  else
  {
    Src = `BasicSimpleString<char>::EmptyString'::`2'::empty;
    if ( v5 )
      Src = v5;
    LOBYTE(v8) = *(_BYTE *)(v12 + 1);
    if ( Src )
    {
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
    }
    else
    {
      LODWORD(v15) = 0;
    }
    LOBYTE(v7) = 2;
    EapHost::Packet::CreateInstance((int)a2, v7, v8, v15 + 5, 1, Src);
  }
  RegistryKey::Clear((RegistryKey *)v18);
  HeapAllocator::Free(v5);
  return a2;
}

```

## disassembly

```asm
0x1800277a8  mov     rax, rsp
0x1800277ab  mov     [rax+10h], rbx
0x1800277af  mov     [rax+20h], rbp
0x1800277b3  mov     [rax+8], rcx
0x1800277b7  push    rsi
0x1800277b8  push    rdi
0x1800277b9  push    r14
0x1800277bb  sub     rsp, 50h
0x1800277bf  mov     rsi, r8
0x1800277c2  mov     rbp, rdx
0x1800277c5  xor     r14d, r14d
0x1800277c8  mov     edi, r14d
0x1800277cb  mov     [rax+18h], r14
0x1800277cf  mov     ebx, 0FDE9h
0x1800277d4  mov     [rax+8], r14d
0x1800277d8  lea     r9d, [r14+1]; unsigned int
0x1800277dc  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ea"...
0x1800277e3  lea     rcx, [rax-30h]; this
0x1800277e7  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)
0x1800277ec  nop
0x1800277ed  lea     r8, [rsp+68h+arg_0]
0x1800277f2  lea     rdx, aIdentityencodi; "IdentityEncodingFormat"
0x1800277f9  lea     rcx, [rsp+68h+var_30]
0x1800277fe  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x180027803  test    eax, eax
0x180027805  jnz     short loc_180027810
0x180027807  cmp     [rsp+68h+arg_0], 1
0x18002780c  cmovz   ebx, r14d
0x180027810  mov     r8d, r14d
0x180027813  test    ebx, ebx
0x180027815  setz    r8b
0x180027819  mov     edx, 1A57h
0x18002781e  xor     ecx, ecx
0x180027820  call    cs:__imp_WinSqmSetDWORD
0x180027827  nop     dword ptr [rax+rax+00h]
0x18002782c  test    byte ptr [rsi+80h], 40h
0x180027833  jnz     short loc_180027869
0x180027835  mov     rcx, [rsi+138h]
0x18002783c  test    rcx, rcx
0x18002783f  jz      short loc_180027869
0x180027841  cmp     [rcx], r14w
0x180027845  jz      short loc_180027869
0x180027847  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18002784c  lea     r9, [rsp+68h+arg_10]
0x180027854  mov     r8, rax; unsigned __int64
0x180027857  mov     rdx, rcx; wchar_t *
0x18002785a  mov     ecx, ebx; unsigned int
0x18002785c  call    ?ConvertWideCharToMultiByte@@YAXIPEB_W_KAEAV?$BasicSimpleString@D@@@Z; ConvertWideCharToMultiByte(uint,wchar_t const *,unsigned __int64,BasicSimpleString<char> &)
0x180027861  mov     rdi, [rsp+68h+arg_10]
0x180027869  mov     rcx, [rsi+130h]
0x180027870  cmp     byte ptr [rcx+4], 0FEh
0x180027874  jnz     short loc_180027891
0x180027876  lea     r8, ?empty@?1??EmptyString@?$BasicSimpleString@D@@CAPEBDXZ@4QBDB; char const near * const `BasicSimpleString<char>::EmptyString(void)'::`2'::empty
0x18002787d  test    rdi, rdi
0x180027880  cmovnz  r8, rdi
0x180027884  mov     dl, [rcx+1]
0x180027887  mov     rcx, rbp
0x18002788a  call    ?CreateExpandedIdentityResponse@Packet@EapHost@@SA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EPEBD@Z; EapHost::Packet::CreateExpandedIdentityResponse(uchar,char const *)
0x18002788f  jmp     short loc_1800278D3
0x180027891  lea     rax, ?empty@?1??EmptyString@?$BasicSimpleString@D@@CAPEBDXZ@4QBDB; char const near * const `BasicSimpleString<char>::EmptyString(void)'::`2'::empty
0x180027898  test    rdi, rdi
0x18002789b  cmovnz  rax, rdi
0x18002789f  mov     r8b, [rcx+1]; int
0x1800278a3  test    rax, rax
0x1800278a6  jnz     short loc_1800278AD
0x1800278a8  mov     ecx, r14d
0x1800278ab  jmp     short loc_1800278BA
0x1800278ad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800278b1  inc     rcx
0x1800278b4  cmp     [rax+rcx], r14b
0x1800278b8  jnz     short loc_1800278B1
0x1800278ba  lea     r9d, [rcx+5]; int
0x1800278be  mov     [rsp+68h+Src], rax; Src
0x1800278c3  mov     [rsp+68h+var_48], 1; char
0x1800278c8  mov     dl, 2; int
0x1800278ca  mov     rcx, rbp; int
0x1800278cd  call    ?CreateInstance@Packet@EapHost@@CA?AV?$unique_ptr@VPacket@EapHost@@U?$default_delete@VPacket@EapHost@@@std@@@std@@EEGEPEBX@Z; EapHost::Packet::CreateInstance(uchar,uchar,ushort,uchar,void const *)
0x1800278d2  nop
0x1800278d3  lea     rcx, [rsp+68h+var_30]; this
0x1800278d8  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x1800278dd  nop
0x1800278de  mov     rcx, rdi; void *
0x1800278e1  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800278e6  mov     rax, rbp
0x1800278e9  lea     r11, [rsp+68h+var_18]
0x1800278ee  mov     rbx, [r11+28h]
0x1800278f2  mov     rbp, [r11+38h]
0x1800278f6  mov     rsp, r11
0x1800278f9  pop     r14
0x1800278fb  pop     rdi
0x1800278fc  pop     rsi
0x1800278fd  retn
```
