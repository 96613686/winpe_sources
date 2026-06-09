# MSXML::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)

- ea: `0x140028454`
- end: `0x1400284db`
- name: `?setProperty@IXMLDOMDocument2@MSXML@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028040`

## callees

- `0x1400193b4`
- `0x140028454`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MSXML::IXMLDOMDocument2::setProperty(struct IUnknown *a1, _bstr_t *a2, __int128 *a3)
{
  ULONG (__stdcall *Release)(IUnknown *); // r9
  __int64 v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  __int128 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  Release = a1->lpVtbl[26].Release;
  if ( *(_QWORD *)a2 )
    v6 = **(_QWORD **)a2;
  else
    v6 = 0;
  v10 = *a3;
  v11 = *((_QWORD *)a3 + 2);
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int128 *))Release)(a1, v6, &v10);
  v8 = v7;
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
  _bstr_t::~_bstr_t(a2);
  return v8;
}

```

## disassembly

```asm
0x140028454  mov     [rsp+arg_0], rbx
0x140028459  mov     [rsp+arg_10], rsi
0x14002845e  mov     [rsp+arg_8], rdx
0x140028463  push    rdi
0x140028464  sub     rsp, 40h
0x140028468  mov     rbx, rdx
0x14002846b  mov     rsi, rcx
0x14002846e  mov     rax, [rcx]
0x140028471  mov     r9, [rax+280h]
0x140028478  mov     rax, [rdx]
0x14002847b  test    rax, rax
0x14002847e  jz      short loc_140028485
0x140028480  mov     rdx, [rax]
0x140028483  jmp     short loc_140028487
0x140028485  xor     edx, edx
0x140028487  movups  xmm0, xmmword ptr [r8]
0x14002848b  movaps  [rsp+48h+var_28], xmm0
0x140028490  movsd   xmm1, qword ptr [r8+10h]
0x140028496  movsd   [rsp+48h+var_18], xmm1
0x14002849c  lea     r8, [rsp+48h+var_28]
0x1400284a1  mov     rax, r9
0x1400284a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400284a9  mov     edi, eax
0x1400284ab  test    eax, eax
0x1400284ad  js      short loc_1400284C9
0x1400284af  mov     rcx, rbx; this
0x1400284b2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1400284b7  mov     eax, edi
0x1400284b9  mov     rbx, [rsp+48h+arg_0]
0x1400284be  mov     rsi, [rsp+48h+arg_10]
0x1400284c3  add     rsp, 40h
0x1400284c7  pop     rdi
0x1400284c8  retn
0x1400284c9  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x1400284d0  mov     rdx, rsi; struct IUnknown *
0x1400284d3  mov     ecx, edi; int
0x1400284d5  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
