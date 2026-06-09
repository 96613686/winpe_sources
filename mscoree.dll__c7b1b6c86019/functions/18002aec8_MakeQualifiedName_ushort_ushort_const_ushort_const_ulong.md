# MakeQualifiedName(ushort *,ushort const *,ushort const *,ulong *)

- ea: `0x18002aec8`
- end: `0x18002b193`
- name: `?MakeQualifiedName@@YAPEAGPEAGPEBG1PEAK@Z`
- size: `715`
- prototype: `unsigned __int16 *__fastcall(wchar_t *Source, const unsigned __int16 *, wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a8b4`

## callees

- `0x180003070`
- `0x180003740`
- `0x180006130`
- `0x18000d434`
- `0x18000d614`
- `0x18002aec8`
- `0x180031668`
- `0x18003fad8`
- `0x180041ac0`

## string_xrefs

- `0x18002b102`: `mscor.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall MakeQualifiedName(wchar_t *Source, unsigned __int16 *a2, wchar_t *a3, unsigned int *a4)
{
  const wchar_t *v5; // rdi
  __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // rdx
  rsize_t v15; // r14
  unsigned __int128 v16; // rax
  unsigned __int64 v17; // kr10_8
  wchar_t *v18; // rbx
  void *v19; // rsp
  void *v20; // rsp
  wchar_t v22[16]; // [rsp+30h] [rbp-40h] BYREF
  wchar_t Sourcea[16]; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+70h] [rbp+0h] BYREF
  wchar_t *v25; // [rsp+78h] [rbp+8h] BYREF
  BOOL v26; // [rsp+80h] [rbp+10h]
  _BYTE v27[48]; // [rsp+88h] [rbp+18h] BYREF

  v5 = a3;
  if ( a3 && *a3 )
  {
    if ( !g_bSingleProc )
      goto LABEL_7;
    if ( !wcsnicmp(L"svr", a3, 3u) )
      *a4 &= ~1u;
  }
  v5 = L"wks";
LABEL_7:
  v24 = 0;
  if ( ((int)Version::SetVersionNumber((Version *)v27, a2, &v24) < 0
     || v24 != 3
     || wcsnicmp(L"v1.0", a2, 4u) && wcsnicmp(L"v1.1", a2, 4u))
    && !wcsnicmp(L"svr", v5, 3u) )
  {
    *a4 |= 0x1000u;
    v5 = L"wks";
  }
  v8 = -1;
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
  }
  else
  {
    v9 = 0;
  }
  if ( Source )
  {
    v10 = -1;
    do
      ++v10;
    while ( Source[v10] );
  }
  else
  {
    v10 = 0;
  }
  if ( ~v10 < v9 || ~(v10 + v9) < 9 )
    return 0;
  v11 = v10 + v9 + 9;
  if ( v5 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v5[v12] );
  }
  else
  {
    v12 = 0;
  }
  if ( ~v11 < v12 )
    return 0;
  v13 = v11 + v12;
  v14 = 2 - ((unsigned __int128)-(__int128)(unsigned __int64)Source >> 64);
  if ( ~(v11 + v12) < v14 )
    return 0;
  v15 = v14 + v13;
  v17 = v14 + v13;
  v16 = (v14 + v13) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v17, 2u) )
    *(_QWORD *)&v16 = -1;
  v18 = (wchar_t *)operator new(v16, *((const struct NoThrow **)&v16 + 1));
  v25 = v18;
  v26 = v18 != 0;
  if ( !v18 || (int)CreateVersionDirectory(Source, a2, v18, v15) < 0 )
  {
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v25);
    return 0;
  }
  do
    ++v8;
  while ( v18[v8] );
  if ( v18[v8 - 1] != 92 )
    wcscat_s(v18, v15, L"\\");
  v19 = alloca(32);
  v20 = alloca(32);
  SplitPath((wchar_t *)L"mscor.dll", 0, 0, 0, 0, Sourcea, 0xAu, v22, 0xAu);
  if ( Sourcea )
    wcscat_s(v18, v15, Sourcea);
  if ( v5 )
    wcscat_s(v18, v15, v5);
  if ( v22 )
    wcscat_s(v18, v15, v22);
  wcscat_s(v18, v15, &word_18005010C);
  v26 = 0;
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v25);
  return v18;
}

```

## disassembly

