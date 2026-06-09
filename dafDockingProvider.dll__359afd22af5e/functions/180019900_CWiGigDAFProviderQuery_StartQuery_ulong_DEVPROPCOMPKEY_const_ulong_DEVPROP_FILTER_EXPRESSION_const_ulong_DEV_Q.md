# CWiGigDAFProviderQuery::StartQuery(ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ushort const *,IAepQueryCallback *,_DEV_QUERY_FLAGS)

- ea: `0x180019900`
- end: `0x180019a3a`
- name: `?StartQuery@CWiGigDAFProviderQuery@@UEAAJKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@PEBGPEAUIAepQueryCallback@@W4_DEV_QUERY_FLAGS@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, __int64, int, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001ef4`
- `0x18000c308`
- `0x180012568`
- `0x180016f0c`
- `0x180019900`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderQuery::StartQuery(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10)
{
  RTL_SRWLOCK *v12; // rbp
  _QWORD *v13; // rax
  _QWORD *v14; // rdi

  if ( !a3 && a2 || !a5 && a4 || !a7 && a6 || !a9 )
    return 2147942487LL;
  if ( *(_QWORD *)(a1 + 32) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids, a1);
    }
    return 2147943647LL;
  }
  else
  {
    *(_DWORD *)(a1 + 56) = a10;
    *(_DWORD *)(a1 + 12) = 0;
    *(_QWORD *)(a1 + 32) = a9;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
    DockCache::MarkAllStale(*(LPCRITICAL_SECTION *)(a1 + 48));
    v12 = *(RTL_SRWLOCK **)(a1 + 40);
    v13 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( v13 )
    {
      *v13 = &QueryWork::`vftable';
      v13[1] = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v14[2] = a9;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a9 + 8LL))(a9);
      v14[3] = 0;
      *((_DWORD *)v14 + 8) = 0;
    }
    else
    {
      v14 = 0;
    }
    return DockingProviders::SubmitWork(v12, (struct Work *)v14);
  }
}

```

## disassembly

```asm
0x180019900  push    rbx
0x180019902  push    rbp
0x180019903  push    rsi
0x180019904  push    rdi
0x180019905  sub     rsp, 28h
0x180019909  mov     rbx, rcx
0x18001990c  test    r8, r8
0x18001990f  jnz     short loc_180019915
0x180019911  test    edx, edx
0x180019913  jnz     short loc_180019941
0x180019915  cmp     [rsp+48h+arg_20], 0
0x18001991b  jnz     short loc_180019922
0x18001991d  test    r9d, r9d
0x180019920  jnz     short loc_180019941
0x180019922  cmp     [rsp+48h+arg_30], 0
0x18001992b  jnz     short loc_180019934
0x18001992d  cmp     [rsp+48h+arg_28], 0
0x180019932  jnz     short loc_180019941
0x180019934  mov     rsi, [rsp+48h+arg_40]
0x18001993c  test    rsi, rsi
0x18001993f  jnz     short loc_18001994B
0x180019941  mov     eax, 80070057h
0x180019946  jmp     loc_180019A31
0x18001994b  cmp     qword ptr [rcx+20h], 0
0x180019950  jz      short loc_180019993
0x180019952  lea     rax, WPP_GLOBAL_Control
0x180019959  mov     rcx, cs:WPP_GLOBAL_Control
0x180019960  cmp     rcx, rax
0x180019963  jz      short loc_180019989
0x180019965  cmp     byte ptr [rcx+19h], 1
0x180019969  jb      short loc_180019989
0x18001996b  test    byte ptr [rcx+1Ch], 1
0x18001996f  jz      short loc_180019989
0x180019971  mov     edx, 2Ch ; ','
0x180019976  mov     r9, rbx
0x180019979  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x180019980  mov     rcx, [rcx+10h]
0x180019984  call    WPP_SF_q
0x180019989  mov     eax, 800704DFh
0x18001998e  jmp     loc_180019A31
0x180019993  mov     eax, [rsp+48h+arg_48]
0x18001999a  mov     [rcx+38h], eax
0x18001999d  mov     dword ptr [rcx+0Ch], 0
0x1800199a4  mov     [rcx+20h], rsi
0x1800199a8  mov     rax, [rsi]
0x1800199ab  mov     rcx, rsi
0x1800199ae  mov     rax, [rax+8]
0x1800199b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199b7  mov     rcx, [rbx+30h]; lpCriticalSection
0x1800199bb  call    ?MarkAllStale@DockCache@@QEAAXXZ; DockCache::MarkAllStale(void)
0x1800199c0  mov     rbp, [rbx+28h]
0x1800199c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800199cb  mov     ecx, 28h ; '('; unsigned __int64
0x1800199d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800199d5  mov     rdi, rax
0x1800199d8  mov     [rsp+48h+arg_10], rax
0x1800199dd  test    rax, rax
0x1800199e0  jz      short loc_180019A24
0x1800199e2  lea     rax, ??_7QueryWork@@6B@; const QueryWork::`vftable'
0x1800199e9  mov     [rdi], rax
0x1800199ec  mov     [rdi+8], rbx
0x1800199f0  mov     rax, [rbx]
0x1800199f3  mov     rcx, rbx
0x1800199f6  mov     rax, [rax+8]
0x1800199fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ff  nop
0x180019a00  mov     [rdi+10h], rsi
0x180019a04  mov     rax, [rsi]
0x180019a07  mov     rcx, rsi
0x180019a0a  mov     rax, [rax+8]
0x180019a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a13  mov     qword ptr [rdi+18h], 0
0x180019a1b  mov     dword ptr [rdi+20h], 0
0x180019a22  jmp     short loc_180019A26
0x180019a24  xor     edi, edi
0x180019a26  mov     rdx, rdi; struct Work *
0x180019a29  mov     rcx, rbp; SRWLock
0x180019a2c  call    ?SubmitWork@DockingProviders@@QEAAJPEAVWork@@@Z; DockingProviders::SubmitWork(Work *)
0x180019a31  add     rsp, 28h
0x180019a35  pop     rdi
0x180019a36  pop     rsi
0x180019a37  pop     rbp
0x180019a38  pop     rbx
0x180019a39  retn
```
