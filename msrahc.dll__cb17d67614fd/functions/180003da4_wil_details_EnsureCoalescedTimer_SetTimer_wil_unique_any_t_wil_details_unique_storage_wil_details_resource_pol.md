# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180003da4`
- end: `0x180003ddf`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005738`
- `0x180005b0c`

## callees

- `0x180003da4`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180003dd0`
- `KERNEL32!SetThreadpoolTimer` at `0x180003dd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x180003da4  push    rbx
0x180003da6  sub     rsp, 20h
0x180003daa  mov     rcx, [rcx]; pti
0x180003dad  mov     rbx, rdx
0x180003db0  test    rcx, rcx
0x180003db3  jz      short loc_180003DD9
0x180003db5  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x180003dbc  shr     r8d, 2
0x180003dc0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180003dc5  mov     r9d, r8d; msWindowLength
0x180003dc8  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180003dcd  xor     r8d, r8d; msPeriod
0x180003dd0  call    cs:__imp_SetThreadpoolTimer
0x180003dd6  mov     byte ptr [rbx], 1
0x180003dd9  add     rsp, 20h
0x180003ddd  pop     rbx
0x180003dde  retn
```
