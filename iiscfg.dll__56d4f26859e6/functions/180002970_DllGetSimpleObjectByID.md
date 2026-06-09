# DllGetSimpleObjectByID

- ea: `0x180002970`
- end: `0x180002adb`
- name: `DllGetSimpleObjectByID`
- size: `363`
- prototype: `__int64 __fastcall(int, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180002af0`
- `0x180002d6c`
- `0x180003370`
- `0x180003918`
- `0x180003e04`
- `0x180003ed0`

## callees

- `0x1800020b8`
- `0x18000225c`
- `0x180002314`
- `0x1800023d8`
- `0x1800024b0`
- `0x180002740`
- `0x180002970`
- `0x1800054d8`
- `0x1800141dc`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800029ea`
- `ole32!CoTaskMemAlloc` at `0x180002a39`
- `ole32!CoTaskMemAlloc` at `0x1800029ea`
- `ole32!CoTaskMemAlloc` at `0x180002a39`

## pseudocode

```c
__int64 __fastcall DllGetSimpleObjectByID(int a1, const struct _GUID *a2, void **a3)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  TMetabaseDifferencing *v13; // rax
  TMetabaseDifferencing *v14; // rax
  TMetabaseDifferencing *v15; // rsi
  unsigned int v16; // edx
  int v17; // ebx
  TMetabase_XMLtable *v18; // rax
  TMetabase_XMLtable *v19; // rax
  TMetabase_XMLtable *v20; // rsi

  if ( a3 && !*a3 )
  {
    v5 = a1 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = v6 - 4;
        if ( v7 )
        {
          v8 = v7 - 4;
          if ( v8 )
          {
            v9 = v8 - 4;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                if ( v10 != 2 )
                  return 2147746065LL;
                return (unsigned int)GetErrorTableInterceptor(a2, a3);
              }
              v13 = (TMetabaseDifferencing *)CoTaskMemAlloc(0x20u);
              if ( v13 )
              {
                v14 = TMetabaseDifferencing::TMetabaseDifferencing(v13);
                v15 = v14;
                if ( v14 )
                {
                  v17 = (**(__int64 (__fastcall ***)(TMetabaseDifferencing *, const struct _GUID *, void **))v14)(
                          v14,
                          a2,
                          a3);
                  if ( v17 < 0 )
                    TMetabaseDifferencing::`scalar deleting destructor'(v15, v16);
                  return (unsigned int)v17;
                }
              }
            }
            else
            {
              v18 = (TMetabase_XMLtable *)CoTaskMemAlloc(0x8F0u);
              if ( v18 )
              {
                v19 = TMetabase_XMLtable::TMetabase_XMLtable(v18);
                v20 = v19;
                if ( v19 )
                {
                  v17 = (**(__int64 (__fastcall ***)(TMetabase_XMLtable *, const struct _GUID *, void **))v19)(
                          v19,
                          a2,
                          a3);
                  if ( v17 < 0 )
                    (*(void (__fastcall **)(TMetabase_XMLtable *, __int64))(*(_QWORD *)v20 + 136LL))(v20, 1);
                  return (unsigned int)v17;
                }
              }
            }
            return (unsigned int)-2147024882;
          }
          return (unsigned int)GetFixedPackedInterceptor(a2, a3);
        }
        else
        {
          return (unsigned int)GetMemoryTableInterceptor(a2, a3);
        }
      }
      else
      {
        return (unsigned int)GetFixedTableInterceptor(a2, a3);
      }
    }
    else
    {
      return (unsigned int)ReallyGetSimpleTableDispenser(a2, a3);
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180002970  mov     [rsp+arg_0], rbx
0x180002975  mov     [rsp+arg_8], rsi
0x18000297a  push    rdi
0x18000297b  sub     rsp, 20h
0x18000297f  mov     rbx, r8
0x180002982  mov     rdi, rdx
0x180002985  test    r8, r8
0x180002988  jz      loc_180002AC6
0x18000298e  cmp     qword ptr [r8], 0
0x180002992  jnz     loc_180002AC6
0x180002998  sub     ecx, 1
0x18000299b  jz      loc_180002AB5
0x1800029a1  sub     ecx, 1
0x1800029a4  jz      loc_180002AA8
0x1800029aa  sub     ecx, 4
0x1800029ad  jz      loc_180002A9B
0x1800029b3  sub     ecx, 4
0x1800029b6  jz      loc_180002A8E
0x1800029bc  sub     ecx, 4
0x1800029bf  jz      short loc_180002A34
0x1800029c1  sub     ecx, 1
0x1800029c4  jz      short loc_1800029E5
0x1800029c6  cmp     ecx, 2
0x1800029c9  jz      short loc_1800029D5
0x1800029cb  mov     eax, 80040111h
0x1800029d0  jmp     loc_180002ACB
0x1800029d5  mov     rdx, rbx; void **
0x1800029d8  mov     rcx, rdi; struct _GUID *
0x1800029db  call    ?GetErrorTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z; GetErrorTableInterceptor(_GUID const &,void * *)
0x1800029e0  jmp     loc_180002AC0
0x1800029e5  mov     ecx, 20h ; ' '; cb
0x1800029ea  call    cs:__imp_CoTaskMemAlloc
0x1800029f0  test    rax, rax
0x1800029f3  jz      loc_180002A87
0x1800029f9  mov     rcx, rax; this
0x1800029fc  call    ??0TMetabaseDifferencing@@QEAA@XZ; TMetabaseDifferencing::TMetabaseDifferencing(void)
0x180002a01  mov     rsi, rax
0x180002a04  test    rax, rax
0x180002a07  jz      short loc_180002A87
0x180002a09  mov     rcx, [rax]
0x180002a0c  mov     r8, rbx
0x180002a0f  mov     rdx, rdi
0x180002a12  mov     rax, [rcx]
0x180002a15  mov     rcx, rsi
0x180002a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1d  mov     ebx, eax
0x180002a1f  test    eax, eax
0x180002a21  jns     loc_180002AC2
0x180002a27  mov     rcx, rsi; this
0x180002a2a  call    ??_GTMetabaseDifferencing@@QEAAPEAXI@Z; TMetabaseDifferencing::`scalar deleting destructor'(uint)
0x180002a2f  jmp     loc_180002AC2
0x180002a34  mov     ecx, 8F0h; cb
0x180002a39  call    cs:__imp_CoTaskMemAlloc
0x180002a3f  test    rax, rax
0x180002a42  jz      short loc_180002A87
0x180002a44  mov     rcx, rax; this
0x180002a47  call    ??0TMetabase_XMLtable@@QEAA@XZ; TMetabase_XMLtable::TMetabase_XMLtable(void)
0x180002a4c  mov     rsi, rax
0x180002a4f  test    rax, rax
0x180002a52  jz      short loc_180002A87
0x180002a54  mov     rcx, [rax]
0x180002a57  mov     r8, rbx
0x180002a5a  mov     rdx, rdi
0x180002a5d  mov     rax, [rcx]
0x180002a60  mov     rcx, rsi
0x180002a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a68  mov     ebx, eax
0x180002a6a  test    eax, eax
0x180002a6c  jns     short loc_180002AC2
0x180002a6e  mov     rax, [rsi]
0x180002a71  mov     edx, 1
0x180002a76  mov     rcx, rsi
0x180002a79  mov     rax, [rax+88h]
0x180002a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a85  jmp     short loc_180002AC2
0x180002a87  mov     ebx, 8007000Eh
0x180002a8c  jmp     short loc_180002AC2
0x180002a8e  mov     rdx, rbx; void **
0x180002a91  mov     rcx, rdi; struct _GUID *
0x180002a94  call    ?GetFixedPackedInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z; GetFixedPackedInterceptor(_GUID const &,void * *)
0x180002a99  jmp     short loc_180002AC0
0x180002a9b  mov     rdx, rbx; void **
0x180002a9e  mov     rcx, rdi; struct _GUID *
0x180002aa1  call    ?GetMemoryTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z; GetMemoryTableInterceptor(_GUID const &,void * *)
0x180002aa6  jmp     short loc_180002AC0
0x180002aa8  mov     rdx, rbx; void **
0x180002aab  mov     rcx, rdi; struct _GUID *
0x180002aae  call    ?GetFixedTableInterceptor@@YAJAEBU_GUID@@PEAPEAX@Z; GetFixedTableInterceptor(_GUID const &,void * *)
0x180002ab3  jmp     short loc_180002AC0
0x180002ab5  mov     rdx, rbx; void **
0x180002ab8  mov     rcx, rdi; struct _GUID *
0x180002abb  call    ?ReallyGetSimpleTableDispenser@@YAJAEBU_GUID@@PEAPEAX@Z; ReallyGetSimpleTableDispenser(_GUID const &,void * *)
0x180002ac0  mov     ebx, eax
0x180002ac2  mov     eax, ebx
0x180002ac4  jmp     short loc_180002ACB
0x180002ac6  mov     eax, 80070057h
0x180002acb  mov     rbx, [rsp+28h+arg_0]
0x180002ad0  mov     rsi, [rsp+28h+arg_8]
0x180002ad5  add     rsp, 20h
0x180002ad9  pop     rdi
0x180002ada  retn
```
