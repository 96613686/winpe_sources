# AnswerFileGenerator::AddHelperAttribute(tagHELPER_ATTRIBUTE * const)

- ea: `0x18000bca0`
- end: `0x18000bd1c`
- name: `?AddHelperAttribute@AnswerFileGenerator@@QEAAJQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(AnswerFileGenerator *this, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000dd58`

## callees

- `0x18000bca0`
- `0x18000bd24`
- `0x18000cde4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000bd06`
- `ole32!CoTaskMemFree` at `0x18000bd06`

## pseudocode

```c
__int64 __fastcall AnswerFileGenerator::AddHelperAttribute(
        AnswerFileGenerator *this,
        struct tagHELPER_ATTRIBUTE *const a2)
{
  int HelperAttributeXML; // edi
  void *v4; // rbx
  __int64 v5; // r8
  const ATL::CAtlException *v7; // [rsp+20h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  pv = 0;
  HelperAttributeXML = ((int (__stdcall *)(struct tagHELPER_ATTRIBUTE *const, unsigned __int16 **))GetHelperAttributeXML)(
                         a2,
                         (unsigned __int16 **)&pv);
  if ( HelperAttributeXML >= 0 )
  {
    v4 = pv;
    if ( pv )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_WORD *)pv + v5) );
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      ATL::CSimpleStringT<unsigned short,0>::Append((char *)this + 8, pv);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v7) )
      {
        v4 = pv;
        HelperAttributeXML = *(_DWORD *)v7;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000BCFA);
      }
    }
    CoTaskMemFree(v4);
  }
  return (unsigned int)HelperAttributeXML;
}

```

## disassembly

```asm
0x18000bca0  mov     [rsp+arg_0], rbx
0x18000bca5  push    rsi
0x18000bca6  push    rdi
0x18000bca7  push    r14
0x18000bca9  sub     rsp, 30h
0x18000bcad  mov     rax, rdx
0x18000bcb0  mov     rsi, rcx
0x18000bcb3  xor     r14d, r14d
0x18000bcb6  mov     [rsp+48h+pv], r14
0x18000bcbb  lea     rdx, [rsp+48h+pv]; unsigned __int16 **
0x18000bcc0  mov     rcx, rax; struct tagHELPER_ATTRIBUTE *
0x18000bcc3  call    ?GetHelperAttributeXML@@YAJQEAUtagHELPER_ATTRIBUTE@@PEAPEAG@Z; GetHelperAttributeXML(tagHELPER_ATTRIBUTE * const,ushort * *)
0x18000bcc8  mov     edi, eax
0x18000bcca  test    eax, eax
0x18000bccc  js      short loc_18000BD0C
0x18000bcce  mov     rbx, [rsp+48h+pv]
0x18000bcd3  test    rbx, rbx
0x18000bcd6  jnz     short loc_18000BCDD
0x18000bcd8  mov     r8d, r14d
0x18000bcdb  jmp     short loc_18000BCEB
0x18000bcdd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bce1  inc     r8
0x18000bce4  cmp     [rbx+r8*2], r14w
0x18000bce9  jnz     short loc_18000BCE1
0x18000bceb  lea     rcx, [rsi+8]
0x18000bcef  mov     rdx, rbx
0x18000bcf2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000bcf7  nop
0x18000bcf8  jmp     short loc_18000BD03
0x18000bcfa  mov     rbx, [rsp+48h+pv]
0x18000bcff  mov     edi, [rsp+48h+arg_10]
0x18000bd03  mov     rcx, rbx; pv
0x18000bd06  call    cs:__imp_CoTaskMemFree
0x18000bd0c  mov     eax, edi
0x18000bd0e  mov     rbx, [rsp+48h+arg_0]
0x18000bd13  add     rsp, 30h
0x18000bd17  pop     r14
0x18000bd19  pop     rdi
0x18000bd1a  pop     rsi
0x18000bd1b  retn
```
