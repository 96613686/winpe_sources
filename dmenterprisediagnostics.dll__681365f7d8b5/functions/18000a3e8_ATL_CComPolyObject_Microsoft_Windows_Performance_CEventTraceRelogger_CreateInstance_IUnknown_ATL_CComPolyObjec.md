# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x18000a3e8`
- end: `0x18000a47b`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a070`

## callees

- `0x18000183c`
- `0x1800090e0`
- `0x18000a3e8`

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
           v5,
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
0x18000a3e8  mov     [rsp+arg_8], rdx
0x18000a3ed  push    rbx
0x18000a3ee  push    rsi
0x18000a3ef  push    rdi
0x18000a3f0  sub     rsp, 20h
0x18000a3f4  mov     rbx, rdx
0x18000a3f7  mov     rsi, rcx
0x18000a3fa  test    rdx, rdx
0x18000a3fd  jnz     short loc_18000A406
0x18000a3ff  mov     eax, 80004003h
0x18000a404  jmp     short loc_18000A472
0x18000a406  mov     qword ptr [rdx], 0
0x18000a40d  mov     edi, 8007000Eh
0x18000a412  mov     [rsp+38h+arg_10], edi
0x18000a416  mov     [rsp+38h+arg_18], 0
0x18000a41f  mov     ecx, 0C0h; Size
0x18000a424  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a429  mov     rdx, rsi
0x18000a42c  mov     rcx, rax
0x18000a42f  call    ??0?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@QEAA@PEAX@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>(void *)
0x18000a434  mov     rcx, rax
0x18000a437  mov     [rsp+38h+arg_18], rax
0x18000a43c  jmp     short loc_18000A44C
0x18000a43e  mov     rbx, [rsp+38h+arg_8]
0x18000a443  mov     edi, [rsp+38h+arg_10]
0x18000a447  mov     rcx, [rsp+38h+arg_18]
0x18000a44c  test    rcx, rcx
0x18000a44f  jz      short loc_18000A46D
0x18000a451  mov     eax, [rcx+8]
0x18000a454  mov     edx, 7FFFFFFFh
0x18000a459  cmp     eax, edx
0x18000a45b  jz      short loc_18000A46B
0x18000a45d  inc     eax
0x18000a45f  mov     [rcx+8], eax
0x18000a462  cmp     eax, edx
0x18000a464  jz      short loc_18000A46B
0x18000a466  dec     eax
0x18000a468  mov     [rcx+8], eax
0x18000a46b  xor     edi, edi
0x18000a46d  mov     [rbx], rcx
0x18000a470  mov     eax, edi
0x18000a472  add     rsp, 20h
0x18000a476  pop     rdi
0x18000a477  pop     rsi
0x18000a478  pop     rbx
0x18000a479  retn
```
