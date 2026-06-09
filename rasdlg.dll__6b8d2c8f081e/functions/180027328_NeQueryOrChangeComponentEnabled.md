# NeQueryOrChangeComponentEnabled

- ea: `0x180027328`
- end: `0x18002744f`
- name: `NeQueryOrChangeComponentEnabled`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b388`
- `0x180026f84`

## callees

- `0x180026e64`
- `0x180027328`
- `0x18004d0c6`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027430`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027430`
- `RASAPI32!FIsNetComponentListed` at `0x180027420`
- `RASAPI32!FIsNetComponentListed` at `0x180027420`
- `RASAPI32!EnableOrDisableNetComponent` at `0x1800273fe`
- `RASAPI32!EnableOrDisableNetComponent` at `0x1800273fe`

## pseudocode

```c
_BOOL8 __fastcall NeQueryOrChangeComponentEnabled(__int64 *a1, __int64 *a2, int a3, BOOL a4)
{
  __int64 v4; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdi
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  BOOL v17; // [rsp+20h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-20h] BYREF

  v4 = *a2;
  Buf1 = 0;
  if ( (*(int (__fastcall **)(__int64 *, __int128 *))(v4 + 80))(a2, &Buf1) >= 0 )
  {
    v9 = *a2;
    pv = 0;
    if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v9 + 48))(a2, &pv) >= 0 )
    {
      v10 = memcmp_0(&Buf1, &GUID_DEVCLASS_NETTRANS, 0x10u);
      v11 = *a1;
      if ( v10 )
      {
        if ( a3 )
        {
          EnableOrDisableNetComponent(*(_QWORD *)(v11 + 872), pv, a4);
        }
        else
        {
          v17 = 0;
          a4 = 1;
          if ( (unsigned int)FIsNetComponentListed(*(_QWORD *)(v11 + 872), pv, &v17, 0) )
            a4 = v17;
        }
      }
      else
      {
        v12 = *(_QWORD *)(v11 + 872);
        v13 = DwProtocolFromComponentId((PCNZWCH)pv);
        v14 = *(_DWORD *)(v12 + 236);
        if ( a3 )
        {
          if ( a4 )
            v15 = v14 & ~v13;
          else
            v15 = v14 | v13;
          *(_DWORD *)(v12 + 236) = v15;
        }
        else
        {
          a4 = (v14 & v13) == 0;
        }
      }
      CoTaskMemFree(pv);
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180027328  push    rbp
0x18002732a  push    rbx
0x18002732b  push    rsi
0x18002732c  push    rdi
0x18002732d  push    r14
0x18002732f  mov     rbp, rsp
0x180027332  sub     rsp, 50h
0x180027336  mov     rax, cs:__security_cookie
0x18002733d  xor     rax, rsp
0x180027340  mov     [rbp+var_10], rax
0x180027344  mov     rax, [rdx]
0x180027347  mov     rdi, rdx
0x18002734a  xorps   xmm0, xmm0
0x18002734d  lea     rdx, [rbp+Buf1]
0x180027351  mov     r14, rcx
0x180027354  mov     ebx, r9d
0x180027357  movups  [rbp+Buf1], xmm0
0x18002735b  mov     rax, [rax+50h]
0x18002735f  mov     rcx, rdi
0x180027362  mov     esi, r8d
0x180027365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002736a  test    eax, eax
0x18002736c  js      loc_180027436
0x180027372  mov     rax, [rdi]
0x180027375  lea     rdx, [rbp+pv]
0x180027379  mov     [rbp+pv], 0
0x180027381  mov     rcx, rdi
0x180027384  mov     rax, [rax+30h]
0x180027388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738d  test    eax, eax
0x18002738f  js      loc_180027436
0x180027395  mov     r8d, 10h; Size
0x18002739b  lea     rdx, GUID_DEVCLASS_NETTRANS; Buf2
0x1800273a2  lea     rcx, [rbp+Buf1]; Buf1
0x1800273a6  call    memcmp_0
0x1800273ab  mov     rcx, [r14]
0x1800273ae  test    eax, eax
0x1800273b0  jnz     short loc_1800273EC
0x1800273b2  mov     rdi, [rcx+368h]
0x1800273b9  mov     rcx, [rbp+pv]; lpString1
0x1800273bd  call    DwProtocolFromComponentId
0x1800273c2  mov     ecx, [rdi+0ECh]
0x1800273c8  test    esi, esi
0x1800273ca  jz      short loc_1800273E0
0x1800273cc  test    ebx, ebx
0x1800273ce  jz      short loc_1800273D6
0x1800273d0  not     eax
0x1800273d2  and     eax, ecx
0x1800273d4  jmp     short loc_1800273D8
0x1800273d6  or      eax, ecx
0x1800273d8  mov     [rdi+0ECh], eax
0x1800273de  jmp     short loc_18002742C
0x1800273e0  test    eax, ecx
0x1800273e2  mov     ebx, 0
0x1800273e7  setz    bl
0x1800273ea  jmp     short loc_18002742C
0x1800273ec  mov     rdx, [rbp+pv]
0x1800273f0  test    esi, esi
0x1800273f2  jz      short loc_180027406
0x1800273f4  mov     rcx, [rcx+368h]
0x1800273fb  mov     r8d, ebx
0x1800273fe  call    cs:__imp_EnableOrDisableNetComponent
0x180027404  jmp     short loc_18002742C
0x180027406  mov     [rbp+var_30], 0
0x18002740d  lea     r8, [rbp+var_30]
0x180027411  mov     rcx, [rcx+368h]
0x180027418  xor     r9d, r9d
0x18002741b  mov     ebx, 1
0x180027420  call    cs:__imp_FIsNetComponentListed
0x180027426  test    eax, eax
0x180027428  cmovnz  ebx, [rbp+var_30]
0x18002742c  mov     rcx, [rbp+pv]; pv
0x180027430  call    cs:__imp_CoTaskMemFree
0x180027436  mov     eax, ebx
0x180027438  mov     rcx, [rbp+var_10]
0x18002743c  xor     rcx, rsp; StackCookie
0x18002743f  call    __security_check_cookie
0x180027444  add     rsp, 50h
0x180027448  pop     r14
0x18002744a  pop     rdi
0x18002744b  pop     rsi
0x18002744c  pop     rbx
0x18002744d  pop     rbp
0x18002744e  retn
```
