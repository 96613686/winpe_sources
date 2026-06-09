# AddToSeeAlsoList(std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>> *,IShellFolder2 *,_ITEMID_CHILD const *)

- ea: `0x18001a5e8`
- end: `0x18001a6be`
- name: `?AddToSeeAlsoList@@YAJPEAV?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@PEAUIShellFolder2@@PEBU_ITEMID_CHILD@@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aac8`

## callees

- `0x180007828`
- `0x18001a5e8`
- `0x18001a900`
- `0x18001aa40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6a1`

## pseudocode

```c
__int64 __fastcall AddToSeeAlsoList(__int64 a1, struct IShellFolder2 *a2, const struct _ITEMID_CHILD *a3)
{
  int DisplayName; // ebx
  unsigned __int16 *v7; // rdi
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[48]; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int16 *v11; // [rsp+78h] [rbp+20h] BYREF

  if ( a1 && a2 && a3 )
  {
    v11 = 0;
    pv = 0;
    DisplayName = GetDisplayName(a2, a3, 0x8000u, &v11);
    if ( DisplayName >= 0 )
    {
      if ( (unsigned int)IsOnSeeAlsoList(v11) )
      {
        DisplayName = GetDisplayName(a2, a3, 0, (unsigned __int16 **)&pv);
        if ( DisplayName >= 0 )
        {
          try
          {
            v7 = v11;
            *(_QWORD *)(*(_QWORD *)std::map<unsigned short *,unsigned short *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,unsigned short *>>>::_Try_emplace<unsigned short * const &,>(
                                     a1,
                                     v10,
                                     &pv)
                      + 40LL) = v7;
          }
          catch ( ... )
          {
            DisplayName = -2147024882;
            goto LABEL_8;
          }
          return (unsigned int)DisplayName;
        }
LABEL_8:
        CoTaskMemFree(pv);
      }
      CoTaskMemFree(v11);
    }
    return (unsigned int)DisplayName;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001a5e8  mov     rax, rsp
0x18001a5eb  mov     [rax+10h], rbx
0x18001a5ef  push    rsi
0x18001a5f0  push    rdi
0x18001a5f1  push    r14
0x18001a5f3  sub     rsp, 40h
0x18001a5f7  mov     rdi, r8
0x18001a5fa  mov     rsi, rdx
0x18001a5fd  mov     r14, rcx
0x18001a600  test    rcx, rcx
0x18001a603  jz      loc_18001A6AB
0x18001a609  test    rdx, rdx
0x18001a60c  jz      loc_18001A6AB
0x18001a612  test    r8, r8
0x18001a615  jz      loc_18001A6AB
0x18001a61b  mov     qword ptr [rax+20h], 0
0x18001a623  mov     qword ptr [rax-38h], 0
0x18001a62b  lea     r9, [rax+20h]; unsigned __int16 **
0x18001a62f  mov     r8d, 8000h; unsigned int
0x18001a635  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18001a638  mov     rcx, rsi; struct IShellFolder2 *
0x18001a63b  call    ?GetDisplayName@@YAJPEAUIShellFolder2@@PEBU_ITEMID_CHILD@@KPEAPEAG@Z; GetDisplayName(IShellFolder2 *,_ITEMID_CHILD const *,ulong,ushort * *)
0x18001a640  mov     ebx, eax
0x18001a642  test    eax, eax
0x18001a644  js      short loc_18001A6A7
0x18001a646  mov     rcx, [rsp+58h+arg_18]; unsigned __int16 *
0x18001a64b  call    ?IsOnSeeAlsoList@@YAHPEBG@Z; IsOnSeeAlsoList(ushort const *)
0x18001a650  test    eax, eax
0x18001a652  jz      short loc_18001A69C
0x18001a654  lea     r9, [rsp+58h+pv]; unsigned __int16 **
0x18001a659  xor     r8d, r8d; unsigned int
0x18001a65c  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18001a65f  mov     rcx, rsi; struct IShellFolder2 *
0x18001a662  call    ?GetDisplayName@@YAJPEAUIShellFolder2@@PEBU_ITEMID_CHILD@@KPEAPEAG@Z; GetDisplayName(IShellFolder2 *,_ITEMID_CHILD const *,ulong,ushort * *)
0x18001a667  mov     ebx, eax
0x18001a669  test    eax, eax
0x18001a66b  js      short loc_18001A691
0x18001a66d  mov     rdi, [rsp+58h+arg_18]
0x18001a672  lea     r8, [rsp+58h+pv]
0x18001a677  lea     rdx, [rsp+58h+var_30]
0x18001a67c  mov     rcx, r14
0x18001a67f  call    ??$_Try_emplace@AEBQEAG$$V@?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAGPEAG@std@@PEAX@std@@_N@1@AEBQEAG@Z; std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>>::_Try_emplace<ushort * const &,>(ushort * const &)
0x18001a684  mov     rax, [rax]
0x18001a687  mov     [rax+28h], rdi
0x18001a68b  jmp     short loc_18001A6A7
0x18001a68d  mov     ebx, [rsp+58h+arg_0]
0x18001a691  mov     rcx, [rsp+58h+pv]; pv
0x18001a696  call    cs:__imp_CoTaskMemFree
0x18001a69c  mov     rcx, [rsp+58h+arg_18]; pv
0x18001a6a1  call    cs:__imp_CoTaskMemFree
0x18001a6a7  mov     eax, ebx
0x18001a6a9  jmp     short loc_18001A6B0
0x18001a6ab  mov     eax, 80004003h
0x18001a6b0  mov     rbx, [rsp+58h+arg_8]
0x18001a6b5  add     rsp, 40h
0x18001a6b9  pop     r14
0x18001a6bb  pop     rdi
0x18001a6bc  pop     rsi
0x18001a6bd  retn
```
