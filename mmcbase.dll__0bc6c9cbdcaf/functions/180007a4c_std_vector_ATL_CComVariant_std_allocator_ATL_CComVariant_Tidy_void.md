# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Tidy(void)

- ea: `0x180007a4c`
- end: `0x180007a8c`
- name: `?_Tidy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXXZ`
- size: `64`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004bf0`
- `0x180004e20`
- `0x180007a18`
- `0x180013d80`
- `0x18001b7b4`
- `0x18001bf3b`

## callees

- `0x180007a4c`
- `0x180013e30`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007a69`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180007a69`

## pseudocode

```c
void __fastcall std::vector<ATL::CComVariant>::_Tidy(_QWORD *a1)
{
  if ( *a1 )
  {
    std::vector<ATL::CComVariant>::_Destroy(a1, *a1, a1[1]);
    operator delete((void *)*a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180007a4c  push    rbx
0x180007a4e  sub     rsp, 20h
0x180007a52  mov     rdx, [rcx]
0x180007a55  mov     rbx, rcx
0x180007a58  test    rdx, rdx
0x180007a5b  jz      short loc_180007A86
0x180007a5d  mov     r8, [rcx+8]
0x180007a61  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x180007a66  mov     rcx, [rbx]
0x180007a69  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007a6f  mov     qword ptr [rbx], 0
0x180007a76  mov     qword ptr [rbx+8], 0
0x180007a7e  mov     qword ptr [rbx+10h], 0
0x180007a86  add     rsp, 20h
0x180007a8a  pop     rbx
0x180007a8b  retn
```
