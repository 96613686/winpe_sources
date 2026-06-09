# CEventClass::RemoveInternal(int,IEventSystemTier2 *)

- ea: `0x180030ef4`
- end: `0x180031038`
- name: `?RemoveInternal@CEventClass@@AEAAJHPEAUIEventSystemTier2@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(CEventClass *__hidden this, int, struct IEventSystemTier2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180030ea0`

## callees

- `0x180008938`
- `0x180012654`
- `0x180030ef4`
- `0x1800434ae`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030f59`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030fa7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030f59`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180030fa7`

## string_xrefs

- `0x180030f44`: `com\complus\src\events\tier1\eventclass.cpp`
- `0x180030f66`: `com\complus\src\events\tier1\eventclass.cpp`
- `0x180030fb4`: `com\complus\src\events\tier1\eventclass.cpp`

## pseudocode

```c
__int64 __fastcall CEventClass::RemoveInternal(CEventClass *this, unsigned int a2, struct IEventSystemTier2 *a3)
{
  HRESULT v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  GUID Buf2; // [rsp+30h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-48h] BYREF

  Buf2 = GUID_NULL;
  pclsid = GUID_NULL;
  if ( !*((_WORD *)this + 24) )
    InternalAssert(
      L"com\\complus\\src\\events\\tier1\\eventclass.cpp",
      0x568u,
      0x10u,
      L"m_fields[EC_ID].vt != VT_EMPTY");
  v6 = CLSIDFromString(*((LPCOLESTR *)this + 7), &pclsid);
  if ( v6 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x56Au, 0x10u, v6);
  if ( memcmp_0(&CLSID_ComServiceEvents, &pclsid, 0x10u) )
  {
    if ( *((_WORD *)this + 156) )
    {
      v7 = CLSIDFromString(*((LPCOLESTR *)this + 40), &Buf2);
      if ( v7 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\eventclass.cpp", 0x572u, 0x10u, v7);
    }
    else
    {
      Buf2 = GUID_NULL;
    }
    v8 = memcmp_0(&GUID_NULL, &Buf2, 0x10u);
    if ( a2 )
    {
      if ( !v8 )
        return 2147746317LL;
    }
    else if ( v8 )
    {
      return 2147746318LL;
    }
  }
  return (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, _QWORD, char *, _QWORD))(*(_QWORD *)a3 + 80LL))(
           a3,
           0,
           (char *)this + 484,
           a2);
}

```

## disassembly

```asm
0x180030ef4  push    rbx
0x180030ef6  push    rbp
0x180030ef7  push    rsi
0x180030ef8  push    rdi
0x180030ef9  push    r14
0x180030efb  sub     rsp, 60h
0x180030eff  mov     rax, cs:__security_cookie
0x180030f06  xor     rax, rsp
0x180030f09  mov     [rsp+88h+var_38], rax
0x180030f0e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180030f15  xor     ebp, ebp
0x180030f17  mov     rsi, r8
0x180030f1a  mov     edi, edx
0x180030f1c  mov     rbx, rcx
0x180030f1f  movdqu  xmmword ptr [rsp+88h+Buf2.Data1], xmm0
0x180030f25  lea     r14d, [rbp+10h]
0x180030f29  movdqu  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x180030f2f  cmp     [rcx+30h], bp
0x180030f33  jnz     short loc_180030F50
0x180030f35  mov     r8d, r14d; unsigned __int16
0x180030f38  lea     r9, aMFieldsEcIdVtV; "m_fields[EC_ID].vt != VT_EMPTY"
0x180030f3f  mov     edx, 568h; unsigned int
0x180030f44  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180030f4b  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180030f50  mov     rcx, [rbx+38h]; lpsz
0x180030f54  lea     rdx, [rsp+88h+pclsid]; pclsid
0x180030f59  call    cs:__imp_CLSIDFromString
0x180030f5f  test    eax, eax
0x180030f61  jns     short loc_180030F7A
0x180030f63  mov     r8d, r14d; unsigned __int16
0x180030f66  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180030f6d  mov     r9d, eax; int
0x180030f70  mov     edx, 56Ah; unsigned int
0x180030f75  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180030f7a  mov     r8, r14; Size
0x180030f7d  lea     rdx, [rsp+88h+pclsid]; Buf2
0x180030f82  lea     rcx, CLSID_ComServiceEvents; Buf1
0x180030f89  call    memcmp_0
0x180030f8e  test    eax, eax
0x180030f90  jz      short loc_180031005
0x180030f92  cmp     [rbx+138h], bp
0x180030f99  jz      short loc_180030FCA
0x180030f9b  mov     rcx, [rbx+140h]; lpsz
0x180030fa2  lea     rdx, [rsp+88h+Buf2]; pclsid
0x180030fa7  call    cs:__imp_CLSIDFromString
0x180030fad  test    eax, eax
0x180030faf  jns     short loc_180030FD7
0x180030fb1  mov     r8d, r14d; unsigned __int16
0x180030fb4  lea     rcx, aComComplusSrcE; "com\\complus\\src\\events\\tier1\\event"...
0x180030fbb  mov     r9d, eax; int
0x180030fbe  mov     edx, 572h; unsigned int
0x180030fc3  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180030fc8  jmp     short loc_180030FD7
0x180030fca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180030fd1  movdqu  xmmword ptr [rsp+88h+Buf2.Data1], xmm0
0x180030fd7  mov     r8, r14; Size
0x180030fda  lea     rdx, [rsp+88h+Buf2]; Buf2
0x180030fdf  lea     rcx, GUID_NULL; Buf1
0x180030fe6  call    memcmp_0
0x180030feb  test    edi, edi
0x180030fed  jz      short loc_180030FFA
0x180030fef  test    eax, eax
0x180030ff1  jnz     short loc_180031005
0x180030ff3  mov     eax, 8004020Dh
0x180030ff8  jmp     short loc_180031020
0x180030ffa  test    eax, eax
0x180030ffc  jz      short loc_180031005
0x180030ffe  mov     eax, 8004020Eh
0x180031003  jmp     short loc_180031020
0x180031005  mov     rax, [rsi]
0x180031008  lea     r8, [rbx+1E4h]
0x18003100f  mov     r9d, edi
0x180031012  xor     edx, edx
0x180031014  mov     rcx, rsi
0x180031017  mov     rax, [rax+50h]
0x18003101b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031020  mov     rcx, [rsp+88h+var_38]
0x180031025  xor     rcx, rsp; StackCookie
0x180031028  call    __security_check_cookie
0x18003102d  add     rsp, 60h
0x180031031  pop     r14
0x180031033  pop     rdi
0x180031034  pop     rsi
0x180031035  pop     rbp
0x180031036  pop     rbx
0x180031037  retn
```
