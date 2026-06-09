# MRSTARTDOC::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x1800917d0`
- end: `0x18009194d`
- name: `?bPlay@MRSTARTDOC@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `381`
- prototype: `int __fastcall(MRSTARTDOC *this, HDC hdc, struct tagHANDLETABLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800305e0`

## callees

- `0x180024f34`
- `0x18007ac50`
- `0x18008eeb4`
- `0x18008f7f0`
- `0x1800917d0`

## import_xrefs

- `GDI32!StartDocW` at `0x180091942`
- `GDI32!StartDocW` at `0x180091942`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800918aa`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18009191c`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180091935`
- `ntdll!RtlLogUnexpectedCodepath` at `0x1800918aa`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18009191c`
- `ntdll!RtlLogUnexpectedCodepath` at `0x180091935`

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
0x1800917d0  push    rbp
0x1800917d2  push    rbx
0x1800917d3  push    rsi
0x1800917d4  push    rdi
0x1800917d5  push    r12
0x1800917d7  push    r14
0x1800917d9  push    r15
0x1800917db  mov     rbp, rsp
0x1800917de  sub     rsp, 70h
0x1800917e2  mov     rax, cs:__security_cookie
0x1800917e9  xor     rax, rsp
0x1800917ec  mov     [rbp+var_8], rax
0x1800917f0  mov     edi, [rcx+4]
0x1800917f3  xorps   xmm0, xmm0
0x1800917f6  mov     r12, rdx
0x1800917f9  xor     eax, eax
0x1800917fb  mov     rdx, r8; struct tagHANDLETABLE *
0x1800917fe  mov     qword ptr [rbp+var_50.fwType], rax
0x180091802  movups  xmmword ptr [rbp+var_50.cbSize], xmm0
0x180091806  mov     r15, r8
0x180091809  mov     rsi, rcx
0x18009180c  movups  xmmword ptr [rbp+var_50.lpszOutput], xmm0
0x180091810  call    ?bCheckRecord@MRSTARTDOC@@QEAAHPEAUtagHANDLETABLE@@@Z; MRSTARTDOC::bCheckRecord(tagHANDLETABLE *)
0x180091815  test    eax, eax
0x180091817  jz      loc_1800918B0
0x18009181d  cmp     qword ptr [rsi+10h], 0
0x180091822  lea     rbx, [rsi+30h]
0x180091826  movups  xmm2, xmmword ptr [rsi+8]
0x18009182a  lea     r14, [rsi+rdi]
0x18009182e  movups  xmm0, xmmword ptr [rsi+18h]
0x180091832  movsd   xmm1, qword ptr [rsi+28h]
0x180091837  movups  xmmword ptr [rbp+var_50.cbSize], xmm2
0x18009183b  movups  xmmword ptr [rbp+var_50.lpszOutput], xmm0
0x18009183f  movsd   qword ptr [rbp+var_50.fwType], xmm1
0x180091844  jz      loc_1800918D0
0x18009184a  mov     rdx, r14
0x18009184d  mov     [rbp+var_50.lpszDocName], rbx
0x180091851  sub     rdx, rbx; unsigned __int64
0x180091854  mov     [rbp+var_28], 0
0x18009185c  lea     r8, [rbp+var_28]; unsigned __int64 *
0x180091860  mov     rcx, rbx; unsigned __int16 *
0x180091863  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180091868  test    eax, eax
0x18009186a  js      short loc_1800918B0
0x18009186c  mov     rdi, [rbp+var_28]
0x180091870  add     rdi, 6
0x180091874  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180091878  cmp     [rbp+var_50.lpszOutput], 0
0x18009187d  jz      short loc_1800918CD
0x18009187f  mov     r8d, ebx
0x180091882  mov     rdx, r15; struct tagHANDLETABLE *
0x180091885  sub     r8d, esi
0x180091888  mov     rcx, rsi; this
0x18009188b  add     r8d, edi; unsigned int
0x18009188e  call    ?bValidOff@MR@@QEAAHPEAUtagHANDLETABLE@@K@Z; MR::bValidOff(tagHANDLETABLE *,ulong)
0x180091893  test    eax, eax
0x180091895  jnz     short loc_1800918CD
0x180091897  mov     dword ptr [rbp+var_28], 36756D9h
0x18009189e  lea     rcx, [rbp+var_28]
0x1800918a2  mov     [rbp+var_28+4], 1
0x1800918aa  call    cs:__imp_RtlLogUnexpectedCodepath
0x1800918b0  xor     eax, eax
0x1800918b2  mov     rcx, [rbp+var_8]
0x1800918b6  xor     rcx, rsp; StackCookie
0x1800918b9  call    __security_check_cookie
0x1800918be  add     rsp, 70h
0x1800918c2  pop     r15
0x1800918c4  pop     r14
0x1800918c6  pop     r12
0x1800918c8  pop     rdi
0x1800918c9  pop     rsi
0x1800918ca  pop     rbx
0x1800918cb  pop     rbp
0x1800918cc  retn
0x1800918cd  add     rbx, rdi
0x1800918d0  cmp     [rbp+var_50.lpszOutput], 0
0x1800918d5  jz      short loc_1800918FA
0x1800918d7  sub     r14, rbx
0x1800918da  mov     [rbp+var_50.lpszOutput], rbx
0x1800918de  mov     rdx, r14; unsigned __int64
0x1800918e1  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1800918e5  mov     rcx, rbx; unsigned __int16 *
0x1800918e8  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800918ed  test    eax, eax
0x1800918ef  jns     short loc_1800918FA
0x1800918f1  mov     dword ptr [rbp+var_28], 25CEE1Ch
0x1800918f8  jmp     short loc_18009189E
0x1800918fa  cmp     [rbp+var_50.lpszDatatype], 0
0x1800918ff  jz      short loc_180091922
0x180091901  lea     rcx, [rbp+var_28]
0x180091905  mov     [rbp+var_50.lpszDatatype], 0
0x18009190d  mov     dword ptr [rbp+var_28], 25CEE1Ch
0x180091914  mov     [rbp+var_28+4], 3
0x18009191c  call    cs:__imp_RtlLogUnexpectedCodepath
0x180091922  lea     rcx, [rbp+var_18]
0x180091926  mov     [rbp+var_18], 36756D9h
0x18009192d  mov     [rbp+var_14], 2
0x180091935  call    cs:__imp_RtlLogUnexpectedCodepath
0x18009193b  lea     rdx, [rbp+var_50]; lpdi
0x18009193f  mov     rcx, r12; hdc
0x180091942  call    cs:__imp_StartDocW
0x180091948  jmp     loc_1800918B2
```
