# ErrorTable::Intercept(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,IAdvancedTableDispenser *,ushort const *,void *,void * *)

- ea: `0x180015180`
- end: `0x180015305`
- name: `?Intercept@ErrorTable@@UEAAJPEBG0KPEAX1KKPEAUIAdvancedTableDispenser@@01PEAPEAX@Z`
- size: `389`
- prototype: `int(ErrorTable *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, void *, unsigned int, unsigned int, struct IAdvancedTableDispenser *, const unsigned __int16 *, void *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015180`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800151b1`
- `msvcrt!_wcsicmp` at `0x1800151c9`
- `msvcrt!_wcsicmp` at `0x1800151b1`
- `msvcrt!_wcsicmp` at `0x1800151c9`
- `ATL!__imp_AtlComQIPtrAssign` at `0x1800152b9`
- `ATL!__imp_AtlComQIPtrAssign` at `0x1800152b9`

## pseudocode

```c
__int64 __fastcall ErrorTable::Intercept(
        ErrorTable *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        _DWORD *a5,
        int *a6,
        unsigned int a7,
        unsigned int a8,
        struct IAdvancedTableDispenser *a9,
        const unsigned __int16 *a10,
        void *a11,
        void **a12)
{
  int v16; // eax
  __int64 result; // rax
  unsigned int v19; // esi

  _InterlockedIncrement((volatile signed __int32 *)this + 9);
  if ( *((_DWORD *)this + 9) != 1 || _wcsicmp(a2, L"ERRORS") || _wcsicmp(a3, L"DETAILEDERRORS") || a11 || !a9 )
    return 2147942487LL;
  v16 = (int)a6;
  *a12 = 0;
  if ( a6 )
    v16 = *a6;
  while ( v16 )
  {
    if ( (a5[3] & 0xF0000000) == 0 )
      return 2149648395LL;
    --v16;
    a5 += 6;
  }
  if ( (a8 & 2) != 0 )
    return 2149648397LL;
  if ( a7 != 3 )
    return 2149648396LL;
  result = (*(__int64 (__fastcall **)(struct IAdvancedTableDispenser *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, int, unsigned int, char *))(*(_QWORD *)a9 + 32LL))(
             a9,
             a2,
             a3,
             a4,
             0,
             0,
             3,
             a8,
             (char *)this + 40);
  v19 = result;
  if ( (int)result >= 0 )
  {
    AtlComQIPtrAssign((char *)this + 48, *((_QWORD *)this + 5), &IID_ISimpleTableController);
    if ( *((_QWORD *)this + 6) )
    {
      *a12 = (void *)(((unsigned __int64)this + 8) & -(__int64)(this != 0));
      (*(void (__fastcall **)(ErrorTable *))(*(_QWORD *)this + 8LL))(this);
      return v19;
    }
    else
    {
      return 2147500034LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015180  push    rbx
0x180015182  push    rbp
0x180015183  push    rsi
0x180015184  push    rdi
0x180015185  push    r14
0x180015187  push    r15
0x180015189  sub     rsp, 58h
0x18001518d  mov     ebp, r9d
0x180015190  mov     rbx, r8
0x180015193  mov     rsi, rdx
0x180015196  mov     rdi, rcx
0x180015199  lock inc dword ptr [rcx+24h]
0x18001519d  cmp     dword ptr [rcx+24h], 1
0x1800151a1  jnz     loc_1800152F3
0x1800151a7  lea     rdx, aErrors; "ERRORS"
0x1800151ae  mov     rcx, rsi; String1
0x1800151b1  call    cs:__imp__wcsicmp
0x1800151b7  test    eax, eax
0x1800151b9  jnz     loc_1800152F3
0x1800151bf  lea     rdx, aDetailederrors; "DETAILEDERRORS"
0x1800151c6  mov     rcx, rbx; String1
0x1800151c9  call    cs:__imp__wcsicmp
0x1800151cf  test    eax, eax
0x1800151d1  jnz     loc_1800152F3
0x1800151d7  cmp     [rsp+88h+arg_50], 0
0x1800151e0  jnz     loc_1800152F3
0x1800151e6  mov     r10, [rsp+88h+arg_40]
0x1800151ee  test    r10, r10
0x1800151f1  jz      loc_1800152F3
0x1800151f7  mov     r14, [rsp+88h+arg_58]
0x1800151ff  mov     rax, [rsp+88h+arg_28]
0x180015207  mov     rcx, [rsp+88h+arg_20]
0x18001520f  mov     qword ptr [r14], 0
0x180015216  test    rax, rax
0x180015219  jz      short loc_18001521D
0x18001521b  mov     eax, [rax]
0x18001521d  test    eax, eax
0x18001521f  jz      short loc_18001523C
0x180015221  test    dword ptr [rcx+0Ch], 0F0000000h
0x180015228  jz      short loc_180015232
0x18001522a  dec     eax
0x18001522c  add     rcx, 18h
0x180015230  jmp     short loc_18001521D
0x180015232  mov     eax, 8021080Bh
0x180015237  jmp     loc_1800152F8
0x18001523c  mov     ecx, [rsp+88h+arg_38]
0x180015243  test    cl, 2
0x180015246  jz      short loc_180015252
0x180015248  mov     eax, 8021080Dh
0x18001524d  jmp     loc_1800152F8
0x180015252  cmp     [rsp+88h+arg_30], 3
0x18001525a  jz      short loc_180015266
0x18001525c  mov     eax, 8021080Ch
0x180015261  jmp     loc_1800152F8
0x180015266  mov     rax, [r10]
0x180015269  lea     r15, [rdi+28h]
0x18001526d  mov     [rsp+88h+var_48], r15
0x180015272  mov     r9d, ebp
0x180015275  mov     [rsp+88h+var_50], ecx
0x180015279  mov     r8, rbx
0x18001527c  mov     [rsp+88h+var_58], 3
0x180015284  mov     rdx, rsi
0x180015287  mov     rax, [rax+20h]
0x18001528b  mov     rcx, r10
0x18001528e  mov     [rsp+88h+var_60], 0
0x180015297  mov     [rsp+88h+var_68], 0
0x1800152a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a5  mov     esi, eax
0x1800152a7  test    eax, eax
0x1800152a9  js      short loc_1800152F8
0x1800152ab  mov     rdx, [r15]
0x1800152ae  lea     r8, IID_ISimpleTableController
0x1800152b5  lea     rcx, [rdi+30h]
0x1800152b9  call    cs:__imp_AtlComQIPtrAssign
0x1800152bf  cmp     qword ptr [rdi+30h], 0
0x1800152c4  jnz     short loc_1800152CD
0x1800152c6  mov     eax, 80004002h
0x1800152cb  jmp     short loc_1800152F8
0x1800152cd  lea     rdx, [rdi+8]
0x1800152d1  mov     rax, rdi
0x1800152d4  neg     rax
0x1800152d7  sbb     rcx, rcx
0x1800152da  and     rcx, rdx
0x1800152dd  mov     [r14], rcx
0x1800152e0  mov     rcx, rdi
0x1800152e3  mov     rax, [rdi]
0x1800152e6  mov     rax, [rax+8]
0x1800152ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ef  mov     eax, esi
0x1800152f1  jmp     short loc_1800152F8
0x1800152f3  mov     eax, 80070057h
0x1800152f8  add     rsp, 58h
0x1800152fc  pop     r15
0x1800152fe  pop     r14
0x180015300  pop     rdi
0x180015301  pop     rsi
0x180015302  pop     rbp
0x180015303  pop     rbx
0x180015304  retn
```
