# UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)

- ea: `0x1800070d4`
- end: `0x1800071e3`
- name: `?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z`
- size: `271`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005c64`
- `0x180009f54`

## callees

- `0x1800035a8`
- `0x1800040b4`
- `0x1800070d4`
- `0x1800071ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000716b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000716b`

## pseudocode

```c
__int64 __fastcall UtilAssembleStringsWithAlloc(
        unsigned __int16 **a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rbx
  int v7; // edi
  int v9; // ebx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  int v12; // eax
  unsigned __int16 *v13; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int16 *v15; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp+38h] BYREF

  v4 = L"%s";
  v16 = 0;
  v15 = L"%s";
  v5 = a4;
  v13 = a4;
  if ( (unsigned __int64)L"%s" < 0x10000 )
  {
    v7 = UtilLoadStringWithAlloc((unsigned __int16)L"%s", &v15, (unsigned int)a3);
    if ( v7 < 0 )
    {
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v16);
      return (unsigned int)v7;
    }
    v4 = v15;
    v16 = v15;
  }
  v14 = 0;
  if ( (unsigned __int64)v5 >= 0x10000 )
  {
LABEL_8:
    v10 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
    v11 = v10;
    if ( !v10 )
    {
      v9 = -2147024882;
      goto LABEL_15;
    }
    v15 = v10;
    v12 = StringCchPrintfW(v10, 0x400u, v4, v5);
    v9 = v12;
    if ( v12 == -2147024774 )
    {
      v9 = 0;
    }
    else if ( v12 < 0 )
    {
LABEL_14:
      TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v15);
      goto LABEL_15;
    }
    v15 = 0;
    *a1 = v11;
    goto LABEL_14;
  }
  v9 = UtilLoadStringWithAlloc((unsigned __int16)v5, &v13, (unsigned int)a3);
  if ( v9 >= 0 )
  {
    v5 = v13;
    v14 = v13;
    goto LABEL_8;
  }
LABEL_15:
  TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v14);
  TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800070d4  mov     [rsp-18h+arg_0], rbx
0x1800070d9  mov     [rsp-18h+arg_8], rsi
0x1800070de  mov     [rsp-18h+arg_10], r8
0x1800070e3  push    rbp
0x1800070e4  push    rdi
0x1800070e5  push    r14
0x1800070e7  mov     rbp, rsp
0x1800070ea  sub     rsp, 30h
0x1800070ee  lea     rdi, aS; "%s"
0x1800070f5  mov     [rbp+arg_18], 0
0x1800070fd  mov     esi, 10000h
0x180007102  mov     [rbp+arg_10], rdi
0x180007106  mov     rbx, r9
0x180007109  mov     r14, rcx
0x18000710c  mov     [rbp+var_10], rbx
0x180007110  cmp     rdi, rsi
0x180007113  jnb     short loc_18000713F
0x180007115  movzx   ecx, di; uID
0x180007118  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000711c  call    ?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z; UtilLoadStringWithAlloc(uint,ushort * *,uint)
0x180007121  mov     edi, eax
0x180007123  test    eax, eax
0x180007125  jns     short loc_180007137
0x180007127  lea     rcx, [rbp+arg_18]
0x18000712b  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x180007130  mov     eax, edi
0x180007132  jmp     loc_1800071D0
0x180007137  mov     rdi, [rbp+arg_10]
0x18000713b  mov     [rbp+arg_18], rdi
0x18000713f  mov     [rbp+var_8], 0
0x180007147  cmp     rbx, rsi
0x18000714a  jnb     short loc_180007166
0x18000714c  movzx   ecx, bx; uID
0x18000714f  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x180007153  call    ?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z; UtilLoadStringWithAlloc(uint,ushort * *,uint)
0x180007158  mov     ebx, eax
0x18000715a  test    eax, eax
0x18000715c  js      short loc_1800071BC
0x18000715e  mov     rbx, [rbp+var_10]
0x180007162  mov     [rbp+var_8], rbx
0x180007166  mov     ecx, 800h; cb
0x18000716b  call    cs:__imp_CoTaskMemAlloc
0x180007171  mov     rsi, rax
0x180007174  test    rax, rax
0x180007177  jnz     short loc_180007180
0x180007179  mov     ebx, 8007000Eh
0x18000717e  jmp     short loc_1800071BC
0x180007180  mov     r9, rbx
0x180007183  mov     [rbp+arg_10], rsi
0x180007187  mov     r8, rdi; unsigned __int16 *
0x18000718a  mov     edx, 400h; unsigned __int64
0x18000718f  mov     rcx, rsi; unsigned __int16 *
0x180007192  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007197  mov     ebx, eax
0x180007199  cmp     eax, 8007007Ah
0x18000719e  jnz     short loc_1800071A4
0x1800071a0  xor     ebx, ebx
0x1800071a2  jmp     short loc_1800071A8
0x1800071a4  test    eax, eax
0x1800071a6  js      short loc_1800071B3
0x1800071a8  mov     [rbp+arg_10], 0
0x1800071b0  mov     [r14], rsi
0x1800071b3  lea     rcx, [rbp+arg_10]
0x1800071b7  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800071bc  lea     rcx, [rbp+var_8]
0x1800071c0  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800071c5  lea     rcx, [rbp+arg_18]
0x1800071c9  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x1800071ce  mov     eax, ebx
0x1800071d0  mov     rbx, [rsp+30h+arg_0]
0x1800071d5  mov     rsi, [rsp+30h+arg_8]
0x1800071da  add     rsp, 30h
0x1800071de  pop     r14
0x1800071e0  pop     rdi
0x1800071e1  pop     rbp
0x1800071e2  retn
```
