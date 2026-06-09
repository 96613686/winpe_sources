# Ipv6cpMakeConfigRequest

- ea: `0x1800225e0`
- end: `0x180022760`
- name: `Ipv6cpMakeConfigRequest`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180020574`
- `0x1800225e0`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180022630`: `Ip6cpMakeConfigRequest retry count = %d`
- `0x1800226f9`: `IPv6CP: ConfigRequest...`
- `0x18002271f`: `DumpingBytes ConfigRequest`

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
  v4 = *((_QWORD *)&xmmword_18004C800 + 1);
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    v5 = *(unsigned int *)(a1 + 176);
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Ip6cpMakeConfigRequest retry count = %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v10);
    v4 = *((_QWORD *)&xmmword_18004C800 + 1);
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
  v4 = *((_QWORD *)&xmmword_18004C800 + 1);
LABEL_13:
  *(_BYTE *)a2 = 1;
  *(_WORD *)(a2 + 2) = 3584;
  ++*(_DWORD *)(a1 + 176);
  if ( v4 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      v4,
      L"IPv6CP: ConfigRequest...");
  if ( qword_18004C820 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004C820,
      L"DumpingBytes ConfigRequest",
      14,
      a2);
  return 0;
}

```

## disassembly

```asm
0x1800225e0  mov     [rsp+arg_10], rbx
0x1800225e5  push    rdi
0x1800225e6  sub     rsp, 840h
0x1800225ed  mov     rax, cs:__security_cookie
0x1800225f4  xor     rax, rsp
0x1800225f7  mov     [rsp+848h+var_18], rax
0x1800225ff  mov     rdi, rdx
0x180022602  mov     rbx, rcx
0x180022605  xor     eax, eax
0x180022607  lea     rcx, [rsp+848h+var_814]; void *
0x18002260c  xor     edx, edx; Val
0x18002260e  mov     [rsp+848h+var_818], eax
0x180022612  mov     r8d, 7FCh; Size
0x180022618  call    memset_0
0x18002261d  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022624  test    rdx, rdx
0x180022627  jz      short loc_18002266E
0x180022629  mov     r8d, [rbx+0B0h]
0x180022630  lea     rdx, aIp6cpmakeconfi; "Ip6cpMakeConfigRequest retry count = %d"
0x180022637  xor     eax, eax
0x180022639  lea     rcx, [rsp+848h+var_818]
0x18002263e  mov     word ptr [rsp+848h+var_818], ax
0x180022643  call    FormatRRASErrorString
0x180022648  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x18002264f  lea     r8, [rsp+848h+var_818]
0x180022654  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002265b  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022667  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x18002266e  mov     rax, [rbx+48h]
0x180022672  mov     word ptr [rdi+4], 0A01h
0x180022678  mov     [rdi+6], rax
0x18002267c  mov     eax, [rbx+0A4h]
0x180022682  test    al, 1
0x180022684  jz      short loc_18002268F
0x180022686  and     eax, 0FFFFFFFEh
0x180022689  mov     [rbx+0A4h], eax
0x18002268f  lea     r8, [rbx+28h]
0x180022693  mov     rcx, [r8]
0x180022696  cmp     rcx, r8
0x180022699  jz      short loc_1800226CB
0x18002269b  mov     rax, [rbx+48h]
0x18002269f  cmp     [rcx+10h], rax
0x1800226a3  jz      short loc_1800226AA
0x1800226a5  mov     rcx, [rcx]
0x1800226a8  jmp     short loc_180022696
0x1800226aa  test    rdx, rdx
0x1800226ad  jz      short loc_1800226DE
0x1800226af  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800226b6  lea     r8, aIpv6cpProposin; "IPv6CP: proposing the same InterfaceId "...
0x1800226bd  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800226c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226c9  jmp     short loc_1800226D7
0x1800226cb  mov     rdx, [rbx+48h]
0x1800226cf  mov     rcx, r8
0x1800226d2  call    InsertInterfaceIdInList
0x1800226d7  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x1800226de  mov     byte ptr [rdi], 1
0x1800226e1  mov     word ptr [rdi+2], 0E00h
0x1800226e7  inc     dword ptr [rbx+0B0h]
0x1800226ed  test    rdx, rdx
0x1800226f0  jz      short loc_18002270C
0x1800226f2  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800226f9  lea     r8, aIpv6cpConfigre; "IPv6CP: ConfigRequest..."
0x180022700  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002270c  mov     rdx, cs:qword_18004C820
0x180022713  test    rdx, rdx
0x180022716  jz      short loc_18002273D
0x180022718  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002271f  lea     r8, aDumpingbytesCo_0; "DumpingBytes ConfigRequest"
0x180022726  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002272d  mov     r9d, 0Eh
0x180022733  mov     [rsp+848h+var_828], rdi
0x180022738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002273d  xor     eax, eax
0x18002273f  mov     rcx, [rsp+848h+var_18]
0x180022747  xor     rcx, rsp; StackCookie
0x18002274a  call    __security_check_cookie
0x18002274f  mov     rbx, [rsp+848h+arg_10]
0x180022757  add     rsp, 840h
0x18002275e  pop     rdi
0x18002275f  retn
```
