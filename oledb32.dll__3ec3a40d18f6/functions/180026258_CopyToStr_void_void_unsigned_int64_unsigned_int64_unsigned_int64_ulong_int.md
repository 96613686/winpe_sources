# CopyToStr(void *,void *,unsigned __int64,unsigned __int64 *,unsigned __int64,ulong *,int)

- ea: `0x180026258`
- end: `0x18002637b`
- name: `?CopyToStr@@YAJPEAX0_KPEA_K1PEAKH@Z`
- size: `291`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, unsigned __int64@<r8>, unsigned __int64 *@<r9>, unsigned __int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003320`

## callees

- `0x180013870`
- `0x180026258`
- `0x180029560`
- `0x18002ec26`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180026284`
- `ole32!CoTaskMemAlloc` at `0x180026284`
- `ole32!CoTaskMemFree` at `0x1800262fd`
- `ole32!CoTaskMemFree` at `0x1800262fd`

## string_xrefs

- `0x1800262a7`: `<CopyToStr|OLEDB|ERR> `
- `0x1800262c6`: `<CopyToStr|Trace|HR> `
- `0x180026365`: `<CopyToStr|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CopyToStr(
        void *Src,
        _QWORD *a2,
        size_t a3,
        unsigned __int64 *a4,
        unsigned __int64 a5,
        unsigned int *a6,
        int a7)
{
  _QWORD *v8; // rbx
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rax
  unsigned int v13; // ebx

  v8 = a2;
  *a4 = a3;
  if ( !a7 )
  {
    v11 = a5;
LABEL_9:
    if ( v11 )
    {
      if ( a3 >= v11 )
      {
        *a6 = 4;
        memcpy_0(v8, Src, v11 - 1);
        *((_BYTE *)v8 + v11 - 1) = 0;
      }
      else
      {
        memcpy_0(v8, Src, a3);
        *((_BYTE *)v8 + a3) = 0;
      }
      if ( (bidGblFlags & 2) != 0 )
        return bidTraceHR(off_1800C8390[0], 10003465, L"<CopyToStr|Trace|HR> ", 0);
    }
    else
    {
      if ( a7 )
      {
        CoTaskMemFree(v8);
        *a2 = 0;
      }
      *a6 = 6;
    }
    return 0;
  }
  v11 = a3 + 1;
  v12 = CoTaskMemAlloc(a3 + 1);
  *v8 = v12;
  if ( v12 )
  {
    v8 = v12;
    goto LABEL_9;
  }
  v13 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147024882, L"<CopyToStr|OLEDB|ERR> ", 0x2602u);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(off_1800C8390[0], 9963529, L"<CopyToStr|Trace|HR> ", 2147942414LL);
  }
  return v13;
}

```

## disassembly

```asm
0x180026258  push    rbx
0x18002625a  push    rsi
0x18002625b  push    rdi
0x18002625c  push    r14
0x18002625e  push    r15
0x180026260  sub     rsp, 20h
0x180026264  cmp     [rsp+48h+arg_30], 0
0x18002626c  mov     rsi, r8
0x18002626f  mov     rbx, rdx
0x180026272  mov     [r9], r8
0x180026275  mov     r14, rcx
0x180026278  mov     r15, rdx
0x18002627b  jz      short loc_1800262E5
0x18002627d  lea     rdi, [r8+1]
0x180026281  mov     rcx, rdi; cb
0x180026284  call    cs:__imp_CoTaskMemAlloc
0x18002628a  mov     [rbx], rax
0x18002628d  test    rax, rax
0x180026290  jnz     short loc_1800262E0
0x180026292  mov     eax, cs:_bidGblFlags
0x180026298  mov     ebx, 8007000Eh
0x18002629d  test    al, 2
0x18002629f  jz      short loc_1800262DC
0x1800262a1  mov     r8d, 2602h; unsigned int
0x1800262a7  lea     rdx, aCopytostrOledb; "<CopyToStr|OLEDB|ERR> "
0x1800262ae  mov     ecx, ebx; int
0x1800262b0  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800262b5  mov     eax, cs:_bidGblFlags
0x1800262bb  test    al, 2
0x1800262bd  jz      short loc_1800262DC
0x1800262bf  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800262c6  lea     r8, aCopytostrTrace; "<CopyToStr|Trace|HR> "
0x1800262cd  mov     r9d, ebx
0x1800262d0  mov     edx, 980809h
0x1800262d5  call    _bidTraceHR
0x1800262da  mov     ebx, eax
0x1800262dc  mov     eax, ebx
0x1800262de  jmp     short loc_180026317
0x1800262e0  mov     rbx, rax
0x1800262e3  jmp     short loc_1800262EA
0x1800262e5  mov     rdi, [rsp+48h+arg_20]
0x1800262ea  cmp     rdi, 1
0x1800262ee  jnb     short loc_180026323
0x1800262f0  cmp     [rsp+48h+arg_30], 0
0x1800262f8  jz      short loc_18002630A
0x1800262fa  mov     rcx, rbx; pv
0x1800262fd  call    cs:__imp_CoTaskMemFree
0x180026303  mov     qword ptr [r15], 0
0x18002630a  mov     rax, [rsp+48h+arg_28]
0x18002630f  mov     dword ptr [rax], 6
0x180026315  xor     eax, eax
0x180026317  add     rsp, 20h
0x18002631b  pop     r15
0x18002631d  pop     r14
0x18002631f  pop     rdi
0x180026320  pop     rsi
0x180026321  pop     rbx
0x180026322  retn
0x180026323  mov     rdx, r14; Src
0x180026326  mov     rcx, rbx; void *
0x180026329  cmp     rsi, rdi
0x18002632c  jnb     short loc_18002633C
0x18002632e  mov     r8, rsi; Size
0x180026331  call    memcpy_0
0x180026336  mov     byte ptr [rbx+rsi], 0
0x18002633a  jmp     short loc_180026355
0x18002633c  mov     rax, [rsp+48h+arg_28]
0x180026341  lea     r8, [rdi-1]; Size
0x180026345  mov     dword ptr [rax], 4
0x18002634b  call    memcpy_0
0x180026350  mov     byte ptr [rbx+rdi-1], 0
0x180026355  test    byte ptr cs:_bidGblFlags, 2
0x18002635c  jz      short loc_180026315
0x18002635e  mov     rcx, cs:off_1800C8390; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180026365  lea     r8, aCopytostrTrace; "<CopyToStr|Trace|HR> "
0x18002636c  xor     r9d, r9d
0x18002636f  mov     edx, 98A409h
0x180026374  call    _bidTraceHR
0x180026379  jmp     short loc_180026317
```
