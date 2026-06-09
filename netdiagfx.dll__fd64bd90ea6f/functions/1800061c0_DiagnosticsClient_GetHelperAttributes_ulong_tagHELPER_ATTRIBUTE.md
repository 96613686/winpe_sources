# DiagnosticsClient::GetHelperAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x1800061c0`
- end: `0x180006344`
- name: `?GetHelperAttributes@DiagnosticsClient@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(DiagnosticsClient *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800061c0`
- `0x180006460`
- `0x180006b60`
- `0x18002c80e`

## import_xrefs

- `wdi!WdiGetParameterCount` at `0x180006214`
- `wdi!WdiGetParameterCount` at `0x180006214`
- `wdi!WdiGetParameterByIndex` at `0x180006298`
- `wdi!WdiGetParameterByIndex` at `0x180006298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000630d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000631a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800062f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000630d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000631a`

## pseudocode

```c
__int64 __fastcall DiagnosticsClient::GetHelperAttributes(
        DiagnosticsClient *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct tagHELPER_ATTRIBUTE *v9; // rax
  struct tagHELPER_ATTRIBUTE *v10; // rbx
  unsigned int v11; // edx
  __int64 v12; // rcx
  unsigned int v13; // esi
  unsigned int v14; // r12d
  int ParameterByIndex; // r15d
  int v16; // esi
  wchar_t *String2; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+70h] [rbp+40h] BYREF
  void *v19; // [rsp+88h] [rbp+58h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 2147942406LL;
  if ( !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v7 = *((_QWORD *)this + 1);
  v18 = 0;
  result = WdiGetParameterCount(v7, &v18);
  if ( (int)result < 0 || v18 <= 1 )
  {
    *a2 = 0;
    return result;
  }
  v8 = v18 - 1;
  v18 = v8;
  if ( (unsigned int)v8 >= 0x1C71C71 )
    return 2147942487LL;
  v9 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(144 * v8);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v11 = v18;
  v12 = 144LL * v18;
  if ( v12 )
  {
    do
    {
      LOBYTE(v9->pwszName) = 0;
      v9 = (struct tagHELPER_ATTRIBUTE *)((char *)v9 + 1);
      --v12;
    }
    while ( v12 );
    v11 = v18;
  }
  v19 = 0;
  v13 = 0;
  if ( v11 )
  {
    while ( 1 )
    {
      v14 = v13 + 1;
      ParameterByIndex = WdiGetParameterByIndex(*((_QWORD *)this + 1), v13 + 1, &v19);
      if ( ParameterByIndex < 0 )
        break;
      String2 = 0;
      if ( (int)GetNameFromWDI(v19, &String2) >= 0 && wcscmp_0(L"NdfOptions", String2) )
      {
        v16 = ParameterToAttribute(v19, &v10[v13]);
        if ( v16 < 0 )
        {
          CoTaskMemFree(v10);
          return (unsigned int)v16;
        }
        ++*a2;
      }
      CoTaskMemFree(String2);
      v13 = v14;
      if ( v14 >= v18 )
        goto LABEL_20;
    }
    CoTaskMemFree(v10);
    return (unsigned int)ParameterByIndex;
  }
  else
  {
LABEL_20:
    *a3 = v10;
    return 0;
  }
}

```

## disassembly

