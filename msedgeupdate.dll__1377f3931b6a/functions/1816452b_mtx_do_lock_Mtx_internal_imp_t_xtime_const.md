# mtx_do_lock(_Mtx_internal_imp_t *,xtime const *)

- ea: `0x1816452b`
- end: `0x181646e6`
- name: `?mtx_do_lock@@YAHPAU_Mtx_internal_imp_t@@PBUxtime@@@Z`
- size: `443`
- prototype: `int __cdecl(struct _Mtx_internal_imp_t *, const struct xtime *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x181647e6`
- `0x1816480b`

## callees

- `0x18007b40`
- `0x18127b28`
- `0x1816452b`
- `0x18164965`
- `0x181649cc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18164553`
- `KERNEL32!GetCurrentThreadId` at `0x18164570`
- `KERNEL32!GetCurrentThreadId` at `0x18164591`
- `KERNEL32!GetCurrentThreadId` at `0x18164614`
- `KERNEL32!GetCurrentThreadId` at `0x18164658`
- `KERNEL32!GetCurrentThreadId` at `0x1816469e`
- `KERNEL32!GetCurrentThreadId` at `0x18164553`
- `KERNEL32!GetCurrentThreadId` at `0x18164570`
- `KERNEL32!GetCurrentThreadId` at `0x18164591`
- `KERNEL32!GetCurrentThreadId` at `0x18164614`
- `KERNEL32!GetCurrentThreadId` at `0x18164658`
- `KERNEL32!GetCurrentThreadId` at `0x1816469e`

## pseudocode

```c
int __cdecl mtx_do_lock(struct _Mtx_internal_imp_t *a1, const struct xtime *a2)
{
  const struct xtime *v2; // esi
  int v4; // edi
  unsigned __int8 (__thiscall *v5)(char *, int); // esi
  int v6; // eax
  DWORD *v7; // esi
  int v8; // ecx
  xtime v10; // [esp+10h] [ebp-14h] BYREF

  v2 = a2;
  if ( (*(_DWORD *)a1 & 0xFFFFFEFF) == 1 )
  {
    if ( *((_DWORD *)a1 + 10) != GetCurrentThreadId() )
    {
      (**((void (__thiscall ***)(char *))a1 + 1))((char *)a1 + 4);
      *((_DWORD *)a1 + 10) = GetCurrentThreadId();
    }
    ++*((_DWORD *)a1 + 11);
    return 0;
  }
  if ( !a2 )
  {
    if ( *((_DWORD *)a1 + 10) != GetCurrentThreadId() )
      (**((void (__thiscall ***)(char *))a1 + 1))((char *)a1 + 4);
LABEL_21:
    v7 = (DWORD *)((char *)a1 + 40);
    v4 = 0;
    goto LABEL_22;
  }
  v4 = 0;
  if ( a2->sec >= 0 && (a2->sec || a2->nsec > 0) )
  {
    xtime_get(&v10, 1);
    while ( v10.sec < v2->sec || v10.sec == v2->sec && v10.nsec < v2->nsec )
    {
      if ( *((_DWORD *)a1 + 10) == GetCurrentThreadId() )
        goto LABEL_21;
      v5 = *(unsigned __int8 (__thiscall **)(char *, int))(*((_DWORD *)a1 + 1) + 8);
      v6 = _Xtime_diff_to_millis2(a2, &v10);
      if ( v5((char *)a1 + 4, v6) )
        goto LABEL_21;
      xtime_get(&v10, 1);
      v2 = a2;
    }
    goto LABEL_31;
  }
  v7 = (DWORD *)((char *)a1 + 40);
  if ( *((_DWORD *)a1 + 10) != GetCurrentThreadId() )
  {
    if ( !(*(unsigned __int8 (__thiscall **)(char *))(*((_DWORD *)a1 + 1) + 4))((char *)a1 + 4) )
    {
      v2 = a2;
      goto LABEL_31;
    }
    goto LABEL_21;
  }
LABEL_22:
  v8 = *((_DWORD *)a1 + 11);
  *((_DWORD *)a1 + 11) = v8 + 1;
  if ( v8 + 1 <= 1 )
  {
    *v7 = GetCurrentThreadId();
  }
  else if ( (*(_DWORD *)a1 & 0x100) == 0 )
  {
    *((_DWORD *)a1 + 11) = v8;
    v4 = 258;
  }
  if ( !v4 )
    return 0;
  v2 = a2;
  if ( !a2 )
    return 3;
LABEL_31:
  if ( v2->sec )
    return 2;
  return 3 - (v2->nsec != 0);
}

```

