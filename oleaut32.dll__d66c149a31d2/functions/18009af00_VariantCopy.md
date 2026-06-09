# VariantCopy

- ea: `0x18009af00`
- end: `0x18009b1c2`
- name: `VariantCopy`
- size: `706`
- prototype: `HRESULT __stdcall(VARIANTARG *pvargDest, const VARIANTARG *pvargSrc)`
- caller_count: `10`
- callee_count: `9`
- tags: ``

## callers

- `0x1800078c0`
- `0x180009ed0`
- `0x18000a360`
- `0x18000ced0`
- `0x18001fa50`
- `0x180025000`
- `0x180074290`
- `0x180075200`
- `0x180075d50`
- `0x18009ac70`

## callees

- `0x1800039b8`
- `0x18000a920`
- `0x18001f470`
- `0x18004dd00`
- `0x18004e530`
- `0x18009a624`
- `0x18009af00`
- `0x18009b1d0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009afd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b15d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009afd0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b15d`

## pseudocode

```c
HRESULT __stdcall VariantCopy(VARIANTARG *pvargDest, const VARIANTARG *pvargSrc)
{
  unsigned int vt; // esi
  __int16 v4; // di
  HRESULT result; // eax
  BSTR bstrVal; // rsi
  unsigned int v8; // edi
  int v9; // ebx
  LONGLONG llVal; // rcx
  APP_DATA *Value; // rax
  char *v12; // rax
  char *v13; // rbx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  IRecordInfo *pRecInfo; // rax
  IRecordInfo *v17; // rcx
  LONGLONG v18; // rax
  void *v19; // rax
  IRecordInfo *v20; // rcx
  size_t Size; // [rsp+48h] [rbp+10h] BYREF

  vt = pvargSrc->vt;
  v4 = vt & 0x6000;
  if ( vt >= 0xC )
  {
    v14 = (unsigned __int16)vt;
    LOWORD(v14) = vt & 0x9FFF;
    if ( !v4 )
      LOWORD(v14) = pvargSrc->vt;
    if ( (unsigned __int16)v14 > 0x24u )
      return -2147352568;
    v15 = 0x1000FF7FFCLL;
    if ( !_bittest64(&v15, v14) )
      return -2147352568;
  }
  if ( pvargDest == pvargSrc )
    return 0;
  result = VariantClear(pvargDest);
  if ( result <= -1 )
    return result;
  if ( v4 != 0x2000 )
  {
    if ( vt == 8 )
    {
      bstrVal = pvargSrc->bstrVal;
      if ( bstrVal )
      {
        v8 = *((_DWORD *)bstrVal - 1);
        v9 = v8 + 25;
        if ( v8 >= 0xFFFFFFE7 )
        {
LABEL_8:
          pvargDest->llVal = 0;
          return -2147024882;
        }
      }
      else
      {
        v8 = 0;
        v9 = 25;
      }
      Value = (APP_DATA *)TlsGetValue(g_itlsAppData);
      if ( !Value )
      {
        if ( (int)InitAppData() < 0 )
          goto LABEL_8;
        Value = (APP_DATA *)TlsGetValue(g_itlsAppData);
      }
      v12 = (char *)APP_DATA::AllocCachedMem(Value, v9 & 0xFFFFFFF0);
      v13 = v12;
      if ( v12 )
      {
        v13 = v12 + 8;
        *((_DWORD *)v12 + 1) = v8;
        if ( bstrVal )
          memcpy_0(v13, bstrVal, v8);
        v13[v8] = 0;
        *(_WORD *)&v13[(v8 + 1) & 0xFFFFFFFE] = 0;
      }
      pvargDest->llVal = (LONGLONG)v13;
      if ( !v13 )
        return -2147024882;
      pvargDest->vt = 8;
      return 0;
    }
    if ( (vt & 0xFFFFBFFF) != 0x24 )
    {
      *(_OWORD *)&pvargDest->vt = *(_OWORD *)&pvargSrc->vt;
      pvargDest->pRecInfo = pvargSrc->pRecInfo;
      if ( vt != 9 )
      {
        if ( vt != 13 )
          return 0;
        llVal = pvargDest->llVal;
        if ( !llVal )
          return 0;
        goto LABEL_51;
      }
      llVal = pvargDest->llVal;
      if ( llVal )
LABEL_51:
        (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 8LL))(llVal);
      return 0;
    }
    pRecInfo = pvargSrc->pRecInfo;
    if ( !pRecInfo && pvargSrc->llVal )
      return -2147024809;
    pvargDest->pRecInfo = pRecInfo;
    v17 = pvargSrc->pRecInfo;
    if ( v17 && (v18 = pvargSrc->llVal) != 0 )
    {
      if ( (pvargSrc->vt & 0x4000) != 0 )
      {
        pvargDest->llVal = v18;
      }
      else
      {
        LODWORD(Size) = 0;
        result = ((__int64 (__fastcall *)(IRecordInfo *, size_t *))v17->lpVtbl->GetSize)(v17, &Size);
        if ( result <= -1 )
          return result;
        v19 = operator new[]((unsigned int)Size);
        pvargDest->llVal = (LONGLONG)v19;
        if ( !v19 )
          return -2147024882;
        memset_0(v19, 0, (unsigned int)Size);
        result = ((__int64 (__fastcall *)(IRecordInfo *, LONGLONG, LONGLONG))pvargSrc->pRecInfo->lpVtbl->RecordCopy)(
                   pvargSrc->pRecInfo,
                   pvargSrc->llVal,
                   pvargDest->llVal);
        if ( result <= -1 )
          return result;
      }
    }
    else
    {
      pvargDest->llVal = 0;
    }
    if ( (pvargSrc->vt & 0x4000) == 0 )
    {
      v20 = pvargDest->pRecInfo;
      if ( v20 )
        ((void (__fastcall *)(IRecordInfo *))v20->lpVtbl->AddRef)(v20);
    }
    pvargDest->vt = vt;
    return 0;
  }
  result = SafeArrayCopy(pvargSrc->parray, &pvargDest->parray);
  if ( result > -1 )
  {
    pvargDest->vt = vt;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18009af00  mov     [rsp+arg_10], rbx
0x18009af05  push    rsi
0x18009af06  push    rdi
0x18009af07  push    r14
0x18009af09  sub     rsp, 20h
0x18009af0d  movzx   esi, word ptr [rdx]
0x18009af10  mov     eax, 6000h
0x18009af15  movzx   edi, si
0x18009af18  mov     rbx, rdx
0x18009af1b  and     di, ax
0x18009af1e  mov     r14, rcx
0x18009af21  cmp     esi, 0Ch
0x18009af24  jnb     loc_18009B04B
0x18009af2a  mov     [rsp+38h+arg_0], rbp
0x18009af2f  cmp     r14, rbx
0x18009af32  jz      loc_18009B036
0x18009af38  mov     rcx, r14; pvarg
0x18009af3b  call    VariantClear
0x18009af40  cmp     eax, 0FFFFFFFFh
0x18009af43  jle     loc_18009B038
0x18009af49  mov     eax, 2000h
0x18009af4e  cmp     di, ax
0x18009af51  jz      loc_18009B07E
0x18009af57  cmp     esi, 8
0x18009af5a  jnz     short loc_18009AF80
0x18009af5c  mov     rsi, [rbx+8]
0x18009af60  xor     ebp, ebp
0x18009af62  test    rsi, rsi
0x18009af65  jz      short loc_18009AFC3
0x18009af67  mov     edi, [rsi-4]
0x18009af6a  lea     ebx, [rdi+19h]
0x18009af6d  cmp     ebx, 19h
0x18009af70  jnb     short loc_18009AFCA
0x18009af72  mov     [r14+8], rbp
0x18009af76  mov     eax, 8007000Eh
0x18009af7b  jmp     loc_18009B038
0x18009af80  mov     eax, esi
0x18009af82  mov     ecx, esi
0x18009af84  btr     eax, 0Eh
0x18009af88  cmp     eax, 24h ; '$'
0x18009af8b  jz      loc_18009B096
0x18009af91  movups  xmm0, xmmword ptr [rbx]
0x18009af94  movups  xmmword ptr [r14], xmm0
0x18009af98  movsd   xmm1, qword ptr [rbx+10h]
0x18009af9d  movsd   qword ptr [r14+10h], xmm1
0x18009afa3  cmp     ecx, 9
0x18009afa6  jz      loc_18009B1A4
0x18009afac  cmp     ecx, 0Dh
0x18009afaf  jnz     loc_18009B036
0x18009afb5  mov     rcx, [r14+8]
0x18009afb9  test    rcx, rcx
0x18009afbc  jz      short loc_18009B036
0x18009afbe  jmp     loc_18009B1B1
0x18009afc3  mov     edi, ebp
0x18009afc5  mov     ebx, 19h
0x18009afca  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18009afd0  call    cs:__imp_TlsGetValue
0x18009afd6  test    rax, rax
0x18009afd9  jz      loc_18009B14A
0x18009afdf  and     ebx, 0FFFFFFF0h
0x18009afe2  mov     rcx, rax; this
0x18009afe5  mov     edx, ebx; unsigned int
0x18009afe7  call    ?AllocCachedMem@APP_DATA@@QEAAPEAXK@Z; APP_DATA::AllocCachedMem(ulong)
0x18009afec  mov     rbx, rax
0x18009afef  test    rax, rax
0x18009aff2  jz      short loc_18009B023
0x18009aff4  add     rbx, 8
0x18009aff8  mov     [rax+4], edi
0x18009affb  test    rsi, rsi
0x18009affe  jz      short loc_18009B00E
0x18009b000  mov     r8d, edi; Size
0x18009b003  mov     rdx, rsi; Src
0x18009b006  mov     rcx, rbx; void *
0x18009b009  call    memcpy_0
0x18009b00e  mov     eax, edi
0x18009b010  mov     ecx, 0FFFFFFFEh
0x18009b015  mov     [rax+rbx], bpl
0x18009b019  lea     eax, [rdi+1]
0x18009b01c  and     rax, rcx
0x18009b01f  mov     [rax+rbx], bp
0x18009b023  mov     [r14+8], rbx
0x18009b027  test    rbx, rbx
0x18009b02a  jz      loc_18009AF76
0x18009b030  mov     word ptr [r14], 8
0x18009b036  xor     eax, eax
0x18009b038  mov     rbp, [rsp+38h+arg_0]
0x18009b03d  mov     rbx, [rsp+38h+arg_10]
0x18009b042  add     rsp, 20h
0x18009b046  pop     r14
0x18009b048  pop     rdi
0x18009b049  pop     rsi
0x18009b04a  retn
0x18009b04b  movzx   eax, si
0x18009b04e  mov     ecx, 9FFFh
0x18009b053  and     ax, cx
0x18009b056  test    di, di
0x18009b059  cmovz   ax, si
0x18009b05d  cmp     ax, 24h ; '$'
0x18009b061  ja      short loc_18009B077
0x18009b063  mov     rcx, 1000FF7FFCh
0x18009b06d  bt      rcx, rax
0x18009b071  jb      loc_18009AF2A
0x18009b077  mov     eax, 80020008h
0x18009b07c  jmp     short loc_18009B03D
0x18009b07e  mov     rcx, [rbx+8]; psa
0x18009b082  lea     rdx, [r14+8]; ppsaOut
0x18009b086  call    SafeArrayCopy
0x18009b08b  cmp     eax, 0FFFFFFFFh
0x18009b08e  jle     short loc_18009B038
0x18009b090  mov     [r14], si
0x18009b094  jmp     short loc_18009B036
0x18009b096  mov     rax, [rbx+10h]
0x18009b09a  test    rax, rax
0x18009b09d  jz      loc_18009B186
0x18009b0a3  mov     [r14+10h], rax
0x18009b0a7  mov     edi, 4000h
0x18009b0ac  mov     rcx, [rbx+10h]
0x18009b0b0  test    rcx, rcx
0x18009b0b3  jnz     short loc_18009B0CD
0x18009b0b5  xor     ebp, ebp
0x18009b0b7  mov     [r14+8], rbp
0x18009b0bb  test    [rbx], di
0x18009b0be  jz      loc_18009B168
0x18009b0c4  mov     [r14], si
0x18009b0c8  jmp     loc_18009B036
0x18009b0cd  mov     rax, [rbx+8]
0x18009b0d1  test    rax, rax
0x18009b0d4  jz      short loc_18009B0B5
0x18009b0d6  test    [rbx], di
0x18009b0d9  jnz     loc_18009B19B
0x18009b0df  xor     ebp, ebp
0x18009b0e1  lea     rdx, [rsp+38h+Size]
0x18009b0e6  mov     dword ptr [rsp+38h+Size], ebp
0x18009b0ea  mov     rax, [rcx]
0x18009b0ed  mov     rax, [rax+40h]
0x18009b0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0f6  cmp     eax, 0FFFFFFFFh
0x18009b0f9  jle     loc_18009B038
0x18009b0ff  mov     ecx, dword ptr [rsp+38h+Size]; unsigned __int64
0x18009b103  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009b108  mov     [r14+8], rax
0x18009b10c  test    rax, rax
0x18009b10f  jz      loc_18009AF76
0x18009b115  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x18009b11a  xor     edx, edx; Val
0x18009b11c  mov     rcx, rax; void *
0x18009b11f  call    memset_0
0x18009b124  mov     rcx, [rbx+10h]
0x18009b128  mov     r8, [r14+8]
0x18009b12c  mov     rdx, [rbx+8]
0x18009b130  mov     rax, [rcx]
0x18009b133  mov     rax, [rax+28h]
0x18009b137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b13c  cmp     eax, 0FFFFFFFFh
0x18009b13f  jg      loc_18009B0BB
0x18009b145  jmp     loc_18009B038
0x18009b14a  call    InitAppData
0x18009b14f  test    eax, eax
0x18009b151  js      loc_18009AF72
0x18009b157  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18009b15d  call    cs:__imp_TlsGetValue
0x18009b163  jmp     loc_18009AFDF
0x18009b168  mov     rcx, [r14+10h]
0x18009b16c  test    rcx, rcx
0x18009b16f  jz      loc_18009B0C4
0x18009b175  mov     rax, [rcx]
0x18009b178  mov     rax, [rax+8]
0x18009b17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b181  jmp     loc_18009B0C4
0x18009b186  cmp     qword ptr [rbx+8], 0
0x18009b18b  jz      loc_18009B0A3
0x18009b191  mov     eax, 80070057h
0x18009b196  jmp     loc_18009B038
0x18009b19b  mov     [r14+8], rax
0x18009b19f  jmp     loc_18009B0BB
0x18009b1a4  mov     rcx, [r14+8]
0x18009b1a8  test    rcx, rcx
0x18009b1ab  jz      loc_18009B036
0x18009b1b1  mov     rax, [rcx]
0x18009b1b4  mov     rax, [rax+8]
0x18009b1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b1bd  jmp     loc_18009B036
```
