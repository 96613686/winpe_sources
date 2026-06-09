# ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::QueryInterface(_GUID const &,void * *)

- ea: `0x140007440`
- end: `0x140007543`
- name: `?QueryInterface@?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007440`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::QueryInterface(
        char *a1,
        _DWORD *a2,
        char **a3)
{
  __int64 result; // rax
  GUID **v7; // rdi
  GUID *v8; // rcx
  int v9; // ebp
  GUID *v10; // rax
  char *v11; // rbx

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !*a2 && !a2[1] && a2[2] == 192 && a2[3] == 1174405120 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
    *a3 = a1;
    return 0;
  }
  v7 = &`ServerClassFactoryT<CProvisioningWapDPURemote>::_GetEntries'::`2'::_entries;
  while ( 1 )
  {
    v8 = *v7;
    if ( !*v7 )
    {
      v9 = 1;
      goto LABEL_18;
    }
    if ( v8->Data1 == *a2
      && *(_DWORD *)&v8->Data2 == a2[1]
      && *(_DWORD *)v8->Data4 == a2[2]
      && *(_DWORD *)&v8->Data4[4] == a2[3] )
    {
      break;
    }
LABEL_22:
    v7 += 3;
    if ( !v7[2] )
      return 2147500034LL;
  }
  v9 = 0;
LABEL_18:
  v10 = v7[2];
  if ( v10 != (GUID *)1 )
  {
    result = ((__int64 (__fastcall *)(char *, _DWORD *, char **, GUID *))v10)(a1, a2, a3, v7[1]);
    if ( !(_DWORD)result || !v9 && (int)result < 0 )
      return result;
    goto LABEL_22;
  }
  v11 = (char *)v7[1] + (_QWORD)a1;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
  *a3 = v11;
  return 0;
}

```

## disassembly

```asm
0x140007440  push    rbx
0x140007442  push    rbp
0x140007443  push    rsi
0x140007444  push    rdi
0x140007445  push    r14
0x140007447  sub     rsp, 30h
0x14000744b  mov     r14, r8
0x14000744e  mov     rbx, rdx
0x140007451  mov     rsi, rcx
0x140007454  test    rcx, rcx
0x140007457  jz      loc_140007532
0x14000745d  test    r8, r8
0x140007460  jnz     short loc_14000746C
0x140007462  mov     eax, 80004003h
0x140007467  jmp     loc_140007537
0x14000746c  mov     qword ptr [r8], 0
0x140007473  cmp     dword ptr [rdx], 0
0x140007476  jnz     short loc_1400074A6
0x140007478  cmp     dword ptr [rdx+4], 0
0x14000747c  jnz     short loc_1400074A6
0x14000747e  cmp     dword ptr [rdx+8], 0C0h
0x140007485  jnz     short loc_1400074A6
0x140007487  cmp     dword ptr [rdx+0Ch], 46000000h
0x14000748e  jnz     short loc_1400074A6
0x140007490  mov     rax, [rcx]
0x140007493  mov     rax, [rax+8]
0x140007497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000749c  mov     [r14], rsi
0x14000749f  xor     eax, eax
0x1400074a1  jmp     loc_140007537
0x1400074a6  lea     rdi, ?_entries@?1??_GetEntries@?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; ATL::_ATL_INTMAP_ENTRY const near * const `ServerClassFactoryT<CProvisioningWapDPURemote>::_GetEntries(void)'::`2'::_entries
0x1400074ad  mov     rcx, [rdi]
0x1400074b0  test    rcx, rcx
0x1400074b3  jnz     short loc_1400074BA
0x1400074b5  lea     ebp, [rcx+1]
0x1400074b8  jmp     short loc_1400074DA
0x1400074ba  mov     eax, [rbx]
0x1400074bc  cmp     [rcx], eax
0x1400074be  jnz     short loc_140007502
0x1400074c0  mov     eax, [rbx+4]
0x1400074c3  cmp     [rcx+4], eax
0x1400074c6  jnz     short loc_140007502
0x1400074c8  mov     eax, [rbx+8]
0x1400074cb  cmp     [rcx+8], eax
0x1400074ce  jnz     short loc_140007502
0x1400074d0  mov     eax, [rbx+0Ch]
0x1400074d3  cmp     [rcx+0Ch], eax
0x1400074d6  jnz     short loc_140007502
0x1400074d8  xor     ebp, ebp
0x1400074da  mov     rax, [rdi+10h]
0x1400074de  cmp     rax, 1
0x1400074e2  jz      short loc_140007514
0x1400074e4  mov     r9, [rdi+8]
0x1400074e8  mov     r8, r14
0x1400074eb  mov     rdx, rbx
0x1400074ee  mov     rcx, rsi
0x1400074f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074f6  test    eax, eax
0x1400074f8  jz      short loc_140007537
0x1400074fa  test    ebp, ebp
0x1400074fc  jnz     short loc_140007502
0x1400074fe  test    eax, eax
0x140007500  js      short loc_140007537
0x140007502  add     rdi, 18h
0x140007506  cmp     qword ptr [rdi+10h], 0
0x14000750b  jnz     short loc_1400074AD
0x14000750d  mov     eax, 80004002h
0x140007512  jmp     short loc_140007537
0x140007514  mov     rbx, [rdi+8]
0x140007518  add     rbx, rsi
0x14000751b  mov     rax, [rbx]
0x14000751e  mov     rcx, rbx
0x140007521  mov     rax, [rax+8]
0x140007525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000752a  mov     [r14], rbx
0x14000752d  jmp     loc_14000749F
0x140007532  mov     eax, 80070057h
0x140007537  add     rsp, 30h
0x14000753b  pop     r14
0x14000753d  pop     rdi
0x14000753e  pop     rsi
0x14000753f  pop     rbp
0x140007540  pop     rbx
0x140007541  retn
```
