# MRSTARTDOC::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180097360`
- end: `0x1800974f6`
- name: `?bPlay@MRSTARTDOC@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `406`
- prototype: `__int64 __fastcall(MRSTARTDOC *__hidden this, HDC hdc, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016350`

## callees

- `0x18002dfb4`
- `0x18007f800`
- `0x1800948cc`
- `0x180095220`
- `0x180097360`

## import_xrefs

- `GDI32!StartDocW` at `0x1800974e5`
- `GDI32!StartDocW` at `0x1800974e5`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18009743a`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800974b3`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800974d2`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18009743a`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800974b3`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800974d2`

## pseudocode

```c
int __fastcall MRSTARTDOC::bPlay(MRSTARTDOC *this, HDC hdc, struct tagHANDLETABLE *a3)
{
  __int64 v3; // rdi
  bool v7; // zf
  const WCHAR *v8; // rbx
  char *v9; // r14
  __int128 v10; // xmm0
  __int64 v11; // xmm1_8
  unsigned __int64 v12; // rdi
  DOCINFOW v14; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v15[12]; // [rsp+48h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-18h] BYREF
  __int64 v17; // [rsp+5Ch] [rbp-14h]

  v3 = *((unsigned int *)this + 1);
  memset(&v14, 0, sizeof(v14));
  if ( !MRSTARTDOC::bCheckRecord(this, a3) )
    return 0;
  v7 = *((_QWORD *)this + 2) == 0;
  v8 = (const WCHAR *)((char *)this + 48);
  v9 = (char *)this + v3;
  v10 = *(_OWORD *)((char *)this + 24);
  v11 = *((_QWORD *)this + 5);
  *(_OWORD *)&v14.cbSize = *(_OWORD *)((char *)this + 8);
  *(_OWORD *)&v14.lpszOutput = v10;
  *(_QWORD *)&v14.fwType = v11;
  if ( !v7 )
  {
    v14.lpszDocName = (LPCWSTR)((char *)this + 48);
    *(_QWORD *)v15 = 0;
    if ( (int)StringCbLengthW((const unsigned __int16 *)this + 24, v9 - (char *)v8, (unsigned __int64 *)v15) < 0 )
      return 0;
    v12 = (*(_QWORD *)v15 + 6LL) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v14.lpszOutput && !(unsigned int)MR::bValidOff(this, a3, (int)v12 + 48) )
    {
      *(_DWORD *)v15 = 57104089;
LABEL_7:
      *(_QWORD *)&v15[4] = 1;
      RtlLogUnexpectedCodepath(v15);
      return 0;
    }
    v8 = (const WCHAR *)((char *)v8 + v12);
  }
  if ( v14.lpszOutput )
  {
    v14.lpszOutput = v8;
    if ( (int)StringCbLengthW(v8, v9 - (char *)v8, (unsigned __int64 *)v15) < 0 )
    {
      *(_DWORD *)v15 = 39644700;
      goto LABEL_7;
    }
  }
  if ( v14.lpszDatatype )
  {
    v14.lpszDatatype = 0;
    *(_DWORD *)v15 = 39644700;
    *(_QWORD *)&v15[4] = 3;
    RtlLogUnexpectedCodepath(v15);
  }
  v16 = 57104089;
  v17 = 2;
  RtlLogUnexpectedCodepath(&v16);
  return StartDocW(hdc, &v14);
}

