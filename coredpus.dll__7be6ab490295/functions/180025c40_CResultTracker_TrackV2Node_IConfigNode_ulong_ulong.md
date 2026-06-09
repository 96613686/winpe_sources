# CResultTracker::TrackV2Node(IConfigNode *,ulong,ulong)

- ea: `0x180025c40`
- end: `0x180025cfc`
- name: `?TrackV2Node@CResultTracker@@UEAAJPEAUIConfigNode@@KK@Z`
- size: `188`
- prototype: `__int64 __fastcall(CResultTracker *__hidden this, struct IConfigNode *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180024308`
- `0x180025614`
- `0x180025c40`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CResultTracker::TrackV2Node(
        CResultTracker *this,
        struct IUnknown *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v7; // esi
  struct IUnknown *v8; // rcx
  __int64 v9; // rbx
  struct IUnknown *v11; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-20h]

  v7 = 0;
  v11 = 0;
  v12 = 0;
  if ( a2 )
  {
    ATL::AtlComPtrAssign(&v11, a2);
    v8 = v11;
    try
    {
      v12 = __PAIR64__(a4, a3);
      v9 = *((_QWORD *)this + 6);
      if ( v9 == *((_QWORD *)this + 7) )
      {
        std::vector<ResultNode>::_Emplace_reallocate<ResultNode const &>((char *)this + 40, *((_QWORD *)this + 6), &v11);
      }
      else
      {
        *(_QWORD *)v9 = v11;
        if ( v8 )
          ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(v8);
        *(_DWORD *)(v9 + 8) = a3;
        *(_DWORD *)(v9 + 12) = a4;
        *((_QWORD *)this + 6) += 16LL;
      }
    }
    catch ( std::bad_alloc )
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v11);
  return v7;
}

```

## disassembly

```asm
0x180025c40  mov     r11, rsp
0x180025c43  mov     [r11+8], rbx
0x180025c47  mov     [r11+18h], rsi
0x180025c4b  push    rdi
0x180025c4c  push    r14
0x180025c4e  push    r15
0x180025c50  sub     rsp, 30h
0x180025c54  mov     r14d, r9d
0x180025c57  mov     r15d, r8d
0x180025c5a  mov     rdi, rcx
0x180025c5d  xor     esi, esi
0x180025c5f  xor     ecx, ecx
0x180025c61  mov     [r11-28h], rcx
0x180025c65  xor     eax, eax
0x180025c67  mov     [r11-20h], rax
0x180025c6b  test    rdx, rdx
0x180025c6e  jnz     short loc_180025C77
0x180025c70  mov     esi, 80070057h
0x180025c75  jmp     short loc_180025CDB
0x180025c77  cmp     rcx, rdx
0x180025c7a  jz      short loc_180025C8B
0x180025c7c  lea     rcx, [rsp+48h+var_28]; struct IUnknown **
0x180025c81  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180025c86  mov     rcx, [rsp+48h+var_28]
0x180025c8b  mov     [rsp+48h+var_20], r15d
0x180025c90  mov     [rsp+48h+var_1C], r14d
0x180025c95  mov     rbx, [rdi+30h]
0x180025c99  cmp     rbx, [rdi+38h]
0x180025c9d  jz      short loc_180025CC3
0x180025c9f  mov     [rbx], rcx
0x180025ca2  test    rcx, rcx
0x180025ca5  jz      short loc_180025CB4
0x180025ca7  mov     rax, [rcx]
0x180025caa  mov     rax, [rax+8]
0x180025cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cb3  nop
0x180025cb4  mov     [rbx+8], r15d
0x180025cb8  mov     [rbx+0Ch], r14d
0x180025cbc  add     qword ptr [rdi+30h], 10h
0x180025cc1  jmp     short loc_180025CD5
0x180025cc3  lea     r8, [rsp+48h+var_28]
0x180025cc8  mov     rdx, rbx
0x180025ccb  lea     rcx, [rdi+28h]
0x180025ccf  call    ??$_Emplace_reallocate@AEBUResultNode@@@?$vector@UResultNode@@V?$allocator@UResultNode@@@std@@@std@@AEAAPEAUResultNode@@QEAU2@AEBU2@@Z; std::vector<ResultNode>::_Emplace_reallocate<ResultNode const &>(ResultNode * const,ResultNode const &)
0x180025cd4  nop
0x180025cd5  jmp     short loc_180025CDB
0x180025cd7  mov     esi, [rsp+48h+arg_8]
0x180025cdb  lea     rcx, [rsp+48h+var_28]
0x180025ce0  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180025ce5  mov     eax, esi
0x180025ce7  mov     rbx, [rsp+48h+arg_0]
0x180025cec  mov     rsi, [rsp+48h+arg_10]
0x180025cf1  add     rsp, 30h
0x180025cf5  pop     r15
0x180025cf7  pop     r14
0x180025cf9  pop     rdi
0x180025cfa  retn
```
