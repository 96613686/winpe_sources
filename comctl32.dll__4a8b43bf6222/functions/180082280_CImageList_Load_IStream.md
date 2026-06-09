# CImageList::Load(IStream *)

- ea: `0x180082280`
- end: `0x18008253b`
- name: `?Load@CImageList@@UEAAJPEAUIStream@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(CImageList *this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800115f0`
- `0x1800169ac`
- `0x180081554`
- `0x180082280`
- `0x180082eac`
- `0x18008462c`
- `0x180090020`

## import_xrefs

- `GDI32!DeleteObject` at `0x180082439`
- `GDI32!DeleteObject` at `0x1800824ec`
- `GDI32!DeleteObject` at `0x180082439`
- `GDI32!DeleteObject` at `0x1800824ec`
- `KERNEL32!EnterCriticalSection` at `0x1800822cb`
- `KERNEL32!EnterCriticalSection` at `0x1800822eb`
- `KERNEL32!EnterCriticalSection` at `0x1800822cb`
- `KERNEL32!EnterCriticalSection` at `0x1800822eb`
- `KERNEL32!LeaveCriticalSection` at `0x1800822e2`
- `KERNEL32!LeaveCriticalSection` at `0x18008250b`
- `KERNEL32!LeaveCriticalSection` at `0x1800822e2`
- `KERNEL32!LeaveCriticalSection` at `0x18008250b`

## pseudocode

```c
__int64 __fastcall CImageList::Load(CImageList *this, struct IStream *a2)
{
  __int64 v5; // rax
  int Bitmap; // ebx
  HBITMAP v7; // rsi
  HBITMAP v8; // r15
  HGDIOBJ v9; // rcx
  __int16 v10; // dx
  int v11; // r14d
  _DWORD *v12; // rax
  HGDIOBJ v13; // [rsp+30h] [rbp-29h] BYREF
  HGDIOBJ ho; // [rsp+38h] [rbp-21h] BYREF
  HBITMAP v15; // [rsp+40h] [rbp-19h] BYREF
  HBITMAP v16; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v17[3]; // [rsp+50h] [rbp-9h] BYREF
  __int16 v18; // [rsp+80h] [rbp+27h]

  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_csDll);
  if ( !g_iILRefCount )
    CImageList::GlobalInit();
  LeaveCriticalSection(&g_csDll);
  EnterCriticalSection(&g_csDll);
  v18 = 0;
  v13 = 0;
  ho = 0;
  v5 = *(_QWORD *)a2;
  memset(v17, 0, sizeof(v17));
  Bitmap = (*(__int64 (__fastcall **)(struct IStream *, _OWORD *, __int64))(v5 + 24))(a2, v17, 28);
  if ( Bitmap >= 0 )
  {
    if ( LODWORD(v17[0]) != 16862281 )
    {
      Bitmap = -2147467259;
      goto LABEL_31;
    }
    v7 = 0;
    v8 = 0;
    v15 = 0;
    v16 = 0;
    Bitmap = Stream_ReadBitmap(a2, BYTE2(v17[1]) & 0xFE, (HBITMAP *)&v13);
    if ( Bitmap >= 0 )
    {
      if ( (BYTE2(v17[1]) & 1) != 0 )
      {
        Bitmap = Stream_ReadBitmap(a2, 0, &v15);
        if ( Bitmap < 0 )
        {
          v9 = v13;
LABEL_20:
          DeleteObject(v9);
          goto LABEL_31;
        }
        v7 = v15;
      }
      v10 = WORD1(v17[1]);
      if ( (WORD1(v17[1]) & 0x1000) != 0 )
      {
        Bitmap = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64))(*(_QWORD *)a2 + 24LL))(
                   a2,
                   (char *)&v17[1] + 12,
                   22);
        if ( Bitmap < 0 )
          goto LABEL_31;
        v10 = WORD1(v17[1]) & 0xEFFF;
        WORD1(v17[1]) &= ~0x1000u;
      }
      v11 = 0;
      if ( (v10 & 0x2000) == 0 )
        goto LABEL_22;
      WORD1(v17[1]) = v10 & 0xDFFF;
      Bitmap = Stream_ReadBitmap(a2, (unsigned __int8)v10 & 0xFE, (HBITMAP *)&ho);
      if ( Bitmap >= 0 )
      {
        v11 = 1;
        if ( (BYTE2(v17[1]) & 1) != 0 )
        {
          Bitmap = Stream_ReadBitmap(a2, 0, &v16);
          if ( Bitmap < 0 )
          {
            v9 = ho;
            goto LABEL_20;
          }
          v8 = v16;
        }
LABEL_22:
        Bitmap = CImageList::_Read(
                   (CImageList *)((char *)this - 32),
                   (const struct _ILFILEHEADER *)v17,
                   (HBITMAP)v13,
                   v7);
        if ( Bitmap < 0 || !v11 )
          goto LABEL_31;
        v12 = operator new(0x640u);
        if ( v12 )
        {
          v12[2] = 1280133448;
          *(_QWORD *)v12 = &CImageList::`vftable'{for `CImageListBase'};
          *((_QWORD *)v12 + 2) = &CImageList::`vftable'{for `IImageList'};
          *((_QWORD *)v12 + 3) = &CImageList::`vftable'{for `IImageListPriv'};
          *((_QWORD *)v12 + 4) = &CImageList::`vftable'{for `IPersistStream'};
          v12[10] = 1;
          *((_QWORD *)v12 + 62) = 0;
        }
        *((_QWORD *)this + 58) = v12;
        if ( v12 )
        {
          CImageList::_Read((CImageList *)v12, (const struct _ILFILEHEADER *)v17, (HBITMAP)ho, v8);
          goto LABEL_31;
        }
        Bitmap = -2147024882;
        DeleteObject(v13);
        if ( !v7 )
          goto LABEL_31;
        v9 = v7;
        goto LABEL_20;
      }
    }
  }
