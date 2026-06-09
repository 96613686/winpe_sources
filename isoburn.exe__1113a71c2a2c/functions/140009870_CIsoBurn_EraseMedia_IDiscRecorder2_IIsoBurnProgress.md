# CIsoBurn::_EraseMedia(IDiscRecorder2 *,IIsoBurnProgress *)

- ea: `0x140009870`
- end: `0x140009a14`
- name: `?_EraseMedia@CIsoBurn@@CAJPEAUIDiscRecorder2@@PEAUIIsoBurnProgress@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(struct IDiscRecorder2 *, struct IIsoBurnProgress *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009e64`

## callees

- `0x140004948`
- `0x140004bb0`
- `0x140009870`
- `0x140010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000994f`
- `OLEAUT32!__imp_SysAllocString` at `0x14000994f`
- `OLEAUT32!__imp_SysFreeString` at `0x140009972`
- `OLEAUT32!__imp_SysFreeString` at `0x140009972`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400098b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400098b5`

## pseudocode

```c
__int64 __fastcall CIsoBurn::_EraseMedia(struct IDiscRecorder2 *a1, struct IIsoBurnProgress *a2)
{
  HRESULT Instance; // ebx
  int v5; // eax
  struct IIsoBurnProgress **v6; // rdi
  struct IUnknown *v7; // rbp
  _QWORD *v8; // rbx
  OLECHAR *v9; // rbx
  struct IUnknown *v11; // [rsp+60h] [rbp+18h] BYREF
  struct IIsoBurnProgress **v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v11 = 0;
  Instance = CoCreateInstance(
               &CLSID_MsftDiscFormat2Erase,
               0,
               0x17u,
               &GUID_27354156_8f64_5b0f_8f00_5d77afbe261e,
               (LPVOID *)&v11);
  if ( Instance >= 0 )
  {
    v5 = ATL::CComObject<CEraseEvent>::CreateInstance(&v12);
    v6 = v12;
    Instance = v5;
    if ( v5 >= 0 )
    {
      (*((void (__fastcall **)(struct IIsoBurnProgress **))*v12 + 1))(v12);
      v7 = v11;
      v8 = v6 + 14;
      if ( v6[14] != a2 && v6 != (struct IIsoBurnProgress **)-112LL )
      {
        if ( a2 )
          (*(void (__fastcall **)(struct IIsoBurnProgress *))(*(_QWORD *)a2 + 8LL))(a2);
        if ( *v8 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
        *v8 = a2;
      }
      Instance = ATL::_IDispEvent::DispEventAdvise((ATL::_IDispEvent *)(v6 + 1), v7, &IID_DDiscFormat2EraseEvents);
      if ( Instance >= 0 )
      {
        v9 = SysAllocString(L"ISOBURN");
        ((void (__fastcall *)(struct IUnknown *, OLECHAR *))v11->lpVtbl[5].Release)(v11, v9);
        SysFreeString(v9);
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IDiscRecorder2 *))v11->lpVtbl[4].QueryInterface)(
                     v11,
                     a1);
        if ( Instance >= 0 )
        {
          (*(void (__fastcall **)(struct IIsoBurnProgress *, __int64))(*(_QWORD *)a2 + 24LL))(a2, 1);
          Instance = ((__int64 (__fastcall *)(struct IUnknown *))v11->lpVtbl[6].AddRef)(v11);
          if ( Instance >= 0 )
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v11->lpVtbl[4].QueryInterface)(v11, 0);
        }
      }
    }
    if ( v6 )
      (*((void (__fastcall **)(struct IIsoBurnProgress **))*v6 + 2))(v6);
  }
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140009870  mov     r11, rsp
0x140009873  mov     [r11+8], rbx
0x140009877  mov     [r11+10h], rbp
0x14000987b  push    rsi
0x14000987c  push    rdi
0x14000987d  push    r14
0x14000987f  sub     rsp, 30h
0x140009883  mov     rsi, rdx
0x140009886  mov     qword ptr [r11+20h], 0
0x14000988e  xor     edx, edx; pUnkOuter
0x140009890  mov     qword ptr [r11+18h], 0
0x140009898  mov     r14, rcx
0x14000989b  lea     rax, [r11+18h]
0x14000989f  lea     r9, _GUID_27354156_8f64_5b0f_8f00_5d77afbe261e; riid
0x1400098a6  mov     [r11-28h], rax
0x1400098aa  lea     rcx, CLSID_MsftDiscFormat2Erase; rclsid
0x1400098b1  lea     r8d, [rdx+17h]; dwClsContext
0x1400098b5  call    cs:__imp_CoCreateInstance
0x1400098bb  mov     ebx, eax
0x1400098bd  test    eax, eax
0x1400098bf  js      loc_1400099E9
0x1400098c5  lea     rcx, [rsp+48h+arg_18]
0x1400098ca  call    ?CreateInstance@?$CComObject@VCEraseEvent@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEraseEvent>::CreateInstance(ATL::CComObject<CEraseEvent> * *)
0x1400098cf  mov     rdi, [rsp+48h+arg_18]
0x1400098d4  mov     ebx, eax
0x1400098d6  test    eax, eax
0x1400098d8  js      loc_1400099D5
0x1400098de  mov     rax, [rdi]
0x1400098e1  mov     rcx, rdi
0x1400098e4  mov     rax, [rax+8]
0x1400098e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098ed  mov     rbp, [rsp+48h+arg_10]
0x1400098f2  lea     rbx, [rdi+70h]
0x1400098f6  cmp     [rbx], rsi
0x1400098f9  jz      short loc_14000992B
0x1400098fb  test    rbx, rbx
0x1400098fe  jz      short loc_14000992B
0x140009900  test    rsi, rsi
0x140009903  jz      short loc_140009914
0x140009905  mov     rax, [rsi]
0x140009908  mov     rcx, rsi
0x14000990b  mov     rax, [rax+8]
0x14000990f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009914  mov     rcx, [rbx]
0x140009917  test    rcx, rcx
0x14000991a  jz      short loc_140009928
0x14000991c  mov     rax, [rcx]
0x14000991f  mov     rax, [rax+10h]
0x140009923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009928  mov     [rbx], rsi
0x14000992b  lea     rcx, [rdi+8]; this
0x14000992f  mov     rdx, rbp; struct IUnknown *
0x140009932  lea     r8, IID_DDiscFormat2EraseEvents; struct _GUID *
0x140009939  call    ?DispEventAdvise@_IDispEvent@ATL@@QEAAJPEAUIUnknown@@PEBU_GUID@@@Z; ATL::_IDispEvent::DispEventAdvise(IUnknown *,_GUID const *)
0x14000993e  mov     ebx, eax
0x140009940  test    eax, eax
0x140009942  js      loc_1400099D5
0x140009948  lea     rcx, psz; "ISOBURN"
0x14000994f  call    cs:__imp_SysAllocString
0x140009955  mov     rcx, [rsp+48h+arg_10]
0x14000995a  mov     rbx, rax
0x14000995d  mov     rdx, [rcx]
0x140009960  mov     rax, [rdx+88h]
0x140009967  mov     rdx, rbx
0x14000996a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000996f  mov     rcx, rbx; bstrString
0x140009972  call    cs:__imp_SysFreeString
0x140009978  mov     rcx, [rsp+48h+arg_10]
0x14000997d  mov     rdx, r14
0x140009980  mov     rax, [rcx]
0x140009983  mov     rax, [rax+60h]
0x140009987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000998c  mov     ebx, eax
0x14000998e  test    eax, eax
0x140009990  js      short loc_1400099D5
0x140009992  mov     rax, [rsi]
0x140009995  mov     edx, 1
0x14000999a  mov     rcx, rsi
0x14000999d  mov     rax, [rax+18h]
0x1400099a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099a6  mov     rcx, [rsp+48h+arg_10]
0x1400099ab  mov     rax, [rcx]
0x1400099ae  mov     rax, [rax+98h]
0x1400099b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099ba  mov     ebx, eax
0x1400099bc  test    eax, eax
0x1400099be  js      short loc_1400099D5
0x1400099c0  mov     rcx, [rsp+48h+arg_10]
0x1400099c5  xor     edx, edx
0x1400099c7  mov     rax, [rcx]
0x1400099ca  mov     rax, [rax+60h]
0x1400099ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099d3  mov     ebx, eax
0x1400099d5  test    rdi, rdi
0x1400099d8  jz      short loc_1400099E9
0x1400099da  mov     rax, [rdi]
0x1400099dd  mov     rcx, rdi
0x1400099e0  mov     rax, [rax+10h]
0x1400099e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099e9  mov     rcx, [rsp+48h+arg_10]
0x1400099ee  test    rcx, rcx
0x1400099f1  jz      short loc_1400099FF
0x1400099f3  mov     rax, [rcx]
0x1400099f6  mov     rax, [rax+10h]
0x1400099fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099ff  mov     rbp, [rsp+48h+arg_8]
0x140009a04  mov     eax, ebx
0x140009a06  mov     rbx, [rsp+48h+arg_0]
0x140009a0b  add     rsp, 30h
0x140009a0f  pop     r14
0x140009a11  pop     rdi
0x140009a12  pop     rsi
0x140009a13  retn
```