```asm
0x18002aec8  push    rbp
0x18002aeca  push    rbx
0x18002aecb  push    rsi
0x18002aecc  push    rdi
0x18002aecd  push    r12
0x18002aecf  push    r13
0x18002aed1  push    r14
0x18002aed3  push    r15
0x18002aed5  sub     rsp, 0A8h
0x18002aedc  lea     rbp, [rsp+50h]
0x18002aee1  mov     rax, cs:__security_cookie
0x18002aee8  xor     rax, rbp
0x18002aeeb  mov     [rbp+90h+var_48], rax
0x18002aeef  mov     rbx, r9
0x18002aef2  mov     rdi, r8
0x18002aef5  mov     r15, rdx
0x18002aef8  mov     r12, rcx
0x18002aefb  mov     r14d, 3
0x18002af01  lea     rsi, aWks; "wks"
0x18002af08  xor     r13d, r13d
0x18002af0b  test    r8, r8
0x18002af0e  jz      short loc_18002AF38
0x18002af10  cmp     [r8], r13w
0x18002af14  jz      short loc_18002AF38
0x18002af16  cmp     cs:?g_bSingleProc@@3HA, r13d; int g_bSingleProc
0x18002af1d  jz      short loc_18002AF3B
0x18002af1f  mov     r8d, r14d; MaxCount
0x18002af22  mov     rdx, rdi; String2
0x18002af25  lea     rcx, aSvr; "svr"
0x18002af2c  call    _wcsnicmp
0x18002af31  test    eax, eax
0x18002af33  jnz     short loc_18002AF38
0x18002af35  and     dword ptr [rbx], 0FFFFFFFEh
0x18002af38  mov     rdi, rsi
0x18002af3b  mov     [rbp+90h+var_90], r13d
0x18002af3f  lea     r8, [rbp+90h+var_90]; unsigned int *
0x18002af43  mov     rdx, r15; unsigned __int16 *
0x18002af46  lea     rcx, [rbp+90h+var_78]; this
0x18002af4a  call    ?SetVersionNumber@Version@@QEAAJPEBGPEAK@Z; Version::SetVersionNumber(ushort const *,ulong *)
0x18002af4f  test    eax, eax
0x18002af51  js      short loc_18002AF8B
0x18002af53  cmp     [rbp+90h+var_90], r14d
0x18002af57  jnz     short loc_18002AF8B
0x18002af59  mov     r8d, 4; MaxCount
0x18002af5f  mov     rdx, r15; String2
0x18002af62  lea     rcx, aV10; "v1.0"
0x18002af69  call    _wcsnicmp
0x18002af6e  test    eax, eax
0x18002af70  jz      short loc_18002AFA8
0x18002af72  mov     r8d, 4; MaxCount
0x18002af78  mov     rdx, r15; String2
0x18002af7b  lea     rcx, aV11; "v1.1"
0x18002af82  call    _wcsnicmp
0x18002af87  test    eax, eax
0x18002af89  jz      short loc_18002AFA8
0x18002af8b  mov     r8, r14; MaxCount
0x18002af8e  mov     rdx, rdi; String2
0x18002af91  lea     rcx, aSvr; "svr"
0x18002af98  call    _wcsnicmp
0x18002af9d  test    eax, eax
0x18002af9f  jnz     short loc_18002AFA8
0x18002afa1  bts     dword ptr [rbx], 0Ch
0x18002afa5  mov     rdi, rsi
0x18002afa8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002afac  test    r15, r15
0x18002afaf  jz      short loc_18002AFC0
0x18002afb1  mov     rdx, rsi
0x18002afb4  inc     rdx
0x18002afb7  cmp     [r15+rdx*2], r13w
0x18002afbc  jnz     short loc_18002AFB4
0x18002afbe  jmp     short loc_18002AFC3
0x18002afc0  mov     rdx, r13
0x18002afc3  test    r12, r12
0x18002afc6  jz      short loc_18002AFD7
0x18002afc8  mov     rcx, rsi
0x18002afcb  inc     rcx
0x18002afce  cmp     [r12+rcx*2], r13w
0x18002afd3  jnz     short loc_18002AFCB
0x18002afd5  jmp     short loc_18002AFDA
0x18002afd7  mov     rcx, r13
0x18002afda  mov     rax, rcx
0x18002afdd  not     rax
0x18002afe0  cmp     rax, rdx
0x18002afe3  jb      loc_18002B174
0x18002afe9  lea     r8, [rcx+rdx]
0x18002afed  mov     rax, r8
0x18002aff0  not     rax
0x18002aff3  cmp     rax, 9
0x18002aff7  jb      loc_18002B174
0x18002affd  add     r8, 9
0x18002b001  test    rdi, rdi
0x18002b004  jz      short loc_18002B015
0x18002b006  mov     rcx, rsi
0x18002b009  inc     rcx
0x18002b00c  cmp     [rdi+rcx*2], r13w
0x18002b011  jnz     short loc_18002B009
0x18002b013  jmp     short loc_18002B018
0x18002b015  mov     rcx, r13
0x18002b018  mov     rax, r8
0x18002b01b  not     rax
0x18002b01e  cmp     rax, rcx
0x18002b021  jb      loc_18002B174
0x18002b027  lea     r9, [r8+rcx]
0x18002b02b  mov     rax, r12
0x18002b02e  neg     rax
0x18002b031  sbb     rdx, rdx
0x18002b034  neg     rdx
0x18002b037  mov     eax, 2
0x18002b03c  add     rdx, rax; struct NoThrow *
0x18002b03f  mov     rcx, r9
0x18002b042  not     rcx
0x18002b045  cmp     rcx, rdx
0x18002b048  jb      loc_18002B174
0x18002b04e  lea     r14, [rdx+r9]
0x18002b052  mul     r14
0x18002b055  cmovb   rax, rsi
0x18002b059  mov     rcx, rax; unsigned __int64
0x18002b05c  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002b061  mov     rbx, rax
0x18002b064  mov     [rbp+90h+var_88], rax
0x18002b068  mov     eax, r13d
0x18002b06b  mov     edx, 1
0x18002b070  test    rbx, rbx
0x18002b073  cmovnz  eax, edx
0x18002b076  mov     [rbp+90h+var_80], eax
0x18002b079  jz      loc_18002B16B
0x18002b07f  mov     r9, r14; SizeInWords
0x18002b082  mov     r8, rbx; Destination
0x18002b085  mov     rdx, r15; wchar_t *
0x18002b088  mov     rcx, r12; Source
0x18002b08b  call    ?CreateVersionDirectory@@YAJPEAGPEBG0_K@Z; CreateVersionDirectory(ushort *,ushort const *,ushort *,unsigned __int64)
0x18002b090  test    eax, eax
0x18002b092  js      loc_18002B16B
0x18002b098  inc     rsi
0x18002b09b  cmp     [rbx+rsi*2], r13w
0x18002b0a0  jnz     short loc_18002B098
0x18002b0a2  cmp     word ptr [rbx+rsi*2-2], 5Ch ; '\'
0x18002b0a8  jz      short loc_18002B0BC
0x18002b0aa  lea     r8, asc_18004C8C0; "\\"
0x18002b0b1  mov     rdx, r14; SizeInWords
0x18002b0b4  mov     rcx, rbx; Destination
0x18002b0b7  call    wcscat_s
0x18002b0bc  mov     eax, dword ptr [rsp+0E0h+var_E0]
0x18002b0bf  mov     eax, 20h ; ' '
0x18002b0c4  sub     rsp, rax
0x18002b0c7  lea     r15, [rsp+100h+Source]
0x18002b0cc  mov     ecx, [r15]
0x18002b0cf  mov     ecx, [rsp+100h+var_100]
0x18002b0d2  sub     rsp, rax
0x18002b0d5  lea     rsi, [rsp+120h+var_D0]
0x18002b0da  mov     eax, [rsi]
0x18002b0dc  mov     eax, 0Ah
0x18002b0e1  mov     [rsp+120h+var_E0], rax; unsigned __int64
0x18002b0e6  mov     [rsp+120h+var_E8], rsi; unsigned __int16 *
0x18002b0eb  mov     [rsp+120h+SizeInWords], rax; SizeInWords
0x18002b0f0  mov     [rsp+120h+var_F8], r15; wchar_t *
0x18002b0f5  mov     [rsp+120h+var_100], r13d; int
0x18002b0fa  xor     r9d, r9d; unsigned __int16 *
0x18002b0fd  xor     r8d, r8d; int
0x18002b100  xor     edx, edx; Destination
0x18002b102  lea     rcx, aMscorDll; "mscor.dll"
0x18002b109  call    ?SplitPath@@YAXPEBGPEAGH1H1_K12@Z; SplitPath(ushort const *,ushort *,int,ushort *,int,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18002b10e  test    r15, r15
0x18002b111  jz      short loc_18002B121
0x18002b113  mov     r8, r15; Source
0x18002b116  mov     rdx, r14; SizeInWords
0x18002b119  mov     rcx, rbx; Destination
0x18002b11c  call    wcscat_s
0x18002b121  test    rdi, rdi
0x18002b124  jz      short loc_18002B134
0x18002b126  mov     r8, rdi; Source
0x18002b129  mov     rdx, r14; SizeInWords
0x18002b12c  mov     rcx, rbx; Destination
0x18002b12f  call    wcscat_s
0x18002b134  test    rsi, rsi
0x18002b137  jz      short loc_18002B147
0x18002b139  mov     r8, rsi; Source
0x18002b13c  mov     rdx, r14; SizeInWords
0x18002b13f  mov     rcx, rbx; Destination
0x18002b142  call    wcscat_s
0x18002b147  lea     r8, word_18005010C; Source
0x18002b14e  mov     rdx, r14; SizeInWords
0x18002b151  mov     rcx, rbx; Destination
0x18002b154  call    wcscat_s
0x18002b159  mov     [rbp+90h+var_80], r13d
0x18002b15d  lea     rcx, [rbp+90h+var_88]
0x18002b161  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18002b166  mov     rax, rbx
0x18002b169  jmp     short loc_18002B176
0x18002b16b  lea     rcx, [rbp+90h+var_88]
0x18002b16f  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18002b174  xor     eax, eax
0x18002b176  mov     rcx, [rbp+90h+var_48]
0x18002b17a  xor     rcx, rbp; StackCookie
0x18002b17d  call    __security_check_cookie
0x18002b182  lea     rsp, [rbp+58h]
0x18002b186  pop     r15
0x18002b188  pop     r14
0x18002b18a  pop     r13
0x18002b18c  pop     r12
0x18002b18e  pop     rdi
0x18002b18f  pop     rsi
0x18002b190  pop     rbx
0x18002b191  pop     rbp
0x18002b192  retn
```
