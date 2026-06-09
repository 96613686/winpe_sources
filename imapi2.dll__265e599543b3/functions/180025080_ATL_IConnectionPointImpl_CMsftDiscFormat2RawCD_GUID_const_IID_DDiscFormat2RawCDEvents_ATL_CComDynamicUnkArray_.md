# ATL::IConnectionPointImpl<CMsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)

- ea: `0x180025080`
- end: `0x180025194`
- name: `?Advise@?$IConnectionPointImpl@VCMsftDiscFormat2RawCD@@$1?IID_DDiscFormat2RawCDEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180016e38`
- `0x180025080`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180025116`
- `KERNEL32!EnterCriticalSection` at `0x180025116`
- `KERNEL32!LeaveCriticalSection` at `0x180025140`
- `KERNEL32!LeaveCriticalSection` at `0x180025140`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscFormat2RawCD,&_GUID const IID_DDiscFormat2RawCDEvents,ATL::CComDynamicUnkArray>::Advise(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int128 *, struct IUnknown **),
        _DWORD *a3)
{
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdi
  int v10; // eax
  int v11; // ebx
  struct IUnknown *v13; // [rsp+20h] [rbp-38h] BYREF
  __int128 v14; // [rsp+28h] [rbp-30h] BYREF

  v13 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 && a3 )
  {
    v6 = *a1;
    v14 = 0;
    (*(void (__fastcall **)(__int64 *, __int128 *))(v6 + 24))(a1, &v14);
    v7 = (**a2)(a2, &v14, &v13);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( v7 == -2147467262 )
        v8 = -2147220990;
    }
    else
    {
      v9 = (__int64)(a1 + 11);
      if ( !a1 )
        v9 = 112;
      EnterCriticalSection((LPCRITICAL_SECTION)v9);
      v10 = ATL::CComDynamicUnkArray::Add((ATL::CComDynamicUnkArray *)(a1 + 1), v13);
      *a3 = v10;
      v11 = v10;
      v8 = v10 == 0 ? 0x80040201 : 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
      if ( v11 )
        return v8;
      ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
    }
    *a3 = 0;
    return v8;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180025080  mov     [rsp+arg_18], rbx
0x180025085  push    rsi
0x180025086  push    rdi
0x180025087  push    r14
0x180025089  sub     rsp, 40h
0x18002508d  mov     rax, cs:__security_cookie
0x180025094  xor     rax, rsp
0x180025097  mov     [rsp+58h+var_20], rax
0x18002509c  mov     [rsp+58h+var_38], 0
0x1800250a5  mov     r14, r8
0x1800250a8  mov     rdi, rdx
0x1800250ab  mov     rbx, rcx
0x1800250ae  test    r8, r8
0x1800250b1  jz      short loc_1800250BA
0x1800250b3  mov     dword ptr [r8], 0
0x1800250ba  test    rdi, rdi
0x1800250bd  jz      loc_180025174
0x1800250c3  test    r14, r14
0x1800250c6  jz      loc_180025174
0x1800250cc  mov     rax, [rcx]
0x1800250cf  lea     rdx, [rsp+58h+var_30]
0x1800250d4  xorps   xmm0, xmm0
0x1800250d7  movups  [rsp+58h+var_30], xmm0
0x1800250dc  mov     rax, [rax+18h]
0x1800250e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250e5  mov     rax, [rdi]
0x1800250e8  lea     r8, [rsp+58h+var_38]
0x1800250ed  lea     rdx, [rsp+58h+var_30]
0x1800250f2  mov     rcx, rdi
0x1800250f5  mov     rax, [rax]
0x1800250f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250fd  mov     esi, eax
0x1800250ff  test    eax, eax
0x180025101  js      short loc_18002515D
0x180025103  mov     eax, 70h ; 'p'
0x180025108  lea     rdi, [rbx+58h]
0x18002510c  test    rbx, rbx
0x18002510f  cmovz   rdi, rax
0x180025113  mov     rcx, rdi; lpCriticalSection
0x180025116  call    cs:__imp_EnterCriticalSection
0x18002511c  mov     rdx, [rsp+58h+var_38]; struct IUnknown *
0x180025121  lea     rcx, [rbx+8]; this
0x180025125  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x18002512a  mov     edx, eax
0x18002512c  mov     [r14], eax
0x18002512f  neg     edx
0x180025131  mov     rcx, rdi; lpCriticalSection
0x180025134  mov     ebx, eax
0x180025136  sbb     esi, esi
0x180025138  not     esi
0x18002513a  and     esi, 80040201h
0x180025140  call    cs:__imp_LeaveCriticalSection
0x180025146  test    ebx, ebx
0x180025148  jnz     short loc_180025170
0x18002514a  mov     rcx, [rsp+58h+var_38]
0x18002514f  mov     rax, [rcx]
0x180025152  mov     rax, [rax+10h]
0x180025156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002515b  jmp     short loc_180025169
0x18002515d  cmp     eax, 80004002h
0x180025162  jnz     short loc_180025169
0x180025164  mov     esi, 80040202h
0x180025169  mov     dword ptr [r14], 0
0x180025170  mov     eax, esi
0x180025172  jmp     short loc_180025179
0x180025174  mov     eax, 80004003h
0x180025179  mov     rcx, [rsp+58h+var_20]
0x18002517e  xor     rcx, rsp; StackCookie
0x180025181  call    __security_check_cookie
0x180025186  mov     rbx, [rsp+58h+arg_18]
0x18002518b  add     rsp, 40h
0x18002518f  pop     r14
0x180025191  pop     rdi
0x180025192  pop     rsi
0x180025193  retn
```
