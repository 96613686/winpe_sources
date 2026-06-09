# CHNetConn::FinalRelease(void)

- ea: `0x18001a6e0`
- end: `0x18001a818`
- name: `?FinalRelease@CHNetConn@@QEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c880`
- `0x18000c8d4`
- `0x18000c928`
- `0x18000c97c`
- `0x18000ca38`
- `0x180018134`

## callees

- `0x18000a45c`
- `0x18001a6e0`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001a73f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a74e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a772`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a73f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a74e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a790`

## pseudocode

```c
__int64 __fastcall CHNetConn::FinalRelease(CHNetConn *this)
{
  __int64 v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  __int64 v5; // rcx
  OLECHAR *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (OLECHAR *)*((_QWORD *)this + 9);
  if ( v3 )
    SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 10);
  if ( v4 )
    SysFreeString(v4);
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = (OLECHAR *)*((_QWORD *)this + 15);
  if ( v6 )
    SysFreeString(v6);
  v7 = (void *)*((_QWORD *)this + 14);
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = (void *)*((_QWORD *)this + 13);
  if ( v8 )
    CoTaskMemFree(v8);
  v9 = *((_QWORD *)this + 16);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 17);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *((_QWORD *)this + 18);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a6e0  mov     [rsp+arg_0], rbx
0x18001a6e5  push    rdi
0x18001a6e6  sub     rsp, 20h
0x18001a6ea  mov     rbx, rcx
0x18001a6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6f4  lea     rdi, WPP_GLOBAL_Control
0x18001a6fb  cmp     rcx, rdi
0x18001a6fe  jz      short loc_18001A721
0x18001a700  test    byte ptr [rcx+1Ch], 8
0x18001a704  jz      short loc_18001A721
0x18001a706  cmp     byte ptr [rcx+19h], 6
0x18001a70a  jb      short loc_18001A721
0x18001a70c  mov     rcx, [rcx+10h]
0x18001a710  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001a717  mov     edx, 10h
0x18001a71c  call    WPP_SF_
0x18001a721  mov     rcx, [rbx+40h]
0x18001a725  test    rcx, rcx
0x18001a728  jz      short loc_18001A736
0x18001a72a  mov     rax, [rcx]
0x18001a72d  mov     rax, [rax+10h]
0x18001a731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a736  mov     rcx, [rbx+48h]; bstrString
0x18001a73a  test    rcx, rcx
0x18001a73d  jz      short loc_18001A745
0x18001a73f  call    cs:__imp_SysFreeString
0x18001a745  mov     rcx, [rbx+50h]; bstrString
0x18001a749  test    rcx, rcx
0x18001a74c  jz      short loc_18001A754
0x18001a74e  call    cs:__imp_SysFreeString
0x18001a754  mov     rcx, [rbx+58h]
0x18001a758  test    rcx, rcx
0x18001a75b  jz      short loc_18001A769
0x18001a75d  mov     rax, [rcx]
0x18001a760  mov     rax, [rax+10h]
0x18001a764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a769  mov     rcx, [rbx+78h]; bstrString
0x18001a76d  test    rcx, rcx
0x18001a770  jz      short loc_18001A778
0x18001a772  call    cs:__imp_SysFreeString
0x18001a778  mov     rcx, [rbx+70h]; pv
0x18001a77c  test    rcx, rcx
0x18001a77f  jz      short loc_18001A787
0x18001a781  call    cs:__imp_CoTaskMemFree
0x18001a787  mov     rcx, [rbx+68h]; pv
0x18001a78b  test    rcx, rcx
0x18001a78e  jz      short loc_18001A796
0x18001a790  call    cs:__imp_CoTaskMemFree
0x18001a796  mov     rcx, [rbx+80h]
0x18001a79d  test    rcx, rcx
0x18001a7a0  jz      short loc_18001A7AE
0x18001a7a2  mov     rax, [rcx]
0x18001a7a5  mov     rax, [rax+10h]
0x18001a7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ae  mov     rcx, [rbx+88h]
0x18001a7b5  test    rcx, rcx
0x18001a7b8  jz      short loc_18001A7C6
0x18001a7ba  mov     rax, [rcx]
0x18001a7bd  mov     rax, [rax+10h]
0x18001a7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7c6  mov     rcx, [rbx+90h]
0x18001a7cd  test    rcx, rcx
0x18001a7d0  jz      short loc_18001A7DE
0x18001a7d2  mov     rax, [rcx]
0x18001a7d5  mov     rax, [rax+10h]
0x18001a7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7e5  cmp     rcx, rdi
0x18001a7e8  jz      short loc_18001A80B
0x18001a7ea  test    byte ptr [rcx+1Ch], 8
0x18001a7ee  jz      short loc_18001A80B
0x18001a7f0  cmp     byte ptr [rcx+19h], 6
0x18001a7f4  jb      short loc_18001A80B
0x18001a7f6  mov     rcx, [rcx+10h]
0x18001a7fa  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001a801  mov     edx, 11h
0x18001a806  call    WPP_SF_
0x18001a80b  mov     rbx, [rsp+28h+arg_0]
0x18001a810  xor     eax, eax
0x18001a812  add     rsp, 20h
0x18001a816  pop     rdi
0x18001a817  retn
```
