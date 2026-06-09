# CProfileMgr::GetConnectionGUIDs(_GUID *,std::list<ushort *,std::allocator<ushort *>> *)

- ea: `0x18001fca8`
- end: `0x18001fde2`
- name: `?GetConnectionGUIDs@CProfileMgr@@QEAAJPEAU_GUID@@PEAV?$list@PEAGV?$allocator@PEAG@std@@@std@@@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fde8`

## callees

- `0x1800075a8`
- `0x180007ffc`
- `0x18001fca8`
- `0x180023010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001fd4f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001fd4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fdbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fdbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileMgr::GetConnectionGUIDs(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rcx
  int v6; // esi
  unsigned int v7; // ecx
  __int64 v8; // rbx
  _QWORD *v9; // r12
  __int64 v10; // r14
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  unsigned int i; // ebx
  LPVOID pv; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h]
  unsigned int v17; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+20h]

  if ( !a2 || !a3 )
    return 2147500035LL;
  v4 = *(_QWORD *)(a1 + 32);
  if ( !v4 )
    return 2147549183LL;
  v17 = 0;
  pv = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, LPVOID *))(*(_QWORD *)v4 + 80LL))(v4, a2, &v17, &pv);
  if ( v6 >= 0 )
  {
    v7 = v17;
    if ( v17 )
    {
      v8 = 0;
      while ( 1 )
      {
        v18 = v8;
        if ( (unsigned int)v8 >= v7 )
          break;
        try
        {
          if ( a3[1] == 0xAAAAAAAAAAAAAAALL )
            std::_Xlength_error("list too long");
          v9 = pv;
          v10 = *a3;
          v15 = a3;
          v16 = 0;
          v11 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(24);
          v11[2] = v9[v8];
          ++a3[1];
          v12 = *(_QWORD **)(v10 + 8);
          *v11 = v10;
          v11[1] = v12;
          v16 = 0;
          *(_QWORD *)(v10 + 8) = v11;
          *v12 = v11;
          std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(&v15);
          v8 = (unsigned int)(v8 + 1);
          v7 = v17;
        }
        catch ( ... )
        {
          for ( i = v18; i < v17; ++i )
            CoTaskMemFree(*((LPVOID *)pv + i));
          v6 = -2147024882;
          break;
        }
      }
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fca8  mov     [rsp+arg_0], rbx
0x18001fcad  push    rsi
0x18001fcae  push    rdi
0x18001fcaf  push    r12
0x18001fcb1  push    r14
0x18001fcb3  push    r15
0x18001fcb5  sub     rsp, 50h
0x18001fcb9  mov     rdi, r8
0x18001fcbc  test    rdx, rdx
0x18001fcbf  jz      loc_18001FDC8
0x18001fcc5  test    r8, r8
0x18001fcc8  jz      loc_18001FDC8
0x18001fcce  mov     rcx, [rcx+20h]
0x18001fcd2  test    rcx, rcx
0x18001fcd5  jnz     short loc_18001FCE1
0x18001fcd7  mov     eax, 8000FFFFh
0x18001fcdc  jmp     loc_18001FDCD
0x18001fce1  mov     [rsp+78h+arg_8], 0
0x18001fcec  mov     [rsp+78h+pv], 0
0x18001fcf5  mov     rax, [rcx]
0x18001fcf8  lea     r9, [rsp+78h+pv]
0x18001fcfd  lea     r8, [rsp+78h+arg_8]
0x18001fd05  mov     rax, [rax+50h]
0x18001fd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd0e  mov     esi, eax
0x18001fd10  test    eax, eax
0x18001fd12  js      loc_18001FDC4
0x18001fd18  mov     ecx, [rsp+78h+arg_8]
0x18001fd1f  test    ecx, ecx
0x18001fd21  jz      loc_18001FDC4
0x18001fd27  xor     ebx, ebx
0x18001fd29  mov     [rsp+78h+arg_18], ebx
0x18001fd30  cmp     ebx, ecx
0x18001fd32  jnb     loc_18001FDB9
0x18001fd38  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001fd42  cmp     [rdi+8], rax
0x18001fd46  jnz     short loc_18001FD55
0x18001fd48  lea     rcx, aListTooLong; "list too long"
0x18001fd4f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001fd55  mov     r12, [rsp+78h+pv]
0x18001fd5a  mov     r14, [rdi]
0x18001fd5d  mov     [rsp+78h+var_38], rdi
0x18001fd62  mov     [rsp+78h+var_30], 0
0x18001fd6b  mov     ecx, 18h
0x18001fd70  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001fd75  mov     rcx, [r12+rbx*8]
0x18001fd79  mov     [rax+10h], rcx
0x18001fd7d  inc     qword ptr [rdi+8]
0x18001fd81  mov     rcx, [r14+8]
0x18001fd85  mov     [rax], r14
0x18001fd88  mov     [rax+8], rcx
0x18001fd8c  mov     [rsp+78h+var_30], 0
0x18001fd95  mov     [r14+8], rax
0x18001fd99  mov     [rcx], rax
0x18001fd9c  lea     rcx, [rsp+78h+var_38]
0x18001fda1  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAUtagNSC_INSTANCE_DATA@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<tagNSC_INSTANCE_DATA *,void *>>>(void)
0x18001fda6  nop
0x18001fda7  inc     ebx
0x18001fda9  mov     ecx, [rsp+78h+arg_8]
0x18001fdb0  jmp     loc_18001FD29
0x18001fdb5  mov     esi, [rsp+78h+var_48]
0x18001fdb9  mov     rcx, [rsp+78h+pv]; pv
0x18001fdbe  call    cs:__imp_CoTaskMemFree
0x18001fdc4  mov     eax, esi
0x18001fdc6  jmp     short loc_18001FDCD
0x18001fdc8  mov     eax, 80004003h
0x18001fdcd  mov     rbx, [rsp+78h+arg_0]
0x18001fdd5  add     rsp, 50h
0x18001fdd9  pop     r15
0x18001fddb  pop     r14
0x18001fddd  pop     r12
0x18001fddf  pop     rdi
0x18001fde0  pop     rsi
0x18001fde1  retn
```
