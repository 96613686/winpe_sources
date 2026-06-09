# GetLogDisplayName(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001f9cc`
- end: `0x18001fc7b`
- name: `?GetLogDisplayName@@YAPEAGPEAUHKEY__@@PEBG11@Z`
- size: `687`
- prototype: `unsigned __int16 *__fastcall(HKEY, wchar_t *Source, const unsigned __int16 *Src, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000728c`
- `0x180016084`

## callees

- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x1800028e0`
- `0x18000513c`
- `0x18000ca0c`
- `0x18001abd8`
- `0x18001ae60`
- `0x18001aef4`
- `0x18001af3c`
- `0x18001f4ec`
- `0x18001f9cc`
- `0x180020430`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001fa17`
- `msvcrt!_wcsicmp` at `0x18001fa17`
- `msvcrt!wcscpy_s` at `0x18001fa82`
- `msvcrt!wcscpy_s` at `0x18001fa82`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001fb63`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001fb63`
- `KERNEL32!LocalAlloc` at `0x18001fa67`
- `KERNEL32!LocalAlloc` at `0x18001fa67`

## string_xrefs

- `0x18001fa98`: `SYSTEM\CurrentControlSet\Services\EventLog`
- `0x18001fa0d`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall GetLogDisplayName(
        HKEY a1,
        wchar_t *Source,
        const unsigned __int16 *Src,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  rsize_t v9; // rdi
  wchar_t *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  const unsigned __int16 *v14; // r8
  __int64 v15; // rdx
  DWORD dwMessageId; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v20[5]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Sourcea[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Srca[264]; // [rsp+280h] [rbp+180h] BYREF

  *(_QWORD *)Buffer = 0;
  if ( _wcsicmp(a4, L"Security") )
    goto LABEL_7;
  LoadStr(0x15Fu, Sourcea, 0x104u, (wchar_t *)&String);
  if ( !Sourcea[0] )
    goto LABEL_7;
  v8 = -1;
  do
    ++v8;
  while ( Sourcea[v8] );
  v9 = v8 + 1;
  v10 = (wchar_t *)LocalAlloc(0x40u, 2 * (v8 + 1));
  *(_QWORD *)Buffer = v10;
  if ( v10 )
  {
    wcscpy_s(v10, v9, Sourcea);
  }
  else
  {
LABEL_7:
    std::wstring::wstring(v20);
    std::wstring::assign(v20, L"SYSTEM\\CurrentControlSet\\Services\\EventLog");
    v11 = std::char_traits<unsigned short>::length(L"\\");
    std::wstring::append(v20, v12, v11);
    v13 = std::char_traits<unsigned short>::length(a4);
    std::wstring::append(v20, a4, v13);
    v18 = 0;
    v14 = (const unsigned __int16 *)v20;
    if ( v20[3] >= (unsigned __int16 *)8 )
      v14 = v20[0];
    if ( (int)CSafeReg::Open((CSafeReg *)&v18, HKEY_LOCAL_MACHINE, v14, 0x20019u) >= 0
      && (int)CSafeReg::QueryPath(&v18, L"DisplayNameFile", (BYTE *)Srca, 0x104u, 1) >= 0 )
    {
      dwMessageId = 0;
      if ( (int)CSafeReg::QueryDword((CSafeReg *)&v18, L"DisplayNameID", &dwMessageId) >= 0 )
      {
        ExpandEnvironmentStringsW(Srca, Sourcea, 0x104u);
        AttemptFormatMessage((CDllCache *)dwMessageId, Sourcea, Buffer, 0);
      }
    }
    CSafeReg::Close((CSafeReg *)&v18);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v20, v15, 0);
  }
  if ( !*(_QWORD *)Buffer && Source && *Source )
  {
    v18 = 0;
    if ( (int)CSafeReg::Open((CSafeReg *)&v18, a1, a4, 0x20019u) >= 0
      && (int)CSafeReg::QueryPath(&v18, L"DisplayNameFile", (BYTE *)Sourcea, 0x104u, 1) >= 0
      && (int)ExpandSystemRootAndConvertToUnc(Sourcea, 0x104u, Source, Src) >= 0 )
    {
      dwMessageId = 0;
      if ( (int)CSafeReg::QueryDword((CSafeReg *)&v18, L"DisplayNameID", &dwMessageId) >= 0 )
        AttemptFormatMessage((CDllCache *)dwMessageId, Sourcea, Buffer, 0);
    }
    CSafeReg::Close((CSafeReg *)&v18);
  }
  return *(unsigned __int16 **)Buffer;
}

