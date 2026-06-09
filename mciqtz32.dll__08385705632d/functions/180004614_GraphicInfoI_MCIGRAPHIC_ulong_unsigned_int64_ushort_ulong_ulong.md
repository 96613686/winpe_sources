# GraphicInfoI(_MCIGRAPHIC *,ulong,unsigned __int64,ushort *,ulong,ulong)

- ea: `0x180004614`
- end: `0x180004855`
- name: `?GraphicInfoI@@YAKPEAU_MCIGRAPHIC@@K_KPEAGKK@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *, int, void *, unsigned __int16 *, int cchBufferMax)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000485c`

## callees

- `0x180004614`
- `0x180007010`

## import_xrefs

- `USER32!LoadStringW` at `0x18000476a`
- `USER32!LoadStringW` at `0x18000480c`
- `USER32!LoadStringW` at `0x18000476a`
- `USER32!LoadStringW` at `0x18000480c`
- `ole32!CoTaskMemFree` at `0x180004739`
- `ole32!CoTaskMemFree` at `0x180004739`

## pseudocode

```c
__int64 __fastcall GraphicInfoI(
        struct _MCIGRAPHIC *a1,
        int a2,
        void *a3,
        unsigned __int16 *a4,
        unsigned int cchBufferMax)
{
  char v6; // bp
  unsigned int v7; // eax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rcx
  void *v11; // r10
  signed int v12; // ebx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  __int64 v15; // r8
  unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // rdx
  __int64 v19; // rdx
  unsigned __int16 *v20; // r9
  __int64 v21; // rax
  unsigned __int16 *v22; // r8
  unsigned __int16 *v23; // rcx
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  pv = a3;
  v6 = a2;
  if ( !a4 )
    return 268;
  v7 = a2 & 0xFFFFFFDC;
  if ( (a2 & 0xFFFFFFDC) == 0 )
    return 273;
  v8 = cchBufferMax;
  v9 = 0;
  switch ( v7 )
  {
    case 0x100u:
      if ( !LoadStringW(ghModule, 2u, a4, cchBufferMax) )
        v9 = 268;
      goto LABEL_43;
    case 0x200u:
      if ( a1 )
      {
        if ( cchBufferMax )
        {
          v19 = cchBufferMax;
          if ( cchBufferMax <= 0x7FFFFFFFuLL )
          {
            v20 = (unsigned __int16 *)*((_QWORD *)a1 + 8);
            v21 = 2147483646;
            v22 = a4;
            do
            {
              if ( !v21 )
                break;
              if ( !*v20 )
                break;
              *v22++ = *v20++;
              --v21;
              --v19;
            }
            while ( v19 );
            v23 = v22 - 1;
            if ( v19 )
              v23 = v22;
            v12 = v19 == 0 ? 0x8007007A : 0;
            *v23 = 0;
          }
          else
          {
            *a4 = 0;
            v12 = -2147024809;
          }
          goto LABEL_40;
        }
        return 268;
      }
      return 274;
    case 0x400u:
      LoadStringW(ghModule, 3u, a4, cchBufferMax);
      goto LABEL_43;
    case 0x4000u:
      v9 = 274;
      goto LABEL_43;
  }
  if ( v7 != 0x10000 )
  {
    v9 = 274;
    if ( v7 != 0x20000 )
      v9 = 284;
    goto LABEL_43;
  }
  if ( !a1 )
    return 274;
  v10 = *((_QWORD *)a1 + 22);
  if ( !v10 )
  {
LABEL_25:
    v9 = 346;
    goto LABEL_43;
  }
  if ( !cchBufferMax )
    return 268;
  pv = 0;
  (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 64LL))(v10, &pv);
  v11 = pv;
  if ( !pv )
    goto LABEL_25;
  if ( (unsigned int)v8 <= 0x7FFFFFFF )
  {
    v13 = 2147483646;
    v14 = (unsigned __int16 *)pv;
    v15 = v8;
    v16 = a4;
    do
    {
      if ( !v13 )
        break;
      if ( !*v14 )
        break;
      *v16++ = *v14++;
      --v13;
      --v15;
    }
    while ( v15 );
    v17 = v16 - 1;
    if ( v15 )
      v17 = v16;
    v12 = v15 == 0 ? 0x8007007A : 0;
    *v17 = 0;
  }
  else
  {
    v12 = -2147024809;
    *a4 = 0;
  }
  CoTaskMemFree(v11);
LABEL_40:
  v9 = (v12 >> 31) & 0x10C;
LABEL_43:
  if ( (v6 & 0x20) != 0 && !(_WORD)v9 )
  {
    v9 = 0;
    if ( (_DWORD)v8 )
      *a4 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180004614  mov     [rsp+arg_0], rbx
0x180004619  mov     [rsp+arg_8], rbp
0x18000461e  mov     [rsp+pv], r8
0x180004623  push    rsi
0x180004624  push    rdi
0x180004625  push    r14
0x180004627  sub     rsp, 20h
0x18000462b  xor     r14d, r14d
0x18000462e  mov     rsi, r9
0x180004631  mov     ebp, edx
0x180004633  test    r9, r9
0x180004636  jz      loc_18000483D
0x18000463c  mov     eax, edx
0x18000463e  and     eax, 0FFFFFFDCh
0x180004641  jz      loc_180004836
0x180004647  mov     edi, [rsp+38h+cchBufferMax]
0x18000464b  mov     ebx, r14d
0x18000464e  cmp     eax, 100h
0x180004653  jz      loc_1800047FA
0x180004659  cmp     eax, 200h
0x18000465e  jz      loc_180004775
0x180004664  cmp     eax, 400h
0x180004669  jz      loc_180004758
0x18000466f  cmp     eax, 4000h
0x180004674  jz      loc_18000474E
0x18000467a  cmp     eax, 10000h
0x18000467f  jz      short loc_180004696
0x180004681  mov     ebx, 112h
0x180004686  cmp     eax, 20000h
0x18000468b  lea     ecx, [rbx+0Ah]
0x18000468e  cmovnz  ebx, ecx
0x180004691  jmp     loc_18000481C
0x180004696  test    rcx, rcx
0x180004699  jz      loc_18000477A
0x18000469f  mov     rcx, [rcx+0B0h]
0x1800046a6  test    rcx, rcx
0x1800046a9  jz      loc_180004744
0x1800046af  test    edi, edi
0x1800046b1  jz      loc_18000483D
0x1800046b7  mov     [rsp+38h+pv], r14
0x1800046bc  lea     rdx, [rsp+38h+pv]
0x1800046c1  mov     rax, [rcx]
0x1800046c4  mov     rax, [rax+40h]
0x1800046c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046cd  mov     r10, [rsp+38h+pv]
0x1800046d2  test    r10, r10
0x1800046d5  jz      short loc_180004744
0x1800046d7  cmp     edi, 7FFFFFFFh
0x1800046dd  jbe     short loc_1800046EA
0x1800046df  mov     ebx, 80070057h
0x1800046e4  mov     [rsi], r14w
0x1800046e8  jmp     short loc_180004736
0x1800046ea  mov     eax, 7FFFFFFEh
0x1800046ef  mov     rcx, r10
0x1800046f2  mov     r8, rdi
0x1800046f5  mov     r9, rsi
0x1800046f8  test    rax, rax
0x1800046fb  jz      short loc_18000471A
0x1800046fd  movzx   edx, word ptr [rcx]
0x180004700  test    dx, dx
0x180004703  jz      short loc_18000471A
0x180004705  mov     [r9], dx
0x180004709  add     rcx, 2
0x18000470d  add     r9, 2
0x180004711  dec     rax
0x180004714  sub     r8, 1
0x180004718  jnz     short loc_1800046F8
0x18000471a  test    r8, r8
0x18000471d  lea     rdx, [r9-2]
0x180004721  cmovnz  rdx, r9
0x180004725  neg     r8
0x180004728  sbb     ebx, ebx
0x18000472a  not     ebx
0x18000472c  and     ebx, 8007007Ah
0x180004732  mov     [rdx], r14w
0x180004736  mov     rcx, r10; pv
0x180004739  call    cs:__imp_CoTaskMemFree
0x18000473f  jmp     loc_1800047EE
0x180004744  mov     ebx, 15Ah
0x180004749  jmp     loc_18000481C
0x18000474e  mov     ebx, 112h
0x180004753  jmp     loc_18000481C
0x180004758  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000475f  mov     r9d, edi; cchBufferMax
0x180004762  mov     r8, rsi; lpBuffer
0x180004765  mov     edx, 3; uID
0x18000476a  call    cs:__imp_LoadStringW
0x180004770  jmp     loc_18000481C
0x180004775  test    rcx, rcx
0x180004778  jnz     short loc_180004784
0x18000477a  mov     eax, 112h
0x18000477f  jmp     loc_180004842
0x180004784  test    edi, edi
0x180004786  jz      loc_18000483D
0x18000478c  mov     rdx, rdi
0x18000478f  cmp     rdi, 7FFFFFFFh
0x180004796  jbe     short loc_1800047A3
0x180004798  mov     [r9], r14w
0x18000479c  mov     ebx, 80070057h
0x1800047a1  jmp     short loc_1800047EE
0x1800047a3  mov     r9, [rcx+40h]
0x1800047a7  mov     eax, 7FFFFFFEh
0x1800047ac  mov     r8, rsi
0x1800047af  test    rax, rax
0x1800047b2  jz      short loc_1800047D2
0x1800047b4  movzx   ecx, word ptr [r9]
0x1800047b8  test    cx, cx
0x1800047bb  jz      short loc_1800047D2
0x1800047bd  mov     [r8], cx
0x1800047c1  add     r9, 2
0x1800047c5  add     r8, 2
0x1800047c9  dec     rax
0x1800047cc  sub     rdx, 1
0x1800047d0  jnz     short loc_1800047AF
0x1800047d2  test    rdx, rdx
0x1800047d5  lea     rcx, [r8-2]
0x1800047d9  cmovnz  rcx, r8
0x1800047dd  neg     rdx
0x1800047e0  sbb     ebx, ebx
0x1800047e2  not     ebx
0x1800047e4  and     ebx, 8007007Ah
0x1800047ea  mov     [rcx], r14w
0x1800047ee  sar     ebx, 1Fh
0x1800047f1  mov     ecx, 10Ch
0x1800047f6  and     ebx, ecx
0x1800047f8  jmp     short loc_18000481C
0x1800047fa  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x180004801  mov     r9d, edi; cchBufferMax
0x180004804  mov     r8, rsi; lpBuffer
0x180004807  mov     edx, 2; uID
0x18000480c  call    cs:__imp_LoadStringW
0x180004812  test    eax, eax
0x180004814  mov     ecx, 10Ch
0x180004819  cmovz   ebx, ecx
0x18000481c  test    bpl, 20h
0x180004820  jz      short loc_180004832
0x180004822  test    bx, bx
0x180004825  jnz     short loc_180004832
0x180004827  mov     ebx, r14d
0x18000482a  test    edi, edi
0x18000482c  jz      short loc_180004832
0x18000482e  mov     [rsi], r14w
0x180004832  mov     eax, ebx
0x180004834  jmp     short loc_180004842
0x180004836  mov     eax, 111h
0x18000483b  jmp     short loc_180004842
0x18000483d  mov     eax, 10Ch
0x180004842  mov     rbx, [rsp+38h+arg_0]
0x180004847  mov     rbp, [rsp+38h+arg_8]
0x18000484c  add     rsp, 20h
0x180004850  pop     r14
0x180004852  pop     rdi
0x180004853  pop     rsi
0x180004854  retn
```
