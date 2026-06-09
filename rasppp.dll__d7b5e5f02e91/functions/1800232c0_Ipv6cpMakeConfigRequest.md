# Ipv6cpMakeConfigRequest

- ea: `0x1800232c0`
- end: `0x180023441`
- name: `Ipv6cpMakeConfigRequest`
- size: `385`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180021184`
- `0x1800232c0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180023310`: `Ip6cpMakeConfigRequest retry count = %d`
- `0x1800233d9`: `IPv6CP: ConfigRequest...`
- `0x1800233ff`: `DumpingBytes ConfigRequest`

## pseudocode

```c
__int64 __fastcall Ipv6cpMakeConfigRequest(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // eax
  _QWORD *i; // rcx
  int v10; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-814h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  v4 = *((_QWORD *)&xmmword_18004D800 + 1);
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    v5 = *(unsigned int *)(a1 + 176);
    LOWORD(v10) = 0;
    FormatRRASErrorString((wchar_t *)&v10, L"Ip6cpMakeConfigRequest retry count = %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v10);
    v4 = *((_QWORD *)&xmmword_18004D800 + 1);
  }
  v6 = *(_QWORD *)(a1 + 72);
  *(_WORD *)(a2 + 4) = 2561;
  *(_QWORD *)(a2 + 6) = v6;
  v7 = *(_DWORD *)(a1 + 164);
  if ( (v7 & 1) != 0 )
    *(_DWORD *)(a1 + 164) = v7 & 0xFFFFFFFE;
  for ( i = *(_QWORD **)(a1 + 40); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(a1 + 40) )
    {
      InsertInterfaceIdInList(a1 + 40, *(_QWORD *)(a1 + 72));
      goto LABEL_12;
    }
    if ( i[2] == *(_QWORD *)(a1 + 72) )
      break;
  }
  if ( !v4 )
    goto LABEL_13;
  ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
    gRasIpv6cpEtwContext,
    v4,
    L"IPv6CP: proposing the same InterfaceId for which negotiation was alreay tried. Should not hit this normally");
LABEL_12:
  v4 = *((_QWORD *)&xmmword_18004D800 + 1);
LABEL_13:
  *(_BYTE *)a2 = 1;
  *(_WORD *)(a2 + 2) = 3584;
  ++*(_DWORD *)(a1 + 176);
  if ( v4 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      v4,
      L"IPv6CP: ConfigRequest...");
  if ( qword_18004D820 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004D820,
      L"DumpingBytes ConfigRequest",
      14,
      a2);
  return 0;
}

```

## disassembly

```asm
0x1800232c0  mov     [rsp+arg_10], rbx
0x1800232c5  push    rdi
0x1800232c6  sub     rsp, 840h
0x1800232cd  mov     rax, cs:__security_cookie
0x1800232d4  xor     rax, rsp
0x1800232d7  mov     [rsp+848h+var_18], rax
0x1800232df  mov     rdi, rdx
0x1800232e2  mov     rbx, rcx
0x1800232e5  xor     eax, eax
0x1800232e7  lea     rcx, [rsp+848h+var_814]; void *
0x1800232ec  xor     edx, edx; Val
0x1800232ee  mov     [rsp+848h+var_818], eax
0x1800232f2  mov     r8d, 7FCh; Size
0x1800232f8  call    memset_0
0x1800232fd  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180023304  test    rdx, rdx
0x180023307  jz      short loc_18002334E
0x180023309  mov     r8d, [rbx+0B0h]
0x180023310  lea     rdx, aIp6cpmakeconfi; "Ip6cpMakeConfigRequest retry count = %d"
0x180023317  xor     eax, eax
0x180023319  lea     rcx, [rsp+848h+var_818]
0x18002331e  mov     word ptr [rsp+848h+var_818], ax
0x180023323  call    FormatRRASErrorString
0x180023328  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002332f  lea     r8, [rsp+848h+var_818]
0x180023334  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002333b  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180023342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023347  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x18002334e  mov     rax, [rbx+48h]
0x180023352  mov     word ptr [rdi+4], 0A01h
0x180023358  mov     [rdi+6], rax
0x18002335c  mov     eax, [rbx+0A4h]
0x180023362  test    al, 1
0x180023364  jz      short loc_18002336F
0x180023366  and     eax, 0FFFFFFFEh
0x180023369  mov     [rbx+0A4h], eax
0x18002336f  lea     r8, [rbx+28h]
0x180023373  mov     rcx, [r8]
0x180023376  cmp     rcx, r8
0x180023379  jz      short loc_1800233AB
0x18002337b  mov     rax, [rbx+48h]
0x18002337f  cmp     [rcx+10h], rax
0x180023383  jz      short loc_18002338A
0x180023385  mov     rcx, [rcx]
0x180023388  jmp     short loc_180023376
0x18002338a  test    rdx, rdx
0x18002338d  jz      short loc_1800233BE
0x18002338f  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023396  lea     r8, aIpv6cpProposin; "IPv6CP: proposing the same InterfaceId "...
0x18002339d  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800233a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233a9  jmp     short loc_1800233B7
0x1800233ab  mov     rdx, [rbx+48h]
0x1800233af  mov     rcx, r8
0x1800233b2  call    InsertInterfaceIdInList
0x1800233b7  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800233be  mov     byte ptr [rdi], 1
0x1800233c1  mov     word ptr [rdi+2], 0E00h
0x1800233c7  inc     dword ptr [rbx+0B0h]
0x1800233cd  test    rdx, rdx
0x1800233d0  jz      short loc_1800233EC
0x1800233d2  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800233d9  lea     r8, aIpv6cpConfigre; "IPv6CP: ConfigRequest..."
0x1800233e0  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800233e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233ec  mov     rdx, cs:qword_18004D820
0x1800233f3  test    rdx, rdx
0x1800233f6  jz      short loc_18002341D
0x1800233f8  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800233ff  lea     r8, aDumpingbytesCo_0; "DumpingBytes ConfigRequest"
0x180023406  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002340d  mov     r9d, 0Eh
0x180023413  mov     [rsp+848h+var_828], rdi
0x180023418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002341d  xor     eax, eax
0x18002341f  mov     rcx, [rsp+848h+var_18]
0x180023427  xor     rcx, rsp; StackCookie
0x18002342a  call    __security_check_cookie
0x18002342f  mov     rbx, [rsp+848h+arg_10]
0x180023437  add     rsp, 840h
0x18002343e  pop     rdi
0x18002343f  retn
```
