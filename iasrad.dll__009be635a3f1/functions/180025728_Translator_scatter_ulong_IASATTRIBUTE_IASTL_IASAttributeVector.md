# Translator::scatter(ulong,_IASATTRIBUTE &,IASTL::IASAttributeVector &)

- ea: `0x180025728`
- end: `0x180025838`
- name: `?scatter@Translator@@KAXKAEAU_IASATTRIBUTE@@AEAVIASAttributeVector@IASTL@@@Z`
- size: `272`
- prototype: `void __fastcall(size_t Size, struct _IASATTRIBUTE *, struct IASTL::IASAttributeVector *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025840`

## callees

- `0x180002106`
- `0x180014478`
- `0x18001b0ec`
- `0x18001c46c`
- `0x18001d124`
- `0x180025728`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002579f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002579f`

## pseudocode

```c
void __fastcall Translator::scatter(size_t Size, struct _IASATTRIBUTE *a2, struct IASTL::IASAttributeVector *a3)
{
  size_t v4; // r14
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  unsigned int v7; // ebx
  char *i; // r12
  unsigned int v9; // esi
  unsigned int v10; // r13d
  char *v11; // rax
  char *v12; // r15
  struct _IASATTRIBUTE *v13; // rdx
  bool v14; // r8
  struct _IASATTRIBUTE *v15; // [rsp+68h] [rbp+10h] BYREF
  IASTL::IASAttributeVector *v16; // [rsp+70h] [rbp+18h]

  v16 = a3;
  v4 = (unsigned int)Size;
  v5 = *((_DWORD *)a2 + 6);
  if ( v5 > 0xFD )
  {
    v6 = 253 - Size;
    v7 = v5 - Size;
    for ( i = (char *)(*((_QWORD *)a2 + 4) + (unsigned int)Size); ; i += v9 )
    {
      IASTL::IASAttribute::_alloc((IASTL::IASAttribute *)&v15);
      v9 = v7;
      if ( v7 >= v6 )
        v9 = v6;
      v10 = v9 + v4;
      if ( v9 + (unsigned int)v4 < v9 )
        _com_issue_error(534);
      v11 = (char *)CoTaskMemAlloc(v10);
      v12 = v11;
      if ( !v11 )
        _com_issue_error(-2147024882);
      if ( (_DWORD)v4 )
      {
        memcpy_0(v11, *((const void **)a2 + 4), v4);
        v12[v4 - 1] = v9 + 2;
      }
      memcpy_0(&v12[v4], i, v9);
      v13 = v15;
      *((_DWORD *)v15 + 2) = *((_DWORD *)a2 + 2);
      *((_DWORD *)v13 + 1) = *((_DWORD *)a2 + 1);
      *((_DWORD *)v13 + 4) = 6;
      *((_DWORD *)v13 + 6) = v10;
      *((_QWORD *)v13 + 4) = v12;
      IASTL::IASAttributeVector::push_back(v16, v13, v14);
      IASTL::IASAttribute::_release((IASTL::IASAttribute *)&v15);
      v7 -= v9;
      if ( !v7 )
        break;
    }
  }
  else
  {
    IASTL::IASAttributeVector::push_back(a3, a2, (bool)a3);
  }
}

```

## disassembly

```asm
0x180025728  mov     [rsp+arg_0], rbx
0x18002572d  mov     [rsp+arg_10], r8
0x180025732  push    rbp
0x180025733  push    rsi
0x180025734  push    rdi
0x180025735  push    r12
0x180025737  push    r13
0x180025739  push    r14
0x18002573b  push    r15
0x18002573d  sub     rsp, 20h
0x180025741  mov     rdi, rdx
0x180025744  mov     r14d, ecx
0x180025747  mov     ebx, [rdx+18h]
0x18002574a  mov     ebp, 0FDh
0x18002574f  cmp     ebx, ebp
0x180025751  ja      short loc_180025770
0x180025753  mov     rcx, r8; this
0x180025756  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x18002575b  mov     rbx, [rsp+58h+arg_0]
0x180025760  add     rsp, 20h
0x180025764  pop     r15
0x180025766  pop     r14
0x180025768  pop     r13
0x18002576a  pop     r12
0x18002576c  pop     rdi
0x18002576d  pop     rsi
0x18002576e  pop     rbp
0x18002576f  retn
0x180025770  sub     ebp, r14d
0x180025773  sub     ebx, r14d
0x180025776  mov     r12, r14
0x180025779  add     r12, [rdx+20h]
0x18002577d  lea     rcx, [rsp+58h+arg_8]; this
0x180025782  call    ?_alloc@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_alloc(void)
0x180025787  nop
0x180025788  mov     esi, ebx
0x18002578a  cmp     ebx, ebp
0x18002578c  cmovnb  esi, ebp
0x18002578f  lea     r13d, [rsi+r14]
0x180025793  cmp     r13d, esi
0x180025796  jb      loc_18002582D
0x18002579c  mov     ecx, r13d; cb
0x18002579f  call    cs:__imp_CoTaskMemAlloc
0x1800257a5  mov     r15, rax
0x1800257a8  test    rax, rax
0x1800257ab  jz      short loc_180025822
0x1800257ad  test    r14d, r14d
0x1800257b0  jz      short loc_1800257C9
0x1800257b2  mov     r8, r14; Size
0x1800257b5  mov     rdx, [rdi+20h]; Src
0x1800257b9  mov     rcx, rax; void *
0x1800257bc  call    memcpy_0
0x1800257c1  lea     ecx, [rsi+2]
0x1800257c4  mov     [r14+r15-1], cl
0x1800257c9  mov     rax, r14
0x1800257cc  mov     r8d, esi; Size
0x1800257cf  lea     rcx, [rax+r15]; void *
0x1800257d3  mov     rdx, r12; Src
0x1800257d6  call    memcpy_0
0x1800257db  mov     eax, [rdi+8]
0x1800257de  mov     rdx, [rsp+58h+arg_8]; struct _IASATTRIBUTE *
0x1800257e3  mov     [rdx+8], eax
0x1800257e6  mov     eax, [rdi+4]
0x1800257e9  mov     [rdx+4], eax
0x1800257ec  mov     dword ptr [rdx+10h], 6
0x1800257f3  mov     [rdx+18h], r13d
0x1800257f7  mov     [rdx+20h], r15
0x1800257fb  mov     rcx, [rsp+58h+arg_10]; this
0x180025800  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x180025805  nop
0x180025806  lea     rcx, [rsp+58h+arg_8]; this
0x18002580b  call    ?_release@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::_release(void)
0x180025810  sub     ebx, esi
0x180025812  jz      loc_18002575B
0x180025818  mov     eax, esi
0x18002581a  add     r12, rax
0x18002581d  jmp     loc_18002577D
0x180025822  mov     ecx, 8007000Eh; int
0x180025827  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002582d  mov     ecx, 216h; int
0x180025832  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
