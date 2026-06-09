# CWMDeColorConvDMO::GenVideoCCCreate(void * *,CC_OPS,tagBITMAPINFOHEADER *,tagBITMAPINFOHEADER *,int,long,long (**)(void *,uchar const *,uchar *,long,long,long,long),int)

- ea: `0x18000c8bc`
- end: `0x18000cb0a`
- name: `?GenVideoCCCreate@CWMDeColorConvDMO@@IEAAJPEAPEAXW4CC_OPS@@PEAUtagBITMAPINFOHEADER@@2HJPEAP6AJPEAXPEBEPEAEJJJJ@ZH@Z`
- size: `590`
- prototype: `__int64 __fastcall(__int64, void **, int, const struct tagBITMAPINFOHEADER *, struct tagBITMAPINFOHEADER *, int, LONG, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cbb0`

## callees

- `0x18000c8bc`
- `0x1800149ec`
- `0x180014a18`
- `0x180014d84`
- `0x180014e50`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::GenVideoCCCreate(
        __int64 a1,
        void **a2,
        int a3,
        const struct tagBITMAPINFOHEADER *a4,
        struct tagBITMAPINFOHEADER *a5,
        int a6,
        LONG a7,
        _QWORD *a8)
{
  int *v8; // r8
  int *v12; // rdx
  int v13; // ebp
  int v14; // r9d
  int v15; // esi
  int *v16; // r14
  int v17; // r15d
  int *v18; // r12
  int v19; // r13d
  int biHeight; // ecx
  LONG v21; // ecx
  _QWORD *v22; // rax
  __int64 result; // rax
  BOOL v24; // esi
  bool v25; // zf
  int v26; // ebp
  unsigned __int64 v27; // rdx
  int v28; // r14d
  int v29; // r8d
  int v30; // r9d
  void *v31; // rax
  struct tagBITMAPINFOHEADER *v32; // r8
  const struct tagBITMAPINFOHEADER *v33; // rdx
  int v34; // eax
  int v35; // [rsp+20h] [rbp-88h]
  int v36; // [rsp+50h] [rbp-58h]
  int v37; // [rsp+C0h] [rbp+18h] BYREF

  v37 = a3;
  v8 = (int *)(a1 + 604);
  if ( *(_DWORD *)(a1 + 600) )
  {
    if ( *v8 < 0 )
      goto LABEL_16;
    v12 = (int *)(a1 + 608);
    v13 = *(_DWORD *)(a1 + 608);
    if ( v13 < 0 )
      goto LABEL_16;
    v14 = *(_DWORD *)(a1 + 620);
    if ( v14 <= 0 )
      goto LABEL_16;
    v15 = *(_DWORD *)(a1 + 624);
    if ( v15 <= 0 )
      goto LABEL_16;
    v16 = (int *)(a1 + 612);
    v17 = *(_DWORD *)(a1 + 612);
    if ( v17 < 0 )
      goto LABEL_16;
    v18 = (int *)(a1 + 616);
    v19 = *(_DWORD *)(a1 + 616);
    if ( v19 < 0 || v14 + *v8 > a4->biWidth )
      goto LABEL_16;
    biHeight = -a4->biHeight;
    if ( a4->biHeight > 0 )
      biHeight = a4->biHeight;
    if ( v15 + v13 > biHeight || v17 + v14 > a5->biWidth )
      goto LABEL_16;
    v21 = -a5->biHeight;
    if ( a5->biHeight > 0 )
      v21 = a5->biHeight;
    if ( v15 + v19 > v21 )
    {
LABEL_16:
      v22 = a8;
      *a2 = 0;
      *v22 = 0;
      return 2147942487LL;
    }
  }
  else
  {
    v12 = (int *)(a1 + 608);
    v16 = (int *)(a1 + 612);
    v18 = (int *)(a1 + 616);
  }
  v24 = a7 && a7 != a5->biWidth;
  if ( a6 )
  {
    if ( a6 != 1 )
      return 2147500037LL;
    v16 = v8;
    v18 = v12;
  }
  v25 = *(_DWORD *)(a1 + 600) == 0;
  v26 = *v18;
  v27 = (unsigned int)*v12;
  v28 = *v16;
  v29 = *v8;
  v30 = *(_DWORD *)(a1 + 632);
  v37 = 0;
  if ( !v25 )
  {
    v31 = directVideoCCCreateWithFullCropping(
            (enum tagColorConvertStatus *)&v37,
            a4,
            a5,
            v29,
            v27,
            v28,
            v26,
            *(_DWORD *)(a1 + 620),
            *(_DWORD *)(a1 + 624),
            v30,
            v36);
    goto LABEL_37;
  }
  if ( !v24 )
  {
    v32 = a5;
    v33 = a4;
LABEL_36:
    v31 = directVideoCCCreate((enum tagColorConvertStatus *)&v37, v33, v32, v30, v35);
    goto LABEL_37;
  }
  if ( a7 <= 0 )
  {
    v31 = 0;
    goto LABEL_37;
  }
  v32 = a5;
  v33 = a4;
  if ( a7 >= a4->biWidth )
    goto LABEL_36;
  v34 = -a4->biHeight;
  if ( a4->biHeight > 0 )
    v34 = a4->biHeight;
  v31 = directVideoCCCreateWithFullCropping((enum tagColorConvertStatus *)&v37, a4, a5, 0, 0, 0, 0, a7, v34, v30, v36);
LABEL_37:
  *a2 = v31;
  if ( !v31 )
    return 2147500037LL;
  *a8 = CallDirectCCColorConv;
  if ( *(_DWORD *)(a1 + 1148) )
  {
    if ( (unsigned int)setColorConvThreadClass(*a2, v27, (unsigned __int16 *)(a1 + 636), *(_DWORD *)(a1 + 1152)) )
      return 2147500037LL;
  }
  result = setMMCSSRegisterCC(*a2, *(_DWORD *)(a1 + 1148));
  if ( (_DWORD)result )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x18000c8bc  mov     [rsp+arg_10], r8d
0x18000c8c1  push    rbx
0x18000c8c2  push    rbp
0x18000c8c3  push    rsi
0x18000c8c4  push    rdi
0x18000c8c5  push    r12
0x18000c8c7  push    r13
0x18000c8c9  push    r14
0x18000c8cb  push    r15
0x18000c8cd  sub     rsp, 68h
0x18000c8d1  cmp     dword ptr [rcx+258h], 0
0x18000c8d8  lea     r8, [rcx+25Ch]
0x18000c8df  mov     r11, [rsp+0A8h+arg_20]
0x18000c8e7  mov     r10, r9
0x18000c8ea  mov     rdi, rdx
0x18000c8ed  mov     rbx, rcx
0x18000c8f0  jz      loc_18000C997
0x18000c8f6  mov     eax, [r8]
0x18000c8f9  test    eax, eax
0x18000c8fb  js      short loc_18000C977
0x18000c8fd  lea     rdx, [rcx+260h]
0x18000c904  mov     ebp, [rdx]
0x18000c906  test    ebp, ebp
0x18000c908  js      short loc_18000C977
0x18000c90a  mov     r9d, [rcx+26Ch]
0x18000c911  test    r9d, r9d
0x18000c914  jle     short loc_18000C977
0x18000c916  mov     esi, [rcx+270h]
0x18000c91c  test    esi, esi
0x18000c91e  jle     short loc_18000C977
0x18000c920  lea     r14, [rcx+264h]
0x18000c927  mov     r15d, [r14]
0x18000c92a  test    r15d, r15d
0x18000c92d  js      short loc_18000C977
0x18000c92f  lea     r12, [rcx+268h]
0x18000c936  mov     r13d, [r12]
0x18000c93a  test    r13d, r13d
0x18000c93d  js      short loc_18000C977
0x18000c93f  add     eax, r9d
0x18000c942  cmp     eax, [r10+4]
0x18000c946  jg      short loc_18000C977
0x18000c948  mov     ecx, [r10+8]
0x18000c94c  lea     eax, [rsi+rbp]
0x18000c94f  neg     ecx
0x18000c951  cmovs   ecx, [r10+8]
0x18000c956  cmp     eax, ecx
0x18000c958  jg      short loc_18000C977
0x18000c95a  lea     eax, [r15+r9]
0x18000c95e  cmp     eax, [r11+4]
0x18000c962  jg      short loc_18000C977
0x18000c964  mov     ecx, [r11+8]
0x18000c968  lea     eax, [rsi+r13]
0x18000c96c  neg     ecx
0x18000c96e  cmovs   ecx, [r11+8]
0x18000c973  cmp     eax, ecx
0x18000c975  jle     short loc_18000C9AC
0x18000c977  mov     rax, [rsp+0A8h+arg_38]
0x18000c97f  mov     qword ptr [rdi], 0
0x18000c986  mov     qword ptr [rax], 0
0x18000c98d  mov     eax, 80070057h
0x18000c992  jmp     loc_18000CAF9
0x18000c997  lea     rdx, [rcx+260h]
0x18000c99e  lea     r14, [rcx+264h]
0x18000c9a5  lea     r12, [rcx+268h]
0x18000c9ac  mov     ecx, [rsp+0A8h+arg_30]
0x18000c9b3  test    ecx, ecx
0x18000c9b5  jz      short loc_18000C9C4
0x18000c9b7  cmp     ecx, [r11+4]
0x18000c9bb  jz      short loc_18000C9C4
0x18000c9bd  mov     esi, 1
0x18000c9c2  jmp     short loc_18000C9C6
0x18000c9c4  xor     esi, esi
0x18000c9c6  mov     eax, [rsp+0A8h+arg_28]
0x18000c9cd  test    eax, eax
0x18000c9cf  jz      short loc_18000C9E0
0x18000c9d1  cmp     eax, 1
0x18000c9d4  jnz     loc_18000CAF4
0x18000c9da  mov     r14, r8
0x18000c9dd  mov     r12, rdx
0x18000c9e0  cmp     dword ptr [rbx+258h], 0
0x18000c9e7  mov     ebp, [r12]
0x18000c9eb  mov     edx, [rdx]
0x18000c9ed  mov     r14d, [r14]
0x18000c9f0  mov     r8d, [r8]
0x18000c9f3  mov     r9d, [rbx+278h]; int
0x18000c9fa  mov     [rsp+0A8h+arg_10], 0
0x18000ca05  jz      short loc_18000CA45
0x18000ca07  mov     eax, [rbx+270h]
0x18000ca0d  mov     [rsp+0A8h+var_60], r9d; int
0x18000ca12  mov     r9d, r8d; int
0x18000ca15  mov     [rsp+0A8h+var_68], eax; int
0x18000ca19  mov     r8, r11; struct tagBITMAPINFOHEADER *
0x18000ca1c  mov     eax, [rbx+26Ch]
0x18000ca22  mov     [rsp+0A8h+var_70], eax; int
0x18000ca26  mov     [rsp+0A8h+var_78], ebp; int
0x18000ca2a  mov     [rsp+0A8h+var_80], r14d; int
0x18000ca2f  mov     [rsp+0A8h+var_88], edx; int
0x18000ca33  mov     rdx, r10; struct tagBITMAPINFOHEADER *
0x18000ca36  lea     rcx, [rsp+0A8h+arg_10]; enum tagColorConvertStatus *
0x18000ca3e  call    ?directVideoCCCreateWithFullCropping@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1JJJJJJJH@Z; directVideoCCCreateWithFullCropping(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,long,long,long,long,long,long,long,int)
0x18000ca43  jmp     short loc_18000CAA5
0x18000ca45  test    esi, esi
0x18000ca47  jz      short loc_18000CA92
0x18000ca49  test    ecx, ecx
0x18000ca4b  jg      short loc_18000CA51
0x18000ca4d  xor     eax, eax
0x18000ca4f  jmp     short loc_18000CAA5
0x18000ca51  mov     r8, r11
0x18000ca54  mov     rdx, r10
0x18000ca57  cmp     ecx, [r10+4]
0x18000ca5b  jge     short loc_18000CA98
0x18000ca5d  mov     eax, [r10+8]
0x18000ca61  mov     [rsp+0A8h+var_60], r9d
0x18000ca66  neg     eax
0x18000ca68  cmovs   eax, [r10+8]
0x18000ca6d  xor     r9d, r9d
0x18000ca70  mov     [rsp+0A8h+var_68], eax
0x18000ca74  mov     [rsp+0A8h+var_70], ecx
0x18000ca78  mov     [rsp+0A8h+var_78], 0
0x18000ca80  mov     [rsp+0A8h+var_80], 0
0x18000ca88  mov     [rsp+0A8h+var_88], 0
0x18000ca90  jmp     short loc_18000CA36
0x18000ca92  mov     r8, r11; struct tagBITMAPINFOHEADER *
0x18000ca95  mov     rdx, r10; struct tagBITMAPINFOHEADER *
0x18000ca98  lea     rcx, [rsp+0A8h+arg_10]; enum tagColorConvertStatus *
0x18000caa0  call    ?directVideoCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1JH@Z; directVideoCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,long,int)
0x18000caa5  mov     [rdi], rax
0x18000caa8  test    rax, rax
0x18000caab  jz      short loc_18000CAF4
0x18000caad  mov     rax, [rsp+0A8h+arg_38]
0x18000cab5  lea     rcx, ?CallDirectCCColorConv@@YAJPEAXPEBEPEAEJJJJ@Z; CallDirectCCColorConv(void *,uchar const *,uchar *,long,long,long,long)
0x18000cabc  mov     [rax], rcx
0x18000cabf  cmp     dword ptr [rbx+47Ch], 0
0x18000cac6  jz      short loc_18000CAE2
0x18000cac8  mov     r9d, [rbx+480h]; unsigned int
0x18000cacf  lea     r8, [rbx+27Ch]; unsigned __int16 *
0x18000cad6  mov     rcx, [rdi]; void *
0x18000cad9  call    ?setColorConvThreadClass@@YAJPEAX_KPEAGK@Z; setColorConvThreadClass(void *,unsigned __int64,ushort *,ulong)
0x18000cade  test    eax, eax
0x18000cae0  jnz     short loc_18000CAF4
0x18000cae2  mov     rcx, [rdi]; void *
0x18000cae5  mov     edx, [rbx+47Ch]; int
0x18000caeb  call    ?setMMCSSRegisterCC@@YAJPEAXH@Z; setMMCSSRegisterCC(void *,int)
0x18000caf0  test    eax, eax
0x18000caf2  jz      short loc_18000CAF9
0x18000caf4  mov     eax, 80004005h
0x18000caf9  add     rsp, 68h
0x18000cafd  pop     r15
0x18000caff  pop     r14
0x18000cb01  pop     r13
0x18000cb03  pop     r12
0x18000cb05  pop     rdi
0x18000cb06  pop     rsi
0x18000cb07  pop     rbp
0x18000cb08  pop     rbx
0x18000cb09  retn
```
