# NameMapper::prependDefaultDomain(ushort const *)

- ea: `0x180021a40`
- end: `0x180021b29`
- name: `?prependDefaultDomain@NameMapper@@IEAAPEAGPEBG@Z`
- size: `233`
- prototype: `unsigned __int16 *(NameMapper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002110c`
- `0x1800213d0`

## callees

- `0x180001f26`
- `0x18000c4a4`
- `0x18000c808`
- `0x180021a40`
- `0x1800254a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021ad1`

## pseudocode

```c
char *__fastcall NameMapper::prependDefaultDomain(NameMapper *this, const unsigned __int16 *a2)
{
  wchar_t *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rbx
  unsigned int v6; // r14d
  char *v7; // rdi
  size_t v8; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("NameMapper::prependDefaultDomain");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids, "NPSSVC");
  }
  v3 = theDefaultDomain;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( theDefaultDomain[v5] );
  do
    ++v4;
  while ( a2[v4] );
  v6 = v4 + 1;
  v7 = (char *)CoTaskMemAlloc(2LL * (unsigned int)(v5 + v4 + 2));
  if ( !v7 )
    _com_issue_error(-2147024882);
  v8 = 2LL * (unsigned int)v5;
  memcpy_0(v7, v3, v8);
  *(_WORD *)&v7[v8] = 92;
  memcpy_0(&v7[v8 + 2], a2, 2LL * v6);
  return v7;
}

```

## disassembly

```asm
0x180021a40  push    rbx
0x180021a42  push    rbp
0x180021a43  push    rsi
0x180021a44  push    rdi
0x180021a45  push    r14
0x180021a47  push    r15
0x180021a49  sub     rsp, 28h
0x180021a4d  mov     rbp, rdx
0x180021a50  mov     rax, cs:WPP_GLOBAL_Control
0x180021a57  lea     rcx, WPP_GLOBAL_Control
0x180021a5e  cmp     rax, rcx
0x180021a61  jz      short loc_180021A9E
0x180021a63  cmp     byte ptr [rax+19h], 4
0x180021a67  jb      short loc_180021A9E
0x180021a69  test    byte ptr [rax+1Ch], 4
0x180021a6d  jz      short loc_180021A9E
0x180021a6f  lea     rcx, aNamemapperPrep; "NameMapper::prependDefaultDomain"
0x180021a76  call    WppDbgPrint
0x180021a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a82  lea     r9, aNpssvc; "NPSSVC"
0x180021a89  mov     edx, 12h
0x180021a8e  lea     r8, WPP_40bf13076849362e12b869b0ef4fb463_Traceguids
0x180021a95  mov     rcx, [rcx+10h]
0x180021a99  call    WPP_SF_s
0x180021a9e  mov     rsi, cs:theDefaultDomain
0x180021aa5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021aa9  mov     rbx, rax
0x180021aac  xor     r15d, r15d
0x180021aaf  inc     rbx
0x180021ab2  cmp     [rsi+rbx*2], r15w
0x180021ab7  jnz     short loc_180021AAF
0x180021ab9  inc     rax
0x180021abc  cmp     [rbp+rax*2+0], r15w
0x180021ac2  jnz     short loc_180021AB9
0x180021ac4  lea     r14d, [rax+1]
0x180021ac8  lea     ecx, [r14+1]
0x180021acc  add     ecx, ebx
0x180021ace  add     rcx, rcx; cb
0x180021ad1  call    cs:__imp_CoTaskMemAlloc
0x180021ad7  mov     rdi, rax
0x180021ada  test    rax, rax
0x180021add  jnz     short loc_180021AEA
0x180021adf  mov     ecx, 8007000Eh; int
0x180021ae4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180021aea  mov     eax, ebx
0x180021aec  mov     rdx, rsi; Src
0x180021aef  mov     rcx, rdi; void *
0x180021af2  lea     rbx, [rax+rax]
0x180021af6  mov     r8, rbx; Size
0x180021af9  call    memcpy_0
0x180021afe  mov     r8d, r14d
0x180021b01  lea     rcx, [rbx+2]
0x180021b05  add     r8, r8; Size
0x180021b08  mov     word ptr [rbx+rdi], 5Ch ; '\'
0x180021b0e  add     rcx, rdi; void *
0x180021b11  mov     rdx, rbp; Src
0x180021b14  call    memcpy_0
0x180021b19  mov     rax, rdi
0x180021b1c  add     rsp, 28h
0x180021b20  pop     r15
0x180021b22  pop     r14
0x180021b24  pop     rdi
0x180021b25  pop     rsi
0x180021b26  pop     rbp
0x180021b27  pop     rbx
0x180021b28  retn
```
