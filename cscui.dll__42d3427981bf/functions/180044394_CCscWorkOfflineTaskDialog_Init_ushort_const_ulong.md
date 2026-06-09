# CCscWorkOfflineTaskDialog::Init(ushort const * *,ulong)

- ea: `0x180044394`
- end: `0x1800444af`
- name: `?Init@CCscWorkOfflineTaskDialog@@QEAAJPEAPEBGK@Z`
- size: `283`
- prototype: `__int64 __fastcall(CCscWorkOfflineTaskDialog *__hidden this, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043ef4`

## callees

- `0x18002aab4`
- `0x18003bdbc`
- `0x180044394`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800443c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800443eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800443c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800443eb`

## pseudocode

```c
__int64 __fastcall CCscWorkOfflineTaskDialog::Init(
        CCscWorkOfflineTaskDialog *this,
        const unsigned __int16 **a2,
        unsigned int a3)
{
  unsigned int v4; // esi
  const unsigned __int16 **v5; // r15
  LPVOID v6; // rax
  unsigned int v7; // edi
  int v8; // ebx
  LPVOID v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int16 **v12; // r12
  const unsigned __int16 *v13; // r13
  unsigned __int64 v14; // rsi
  __int64 result; // rax
  unsigned __int16 **v16; // [rsp+20h] [rbp-58h]
  unsigned __int64 *v17; // [rsp+28h] [rbp-50h]
  unsigned int v18; // [rsp+30h] [rbp-48h]

  v4 = a3;
  v5 = a2;
  v6 = CoTaskMemAlloc(8LL * a3);
  *((_QWORD *)this + 54) = v6;
  v7 = 0;
  if ( v6 )
  {
    v8 = 0;
    while ( v7 < v4 )
    {
      v9 = CoTaskMemAlloc(0x10u);
      v10 = *((_QWORD *)this + 54);
      v11 = v7;
      *(_QWORD *)(v10 + 8LL * v7) = v9;
      v12 = *(unsigned __int16 ***)(*((_QWORD *)this + 54) + 8LL * v7);
      if ( !v12 )
      {
        ++v7;
        goto LABEL_14;
      }
      v13 = v5[v7];
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      *v12 = 0;
      if ( v14 + 1 < v14 )
      {
        v8 = -2147024362;
      }
      else
      {
        v8 = _AllocArray<unsigned short,CTLocalAllocPolicy>(v10, 0, v14 + 1, v12);
        if ( v8 >= 0 )
          StringCchCopyNExW(*v12, v14 + 1, v13, v14, v16, v17, v18);
      }
      ++v7;
      v4 = a3;
      v5 = a2;
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 54) + 8 * v11) + 8LL) = 0;
      if ( v8 < 0 )
        break;
    }
  }
  else
  {
LABEL_14:
    v8 = -2147024882;
  }
  result = (unsigned int)v8;
  *((_DWORD *)this + 110) = v7;
  return result;
}

```

## disassembly

```asm
0x180044394  mov     [rsp+arg_0], rbx
0x180044399  mov     [rsp+arg_10], r8d
0x18004439e  mov     [rsp+arg_8], rdx
0x1800443a3  push    rbp
0x1800443a4  push    rsi
0x1800443a5  push    rdi
0x1800443a6  push    r12
0x1800443a8  push    r13
0x1800443aa  push    r14
0x1800443ac  push    r15
0x1800443ae  sub     rsp, 40h
0x1800443b2  mov     rbp, rcx
0x1800443b5  mov     esi, r8d
0x1800443b8  mov     ecx, r8d
0x1800443bb  mov     r15, rdx
0x1800443be  shl     rcx, 3; cb
0x1800443c2  call    cs:__imp_CoTaskMemAlloc
0x1800443c8  xor     edx, edx
0x1800443ca  mov     [rbp+1B0h], rax
0x1800443d1  mov     edi, edx
0x1800443d3  test    rax, rax
0x1800443d6  jz      loc_18004448A
0x1800443dc  mov     ebx, edx
0x1800443de  cmp     edi, esi
0x1800443e0  jnb     loc_18004448F
0x1800443e6  mov     ecx, 10h; cb
0x1800443eb  call    cs:__imp_CoTaskMemAlloc
0x1800443f1  mov     rcx, [rbp+1B0h]
0x1800443f8  xor     edx, edx
0x1800443fa  mov     r14d, edi
0x1800443fd  mov     [rcx+r14*8], rax
0x180044401  mov     rax, [rbp+1B0h]
0x180044408  mov     r12, [rax+r14*8]
0x18004440c  test    r12, r12
0x18004440f  jz      short loc_180044488
0x180044411  mov     r13, [r15+r14*8]
0x180044415  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180044419  inc     rsi
0x18004441c  cmp     [r13+rsi*2+0], dx
0x180044422  jnz     short loc_180044419
0x180044424  lea     r15, [rsi+1]
0x180044428  mov     [r12], rdx
0x18004442c  cmp     r15, rsi
0x18004442f  jb      short loc_18004445A
0x180044431  mov     r9, r12
0x180044434  mov     r8, r15
0x180044437  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18004443c  xor     edx, edx
0x18004443e  mov     ebx, eax
0x180044440  test    eax, eax
0x180044442  js      short loc_18004445F
0x180044444  mov     rcx, [r12]; unsigned __int16 *
0x180044448  mov     r9, rsi; unsigned __int64
0x18004444b  mov     r8, r13; unsigned __int16 *
0x18004444e  mov     rdx, r15; unsigned __int64
0x180044451  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180044456  xor     edx, edx
0x180044458  jmp     short loc_18004445F
0x18004445a  mov     ebx, 80070216h
0x18004445f  mov     rax, [rbp+1B0h]
0x180044466  inc     edi
0x180044468  mov     esi, [rsp+78h+arg_10]
0x18004446f  mov     r15, [rsp+78h+arg_8]
0x180044477  mov     rcx, [rax+r14*8]
0x18004447b  mov     [rcx+8], edx
0x18004447e  test    ebx, ebx
0x180044480  jns     loc_1800443DE
0x180044486  jmp     short loc_18004448F
0x180044488  inc     edi
0x18004448a  mov     ebx, 8007000Eh
0x18004448f  mov     eax, ebx
0x180044491  mov     [rbp+1B8h], edi
0x180044497  mov     rbx, [rsp+78h+arg_0]
0x18004449f  add     rsp, 40h
0x1800444a3  pop     r15
0x1800444a5  pop     r14
0x1800444a7  pop     r13
0x1800444a9  pop     r12
0x1800444ab  pop     rdi
0x1800444ac  pop     rsi
0x1800444ad  pop     rbp
0x1800444ae  retn
```
