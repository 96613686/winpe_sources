# CComponentObj::HrInit(std::list<CBindingPathObj *,std::allocator<CBindingPathObj *>> *)

- ea: `0x18000a45c`
- end: `0x18000a560`
- name: `?HrInit@CComponentObj@@QEAAJPEAV?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009970`

## callees

- `0x18000a45c`
- `0x18001b348`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a4fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a4fb`
- `ole32!CoTaskMemFree` at `0x18000a51f`
- `ole32!CoTaskMemFree` at `0x18000a547`
- `ole32!CoTaskMemFree` at `0x18000a51f`
- `ole32!CoTaskMemFree` at `0x18000a547`

## pseudocode

```c
__int64 __fastcall CComponentObj::HrInit(__int64 *a1, _QWORD *a2)
{
  int v4; // edi
  _QWORD *v5; // rbx
  LPCWSTR lpString1; // [rsp+50h] [rbp+30h] BYREF
  __int64 v8; // [rsp+60h] [rbp+40h] BYREF
  LPCWSTR lpString2; // [rsp+68h] [rbp+48h] BYREF

  lpString2 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)*a1 + 48LL))(*a1, &lpString2);
  if ( v4 >= 0 )
  {
    v5 = (_QWORD *)*a2;
    while ( 1 )
    {
      v5 = (_QWORD *)*v5;
      if ( v5 == (_QWORD *)*a2 )
        break;
      v8 = 0;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v5[2] + 64LL))(*(_QWORD *)v5[2], &v8);
      if ( v4 >= 0 )
      {
        lpString1 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v8 + 48LL))(v8, &lpString1);
        if ( v4 >= 0 )
        {
          if ( !lstrcmpiW(lpString1, lpString2) )
          {
            std::list<CBindingPathObj *>::_Emplace<CBindingPathObj * const &>((__int64)(a1 + 1), a1[1], v5 + 2);
            *(_QWORD *)(v5[2] + 48LL) = a1;
          }
          CoTaskMemFree((LPVOID)lpString1);
        }
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    CoTaskMemFree((LPVOID)lpString2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a45c  mov     [rsp-28h+arg_8], rbx
0x18000a461  push    rbp
0x18000a462  push    rsi
0x18000a463  push    rdi
0x18000a464  push    r14
0x18000a466  push    r15
0x18000a468  mov     rbp, rsp
0x18000a46b  sub     rsp, 20h
0x18000a46f  mov     r15, rcx
0x18000a472  mov     [rbp+lpString2], 0
0x18000a47a  mov     rcx, [rcx]
0x18000a47d  mov     rsi, rdx
0x18000a480  lea     rdx, [rbp+lpString2]
0x18000a484  mov     rax, [rcx]
0x18000a487  mov     rax, [rax+30h]
0x18000a48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a490  mov     edi, eax
0x18000a492  test    eax, eax
0x18000a494  js      loc_18000A54D
0x18000a49a  mov     rbx, [rsi]
0x18000a49d  mov     rbx, [rbx]
0x18000a4a0  cmp     rbx, [rsi]
0x18000a4a3  jz      loc_18000A543
0x18000a4a9  mov     [rbp+arg_10], 0
0x18000a4b1  lea     r14, [rbx+10h]
0x18000a4b5  mov     rax, [r14]
0x18000a4b8  lea     rdx, [rbp+arg_10]
0x18000a4bc  mov     rcx, [rax]
0x18000a4bf  mov     rax, [rcx]
0x18000a4c2  mov     rax, [rax+40h]
0x18000a4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4cb  mov     edi, eax
0x18000a4cd  test    eax, eax
0x18000a4cf  js      short loc_18000A49D
0x18000a4d1  mov     rcx, [rbp+arg_10]
0x18000a4d5  lea     rdx, [rbp+lpString1]
0x18000a4d9  mov     [rbp+lpString1], 0
0x18000a4e1  mov     rax, [rcx]
0x18000a4e4  mov     rax, [rax+30h]
0x18000a4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ed  mov     edi, eax
0x18000a4ef  test    eax, eax
0x18000a4f1  js      short loc_18000A525
0x18000a4f3  mov     rdx, [rbp+lpString2]; lpString2
0x18000a4f7  mov     rcx, [rbp+lpString1]; lpString1
0x18000a4fb  call    cs:__imp_lstrcmpiW
0x18000a501  test    eax, eax
0x18000a503  jnz     short loc_18000A51B
0x18000a505  lea     rcx, [r15+8]
0x18000a509  mov     r8, r14
0x18000a50c  mov     rdx, [rcx]
0x18000a50f  call    ??$_Emplace@AEBQEAVCBindingPathObj@@@?$list@PEAVCBindingPathObj@@V?$allocator@PEAVCBindingPathObj@@@std@@@std@@QEAAPEAU?$_List_node@PEAVCBindingPathObj@@PEAX@1@QEAU21@AEBQEAVCBindingPathObj@@@Z; std::list<CBindingPathObj *>::_Emplace<CBindingPathObj * const &>(std::_List_node<CBindingPathObj *,void *> * const,CBindingPathObj * const &)
0x18000a514  mov     rax, [r14]
0x18000a517  mov     [rax+30h], r15
0x18000a51b  mov     rcx, [rbp+lpString1]; pv
0x18000a51f  call    cs:__imp_CoTaskMemFree
0x18000a525  mov     rcx, [rbp+arg_10]
0x18000a529  test    rcx, rcx
0x18000a52c  jz      loc_18000A49D
0x18000a532  mov     rax, [rcx]
0x18000a535  mov     rax, [rax+10h]
0x18000a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a53e  jmp     loc_18000A49D
0x18000a543  mov     rcx, [rbp+lpString2]; pv
0x18000a547  call    cs:__imp_CoTaskMemFree
0x18000a54d  mov     rbx, [rsp+20h+arg_8]
0x18000a552  mov     eax, edi
0x18000a554  add     rsp, 20h
0x18000a558  pop     r15
0x18000a55a  pop     r14
0x18000a55c  pop     rdi
0x18000a55d  pop     rsi
0x18000a55e  pop     rbp
0x18000a55f  retn
```
