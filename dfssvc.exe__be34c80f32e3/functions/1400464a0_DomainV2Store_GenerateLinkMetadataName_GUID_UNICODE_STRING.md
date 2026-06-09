# DomainV2Store::GenerateLinkMetadataName(_GUID *,_UNICODE_STRING *)

- ea: `0x1400464a0`
- end: `0x140046569`
- name: `?GenerateLinkMetadataName@DomainV2Store@@UEAAKPEAU_GUID@@PEAU_UNICODE_STRING@@@Z`
- size: `201`
- prototype: `unsigned int(DomainV2Store *__hidden this, struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1400011d0`
- `0x14000aed8`
- `0x1400464a0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140046526`
- `ntdll!RtlInitUnicodeStringEx` at `0x140046526`
- `RPCRT4!RpcStringFreeW` at `0x14004653e`
- `RPCRT4!RpcStringFreeW` at `0x14004653e`
- `RPCRT4!UuidToStringW` at `0x1400464c4`
- `RPCRT4!UuidToStringW` at `0x1400464c4`

## string_xrefs

- `0x14004650e`: `link-%s`

## pseudocode

```c
__int64 __fastcall DomainV2Store::GenerateLinkMetadataName(
        DomainV2Store *this,
        struct _GUID *a2,
        struct _UNICODE_STRING *a3)
{
  unsigned int v3; // ebx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  const WCHAR *v8; // rsi
  RPC_WSTR String; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  String = 0;
  if ( UuidToStringW(a2, &String) )
  {
    return 8;
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( String[v5] );
    v6 = v5 + 6;
    v7 = (unsigned __int16 *)operator new(saturated_mul(v6, 2u));
    v8 = v7;
    if ( v7 )
    {
      StringCchPrintfW(v7, v6, L"link-%s", String);
      RtlInitUnicodeStringEx(a3, v8);
    }
    else
    {
      v3 = 8;
    }
    RpcStringFreeW(&String);
  }
  return v3;
}

```

## disassembly

```asm
0x1400464a0  mov     rax, rsp
0x1400464a3  mov     [rax+8], rbx
0x1400464a7  mov     [rax+10h], rbp
0x1400464ab  mov     [rax+18h], rsi
0x1400464af  push    rdi
0x1400464b0  sub     rsp, 20h
0x1400464b4  mov     rcx, rdx; Uuid
0x1400464b7  xor     ebx, ebx
0x1400464b9  lea     rdx, [rax+20h]; StringUuid
0x1400464bd  mov     [rax+20h], rbx
0x1400464c1  mov     rbp, r8
0x1400464c4  call    cs:__imp_UuidToStringW
0x1400464cb  nop     dword ptr [rax+rax+00h]
0x1400464d0  test    eax, eax
0x1400464d2  jnz     short loc_14004654C
0x1400464d4  mov     rax, [rsp+28h+String]
0x1400464d9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400464dd  mov     rdi, rcx
0x1400464e0  inc     rdi
0x1400464e3  cmp     [rax+rdi*2], bx
0x1400464e7  jnz     short loc_1400464E0
0x1400464e9  add     rdi, 6
0x1400464ed  mov     eax, 2
0x1400464f2  mul     rdi
0x1400464f5  cmovo   rax, rcx
0x1400464f9  mov     rcx, rax; Size
0x1400464fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140046501  mov     rsi, rax
0x140046504  test    rax, rax
0x140046507  jz      short loc_140046534
0x140046509  mov     r9, [rsp+28h+String]
0x14004650e  lea     r8, aLinkS; "link-%s"
0x140046515  mov     rdx, rdi; unsigned __int64
0x140046518  mov     rcx, rax; unsigned __int16 *
0x14004651b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140046520  mov     rdx, rsi; SourceString
0x140046523  mov     rcx, rbp; DestinationString
0x140046526  call    cs:__imp_RtlInitUnicodeStringEx
0x14004652d  nop     dword ptr [rax+rax+00h]
0x140046532  jmp     short loc_140046539
0x140046534  mov     ebx, 8
0x140046539  lea     rcx, [rsp+28h+String]; String
0x14004653e  call    cs:__imp_RpcStringFreeW
0x140046545  nop     dword ptr [rax+rax+00h]
0x14004654a  jmp     short loc_140046551
0x14004654c  mov     ebx, 8
0x140046551  mov     rbp, [rsp+28h+arg_8]
0x140046556  mov     eax, ebx
0x140046558  mov     rbx, [rsp+28h+arg_0]
0x14004655d  mov     rsi, [rsp+28h+arg_10]
0x140046562  add     rsp, 20h
0x140046566  pop     rdi
0x140046567  retn
```
