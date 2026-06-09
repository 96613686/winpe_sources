# ATL::AtlGetFuncInfoFromId(ITypeInfo *,_GUID const &,long,ulong,ATL::_ATL_FUNC_INFO &)

- ea: `0x140004300`
- end: `0x1400044c5`
- name: `?AtlGetFuncInfoFromId@ATL@@YAJPEAUITypeInfo@@AEBU_GUID@@JKAEAU_ATL_FUNC_INFO@1@@Z`
- size: `453`
- prototype: `__int64 __usercall@<rax>(struct ITypeInfo *@<rcx>, const struct _GUID *@<rdx>, int@<r8d>, unsigned int@<r9d>, struct ATL::_ATL_FUNC_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400052e0`
- `0x1400053f0`

## callees

- `0x140004300`
- `0x1400044cc`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::AtlGetFuncInfoFromId(
        struct ITypeInfo *a1,
        const struct _GUID *a2,
        int a3,
        __int64 a4,
        struct ATL::_ATL_FUNC_INFO *a5)
{
  __int64 result; // rax
  struct ITypeInfoVtbl *lpVtbl; // rax
  int v9; // edi
  const struct _GUID *v10; // r8
  struct ATL::_ATL_FUNC_INFO *v11; // rsi
  int v12; // edi
  __int64 v13; // r9
  __int16 v14; // ax
  unsigned __int16 UserDefinedType; // ax
  __int16 v16; // dx
  __int64 v17; // [rsp+40h] [rbp+8h] BYREF
  const struct _GUID *v18; // [rsp+48h] [rbp+10h] BYREF

