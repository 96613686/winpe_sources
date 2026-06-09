# IMSMQQueue4::ReceiveByLookupIdAllowPeek(_variant_t const &,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x14000d5ac`
- end: `0x14000d641`
- name: `?ReceiveByLookupIdAllowPeek@IMSMQQueue4@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIMSMQMessage4@@$1?_GUID_eba96b23_2168_11d3_898c_00e02c074f6b@@3U__s_GUID@@B@@@@AEBV_variant_t@@PEAUtagVARIANT@@111@Z`
- size: `149`
- prototype: `_QWORD *(struct IUnknown *, _QWORD *, __int128 *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d648`

## callees

- `0x14000d5ac`
- `0x14000ec38`
- `0x140020010`

## pseudocode

```c
_QWORD *IMSMQQueue4::ReceiveByLookupIdAllowPeek(struct IUnknown *a1, _QWORD *a2, __int128 *a3, ...)
{
  __int128 v4; // xmm0
  __int64 v6; // xmm1_8
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  int v8; // eax
  __int128 v10; // [rsp+50h] [rbp-28h] BYREF
  __int64 v11; // [rsp+60h] [rbp-18h]
  __int64 v12; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  va_list va1; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  v4 = *a3;
  v6 = *((_QWORD *)a3 + 2);
  QueryInterface = a1->lpVtbl[13].QueryInterface;
  v12 = 0;
  v10 = v4;
  v11 = v6;
  v8 = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *, __int64 *, __int64 *, __int64 *, __int64 *, __int64 *))QueryInterface)(
         a1,
         &v10,
         vtMissing,
         vtMissing,
         vtMissing,
         vtMissing,
         (__int64 *)va);
  if ( v8 < 0 )
    _com_issue_errorex(v8, a1, &GUID_eba96b20_2168_11d3_898c_00e02c074f6b);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x14000d5ac  mov     r11, rsp
0x14000d5af  mov     [r11+8], rbx
0x14000d5b3  mov     [r11+20h], r9
0x14000d5b7  push    rdi
0x14000d5b8  sub     rsp, 70h
0x14000d5bc  mov     rax, [rcx]
0x14000d5bf  mov     rdi, rcx
0x14000d5c2  movups  xmm0, xmmword ptr [r8]
0x14000d5c6  lea     rcx, [r11+20h]
0x14000d5ca  mov     rbx, rdx
0x14000d5cd  movsd   xmm1, qword ptr [r8+10h]
0x14000d5d3  lea     rdx, [r11-28h]
0x14000d5d7  mov     rax, [rax+138h]
0x14000d5de  lea     r8, ?vtMissing@@3V_variant_t@@A; _variant_t vtMissing
0x14000d5e5  mov     [r11-48h], rcx
0x14000d5e9  mov     r9, r8
0x14000d5ec  mov     [r11-50h], r8
0x14000d5f0  mov     rcx, rdi
0x14000d5f3  mov     qword ptr [r11+20h], 0
0x14000d5fb  movaps  [rsp+78h+var_28], xmm0
0x14000d600  movsd   [rsp+78h+var_18], xmm1
0x14000d606  mov     [r11-58h], r8
0x14000d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d60f  test    eax, eax
0x14000d611  jns     short loc_14000D625
0x14000d613  lea     r8, _GUID_eba96b20_2168_11d3_898c_00e02c074f6b; struct _GUID *
0x14000d61a  mov     rdx, rdi; struct IUnknown *
0x14000d61d  mov     ecx, eax; int
0x14000d61f  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000d625  mov     rax, [rsp+78h+arg_18]
0x14000d62d  mov     [rbx], rax
0x14000d630  mov     rax, rbx
0x14000d633  mov     rbx, [rsp+78h+arg_0]
0x14000d63b  add     rsp, 70h
0x14000d63f  pop     rdi
0x14000d640  retn
```
