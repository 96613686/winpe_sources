# TDSLSet<tagDBPROPSET,CDSLProperty>::Free(int)

- ea: `0x1800150ac`
- end: `0x180015168`
- name: `?Free@?$TDSLSet@UtagDBPROPSET@@VCDSLProperty@@@@QEAAXH@Z`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180013e30`
- `0x180014914`
- `0x180014970`

## callees

- `0x1800150ac`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001513e`
- `OLEAUT32!__imp_VariantClear` at `0x18001513e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001511d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001511d`
- `ole32!CoTaskMemFree` at `0x18001514b`
- `ole32!CoTaskMemFree` at `0x18001514b`

## pseudocode

```c
void __fastcall TDSLSet<tagDBPROPSET,CDSLProperty>::Free(__int64 a1, int a2)
{
  int v2; // esi
  VARIANTARG *v4; // rdi
  BOOL v5; // ebp
  VARIANTARG *v6; // r15
  VARIANTARG *v7; // rax
  VARIANTARG *v8; // r14
  OLECHAR *bstrVal; // rcx
  __int64 v10; // rcx
  BYTE *i; // rax

  v2 = *(_DWORD *)(a1 + 8);
  v4 = *(VARIANTARG **)a1;
  v5 = a2
    && *(_QWORD *)(a1 + 12) == *(_QWORD *)&DBPROPSET_DBINIT.Data1
    && *(_QWORD *)(a1 + 20) == *(_QWORD *)DBPROPSET_DBINIT.Data4;
  while ( v2 )
  {
    v6 = v4;
    v7 = v4;
    v8 = v4;
    --v2;
    v4 += 3;
    if ( v5 && (*(_DWORD *)&v8->vt == 9 || *(_DWORD *)&v8->vt == 160) && v7[2].vt == 8 )
    {
      bstrVal = v8[2].bstrVal;
      if ( bstrVal )
      {
        v10 = SysStringByteLen(bstrVal);
        for ( i = v8[2].pbVal; v10; --v10 )
          *i++ = 0;
      }
    }
    VariantClear(v6 + 2);
  }
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x1800150ac  push    rbx
0x1800150ae  push    rbp
0x1800150af  push    rsi
0x1800150b0  push    rdi
0x1800150b1  push    r14
0x1800150b3  push    r15
0x1800150b5  sub     rsp, 28h
0x1800150b9  mov     esi, [rcx+8]
0x1800150bc  mov     rbx, rcx
0x1800150bf  mov     rdi, [rcx]
0x1800150c2  test    edx, edx
0x1800150c4  jz      short loc_1800150E7
0x1800150c6  mov     rax, [rcx+0Ch]
0x1800150ca  cmp     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x1800150d1  jnz     short loc_1800150E7
0x1800150d3  mov     rax, [rcx+14h]
0x1800150d7  cmp     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x1800150de  jnz     short loc_1800150E7
0x1800150e0  mov     ebp, 1
0x1800150e5  jmp     short loc_180015144
0x1800150e7  xor     ebp, ebp
0x1800150e9  jmp     short loc_180015144
0x1800150eb  mov     r15, rdi
0x1800150ee  mov     rax, rdi
0x1800150f1  mov     r14, rdi
0x1800150f4  dec     esi
0x1800150f6  add     rdi, 48h ; 'H'
0x1800150fa  test    ebp, ebp
0x1800150fc  jz      short loc_18001513A
0x1800150fe  cmp     dword ptr [r14], 9
0x180015102  jz      short loc_18001510D
0x180015104  cmp     dword ptr [r14], 0A0h
0x18001510b  jnz     short loc_18001513A
0x18001510d  cmp     word ptr [rax+30h], 8
0x180015112  jnz     short loc_18001513A
0x180015114  mov     rcx, [r14+38h]; bstr
0x180015118  test    rcx, rcx
0x18001511b  jz      short loc_18001513A
0x18001511d  call    cs:__imp_SysStringByteLen
0x180015123  mov     ecx, eax
0x180015125  mov     rax, [r14+38h]
0x180015129  test    rcx, rcx
0x18001512c  jz      short loc_18001513A
0x18001512e  mov     byte ptr [rax], 0
0x180015131  inc     rax
0x180015134  sub     rcx, 1
0x180015138  jnz     short loc_18001512E
0x18001513a  lea     rcx, [r15+30h]; pvarg
0x18001513e  call    cs:__imp_VariantClear
0x180015144  test    esi, esi
0x180015146  jnz     short loc_1800150EB
0x180015148  mov     rcx, [rbx]; pv
0x18001514b  call    cs:__imp_CoTaskMemFree
0x180015151  mov     qword ptr [rbx], 0
0x180015158  mov     [rbx+8], esi
0x18001515b  add     rsp, 28h
0x18001515f  pop     r15
0x180015161  pop     r14
0x180015163  pop     rdi
0x180015164  pop     rsi
0x180015165  pop     rbp
0x180015166  pop     rbx
0x180015167  retn
```