  v18 = a2;
  if ( !a1 )
    return 2147942487LL;
  lpVtbl = a1->lpVtbl;
  v18 = 0;
  v17 = 0;
  result = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a1, &v17);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    if ( *(_WORD *)(v17 + 48) )
    {
      while ( 1 )
      {
        result = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, const struct _GUID **))a1->lpVtbl->GetFuncDesc)(
                   a1,
                   (unsigned int)v9,
                   &v18);
        if ( (int)result < 0 )
          break;
        if ( v18->Data1 != a3 )
        {
          ((void (__fastcall *)(struct ITypeInfo *))a1->lpVtbl->ReleaseFuncDesc)(a1);
          ++v9;
          v18 = 0;
          if ( v9 < *(unsigned __int16 *)(v17 + 48) )
            continue;
        }
        goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      ((void (__fastcall *)(struct ITypeInfo *))a1->lpVtbl->ReleaseTypeAttr)(a1);
      v10 = v18;
      if ( v18 && (__int16)v18[2].Data2 <= 8 )
      {
        v11 = a5;
        v12 = 0;
        if ( (__int16)v18[2].Data2 > 0 )
        {
          do
          {
            v13 = 32LL * v12;
            v14 = *(_WORD *)(v13 + *(_QWORD *)&v10[1].Data1 + 8);
            *((_WORD *)v11 + v12 + 4) = v14;
            if ( v14 == 26 )
            {
              v14 = *(_WORD *)(*(_QWORD *)(v13 + *(_QWORD *)&v10[1].Data1) + 8LL) | 0x4000;
              *((_WORD *)v11 + v12 + 4) = v14;
            }
            if ( v14 == 29 )
            {
              UserDefinedType = ATL::AtlGetUserDefinedType(a1, *(_DWORD *)(v13 + *(_QWORD *)&v10[1].Data1));
              v10 = v18;
              *((_WORD *)v11 + v12 + 4) = UserDefinedType;
            }
            ++v12;
          }
          while ( v12 < (__int16)v10[2].Data2 );
        }
        v16 = *(_WORD *)v10[3].Data4;
        if ( v16 == 22 )
        {
          v16 = 3;
        }
        else
        {
          switch ( *(_WORD *)v10[3].Data4 )
          {
            case 0x17:
              v16 = 19;
              break;
            case 0x18:
              v16 = 0;
              break;
            case 0x19:
              v16 = 10;
              break;
          }
        }
        *((_WORD *)v11 + 2) = v16;
        *(_DWORD *)v11 = v10[2].Data1;
        *((_WORD *)v11 + 3) = v10[2].Data2;
        ((void (__fastcall *)(struct ITypeInfo *, const struct _GUID *))a1->lpVtbl->ReleaseFuncDesc)(a1, v10);
        return 0;
      }
      else
      {
        return 2147500037LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004300  mov     [rsp+arg_10], rbx
0x140004305  mov     [rsp+arg_8], rdx
0x14000430a  push    rbp
0x14000430b  push    rsi
0x14000430c  push    rdi
0x14000430d  sub     rsp, 20h
0x140004311  mov     esi, r8d
0x140004314  mov     rbx, rcx
0x140004317  test    rcx, rcx
0x14000431a  jnz     short loc_140004326
0x14000431c  mov     eax, 80070057h
0x140004321  jmp     loc_1400044B8
0x140004326  mov     rax, [rcx]
0x140004329  lea     rdx, [rsp+38h+arg_0]
0x14000432e  mov     [rsp+38h+arg_8], 0
0x140004337  mov     [rsp+38h+arg_0], 0
0x140004340  mov     rax, [rax+18h]
0x140004344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004349  test    eax, eax
0x14000434b  js      loc_1400044B8
0x140004351  mov     rdx, [rsp+38h+arg_0]
0x140004356  xor     edi, edi
0x140004358  xor     eax, eax
0x14000435a  cmp     ax, [rdx+30h]
0x14000435e  jnb     short loc_1400043B8
0x140004360  mov     rax, [rbx]
0x140004363  lea     r8, [rsp+38h+arg_8]
0x140004368  mov     edx, edi
0x14000436a  mov     rcx, rbx
0x14000436d  mov     rax, [rax+28h]
0x140004371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004376  test    eax, eax
0x140004378  js      loc_1400044B8
0x14000437e  mov     rdx, [rsp+38h+arg_8]
0x140004383  cmp     [rdx], esi
0x140004385  jz      short loc_1400043B3
0x140004387  mov     rax, [rbx]
0x14000438a  mov     rcx, rbx
0x14000438d  mov     rax, [rax+0A0h]
0x140004394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004399  mov     rdx, [rsp+38h+arg_0]
0x14000439e  inc     edi
0x1400043a0  mov     [rsp+38h+arg_8], 0
0x1400043a9  movzx   eax, word ptr [rdx+30h]
0x1400043ad  cmp     edi, eax
0x1400043af  jl      short loc_140004360
0x1400043b1  jmp     short loc_1400043B8
0x1400043b3  mov     rdx, [rsp+38h+arg_0]
0x1400043b8  mov     rax, [rbx]
0x1400043bb  mov     rcx, rbx
0x1400043be  mov     rax, [rax+98h]
0x1400043c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043ca  mov     r8, [rsp+38h+arg_8]
0x1400043cf  test    r8, r8
0x1400043d2  jz      loc_1400044B3
0x1400043d8  cmp     word ptr [r8+24h], 8
0x1400043de  jg      loc_1400044B3
0x1400043e4  mov     rsi, [rsp+38h+arg_20]
0x1400043e9  xor     edi, edi
0x1400043eb  xor     eax, eax
0x1400043ed  cmp     ax, [r8+24h]
0x1400043f2  jge     short loc_140004454
0x1400043f4  mov     rax, [r8+10h]
0x1400043f8  movsxd  rbp, edi
0x1400043fb  mov     r9, rbp
0x1400043fe  shl     r9, 5
0x140004402  movzx   eax, word ptr [r9+rax+8]
0x140004408  mov     [rsi+rbp*2+8], ax
0x14000440d  cmp     ax, 1Ah
0x140004411  jnz     short loc_140004429
0x140004413  mov     rax, [r8+10h]
0x140004417  mov     rcx, [r9+rax]
0x14000441b  mov     eax, 4000h
0x140004420  or      ax, [rcx+8]
0x140004424  mov     [rsi+rbp*2+8], ax
0x140004429  cmp     ax, 1Dh
0x14000442d  jnz     short loc_140004449
0x14000442f  mov     rdx, [r8+10h]
0x140004433  mov     rcx, rbx; struct ITypeInfo *
0x140004436  mov     edx, [r9+rdx]; unsigned int
0x14000443a  call    ?AtlGetUserDefinedType@ATL@@YAGPEAUITypeInfo@@K@Z; ATL::AtlGetUserDefinedType(ITypeInfo *,ulong)
0x14000443f  mov     r8, [rsp+38h+arg_8]
0x140004444  mov     [rsi+rbp*2+8], ax
0x140004449  movsx   eax, word ptr [r8+24h]
0x14000444e  inc     edi
0x140004450  cmp     edi, eax
0x140004452  jl      short loc_1400043F4
0x140004454  movzx   edx, word ptr [r8+38h]
0x140004459  mov     ecx, edx
0x14000445b  sub     ecx, 16h
0x14000445e  jz      short loc_140004482
0x140004460  sub     ecx, 1
0x140004463  jz      short loc_14000447B
0x140004465  sub     ecx, 1
0x140004468  jz      short loc_140004474
0x14000446a  cmp     ecx, 1
0x14000446d  jnz     short loc_140004487
0x14000446f  lea     edx, [rcx+9]
0x140004472  jmp     short loc_140004487
0x140004474  xor     eax, eax
0x140004476  movzx   edx, ax
0x140004479  jmp     short loc_140004487
0x14000447b  mov     edx, 13h
0x140004480  jmp     short loc_140004487
0x140004482  mov     edx, 3
0x140004487  mov     [rsi+4], dx
0x14000448b  mov     rcx, rbx
0x14000448e  mov     eax, [r8+20h]
0x140004492  mov     rdx, r8
0x140004495  mov     [rsi], eax
0x140004497  movzx   eax, word ptr [r8+24h]
0x14000449c  mov     [rsi+6], ax
0x1400044a0  mov     rax, [rbx]
0x1400044a3  mov     rax, [rax+0A0h]
0x1400044aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044af  xor     eax, eax
0x1400044b1  jmp     short loc_1400044B8
0x1400044b3  mov     eax, 80004005h
0x1400044b8  mov     rbx, [rsp+38h+arg_10]
0x1400044bd  add     rsp, 20h
0x1400044c1  pop     rdi
0x1400044c2  pop     rsi
0x1400044c3  pop     rbp
0x1400044c4  retn
```
