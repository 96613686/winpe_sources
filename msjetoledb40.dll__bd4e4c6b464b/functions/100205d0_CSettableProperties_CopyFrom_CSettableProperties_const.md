# CSettableProperties::CopyFrom(CSettableProperties const &)

- ea: `0x100205d0`
- end: `0x100207c1`
- name: `?CopyFrom@CSettableProperties@@QAEJABV1@@Z`
- size: `497`
- prototype: `int __thiscall(CSettableProperties *__hidden this, const struct CSettableProperties *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x100153e0`
- `0x1001a970`
- `0x1001af60`
- `0x1001ebc0`
- `0x10028340`

## callees

- `0x1001c6d0`
- `0x1001f270`
- `0x100205d0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`
- `0x1004d8cb`

## import_xrefs

- `OLEAUT32!__imp__VariantCopy@8` at `0x100206f1`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100206f1`

## pseudocode

```c
unsigned int __thiscall CSettableProperties::CopyFrom(CSettableProperties *this, const struct CSettableProperties *a2)
{
  CSettableProperties *v2; // edx
  const struct CSettableProperties *v3; // edi
  unsigned int result; // eax
  int v5; // edi
  int v6; // ecx
  int v7; // esi
  unsigned int v8; // edi
  int v9; // eax
  bool v10; // cf
  size_t v11; // eax
  unsigned int *v12; // eax
  _DWORD *v13; // edi
  unsigned int v14; // eax
  int v15; // edx
  int v16; // edi
  HRESULT v17; // eax
  void (__thiscall ***v18)(_DWORD, int); // eax
  int v20; // [esp-24h] [ebp-30h]
  int v21; // [esp-20h] [ebp-2Ch]
  unsigned int v22; // [esp-1Ch] [ebp-28h]
  unsigned int v23; // [esp-1Ch] [ebp-28h]
  unsigned int v24; // [esp-18h] [ebp-24h]
  int v25; // [esp-14h] [ebp-20h]
  _DWORD *v26; // [esp-14h] [ebp-20h]

  v2 = this;
  v3 = a2;
  result = 0;
  if ( a2 != this )
  {
    v24 = 0;
    while ( 1 )
    {
      v5 = *((_DWORD *)v3 + result + 2);
      v6 = 0;
      v7 = *((_DWORD *)v2 + result + 2);
      v20 = v5;
      v21 = *(_DWORD *)(v5 + 16);
      if ( v5 == v7 )
        goto LABEL_26;
      if ( *(_DWORD *)(v7 + 16) )
        JoltProperties::FreeMemory((JoltProperties *)v7);
      v8 = *(_DWORD *)(v5 + 8);
      v22 = v8;
      v9 = 48 * v8;
      *(_DWORD *)(v7 + 12) = v8;
      *(_DWORD *)(v7 + 8) = v8;
      if ( !is_mul_ok(0x30u, v8) )
        v9 = -1;
      v10 = __CFADD__(v9, 4);
      v11 = v9 + 4;
      if ( v10 )
        v11 = -1;
      v12 = (unsigned int *)operator new(v11);
      if ( v12 )
      {
        *v12 = v8;
        v13 = v12 + 1;
        `eh vector constructor iterator'(
          v12 + 1,
          0x30u,
          v22,
          (void (__thiscall *)(void *))JoltProperty::JoltProperty,
          (void (__thiscall *)(void *))JoltColumnProperty::~JoltColumnProperty);
      }
      else
      {
        v13 = 0;
      }
      *(_DWORD *)(v7 + 16) = v13;
      if ( !v13 )
        break;
      v14 = 0;
      v23 = 0;
      if ( *(_DWORD *)(v7 + 8) )
      {
        v15 = v21;
        while ( 1 )
        {
          v16 = 48 * v14 + *(_DWORD *)(v7 + 16);
          v26 = (_DWORD *)(48 * v14 + v15);
          *(_DWORD *)(v16 + 8) = v26[2];
          v17 = VariantCopy((VARIANTARG *)(v16 + 16), (const VARIANTARG *)(48 * v14 + v15 + 16));
          v6 = v17;
          if ( v17 < 0 )
            break;
          *(_DWORD *)(v16 + 32) = v26[8];
          *(_DWORD *)(v16 + 40) = v26[10];
          v15 = v21;
          *(_DWORD *)(v16 + 36) = v26[9];
          v14 = v23 + 1;
          v23 = v14;
          if ( v14 >= *(_DWORD *)(v7 + 8) )
          {
            result = v24;
            *(_OWORD *)(v7 + 20) = *(_OWORD *)(v20 + 20);
            goto LABEL_27;
          }
        }
        v25 = v17;
        goto LABEL_21;
      }
      v6 = 0;
      result = v24;
      *(_OWORD *)(v7 + 20) = *(_OWORD *)(v20 + 20);
LABEL_27:
      v2 = this;
      ++result;
      v3 = a2;
      v24 = result;
      if ( result >= 2 )
        return v6;
    }
    v25 = -2147024882;
LABEL_21:
    v18 = *(void (__thiscall ****)(_DWORD, int))(v7 + 16);
    if ( v18 )
    {
      if ( *(v18 - 1) )
        (**v18)(v18, 3);
      else
        operator delete(v18 - 1);
    }
    v6 = v25;
    result = v24;
    *(_DWORD *)(v7 + 16) = 0;
    *(_DWORD *)(v7 + 8) = 0;
    *(_DWORD *)(v7 + 12) = 0;
LABEL_26:
    if ( v6 < 0 )
      return v6;
    goto LABEL_27;
  }
  return result;
}

```

## disassembly

```asm
0x100205d0  mov     edi, edi
0x100205d2  push    ebx
0x100205d3  mov     ebx, esp
0x100205d5  sub     esp, 8
0x100205d8  and     esp, 0FFFFFFF8h
0x100205db  add     esp, 4
0x100205de  push    ebp
0x100205df  mov     ebp, [ebx+4]
0x100205e2  mov     [esp+0Ch+var_8], ebp
0x100205e6  mov     ebp, esp
0x100205e8  push    0FFFFFFFFh
0x100205ea  push    offset loc_1004E7E0
0x100205ef  mov     eax, large fs:0
0x100205f5  push    eax
0x100205f6  push    ebx
0x100205f7  sub     esp, 20h
0x100205fa  push    esi
0x100205fb  push    edi
0x100205fc  mov     eax, ___security_cookie
0x10020601  xor     eax, ebp
0x10020603  push    eax
0x10020604  lea     eax, [ebp-0Ch]
0x10020607  mov     large fs:0, eax
0x1002060d  mov     edx, ecx
0x1002060f  mov     [ebp-28h], edx
0x10020612  mov     edi, [ebx+8]
0x10020615  xor     eax, eax
0x10020617  cmp     edi, edx
0x10020619  jz      loc_10020799
0x1002061f  mov     [ebp-18h], eax
0x10020622  mov     edi, [edi+eax*4+8]
0x10020626  xor     ecx, ecx
0x10020628  mov     esi, [edx+eax*4+8]
0x1002062c  mov     [ebp-24h], edi
0x1002062f  mov     edx, [edi+10h]
0x10020632  mov     [ebp-20h], edx
0x10020635  cmp     edi, esi
0x10020637  jz      loc_10020780
0x1002063d  cmp     [esi+10h], ecx
0x10020640  jz      short loc_10020649
0x10020642  mov     ecx, esi; this
0x10020644  call    ?FreeMemory@JoltProperties@@QAEJXZ; JoltProperties::FreeMemory(void)
0x10020649  mov     edi, [edi+8]
0x1002064c  mov     ecx, 30h ; '0'
0x10020651  mov     eax, edi
0x10020653  mov     [ebp-1Ch], edi
0x10020656  mul     ecx
0x10020658  mov     ecx, 0FFFFFFFFh
0x1002065d  mov     [esi+0Ch], edi
0x10020660  mov     [esi+8], edi
0x10020663  cmovb   eax, ecx
0x10020666  add     eax, 4
0x10020669  cmovb   eax, ecx
0x1002066c  push    eax; Size
0x1002066d  call    ??2@YAPAXI@Z; operator new(uint)
0x10020672  add     esp, 4
0x10020675  mov     [ebp-2Ch], eax
0x10020678  mov     dword ptr [ebp-4], 0
0x1002067f  test    eax, eax
0x10020681  jz      short loc_1002069F
0x10020683  push    offset ??1JoltColumnProperty@@UAE@XZ; void (__thiscall *)(void *)
0x10020688  push    offset ??0JoltProperty@@QAE@XZ; void (__thiscall *)(void *)
0x1002068d  push    dword ptr [ebp-1Ch]; unsigned int
0x10020690  mov     [eax], edi
0x10020692  lea     edi, [eax+4]
0x10020695  push    30h ; '0'; unsigned int
0x10020697  push    edi; void *
0x10020698  call    ??_L@YGXPAXIIP6EX0@Z1@Z; `eh vector constructor iterator'(void *,uint,uint,void (*)(void *),void (*)(void *))
0x1002069d  jmp     short loc_100206A1
0x1002069f  xor     edi, edi
0x100206a1  mov     dword ptr [ebp-4], 0FFFFFFFFh
0x100206a8  mov     [esi+10h], edi
0x100206ab  test    edi, edi
0x100206ad  jnz     short loc_100206B8
0x100206af  mov     dword ptr [ebp-14h], 8007000Eh
0x100206b6  jmp     short loc_10020734
0x100206b8  xor     eax, eax
0x100206ba  mov     [ebp-1Ch], eax
0x100206bd  cmp     [esi+8], eax
0x100206c0  jbe     loc_100207AF
0x100206c6  mov     edx, [ebp-20h]
0x100206c9  nop     dword ptr [eax+00000000h]
0x100206d0  mov     edi, [esi+10h]
0x100206d3  lea     ecx, [eax+eax*2]
0x100206d6  shl     ecx, 4
0x100206d9  add     edi, ecx
0x100206db  lea     eax, [ecx+edx]
0x100206de  mov     [ebp-14h], eax
0x100206e1  mov     eax, [eax+8]
0x100206e4  mov     [edi+8], eax
0x100206e7  lea     eax, [edx+10h]
0x100206ea  add     eax, ecx
0x100206ec  push    eax; pvargSrc
0x100206ed  lea     eax, [edi+10h]
0x100206f0  push    eax; pvargDest
0x100206f1  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100206f7  mov     ecx, eax
0x100206f9  test    ecx, ecx
0x100206fb  js      short loc_10020731
0x100206fd  mov     edx, [ebp-14h]
0x10020700  mov     eax, [edx+20h]
0x10020703  mov     [edi+20h], eax
0x10020706  mov     eax, [edx+28h]
0x10020709  mov     [edi+28h], eax
0x1002070c  mov     eax, [edx+24h]
0x1002070f  mov     edx, [ebp-20h]
0x10020712  mov     [edi+24h], eax
0x10020715  mov     eax, [ebp-1Ch]
0x10020718  inc     eax
0x10020719  mov     [ebp-1Ch], eax
0x1002071c  cmp     eax, [esi+8]
0x1002071f  jb      short loc_100206D0
0x10020721  mov     eax, [ebp-24h]
0x10020724  movups  xmm0, xmmword ptr [eax+14h]
0x10020728  mov     eax, [ebp-18h]
0x1002072b  movups  xmmword ptr [esi+14h], xmm0
0x1002072f  jmp     short loc_10020784
0x10020731  mov     [ebp-14h], ecx
0x10020734  mov     eax, [esi+10h]
0x10020737  mov     [ebp-20h], eax
0x1002073a  test    eax, eax
0x1002073c  jz      short loc_10020765
0x1002073e  cmp     dword ptr [eax-4], 0
0x10020742  lea     ecx, [eax-4]
0x10020745  jz      short loc_1002075C
0x10020747  mov     eax, [eax]
0x10020749  push    3
0x1002074b  mov     edi, [eax]
0x1002074d  mov     ecx, edi
0x1002074f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10020755  mov     ecx, [ebp-20h]
0x10020758  call    edi
0x1002075a  jmp     short loc_10020765
0x1002075c  push    ecx; Block
0x1002075d  call    ??3@YAXPAX@Z; operator delete(void *)
0x10020762  add     esp, 4
0x10020765  mov     ecx, [ebp-14h]
0x10020768  mov     eax, [ebp-18h]
0x1002076b  mov     dword ptr [esi+10h], 0
0x10020772  mov     dword ptr [esi+8], 0
0x10020779  mov     dword ptr [esi+0Ch], 0
0x10020780  test    ecx, ecx
0x10020782  js      short loc_10020797
0x10020784  mov     edx, [ebp-28h]
0x10020787  inc     eax
0x10020788  mov     edi, [ebx+8]
0x1002078b  mov     [ebp-18h], eax
0x1002078e  cmp     eax, 2
0x10020791  jb      loc_10020622
0x10020797  mov     eax, ecx
0x10020799  mov     ecx, [ebp-0Ch]
0x1002079c  mov     large fs:0, ecx
0x100207a3  pop     ecx
0x100207a4  pop     edi
0x100207a5  pop     esi
0x100207a6  mov     esp, ebp
0x100207a8  pop     ebp
0x100207a9  mov     esp, ebx
0x100207ab  pop     ebx
0x100207ac  retn    4
0x100207af  mov     ecx, eax
0x100207b1  mov     eax, [ebp-24h]
0x100207b4  movups  xmm0, xmmword ptr [eax+14h]
0x100207b8  mov     eax, [ebp-18h]
0x100207bb  movups  xmmword ptr [esi+14h], xmm0
0x100207bf  jmp     short loc_10020784
0x1004e7d0  mov     eax, [ebp-2Ch]
0x1004e7d3  push    eax; Block
0x1004e7d4  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004e7d9  pop     ecx
0x1004e7da  retn
0x1004e7e0  nop
0x1004e7e1  nop
0x1004e7e2  mov     edx, [esp+arg_4]
0x1004e7e6  lea     eax, [edx+0Ch]
0x1004e7e9  mov     ecx, [edx-30h]
0x1004e7ec  xor     ecx, eax; StackCookie
0x1004e7ee  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e7f3  mov     eax, offset stru_1004FB38
0x1004e7f8  jmp     ___CxxFrameHandler3
```
