# CDSLink::SetDirectSound(IDirectSound *,IDirectSoundBuffer *)

- ea: `0x1800101c0`
- end: `0x180010445`
- name: `?SetDirectSound@CDSLink@@UEAAJPEAUIDirectSound@@PEAUIDirectSoundBuffer@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, struct IDirectSound *, struct IDirectSoundBuffer *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800014f0`
- `0x18000fc80`
- `0x1800101c0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010239`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010416`

## pseudocode

```c
__int64 __fastcall CDSLink::SetDirectSound(CDSLink *this, struct IDirectSound *a2, struct IDirectSoundBuffer *a3)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  CDSLink *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  int v15; // [rsp+30h] [rbp-48h] BYREF
  __int128 v16; // [rsp+38h] [rbp-40h] BYREF
  __int16 v17; // [rsp+48h] [rbp-30h]
  int v18; // [rsp+50h] [rbp-28h] BYREF
  __int128 v19; // [rsp+54h] [rbp-24h]

  if ( a2 && (!a2->lpVtbl || !a2->lpVtbl->QueryInterface) || a3 && (!a3->lpVtbl || !a3->lpVtbl->QueryInterface) )
    return 2147500035LL;
  if ( *((_DWORD *)this + 56) )
    return 2289570098LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v7 = *((_QWORD *)this + 16);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 16) = 0;
  }
  v8 = *((_QWORD *)this + 13);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  *((_QWORD *)this + 13) = a2;
  if ( !a2 )
    goto LABEL_35;
  ((void (__fastcall *)(struct IDirectSound *))a2->lpVtbl->AddRef)(a2);
  v9 = *((_QWORD *)this + 3);
  if ( !v9 )
  {
    v13 = -2005397199;
    goto LABEL_32;
  }
  v15 = 18;
  if ( (*(int (__fastcall **)(__int64, char *, int *))(*(_QWORD *)v9 + 144LL))(v9, (char *)this + 84, &v15) < 0
    || !(unsigned int)CDSLink::IsValidFormat(v10, (const struct tWAVEFORMATEX *)((char *)this + 84)) )
  {
    goto LABEL_29;
  }
  *((_QWORD *)this + 16) = a3;
  if ( !a3 )
    goto LABEL_35;
  ((void (__fastcall *)(struct IDirectSoundBuffer *))a3->lpVtbl->AddRef)(a3);
  v11 = *((_QWORD *)this + 16);
  v17 = 0;
  v16 = 0;
  if ( (*(int (__fastcall **)(__int64, __int128 *, __int64, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, &v16, 18, 0) < 0 )
    goto LABEL_29;
  if ( (_QWORD)v16 != *(_QWORD *)((char *)this + 84)
    || WORD6(v16) != *((_WORD *)this + 48)
    || DWORD2(v16) != *((_DWORD *)this + 23)
    || HIWORD(v16) != *((_WORD *)this + 49) )
  {
    v13 = -2005397188;
    goto LABEL_32;
  }
  v12 = *((_QWORD *)this + 16);
  v18 = 20;
  v19 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 24LL))(v12, &v18) < 0 )
  {
LABEL_29:
    v13 = -2147418113;
    goto LABEL_32;
  }
  if ( (v19 & 3) != 0 )
  {
    v13 = -2005397189;
LABEL_32:
    v14 = *((_QWORD *)this + 16);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 16) = 0;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 16LL))(*((_QWORD *)this + 13));
    *((_QWORD *)this + 13) = 0;
    goto LABEL_36;
  }
  if ( DWORD1(v19) < *((_DWORD *)this + 23) )
  {
    v13 = -2005397244;
    goto LABEL_32;
  }
LABEL_35:
  v13 = 0;
LABEL_36:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  return v13;
}

