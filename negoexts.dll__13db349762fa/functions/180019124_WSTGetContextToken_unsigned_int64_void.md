# WSTGetContextToken(unsigned __int64,void * *)

- ea: `0x180019124`
- end: `0x1800191f8`
- name: `?WSTGetContextToken@@YAJ_KPEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019600`

## callees

- `0x18000c700`
- `0x18000ec28`
- `0x180015a58`
- `0x180018ea0`
- `0x180019124`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTGetContextToken(unsigned __int64 a1, void **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  struct _NEGOEXTS_UMODE_CONTEXT *v6; // rdi
  struct _NEGOEXTS_UMODE_CONTEXT *v8; // [rsp+68h] [rbp+10h] BYREF

  v8 = 0;
  if ( a2 )
  {
    v5 = WSTReferenceUserModeContextByLsaHandle(a1, 0, &v8);
    v6 = v8;
    v4 = v5;
    if ( v5 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, void **))(*((_QWORD *)v8 + 6) + 48LL))(*((_QWORD *)v8 + 4), a2);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids, a1, v5);
    }
    if ( v6 )
      WSTDereferenceUserModeContext(v6);
  }
  else
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x180019124  push    rbx
0x180019126  push    rbp
0x180019127  push    rsi
0x180019128  push    rdi
0x180019129  sub     rsp, 38h
0x18001912d  mov     [rsp+58h+arg_8], 0
0x180019136  mov     rsi, rdx
0x180019139  mov     rbp, rcx
0x18001913c  test    rdx, rdx
0x18001913f  jnz     short loc_18001917C
0x180019141  mov     ebx, 0C000000Dh
0x180019146  mov     rcx, cs:WPP_GLOBAL_Control
0x18001914d  lea     rax, WPP_GLOBAL_Control
0x180019154  cmp     rcx, rax
0x180019157  jz      loc_1800191ED
0x18001915d  test    byte ptr [rcx+1Ch], 1
0x180019161  jz      loc_1800191ED
0x180019167  mov     rcx, [rcx+10h]
0x18001916b  lea     edx, [rsi+12h]
0x18001916e  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x180019175  call    WPP_SF_
0x18001917a  jmp     short loc_1800191ED
0x18001917c  lea     r8, [rsp+58h+arg_8]; struct _NEGOEXTS_UMODE_CONTEXT **
0x180019181  xor     edx, edx; unsigned __int8
0x180019183  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_NEGOEXTS_UMODE_CONTEXT * *)
0x180019188  mov     rdi, [rsp+58h+arg_8]
0x18001918d  mov     ebx, eax
0x18001918f  test    eax, eax
0x180019191  jns     short loc_1800191CA
0x180019193  mov     rcx, cs:WPP_GLOBAL_Control
0x18001919a  lea     rax, WPP_GLOBAL_Control
0x1800191a1  cmp     rcx, rax
0x1800191a4  jz      short loc_1800191E0
0x1800191a6  test    byte ptr [rcx+1Ch], 1
0x1800191aa  jz      short loc_1800191E0
0x1800191ac  mov     rcx, [rcx+10h]
0x1800191b0  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x1800191b7  mov     edx, 13h
0x1800191bc  mov     [rsp+58h+var_38], ebx
0x1800191c0  mov     r9, rbp
0x1800191c3  call    WPP_SF_qD
0x1800191c8  jmp     short loc_1800191E0
0x1800191ca  mov     rax, [rdi+30h]
0x1800191ce  mov     rdx, rsi
0x1800191d1  mov     rcx, [rdi+20h]
0x1800191d5  mov     rax, [rax+30h]
0x1800191d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191de  mov     ebx, eax
0x1800191e0  test    rdi, rdi
0x1800191e3  jz      short loc_1800191ED
0x1800191e5  mov     rcx, rdi; struct _NEGOEXTS_UMODE_CONTEXT *
0x1800191e8  call    ?WSTDereferenceUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x1800191ed  mov     eax, ebx
0x1800191ef  add     rsp, 38h
0x1800191f3  pop     rdi
0x1800191f4  pop     rsi
0x1800191f5  pop     rbp
0x1800191f6  pop     rbx
0x1800191f7  retn
```
