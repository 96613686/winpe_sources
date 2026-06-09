# ATL::IConnectionPointImpl<CMsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)

- ea: `0x1800280c0`
- end: `0x1800281d4`
- name: `?Advise@?$IConnectionPointImpl@VCMsftDiscMaster2@@$1?IID_DDiscMaster2Events@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180016e38`
- `0x1800280c0`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180028156`
- `KERNEL32!EnterCriticalSection` at `0x180028156`
- `KERNEL32!LeaveCriticalSection` at `0x180028180`
- `KERNEL32!LeaveCriticalSection` at `0x180028180`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CMsftDiscMaster2,&_GUID const IID_DDiscMaster2Events,ATL::CComDynamicUnkArray>::Advise(
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
      v9 = (__int64)(a1 + 5);
      if ( !a1 )
        v9 = 64;
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
0x1800280c0  mov     [rsp+arg_18], rbx
0x1800280c5  push    rsi
0x1800280c6  push    rdi
0x1800280c7  push    r14
0x1800280c9  sub     rsp, 40h
0x1800280cd  mov     rax, cs:__security_cookie
0x1800280d4  xor     rax, rsp
0x1800280d7  mov     [rsp+58h+var_20], rax
0x1800280dc  mov     [rsp+58h+var_38], 0
0x1800280e5  mov     r14, r8
0x1800280e8  mov     rdi, rdx
0x1800280eb  mov     rbx, rcx
0x1800280ee  test    r8, r8
0x1800280f1  jz      short loc_1800280FA
0x1800280f3  mov     dword ptr [r8], 0
0x1800280fa  test    rdi, rdi
0x1800280fd  jz      loc_1800281B4
0x180028103  test    r14, r14
0x180028106  jz      loc_1800281B4
0x18002810c  mov     rax, [rcx]
0x18002810f  lea     rdx, [rsp+58h+var_30]
0x180028114  xorps   xmm0, xmm0
0x180028117  movups  [rsp+58h+var_30], xmm0
0x18002811c  mov     rax, [rax+18h]
0x180028120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028125  mov     rax, [rdi]
0x180028128  lea     r8, [rsp+58h+var_38]
0x18002812d  lea     rdx, [rsp+58h+var_30]
0x180028132  mov     rcx, rdi
0x180028135  mov     rax, [rax]
0x180028138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002813d  mov     esi, eax
0x18002813f  test    eax, eax
0x180028141  js      short loc_18002819D
0x180028143  mov     eax, 40h ; '@'
0x180028148  lea     rdi, [rbx+28h]
0x18002814c  test    rbx, rbx
0x18002814f  cmovz   rdi, rax
0x180028153  mov     rcx, rdi; lpCriticalSection
0x180028156  call    cs:__imp_EnterCriticalSection
0x18002815c  mov     rdx, [rsp+58h+var_38]; struct IUnknown *
0x180028161  lea     rcx, [rbx+8]; this
0x180028165  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x18002816a  mov     edx, eax
0x18002816c  mov     [r14], eax
0x18002816f  neg     edx
0x180028171  mov     rcx, rdi; lpCriticalSection
0x180028174  mov     ebx, eax
0x180028176  sbb     esi, esi
0x180028178  not     esi
0x18002817a  and     esi, 80040201h
0x180028180  call    cs:__imp_LeaveCriticalSection
0x180028186  test    ebx, ebx
0x180028188  jnz     short loc_1800281B0
0x18002818a  mov     rcx, [rsp+58h+var_38]
0x18002818f  mov     rax, [rcx]
0x180028192  mov     rax, [rax+10h]
0x180028196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002819b  jmp     short loc_1800281A9
0x18002819d  cmp     eax, 80004002h
0x1800281a2  jnz     short loc_1800281A9
0x1800281a4  mov     esi, 80040202h
0x1800281a9  mov     dword ptr [r14], 0
0x1800281b0  mov     eax, esi
0x1800281b2  jmp     short loc_1800281B9
0x1800281b4  mov     eax, 80004003h
0x1800281b9  mov     rcx, [rsp+58h+var_20]
0x1800281be  xor     rcx, rsp; StackCookie
0x1800281c1  call    __security_check_cookie
0x1800281c6  mov     rbx, [rsp+58h+arg_18]
0x1800281cb  add     rsp, 40h
0x1800281cf  pop     r14
0x1800281d1  pop     rdi
0x1800281d2  pop     rsi
0x1800281d3  retn
```
