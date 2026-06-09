# Mso::OfficeWebServiceApi::Service::IsConfigServiceEndpoint(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18007ffa0`
- end: `0x18008010e`
- name: `?IsConfigServiceEndpoint@Service@OfficeWebServiceApi@Mso@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180077c48`
- `0x18007fc64`
- `0x18007fe18`

## callees

- `0x180008f14`
- `0x1800409e0`
- `0x18007ffa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008008a`
- `KERNEL32!GetLastError` at `0x18008008a`
- `KERNEL32!CompareStringEx` at `0x180080039`
- `KERNEL32!CompareStringEx` at `0x180080080`
- `KERNEL32!CompareStringEx` at `0x180080039`
- `KERNEL32!CompareStringEx` at `0x180080080`

## pseudocode

```c
bool __fastcall Mso::OfficeWebServiceApi::Service::IsConfigServiceEndpoint(const WCHAR *lpString1)
{
  const WCHAR *v1; // rdi
  unsigned __int64 v2; // rsi
  int cchCount2; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int pExceptionObject; // [rsp+50h] [rbp-398h] BYREF
  __int16 v11; // [rsp+54h] [rbp-394h]
  DWORD LastError; // [rsp+254h] [rbp-194h]
  __int16 v13; // [rsp+258h] [rbp-190h]
  __int16 v14; // [rsp+358h] [rbp-90h]
  int v15; // [rsp+3D8h] [rbp-10h]

  v1 = lpString1;
  if ( *((_QWORD *)lpString1 + 3) > 7u )
    v1 = *(const WCHAR **)lpString1;
  if ( v1 && *v1 )
  {
    if ( aOneturl[0] )
    {
      v2 = -1;
      do
        ++v2;
      while ( v1[v2] );
      cchCount2 = OcfxInt32FromSize_t(7u);
      v4 = OcfxInt32FromSize_t(v2);
      v5 = CompareStringEx(&LocaleName, 0, v1, v4, L"ONetUrl", cchCount2, 0, 0, 0);
      if ( !v5 )
      {
        v6 = OcfxInt32FromSize_t(7u);
        v7 = OcfxInt32FromSize_t(v2);
        v5 = CompareStringEx(L"en-US", 0, v1, v7, L"ONetUrl", v6, 0, 0, 0);
        if ( !v5 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v15 = 808464432;
          v14 = 0;
          v13 = 0;
          v11 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      v8 = v5 - 2;
    }
    else
    {
      v8 = 1;
    }
  }
  else
  {
    v8 = -(aOneturl[0] != 0);
  }
  return v8 == 0;
}

```

## disassembly

```asm
0x18007ffa0  mov     rax, rsp
0x18007ffa3  mov     [rax+8], rbx
0x18007ffa7  mov     [rax+10h], rbp
0x18007ffab  mov     [rax+18h], rsi
0x18007ffaf  mov     [rax+20h], rdi
0x18007ffb3  push    r15
0x18007ffb5  sub     rsp, 3E0h
0x18007ffbc  mov     rdi, rcx
0x18007ffbf  cmp     qword ptr [rcx+18h], 7
0x18007ffc4  jbe     short loc_18007FFC9
0x18007ffc6  mov     rdi, [rcx]
0x18007ffc9  xor     ebp, ebp
0x18007ffcb  test    rdi, rdi
0x18007ffce  jz      loc_1800800DD
0x18007ffd4  cmp     bp, [rdi]
0x18007ffd7  jz      loc_1800800DD
0x18007ffdd  cmp     bp, word ptr cs:aOneturl; "ONetUrl"
0x18007ffe4  jz      loc_1800800D6
0x18007ffea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007ffee  inc     rsi
0x18007fff1  cmp     [rdi+rsi*2], bp
0x18007fff5  jnz     short loc_18007FFEE
0x18007fff7  mov     ecx, 7; unsigned __int64
0x18007fffc  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180080001  mov     ebx, eax
0x180080003  mov     rcx, rsi; unsigned __int64
0x180080006  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18008000b  mov     [rsp+3E8h+lParam], rbp; lParam
0x180080010  mov     [rsp+3E8h+lpReserved], rbp; lpReserved
0x180080015  mov     [rsp+3E8h+lpVersionInformation], rbp; lpVersionInformation
0x18008001a  mov     [rsp+3E8h+cchCount2], ebx; cchCount2
0x18008001e  lea     r15, aOneturl; "ONetUrl"
0x180080025  mov     [rsp+3E8h+lpString2], r15; lpString2
0x18008002a  mov     r9d, eax; cchCount1
0x18008002d  mov     r8, rdi; lpString1
0x180080030  xor     edx, edx; dwCmpFlags
0x180080032  lea     rcx, LocaleName; lpLocaleName
0x180080039  call    cs:__imp_CompareStringEx
0x18008003f  test    eax, eax
0x180080041  jnz     loc_1800800D1
0x180080047  lea     ecx, [rax+7]; unsigned __int64
0x18008004a  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18008004f  mov     ebx, eax
0x180080051  mov     rcx, rsi; unsigned __int64
0x180080054  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180080059  mov     [rsp+3E8h+lParam], rbp; lParam
0x18008005e  mov     [rsp+3E8h+lpReserved], rbp; lpReserved
0x180080063  mov     [rsp+3E8h+lpVersionInformation], rbp; lpVersionInformation
0x180080068  mov     [rsp+3E8h+cchCount2], ebx; cchCount2
0x18008006c  mov     [rsp+3E8h+lpString2], r15; lpString2
0x180080071  mov     r9d, eax; cchCount1
0x180080074  mov     r8, rdi; lpString1
0x180080077  xor     edx, edx; dwCmpFlags
0x180080079  lea     rcx, aEnUs; "en-US"
0x180080080  call    cs:__imp_CompareStringEx
0x180080086  test    eax, eax
0x180080088  jnz     short loc_1800800D1
0x18008008a  call    cs:__imp_GetLastError
0x180080090  mov     [rsp+3E8h+pExceptionObject], 0Fh
0x180080098  mov     [rsp+3E8h+var_194], eax
0x18008009f  mov     [rsp+3E8h+var_10], 30303030h
0x1800800aa  mov     [rsp+3E8h+var_90], bp
0x1800800b2  mov     [rsp+3E8h+var_190], bp
0x1800800ba  mov     [rsp+3E8h+var_394], bp
0x1800800bf  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800800c6  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x1800800cb  call    _CxxThrowException
0x1800800d1  add     eax, 0FFFFFFFEh
0x1800800d4  jmp     short loc_1800800EB
0x1800800d6  mov     eax, 1
0x1800800db  jmp     short loc_1800800EB
0x1800800dd  mov     ecx, ebp
0x1800800df  sub     cx, word ptr cs:aOneturl; "ONetUrl"
0x1800800e6  neg     cx
0x1800800e9  sbb     eax, eax
0x1800800eb  test    eax, eax
0x1800800ed  setz    al
0x1800800f0  lea     r11, [rsp+3E8h+var_8]
0x1800800f8  mov     rbx, [r11+10h]
0x1800800fc  mov     rbp, [r11+18h]
0x180080100  mov     rsi, [r11+20h]
0x180080104  mov     rdi, [r11+28h]
0x180080108  mov     rsp, r11
0x18008010b  pop     r15
0x18008010d  retn
```
