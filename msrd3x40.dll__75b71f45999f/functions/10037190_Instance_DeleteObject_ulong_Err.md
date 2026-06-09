# Instance::DeleteObject(ulong,Err &)

- ea: `0x10037190`
- end: `0x1003745c`
- name: `?DeleteObject@Instance@@QAEXKAAVErr@@@Z`
- size: `716`
- prototype: `void __thiscall(Instance *__hidden this, unsigned int, struct Err *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x10028bc0`
- `0x10029260`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x10025fc0`
- `0x10026020`
- `0x100364e0`
- `0x10037190`
- `0x1005e3b0`
- `0x1005e7dc`

## pseudocode

```c
void __thiscall Instance::DeleteObject(Instance *this, unsigned int a2, struct Err *a3)
{
  struct Err *v3; // ebx
  int v4; // ecx
  unsigned int v5; // eax
  int v6; // ecx
  unsigned int v7; // [esp+Ch] [ebp-98h] BYREF
  _DWORD **v8; // [esp+10h] [ebp-94h]
  unsigned int v9; // [esp+14h] [ebp-90h] BYREF
  Instance *v10; // [esp+18h] [ebp-8Ch]
  unsigned __int16 v11[66]; // [esp+1Ch] [ebp-88h] BYREF

  v3 = a3;
  v10 = this;
  (*(void (__thiscall **)(_DWORD, const unsigned __int16 *, struct Err *))(**((_DWORD **)this + 5) + 8))(
    *((_DWORD *)this + 5),
    L"Id",
    a3);
  if ( (*(_BYTE *)v3 & 8) == 0 )
  {
    (*(void (__thiscall **)(_DWORD, unsigned int *, int, _DWORD, struct Err *))(**(_DWORD **)(*((_DWORD *)v10 + 5) + 36)
                                                                              + 24))(
      *(_DWORD *)(*((_DWORD *)v10 + 5) + 36),
      &a2,
      4,
      0,
      v3);
    (*(void (__thiscall **)(_DWORD, _DWORD, struct Err *))(**(_DWORD **)(*((_DWORD *)v10 + 5) + 36) + 28))(
      *(_DWORD *)(*((_DWORD *)v10 + 5) + 36),
      0,
      v3);
  }
  if ( (*(_DWORD *)v3 & 8) != 0 )
  {
    if ( (*(_DWORD *)v3 & 1) == 0 && *((_DWORD *)v3 + 1) == -1601 )
      Err::OverrideError(v3, -1305);
  }
  else if ( a2 >= 0xF000000 )
  {
    if ( a2 > 0x10000000 )
    {
      LOWORD(v9) = 0;
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)v10 + 5) + 108))(
        *((_DWORD *)v10 + 5),
        *((_DWORD *)v10 + 10),
        &v9,
        2,
        0,
        v3);
      if ( (_WORD)v9 == 3 )
      {
        v8 = (_DWORD **)(*(int (__thiscall **)(_DWORD, struct Err *))(**((_DWORD **)v10 + 5) + 4))(
                          *((_DWORD *)v10 + 5),
                          v3);
        ((void (__thiscall *)(_DWORD **, const wchar_t *, struct Err *))(*v8)[2])(v8, L"ParentIdName", v3);
        (*(void (__thiscall **)(_DWORD *, unsigned int *, int, _DWORD, struct Err *))(*v8[9] + 24))(
          v8[9],
          &a2,
          4,
          0,
          v3);
        (*(void (__thiscall **)(_DWORD *, int, struct Err *))(*v8[9] + 28))(v8[9], 5, v3);
        if ( (*(_DWORD *)v3 & 8) != 0 )
        {
          if ( (*(_DWORD *)v3 & 1) == 0 && *((_DWORD *)v3 + 1) == -1601 )
            Err::Reset(v3);
        }
        else
        {
          ((void (__thiscall *)(_DWORD **, _DWORD, unsigned int *, int, _DWORD, struct Err *))(*v8)[27])(
            v8,
            *((_DWORD *)v10 + 7),
            &v7,
            4,
            0,
            v3);
          Err::Reset(v3);
          if ( v7 == a2 )
            Err::SetError(v3, -1043, v6);
        }
        ((void (__thiscall *)(_DWORD **, int))**v8)(v8, 1);
      }
      if ( (*(_BYTE *)v3 & 8) == 0 )
        (*(void (__thiscall **)(_DWORD, struct Err *))(**((_DWORD **)v10 + 5) + 32))(*((_DWORD *)v10 + 5), v3);
    }
    else
    {
      Err::SetError(v3, -1907, v4);
    }
  }
  else
  {
    v5 = (*(int (__thiscall **)(_DWORD, _DWORD, unsigned __int16 *, int, _DWORD, struct Err *))(**((_DWORD **)v10 + 5)
                                                                                              + 108))(
           *((_DWORD *)v10 + 5),
           *((_DWORD *)v10 + 9),
           v11,
           128,
           0,
           v3)
       & 0xFFFFFFFE;
    if ( v5 >= 0x82 )
      __report_rangecheckfailure();
    *(unsigned __int16 *)((char *)v11 + v5) = 0;
    Instance::DeleteTable(v10, v11, v3);
  }
}

