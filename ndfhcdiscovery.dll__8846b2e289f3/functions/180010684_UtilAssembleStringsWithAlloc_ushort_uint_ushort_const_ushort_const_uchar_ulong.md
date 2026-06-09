# UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)

- ea: `0x180010684`
- end: `0x1800107e8`
- name: `?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z`
- size: `356`
- prototype: `int(unsigned __int16 **, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b6fc`
- `0x18000cfe4`
- `0x18000d0bc`
- `0x18000d134`
- `0x18000dbd0`
- `0x18000dcb0`
- `0x18000dcf0`
- `0x18000e200`
- `0x180010564`
- `0x180011fcc`

## callees

- `0x180003414`
- `0x180010684`
- `0x1800107f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001074a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001075e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001074a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001075e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001072e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001072e`

## pseudocode

```c
__int64 __fastcall UtilAssembleStringsWithAlloc(
        unsigned __int16 **a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // r14
  unsigned __int64 v5; // rbp
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rsi
  __int64 result; // rax
  unsigned __int16 *v10; // rdi
  int v11; // edi
  unsigned __int64 v12; // r15
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbp
  int v15; // esi
  unsigned __int16 *v16; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp+20h] BYREF

  v4 = L"%s";
  v5 = a2;
  v6 = 0;
  v16 = L"%s";
  v17 = a4;
  v7 = a4;
  if ( (unsigned __int64)L"%s" < 0x10000 )
  {
    result = UtilLoadStringWithAlloc((unsigned __int16)L"%s", &v16, a2);
    if ( (int)result < 0 )
      return result;
    v4 = v16;
    v6 = v16;
  }
  v10 = 0;
  if ( (unsigned __int64)v7 < 0x10000 )
  {
    v11 = UtilLoadStringWithAlloc((unsigned __int16)v7, &v17, v5);
    if ( v11 < 0 )
    {
      if ( v6 )
        CoTaskMemFree(v6);
      return (unsigned int)v11;
    }
    v7 = v17;
    v10 = v17;
  }
  v12 = v5;
  v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
  v14 = v13;
  if ( !v13 )
  {
    if ( v10 )
      CoTaskMemFree(v10);
    if ( v6 )
      CoTaskMemFree(v6);
    return 2147942414LL;
  }
  v15 = StringCchPrintfW(v13, v12, v4, v7);
  if ( v15 == -2147024774 )
  {
    v15 = 0;
  }
  else if ( v15 < 0 )
  {
    CoTaskMemFree(v14);
    goto LABEL_19;
  }
  *a1 = v14;
LABEL_19:
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180010684  mov     rax, rsp
0x180010687  mov     [rax+8], rbx
0x18001068b  mov     [rax+10h], rbp
0x18001068f  mov     [rax+18h], r8
0x180010693  push    rsi
0x180010694  push    rdi
0x180010695  push    r12
0x180010697  push    r14
0x180010699  push    r15
0x18001069b  sub     rsp, 20h
0x18001069f  lea     r14, aS_0; "%s"
0x1800106a6  mov     ebp, edx
0x1800106a8  xor     ebx, ebx
0x1800106aa  mov     [rax+18h], r14
0x1800106ae  mov     r15d, 10000h
0x1800106b4  mov     [rax+20h], r9
0x1800106b8  mov     rsi, r9
0x1800106bb  mov     r12, rcx
0x1800106be  cmp     r14, r15
0x1800106c1  jnb     short loc_1800106E3
0x1800106c3  movzx   ecx, r14w; uID
0x1800106c7  lea     rdx, [rax+18h]; unsigned __int16 **
0x1800106cb  mov     r8d, ebp; unsigned int
0x1800106ce  call    ?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z; UtilLoadStringWithAlloc(uint,ushort * *,uint)
0x1800106d3  test    eax, eax
0x1800106d5  js      loc_1800107BB
0x1800106db  mov     r14, [rsp+48h+arg_10]
0x1800106e0  mov     rbx, r14
0x1800106e3  xor     edi, edi
0x1800106e5  cmp     rsi, r15
0x1800106e8  jnb     short loc_180010723
0x1800106ea  movzx   ecx, si; uID
0x1800106ed  lea     rdx, [rsp+48h+arg_18]; unsigned __int16 **
0x1800106f2  mov     r8d, ebp; unsigned int
0x1800106f5  call    ?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z; UtilLoadStringWithAlloc(uint,ushort * *,uint)
0x1800106fa  mov     edi, eax
0x1800106fc  test    eax, eax
0x1800106fe  jns     short loc_18001071B
0x180010700  test    rbx, rbx
0x180010703  jz      short loc_180010714
0x180010705  mov     rcx, rbx; pv
0x180010708  call    cs:__imp_CoTaskMemFree
0x18001070f  nop     dword ptr [rax+rax+00h]
0x180010714  mov     eax, edi
0x180010716  jmp     loc_1800107BB
0x18001071b  mov     rsi, [rsp+48h+arg_18]
0x180010720  mov     rdi, rsi
0x180010723  lea     rcx, ds:0[rbp*2]; cb
0x18001072b  mov     r15, rbp
0x18001072e  call    cs:__imp_CoTaskMemAlloc
0x180010735  nop     dword ptr [rax+rax+00h]
0x18001073a  mov     rbp, rax
0x18001073d  test    rax, rax
0x180010740  jnz     short loc_180010771
0x180010742  test    rdi, rdi
0x180010745  jz      short loc_180010756
0x180010747  mov     rcx, rdi; pv
0x18001074a  call    cs:__imp_CoTaskMemFree
0x180010751  nop     dword ptr [rax+rax+00h]
0x180010756  test    rbx, rbx
0x180010759  jz      short loc_18001076A
0x18001075b  mov     rcx, rbx; pv
0x18001075e  call    cs:__imp_CoTaskMemFree
0x180010765  nop     dword ptr [rax+rax+00h]
0x18001076a  mov     eax, 8007000Eh
0x18001076f  jmp     short loc_1800107BB
0x180010771  mov     r9, rsi
0x180010774  mov     r8, r14; unsigned __int16 *
0x180010777  mov     rdx, r15; unsigned __int64
0x18001077a  mov     rcx, rbp; unsigned __int16 *
0x18001077d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010782  mov     esi, eax
0x180010784  cmp     eax, 8007007Ah
0x180010789  jnz     short loc_1800107D3
0x18001078b  xor     esi, esi
0x18001078d  mov     [r12], rbp
0x180010791  test    rdi, rdi
0x180010794  jz      short loc_1800107A5
0x180010796  mov     rcx, rdi; pv
0x180010799  call    cs:__imp_CoTaskMemFree
0x1800107a0  nop     dword ptr [rax+rax+00h]
0x1800107a5  test    rbx, rbx
0x1800107a8  jz      short loc_1800107B9
0x1800107aa  mov     rcx, rbx; pv
0x1800107ad  call    cs:__imp_CoTaskMemFree
0x1800107b4  nop     dword ptr [rax+rax+00h]
0x1800107b9  mov     eax, esi
0x1800107bb  mov     rbx, [rsp+48h+arg_0]
0x1800107c0  mov     rbp, [rsp+48h+arg_8]
0x1800107c5  add     rsp, 20h
0x1800107c9  pop     r15
0x1800107cb  pop     r14
0x1800107cd  pop     r12
0x1800107cf  pop     rdi
0x1800107d0  pop     rsi
0x1800107d1  retn
0x1800107d3  test    esi, esi
0x1800107d5  jns     short loc_18001078D
0x1800107d7  mov     rcx, rbp; pv
0x1800107da  call    cs:__imp_CoTaskMemFree
0x1800107e1  nop     dword ptr [rax+rax+00h]
0x1800107e6  jmp     short loc_180010791
```
