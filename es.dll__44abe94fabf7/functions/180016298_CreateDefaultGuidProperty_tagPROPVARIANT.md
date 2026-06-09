# CreateDefaultGuidProperty(tagPROPVARIANT &)

- ea: `0x180016298`
- end: `0x180016371`
- name: `?CreateDefaultGuidProperty@@YAXAEAUtagPROPVARIANT@@@Z`
- size: `217`
- prototype: `void __fastcall(struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015d10`
- `0x180030820`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180012654`
- `0x180016298`
- `0x180043510`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800162f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800162f2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800162c3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800162c3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800162dd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800162dd`

## string_xrefs

- `0x180016320`: `com\complus\src\events\tier1\utilities.cpp`
- `0x180016342`: `com\complus\src\events\tier1\utilities.cpp`
- `0x180016359`: `com\complus\src\events\tier1\utilities.cpp`

## pseudocode

```c
void __fastcall CreateDefaultGuidProperty(struct tagPROPVARIANT *a1)
{
  HRESULT v2; // eax
  BSTR v3; // rax
  GUID pguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\utilities.cpp", 0x1Eu, 0x10u, v2);
  if ( StringFromGUID2(&pguid, sz, 39) != 39 )
    InternalAssert(L"com\\complus\\src\\events\\tier1\\utilities.cpp", 0x22u, 0x10u, L"len == guidLen");
  a1->vt = 8;
  v3 = SysAllocString(sz);
  a1->hVal.QuadPart = (LONGLONG)v3;
  if ( !v3 )
    InternalError(L"com\\complus\\src\\events\\tier1\\utilities.cpp", 0x25u, 0xC0001204, 0x10u);
}

```

## disassembly

```asm
0x180016298  push    rbx
0x18001629a  sub     rsp, 90h
0x1800162a1  mov     rax, cs:__security_cookie
0x1800162a8  xor     rax, rsp
0x1800162ab  mov     [rsp+98h+var_18], rax
0x1800162b3  mov     rbx, rcx
0x1800162b6  xorps   xmm0, xmm0
0x1800162b9  lea     rcx, [rsp+98h+pguid]; pguid
0x1800162be  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x1800162c3  call    cs:__imp_CoCreateGuid
0x1800162c9  test    eax, eax
0x1800162cb  js      short loc_18001631A
0x1800162cd  mov     r8d, 27h ; '''; cchMax
0x1800162d3  lea     rdx, [rsp+98h+sz]; lpsz
0x1800162d8  lea     rcx, [rsp+98h+pguid]; rguid
0x1800162dd  call    cs:__imp_StringFromGUID2
0x1800162e3  cmp     eax, 27h ; '''
0x1800162e6  jnz     short loc_180016335
0x1800162e8  lea     rcx, [rsp+98h+sz]; psz
0x1800162ed  mov     word ptr [rbx], 8
0x1800162f2  call    cs:__imp_SysAllocString
0x1800162f8  mov     [rbx+8], rax
0x1800162fc  test    rax, rax
0x1800162ff  jz      short loc_180016354
0x180016301  mov     rcx, [rsp+98h+var_18]
0x180016309  xor     rcx, rsp; StackCookie
0x18001630c  call    __security_check_cookie
0x180016311  add     rsp, 90h
0x180016318  pop     rbx
0x180016319  retn
0x18001631a  mov     r8d, 10h; unsigned __int16
0x180016320  lea     rcx, aComComplusSrcE_2; "com\\complus\\src\\events\\tier1\\utili"...
0x180016327  mov     r9d, eax; int
0x18001632a  lea     edx, [r8+0Eh]; unsigned int
0x18001632e  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180016333  jmp     short loc_1800162CD
0x180016335  mov     r8d, 10h; unsigned __int16
0x18001633b  lea     r9, aLenGuidlen; "len == guidLen"
0x180016342  lea     rcx, aComComplusSrcE_2; "com\\complus\\src\\events\\tier1\\utili"...
0x180016349  lea     edx, [r8+12h]; unsigned int
0x18001634d  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x180016352  jmp     short loc_1800162E8
0x180016354  mov     edx, 25h ; '%'; unsigned int
0x180016359  lea     rcx, aComComplusSrcE_2; "com\\complus\\src\\events\\tier1\\utili"...
0x180016360  mov     r8d, 0C0001204h; unsigned int
0x180016366  lea     r9d, [rdx-15h]; unsigned __int16
0x18001636a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001636f  jmp     short loc_180016301
```
