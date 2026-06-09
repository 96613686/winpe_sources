# Ipv6cpMakeConfigResult

- ea: `0x180022770`
- end: `0x180022a1c`
- name: `Ipv6cpMakeConfigResult`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180022770`
- `0x180022a24`
- `0x180022d60`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## string_xrefs

- `0x1800227e6`: `IPv6CPMakeConfigResult`
- `0x1800229b8`: `IPv6CPMakeConfigResult: done %d`

## pseudocode

```c
__int64 __fastcall Ipv6cpMakeConfigResult(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // r12
  __int64 v5; // r13
  int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // edi
  int v13; // r9d
  _DWORD v15[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v3 = *(unsigned __int8 *)(a2 + 3);
  v5 = *(unsigned __int8 *)(a2 + 2);
  v15[0] = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v9 = *((_QWORD *)&xmmword_18004C800 + 1);
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      L"IPv6CPMakeConfigResult");
    v9 = *((_QWORD *)&xmmword_18004C800 + 1);
  }
  v10 = qword_18004C820;
  if ( qword_18004C820 )
  {
    if ( a2 )
      v11 = *(unsigned __int8 *)(a2 + 3) + (*(unsigned __int8 *)(a2 + 2) << 8);
    else
      v11 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004C820,
      L"DumpingBytes",
      v11,
      a2);
    v10 = qword_18004C820;
    v9 = *((_QWORD *)&xmmword_18004C800 + 1);
  }
  if ( v9 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      v9,
      L"Remote Interface Id:");
    v10 = qword_18004C820;
  }
  if ( v10 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      v10,
      L"DumpingBytes Remote Interface Id",
      8,
      a2 + 6);
  v12 = Ipv6cpRejectCheck(a1, a2, (_DWORD)a3, v8, (__int64)v15);
  if ( !v12 && !v15[0] )
  {
    v12 = Ipv6cpNakCheck(a1, a2, (_DWORD)a3, v13, (__int64)v15);
    if ( !v12 && !v15[0] )
    {
      *(_QWORD *)(a1 + 80) = *(_QWORD *)(a2 + 6);
      if ( *(_DWORD *)a1 != v12 && *((_QWORD *)&xmmword_18004C4F0 + 1) )
      {
        v16 = *(_OWORD *)(a1 + 2084);
        (*((void (__fastcall **)(__int128 *, __int64))&xmmword_18004C4F0 + 1))(&v16, a1 + 80);
      }
      if ( *((_QWORD *)&xmmword_18004C800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004C800 + 1),
          L"Remote Interface Id:");
      if ( qword_18004C820 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
          gRasIpv6cpEtwContext,
          qword_18004C820,
          L"DumpingBytes Remote Interface Id",
          8,
          a1 + 80);
      memcpy_0(a3, (const void *)a2, v3 + (v5 << 8));
      *a3 = 2;
    }
  }
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"IPv6CPMakeConfigResult: done %d", v12);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v17);
  }
  return v12;
}

