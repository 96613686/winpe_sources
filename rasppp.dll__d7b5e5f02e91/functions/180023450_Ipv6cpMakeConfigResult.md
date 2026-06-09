# Ipv6cpMakeConfigResult

- ea: `0x180023450`
- end: `0x1800236fd`
- name: `Ipv6cpMakeConfigResult`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180023450`
- `0x180023704`
- `0x180023a40`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## string_xrefs

- `0x1800234c6`: `IPv6CPMakeConfigResult`
- `0x180023698`: `IPv6CPMakeConfigResult: done %d`

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
  v9 = *((_QWORD *)&xmmword_18004D800 + 1);
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"IPv6CPMakeConfigResult");
    v9 = *((_QWORD *)&xmmword_18004D800 + 1);
  }
  v10 = qword_18004D820;
  if ( qword_18004D820 )
  {
    if ( a2 )
      v11 = *(unsigned __int8 *)(a2 + 3) + (*(unsigned __int8 *)(a2 + 2) << 8);
    else
      v11 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004D820,
      L"DumpingBytes",
      v11,
      a2);
    v10 = qword_18004D820;
    v9 = *((_QWORD *)&xmmword_18004D800 + 1);
  }
  if ( v9 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      v9,
      L"Remote Interface Id:");
    v10 = qword_18004D820;
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
      if ( *(_DWORD *)a1 != v12 && *(&xmmword_18004D4F0 + 1) )
      {
        v16 = *(_OWORD *)(a1 + 2084);
        (*(&xmmword_18004D4F0 + 1))(&v16, a1 + 80);
      }
      if ( *((_QWORD *)&xmmword_18004D800 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          *((_QWORD *)&xmmword_18004D800 + 1),
          L"Remote Interface Id:");
      if ( qword_18004D820 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, __int64))gRasIpv6cpByteTemplateFunc)(
          gRasIpv6cpEtwContext,
          qword_18004D820,
          L"DumpingBytes Remote Interface Id",
          8,
          a1 + 80);
      memcpy_0(a3, (const void *)a2, v3 + (v5 << 8));
      *a3 = 2;
    }
  }
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString((wchar_t *)&v17, L"IPv6CPMakeConfigResult: done %d", v12);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v17);
  }
  return v12;
}

```

## disassembly

