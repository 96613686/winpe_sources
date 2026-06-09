# CreateMPMallocCopyOfProps(ulong,tagDBPROPSET *,ulong *,tagDBPROPSET * *,bool)

- ea: `0x18000feec`
- end: `0x1800100bb`
- name: `?CreateMPMallocCopyOfProps@@YAJKPEAUtagDBPROPSET@@PEAKPEAPEAU1@_N@Z`
- size: `463`
- prototype: `__int64 __fastcall(unsigned int, struct tagDBPROPSET *, unsigned int *, struct tagDBPROPSET **, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800100c4`
- `0x18006f554`

## callees

- `0x18000feec`
- `0x180011bf0`
- `0x180013394`
- `0x180013870`
- `0x180029560`

## import_xrefs

- `MSDART!mpMalloc` at `0x18000ff1a`
- `MSDART!mpMalloc` at `0x18000ff62`
- `MSDART!mpMalloc` at `0x18000ff1a`
- `MSDART!mpMalloc` at `0x18000ff62`
- `OLEAUT32!__imp_VariantInit` at `0x18000ff91`
- `OLEAUT32!__imp_VariantInit` at `0x18000ff91`

## string_xrefs

- `0x18000fff0`: `<CreateMPMallocCopyOfProps|OLEDB|ERR> `
- `0x18001000f`: `<CreateMPMallocCopyOfProps|Trace|HR> `
- `0x180010050`: `<CreateMPMallocCopyOfProps|Trace|HR> `
- `0x180010092`: `<CreateMPMallocCopyOfProps|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CreateMPMallocCopyOfProps(
        unsigned int a1,
        struct tagDBPROPSET *a2,
        unsigned int *a3,
        struct tagDBPROPSET **a4)
{
  int v4; // ebx
  struct tagDBPROPSET *v8; // rsi
  struct tagDBPROPSET *v9; // rax
  __int64 v10; // rdx
  struct tagDBPROPSET *v11; // rdi
  unsigned int v12; // r13d
  __int64 v13; // rax
  struct tagDBPROP *v14; // rbp
  ULONG v15; // eax
  __int64 v16; // rdx
  struct tagDBPROP *rgProperties; // [rsp+20h] [rbp-58h]
  ULONG v20; // [rsp+A0h] [rbp+28h]

  v4 = 0;
  v8 = a2;
  if ( a1 )
  {
    v9 = (struct tagDBPROPSET *)mpMalloc(32LL * a1, a2);
    v11 = v9;
    if ( v9 )
    {
      *a4 = v9;
      v12 = 0;
      while ( v12 < a1 )
      {
        *a3 = ++v12;
        v11->cProperties = 0;
        v11->guidPropertySet = v8->guidPropertySet;
        if ( v8->cProperties )
        {
          v13 = mpMalloc(72LL * v8->cProperties, v10);
          v11->rgProperties = (DBPROP *)v13;
          v14 = (struct tagDBPROP *)v13;
          if ( !v13 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_21;
            v16 = 2248713;
            goto LABEL_20;
          }
          rgProperties = v8->rgProperties;
          v15 = 0;
          while ( 1 )
          {
            v20 = v15;
            if ( v15 >= v8->cProperties )
              break;
            VariantInit(&v14->vValue);
            v4 = CopyProperty(v14, rgProperties, 0, 0);
            if ( v4 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v4, L"<CreateMPMallocCopyOfProps|OLEDB|ERR> ", 0x88Cu);
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceHR(off_1800C84F0[0], 2240521, L"<CreateMPMallocCopyOfProps|Trace|HR> ", (unsigned int)v4);
              }
              goto LABEL_23;
            }
            ++v11->cProperties;
            v15 = v20 + 1;
            ++rgProperties;
            ++v14;
          }
        }
        else
        {
          v11->rgProperties = 0;
        }
        ++v8;
        ++v11;
      }
    }
    else
    {
      *a3 = 0;
      *a4 = 0;
      if ( (bidGblFlags & 2) != 0 )
      {
        v16 = 2262025;
LABEL_20:
        v4 = bidTraceHR(off_1800C84F0[0], v16, L"<CreateMPMallocCopyOfProps|Trace|HR> ", 2147942414LL);
      }
      else
      {
LABEL_21:
        v4 = -2147024882;
      }
    }
    if ( v4 < 0 )
LABEL_23:
      FreeMPMallocedPropSets(*a3, *a4);
  }
  else
  {
    *a3 = 0;
    *a4 = 0;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C84F0[0],
                           2277385,
                           L"<CreateMPMallocCopyOfProps|Trace|HR> ",
                           (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000feec  push    rbx
0x18000feee  push    rbp
0x18000feef  push    rsi
0x18000fef0  push    rdi
0x18000fef1  push    r12
0x18000fef3  push    r13
0x18000fef5  push    r14
0x18000fef7  push    r15
0x18000fef9  sub     rsp, 38h
0x18000fefd  xor     ebx, ebx
0x18000feff  mov     r12d, ecx
0x18000ff02  mov     r14, r9
0x18000ff05  mov     r15, r8
0x18000ff08  mov     rsi, rdx
0x18000ff0b  test    ecx, ecx
0x18000ff0d  jz      loc_18001007C
0x18000ff13  mov     ecx, r12d
0x18000ff16  shl     rcx, 5
0x18000ff1a  call    cs:__imp_mpMalloc
0x18000ff20  mov     rdi, rax
0x18000ff23  test    rax, rax
0x18000ff26  jz      loc_180010035
0x18000ff2c  mov     [r14], rax
0x18000ff2f  xor     r13d, r13d
0x18000ff32  cmp     r13d, r12d
0x18000ff35  jnb     loc_18001006B
0x18000ff3b  inc     r13d
0x18000ff3e  mov     [r15], r13d
0x18000ff41  mov     dword ptr [rdi+8], 0
0x18000ff48  movups  xmm0, xmmword ptr [rsi+0Ch]
0x18000ff4c  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x18000ff51  cmp     dword ptr [rsi+8], 0
0x18000ff55  jz      short loc_18000FFC8
0x18000ff57  mov     eax, [rsi+8]
0x18000ff5a  lea     rcx, [rax+rax*8]
0x18000ff5e  shl     rcx, 3
0x18000ff62  call    cs:__imp_mpMalloc
0x18000ff68  mov     [rdi], rax
0x18000ff6b  mov     rbp, rax
0x18000ff6e  test    rax, rax
0x18000ff71  jz      loc_180010025
0x18000ff77  mov     rax, [rsi]
0x18000ff7a  mov     [rsp+78h+var_58], rax
0x18000ff7f  xor     eax, eax
0x18000ff81  mov     dword ptr [rsp+78h+arg_20], eax
0x18000ff88  cmp     eax, [rsi+8]
0x18000ff8b  jnb     short loc_18000FFCF
0x18000ff8d  lea     rcx, [rbp+30h]; pvarg
0x18000ff91  call    cs:__imp_VariantInit
0x18000ff97  mov     rdx, [rsp+78h+var_58]; struct tagDBPROP *
0x18000ff9c  xor     r9d, r9d; unsigned int
0x18000ff9f  xor     r8d, r8d; bool
0x18000ffa2  mov     rcx, rbp; struct tagDBPROP *
0x18000ffa5  call    ?CopyProperty@@YAJPEAUtagDBPROP@@PEBU1@_NK@Z; CopyProperty(tagDBPROP *,tagDBPROP const *,bool,ulong)
0x18000ffaa  mov     ebx, eax
0x18000ffac  test    eax, eax
0x18000ffae  js      short loc_18000FFDC
0x18000ffb0  mov     eax, dword ptr [rsp+78h+arg_20]
0x18000ffb7  inc     dword ptr [rdi+8]
0x18000ffba  inc     eax
0x18000ffbc  add     [rsp+78h+var_58], 48h ; 'H'
0x18000ffc2  add     rbp, 48h ; 'H'
0x18000ffc6  jmp     short loc_18000FF81
0x18000ffc8  mov     qword ptr [rdi], 0
0x18000ffcf  add     rsi, 20h ; ' '
0x18000ffd3  add     rdi, 20h ; ' '
0x18000ffd7  jmp     loc_18000FF32
0x18000ffdc  mov     eax, cs:_bidGblFlags
0x18000ffe2  test    al, 2
0x18000ffe4  jz      loc_18001006F
0x18000ffea  mov     r8d, 88Ch; unsigned int
0x18000fff0  lea     rdx, aCreatempmalloc_0; "<CreateMPMallocCopyOfProps|OLEDB|ERR> "
0x18000fff7  mov     ecx, ebx; int
0x18000fff9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18000fffe  mov     eax, cs:_bidGblFlags
0x180010004  test    al, 2
0x180010006  jz      short loc_18001006F
0x180010008  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001000f  lea     r8, aCreatempmalloc; "<CreateMPMallocCopyOfProps|Trace|HR> "
0x180010016  mov     r9d, ebx
0x180010019  mov     edx, 223009h
0x18001001e  call    _bidTraceHR
0x180010023  jmp     short loc_18001006F
0x180010025  test    byte ptr cs:_bidGblFlags, 2
0x18001002c  jz      short loc_180010066
0x18001002e  mov     edx, 225009h
0x180010033  jmp     short loc_180010049
0x180010035  mov     [r15], ebx
0x180010038  mov     [r14], rbx
0x18001003b  test    byte ptr cs:_bidGblFlags, 2
0x180010042  jz      short loc_180010066
0x180010044  mov     edx, 228409h
0x180010049  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180010050  lea     r8, aCreatempmalloc; "<CreateMPMallocCopyOfProps|Trace|HR> "
0x180010057  mov     r9d, 8007000Eh
0x18001005d  call    _bidTraceHR
0x180010062  mov     ebx, eax
0x180010064  jmp     short loc_18001006B
0x180010066  mov     ebx, 8007000Eh
0x18001006b  test    ebx, ebx
0x18001006d  jns     short loc_180010082
0x18001006f  mov     rdx, [r14]; struct tagDBPROPSET *
0x180010072  mov     ecx, [r15]; unsigned int
0x180010075  call    ?FreeMPMallocedPropSets@@YAXKPEAUtagDBPROPSET@@@Z; FreeMPMallocedPropSets(ulong,tagDBPROPSET *)
0x18001007a  jmp     short loc_180010082
0x18001007c  mov     [r8], ebx
0x18001007f  mov     [r9], rbx
0x180010082  test    byte ptr cs:_bidGblFlags, 2
0x180010089  jz      short loc_1800100A8
0x18001008b  mov     rcx, cs:off_1800C84F0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180010092  lea     r8, aCreatempmalloc; "<CreateMPMallocCopyOfProps|Trace|HR> "
0x180010099  mov     r9d, ebx
0x18001009c  mov     edx, 22C009h
0x1800100a1  call    _bidTraceHR
0x1800100a6  mov     ebx, eax
0x1800100a8  mov     eax, ebx
0x1800100aa  add     rsp, 38h
0x1800100ae  pop     r15
0x1800100b0  pop     r14
0x1800100b2  pop     r13
0x1800100b4  pop     r12
0x1800100b6  pop     rdi
0x1800100b7  pop     rsi
0x1800100b8  pop     rbp
0x1800100b9  pop     rbx
0x1800100ba  retn
```
