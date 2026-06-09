# ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY(void)

- ea: `0x18000b0bc`
- end: `0x18000b1d5`
- name: `??1ATTRIBUTE_SAFEARRAY@@AEAA@XZ`
- size: `281`
- prototype: `void __fastcall(ATTRIBUTE_SAFEARRAY *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b288`
- `0x18000b888`
- `0x18000d8e0`

## callees

- `0x18000b0bc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000b171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b18a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b171`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b18a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b1ba`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000b1ba`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000b14c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000b14c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000b134`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000b134`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000b101`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000b101`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b0e7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b1a5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b0e7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000b1a5`

## pseudocode

```c
void __fastcall ATTRIBUTE_SAFEARRAY::~ATTRIBUTE_SAFEARRAY(ATTRIBUTE_SAFEARRAY *this)
{
  SAFEARRAY *v2; // rcx
  bool v3; // zf
  SAFEARRAY *v4; // rcx
  LONG i; // edi
  _QWORD *v6; // rbp
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  LONG plUbound; // [rsp+40h] [rbp+8h] BYREF
  LONG plLbound; // [rsp+48h] [rbp+10h] BYREF
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF

  v2 = (SAFEARRAY *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    v3 = *((_DWORD *)this + 1) == 0;
    ppvData = 0;
    if ( !v3 && SafeArrayUnaccessData(v2) >= 0 )
      *((_DWORD *)this + 1) = 0;
    if ( SafeArrayAccessData(*((SAFEARRAY **)this + 1), &ppvData) >= 0 )
    {
      *((_DWORD *)this + 1) = 1;
      v4 = (SAFEARRAY *)*((_QWORD *)this + 1);
      plLbound = 0;
      plUbound = 0;
      if ( SafeArrayGetLBound(v4, 1u, &plLbound) >= 0
        && SafeArrayGetUBound(*((SAFEARRAY **)this + 1), 1u, &plUbound) >= 0 )
      {
        for ( i = plLbound; i <= plUbound; ++i )
        {
          v6 = ppvData;
          v7 = (OLECHAR *)*((_QWORD *)ppvData + 2 * i);
          if ( v7 )
          {
            SysFreeString(v7);
            v6[2 * i] = 0;
          }
          v8 = (OLECHAR *)v6[2 * i + 1];
          if ( v8 )
          {
            SysFreeString(v8);
            v6[2 * i + 1] = 0;
          }
        }
      }
    }
    if ( SafeArrayUnaccessData(*((SAFEARRAY **)this + 1)) >= 0 )
      *((_DWORD *)this + 1) = 0;
    SafeArrayDestroy(*((SAFEARRAY **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000b0bc  mov     [rsp+arg_18], rbx
0x18000b0c1  push    rbp
0x18000b0c2  push    rsi
0x18000b0c3  push    rdi
0x18000b0c4  sub     rsp, 20h
0x18000b0c8  mov     rbx, rcx
0x18000b0cb  mov     rcx, [rcx+8]; psa
0x18000b0cf  test    rcx, rcx
0x18000b0d2  jz      loc_18000B1C8
0x18000b0d8  cmp     dword ptr [rbx+4], 0
0x18000b0dc  mov     [rsp+38h+ppvData], 0
0x18000b0e5  jz      short loc_18000B0F8
0x18000b0e7  call    cs:__imp_SafeArrayUnaccessData
0x18000b0ed  test    eax, eax
0x18000b0ef  js      short loc_18000B0F8
0x18000b0f1  mov     dword ptr [rbx+4], 0
0x18000b0f8  mov     rcx, [rbx+8]; psa
0x18000b0fc  lea     rdx, [rsp+38h+ppvData]; ppvData
0x18000b101  call    cs:__imp_SafeArrayAccessData
0x18000b107  test    eax, eax
0x18000b109  js      loc_18000B1A1
0x18000b10f  mov     dword ptr [rbx+4], 1
0x18000b116  mov     rcx, [rbx+8]; psa
0x18000b11a  lea     r8, [rsp+38h+plLbound]; plLbound
0x18000b11f  mov     edx, 1; nDim
0x18000b124  mov     [rsp+38h+plLbound], 0
0x18000b12c  mov     [rsp+38h+plUbound], 0
0x18000b134  call    cs:__imp_SafeArrayGetLBound
0x18000b13a  test    eax, eax
0x18000b13c  js      short loc_18000B1A1
0x18000b13e  mov     rcx, [rbx+8]; psa
0x18000b142  lea     r8, [rsp+38h+plUbound]; plUbound
0x18000b147  mov     edx, 1; nDim
0x18000b14c  call    cs:__imp_SafeArrayGetUBound
0x18000b152  test    eax, eax
0x18000b154  js      short loc_18000B1A1
0x18000b156  mov     edi, [rsp+38h+plLbound]
0x18000b15a  jmp     short loc_18000B19B
0x18000b15c  mov     rbp, [rsp+38h+ppvData]
0x18000b161  movsxd  rsi, edi
0x18000b164  add     rsi, rsi
0x18000b167  mov     rcx, [rbp+rsi*8+0]; bstrString
0x18000b16c  test    rcx, rcx
0x18000b16f  jz      short loc_18000B180
0x18000b171  call    cs:__imp_SysFreeString
0x18000b177  mov     qword ptr [rbp+rsi*8+0], 0
0x18000b180  mov     rcx, [rbp+rsi*8+8]; bstrString
0x18000b185  test    rcx, rcx
0x18000b188  jz      short loc_18000B199
0x18000b18a  call    cs:__imp_SysFreeString
0x18000b190  mov     qword ptr [rbp+rsi*8+8], 0
0x18000b199  inc     edi
0x18000b19b  cmp     edi, [rsp+38h+plUbound]
0x18000b19f  jle     short loc_18000B15C
0x18000b1a1  mov     rcx, [rbx+8]; psa
0x18000b1a5  call    cs:__imp_SafeArrayUnaccessData
0x18000b1ab  test    eax, eax
0x18000b1ad  js      short loc_18000B1B6
0x18000b1af  mov     dword ptr [rbx+4], 0
0x18000b1b6  mov     rcx, [rbx+8]; psa
0x18000b1ba  call    cs:__imp_SafeArrayDestroy
0x18000b1c0  mov     qword ptr [rbx+8], 0
0x18000b1c8  mov     rbx, [rsp+38h+arg_18]
0x18000b1cd  add     rsp, 20h
0x18000b1d1  pop     rdi
0x18000b1d2  pop     rsi
0x18000b1d3  pop     rbp
0x18000b1d4  retn
```
