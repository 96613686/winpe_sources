# RfspServerNameInitializeAsIpv6Literal

- ea: `0x140054214`
- end: `0x1400543c3`
- name: `RfspServerNameInitializeAsIpv6Literal`
- size: `431`
- prototype: `__int64 __fastcall(__m128i *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140053b10`

## callees

- `0x140037120`
- `0x140054048`
- `0x140054214`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400542df`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400542df`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400542a8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400542a8`

## pseudocode

```c
__int64 __fastcall RfspServerNameInitializeAsIpv6Literal(__m128i *a1, __int64 a2)
{
  unsigned int v3; // eax
  __int16 v5; // ax
  USHORT Length; // cx
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // r8
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // cx
  unsigned __int16 i; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-D0h] BYREF
  char v15; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)&DestinationString.Length = 0x2000000;
  DestinationString.Buffer = (PWSTR)&v15;
  v3 = a1->m128i_u16[0];
  if ( (unsigned __int16)v3 > 0x1FEu )
    return 3221225494LL;
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  if ( (unsigned __int16)v3 < 0x22u )
    return 3221225494LL;
  *(_DWORD *)&String1.Length = 2228258;
  String1.Buffer = (PWSTR)(a1->m128i_i64[1] - 34 + v3);
  if ( !RtlEqualUnicodeString(&String1, &RfspIpv6LiteralDomainName, 1u) )
    return 3221225494LL;
  v5 = _mm_cvtsi128_si32(*a1);
  String1 = (UNICODE_STRING)*a1;
  String1.Length = v5 - 34;
  RtlCopyUnicodeString(&DestinationString, &String1);
  Length = DestinationString.Length;
  v7 = 0;
  v8 = DestinationString.Length >> 1;
  if ( DestinationString.Length >> 1 )
  {
    do
    {
      if ( DestinationString.Buffer[v7] == 45 )
        DestinationString.Buffer[v7] = 58;
      ++v7;
    }
    while ( v7 < v8 );
    Length = DestinationString.Length;
  }
  v9 = 0;
  if ( Length >> 1 )
  {
    do
    {
      if ( DestinationString.Buffer[v9] == 115 )
        DestinationString.Buffer[v9] = 37;
      ++v9;
    }
    while ( v9 < (unsigned __int16)(Length >> 1) );
    Length = DestinationString.Length;
  }
  v10 = Length >> 1;
  for ( i = 0; i < v10; ++i )
  {
    if ( DestinationString.Buffer[i] == 83 )
      DestinationString.Buffer[i] = 37;
  }
  return RfspServerNameInitializeAsIpv6((__int64)&DestinationString, a2);
}

