# NPrintTicketUtil::CreateQName(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,ushort const *,ushort const *,ushort * *,ushort const *)

- ea: `0x1800070e0`
- end: `0x1800073de`
- name: `?CreateQName@NPrintTicketUtil@@YAJPEAVCPrintTicketWrapper@1@PEAUIXMLDOMElement@@PEBG2PEAPEAG2@Z`
- size: `766`
- prototype: `__int64 __usercall@<rax>(NPrintTicketUtil *__hidden this@<rcx>, struct IXMLDOMElement *@<rdx>, struct IXMLDOMElement *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003c20`
- `0x180006130`
- `0x1800064a0`
- `0x180006884`
- `0x180006b10`
- `0x180006c74`
- `0x180006d70`
- `0x180006f80`
- `0x1800077f0`
- `0x180007a04`
- `0x180009da8`
- `0x18000e084`
- `0x18001c060`
- `0x18001c2b0`
- `0x18001c37c`
- `0x18001f850`

## callees

- `0x1800070e0`
- `0x1800073e4`
- `0x180007660`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000719a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007315`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007345`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000719a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007315`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180007345`
- `OLEAUT32!__imp_SysFreeString` at `0x180007238`
- `OLEAUT32!__imp_SysFreeString` at `0x180007399`
- `OLEAUT32!__imp_SysFreeString` at `0x180007238`
- `OLEAUT32!__imp_SysFreeString` at `0x180007399`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CreateQName(
        NPrintTicketUtil *this,
        struct IXMLDOMElement *a2,
        struct IXMLDOMElement *a3,
        char *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v8; // r13
  OLECHAR *v9; // rbx
  int v12; // r12d
  int v13; // esi
  unsigned __int16 **v14; // rax
  const unsigned __int16 *v16; // r9
  int v17; // r10d
  char *v18; // rax
  int v19; // ecx
  int v20; // edx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // esi
  unsigned __int16 *v25; // rax
  signed int v26; // esi
  unsigned __int16 *v27; // rax

  v8 = a5;
  v9 = 0;
  a6 = 0;
  *(_QWORD *)a5 = 0;
  LODWORD(a5) = 0;
  if ( !a2 || !a4 )
  {
    v13 = -2147024809;
    goto LABEL_14;
  }
  v12 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, __int64))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          a2,
          1);
  if ( v13 >= 0 )
  {
    v12 = 1;
    v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, unsigned __int16 **))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            a4,
            0,
            0,
            &a5);
  }
  if ( !v13 )
  {
    LODWORD(a5) = (_DWORD)a5 + 1;
    v14 = (unsigned __int16 **)SysAllocStringLen(0, (UINT)a5);
    a6 = v14;
    v9 = (OLECHAR *)v14;
    if ( !v14 )
    {
      v13 = -2147024882;
      goto LABEL_11;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, unsigned __int16 **, unsigned __int16 **))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            a4,
            0,
            v14,
            &a5);
    if ( v13 < 0 )
    {
      SysFreeString(v9);
      v9 = 0;
      a6 = 0;
    }
  }
  if ( v13 == -2147467259 || v13 == 1 )
    v13 = 1;
LABEL_11:
  if ( v12 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
  if ( v13 >= 0 )
  {
    v16 = 0;
    if ( v9 )
      goto LABEL_28;
    v17 = 0;
    if ( L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework" )
    {
      do
      {
        if ( v16 )
          break;
        v18 = a4;
        do
        {
          v19 = *(unsigned __int16 *)&v18[(char *)off_180024330[2 * v17] - a4];
          v20 = *(unsigned __int16 *)v18 - v19;
          if ( v20 )
            break;
          v18 += 2;
        }
        while ( v19 );
        if ( !v20 )
          v16 = off_180024330[2 * v17 + 1];
        ++v17;
      }
      while ( off_180024330[2 * v17] );
    }
    v21 = NPrintTicketUtil::CPrintTicketWrapper::declarePrefix(this, a2, (OLECHAR *)a4, v16, (unsigned __int16 **)&a6);
    v9 = (OLECHAR *)a6;
    v13 = v21;
    if ( v21 < 0 )
      goto LABEL_14;
    if ( a6 )
    {
LABEL_28:
      v22 = -1;
      v23 = -1;
      do
        ++v23;
      while ( v9[v23] );
      do
        ++v22;
      while ( *((_WORD *)&a3->lpVtbl + v22) );
      if ( (int)v23 > 0 )
      {
        v26 = v22 + v23 + 2;
        v27 = SysAllocStringLen(0, v26);
        *(_QWORD *)v8 = v27;
        if ( v27 )
        {
          v13 = StringCchPrintfW(v27, v26, L"%s:%s", v9, a3);
          goto LABEL_14;
        }
        goto LABEL_33;
      }
    }
    else
    {
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)&a3->lpVtbl + v22) );
    }
    v24 = v22 + 1;
    v25 = SysAllocStringLen(0, (int)v22 + 1);
    *(_QWORD *)v8 = v25;
    if ( v25 )
    {
      v13 = StringCchPrintfW(v25, v24, L"%s", a3);
      goto LABEL_14;
    }
