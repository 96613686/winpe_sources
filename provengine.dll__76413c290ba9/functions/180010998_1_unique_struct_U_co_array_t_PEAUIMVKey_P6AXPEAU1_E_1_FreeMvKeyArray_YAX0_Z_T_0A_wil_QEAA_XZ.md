# ??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x180010998`
- end: `0x1800109e8`
- name: `??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004528f`
- `0x1800452b3`
- `0x1800452fb`
- `0x180045bfe`

## callees

- `0x180010998`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_struct_U__co_array_t_PEAUIMVKey____P6AXPEAU1___E_1_FreeMvKeyArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  _QWORD *v1; // rdi
  unsigned int v2; // esi
  __int64 i; // rbx
  __int64 v4; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
    {
      v4 = v1[i];
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        v1[i] = 0;
      }
    }
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180010998  push    rbx
0x18001099a  push    rbp
0x18001099b  push    rsi
0x18001099c  push    rdi
0x18001099d  sub     rsp, 28h
0x1800109a1  mov     rdi, [rcx]
0x1800109a4  test    rdi, rdi
0x1800109a7  jz      short loc_1800109DF
0x1800109a9  mov     esi, [rcx+8]
0x1800109ac  xor     ebx, ebx
0x1800109ae  test    esi, esi
0x1800109b0  jz      short loc_1800109D5
0x1800109b2  mov     rcx, [rdi+rbx*8]
0x1800109b6  test    rcx, rcx
0x1800109b9  jz      short loc_1800109CF
0x1800109bb  mov     rax, [rcx]
0x1800109be  mov     rax, [rax+10h]
0x1800109c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c7  mov     qword ptr [rdi+rbx*8], 0
0x1800109cf  inc     ebx
0x1800109d1  cmp     ebx, esi
0x1800109d3  jb      short loc_1800109B2
0x1800109d5  mov     rcx, rdi; pv
0x1800109d8  call    cs:__imp_CoTaskMemFree
0x1800109de  nop
0x1800109df  add     rsp, 28h
0x1800109e3  pop     rdi
0x1800109e4  pop     rsi
0x1800109e5  pop     rbp
0x1800109e6  pop     rbx
0x1800109e7  retn
```
