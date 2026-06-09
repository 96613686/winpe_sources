# FreeDbPropSet(ulong,tagDBPROPSET *,bool)

- ea: `0x180049070`
- end: `0x180049167`
- name: `?FreeDbPropSet@@YAXKPEAUtagDBPROPSET@@_N@Z`
- size: `247`
- prototype: `void __fastcall(unsigned int, struct tagDBPROPSET *, bool)`
- caller_count: `17`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800145d0`
- `0x1800174b0`
- `0x18001a910`
- `0x18001afa0`
- `0x18001b8f8`
- `0x18003ce60`
- `0x1800413b4`
- `0x18006a9dc`
- `0x18006ab5c`
- `0x18006ad20`
- `0x18006ae40`
- `0x180071ca0`
- `0x180081d00`
- `0x180084380`
- `0x180085e24`
- `0x180087824`
- `0x1800a61b4`

## callees

- `0x180049070`

## import_xrefs

- `MSDART!MpHeapFree` at `0x180049135`
- `MSDART!MpHeapFree` at `0x180049152`
- `MSDART!MpHeapFree` at `0x180049135`
- `MSDART!MpHeapFree` at `0x180049152`
- `ole32!CoTaskMemFree` at `0x1800490c4`
- `ole32!CoTaskMemFree` at `0x1800490c4`
- `ole32!CoTaskMemFree` at `0x1800490f4`
- `OLEAUT32!__imp_VariantClear` at `0x180049112`
- `OLEAUT32!__imp_VariantClear` at `0x180049112`

## pseudocode

```c
void __fastcall FreeDbPropSet(unsigned int a1, struct tagDBPROPSET *a2, char a3)
{
  unsigned int i; // ebp
  struct tagDBPROPSET *v7; // r14
  __int64 v8; // r15
  DBPROP *rgProperties; // rdx

  if ( a1 )
  {
    for ( i = 0; i < a1; ++i )
    {
      v7 = &a2[i];
      if ( v7->cProperties )
      {
        v8 = 0;
        do
        {
          VariantClear((VARIANTARG *)((char *)&v7->rgProperties->vValue + 64 * v8 + 8 * v8));
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (unsigned int)v8 < v7->cProperties );
        rgProperties = v7->rgProperties;
        if ( a3 )
        {
          CoTaskMemFree(v7->rgProperties);
        }
        else if ( rgProperties )
        {
          MpHeapFree(g_hHeapHandle, rgProperties);
        }
      }
    }
    if ( a3 )
    {
      CoTaskMemFree(a2);
    }
    else if ( a2 )
    {
      MpHeapFree(g_hHeapHandle, a2);
    }
  }
}

```

## disassembly

```asm
0x180049070  test    ecx, ecx
0x180049072  jnz     short loc_180049076
0x180049074  retn
0x180049076  push    rbx
0x180049077  push    rsi
0x180049078  push    rdi
0x180049079  sub     rsp, 20h
0x18004907d  mov     [rsp+38h+arg_0], rbp
0x180049082  movzx   edi, r8b
0x180049086  xor     ebp, ebp
0x180049088  mov     rsi, rdx
0x18004908b  mov     ebx, ecx
0x18004908d  test    ecx, ecx
0x18004908f  jz      short loc_1800490E0
0x180049091  mov     [rsp+38h+arg_8], r14
0x180049096  mov     [rsp+38h+arg_10], r15
0x18004909b  nop     dword ptr [rax+rax+00h]
0x1800490a0  mov     r14d, ebp
0x1800490a3  shl     r14, 5
0x1800490a7  add     r14, rsi
0x1800490aa  mov     eax, [r14+8]
0x1800490ae  test    eax, eax
0x1800490b0  jz      short loc_1800490D0
0x1800490b2  xor     r15d, r15d
0x1800490b5  test    eax, eax
0x1800490b7  jnz     short loc_180049100
0x1800490b9  mov     rdx, [r14]
0x1800490bc  test    dil, dil
0x1800490bf  jz      short loc_180049129
0x1800490c1  mov     rcx, rdx; pv
0x1800490c4  call    cs:__imp_CoTaskMemFree
0x1800490cb  nop     dword ptr [rax+rax+00h]
0x1800490d0  inc     ebp
0x1800490d2  cmp     ebp, ebx
0x1800490d4  jb      short loc_1800490A0
0x1800490d6  mov     r15, [rsp+38h+arg_10]
0x1800490db  mov     r14, [rsp+38h+arg_8]
0x1800490e0  mov     rbp, [rsp+38h+arg_0]
0x1800490e5  test    dil, dil
0x1800490e8  jz      short loc_180049143
0x1800490ea  mov     rcx, rsi
0x1800490ed  add     rsp, 20h
0x1800490f1  pop     rdi
0x1800490f2  pop     rsi
0x1800490f3  pop     rbx
0x1800490f4  jmp     cs:__imp_CoTaskMemFree
0x180049100  mov     rax, [r14]
0x180049103  lea     rcx, ds:6[r15*8]
0x18004910b  add     rcx, r15
0x18004910e  lea     rcx, [rax+rcx*8]; pvarg
0x180049112  call    cs:__imp_VariantClear
0x180049119  nop     dword ptr [rax+rax+00h]
0x18004911e  inc     r15d
0x180049121  cmp     r15d, [r14+8]
0x180049125  jb      short loc_180049100
0x180049127  jmp     short loc_1800490B9
0x180049129  test    rdx, rdx
0x18004912c  jz      short loc_1800490D0
0x18004912e  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180049135  call    cs:__imp_MpHeapFree
0x18004913c  nop     dword ptr [rax+rax+00h]
0x180049141  jmp     short loc_1800490D0
0x180049143  test    rsi, rsi
0x180049146  jz      short loc_18004915E
0x180049148  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004914f  mov     rdx, rsi
0x180049152  call    cs:__imp_MpHeapFree
0x180049159  nop     dword ptr [rax+rax+00h]
0x18004915e  add     rsp, 20h
0x180049162  pop     rdi
0x180049163  pop     rsi
0x180049164  pop     rbx
0x180049165  retn
```