```asm
0x180023450  mov     [rsp-8+arg_18], rbx
0x180023455  push    rbp
0x180023456  push    rsi
0x180023457  push    rdi
0x180023458  push    r12
0x18002345a  push    r13
0x18002345c  push    r14
0x18002345e  push    r15
0x180023460  lea     rbp, [rsp-760h]
0x180023468  sub     rsp, 860h
0x18002346f  mov     rax, cs:__security_cookie
0x180023476  xor     rax, rsp
0x180023479  mov     [rbp+790h+var_40], rax
0x180023480  movzx   r12d, byte ptr [rdx+3]
0x180023485  mov     r15, r8
0x180023488  movzx   r13d, byte ptr [rdx+2]
0x18002348d  mov     rbx, rdx
0x180023490  mov     r14, rcx
0x180023493  mov     [rsp+890h+var_860], 0
0x18002349b  xor     eax, eax
0x18002349d  lea     rcx, [rsp+890h+var_83C]; void *
0x1800234a2  xor     edx, edx; Val
0x1800234a4  mov     [rsp+890h+var_840], eax
0x1800234a8  mov     r8d, 7FCh; Size
0x1800234ae  call    memset_0
0x1800234b3  mov     rax, qword ptr cs:xmmword_18004D800+8
0x1800234ba  test    rax, rax
0x1800234bd  jz      short loc_1800234E3
0x1800234bf  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800234c6  lea     r8, aIpv6cpmakeconf; "IPv6CPMakeConfigResult"
0x1800234cd  mov     rdx, rax
0x1800234d0  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800234d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234dc  mov     rax, qword ptr cs:xmmword_18004D800+8
0x1800234e3  mov     rdx, cs:qword_18004D820
0x1800234ea  test    rdx, rdx
0x1800234ed  jz      short loc_180023536
0x1800234ef  test    rbx, rbx
0x1800234f2  jz      short loc_180023506
0x1800234f4  movzx   r9d, byte ptr [rbx+2]
0x1800234f9  movzx   eax, byte ptr [rbx+3]
0x1800234fd  shl     r9d, 8
0x180023501  add     r9d, eax
0x180023504  jmp     short loc_180023509
0x180023506  xor     r9d, r9d
0x180023509  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023510  lea     r8, aDumpingbytes; "DumpingBytes"
0x180023517  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002351e  mov     [rsp+890h+var_870], rbx
0x180023523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023528  mov     rdx, cs:qword_18004D820
0x18002352f  mov     rax, qword ptr cs:xmmword_18004D800+8
0x180023536  test    rax, rax
0x180023539  jz      short loc_18002355F
0x18002353b  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023542  lea     r8, aRemoteInterfac; "Remote Interface Id:"
0x180023549  mov     rdx, rax
0x18002354c  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180023553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023558  mov     rdx, cs:qword_18004D820
0x18002355f  test    rdx, rdx
0x180023562  jz      short loc_18002358D
0x180023564  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x18002356b  lea     rcx, [rbx+6]
0x18002356f  mov     [rsp+890h+var_870], rcx
0x180023574  lea     r8, aDumpingbytesRe_0; "DumpingBytes Remote Interface Id"
0x18002357b  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023582  mov     r9d, 8
0x180023588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002358d  lea     rax, [rsp+890h+var_860]
0x180023592  mov     r8, r15
0x180023595  mov     rdx, rbx
0x180023598  mov     [rsp+890h+var_870], rax
0x18002359d  mov     rcx, r14
0x1800235a0  call    Ipv6cpRejectCheck
0x1800235a5  mov     edi, eax
0x1800235a7  test    eax, eax
0x1800235a9  jnz     loc_18002368C
0x1800235af  cmp     [rsp+890h+var_860], eax
0x1800235b3  jnz     loc_18002368C
0x1800235b9  lea     rax, [rsp+890h+var_860]
0x1800235be  mov     r8, r15
0x1800235c1  mov     rdx, rbx
0x1800235c4  mov     [rsp+890h+var_870], rax
0x1800235c9  mov     rcx, r14
0x1800235cc  call    Ipv6cpNakCheck
0x1800235d1  mov     edi, eax
0x1800235d3  test    eax, eax
0x1800235d5  jnz     loc_18002368C
0x1800235db  cmp     [rsp+890h+var_860], eax
0x1800235df  jnz     loc_18002368C
0x1800235e5  lea     rsi, [r14+50h]
0x1800235e9  mov     rax, [rbx+6]
0x1800235ed  mov     [rsi], rax
0x1800235f0  cmp     [r14], edi
0x1800235f3  jz      short loc_18002361C
0x1800235f5  mov     rax, qword ptr cs:xmmword_18004D4F0+8
0x1800235fc  test    rax, rax
0x1800235ff  jz      short loc_18002361C
0x180023601  movups  xmm0, xmmword ptr [r14+824h]
0x180023609  mov     rdx, rsi
0x18002360c  lea     rcx, [rsp+890h+var_850]
0x180023611  movdqu  [rsp+890h+var_850], xmm0
0x180023617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002361c  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180023623  test    rdx, rdx
0x180023626  jz      short loc_180023642
0x180023628  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002362f  lea     r8, aRemoteInterfac; "Remote Interface Id:"
0x180023636  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002363d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023642  mov     rdx, cs:qword_18004D820
0x180023649  test    rdx, rdx
0x18002364c  jz      short loc_180023673
0x18002364e  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023655  lea     r8, aDumpingbytesRe_0; "DumpingBytes Remote Interface Id"
0x18002365c  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x180023663  mov     r9d, 8
0x180023669  mov     [rsp+890h+var_870], rsi
0x18002366e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023673  mov     r8, r13
0x180023676  mov     rdx, rbx; Src
0x180023679  shl     r8, 8
0x18002367d  mov     rcx, r15; void *
0x180023680  add     r8, r12; Size
0x180023683  call    memcpy_0
0x180023688  mov     byte ptr [r15], 2
0x18002368c  cmp     qword ptr cs:xmmword_18004D800+8, 0
0x180023694  jz      short loc_1800236D0
0x180023696  xor     eax, eax
0x180023698  lea     rdx, aIpv6cpmakeconf_0; "IPv6CPMakeConfigResult: done %d"
0x18002369f  mov     r8d, edi
0x1800236a2  mov     word ptr [rsp+890h+var_840], ax
0x1800236a7  lea     rcx, [rsp+890h+var_840]
0x1800236ac  call    FormatRRASErrorString
0x1800236b1  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800236b8  lea     r8, [rsp+890h+var_840]
0x1800236bd  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800236c4  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800236cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236d0  mov     eax, edi
0x1800236d2  mov     rcx, [rbp+790h+var_40]
0x1800236d9  xor     rcx, rsp; StackCookie
0x1800236dc  call    __security_check_cookie
0x1800236e1  mov     rbx, [rsp+890h+arg_18]
0x1800236e9  add     rsp, 860h
0x1800236f0  pop     r15
0x1800236f2  pop     r14
0x1800236f4  pop     r13
0x1800236f6  pop     r12
0x1800236f8  pop     rdi
0x1800236f9  pop     rsi
0x1800236fa  pop     rbp
0x1800236fb  retn
```
