# ZoneCheckUrlAction(IUnknown *,ulong,ushort const *,ulong)

- ea: `0x180023034`
- end: `0x18002313d`
- name: `?ZoneCheckUrlAction@@YAHPEAUIUnknown@@KPEBGK@Z`
- size: `265`
- prototype: `__int64 __fastcall(IUnknown *punk, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022fb0`

## callees

- `0x180022eb0`
- `0x180023034`
- `0x180023144`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180023067`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180023067`
- `SHLWAPI!__imp_ZoneCheckUrlW` at `0x1800230f6`
- `SHLWAPI!__imp_ZoneCheckUrlW` at `0x1800230f6`
- `SHLWAPI!__imp_ZoneCheckHost` at `0x18002307e`
- `SHLWAPI!__imp_ZoneCheckHost` at `0x18002307e`
- `OLEAUT32!__imp_SysFreeString` at `0x180023109`
- `OLEAUT32!__imp_SysFreeString` at `0x180023109`

## pseudocode

```c
_BOOL8 __fastcall ZoneCheckUrlAction(IUnknown *punk, __int64 a2, const unsigned __int16 *a3)
{
  BOOL v5; // edi
  unsigned int v6; // r8d
  unsigned int v7; // r9d
  int v8; // ebx
  int v9; // eax
  BOOL v10; // ecx
  void *ppvOut; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  void *v14; // [rsp+30h] [rbp-10h] BYREF

  ppvOut = 0;
  v5 = 1;
  if ( IUnknown_QueryService(
         punk,
         &IID_IInternetHostSecurityManager,
         &GUID_3af280b6_cb3f_11d0_891e_00c04fb6bfc4,
         &ppvOut) < 0
    || (v8 = ZoneCheckHost(ppvOut, 6147, 4),
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut),
        v5 = v8 == 0,
        !v8) )
  {
    v14 = 0;
    if ( !punk )
      return (BOOL)ProcessUrlAction(punk, a3, v6, v7);
    if ( (int)GetHTMLDoc2(punk, &v14) >= 0 )
    {
      bstrString = 0;
      if ( (*(int (__fastcall **)(void *, BSTR *))(*(_QWORD *)v14 + 320LL))(v14, &bstrString) >= 0 )
      {
        v9 = ZoneCheckUrlW(bstrString, 6147, 4);
        v10 = 0;
        if ( !v9 )
          v10 = v5;
        v5 = v10;
        SysFreeString(bstrString);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    if ( v5 )
      return (BOOL)ProcessUrlAction(punk, a3, v6, v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180023034  push    rbp
0x180023036  push    rbx
0x180023037  push    rsi
0x180023038  push    rdi
0x180023039  push    r14
0x18002303b  mov     rbp, rsp
0x18002303e  sub     rsp, 40h
0x180023042  mov     r14, r8
0x180023045  mov     [rbp+ppvOut], 0
0x18002304d  lea     r8, _GUID_3af280b6_cb3f_11d0_891e_00c04fb6bfc4; riid
0x180023054  mov     rsi, rcx
0x180023057  lea     r9, [rbp+ppvOut]; ppvOut
0x18002305b  mov     edi, 1
0x180023060  lea     rdx, IID_IInternetHostSecurityManager; guidService
0x180023067  call    cs:__imp_IUnknown_QueryService
0x18002306d  test    eax, eax
0x18002306f  js      short loc_1800230A6
0x180023071  mov     rcx, [rbp+ppvOut]
0x180023075  lea     r8d, [rdi+3]
0x180023079  mov     edx, 1803h
0x18002307e  call    cs:__imp_ZoneCheckHost
0x180023084  mov     rcx, [rbp+ppvOut]
0x180023088  mov     ebx, eax
0x18002308a  mov     rax, [rcx]
0x18002308d  mov     rax, [rax+10h]
0x180023091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023096  xor     edi, edi
0x180023098  test    ebx, ebx
0x18002309a  setz    dil
0x18002309e  test    ebx, ebx
0x1800230a0  jnz     loc_180023130
0x1800230a6  mov     [rbp+var_10], 0
0x1800230ae  test    rsi, rsi
0x1800230b1  jz      short loc_180023123
0x1800230b3  lea     rdx, [rbp+var_10]; ppvOut
0x1800230b7  mov     rcx, rsi; punk
0x1800230ba  call    GetHTMLDoc2
0x1800230bf  test    eax, eax
0x1800230c1  js      short loc_18002311F
0x1800230c3  mov     rcx, [rbp+var_10]
0x1800230c7  lea     rdx, [rbp+bstrString]
0x1800230cb  mov     [rbp+bstrString], 0
0x1800230d3  mov     rax, [rcx]
0x1800230d6  mov     rax, [rax+140h]
0x1800230dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230e2  test    eax, eax
0x1800230e4  js      short loc_18002310F
0x1800230e6  mov     rcx, [rbp+bstrString]
0x1800230ea  xor     r9d, r9d
0x1800230ed  mov     edx, 1803h
0x1800230f2  lea     r8d, [r9+4]
0x1800230f6  call    cs:__imp_ZoneCheckUrlW
0x1800230fc  xor     ecx, ecx
0x1800230fe  test    eax, eax
0x180023100  cmovz   ecx, edi
0x180023103  mov     edi, ecx
0x180023105  mov     rcx, [rbp+bstrString]; bstrString
0x180023109  call    cs:__imp_SysFreeString
0x18002310f  mov     rcx, [rbp+var_10]
0x180023113  mov     rax, [rcx]
0x180023116  mov     rax, [rax+10h]
0x18002311a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002311f  test    edi, edi
0x180023121  jz      short loc_180023130
0x180023123  mov     rdx, r14; unsigned __int16 *
0x180023126  mov     rcx, rsi; punkSite
0x180023129  call    ?ProcessUrlAction@@YAHPEAUIUnknown@@PEBGKK@Z; ProcessUrlAction(IUnknown *,ushort const *,ulong,ulong)
0x18002312e  mov     edi, eax
0x180023130  mov     eax, edi
0x180023132  add     rsp, 40h
0x180023136  pop     r14
0x180023138  pop     rdi
0x180023139  pop     rsi
0x18002313a  pop     rbx
0x18002313b  pop     rbp
0x18002313c  retn
```
