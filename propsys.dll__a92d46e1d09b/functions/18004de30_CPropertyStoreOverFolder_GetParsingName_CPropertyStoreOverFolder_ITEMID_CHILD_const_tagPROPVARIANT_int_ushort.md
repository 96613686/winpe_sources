# CPropertyStoreOverFolder::_GetParsingName(CPropertyStoreOverFolder *,_ITEMID_CHILD const *,tagPROPVARIANT *,int,ushort * *)

- ea: `0x18004de30`
- end: `0x18004e018`
- name: `?_GetParsingName@CPropertyStoreOverFolder@@CAJPEAV1@PEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `488`
- prototype: `static int(struct CPropertyStoreOverFolder *, const struct _ITEMID_CHILD *, struct tagPROPVARIANT *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004de30`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dfc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dfc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dfa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dfa0`
- `SHCORE!__imp_StrRetToStrW` at `0x18004df50`
- `SHCORE!__imp_StrRetToStrW` at `0x18004df50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyStoreOverFolder::_GetParsingName(
        struct CPropertyStoreOverFolder *a1,
        const ITEMIDLIST *a2,
        struct tagPROPVARIANT *a3,
        __int64 a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rdx
  HRESULT v10; // ebx
  __int64 v11; // rcx
  const wchar_t *v12; // r9
  __int64 v13; // r8
  unsigned __int16 *v14; // rax
  __int64 v15; // r10
  wchar_t v16; // r11
  __int64 v17; // r9
  unsigned __int16 *v18; // rcx
  __int64 v19; // rbx
  __int64 v21; // rsi
  unsigned __int16 *v22; // rax
  STRRET pstr; // [rsp+50h] [rbp-158h] BYREF

  v8 = 0;
  if ( is_mul_ok(0x14u, 2u) )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(0x28u);
    v10 = v8 == 0 ? 0x8007000E : 0;
    v9 = v8;
  }
  else
  {
    v9 = 0;
    v10 = -2147024362;
  }
  if ( v10 >= 0 )
  {
    if ( v9 )
    {
      v11 = 19;
      v12 = L"PropStoreOverFolder";
      v13 = 20;
      v14 = v9;
      v15 = 0;
      do
      {
        if ( !v11 )
          break;
        v16 = *v12;
        if ( !*v12 )
          break;
        ++v12;
        *v14++ = v16;
        --v11;
        ++v15;
        --v13;
      }
      while ( v13 );
      v17 = v15 - 1;
      if ( v13 )
        v17 = v15;
      v18 = v14 - 1;
      if ( v13 )
        v18 = v14;
      *v18 = 0;
      if ( v13 )
      {
        v21 = 20 - v17;
        if ( v17 != 20 && v17 != 19 && (unsigned __int64)(2 * v21) > 2 )
          memset_0(&v9[v17 + 1], 0, 2 * v21 - 2);
      }
    }
    else
    {
      MEMORY[0] = 0;
    }
    v19 = *((_QWORD *)a1 + 7);
    a3->hVal.QuadPart = 0;
    memset_0(&pstr, 0, sizeof(pstr));
    v10 = (*(__int64 (__fastcall **)(__int64, const ITEMIDLIST *, __int64, STRRET *))(*(_QWORD *)v19 + 88LL))(
            v19,
            a2,
            32769,
            &pstr);
    if ( v10 >= 0 )
      v10 = StrRetToStrW(&pstr, a2, &a3->bstrVal);
    if ( v10 >= 0 )
    {
      a3->vt = 31;
      if ( a5 )
      {
        v22 = v8;
        v8 = 0;
        *a5 = v22;
      }
    }
  }
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004de30  mov     [rsp+arg_18], rbx
0x18004de35  push    rbp
0x18004de36  push    rsi
0x18004de37  push    rdi
0x18004de38  push    r12
0x18004de3a  push    r13
0x18004de3c  push    r14
0x18004de3e  push    r15
0x18004de40  sub     rsp, 170h
0x18004de47  mov     rax, cs:__security_cookie
0x18004de4e  xor     rax, rsp
0x18004de51  mov     [rsp+1A8h+var_48], rax
0x18004de59  mov     r15, r8
0x18004de5c  mov     rbp, rdx
0x18004de5f  mov     r13, rcx
0x18004de62  mov     r14, [rsp+1A8h+arg_20]
0x18004de6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004de6e  mov     [rsp+1A8h+var_170], rax
0x18004de73  mov     [rsp+1A8h+var_168], rax
0x18004de78  xor     r12d, r12d
0x18004de7b  mov     edi, r12d
0x18004de7e  mov     [rsp+1A8h+var_178], r12
0x18004de83  lea     esi, [rax+15h]
0x18004de86  lea     eax, [rsi-12h]
0x18004de89  mul     rsi
0x18004de8c  test    rdx, rdx
0x18004de8f  jz      loc_18004DF9D
0x18004de95  mov     edx, r12d
0x18004de98  mov     ebx, 80070216h
0x18004de9d  test    ebx, ebx
0x18004de9f  js      loc_18004DF6B
0x18004dea5  test    rdx, rdx
0x18004dea8  jz      loc_18004E000
0x18004deae  mov     ecx, 13h
0x18004deb3  lea     r9, aPropstoreoverf_0; "PropStoreOverFolder"
0x18004deba  mov     r8, rsi
0x18004debd  mov     rax, rdx
0x18004dec0  mov     r10, r12
0x18004dec3  test    rcx, rcx
0x18004dec6  jz      short loc_18004DEEA
0x18004dec8  movzx   r11d, word ptr [r9]
0x18004decc  test    r11w, r11w
0x18004ded0  jz      short loc_18004DEEA
0x18004ded2  add     r9, 2
0x18004ded6  mov     [rax], r11w
0x18004deda  add     rax, 2
0x18004dede  dec     rcx
0x18004dee1  inc     r10
0x18004dee4  sub     r8, 1
0x18004dee8  jnz     short loc_18004DEC3
0x18004deea  lea     r9, [r10-1]
0x18004deee  test    r8, r8
0x18004def1  cmovnz  r9, r10
0x18004def5  lea     rcx, [rax-2]
0x18004def9  cmovnz  rcx, rax
0x18004defd  mov     [rcx], r12w
0x18004df01  jnz     loc_18004DFCE
0x18004df07  mov     rbx, [r13+38h]
0x18004df0b  mov     [r15+8], r12
0x18004df0f  xor     edx, edx; Val
0x18004df11  mov     r8d, 110h; Size
0x18004df17  lea     rcx, [rsp+1A8h+pstr]; void *
0x18004df1c  call    memset_0
0x18004df21  mov     rax, [rbx]
0x18004df24  lea     r9, [rsp+1A8h+pstr]
0x18004df29  mov     r8d, 8001h
0x18004df2f  mov     rdx, rbp
0x18004df32  mov     rcx, rbx
0x18004df35  mov     rax, [rax+58h]
0x18004df39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df3e  mov     ebx, eax
0x18004df40  test    eax, eax
0x18004df42  js      short loc_18004DF58
0x18004df44  lea     r8, [r15+8]; ppsz
0x18004df48  mov     rdx, rbp; pidl
0x18004df4b  lea     rcx, [rsp+1A8h+pstr]; pstr
0x18004df50  call    cs:__imp_StrRetToStrW
0x18004df56  mov     ebx, eax
0x18004df58  test    ebx, ebx
0x18004df5a  js      short loc_18004DF6B
0x18004df5c  mov     word ptr [r15], 1Fh
0x18004df62  test    r14, r14
0x18004df65  jnz     loc_18004E009
0x18004df6b  test    rdi, rdi
0x18004df6e  jnz     short loc_18004DFC3
0x18004df70  mov     eax, ebx
0x18004df72  mov     rcx, [rsp+1A8h+var_48]
0x18004df7a  xor     rcx, rsp; StackCookie
0x18004df7d  call    __security_check_cookie
0x18004df82  mov     rbx, [rsp+1A8h+arg_18]
0x18004df8a  add     rsp, 170h
0x18004df91  pop     r15
0x18004df93  pop     r14
0x18004df95  pop     r13
0x18004df97  pop     r12
0x18004df99  pop     rdi
0x18004df9a  pop     rsi
0x18004df9b  pop     rbp
0x18004df9c  retn
0x18004df9d  mov     rcx, rax; cb
0x18004dfa0  call    cs:__imp_CoTaskMemAlloc
0x18004dfa6  mov     rdi, rax
0x18004dfa9  mov     [rsp+1A8h+var_178], rax
0x18004dfae  neg     rax
0x18004dfb1  sbb     ebx, ebx
0x18004dfb3  not     ebx
0x18004dfb5  and     ebx, 8007000Eh
0x18004dfbb  mov     rdx, rdi
0x18004dfbe  jmp     loc_18004DE9D
0x18004dfc3  mov     rcx, rdi; pv
0x18004dfc6  call    cs:__imp_CoTaskMemFree
0x18004dfcc  jmp     short loc_18004DF70
0x18004dfce  sub     rsi, r9
0x18004dfd1  cmp     rsi, 1
0x18004dfd5  jbe     loc_18004DF07
0x18004dfdb  lea     r8, [rsi+rsi]
0x18004dfdf  cmp     r8, 2
0x18004dfe3  jbe     loc_18004DF07
0x18004dfe9  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18004dfed  inc     r9
0x18004dff0  lea     rcx, [rdx+r9*2]; void *
0x18004dff4  xor     edx, edx; Val
0x18004dff6  call    memset_0
0x18004dffb  jmp     loc_18004DF07
0x18004e000  mov     [rdx], r12w
0x18004e004  jmp     loc_18004DF07
0x18004e009  mov     rax, rdi
0x18004e00c  mov     rdi, r12
0x18004e00f  mov     [r14], rax
0x18004e012  jmp     loc_18004DF6B
```