```asm
0x1800061c0  mov     [rsp-38h+arg_8], rbx
0x1800061c5  push    rbp
0x1800061c6  push    rsi
0x1800061c7  push    rdi
0x1800061c8  push    r12
0x1800061ca  push    r13
0x1800061cc  push    r14
0x1800061ce  push    r15
0x1800061d0  mov     rbp, rsp
0x1800061d3  sub     rsp, 30h
0x1800061d7  xor     r15d, r15d
0x1800061da  mov     r14, r8
0x1800061dd  mov     rdi, rdx
0x1800061e0  mov     r13, rcx
0x1800061e3  cmp     [rcx+8], r15
0x1800061e7  jnz     short loc_1800061F3
0x1800061e9  mov     eax, 80070006h
0x1800061ee  jmp     loc_18000632F
0x1800061f3  test    rdi, rdi
0x1800061f6  jz      loc_18000632A
0x1800061fc  test    r14, r14
0x1800061ff  jz      loc_18000632A
0x180006205  mov     [r8], r15
0x180006208  lea     rdx, [rbp+arg_0]
0x18000620c  mov     rcx, [rcx+8]
0x180006210  mov     [rbp+arg_0], r15d
0x180006214  call    cs:__imp_WdiGetParameterCount
0x18000621a  test    eax, eax
0x18000621c  js      loc_180006325
0x180006222  mov     ecx, [rbp+arg_0]
0x180006225  cmp     ecx, 1
0x180006228  jbe     loc_180006325
0x18000622e  dec     ecx
0x180006230  mov     [rbp+arg_0], ecx
0x180006233  cmp     ecx, 1C71C71h
0x180006239  jnb     loc_18000632A
0x18000623f  lea     rcx, [rcx+rcx*8]
0x180006243  shl     rcx, 4; cb
0x180006247  call    cs:__imp_CoTaskMemAlloc
0x18000624d  mov     rbx, rax
0x180006250  test    rax, rax
0x180006253  jnz     short loc_18000625F
0x180006255  mov     eax, 8007000Eh
0x18000625a  jmp     loc_18000632F
0x18000625f  mov     edx, [rbp+arg_0]
0x180006262  lea     rcx, [rdx+rdx*8]
0x180006266  shl     rcx, 4
0x18000626a  test    rcx, rcx
0x18000626d  jz      short loc_18000627E
0x18000626f  mov     [rax], r15b
0x180006272  inc     rax
0x180006275  sub     rcx, 1
0x180006279  jnz     short loc_18000626F
0x18000627b  mov     edx, [rbp+arg_0]
0x18000627e  mov     [rbp+arg_18], r15
0x180006282  mov     esi, r15d
0x180006285  test    edx, edx
0x180006287  jz      short loc_180006303
0x180006289  mov     rcx, [r13+8]
0x18000628d  lea     r12d, [rsi+1]
0x180006291  mov     edx, r12d
0x180006294  lea     r8, [rbp+arg_18]
0x180006298  call    cs:__imp_WdiGetParameterByIndex
0x18000629e  mov     r15d, eax
0x1800062a1  test    eax, eax
0x1800062a3  js      short loc_180006317
0x1800062a5  mov     rcx, [rbp+arg_18]; void *
0x1800062a9  lea     rdx, [rbp+String2]; unsigned __int16 **
0x1800062ad  mov     [rbp+String2], 0
0x1800062b5  call    ?GetNameFromWDI@@YAJPEAXPEAPEAG@Z; GetNameFromWDI(void *,ushort * *)
0x1800062ba  test    eax, eax
0x1800062bc  js      short loc_1800062F0
0x1800062be  mov     rdx, [rbp+String2]; String2
0x1800062c2  lea     rcx, aNdfoptions; "NdfOptions"
0x1800062c9  call    wcscmp_0
0x1800062ce  test    eax, eax
0x1800062d0  jz      short loc_1800062F0
0x1800062d2  mov     rcx, [rbp+arg_18]; void *
0x1800062d6  mov     eax, esi
0x1800062d8  lea     rdx, [rax+rax*8]
0x1800062dc  shl     rdx, 4
0x1800062e0  add     rdx, rbx; struct tagHELPER_ATTRIBUTE *
0x1800062e3  call    ?ParameterToAttribute@@YAJPEAXPEAUtagHELPER_ATTRIBUTE@@@Z; ParameterToAttribute(void *,tagHELPER_ATTRIBUTE *)
0x1800062e8  mov     esi, eax
0x1800062ea  test    eax, eax
0x1800062ec  js      short loc_18000630A
0x1800062ee  inc     dword ptr [rdi]
0x1800062f0  mov     rcx, [rbp+String2]; pv
0x1800062f4  call    cs:__imp_CoTaskMemFree
0x1800062fa  mov     esi, r12d
0x1800062fd  cmp     r12d, [rbp+arg_0]
0x180006301  jb      short loc_180006289
0x180006303  mov     [r14], rbx
0x180006306  xor     eax, eax
0x180006308  jmp     short loc_18000632F
0x18000630a  mov     rcx, rbx; pv
0x18000630d  call    cs:__imp_CoTaskMemFree
0x180006313  mov     eax, esi
0x180006315  jmp     short loc_18000632F
0x180006317  mov     rcx, rbx; pv
0x18000631a  call    cs:__imp_CoTaskMemFree
0x180006320  mov     eax, r15d
0x180006323  jmp     short loc_18000632F
0x180006325  mov     [rdi], r15d
0x180006328  jmp     short loc_18000632F
0x18000632a  mov     eax, 80070057h
0x18000632f  mov     rbx, [rsp+30h+arg_8]
0x180006334  add     rsp, 30h
0x180006338  pop     r15
0x18000633a  pop     r14
0x18000633c  pop     r13
0x18000633e  pop     r12
0x180006340  pop     rdi
0x180006341  pop     rsi
0x180006342  pop     rbp
0x180006343  retn
```