```

## disassembly

```asm
0x10037190  mov     edi, edi
0x10037192  push    ebp
0x10037193  mov     ebp, esp
0x10037195  sub     esp, 98h
0x1003719b  mov     eax, ___security_cookie
0x100371a0  xor     eax, ebp
0x100371a2  mov     [ebp+var_4], eax
0x100371a5  push    ebx
0x100371a6  mov     ebx, [ebp+arg_4]
0x100371a9  mov     eax, ecx
0x100371ab  push    esi
0x100371ac  push    edi; unsigned int
0x100371ad  mov     [ebp+var_8C], eax
0x100371b3  mov     edi, [eax+14h]
0x100371b6  push    ebx; unsigned int
0x100371b7  push    offset aId; "Id"
0x100371bc  mov     eax, [edi]
0x100371be  mov     esi, [eax+8]
0x100371c1  mov     ecx, esi
0x100371c3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100371c9  mov     ecx, edi
0x100371cb  call    esi
0x100371cd  test    byte ptr [ebx], 8
0x100371d0  jnz     short loc_10037218
0x100371d2  mov     eax, [ebp+var_8C]
0x100371d8  push    ebx
0x100371d9  push    0
0x100371db  push    4; unsigned int
0x100371dd  mov     eax, [eax+14h]
0x100371e0  mov     edi, [eax+24h]
0x100371e3  lea     eax, [ebp+arg_0]
0x100371e6  push    eax; void *
0x100371e7  mov     esi, [edi]
0x100371e9  mov     esi, [esi+18h]
0x100371ec  mov     ecx, esi
0x100371ee  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100371f4  mov     ecx, edi
0x100371f6  call    esi
0x100371f8  mov     ecx, [ebp+var_8C]
0x100371fe  push    ebx; unsigned int
0x100371ff  push    0; void *
0x10037201  mov     eax, [ecx+14h]
0x10037204  mov     edi, [eax+24h]
0x10037207  mov     eax, [edi]
0x10037209  mov     esi, [eax+1Ch]
0x1003720c  mov     ecx, esi
0x1003720e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037214  mov     ecx, edi
0x10037216  call    esi
0x10037218  mov     eax, [ebx]
0x1003721a  test    al, 8
0x1003721c  jz      short loc_10037252
0x1003721e  test    al, 1
0x10037220  jnz     loc_10037444
0x10037226  cmp     dword ptr [ebx+4], 0FFFFF9BFh
0x1003722d  jnz     loc_10037444
0x10037233  push    0FFFFFAE7h; int
0x10037238  mov     ecx, ebx; this
0x1003723a  call    ?OverrideError@Err@@QAEXJ@Z; Err::OverrideError(long)
0x1003723f  pop     edi
0x10037240  pop     esi
0x10037241  pop     ebx
0x10037242  mov     ecx, [ebp+var_4]
0x10037245  xor     ecx, ebp; StackCookie
0x10037247  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003724c  mov     esp, ebp
0x1003724e  pop     ebp
0x1003724f  retn    8
0x10037252  mov     eax, [ebp+arg_0]
0x10037255  cmp     eax, 0F000000h
0x1003725a  jnb     short loc_100372C6
0x1003725c  mov     ecx, [ebp+var_8C]
0x10037262  push    ebx
0x10037263  push    0
0x10037265  push    80h
0x1003726a  mov     edi, [ecx+14h]
0x1003726d  mov     eax, [edi]
0x1003726f  mov     esi, [eax+6Ch]
0x10037272  lea     eax, [ebp+var_88]
0x10037278  push    eax; unsigned int
0x10037279  push    dword ptr [ecx+24h]; void *
0x1003727c  mov     ecx, esi
0x1003727e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037284  mov     ecx, edi
0x10037286  call    esi
0x10037288  and     eax, 0FFFFFFFEh
0x1003728b  cmp     eax, 82h
0x10037290  jnb     loc_10037457
0x10037296  xor     ecx, ecx
0x10037298  mov     [ebp+eax+var_88], cx
0x100372a0  lea     eax, [ebp+var_88]
0x100372a6  mov     ecx, [ebp+var_8C]; this
0x100372ac  push    ebx; struct Err *
0x100372ad  push    eax; unsigned __int16 *
0x100372ae  call    ?DeleteTable@Instance@@QAEXPBGAAVErr@@@Z; Instance::DeleteTable(ushort const *,Err &)
0x100372b3  pop     edi
0x100372b4  pop     esi
0x100372b5  pop     ebx
0x100372b6  mov     ecx, [ebp+var_4]
0x100372b9  xor     ecx, ebp; StackCookie
0x100372bb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100372c0  mov     esp, ebp
0x100372c2  pop     ebp
0x100372c3  retn    8
0x100372c6  cmp     eax, 10000000h
0x100372cb  ja      short loc_100372ED
0x100372cd  push    ecx
0x100372ce  push    0FFFFF88Dh
0x100372d3  mov     ecx, ebx
0x100372d5  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100372da  pop     edi
0x100372db  pop     esi
0x100372dc  pop     ebx
0x100372dd  mov     ecx, [ebp+var_4]
0x100372e0  xor     ecx, ebp; StackCookie
0x100372e2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100372e7  mov     esp, ebp
0x100372e9  pop     ebp
0x100372ea  retn    8
0x100372ed  xor     eax, eax
0x100372ef  lea     ecx, [ebp+var_90]
0x100372f5  mov     word ptr [ebp+var_90], ax
0x100372fc  mov     eax, [ebp+var_8C]
0x10037302  push    ebx
0x10037303  push    0
0x10037305  push    2
0x10037307  mov     edi, [eax+14h]
0x1003730a  push    ecx; unsigned int
0x1003730b  push    dword ptr [eax+28h]; void *
0x1003730e  mov     esi, [edi]
0x10037310  mov     esi, [esi+6Ch]
0x10037313  mov     ecx, esi
0x10037315  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003731b  mov     ecx, edi
0x1003731d  call    esi
0x1003731f  cmp     word ptr [ebp+var_90], 3
0x10037327  jnz     loc_10037424
0x1003732d  mov     eax, [ebp+var_8C]
0x10037333  push    ebx; void *
0x10037334  mov     edi, [eax+14h]
0x10037337  mov     eax, [edi]
0x10037339  mov     esi, [eax+4]
0x1003733c  mov     ecx, esi
0x1003733e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037344  mov     ecx, edi
0x10037346  call    esi
0x10037348  mov     edi, eax
0x1003734a  push    ebx; unsigned int
0x1003734b  push    offset aParentidname; "ParentIdName"
0x10037350  mov     [ebp+var_94], edi
0x10037356  mov     ecx, [edi]
0x10037358  mov     esi, [ecx+8]
0x1003735b  mov     ecx, esi
0x1003735d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037363  mov     ecx, edi
0x10037365  call    esi
0x10037367  mov     edi, [edi+24h]
0x1003736a  lea     eax, [ebp+arg_0]
0x1003736d  push    ebx
0x1003736e  push    0
0x10037370  push    4; unsigned int
0x10037372  mov     esi, [edi]
0x10037374  push    eax; void *
0x10037375  mov     esi, [esi+18h]
0x10037378  mov     ecx, esi
0x1003737a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037380  mov     ecx, edi
0x10037382  call    esi
0x10037384  mov     edi, [ebp+var_94]
0x1003738a  push    ebx; unsigned int
0x1003738b  push    5; void *
0x1003738d  mov     edi, [edi+24h]
0x10037390  mov     eax, [edi]
0x10037392  mov     esi, [eax+1Ch]
0x10037395  mov     ecx, esi
0x10037397  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003739d  mov     ecx, edi
0x1003739f  call    esi
0x100373a1  mov     eax, [ebx]
0x100373a3  test    al, 8
0x100373a5  jz      short loc_100373BD
0x100373a7  test    al, 1
0x100373a9  jnz     short loc_10037408
0x100373ab  cmp     dword ptr [ebx+4], 0FFFFF9BFh
0x100373b2  jnz     short loc_10037408
0x100373b4  mov     ecx, ebx; this
0x100373b6  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x100373bb  jmp     short loc_10037408
0x100373bd  mov     edi, [ebp+var_94]
0x100373c3  lea     eax, [ebp+var_98]
0x100373c9  push    ebx
0x100373ca  push    0
0x100373cc  push    4
0x100373ce  mov     esi, [edi]
0x100373d0  push    eax; unsigned int
0x100373d1  mov     eax, [ebp+var_8C]
0x100373d7  mov     esi, [esi+6Ch]
0x100373da  mov     ecx, esi
0x100373dc  push    dword ptr [eax+1Ch]; void *
0x100373df  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100373e5  mov     ecx, edi
0x100373e7  call    esi
0x100373e9  mov     ecx, ebx; this
0x100373eb  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x100373f0  mov     eax, [ebp+var_98]
0x100373f6  cmp     eax, [ebp+arg_0]
0x100373f9  jnz     short loc_10037408
0x100373fb  push    ecx
0x100373fc  push    0FFFFFBEDh
0x10037401  mov     ecx, ebx
0x10037403  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10037408  mov     eax, [ebp+var_94]
0x1003740e  push    1; void *
0x10037410  mov     eax, [eax]
0x10037412  mov     esi, [eax]
0x10037414  mov     ecx, esi
0x10037416  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003741c  mov     ecx, [ebp+var_94]
0x10037422  call    esi
0x10037424  test    byte ptr [ebx], 8
0x10037427  jnz     short loc_10037444
0x10037429  mov     eax, [ebp+var_8C]
0x1003742f  push    ebx; void *
0x10037430  mov     edi, [eax+14h]
0x10037433  mov     eax, [edi]
0x10037435  mov     esi, [eax+20h]
0x10037438  mov     ecx, esi
0x1003743a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037440  mov     ecx, edi
0x10037442  call    esi
0x10037444  mov     ecx, [ebp+var_4]
0x10037447  pop     edi
0x10037448  pop     esi
0x10037449  xor     ecx, ebp; StackCookie
0x1003744b  pop     ebx
0x1003744c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037451  mov     esp, ebp
0x10037453  pop     ebp
0x10037454  retn    8
0x10037457  call    ___report_rangecheckfailure
```