LABEL_31:
  LeaveCriticalSection(&g_csDll);
  return (unsigned int)Bitmap;
}

```

## disassembly

```asm
0x180082280  mov     [rsp-8+arg_10], rbx
0x180082285  mov     [rsp-8+arg_18], rsi
0x18008228a  push    rbp
0x18008228b  push    rdi
0x18008228c  push    r13
0x18008228e  push    r14
0x180082290  push    r15
0x180082292  lea     rbp, [rsp-37h]
0x180082297  sub     rsp, 90h
0x18008229e  mov     rax, cs:__security_cookie
0x1800822a5  xor     rax, rsp
0x1800822a8  mov     [rbp+57h+var_28], rax
0x1800822ac  mov     rdi, rdx
0x1800822af  mov     r13, rcx
0x1800822b2  test    rdx, rdx
0x1800822b5  jnz     short loc_1800822C1
0x1800822b7  mov     eax, 80070057h
0x1800822bc  jmp     loc_180082513
0x1800822c1  lea     rbx, g_csDll
0x1800822c8  mov     rcx, rbx; lpCriticalSection
0x1800822cb  call    cs:__imp_EnterCriticalSection
0x1800822d1  cmp     cs:?g_iILRefCount@@3HA, 0; int g_iILRefCount
0x1800822d8  jnz     short loc_1800822DF
0x1800822da  call    ?GlobalInit@CImageList@@SAHXZ; CImageList::GlobalInit(void)
0x1800822df  mov     rcx, rbx; lpCriticalSection
0x1800822e2  call    cs:__imp_LeaveCriticalSection
0x1800822e8  mov     rcx, rbx; lpCriticalSection
0x1800822eb  call    cs:__imp_EnterCriticalSection
0x1800822f1  xor     eax, eax
0x1800822f3  lea     rdx, [rbp+57h+var_60]
0x1800822f7  xorps   xmm0, xmm0
0x1800822fa  mov     [rbp+57h+var_30], ax
0x1800822fe  mov     [rbp+57h+var_80], rax
0x180082302  xor     r9d, r9d
0x180082305  mov     [rbp+57h+ho], rax
0x180082309  mov     rcx, rdi
0x18008230c  mov     rax, [rdi]
0x18008230f  movups  [rbp+57h+var_60], xmm0
0x180082313  lea     r8d, [r9+1Ch]
0x180082317  movups  [rbp+57h+var_50], xmm0
0x18008231b  mov     rax, [rax+18h]
0x18008231f  movups  [rbp+57h+var_40], xmm0
0x180082323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082328  mov     ebx, eax
0x18008232a  test    eax, eax
0x18008232c  js      loc_180082504
0x180082332  mov     eax, 4C49h
0x180082337  cmp     word ptr [rbp+57h+var_60], ax
0x18008233b  jnz     loc_1800824FF
0x180082341  mov     eax, 101h
0x180082346  cmp     word ptr [rbp+57h+var_60+2], ax
0x18008234a  jnz     loc_1800824FF
0x180082350  movsx   edx, word ptr [rbp+57h+var_50+2]
0x180082354  lea     r8, [rbp+57h+var_80]; HBITMAP *
0x180082358  xor     esi, esi
0x18008235a  xor     r15d, r15d
0x18008235d  and     edx, 0FEh; int
0x180082363  mov     [rbp+57h+var_70], rsi
0x180082367  mov     rcx, rdi; struct IStream *
0x18008236a  mov     [rbp+57h+var_68], r15
0x18008236e  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HPEAPEAUHBITMAP__@@@Z; Stream_ReadBitmap(IStream *,int,HBITMAP__ * *)
0x180082373  mov     ebx, eax
0x180082375  test    eax, eax
0x180082377  js      loc_180082504
0x18008237d  test    byte ptr [rbp+57h+var_50+2], 1
0x180082381  jz      short loc_1800823A4
0x180082383  lea     r8, [rbp+57h+var_70]; HBITMAP *
0x180082387  xor     edx, edx; int
0x180082389  mov     rcx, rdi; struct IStream *
0x18008238c  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HPEAPEAUHBITMAP__@@@Z; Stream_ReadBitmap(IStream *,int,HBITMAP__ * *)
0x180082391  mov     ebx, eax
0x180082393  test    eax, eax
0x180082395  jns     short loc_1800823A0
0x180082397  mov     rcx, [rbp+57h+var_80]
0x18008239b  jmp     loc_180082439
0x1800823a0  mov     rsi, [rbp+57h+var_70]
0x1800823a4  movzx   edx, word ptr [rbp+57h+var_50+2]
0x1800823a8  bt      dx, 0Ch
0x1800823ad  jnb     short loc_1800823E3
0x1800823af  mov     rax, [rdi]
0x1800823b2  lea     rdx, [rbp+57h+var_50+0Ch]
0x1800823b6  xor     r9d, r9d
0x1800823b9  mov     rcx, rdi
0x1800823bc  mov     rax, [rax+18h]
0x1800823c0  lea     r8d, [r9+16h]
0x1800823c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800823c9  mov     ebx, eax
0x1800823cb  test    eax, eax
0x1800823cd  js      loc_180082504
0x1800823d3  movzx   edx, word ptr [rbp+57h+var_50+2]
0x1800823d7  mov     eax, 0FFFFEFFFh
0x1800823dc  and     dx, ax
0x1800823df  mov     word ptr [rbp+57h+var_50+2], dx
0x1800823e3  xor     r14d, r14d
0x1800823e6  bt      dx, 0Dh
0x1800823eb  jnb     short loc_180082448
0x1800823ed  mov     eax, 0FFFFDFFFh
0x1800823f2  lea     r8, [rbp+57h+ho]; HBITMAP *
0x1800823f6  and     dx, ax
0x1800823f9  mov     rcx, rdi; struct IStream *
0x1800823fc  mov     word ptr [rbp+57h+var_50+2], dx
0x180082400  and     edx, 0FEh; int
0x180082406  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HPEAPEAUHBITMAP__@@@Z; Stream_ReadBitmap(IStream *,int,HBITMAP__ * *)
0x18008240b  mov     ebx, eax
0x18008240d  test    eax, eax
0x18008240f  js      loc_180082504
0x180082415  mov     r14d, 1
0x18008241b  test    byte ptr [rbp+57h+var_50+2], r14b
0x18008241f  jz      short loc_180082448
0x180082421  lea     r8, [rbp+57h+var_68]; HBITMAP *
0x180082425  xor     edx, edx; int
0x180082427  mov     rcx, rdi; struct IStream *
0x18008242a  call    ?Stream_ReadBitmap@@YAJPEAUIStream@@HPEAPEAUHBITMAP__@@@Z; Stream_ReadBitmap(IStream *,int,HBITMAP__ * *)
0x18008242f  mov     ebx, eax
0x180082431  test    eax, eax
0x180082433  jns     short loc_180082444
0x180082435  mov     rcx, [rbp+57h+ho]; ho
0x180082439  call    cs:__imp_DeleteObject
0x18008243f  jmp     loc_180082504
0x180082444  mov     r15, [rbp+57h+var_68]
0x180082448  mov     r8, [rbp+57h+var_80]; HBITMAP
0x18008244c  lea     rcx, [r13-20h]; this
0x180082450  mov     r9, rsi; HBITMAP
0x180082453  lea     rdx, [rbp+57h+var_60]; struct _ILFILEHEADER *
0x180082457  call    ?_Read@CImageList@@QEAAJPEBU_ILFILEHEADER@@PEAUHBITMAP__@@1@Z; CImageList::_Read(_ILFILEHEADER const *,HBITMAP__ *,HBITMAP__ *)
0x18008245c  mov     ebx, eax
0x18008245e  test    eax, eax
0x180082460  js      loc_180082504
0x180082466  test    r14d, r14d
0x180082469  jz      loc_180082504
0x18008246f  mov     ecx, 640h; unsigned __int64
0x180082474  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180082479  test    rax, rax
0x18008247c  jz      short loc_1800824C2
0x18008247e  lea     rcx, ??_7CImageList@@6BCImageListBase@@@; const CImageList::`vftable'{for `CImageListBase'}
0x180082485  mov     dword ptr [rax+8], 4C4D4948h
0x18008248c  mov     [rax], rcx
0x18008248f  lea     rcx, ??_7CImageList@@6BIImageList@@@; const CImageList::`vftable'{for `IImageList'}
0x180082496  mov     [rax+10h], rcx
0x18008249a  lea     rcx, ??_7CImageList@@6BIImageListPriv@@@; const CImageList::`vftable'{for `IImageListPriv'}
0x1800824a1  mov     [rax+18h], rcx
0x1800824a5  lea     rcx, ??_7CImageList@@6BIPersistStream@@@; const CImageList::`vftable'{for `IPersistStream'}
0x1800824ac  mov     [rax+20h], rcx
0x1800824b0  mov     dword ptr [rax+28h], 1
0x1800824b7  mov     qword ptr [rax+1F0h], 0
0x1800824c2  mov     [r13+1D0h], rax
0x1800824c9  test    rax, rax
0x1800824cc  jz      short loc_1800824E3
0x1800824ce  mov     r8, [rbp+57h+ho]; HBITMAP
0x1800824d2  lea     rdx, [rbp+57h+var_60]; struct _ILFILEHEADER *
0x1800824d6  mov     r9, r15; HBITMAP
0x1800824d9  mov     rcx, rax; this
0x1800824dc  call    ?_Read@CImageList@@QEAAJPEBU_ILFILEHEADER@@PEAUHBITMAP__@@1@Z; CImageList::_Read(_ILFILEHEADER const *,HBITMAP__ *,HBITMAP__ *)
0x1800824e1  jmp     short loc_180082504
0x1800824e3  mov     rcx, [rbp+57h+var_80]; ho
0x1800824e7  mov     ebx, 8007000Eh
0x1800824ec  call    cs:__imp_DeleteObject
0x1800824f2  test    rsi, rsi
0x1800824f5  jz      short loc_180082504
0x1800824f7  mov     rcx, rsi
0x1800824fa  jmp     loc_180082439
0x1800824ff  mov     ebx, 80004005h
0x180082504  lea     rcx, g_csDll; lpCriticalSection
0x18008250b  call    cs:__imp_LeaveCriticalSection
0x180082511  mov     eax, ebx
0x180082513  mov     rcx, [rbp+57h+var_28]
0x180082517  xor     rcx, rsp; StackCookie
0x18008251a  call    __security_check_cookie
0x18008251f  lea     r11, [rsp+0B0h+var_20]
0x180082527  mov     rbx, [r11+40h]
0x18008252b  mov     rsi, [r11+48h]
0x18008252f  mov     rsp, r11
0x180082532  pop     r15
0x180082534  pop     r14
0x180082536  pop     r13
0x180082538  pop     rdi
0x180082539  pop     rbp
0x18008253a  retn
```
