# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x180009e80`
- end: `0x180009f12`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009b10`

## callees

- `0x18000181c`
- `0x180008c94`
- `0x180009e80`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rbx
  void *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+58h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  try
  {
    *a2 = 0;
    v9 = -2147024882;
    v5 = operator new(0xC0u);
    v6 = ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(
           (__int64)v5,
           a1);
    v11 = v6;
  }
  catch ( ... )
  {
    v2 = a2;
    v9 = -2147024882;
    v6 = v11;
  }
  if ( v6 )
  {
    v7 = *(_DWORD *)(v6 + 8);
    if ( v7 != 0x7FFFFFFF )
    {
      v8 = v7 + 1;
      *(_DWORD *)(v6 + 8) = v8;
      if ( v8 != 0x7FFFFFFF )
        *(_DWORD *)(v6 + 8) = v8 - 1;
    }
    v9 = 0;
  }
  *v2 = v6;
  return v9;
}

```

## disassembly

```asm
0x180009e80  mov     [rsp+arg_8], rdx
0x180009e85  push    rbx
0x180009e86  push    rsi
0x180009e87  push    rdi
0x180009e88  sub     rsp, 20h
0x180009e8c  mov     rbx, rdx
0x180009e8f  mov     rsi, rcx
0x180009e92  test    rdx, rdx
0x180009e95  jnz     short loc_180009E9E
0x180009e97  mov     eax, 80004003h
0x180009e9c  jmp     short loc_180009F0A
0x180009e9e  mov     qword ptr [rdx], 0
0x180009ea5  mov     edi, 8007000Eh
0x180009eaa  mov     [rsp+38h+arg_10], edi
0x180009eae  mov     [rsp+38h+arg_18], 0
0x180009eb7  mov     ecx, 0C0h; Size
0x180009ebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ec1  mov     rdx, rsi
0x180009ec4  mov     rcx, rax
0x180009ec7  call    ??0?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@QEAA@PEAX@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void *)
0x180009ecc  mov     rcx, rax
0x180009ecf  mov     [rsp+38h+arg_18], rax
0x180009ed4  jmp     short loc_180009EE4
0x180009ed6  mov     rbx, [rsp+38h+arg_8]
0x180009edb  mov     edi, [rsp+38h+arg_10]
0x180009edf  mov     rcx, [rsp+38h+arg_18]
0x180009ee4  test    rcx, rcx
0x180009ee7  jz      short loc_180009F05
0x180009ee9  mov     eax, [rcx+8]
0x180009eec  mov     edx, 7FFFFFFFh
0x180009ef1  cmp     eax, edx
0x180009ef3  jz      short loc_180009F03
0x180009ef5  inc     eax
0x180009ef7  mov     [rcx+8], eax
0x180009efa  cmp     eax, edx
0x180009efc  jz      short loc_180009F03
0x180009efe  dec     eax
0x180009f00  mov     [rcx+8], eax
0x180009f03  xor     edi, edi
0x180009f05  mov     [rbx], rcx
0x180009f08  mov     eax, edi
0x180009f0a  add     rsp, 20h
0x180009f0e  pop     rdi
0x180009f0f  pop     rsi
0x180009f10  pop     rbx
0x180009f11  retn
```