```

## disassembly

```asm
0x180097360  push    rbp
0x180097362  push    rbx
0x180097363  push    rsi
0x180097364  push    rdi
0x180097365  push    r12
0x180097367  push    r14
0x180097369  push    r15
0x18009736b  mov     rbp, rsp
0x18009736e  sub     rsp, 70h
0x180097372  mov     rax, cs:__security_cookie
0x180097379  xor     rax, rsp
0x18009737c  mov     [rbp+var_8], rax
0x180097380  mov     edi, [rcx+4]
0x180097383  xorps   xmm0, xmm0
0x180097386  mov     r12, rdx
0x180097389  xor     eax, eax
0x18009738b  mov     rdx, r8; struct tagHANDLETABLE *
0x18009738e  mov     qword ptr [rbp+var_50.fwType], rax
0x180097392  movups  xmmword ptr [rbp+var_50.cbSize], xmm0
0x180097396  mov     r15, r8
0x180097399  mov     rsi, rcx
0x18009739c  movups  xmmword ptr [rbp+var_50.lpszOutput], xmm0
0x1800973a0  call    ?bCheckRecord@MRSTARTDOC@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTARTDOC::bCheckRecord(tagHANDLETABLE *)
0x1800973a5  test    eax, eax
0x1800973a7  jz      loc_180097446
0x1800973ad  cmp     qword ptr [rsi+10h], 0
0x1800973b2  lea     rbx, [rsi+30h]
0x1800973b6  movups  xmm2, xmmword ptr [rsi+8]
0x1800973ba  lea     r14, [rsi+rdi]
0x1800973be  movups  xmm0, xmmword ptr [rsi+18h]
0x1800973c2  movsd   xmm1, qword ptr [rsi+28h]
0x1800973c7  movups  xmmword ptr [rbp+var_50.cbSize], xmm2
0x1800973cb  movups  xmmword ptr [rbp+var_50.lpszOutput], xmm0
0x1800973cf  movsd   qword ptr [rbp+var_50.fwType], xmm1
0x1800973d4  jz      loc_180097467
0x1800973da  mov     rdx, r14
0x1800973dd  mov     [rbp+var_50.lpszDocName], rbx
0x1800973e1  sub     rdx, rbx; unsigned __int64
0x1800973e4  mov     [rbp+var_28], 0
0x1800973ec  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1800973f0  mov     rcx, rbx; unsigned __int16 *
0x1800973f3  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800973f8  test    eax, eax
0x1800973fa  js      short loc_180097446
0x1800973fc  mov     rdi, [rbp+var_28]
0x180097400  add     rdi, 6
0x180097404  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180097408  cmp     [rbp+var_50.lpszOutput], 0
0x18009740d  jz      short loc_180097464
0x18009740f  mov     r8d, ebx
0x180097412  mov     rdx, r15; struct tagHANDLETABLE *
0x180097415  sub     r8d, esi
0x180097418  mov     rcx, rsi; this
0x18009741b  add     r8d, edi; unsigned int
0x18009741e  call    ?bValidOff@MR@@QEAAHPEAUtagHANDLETABLE@@K@Z; MR::bValidOff(tagHANDLETABLE *,ulong)
0x180097423  test    eax, eax
0x180097425  jnz     short loc_180097464
0x180097427  mov     dword ptr [rbp+var_28], 36756D9h
0x18009742e  lea     rcx, [rbp+var_28]
0x180097432  mov     [rbp+var_28+4], 1
0x18009743a  call    cs:__imp_RtlLogUnexpectedCodepath
0x180097441  nop     dword ptr [rax+rax+00h]
0x180097446  xor     eax, eax
0x180097448  mov     rcx, [rbp+var_8]
0x18009744c  xor     rcx, rsp; StackCookie
0x18009744f  call    __security_check_cookie
0x180097454  add     rsp, 70h
0x180097458  pop     r15
0x18009745a  pop     r14
0x18009745c  pop     r12
0x18009745e  pop     rdi
0x18009745f  pop     rsi
0x180097460  pop     rbx
0x180097461  pop     rbp
0x180097462  retn
0x180097464  add     rbx, rdi
0x180097467  cmp     [rbp+var_50.lpszOutput], 0
0x18009746c  jz      short loc_180097491
0x18009746e  sub     r14, rbx
0x180097471  mov     [rbp+var_50.lpszOutput], rbx
0x180097475  mov     rdx, r14; unsigned __int64
0x180097478  lea     r8, [rbp+var_28]; unsigned __int64 *
0x18009747c  mov     rcx, rbx; unsigned __int16 *
0x18009747f  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180097484  test    eax, eax
0x180097486  jns     short loc_180097491
0x180097488  mov     dword ptr [rbp+var_28], 25CEE1Ch
0x18009748f  jmp     short loc_18009742E
0x180097491  cmp     [rbp+var_50.lpszDatatype], 0
0x180097496  jz      short loc_1800974BF
0x180097498  lea     rcx, [rbp+var_28]
0x18009749c  mov     [rbp+var_50.lpszDatatype], 0
0x1800974a4  mov     dword ptr [rbp+var_28], 25CEE1Ch
0x1800974ab  mov     [rbp+var_28+4], 3
0x1800974b3  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800974ba  nop     dword ptr [rax+rax+00h]
0x1800974bf  lea     rcx, [rbp+var_18]
0x1800974c3  mov     [rbp+var_18], 36756D9h
0x1800974ca  mov     [rbp+var_14], 2
0x1800974d2  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800974d9  nop     dword ptr [rax+rax+00h]
0x1800974de  lea     rdx, [rbp+var_50]; lpdi
0x1800974e2  mov     rcx, r12; hdc
0x1800974e5  call    cs:__imp_StartDocW
0x1800974ec  nop     dword ptr [rax+rax+00h]
0x1800974f1  jmp     loc_180097448
```
