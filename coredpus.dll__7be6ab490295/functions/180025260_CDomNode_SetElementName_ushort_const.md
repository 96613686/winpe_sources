# CDomNode::SetElementName(ushort const *)

- ea: `0x180025260`
- end: `0x1800252f5`
- name: `?SetElementName@CDomNode@@UEAAJPEBG@Z`
- size: `149`
- prototype: `__int64 __fastcall(CDomNode *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013890`
- `0x18001d87c`
- `0x180025260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800252c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800252c8`

## pseudocode

```c
__int64 __fastcall CDomNode::SetElementName(CDomNode *this, const unsigned __int16 *a2)
{
  unsigned int Instance; // ebx
  char *v4; // rsi
  LPVOID *ppv; // rdi

  Instance = 0;
  if ( a2 )
  {
    try
    {
      v4 = (char *)this + 128;
      std::wstring::assign((char *)this + 128);
      ppv = (LPVOID *)((char *)this + 184);
      if ( !*ppv && !(unsigned int)std::wstring::compare(v4, L"wap-provisioningdoc") )
        Instance = CoCreateInstance(
                     &GUID_dd1432d7_b76b_4227_9c57_d82e9d844441,
                     0,
                     1u,
                     &GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314,
                     ppv);
    }
    catch ( std::bad_alloc )
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return Instance;
}

```

## disassembly

```asm
0x180025260  mov     [rsp+arg_0], rbx
0x180025265  mov     [rsp+arg_10], rsi
0x18002526a  push    rdi
0x18002526b  sub     rsp, 30h
0x18002526f  mov     rdi, rcx
0x180025272  xor     ebx, ebx
0x180025274  test    rdx, rdx
0x180025277  jnz     short loc_180025280
0x180025279  mov     ebx, 80070057h
0x18002527e  jmp     short loc_1800252E2
0x180025280  lea     rsi, [rcx+80h]
0x180025287  mov     rcx, rsi
0x18002528a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002528f  add     rdi, 0B8h
0x180025296  cmp     qword ptr [rdi], 0
0x18002529a  jnz     short loc_1800252DC
0x18002529c  lea     rdx, aWapProvisionin_0; "wap-provisioningdoc"
0x1800252a3  mov     rcx, rsi
0x1800252a6  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800252ab  test    eax, eax
0x1800252ad  jnz     short loc_1800252DC
0x1800252af  mov     [rsp+38h+ppv], rdi; ppv
0x1800252b4  lea     r9, _GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314; riid
0x1800252bb  xor     edx, edx; pUnkOuter
0x1800252bd  lea     r8d, [rax+1]; dwClsContext
0x1800252c1  lea     rcx, _GUID_dd1432d7_b76b_4227_9c57_d82e9d844441; rclsid
0x1800252c8  call    cs:__imp_CoCreateInstance
0x1800252cf  nop     dword ptr [rax+rax+00h]
0x1800252d4  mov     ebx, eax
0x1800252d6  test    eax, eax
0x1800252d8  jns     short loc_1800252DC
0x1800252da  jmp     short loc_1800252E2
0x1800252dc  jmp     short loc_1800252E2
0x1800252de  mov     ebx, [rsp+38h+arg_8]
0x1800252e2  mov     eax, ebx
0x1800252e4  mov     rbx, [rsp+38h+arg_0]
0x1800252e9  mov     rsi, [rsp+38h+arg_10]
0x1800252ee  add     rsp, 30h
0x1800252f2  pop     rdi
0x1800252f3  retn
```