```

## disassembly

```asm
0x140054214  mov     [rsp-8+arg_10], rbx
0x140054219  mov     [rsp-8+arg_18], rdi
0x14005421e  push    rbp
0x14005421f  lea     rbp, [rsp-150h]
0x140054227  sub     rsp, 250h
0x14005422e  mov     rax, cs:__security_cookie
0x140054235  xor     rax, rsp
0x140054238  mov     [rbp+150h+var_10], rax
0x14005423f  lea     rax, [rsp+250h+var_210]
0x140054244  mov     qword ptr [rsp+250h+DestinationString.Length], 2000000h
0x14005424d  mov     [rsp+250h+DestinationString.Buffer], rax
0x140054252  mov     rbx, rcx
0x140054255  movzx   eax, word ptr [rcx]
0x140054258  mov     rdi, rdx
0x14005425b  mov     ecx, 1FEh
0x140054260  cmp     ax, cx
0x140054263  ja      loc_140054399
0x140054269  mov     edx, 22h ; '"'
0x14005426e  mov     dword ptr [rsp+250h+String1+4], 0
0x140054276  cmp     ax, dx
0x140054279  jb      loc_140054399
0x14005427f  mov     ecx, eax
0x140054281  mov     dword ptr [rsp+250h+String1.Length], 220022h
0x140054289  mov     rax, [rbx+8]
0x14005428d  lea     rdx, RfspIpv6LiteralDomainName; String2
0x140054294  add     rax, 0FFFFFFFFFFFFFFDEh
0x140054298  mov     r8b, 1; CaseInSensitive
0x14005429b  add     rcx, rax
0x14005429e  mov     [rsp+250h+String1.Buffer], rcx
0x1400542a3  lea     rcx, [rsp+250h+String1]; String1
0x1400542a8  call    cs:__imp_RtlEqualUnicodeString
0x1400542af  nop     dword ptr [rax+rax+00h]
0x1400542b4  test    al, al
0x1400542b6  jz      loc_140054399
0x1400542bc  movups  xmm0, xmmword ptr [rbx]
0x1400542bf  mov     ecx, 0FFDEh
0x1400542c4  lea     rdx, [rsp+250h+String1]; SourceString
0x1400542c9  movd    eax, xmm0
0x1400542cd  movups  xmmword ptr [rsp+250h+String1.Length], xmm0
0x1400542d2  add     ax, cx
0x1400542d5  lea     rcx, [rsp+250h+DestinationString]; DestinationString
0x1400542da  mov     [rsp+250h+String1.Length], ax
0x1400542df  call    cs:__imp_RtlCopyUnicodeString
0x1400542e6  nop     dword ptr [rax+rax+00h]
0x1400542eb  movzx   ecx, [rsp+250h+DestinationString.Length]
0x1400542f0  xor     edx, edx
0x1400542f2  movzx   r8d, cx
0x1400542f6  xor     eax, eax
0x1400542f8  shr     r8w, 1
0x1400542fc  cmp     ax, r8w
0x140054300  jnb     short loc_140054325
0x140054302  mov     rcx, [rsp+250h+DestinationString.Buffer]
0x140054307  movzx   eax, dx
0x14005430a  cmp     word ptr [rcx+rax*2], 2Dh ; '-'
0x14005430f  jnz     short loc_140054317
0x140054311  mov     word ptr [rcx+rax*2], 3Ah ; ':'
0x140054317  inc     dx
0x14005431a  cmp     dx, r8w
0x14005431e  jb      short loc_140054302
0x140054320  movzx   ecx, [rsp+250h+DestinationString.Length]
0x140054325  xor     edx, edx
0x140054327  movzx   r8d, cx
0x14005432b  shr     r8w, 1
0x14005432f  xor     eax, eax
0x140054331  lea     r10d, [rdx+25h]
0x140054335  cmp     ax, r8w
0x140054339  jnb     short loc_14005435D
0x14005433b  mov     rcx, [rsp+250h+DestinationString.Buffer]
0x140054340  movzx   eax, dx
0x140054343  cmp     word ptr [rcx+rax*2], 73h ; 's'
0x140054348  jnz     short loc_14005434F
0x14005434a  mov     [rcx+rax*2], r10w
0x14005434f  inc     dx
0x140054352  cmp     dx, r8w
0x140054356  jb      short loc_14005433B
0x140054358  movzx   ecx, [rsp+250h+DestinationString.Length]
0x14005435d  shr     cx, 1
0x140054360  xor     r8d, r8d
0x140054363  xor     eax, eax
0x140054365  cmp     ax, cx
0x140054368  jnb     short loc_14005438A
0x14005436a  mov     r9, [rsp+250h+DestinationString.Buffer]
0x14005436f  movzx   eax, r8w
0x140054373  cmp     word ptr [r9+rax*2], 53h ; 'S'
0x140054379  jnz     short loc_140054380
0x14005437b  mov     [r9+rax*2], r10w
0x140054380  inc     r8w
0x140054384  cmp     r8w, cx
0x140054388  jb      short loc_14005436A
0x14005438a  mov     rdx, rdi
0x14005438d  lea     rcx, [rsp+250h+DestinationString]
0x140054392  call    RfspServerNameInitializeAsIpv6
0x140054397  jmp     short loc_14005439E
0x140054399  mov     eax, 0C0000016h
0x14005439e  mov     rcx, [rbp+150h+var_10]
0x1400543a5  xor     rcx, rsp; StackCookie
0x1400543a8  call    __security_check_cookie
0x1400543ad  lea     r11, [rsp+250h+var_s0]
0x1400543b5  mov     rbx, [r11+20h]
0x1400543b9  mov     rdi, [r11+28h]
0x1400543bd  mov     rsp, r11
0x1400543c0  pop     rbp
0x1400543c1  retn
```
