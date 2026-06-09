# RadiusExtensionPoint::Load(_RADIUS_EXTENSION_POINT,uchar *)

- ea: `0x18001224c`
- end: `0x180012475`
- name: `?Load@RadiusExtensionPoint@@QEAAKW4_RADIUS_EXTENSION_POINT@@PEAE@Z`
- size: `553`
- prototype: `unsigned int __fastcall(RadiusExtensionPoint *__hidden this, enum _RADIUS_EXTENSION_POINT, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180012660`

## callees

- `0x180001e70`
- `0x18000342c`
- `0x18000c4a4`
- `0x180012218`
- `0x18001224c`
- `0x1800145dc`
- `0x180014608`
- `0x1800254a0`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800123a2`
- `msvcrt!_ultow_s` at `0x1800123a2`
- `ADVAPI32!ReportEventW` at `0x1800123eb`
- `ADVAPI32!ReportEventW` at `0x1800123eb`

## string_xrefs

- `0x18001241a`: `No extensions registered.`

## pseudocode

```c
__int64 __fastcall RadiusExtensionPoint::Load(
        RadiusExtensionPoint *this,
        enum _RADIUS_EXTENSION_POINT a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rbx
  unsigned int v5; // r14d
  unsigned __int64 v6; // rbp
  const unsigned __int16 *v7; // rsi
  bool v8; // al
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int128 v11; // rax
  bool v12; // cf
  unsigned __int64 *v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  LPCWSTR Strings[2]; // [rsp+50h] [rbp-58h] BYREF
  int v18; // [rsp+60h] [rbp-48h] BYREF
  wchar_t Buffer[10]; // [rsp+64h] [rbp-44h] BYREF

  v3 = a3;
  v5 = 0;
  v6 = 0;
  v7 = a3;
  if ( !*a3 )
    goto LABEL_29;
  do
  {
    v8 = IsNT4Only(v7);
    v9 = v6 + 1;
    if ( v8 )
      v9 = v6;
    v6 = v9;
    v10 = -1;
    do
      ++v10;
    while ( v7[v10] );
    v7 += v10 + 1;
  }
  while ( *v7 );
  if ( v9 )
  {
    v11 = v9 * (unsigned __int128)0x48uLL;
    if ( !is_mul_ok(v9, 0x48u) )
      *(_QWORD *)&v11 = -1;
    v12 = __CFADD__((_QWORD)v11, 8);
    *(_QWORD *)&v11 = v11 + 8;
    if ( v12 )
      *(_QWORD *)&v11 = -1;
    v13 = (unsigned __int64 *)operator new[](v11, *((const struct std::nothrow_t **)&v11 + 1));
    if ( v13 )
    {
      *v13 = v6;
      v14 = v13 + 1;
      `eh vector constructor iterator'(
        v13 + 1,
        0x48u,
        v6,
        (void (*)(void *))RadiusExtension::RadiusExtension,
        (void (*)(void *))RadiusExtension::~RadiusExtension);
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)this + 1) = v14;
    if ( v14 )
    {
      *((_QWORD *)this + 2) = v14;
      while ( *v3 )
      {
        if ( !IsNT4Only(v3) )
        {
          v5 = RadiusExtension::Load(*((RadiusExtension **)this + 2), v3);
          if ( v5 )
          {
            RadiusExtensionPoint::Clear(this);
            if ( g_NPSEventLog )
            {
              v18 = 7864368;
              _ultow_s(v5, Buffer, 0xAu, 16);
              Strings[0] = v3;
              Strings[1] = (LPCWSTR)&v18;
              ReportEventW(g_NPSEventLog, 1u, 0, 0xC000002F, 0, 2u, 0, Strings, 0);
            }
            return v5;
          }
          *((_QWORD *)this + 2) += 72LL;
        }
        v15 = -1;
        do
          ++v15;
        while ( v3[v15] );
        v3 += v15 + 1;
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
LABEL_29:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("No extensions registered.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3e87bee23e33317d415fe2a0046bc3db_Traceguids, "NPSSVC");
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001224c  mov     [rsp+arg_8], rbx
0x180012251  mov     [rsp+arg_18], rbp
0x180012256  push    rsi
0x180012257  push    rdi
0x180012258  push    r12
0x18001225a  push    r14
0x18001225c  push    r15
0x18001225e  sub     rsp, 80h
0x180012265  mov     rax, cs:__security_cookie
0x18001226c  xor     rax, rsp
0x18001226f  mov     [rsp+0A8h+var_30], rax
0x180012274  mov     rbx, r8
0x180012277  mov     rdi, rcx
0x18001227a  xor     r15d, r15d
0x18001227d  mov     r14d, r15d
0x180012280  mov     ebp, r15d
0x180012283  mov     rsi, r8
0x180012286  cmp     [r8], r15w
0x18001228a  jz      loc_1800123FB
0x180012290  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012294  mov     rcx, rsi; unsigned __int16 *
0x180012297  call    ?IsNT4Only@@YA?B_NPEBG@Z; IsNT4Only(ushort const *)
0x18001229c  lea     rcx, [rbp+1]
0x1800122a0  test    al, al
0x1800122a2  cmovnz  rcx, rbp
0x1800122a6  mov     rbp, rcx
0x1800122a9  mov     rax, r12
0x1800122ac  inc     rax
0x1800122af  cmp     [rsi+rax*2], r15w
0x1800122b4  jnz     short loc_1800122AC
0x1800122b6  lea     rsi, [rsi+rax*2]
0x1800122ba  add     rsi, 2
0x1800122be  cmp     [rsi], r15w
0x1800122c2  jnz     short loc_180012294
0x1800122c4  test    rbp, rbp
0x1800122c7  jz      loc_1800123FB
0x1800122cd  mov     eax, 48h ; 'H'
0x1800122d2  mul     rbp
0x1800122d5  cmovb   rax, r12
0x1800122d9  add     rax, 8
0x1800122dd  cmovb   rax, r12
0x1800122e1  mov     rcx, rax; Size
0x1800122e4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800122e9  test    rax, rax
0x1800122ec  jz      short loc_18001231A
0x1800122ee  mov     [rax], rbp
0x1800122f1  lea     rsi, [rax+8]
0x1800122f5  lea     rax, ??1RadiusExtension@@QEAA@XZ; RadiusExtension::~RadiusExtension(void)
0x1800122fc  mov     [rsp+0A8h+lpUserSid], rax; void (*)(void *)
0x180012301  lea     r9, ??0RadiusExtension@@QEAA@XZ; void (*)(void *)
0x180012308  mov     r8, rbp; unsigned __int64
0x18001230b  mov     edx, 48h ; 'H'; unsigned __int64
0x180012310  mov     rcx, rsi; void *
0x180012313  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180012318  jmp     short loc_18001231D
0x18001231a  mov     rsi, r15
0x18001231d  mov     [rdi+8], rsi
0x180012321  test    rsi, rsi
0x180012324  jz      loc_1800123F3
0x18001232a  mov     [rdi+10h], rsi
0x18001232e  cmp     [rbx], r15w
0x180012332  jz      loc_180012449
0x180012338  mov     rcx, rbx; unsigned __int16 *
0x18001233b  call    ?IsNT4Only@@YA?B_NPEBG@Z; IsNT4Only(ushort const *)
0x180012340  test    al, al
0x180012342  jnz     short loc_18001235C
0x180012344  mov     rdx, rbx; unsigned __int16 *
0x180012347  mov     rcx, [rdi+10h]; this
0x18001234b  call    ?Load@RadiusExtension@@QEAAKPEBG@Z; RadiusExtension::Load(ushort const *)
0x180012350  mov     r14d, eax
0x180012353  test    eax, eax
0x180012355  jnz     short loc_180012373
0x180012357  add     qword ptr [rdi+10h], 48h ; 'H'
0x18001235c  mov     rcx, r12
0x18001235f  inc     rcx
0x180012362  cmp     [rbx+rcx*2], r15w
0x180012367  jnz     short loc_18001235F
0x180012369  lea     rbx, [rbx+rcx*2]
0x18001236d  add     rbx, 2
0x180012371  jmp     short loc_18001232E
0x180012373  mov     rcx, rdi; this
0x180012376  call    ?Clear@RadiusExtensionPoint@@QEAAXXZ; RadiusExtensionPoint::Clear(void)
0x18001237b  cmp     cs:?g_NPSEventLog@@3PEAXEA, r15; void * g_NPSEventLog
0x180012382  jz      loc_180012449
0x180012388  mov     [rsp+0A8h+var_48], 780030h
0x180012390  mov     r9d, 10h; Radix
0x180012396  lea     r8d, [r9-6]; BufferCount
0x18001239a  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x18001239f  mov     ecx, r14d; Value
0x1800123a2  call    cs:__imp__ultow_s
0x1800123a8  mov     [rsp+0A8h+Strings], rbx
0x1800123ad  lea     rax, [rsp+0A8h+var_48]
0x1800123b2  mov     [rsp+0A8h+var_50], rax
0x1800123b7  xor     r8d, r8d; wCategory
0x1800123ba  lea     edx, [r8+1]; wType
0x1800123be  mov     [rsp+0A8h+lpRawData], r15; lpRawData
0x1800123c3  lea     rax, [rsp+0A8h+Strings]
0x1800123c8  mov     [rsp+0A8h+lpStrings], rax; lpStrings
0x1800123cd  mov     [rsp+0A8h+dwDataSize], r15d; dwDataSize
0x1800123d2  mov     [rsp+0A8h+wNumStrings], 2; wNumStrings
0x1800123d9  mov     [rsp+0A8h+lpUserSid], r15; lpUserSid
0x1800123de  mov     r9d, 0C000002Fh; dwEventID
0x1800123e4  mov     rcx, cs:?g_NPSEventLog@@3PEAXEA; hEventLog
0x1800123eb  call    cs:__imp_ReportEventW
0x1800123f1  jmp     short loc_180012449
0x1800123f3  mov     r14d, 8
0x1800123f9  jmp     short loc_180012449
0x1800123fb  lea     rcx, WPP_GLOBAL_Control
0x180012402  mov     rax, cs:WPP_GLOBAL_Control
0x180012409  cmp     rax, rcx
0x18001240c  jz      short loc_180012449
0x18001240e  cmp     byte ptr [rax+19h], 4
0x180012412  jb      short loc_180012449
0x180012414  test    byte ptr [rax+1Ch], 4
0x180012418  jz      short loc_180012449
0x18001241a  lea     rcx, aNoExtensionsRe; "No extensions registered."
0x180012421  call    WppDbgPrint
0x180012426  mov     edx, 0Ah
0x18001242b  lea     r9, aNpssvc; "NPSSVC"
0x180012432  lea     r8, WPP_3e87bee23e33317d415fe2a0046bc3db_Traceguids
0x180012439  mov     rcx, cs:WPP_GLOBAL_Control
0x180012440  mov     rcx, [rcx+10h]
0x180012444  call    WPP_SF_s
0x180012449  mov     eax, r14d
0x18001244c  mov     rcx, [rsp+0A8h+var_30]
0x180012451  xor     rcx, rsp; StackCookie
0x180012454  call    __security_check_cookie
0x180012459  lea     r11, [rsp+0A8h+var_28]
0x180012461  mov     rbx, [r11+38h]
0x180012465  mov     rbp, [r11+48h]
0x180012469  mov     rsp, r11
0x18001246c  pop     r15
0x18001246e  pop     r14
0x180012470  pop     r12
0x180012472  pop     rdi
0x180012473  pop     rsi
0x180012474  retn
```
