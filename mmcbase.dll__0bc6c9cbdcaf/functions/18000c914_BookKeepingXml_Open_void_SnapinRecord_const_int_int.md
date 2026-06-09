# BookKeepingXml::Open(void *,SnapinRecord const &,int,int)

- ea: `0x18000c914`
- end: `0x18000cae7`
- name: `?Open@BookKeepingXml@@QEAAJPEAXAEBVSnapinRecord@@HH@Z`
- size: `467`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this, void *, const struct SnapinRecord *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x180008630`
- `0x18000c2d8`
- `0x18000c378`
- `0x18000c3e8`
- `0x18000c68c`
- `0x18000c914`
- `0x180010290`
- `0x18001b550`

## import_xrefs

- `msvcrt!_itow` at `0x18000c9ef`
- `msvcrt!_itow` at `0x18000ca02`
- `msvcrt!_itow` at `0x18000c9ef`
- `msvcrt!_itow` at `0x18000ca02`

## string_xrefs

- `0x18000c9a0`: `<?xml version="1.0"?>\n`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::Open(BookKeepingXml *this, void *a2, const struct SnapinRecord *a3)
{
  int v5; // ebx
  _WORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  wchar_t v11[12]; // [rsp+40h] [rbp-48h] BYREF
  wchar_t Buffer[12]; // [rsp+58h] [rbp-30h] BYREF

  if ( a2 == (void *)-1LL )
  {
    v5 = -2147024809;
    goto LABEL_20;
  }
  *((_QWORD *)this + 2) = a2;
  v6 = (_WORD *)((char *)this + 40);
  *((_QWORD *)this + 4) = 4096;
  *((_QWORD *)this + 3) = v6;
  *v6 = 0;
  v5 = BookKeepingXml::CheckBufferSize(this, 0x17u);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_20;
    v8 = 10;
    goto LABEL_19;
  }
  v5 = BookKeepingXml::Append(this, aXmlVersion10);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_20;
    v8 = 11;
    goto LABEL_19;
  }
  _itow(3, Buffer, 10);
  _itow(0, v11, 10);
  LOBYTE(v9) = 1;
  v5 = BookKeepingXml::AddXml(this, v9, 3);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_20;
    v8 = 12;
    goto LABEL_19;
  }
  *((_DWORD *)this + 2058) = 3;
  v5 = SnapinRecord::Dump(a3, this);
  if ( v5 >= 0 )
  {
    *((_DWORD *)this + 2058) = 50;
    return (unsigned int)v5;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v8 = 13;
LABEL_19:
    WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids, (unsigned int)v5);
  }
LABEL_20:
  BookKeepingXml::Empty(this);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c914  mov     [rsp+arg_8], rbx
0x18000c919  mov     [rsp+arg_18], rbp
0x18000c91e  push    rdi
0x18000c91f  sub     rsp, 80h
0x18000c926  mov     rax, cs:__security_cookie
0x18000c92d  xor     rax, rsp
0x18000c930  mov     [rsp+88h+var_18], rax
0x18000c935  mov     rbp, r8
0x18000c938  mov     rdi, rcx
0x18000c93b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000c93f  jnz     short loc_18000C94B
0x18000c941  mov     ebx, 80070057h
0x18000c946  jmp     loc_18000CAAF
0x18000c94b  mov     [rcx+10h], rdx
0x18000c94f  xor     eax, eax
0x18000c951  add     rcx, 28h ; '('
0x18000c955  mov     qword ptr [rdi+20h], 1000h
0x18000c95d  mov     [rdi+18h], rcx
0x18000c961  lea     edx, [rax+17h]; unsigned __int64
0x18000c964  mov     [rcx], ax
0x18000c967  mov     rcx, rdi; this
0x18000c96a  call    ?CheckBufferSize@BookKeepingXml@@AEAAJ_K@Z; BookKeepingXml::CheckBufferSize(unsigned __int64)
0x18000c96f  mov     ebx, eax
0x18000c971  test    eax, eax
0x18000c973  jns     short loc_18000C9A0
0x18000c975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c97c  lea     rax, WPP_GLOBAL_Control
0x18000c983  cmp     rcx, rax
0x18000c986  jz      loc_18000CAAF
0x18000c98c  cmp     byte ptr [rcx+19h], 2
0x18000c990  jb      loc_18000CAAF
0x18000c996  mov     edx, 0Ah
0x18000c99b  jmp     loc_18000CA9C
0x18000c9a0  lea     rdx, aXmlVersion10; "<?xml version=\"1.0\"?>\r\n"
0x18000c9a7  mov     rcx, rdi; this
0x18000c9aa  call    ?Append@BookKeepingXml@@AEAAJPEBGZZ; BookKeepingXml::Append(ushort const *,...)
0x18000c9af  mov     ebx, eax
0x18000c9b1  test    eax, eax
0x18000c9b3  jns     short loc_18000C9E0
0x18000c9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9bc  lea     rax, WPP_GLOBAL_Control
0x18000c9c3  cmp     rcx, rax
0x18000c9c6  jz      loc_18000CAAF
0x18000c9cc  cmp     byte ptr [rcx+19h], 2
0x18000c9d0  jb      loc_18000CAAF
0x18000c9d6  mov     edx, 0Bh
0x18000c9db  jmp     loc_18000CA9C
0x18000c9e0  mov     r8d, 0Ah; Radix
0x18000c9e6  lea     rdx, [rsp+88h+Buffer]; Buffer
0x18000c9eb  lea     ecx, [r8-7]; Value
0x18000c9ef  call    cs:__imp__itow
0x18000c9f5  mov     r8d, 0Ah; Radix
0x18000c9fb  lea     rdx, [rsp+88h+var_48]; Buffer
0x18000ca00  xor     ecx, ecx; Value
0x18000ca02  call    cs:__imp__itow
0x18000ca08  lea     rax, [rsp+88h+var_48]
0x18000ca0d  xor     r9d, r9d
0x18000ca10  mov     [rsp+88h+var_50], rax
0x18000ca15  mov     dl, 1
0x18000ca17  lea     rax, [rsp+88h+Buffer]
0x18000ca1c  mov     [rsp+88h+var_58], 0Ah
0x18000ca24  mov     [rsp+88h+var_60], rax
0x18000ca29  mov     rcx, rdi
0x18000ca2c  lea     r8d, [r9+3]
0x18000ca30  mov     [rsp+88h+var_68], 9
0x18000ca38  call    ?AddXml@BookKeepingXml@@AEAAJ_NW4_XmlNameId@1@PEBG1212@Z; BookKeepingXml::AddXml(bool,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *,BookKeepingXml::_XmlNameId,ushort const *)
0x18000ca3d  mov     ebx, eax
0x18000ca3f  test    eax, eax
0x18000ca41  jns     short loc_18000CA63
0x18000ca43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca4a  lea     rax, WPP_GLOBAL_Control
0x18000ca51  cmp     rcx, rax
0x18000ca54  jz      short loc_18000CAAF
0x18000ca56  cmp     byte ptr [rcx+19h], 2
0x18000ca5a  jb      short loc_18000CAAF
0x18000ca5c  mov     edx, 0Ch
0x18000ca61  jmp     short loc_18000CA9C
0x18000ca63  mov     rdx, rdi; struct BookKeepingXml *
0x18000ca66  mov     dword ptr [rdi+2028h], 3
0x18000ca70  mov     rcx, rbp; this
0x18000ca73  call    ?Dump@SnapinRecord@@QEBAJAEAVBookKeepingXml@@@Z; SnapinRecord::Dump(BookKeepingXml &)
0x18000ca78  mov     ebx, eax
0x18000ca7a  test    eax, eax
0x18000ca7c  jns     short loc_18000CAB9
0x18000ca7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca85  lea     rax, WPP_GLOBAL_Control
0x18000ca8c  cmp     rcx, rax
0x18000ca8f  jz      short loc_18000CAAF
0x18000ca91  cmp     byte ptr [rcx+19h], 2
0x18000ca95  jb      short loc_18000CAAF
0x18000ca97  mov     edx, 0Dh
0x18000ca9c  mov     rcx, [rcx+10h]
0x18000caa0  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000caa7  mov     r9d, ebx
0x18000caaa  call    WPP_SF_d
0x18000caaf  mov     rcx, rdi; this
0x18000cab2  call    ?Empty@BookKeepingXml@@QEAAXXZ; BookKeepingXml::Empty(void)
0x18000cab7  jmp     short loc_18000CAC3
0x18000cab9  mov     dword ptr [rdi+2028h], 32h ; '2'
0x18000cac3  mov     eax, ebx
0x18000cac5  mov     rcx, [rsp+88h+var_18]
0x18000caca  xor     rcx, rsp; StackCookie
0x18000cacd  call    __security_check_cookie
0x18000cad2  lea     r11, [rsp+88h+var_8]
0x18000cada  mov     rbx, [r11+18h]
0x18000cade  mov     rbp, [r11+28h]
0x18000cae2  mov     rsp, r11
0x18000cae5  pop     rdi
0x18000cae6  retn
```