```

## disassembly

```asm
0x1800101c0  mov     [rsp+arg_10], rbx
0x1800101c5  mov     [rsp+arg_18], rsi
0x1800101ca  push    rdi
0x1800101cb  sub     rsp, 70h
0x1800101cf  mov     rax, cs:__security_cookie
0x1800101d6  xor     rax, rsp
0x1800101d9  mov     [rsp+78h+var_10], rax
0x1800101de  mov     rsi, r8
0x1800101e1  mov     rbx, rdx
0x1800101e4  mov     rdi, rcx
0x1800101e7  test    rdx, rdx
0x1800101ea  jz      short loc_1800101FA
0x1800101ec  mov     rax, [rdx]
0x1800101ef  test    rax, rax
0x1800101f2  jz      short loc_18001020D
0x1800101f4  cmp     qword ptr [rax], 0
0x1800101f8  jz      short loc_18001020D
0x1800101fa  test    rsi, rsi
0x1800101fd  jz      short loc_180010217
0x1800101ff  mov     rax, [r8]
0x180010202  test    rax, rax
0x180010205  jz      short loc_18001020D
0x180010207  cmp     qword ptr [rax], 0
0x18001020b  jnz     short loc_180010217
0x18001020d  mov     eax, 80004003h
0x180010212  jmp     loc_180010426
0x180010217  cmp     dword ptr [rcx+0E0h], 0
0x18001021e  jz      short loc_18001022A
0x180010220  mov     eax, 88781132h
0x180010225  jmp     loc_180010426
0x18001022a  add     rcx, 88h; lpCriticalSection
0x180010231  mov     [rsp+78h+arg_8], rbp
0x180010239  call    cs:__imp_EnterCriticalSection
0x18001023f  mov     rcx, [rdi+80h]
0x180010246  test    rcx, rcx
0x180010249  jz      short loc_180010262
0x18001024b  mov     rax, [rcx]
0x18001024e  mov     rax, [rax+10h]
0x180010252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010257  mov     qword ptr [rdi+80h], 0
0x180010262  mov     rcx, [rdi+68h]
0x180010266  test    rcx, rcx
0x180010269  jz      short loc_180010277
0x18001026b  mov     rax, [rcx]
0x18001026e  mov     rax, [rax+10h]
0x180010272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010277  mov     [rdi+68h], rbx
0x18001027b  test    rbx, rbx
0x18001027e  jz      loc_18001040D
0x180010284  mov     rax, [rbx]
0x180010287  mov     rcx, rbx
0x18001028a  mov     rax, [rax+8]
0x18001028e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010293  mov     rcx, [rdi+18h]
0x180010297  test    rcx, rcx
0x18001029a  jz      loc_1800103CB
0x1800102a0  mov     [rsp+78h+var_48], 12h
0x1800102a8  lea     r8, [rsp+78h+var_48]
0x1800102ad  mov     rax, [rcx]
0x1800102b0  lea     rdx, [rdi+54h]
0x1800102b4  mov     rax, [rax+90h]
0x1800102bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102c0  test    eax, eax
0x1800102c2  js      loc_1800103BD
0x1800102c8  lea     rdx, [rdi+54h]; struct tWAVEFORMATEX *
0x1800102cc  call    ?IsValidFormat@CDSLink@@AEAAHPEBUtWAVEFORMATEX@@@Z; CDSLink::IsValidFormat(tWAVEFORMATEX const *)
0x1800102d1  test    eax, eax
0x1800102d3  jz      loc_1800103BD
0x1800102d9  mov     [rdi+80h], rsi
0x1800102e0  test    rsi, rsi
0x1800102e3  jz      loc_18001040D
0x1800102e9  mov     rax, [rsi]
0x1800102ec  mov     rcx, rsi
0x1800102ef  mov     rax, [rax+8]
0x1800102f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102f8  mov     rcx, [rdi+80h]
0x1800102ff  lea     rdx, [rsp+78h+var_40]
0x180010304  xor     eax, eax
0x180010306  xorps   xmm0, xmm0
0x180010309  mov     [rsp+78h+var_30], ax
0x18001030e  xor     r9d, r9d
0x180010311  movups  [rsp+78h+var_40], xmm0
0x180010316  mov     rax, [rcx]
0x180010319  mov     r8d, 12h
0x18001031f  mov     rax, [rax+28h]
0x180010323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010328  test    eax, eax
0x18001032a  js      loc_1800103BD
0x180010330  movzx   eax, word ptr [rdi+54h]
0x180010334  cmp     word ptr [rsp+78h+var_40], ax
0x180010339  jnz     loc_1800103C4
0x18001033f  movzx   eax, word ptr [rdi+56h]
0x180010343  cmp     word ptr [rsp+78h+var_40+2], ax
0x180010348  jnz     short loc_1800103C4
0x18001034a  mov     eax, [rdi+58h]
0x18001034d  cmp     dword ptr [rsp+78h+var_40+4], eax
0x180010351  jnz     short loc_1800103C4
0x180010353  movzx   eax, word ptr [rdi+60h]
0x180010357  cmp     word ptr [rsp+78h+var_40+0Ch], ax
0x18001035c  jnz     short loc_1800103C4
0x18001035e  mov     eax, [rdi+5Ch]
0x180010361  cmp     dword ptr [rsp+78h+var_40+8], eax
0x180010365  jnz     short loc_1800103C4
0x180010367  movzx   eax, word ptr [rdi+62h]
0x18001036b  cmp     word ptr [rsp+78h+var_40+0Eh], ax
0x180010370  jnz     short loc_1800103C4
0x180010372  mov     rcx, [rdi+80h]
0x180010379  lea     rdx, [rsp+78h+var_28]
0x18001037e  xorps   xmm0, xmm0
0x180010381  mov     [rsp+78h+var_28], 14h
0x180010389  movdqu  [rsp+78h+var_24], xmm0
0x18001038f  mov     rax, [rcx]
0x180010392  mov     rax, [rax+18h]
0x180010396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001039b  test    eax, eax
0x18001039d  js      short loc_1800103BD
0x18001039f  test    byte ptr [rsp+78h+var_24], 3
0x1800103a4  jz      short loc_1800103AD
0x1800103a6  mov     ebx, 8878113Bh
0x1800103ab  jmp     short loc_1800103D0
0x1800103ad  mov     eax, [rdi+5Ch]
0x1800103b0  cmp     dword ptr [rsp+78h+var_24+4], eax
0x1800103b4  jnb     short loc_18001040D
0x1800103b6  mov     ebx, 88781104h
0x1800103bb  jmp     short loc_1800103D0
0x1800103bd  mov     ebx, 8000FFFFh
0x1800103c2  jmp     short loc_1800103D0
0x1800103c4  mov     ebx, 8878113Ch
0x1800103c9  jmp     short loc_1800103D0
0x1800103cb  mov     ebx, 88781131h
0x1800103d0  mov     rcx, [rdi+80h]
0x1800103d7  test    rcx, rcx
0x1800103da  jz      short loc_1800103F3
0x1800103dc  mov     rax, [rcx]
0x1800103df  mov     rax, [rax+10h]
0x1800103e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e8  mov     qword ptr [rdi+80h], 0
0x1800103f3  mov     rcx, [rdi+68h]
0x1800103f7  mov     rax, [rcx]
0x1800103fa  mov     rax, [rax+10h]
0x1800103fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010403  mov     qword ptr [rdi+68h], 0
0x18001040b  jmp     short loc_18001040F
0x18001040d  xor     ebx, ebx
0x18001040f  lea     rcx, [rdi+88h]; lpCriticalSection
0x180010416  call    cs:__imp_LeaveCriticalSection
0x18001041c  mov     rbp, [rsp+78h+arg_8]
0x180010424  mov     eax, ebx
0x180010426  mov     rcx, [rsp+78h+var_10]
0x18001042b  xor     rcx, rsp; StackCookie
0x18001042e  call    __security_check_cookie
0x180010433  lea     r11, [rsp+78h+var_8]
0x180010438  mov     rbx, [r11+20h]
0x18001043c  mov     rsi, [r11+28h]
0x180010440  mov     rsp, r11
0x180010443  pop     rdi
0x180010444  retn
```