```

## disassembly

```asm
0x18001f9cc  push    rbp
0x18001f9ce  push    rbx
0x18001f9cf  push    rsi
0x18001f9d0  push    rdi
0x18001f9d1  push    r12
0x18001f9d3  push    r13
0x18001f9d5  push    r14
0x18001f9d7  push    r15
0x18001f9d9  lea     rbp, [rsp-3A8h]
0x18001f9e1  sub     rsp, 4A8h
0x18001f9e8  mov     rax, cs:__security_cookie
0x18001f9ef  xor     rax, rsp
0x18001f9f2  mov     [rbp+3E0h+var_50], rax
0x18001f9f9  mov     rsi, r9
0x18001f9fc  mov     r14, r8
0x18001f9ff  mov     rbx, rdx
0x18001fa02  mov     r15, rcx
0x18001fa05  xor     r12d, r12d
0x18001fa08  mov     qword ptr [rsp+4E0h+Buffer], r12
0x18001fa0d  lea     rdx, aSecurity; "Security"
0x18001fa14  mov     rcx, r9; String1
0x18001fa17  call    cs:__imp__wcsicmp
0x18001fa1d  mov     r13d, 104h
0x18001fa23  test    eax, eax
0x18001fa25  jnz     short loc_18001FA8D
0x18001fa27  lea     r9, String; Source
0x18001fa2e  mov     r8d, r13d; SizeInWords
0x18001fa31  lea     rdx, [rsp+4E0h+Source]; Destination
0x18001fa36  lea     ecx, [r13+5Bh]; uID
0x18001fa3a  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18001fa3f  cmp     [rsp+4E0h+Source], r12w
0x18001fa45  jz      short loc_18001FA8D
0x18001fa47  lea     rcx, [rsp+4E0h+Source]
0x18001fa4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fa50  inc     rax
0x18001fa53  cmp     [rcx+rax*2], r12w
0x18001fa58  jnz     short loc_18001FA50
0x18001fa5a  lea     rdi, [rax+1]
0x18001fa5e  lea     rdx, [rdi+rdi]; uBytes
0x18001fa62  mov     ecx, 40h ; '@'; uFlags
0x18001fa67  call    cs:__imp_LocalAlloc
0x18001fa6d  mov     qword ptr [rsp+4E0h+Buffer], rax
0x18001fa72  test    rax, rax
0x18001fa75  jz      short loc_18001FA8D
0x18001fa77  lea     r8, [rsp+4E0h+Source]; Source
0x18001fa7c  mov     rdx, rdi; SizeInWords
0x18001fa7f  mov     rcx, rax; Destination
0x18001fa82  call    cs:__imp_wcscpy_s
0x18001fa88  jmp     loc_18001FB9A
0x18001fa8d  lea     rcx, [rsp+4E0h+var_498]
0x18001fa92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001fa97  nop
0x18001fa98  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18001fa9f  lea     rcx, [rsp+4E0h+var_498]
0x18001faa4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001faa9  lea     rcx, SubBlock; "\\"
0x18001fab0  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001fab5  mov     r8, rax
0x18001fab8  mov     rdx, rcx
0x18001fabb  lea     rcx, [rsp+4E0h+var_498]
0x18001fac0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001fac5  mov     rcx, rsi
0x18001fac8  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001facd  mov     r8, rax
0x18001fad0  mov     rdx, rsi
0x18001fad3  lea     rcx, [rsp+4E0h+var_498]
0x18001fad8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001fadd  mov     [rsp+4E0h+var_4A8], r12
0x18001fae2  lea     r8, [rsp+4E0h+var_498]
0x18001fae7  cmp     [rsp+4E0h+var_480], 8
0x18001faed  cmovnb  r8, [rsp+4E0h+var_498]; unsigned __int16 *
0x18001faf3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001fafa  mov     r9d, 20019h; unsigned int
0x18001fb00  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fb05  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18001fb0a  test    eax, eax
0x18001fb0c  js      short loc_18001FB80
0x18001fb0e  mov     [rsp+4E0h+var_4C0], 1; int
0x18001fb16  mov     r9d, r13d; unsigned int
0x18001fb19  lea     r8, [rbp+3E0h+Src]; unsigned __int16 *
0x18001fb20  lea     rdx, aDisplaynamefil; "DisplayNameFile"
0x18001fb27  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fb2c  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18001fb31  test    eax, eax
0x18001fb33  js      short loc_18001FB80
0x18001fb35  mov     [rsp+4E0h+dwMessageId], r12d
0x18001fb3a  lea     r8, [rsp+4E0h+dwMessageId]; unsigned int *
0x18001fb3f  lea     rdx, aDisplaynameid; "DisplayNameID"
0x18001fb46  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fb4b  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x18001fb50  test    eax, eax
0x18001fb52  js      short loc_18001FB80
0x18001fb54  mov     r8d, r13d; nSize
0x18001fb57  lea     rdx, [rsp+4E0h+Source]; lpDst
0x18001fb5c  lea     rcx, [rbp+3E0h+Src]; lpSrc
0x18001fb63  call    cs:__imp_ExpandEnvironmentStringsW
0x18001fb69  xor     r9d, r9d; int
0x18001fb6c  lea     r8, [rsp+4E0h+Buffer]; lpBuffer
0x18001fb71  lea     rdx, [rsp+4E0h+Source]; unsigned __int16 *
0x18001fb76  mov     ecx, [rsp+4E0h+dwMessageId]; dwMessageId
0x18001fb7a  call    ?AttemptFormatMessage@@YAHKPEBGPEAPEAGH@Z; AttemptFormatMessage(ulong,ushort const *,ushort * *,int)
0x18001fb7f  nop
0x18001fb80  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fb85  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001fb8a  nop
0x18001fb8b  xor     r8d, r8d
0x18001fb8e  mov     dl, 1
0x18001fb90  lea     rcx, [rsp+4E0h+var_498]
0x18001fb95  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001fb9a  cmp     qword ptr [rsp+4E0h+Buffer], r12
0x18001fb9f  jnz     loc_18001FC53
0x18001fba5  test    rbx, rbx
0x18001fba8  jz      loc_18001FC53
0x18001fbae  cmp     [rbx], r12w
0x18001fbb2  jz      loc_18001FC53
0x18001fbb8  mov     [rsp+4E0h+var_4A8], r12
0x18001fbbd  mov     r9d, 20019h; unsigned int
0x18001fbc3  mov     r8, rsi; unsigned __int16 *
0x18001fbc6  mov     rdx, r15; HKEY
0x18001fbc9  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fbce  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18001fbd3  test    eax, eax
0x18001fbd5  js      short loc_18001FC49
0x18001fbd7  mov     [rsp+4E0h+var_4C0], 1; int
0x18001fbdf  mov     r9d, r13d; unsigned int
0x18001fbe2  lea     r8, [rsp+4E0h+Source]; unsigned __int16 *
0x18001fbe7  lea     rdx, aDisplaynamefil; "DisplayNameFile"
0x18001fbee  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fbf3  call    ?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z; CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)
0x18001fbf8  test    eax, eax
0x18001fbfa  js      short loc_18001FC49
0x18001fbfc  mov     r9, r14; Src
0x18001fbff  mov     r8, rbx; Source
0x18001fc02  mov     edx, r13d; SizeInWords
0x18001fc05  lea     rcx, [rsp+4E0h+Source]; Destination
0x18001fc0a  call    ?ExpandSystemRootAndConvertToUnc@@YAJPEAGKPEBG1@Z; ExpandSystemRootAndConvertToUnc(ushort *,ulong,ushort const *,ushort const *)
0x18001fc0f  test    eax, eax
0x18001fc11  js      short loc_18001FC49
0x18001fc13  mov     [rsp+4E0h+dwMessageId], r12d
0x18001fc18  lea     r8, [rsp+4E0h+dwMessageId]; unsigned int *
0x18001fc1d  lea     rdx, aDisplaynameid; "DisplayNameID"
0x18001fc24  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fc29  call    ?QueryDword@CSafeReg@@QEAAJPEBGPEAK@Z; CSafeReg::QueryDword(ushort const *,ulong *)
0x18001fc2e  test    eax, eax
0x18001fc30  js      short loc_18001FC49
0x18001fc32  xor     r9d, r9d; int
0x18001fc35  lea     r8, [rsp+4E0h+Buffer]; lpBuffer
0x18001fc3a  lea     rdx, [rsp+4E0h+Source]; unsigned __int16 *
0x18001fc3f  mov     ecx, [rsp+4E0h+dwMessageId]; dwMessageId
0x18001fc43  call    ?AttemptFormatMessage@@YAHKPEBGPEAPEAGH@Z; AttemptFormatMessage(ulong,ushort const *,ushort * *,int)
0x18001fc48  nop
0x18001fc49  lea     rcx, [rsp+4E0h+var_4A8]; this
0x18001fc4e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001fc53  mov     rax, qword ptr [rsp+4E0h+Buffer]
0x18001fc58  mov     rcx, [rbp+3E0h+var_50]
0x18001fc5f  xor     rcx, rsp; StackCookie
0x18001fc62  call    __security_check_cookie
0x18001fc67  add     rsp, 4A8h
0x18001fc6e  pop     r15
0x18001fc70  pop     r14
0x18001fc72  pop     r13
0x18001fc74  pop     r12
0x18001fc76  pop     rdi
0x18001fc77  pop     rsi
0x18001fc78  pop     rbx
0x18001fc79  pop     rbp
0x18001fc7a  retn
```
