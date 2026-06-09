# TMetabase_XMLtable::LoadDocumentFromURL(IXMLDOMDocument *)

- ea: `0x18000c8e4`
- end: `0x18000c9cc`
- name: `?LoadDocumentFromURL@TMetabase_XMLtable@@AEAAJPEAUIXMLDOMDocument@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ce00`

## callees

- `0x180005b50`
- `0x18000c8e4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000c9bb`
- `OLEAUT32!__imp_VariantClear` at `0x18000c9bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TMetabase_XMLtable::LoadDocumentFromURL(TMetabase_XMLtable *this, struct IXMLDOMDocument *a2)
{
  __int64 result; // rax
  signed int v5; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG v7; // [rsp+40h] [rbp-28h] BYREF
  __int16 v8; // [rsp+98h] [rbp+30h] BYREF

  result = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))a2->lpVtbl->put_async)(a2, 0);
  if ( (int)result >= 0 )
  {
    result = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64))a2->lpVtbl->put_resolveExternals)(
               a2,
               0xFFFFFFFFLL);
    if ( (int)result >= 0 )
    {
      v8 = 0;
      pvarg.vt = 0;
      ATL::CComVariant::operator=(&pvarg, (char *)this + 40);
      v7 = pvarg;
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, VARIANTARG *, __int16 *))a2->lpVtbl->load)(a2, &v7, &v8);
      if ( v5 >= 0 )
      {
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        v5 = v8 != -1 ? 0x80004005 : 0;
      }
      else if ( pvarg.vt == 4095 )
      {
        pvarg.vt = 8;
      }
      VariantClear(&pvarg);
      return (unsigned int)v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c8e4  push    rbp
0x18000c8e6  push    rbx
0x18000c8e7  push    rsi
0x18000c8e8  push    rdi
0x18000c8e9  mov     rbp, rsp
0x18000c8ec  sub     rsp, 68h
0x18000c8f0  mov     rbx, rdx
0x18000c8f3  mov     rdi, rcx
0x18000c8f6  mov     rax, [rdx]
0x18000c8f9  xor     edx, edx
0x18000c8fb  mov     rcx, rbx
0x18000c8fe  mov     rax, [rax+1F8h]
0x18000c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90a  test    eax, eax
0x18000c90c  js      loc_18000C9C3
0x18000c912  mov     rax, [rbx]
0x18000c915  or      esi, 0FFFFFFFFh
0x18000c918  mov     edx, esi
0x18000c91a  mov     rcx, rbx
0x18000c91d  mov     rax, [rax+230h]
0x18000c924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c929  test    eax, eax
0x18000c92b  js      loc_18000C9C3
0x18000c931  xor     eax, eax
0x18000c933  mov     [rbp+arg_8], ax
0x18000c937  mov     word ptr [rbp+pvarg], ax
0x18000c93b  lea     rdx, [rdi+28h]
0x18000c93f  lea     rcx, [rbp+pvarg]
0x18000c943  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAG@Z; ATL::CComVariant::operator=(ushort *)
0x18000c948  nop
0x18000c949  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000c94d  movaps  [rbp+var_28], xmm0
0x18000c951  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000c956  movsd   [rbp+var_18], xmm1
0x18000c95b  mov     rax, [rbx]
0x18000c95e  lea     r8, [rbp+arg_8]
0x18000c962  lea     rdx, [rbp+var_28]
0x18000c966  mov     rcx, rbx
0x18000c969  mov     rax, [rax+1D0h]
0x18000c970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c975  mov     ebx, eax
0x18000c977  test    eax, eax
0x18000c979  jns     short loc_18000C98F
0x18000c97b  mov     ecx, 0FFFh
0x18000c980  cmp     word ptr [rbp+pvarg], cx
0x18000c984  jnz     short loc_18000C9B7
0x18000c986  lea     ecx, [rsi+9]
0x18000c989  mov     word ptr [rbp+pvarg], cx
0x18000c98d  jmp     short loc_18000C9B7
0x18000c98f  movzx   eax, [rbp+arg_8]
0x18000c993  sub     ax, si
0x18000c996  neg     ax
0x18000c999  sbb     edx, edx
0x18000c99b  and     edx, 80004005h
0x18000c9a1  mov     ecx, 0FFFh
0x18000c9a6  cmp     word ptr [rbp+pvarg], cx
0x18000c9aa  jnz     short loc_18000C9B5
0x18000c9ac  mov     ecx, 8
0x18000c9b1  mov     word ptr [rbp+pvarg], cx
0x18000c9b5  mov     ebx, edx
0x18000c9b7  lea     rcx, [rbp+pvarg]; pvarg
0x18000c9bb  call    cs:__imp_VariantClear
0x18000c9c1  mov     eax, ebx
0x18000c9c3  add     rsp, 68h
0x18000c9c7  pop     rdi
0x18000c9c8  pop     rsi
0x18000c9c9  pop     rbx
0x18000c9ca  pop     rbp
0x18000c9cb  retn
```
