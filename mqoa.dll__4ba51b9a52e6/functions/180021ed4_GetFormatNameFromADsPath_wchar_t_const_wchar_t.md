# GetFormatNameFromADsPath(wchar_t const *,wchar_t * *)

- ea: `0x180021ed4`
- end: `0x180021fbd`
- name: `?GetFormatNameFromADsPath@@YAJPEB_WPEAPEA_W@Z`
- size: `233`
- prototype: `__int64 __fastcall(LPCWSTR lpwcsADsPath, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180022560`

## callees

- `0x180013590`
- `0x180013970`
- `0x1800149b0`
- `0x1800149e0`
- `0x180021ed4`
- `0x1800273b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180021f78`
- `OLEAUT32!__imp_SysAllocString` at `0x180021f78`
- `mqrt!MQADsPathToFormatName` at `0x180021f42`
- `mqrt!MQADsPathToFormatName` at `0x180021f42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFormatNameFromADsPath(LPCWSTR lpwcsADsPath, wchar_t **a2)
{
  WCHAR *Buffer; // rax
  int v5; // ebx
  const OLECHAR *v6; // rax
  wchar_t *v7; // rax
  DWORD dwFormatNameLength[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh]

  v10[1] = 0;
  v11 = 0;
  v10[0] = &CStaticBufferGrowing<wchar_t,1024>::`vftable';
  dwFormatNameLength[0] = CBaseStaticBufferGrowing<unsigned char>::GetBufferMaxSize(v10);
  while ( 1 )
  {
    Buffer = (WCHAR *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v10);
    v5 = MQADsPathToFormatName(lpwcsADsPath, Buffer, dwFormatNameLength);
    if ( v5 != -1072824289 )
      break;
    v5 = CBaseStaticBufferGrowing<wchar_t>::AllocateBuffer((__int64)v10, dwFormatNameLength[0]);
    if ( v5 < 0 )
      goto LABEL_9;
  }
  if ( v5 >= 0 )
  {
    v6 = (const OLECHAR *)CBaseStaticBufferGrowing<wchar_t>::GetBuffer((__int64)v10);
    v7 = SysAllocString(v6);
    if ( v7 )
    {
      *a2 = v7;
      v5 = 0;
    }
    else
    {
      v5 = -2147024882;
    }
  }
LABEL_9:
  CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180021ed4  mov     [rsp-8+arg_10], rbx
0x180021ed9  push    rbp
0x180021eda  push    rsi
0x180021edb  push    rdi
0x180021edc  lea     rbp, [rsp-760h]
0x180021ee4  sub     rsp, 860h
0x180021eeb  mov     rax, cs:__security_cookie
0x180021ef2  xor     rax, rsp
0x180021ef5  mov     [rbp+770h+var_20], rax
0x180021efc  mov     rsi, rdx
0x180021eff  mov     rdi, rcx
0x180021f02  mov     [rsp+870h+var_838], 0
0x180021f0b  mov     [rsp+870h+var_82C], 0
0x180021f13  lea     rax, ??_7?$CStaticBufferGrowing@_W$0EAA@@@6B@; const CStaticBufferGrowing<wchar_t,1024>::`vftable'
0x180021f1a  mov     [rsp+870h+var_840], rax
0x180021f1f  lea     rcx, [rsp+870h+var_840]
0x180021f24  call    ?GetBufferMaxSize@?$CBaseStaticBufferGrowing@E@@UEAAKXZ; CBaseStaticBufferGrowing<uchar>::GetBufferMaxSize(void)
0x180021f29  mov     [rsp+870h+dwFormatNameLength], eax
0x180021f2d  lea     rcx, [rsp+870h+var_840]
0x180021f32  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x180021f37  lea     r8, [rsp+870h+dwFormatNameLength]; lpdwFormatNameLength
0x180021f3c  mov     rdx, rax; lpwcsFormatName
0x180021f3f  mov     rcx, rdi; lpwcsADsPath
0x180021f42  call    cs:__imp_MQADsPathToFormatName
0x180021f48  mov     ebx, eax
0x180021f4a  cmp     eax, 0C00E001Fh
0x180021f4f  jnz     short loc_180021F67
0x180021f51  mov     edx, [rsp+870h+dwFormatNameLength]
0x180021f55  lea     rcx, [rsp+870h+var_840]
0x180021f5a  call    ?AllocateBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAJK@Z; CBaseStaticBufferGrowing<wchar_t>::AllocateBuffer(ulong)
0x180021f5f  mov     ebx, eax
0x180021f61  test    eax, eax
0x180021f63  js      short loc_180021F8F
0x180021f65  jmp     short loc_180021F2D
0x180021f67  test    ebx, ebx
0x180021f69  js      short loc_180021F8F
0x180021f6b  lea     rcx, [rsp+870h+var_840]
0x180021f70  call    ?GetBuffer@?$CBaseStaticBufferGrowing@_W@@UEAAPEA_WXZ; CBaseStaticBufferGrowing<wchar_t>::GetBuffer(void)
0x180021f75  mov     rcx, rax; psz
0x180021f78  call    cs:__imp_SysAllocString
0x180021f7e  test    rax, rax
0x180021f81  jnz     short loc_180021F8A
0x180021f83  mov     ebx, 8007000Eh
0x180021f88  jmp     short loc_180021F8F
0x180021f8a  mov     [rsi], rax
0x180021f8d  xor     ebx, ebx
0x180021f8f  lea     rcx, [rsp+870h+var_840]
0x180021f94  call    ??1?$CBaseStaticBufferGrowing@_W@@UEAA@XZ; CBaseStaticBufferGrowing<wchar_t>::~CBaseStaticBufferGrowing<wchar_t>(void)
0x180021f99  mov     eax, ebx
0x180021f9b  mov     rcx, [rbp+770h+var_20]
0x180021fa2  xor     rcx, rsp; StackCookie
0x180021fa5  call    __security_check_cookie
0x180021faa  mov     rbx, [rsp+870h+arg_10]
0x180021fb2  add     rsp, 860h
0x180021fb9  pop     rdi
0x180021fba  pop     rsi
0x180021fbb  pop     rbp
0x180021fbc  retn
```
