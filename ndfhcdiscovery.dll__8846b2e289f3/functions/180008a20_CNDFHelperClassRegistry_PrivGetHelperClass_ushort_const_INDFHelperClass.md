# CNDFHelperClassRegistry::PrivGetHelperClass(ushort const *,INDFHelperClass * *)

- ea: `0x180008a20`
- end: `0x180008ae5`
- name: `?PrivGetHelperClass@CNDFHelperClassRegistry@@AEAAJPEBGPEAPEAUINDFHelperClass@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, const unsigned __int16 *, struct INDFHelperClass **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007520`
- `0x1800075c0`

## callees

- `0x180006a6c`
- `0x180007018`
- `0x180008a20`
- `0x18000b0cc`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::PrivGetHelperClass(
        CNDFHelperClassRegistry *this,
        const unsigned __int16 *a2,
        struct INDFHelperClass **a3)
{
  _QWORD *v3; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 *CaseInsensitive; // rax
  __int64 result; // rax
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v3 = (_QWORD *)((char *)this + 584);
  FindCaseInsensitive(&v13, a2, (char *)this + 584);
  v9 = v13;
  if ( v13 == *v3
    && (CaseInsensitive = (__int64 *)FindCaseInsensitive(&v13, a2, (char *)this + 600),
        v9 = *CaseInsensitive,
        *CaseInsensitive == *((_QWORD *)this + 75)) )
  {
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqz_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)HelperClassError, -2147024894, 320, a2);
    return 2147942402LL;
  }
  else
  {
    v12 = 0;
    result = ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(v8, v7, &v12);
    if ( (int)result >= 0 )
    {
      *(_QWORD *)(v12 + 64) = *(_QWORD *)(v9 + 64);
      *a3 = (struct INDFHelperClass *)v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008a20  mov     [rsp+arg_8], rbx
0x180008a25  mov     [rsp+arg_10], rbp
0x180008a2a  push    rsi
0x180008a2b  push    rdi
0x180008a2c  push    r14
0x180008a2e  sub     rsp, 30h
0x180008a32  lea     rdi, [rcx+248h]
0x180008a39  mov     r14, r8
0x180008a3c  mov     rbp, rcx
0x180008a3f  mov     r8, rdi
0x180008a42  lea     rcx, [rsp+48h+arg_18]
0x180008a47  mov     rsi, rdx
0x180008a4a  call    FindCaseInsensitive
0x180008a4f  mov     rbx, [rsp+48h+arg_18]
0x180008a54  cmp     rbx, [rdi]
0x180008a57  jnz     short loc_180008AA5
0x180008a59  lea     rdi, [rbp+258h]
0x180008a60  mov     rdx, rsi
0x180008a63  mov     r8, rdi
0x180008a66  lea     rcx, [rsp+48h+arg_18]
0x180008a6b  call    FindCaseInsensitive
0x180008a70  mov     rbx, [rax]
0x180008a73  cmp     rbx, [rdi]
0x180008a76  jnz     short loc_180008AA5
0x180008a78  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x180008a7f  jz      short loc_180008A9E
0x180008a81  mov     r9d, 140h
0x180008a87  mov     [rsp+48h+var_28], rsi
0x180008a8c  mov     r8d, 80070002h
0x180008a92  lea     rdx, HelperClassError
0x180008a99  call    McTemplateU0qqz_EventWriteTransfer
0x180008a9e  mov     eax, 80070002h
0x180008aa3  jmp     short loc_180008AD1
0x180008aa5  lea     r8, [rsp+48h+arg_0]
0x180008aaa  mov     [rsp+48h+arg_0], 0
0x180008ab3  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCINDFHelperClassImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CINDFHelperClassImpl>>::CreateInstance(void *,_GUID const &,void * *)
0x180008ab8  test    eax, eax
0x180008aba  js      short loc_180008AD1
0x180008abc  mov     rcx, [rsp+48h+arg_0]
0x180008ac1  mov     rdx, [rbx+40h]
0x180008ac5  mov     [rcx+40h], rdx
0x180008ac9  mov     rcx, [rsp+48h+arg_0]
0x180008ace  mov     [r14], rcx
0x180008ad1  mov     rbx, [rsp+48h+arg_8]
0x180008ad6  mov     rbp, [rsp+48h+arg_10]
0x180008adb  add     rsp, 30h
0x180008adf  pop     r14
0x180008ae1  pop     rdi
0x180008ae2  pop     rsi
0x180008ae3  retn
```