## disassembly

```asm
0x1816452b  push    ebp
0x1816452c  mov     ebp, esp
0x1816452e  sub     esp, 18h
0x18164531  mov     eax, ___security_cookie
0x18164536  xor     eax, ebp
0x18164538  mov     [ebp+var_4], eax
0x1816453b  push    ebx
0x1816453c  mov     ebx, [ebp+arg_0]
0x1816453f  push    esi
0x18164540  mov     esi, [ebp+arg_4]
0x18164543  push    edi
0x18164544  mov     eax, [ebx]
0x18164546  and     eax, 0FFFFFEFFh
0x1816454b  mov     [ebp+var_18], esi
0x1816454e  cmp     eax, 1
0x18164551  jnz     short loc_1816458D
0x18164553  call    ds:__imp_GetCurrentThreadId
0x18164559  cmp     [ebx+28h], eax
0x1816455c  jz      short loc_18164579
0x1816455e  mov     eax, [ebx+4]
0x18164561  mov     esi, [eax]
0x18164563  mov     ecx, esi
0x18164565  call    ds:___guard_check_icall_fptr
0x1816456b  lea     ecx, [ebx+4]
0x1816456e  call    esi
0x18164570  call    ds:__imp_GetCurrentThreadId
0x18164576  mov     [ebx+28h], eax
0x18164579  inc     dword ptr [ebx+2Ch]
0x1816457c  xor     eax, eax
0x1816457e  mov     ecx, [ebp+var_4]
0x18164581  pop     edi
0x18164582  pop     esi
0x18164583  xor     ecx, ebp; StackCookie
0x18164585  pop     ebx
0x18164586  call    @__security_check_cookie@4
0x1816458b  leave
0x1816458c  retn
0x1816458d  test    esi, esi
0x1816458f  jnz     short loc_181645B7
0x18164591  call    ds:__imp_GetCurrentThreadId
0x18164597  cmp     [ebx+28h], eax
0x1816459a  jz      loc_18164679
0x181645a0  mov     eax, [ebx+4]
0x181645a3  mov     esi, [eax]
0x181645a5  mov     ecx, esi
0x181645a7  call    ds:___guard_check_icall_fptr
0x181645ad  lea     ecx, [ebx+4]
0x181645b0  call    esi
0x181645b2  jmp     loc_18164679
0x181645b7  mov     eax, [esi]
0x181645b9  xor     edi, edi
0x181645bb  cmp     [esi+4], edi
0x181645be  jl      loc_18164655
0x181645c4  jg      short loc_181645CE
0x181645c6  cmp     eax, edi
0x181645c8  jb      loc_18164655
0x181645ce  or      eax, [esi+4]
0x181645d1  jnz     short loc_181645D8
0x181645d3  cmp     [esi+8], edi
0x181645d6  jle     short loc_18164655
0x181645d8  lea     eax, [ebp+var_14]
0x181645db  push    1; int
0x181645dd  push    eax; xtime *
0x181645de  call    _xtime_get
0x181645e3  mov     eax, [esi]
0x181645e5  pop     ecx
0x181645e6  pop     ecx
0x181645e7  mov     ecx, dword ptr [ebp+var_14.sec+4]
0x181645ea  cmp     ecx, [esi+4]
0x181645ed  jl      short loc_18164614
0x181645ef  jg      short loc_181645F6
0x181645f1  cmp     dword ptr [ebp+var_14.sec], eax
0x181645f4  jb      short loc_18164614
0x181645f6  cmp     dword ptr [ebp+var_14.sec], eax
0x181645f9  jnz     loc_181646CC
0x181645ff  cmp     ecx, [esi+4]
0x18164602  jnz     loc_181646CC
0x18164608  mov     eax, [ebp+var_14.nsec]
0x1816460b  cmp     eax, [esi+8]
0x1816460e  jge     loc_181646CC
0x18164614  call    ds:__imp_GetCurrentThreadId
0x1816461a  cmp     [ebx+28h], eax
0x1816461d  jz      short loc_18164679
0x1816461f  mov     eax, [ebx+4]
0x18164622  mov     esi, [eax+8]
0x18164625  lea     eax, [ebp+var_14]
0x18164628  push    eax; xtime *
0x18164629  push    [ebp+var_18]; xtime *
0x1816462c  call    __Xtime_diff_to_millis2
0x18164631  pop     ecx
0x18164632  pop     ecx
0x18164633  push    eax
0x18164634  mov     ecx, esi
0x18164636  call    ds:___guard_check_icall_fptr
0x1816463c  lea     ecx, [ebx+4]
0x1816463f  call    esi
0x18164641  test    al, al
0x18164643  jnz     short loc_18164679
0x18164645  lea     eax, [ebp+var_14]
0x18164648  push    1; int
0x1816464a  push    eax; xtime *
0x1816464b  call    _xtime_get
0x18164650  mov     esi, [ebp+var_18]
0x18164653  jmp     short loc_181645E3
0x18164655  lea     esi, [ebx+28h]
0x18164658  call    ds:__imp_GetCurrentThreadId
0x1816465e  cmp     [esi], eax
0x18164660  jz      short loc_1816467E
0x18164662  mov     eax, [ebx+4]
0x18164665  mov     esi, [eax+4]
0x18164668  mov     ecx, esi
0x1816466a  call    ds:___guard_check_icall_fptr
0x18164670  lea     ecx, [ebx+4]
0x18164673  call    esi
0x18164675  test    al, al
0x18164677  jz      short loc_181646C9
0x18164679  lea     esi, [ebx+28h]
0x1816467c  xor     edi, edi
0x1816467e  mov     ecx, [ebx+2Ch]
0x18164681  lea     eax, [ecx+1]
0x18164684  mov     [ebx+2Ch], eax
0x18164687  cmp     eax, 1
0x1816468a  jle     short loc_1816469E
0x1816468c  test    dword ptr [ebx], 100h
0x18164692  jnz     short loc_181646A6
0x18164694  mov     [ebx+2Ch], ecx
0x18164697  mov     edi, 102h
0x1816469c  jmp     short loc_181646A6
0x1816469e  call    ds:__imp_GetCurrentThreadId
0x181646a4  mov     [esi], eax
0x181646a6  test    edi, edi
0x181646a8  jz      loc_1816457C
0x181646ae  cmp     edi, 102h
0x181646b4  jz      short loc_181646BA
0x181646b6  push    4
0x181646b8  jmp     short loc_181646C3
0x181646ba  mov     esi, [ebp+var_18]
0x181646bd  test    esi, esi
0x181646bf  jnz     short loc_181646CC
0x181646c1  push    3
0x181646c3  pop     eax
0x181646c4  jmp     loc_1816457E
0x181646c9  mov     esi, [ebp+var_18]
0x181646cc  mov     eax, [esi]
0x181646ce  or      eax, [esi+4]
0x181646d1  jnz     short loc_181646E2
0x181646d3  mov     eax, [esi+8]
0x181646d6  neg     eax
0x181646d8  sbb     eax, eax
0x181646da  add     eax, 3
0x181646dd  jmp     loc_1816457E
0x181646e2  push    2
0x181646e4  jmp     short loc_181646C3
```