```

## disassembly

```asm
0x180022770  mov     [rsp-8+arg_18], rbx
0x180022775  push    rbp
0x180022776  push    rsi
0x180022777  push    rdi
0x180022778  push    r12
0x18002277a  push    r13
0x18002277c  push    r14
0x18002277e  push    r15
0x180022780  lea     rbp, [rsp-760h]
0x180022788  sub     rsp, 860h
0x18002278f  mov     rax, cs:__security_cookie
0x180022796  xor     rax, rsp
0x180022799  mov     [rbp+790h+var_40], rax
0x1800227a0  movzx   r12d, byte ptr [rdx+3]
0x1800227a5  mov     r15, r8
0x1800227a8  movzx   r13d, byte ptr [rdx+2]
0x1800227ad  mov     rbx, rdx
0x1800227b0  mov     r14, rcx
0x1800227b3  mov     [rsp+890h+var_860], 0
0x1800227bb  xor     eax, eax
0x1800227bd  lea     rcx, [rsp+890h+var_83C]; void *
0x1800227c2  xor     edx, edx; Val
0x1800227c4  mov     [rsp+890h+var_840], eax
0x1800227c8  mov     r8d, 7FCh; Size
0x1800227ce  call    memset_0
0x1800227d3  mov     rax, qword ptr cs:xmmword_18004C800+8
0x1800227da  test    rax, rax
0x1800227dd  jz      short loc_180022803
0x1800227df  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800227e6  lea     r8, aIpv6cpmakeconf; "IPv6CPMakeConfigResult"
0x1800227ed  mov     rdx, rax
0x1800227f0  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800227f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227fc  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180022803  mov     rdx, cs:qword_18004C820
0x18002280a  test    rdx, rdx
0x18002280d  jz      short loc_180022856
0x18002280f  test    rbx, rbx
0x180022812  jz      short loc_180022826
0x180022814  movzx   r9d, byte ptr [rbx+2]
0x180022819  movzx   eax, byte ptr [rbx+3]
0x18002281d  shl     r9d, 8
0x180022821  add     r9d, eax
0x180022824  jmp     short loc_180022829
0x180022826  xor     r9d, r9d
0x180022829  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022830  lea     r8, aDumpingbytes; "DumpingBytes"
0x180022837  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002283e  mov     [rsp+890h+var_870], rbx
0x180022843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022848  mov     rdx, cs:qword_18004C820
0x18002284f  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180022856  test    rax, rax
0x180022859  jz      short loc_18002287F
0x18002285b  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022862  lea     r8, aRemoteInterfac; "Remote Interface Id:"
0x180022869  mov     rdx, rax
0x18002286c  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022878  mov     rdx, cs:qword_18004C820
0x18002287f  test    rdx, rdx
0x180022882  jz      short loc_1800228AD
0x180022884  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002288b  lea     rcx, [rbx+6]
0x18002288f  mov     [rsp+890h+var_870], rcx
0x180022894  lea     r8, aDumpingbytesRe_0; "DumpingBytes Remote Interface Id"
0x18002289b  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800228a2  mov     r9d, 8
0x1800228a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ad  lea     rax, [rsp+890h+var_860]
0x1800228b2  mov     r8, r15
0x1800228b5  mov     rdx, rbx
0x1800228b8  mov     [rsp+890h+var_870], rax
0x1800228bd  mov     rcx, r14
0x1800228c0  call    Ipv6cpRejectCheck
0x1800228c5  mov     edi, eax
0x1800228c7  test    eax, eax
0x1800228c9  jnz     loc_1800229AC
0x1800228cf  cmp     [rsp+890h+var_860], eax
0x1800228d3  jnz     loc_1800229AC
0x1800228d9  lea     rax, [rsp+890h+var_860]
0x1800228de  mov     r8, r15
0x1800228e1  mov     rdx, rbx
0x1800228e4  mov     [rsp+890h+var_870], rax
0x1800228e9  mov     rcx, r14
0x1800228ec  call    Ipv6cpNakCheck
0x1800228f1  mov     edi, eax
0x1800228f3  test    eax, eax
0x1800228f5  jnz     loc_1800229AC
0x1800228fb  cmp     [rsp+890h+var_860], eax
0x1800228ff  jnz     loc_1800229AC
0x180022905  lea     rsi, [r14+50h]
0x180022909  mov     rax, [rbx+6]
0x18002290d  mov     [rsi], rax
0x180022910  cmp     [r14], edi
0x180022913  jz      short loc_18002293C
0x180022915  mov     rax, qword ptr cs:xmmword_18004C4F0+8
0x18002291c  test    rax, rax
0x18002291f  jz      short loc_18002293C
0x180022921  movups  xmm0, xmmword ptr [r14+824h]
0x180022929  mov     rdx, rsi
0x18002292c  lea     rcx, [rsp+890h+var_850]
0x180022931  movdqu  [rsp+890h+var_850], xmm0
0x180022937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002293c  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022943  test    rdx, rdx
0x180022946  jz      short loc_180022962
0x180022948  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002294f  lea     r8, aRemoteInterfac; "Remote Interface Id:"
0x180022956  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002295d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022962  mov     rdx, cs:qword_18004C820
0x180022969  test    rdx, rdx
0x18002296c  jz      short loc_180022993
0x18002296e  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022975  lea     r8, aDumpingbytesRe_0; "DumpingBytes Remote Interface Id"
0x18002297c  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x180022983  mov     r9d, 8
0x180022989  mov     [rsp+890h+var_870], rsi
0x18002298e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022993  mov     r8, r13
0x180022996  mov     rdx, rbx; Src
0x180022999  shl     r8, 8
0x18002299d  mov     rcx, r15; void *
0x1800229a0  add     r8, r12; Size
0x1800229a3  call    memcpy_0
0x1800229a8  mov     byte ptr [r15], 2
0x1800229ac  cmp     qword ptr cs:xmmword_18004C800+8, 0
0x1800229b4  jz      short loc_1800229F0
0x1800229b6  xor     eax, eax
0x1800229b8  lea     rdx, aIpv6cpmakeconf_0; "IPv6CPMakeConfigResult: done %d"
0x1800229bf  mov     r8d, edi
0x1800229c2  mov     word ptr [rsp+890h+var_840], ax
0x1800229c7  lea     rcx, [rsp+890h+var_840]
0x1800229cc  call    FormatRRASErrorString
0x1800229d1  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x1800229d8  lea     r8, [rsp+890h+var_840]
0x1800229dd  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800229e4  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800229eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229f0  mov     eax, edi
0x1800229f2  mov     rcx, [rbp+790h+var_40]
0x1800229f9  xor     rcx, rsp; StackCookie
0x1800229fc  call    __security_check_cookie
0x180022a01  mov     rbx, [rsp+890h+arg_18]
0x180022a09  add     rsp, 860h
0x180022a10  pop     r15
0x180022a12  pop     r14
0x180022a14  pop     r13
0x180022a16  pop     r12
0x180022a18  pop     rdi
0x180022a19  pop     rsi
0x180022a1a  pop     rbp
0x180022a1b  retn
```