LABEL_33:
    v13 = -2147024882;
  }
LABEL_14:
  if ( v9 )
    SysFreeString(v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800070e0  mov     r11, rsp
0x1800070e3  push    rbx
0x1800070e4  push    rsi
0x1800070e5  sub     rsp, 48h
0x1800070e9  mov     [r11+8], rbp
0x1800070ed  xor     eax, eax
0x1800070ef  mov     [r11+10h], rdi
0x1800070f3  mov     rdi, r8
0x1800070f6  mov     [r11-18h], r13
0x1800070fa  mov     rbp, rcx
0x1800070fd  mov     r13, [rsp+58h+arg_20]
0x180007105  mov     ebx, eax
0x180007107  mov     [r11-20h], r14
0x18000710b  mov     r14, r9
0x18000710e  mov     [r11-28h], r15
0x180007112  mov     r15, rdx
0x180007115  mov     [r11+30h], rax
0x180007119  mov     [r13+0], rax
0x18000711d  mov     [r11+28h], eax
0x180007121  test    rdx, rdx
0x180007124  jz      loc_180007332
0x18000712a  test    r9, r9
0x18000712d  jz      loc_180007332
0x180007133  mov     rcx, [rcx+10h]
0x180007137  mov     r8d, 1
0x18000713d  mov     [r11+18h], r12
0x180007141  mov     r12d, eax
0x180007144  mov     rax, [rcx]
0x180007147  mov     rax, [rax+38h]
0x18000714b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007150  mov     esi, eax
0x180007152  test    eax, eax
0x180007154  js      short loc_180007184
0x180007156  mov     rcx, [rbp+10h]
0x18000715a  lea     rdx, [rsp+58h+arg_20]
0x180007162  mov     [rsp+58h+var_38], rdx
0x180007167  xor     r9d, r9d
0x18000716a  xor     r8d, r8d
0x18000716d  mov     rdx, r14
0x180007170  mov     r12d, 1
0x180007176  mov     rax, [rcx]
0x180007179  mov     rax, [rax+58h]
0x18000717d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007182  mov     esi, eax
0x180007184  test    esi, esi
0x180007186  jnz     short loc_1800071E4
0x180007188  mov     edx, dword ptr [rsp+58h+arg_20]
0x18000718f  xor     ecx, ecx; strIn
0x180007191  inc     edx; ui
0x180007193  mov     dword ptr [rsp+58h+arg_20], edx
0x18000719a  call    cs:__imp_SysAllocStringLen
0x1800071a0  mov     [rsp+58h+arg_28], rax
0x1800071a8  mov     rbx, rax
0x1800071ab  test    rax, rax
0x1800071ae  jz      loc_18000738C
0x1800071b4  mov     rcx, [rbp+10h]
0x1800071b8  lea     rdx, [rsp+58h+arg_20]
0x1800071c0  mov     [rsp+58h+var_38], rdx
0x1800071c5  mov     r9, rbx
0x1800071c8  xor     r8d, r8d
0x1800071cb  mov     rdx, r14
0x1800071ce  mov     rax, [rcx]
0x1800071d1  mov     rax, [rax+58h]
0x1800071d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071da  mov     esi, eax
0x1800071dc  test    eax, eax
0x1800071de  js      loc_180007396
0x1800071e4  cmp     esi, 80004005h
0x1800071ea  jz      loc_1800073AE
0x1800071f0  cmp     esi, 1
0x1800071f3  jz      loc_1800073AE
0x1800071f9  test    r12d, r12d
0x1800071fc  mov     r12, [rsp+58h+arg_10]
0x180007201  jz      short loc_180007213
0x180007203  mov     rcx, [rbp+10h]
0x180007207  mov     rax, [rcx]
0x18000720a  mov     rax, [rax+40h]
0x18000720e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007213  test    esi, esi
0x180007215  jns     short loc_180007247
0x180007217  mov     r15, [rsp+58h+var_28]
0x18000721c  mov     r14, [rsp+58h+var_20]
0x180007221  mov     r13, [rsp+58h+var_18]
0x180007226  mov     rdi, [rsp+58h+arg_8]
0x18000722b  mov     rbp, [rsp+58h+arg_0]
0x180007230  test    rbx, rbx
0x180007233  jz      short loc_18000723E
0x180007235  mov     rcx, rbx; bstrString
0x180007238  call    cs:__imp_SysFreeString
0x18000723e  mov     eax, esi
0x180007240  add     rsp, 48h
0x180007244  pop     rsi
0x180007245  pop     rbx
0x180007246  retn
0x180007247  xor     r9d, r9d; unsigned __int16 *
0x18000724a  test    rbx, rbx
0x18000724d  jnz     loc_1800072E7
0x180007253  xor     r10d, r10d
0x180007256  cmp     cs:off_180024330, r9; "http://schemas.microsoft.com/windows/20"...
0x18000725d  jz      short loc_1800072AC
0x18000725f  lea     rsi, off_180024330; "http://schemas.microsoft.com/windows/20"...
0x180007266  test    r9, r9
0x180007269  jnz     short loc_1800072AC
0x18000726b  movsxd  r11, r10d
0x18000726e  mov     rax, r14
0x180007271  add     r11, r11
0x180007274  mov     r8, [rsi+r11*8]
0x180007278  sub     r8, r14
0x18000727b  nop     dword ptr [rax+rax+00h]
0x180007280  movzx   edx, word ptr [rax]
0x180007283  movzx   ecx, word ptr [rax+r8]
0x180007288  sub     edx, ecx
0x18000728a  jnz     short loc_180007294
0x18000728c  add     rax, 2
0x180007290  test    ecx, ecx
0x180007292  jnz     short loc_180007280
0x180007294  test    edx, edx
0x180007296  jz      loc_1800073B8
0x18000729c  inc     r10d
0x18000729f  movsxd  rax, r10d
0x1800072a2  add     rax, rax
0x1800072a5  cmp     qword ptr [rsi+rax*8], 0
0x1800072aa  jnz     short loc_180007266
0x1800072ac  test    rbx, rbx
0x1800072af  jnz     short loc_1800072E7
0x1800072b1  lea     rax, [rsp+58h+arg_28]
0x1800072b9  mov     r8, r14; unsigned __int16 *
0x1800072bc  mov     rdx, r15; struct IXMLDOMElement *
0x1800072bf  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x1800072c4  mov     rcx, rbp; this
0x1800072c7  call    ?declarePrefix@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1PEAPEAG@Z; NPrintTicketUtil::CPrintTicketWrapper::declarePrefix(IXMLDOMElement *,ushort const *,ushort const *,ushort * *)
0x1800072cc  mov     rbx, [rsp+58h+arg_28]
0x1800072d4  mov     esi, eax
0x1800072d6  test    eax, eax
0x1800072d8  js      loc_180007217
0x1800072de  test    rbx, rbx
0x1800072e1  jz      loc_180007375
0x1800072e7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800072ee  mov     rcx, rax
0x1800072f1  inc     rcx
0x1800072f4  cmp     word ptr [rbx+rcx*2], 0
0x1800072f9  jnz     short loc_1800072F1
0x1800072fb  nop     dword ptr [rax+rax+00h]
0x180007300  inc     rax
0x180007303  cmp     word ptr [rdi+rax*2], 0
0x180007308  jnz     short loc_180007300
0x18000730a  test    ecx, ecx
0x18000730c  jg      short loc_18000733C
0x18000730e  lea     esi, [rax+1]
0x180007311  xor     ecx, ecx; strIn
0x180007313  mov     edx, esi; ui
0x180007315  call    cs:__imp_SysAllocStringLen
0x18000731b  mov     [r13+0], rax
0x18000731f  test    rax, rax
0x180007322  jnz     loc_1800073C2
0x180007328  mov     esi, 8007000Eh
0x18000732d  jmp     loc_180007217
0x180007332  mov     esi, 80070057h
0x180007337  jmp     loc_180007217
0x18000733c  lea     esi, [rcx+2]
0x18000733f  xor     ecx, ecx; strIn
0x180007341  add     esi, eax
0x180007343  mov     edx, esi; ui
0x180007345  call    cs:__imp_SysAllocStringLen
0x18000734b  mov     [r13+0], rax
0x18000734f  test    rax, rax
0x180007352  jz      short loc_180007328
0x180007354  movsxd  rdx, esi; unsigned __int64
0x180007357  lea     r8, aSS_0; "%s:%s"
0x18000735e  mov     r9, rbx
0x180007361  mov     [rsp+58h+var_38], rdi
0x180007366  mov     rcx, rax; unsigned __int16 *
0x180007369  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000736e  mov     esi, eax
0x180007370  jmp     loc_180007217
0x180007375  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000737c  nop     dword ptr [rax+00h]
0x180007380  inc     rax
0x180007383  cmp     word ptr [rdi+rax*2], 0
0x180007388  jnz     short loc_180007380
0x18000738a  jmp     short loc_18000730E
0x18000738c  mov     esi, 8007000Eh
0x180007391  jmp     loc_1800071F9
0x180007396  mov     rcx, rbx; bstrString
0x180007399  call    cs:__imp_SysFreeString
0x18000739f  xor     ebx, ebx
0x1800073a1  mov     [rsp+58h+arg_28], rbx
0x1800073a9  jmp     loc_1800071E4
0x1800073ae  mov     esi, 1
0x1800073b3  jmp     loc_1800071F9
0x1800073b8  mov     r9, [rsi+r11*8+8]
0x1800073bd  jmp     loc_18000729C
0x1800073c2  movsxd  rdx, esi; unsigned __int64
0x1800073c5  lea     r8, aS_0; "%s"
0x1800073cc  mov     r9, rdi
0x1800073cf  mov     rcx, rax; unsigned __int16 *
0x1800073d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800073d7  mov     esi, eax
0x1800073d9  jmp     loc_180007217
```
