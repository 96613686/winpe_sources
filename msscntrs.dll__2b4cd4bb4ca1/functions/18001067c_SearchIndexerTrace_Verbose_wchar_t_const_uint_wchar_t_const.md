# SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)

- ea: `0x18001067c`
- end: `0x180010711`
- name: `?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ`
- size: `149`
- prototype: `void(wchar_t *this, const wchar_t *, __int64, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18000da9c`
- `0x18000fd0c`
- `0x180010d50`
- `0x180010db0`
- `0x180011500`

## callees

- `0x1800024a0`
- `0x180004764`
- `0x18000de7c`
- `0x18001067c`
- `0x180010718`
- `0x180010a34`

## pseudocode

```c
void SearchIndexerTrace::Verbose(wchar_t *this, const wchar_t *a2, __int64 a3, const wchar_t *a4, ...)
{
  unsigned int v4; // edi
  _DWORD *v6; // rax
  const wchar_t *v7; // r8
  wchar_t *v8[4]; // [rsp+28h] [rbp-40h] BYREF
  const wchar_t *v10; // [rsp+88h] [rbp+20h] BYREF

  v10 = a4;
  v4 = (unsigned int)a2;
  v6 = (_DWORD *)*((_QWORD *)SearchIndexerTraceProvider::Instance() + 1);
  if ( v6 && *v6 > 5u )
  {
    format_string::format_va(v8, a3, &v10);
    v7 = (const wchar_t *)v8;
    if ( v8[3] > (wchar_t *)7 )
      v7 = v8[0];
    SearchIndexerTraceProvider::Verbose(this, v4, v7);
    std::wstring::~wstring((char **)v8);
  }
}

```

## disassembly

```asm
0x18001067c  mov     [rsp+arg_10], r8
0x180010681  mov     [rsp+arg_18], r9
0x180010686  push    rbx
0x180010687  push    rdi
0x180010688  sub     rsp, 58h
0x18001068c  mov     rax, cs:__security_cookie
0x180010693  xor     rax, rsp
0x180010696  mov     [rsp+68h+var_20], rax
0x18001069b  mov     edi, edx
0x18001069d  mov     rbx, rcx
0x1800106a0  call    ?Instance@SearchIndexerTraceProvider@@KAPEAU1@XZ; SearchIndexerTraceProvider::Instance(void)
0x1800106a5  mov     rax, [rax+8]
0x1800106a9  test    rax, rax
0x1800106ac  jz      short loc_1800106FD
0x1800106ae  mov     eax, [rax]
0x1800106b0  cmp     eax, 5
0x1800106b3  jbe     short loc_1800106FD
0x1800106b5  mov     rdx, [rsp+68h+arg_10]
0x1800106bd  lea     r8, [rsp+68h+arg_18]
0x1800106c5  lea     rcx, [rsp+68h+var_40]
0x1800106ca  mov     [rsp+68h+var_48], 0
0x1800106d3  call    ?format_va@format_string@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WPEAD@Z; format_string::format_va(wchar_t const *,char *)
0x1800106d8  cmp     [rsp+68h+var_28], 7
0x1800106de  lea     r8, [rsp+68h+var_40]
0x1800106e3  mov     edx, edi; unsigned int
0x1800106e5  mov     rcx, rbx; wchar_t *
0x1800106e8  cmova   r8, [rsp+68h+var_40]; wchar_t *
0x1800106ee  call    ?Verbose@SearchIndexerTraceProvider@@SAXPEB_WI0@Z; SearchIndexerTraceProvider::Verbose(wchar_t const *,uint,wchar_t const *)
0x1800106f3  lea     rcx, [rsp+68h+var_40]
0x1800106f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800106fd  mov     rcx, [rsp+68h+var_20]
0x180010702  xor     rcx, rsp; StackCookie
0x180010705  call    __security_check_cookie
0x18001070a  add     rsp, 58h
0x18001070e  pop     rdi
0x18001070f  pop     rbx
0x180010710  retn
```
