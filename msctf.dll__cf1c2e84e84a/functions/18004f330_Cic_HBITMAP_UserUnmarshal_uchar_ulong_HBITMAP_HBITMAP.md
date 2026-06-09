# Cic_HBITMAP_UserUnmarshal(uchar *,ulong,HBITMAP__ * *,HBITMAP__ * *)

- ea: `0x18004f330`
- end: `0x18004f677`
- name: `?Cic_HBITMAP_UserUnmarshal@@YAPEAEPEAEKPEAPEAUHBITMAP__@@1@Z`
- size: `839`
- prototype: `unsigned __int8 *__fastcall(unsigned __int8 *, unsigned int, HBITMAP *, HBITMAP *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004f244`
- `0x18008d588`

## callees

- `0x18004f330`
- `0x18004f680`
- `0x18004f700`
- `0x18009eac6`
- `0x180106a60`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004f661`
- `GDI32!DeleteObject` at `0x18004f66c`
- `GDI32!DeleteObject` at `0x18004f661`
- `GDI32!DeleteObject` at `0x18004f66c`
- `GDI32!CreateCompatibleDC` at `0x18004f459`
- `GDI32!CreateCompatibleDC` at `0x18004f459`
- `GDI32!CreateBitmap` at `0x18004f581`
- `GDI32!CreateBitmap` at `0x18004f653`
- `GDI32!CreateBitmap` at `0x18004f581`
- `GDI32!CreateBitmap` at `0x18004f653`
- `GDI32!CreateDIBSection` at `0x18004f4c8`
- `GDI32!CreateDIBSection` at `0x18004f4c8`

## pseudocode

```c
unsigned __int8 *__fastcall Cic_HBITMAP_UserUnmarshal(unsigned __int8 *a1, unsigned int a2, HBITMAP *a3, HBITMAP *a4)
{
  HGDIOBJ *v4; // r13
  HGDIOBJ *v5; // r15
  unsigned __int8 *v6; // rbx
  HBITMAP Bitmap; // rbp
  unsigned __int8 *result; // rax
  unsigned __int8 *v9; // rax
  int v10; // ecx
  HBITMAP DIB; // rdi
  LONG v12; // r14d
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  __int64 v15; // r12
  unsigned __int64 v16; // rcx
  UINT v17; // ecx
  LONG v18; // ebp
  unsigned int v19; // r14d
  __int64 v20; // r9
  unsigned int v21; // r10d
  __int64 v22; // r11
  unsigned __int64 v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  unsigned int v26; // ecx
  UINT v27; // eax
  int v28; // ecx
  unsigned __int64 v29; // rax
  LONG v30; // edi
  HANDLE hSection; // [rsp+20h] [rbp-D8h]
  unsigned int v32; // [rsp+30h] [rbp-C8h]
  unsigned int v33; // [rsp+34h] [rbp-C4h]
  void *ppvBits; // [rsp+38h] [rbp-C0h] BYREF
  HBITMAP v35; // [rsp+40h] [rbp-B8h]
  __int64 v36; // [rsp+48h] [rbp-B0h]
  HBITMAP *v37; // [rsp+50h] [rbp-A8h]
  HBITMAP *v38; // [rsp+58h] [rbp-A0h]
  __int128 v39; // [rsp+60h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-88h]
  HDC CompatibleDC; // [rsp+78h] [rbp-80h]
  BITMAPINFO pbmi; // [rsp+80h] [rbp-78h] BYREF

  v38 = a4;
  v4 = (HGDIOBJ *)a4;
  v37 = a3;
  v5 = (HGDIOBJ *)a3;
  v33 = a2;
  v6 = a1;
  if ( a2 < 0x68 )
    return 0;
  Bitmap = (HBITMAP)*((unsigned int *)a1 + 1);
  if ( *((_DWORD *)a1 + 1) )
  {
    v9 = a1;
  }
  else
  {
    if ( !a4 )
    {
      result = a1 + 104;
      *a3 = 0;
      return result;
    }
    v9 = a1 + 8;
  }
  v10 = *(_DWORD *)v9;
  DIB = (HBITMAP)*((unsigned int *)v6 + 3);
  v35 = DIB;
  if ( v10 == 1 )
  {
    if ( Bitmap )
    {
      v12 = *((_DWORD *)v6 + 8);
      v13 = *((unsigned __int16 *)v6 + 20);
      v14 = v13 * (unsigned int)v12;
      if ( v14 > 0xFFFFFFFF )
        return 0;
      v15 = *((unsigned int *)v6 + 9);
      v16 = v15 * (unsigned int)v14;
      if ( v16 > 0xFFFFFFFF )
        return 0;
      v36 = *((unsigned int *)v6 + 4);
      if ( v36 != (unsigned int)v16 )
        return 0;
      v32 = v16 + 104;
      if ( (unsigned int)(v16 + 104) < 0x68 || a2 < (int)v16 + 104 )
        return 0;
      v17 = *((unsigned __int16 *)v6 + 21);
      v18 = *((_DWORD *)v6 + 7);
      if ( v17 == 32 )
      {
        v40 = 0;
        v39 = 0;
        CompatibleDC = CreateCompatibleDC(0);
        pbmi.bmiHeader.biSize = 40;
        pbmi.bmiHeader.biWidth = v18;
        pbmi.bmiHeader.biHeight = v12;
        memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        ppvBits = 0;
        Bitmap = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
        if ( Bitmap )
        {
          v30 = 0;
          if ( v12 > 0 )
          {
            do
            {
              memcpy_0((char *)ppvBits + (int)v15 * (v12 - v30 - 1), &v6[(int)v15 * v30 + 96], (int)v15);
              ++v30;
            }
            while ( v30 < v12 );
            v5 = (HGDIOBJ *)v37;
            v4 = (HGDIOBJ *)v38;
          }
          DIB = v35;
        }
        CBitmapDC::~CBitmapDC((CBitmapDC *)&v39);
      }
      else
      {
        Bitmap = CreateBitmap(v18, v12, v13, v17, v6 + 96);
      }
      v19 = v32;
      a2 = v33;
      v20 = v36;
    }
    else
    {
      v19 = 104;
      v20 = 0;
    }
    if ( !DIB )
    {
      DIB = 0;
LABEL_28:
      v29 = (v19 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( (unsigned __int64)v19 + 7 < v19 )
        v29 = 0;
      v6 += v29;
      goto LABEL_31;
    }
    v21 = *((_DWORD *)v6 + 18);
    v22 = *((unsigned __int16 *)v6 + 40);
    v23 = v22 * v21;
    if ( v23 <= 0xFFFFFFFF )
    {
      v24 = *((unsigned int *)v6 + 19);
      v25 = v24 * (unsigned int)v23;
      if ( v25 <= 0xFFFFFFFF && *((_DWORD *)v6 + 14) == (_DWORD)v25 )
      {
        v26 = v25 + v19;
        if ( (unsigned int)v25 + v19 >= v19 && a2 >= v26 )
        {
          v27 = *((unsigned __int16 *)v6 + 41);
          v19 = v26;
          v28 = *((_DWORD *)v6 + 17);
          if ( v27 == 32 )
            DIB = CreateDIB(v28, v21, v24, &v6[v20 + 96], (unsigned __int64)hSection);
          else
            DIB = CreateBitmap(v28, v21, v22, v27, &v6[v20 + 96]);
          goto LABEL_28;
        }
      }
    }
    return 0;
  }
  if ( v10 != 2 )
    return 0;
LABEL_31:
  if ( *v5 )
    DeleteObject(*v5);
  *v5 = Bitmap;
  if ( v4 )
  {
    if ( *v4 )
      DeleteObject(*v4);
    *v4 = DIB;
  }
  return v6;
}

```

## disassembly

```asm
0x18004f330  mov     [rsp+arg_8], rbx
0x18004f335  push    rbp
0x18004f336  push    rsi
0x18004f337  push    rdi
0x18004f338  push    r12
0x18004f33a  push    r13
0x18004f33c  push    r14
0x18004f33e  push    r15
0x18004f340  sub     rsp, 0C0h
0x18004f347  mov     rax, cs:__security_cookie
0x18004f34e  xor     rax, rsp
0x18004f351  mov     [rsp+0F8h+var_48], rax
0x18004f359  mov     [rsp+0F8h+var_A0], r9
0x18004f35e  mov     r13, r9
0x18004f361  mov     [rsp+0F8h+var_A8], r8
0x18004f366  mov     r15, r8
0x18004f369  mov     [rsp+0F8h+var_C4], edx
0x18004f36d  mov     rbx, rcx
0x18004f370  cmp     edx, 68h ; 'h'
0x18004f373  jb      short loc_18004F391
0x18004f375  mov     ebp, [rcx+4]
0x18004f378  test    rbp, rbp
0x18004f37b  jnz     loc_18004F4F9
0x18004f381  test    r9, r9
0x18004f384  jnz     short loc_18004F3BE
0x18004f386  xor     esi, esi
0x18004f388  lea     rax, [rcx+68h]
0x18004f38c  mov     [r8], rsi
0x18004f38f  jmp     short loc_18004F393
0x18004f391  xor     eax, eax
0x18004f393  mov     rcx, [rsp+0F8h+var_48]
0x18004f39b  xor     rcx, rsp; StackCookie
0x18004f39e  call    __security_check_cookie
0x18004f3a3  mov     rbx, [rsp+0F8h+arg_8]
0x18004f3ab  add     rsp, 0C0h
0x18004f3b2  pop     r15
0x18004f3b4  pop     r14
0x18004f3b6  pop     r13
0x18004f3b8  pop     r12
0x18004f3ba  pop     rdi
0x18004f3bb  pop     rsi
0x18004f3bc  pop     rbp
0x18004f3bd  retn
0x18004f3be  lea     rax, [rcx+8]
0x18004f3c2  mov     ecx, [rax]
0x18004f3c4  mov     edi, [rbx+0Ch]
0x18004f3c7  mov     [rsp+0F8h+var_B8], rdi
0x18004f3cc  cmp     ecx, 1
0x18004f3cf  jnz     loc_18004F5E4
0x18004f3d5  xor     esi, esi
0x18004f3d7  mov     ecx, 0FFFFFFFFh
0x18004f3dc  test    rbp, rbp
0x18004f3df  jz      loc_18004F501
0x18004f3e5  mov     r14d, [rbx+20h]
0x18004f3e9  movzx   r8d, word ptr [rbx+28h]; nPlanes
0x18004f3ee  mov     eax, r14d
0x18004f3f1  imul    rax, r8
0x18004f3f5  cmp     rax, rcx
0x18004f3f8  ja      short loc_18004F391
0x18004f3fa  mov     r12d, [rbx+24h]
0x18004f3fe  mov     ecx, eax
0x18004f400  mov     eax, 0FFFFFFFFh
0x18004f405  imul    rcx, r12
0x18004f409  cmp     rcx, rax
0x18004f40c  ja      short loc_18004F391
0x18004f40e  mov     eax, ecx
0x18004f410  mov     ecx, [rbx+10h]
0x18004f413  mov     [rsp+0F8h+var_B0], rcx
0x18004f418  cmp     rcx, rax
0x18004f41b  jnz     loc_18004F391
0x18004f421  add     eax, 68h ; 'h'
0x18004f424  mov     [rsp+0F8h+var_C8], eax
0x18004f428  cmp     eax, 68h ; 'h'
0x18004f42b  jb      loc_18004F391
0x18004f431  cmp     edx, eax
0x18004f433  jb      loc_18004F391
0x18004f439  movzx   ecx, word ptr [rbx+2Ah]
0x18004f43d  mov     ebp, [rbx+1Ch]
0x18004f440  cmp     ecx, 20h ; ' '
0x18004f443  jnz     loc_18004F642
0x18004f449  xorps   xmm0, xmm0
0x18004f44c  mov     [rsp+0F8h+var_88], rsi
0x18004f451  xor     ecx, ecx; hdc
0x18004f453  movdqu  [rsp+0F8h+var_98], xmm0
0x18004f459  call    cs:__imp_CreateCompatibleDC
0x18004f45f  xor     ecx, ecx
0x18004f461  mov     [rsp+0F8h+offset], esi; offset
0x18004f465  xorps   xmm0, xmm0
0x18004f468  mov     qword ptr [rsp+0F8h+pbmi.bmiHeader.biClrImportant], rcx
0x18004f470  movups  xmmword ptr [rsp+0F8h+pbmi.bmiHeader.biWidth], xmm0
0x18004f478  mov     rcx, rax; hdc
0x18004f47b  mov     [rsp+0F8h+var_80], rax
0x18004f480  lea     r9, [rsp+0F8h+ppvBits]; ppvBits
0x18004f485  mov     [rsp+0F8h+pbmi.bmiHeader.biSize], 28h ; '('
0x18004f490  xor     r8d, r8d; usage
0x18004f493  mov     [rsp+0F8h+pbmi.bmiHeader.biWidth], ebp
0x18004f49a  lea     rdx, [rsp+0F8h+pbmi]; pbmi
0x18004f4a2  mov     [rsp+0F8h+pbmi.bmiHeader.biHeight], r14d
0x18004f4aa  movups  xmmword ptr [rsp+0F8h+pbmi.bmiHeader.biSizeImage], xmm0
0x18004f4b2  mov     qword ptr [rsp+0F8h+pbmi.bmiHeader.biPlanes], 200001h
0x18004f4be  mov     [rsp+0F8h+ppvBits], rsi
0x18004f4c3  mov     [rsp+0F8h+hSection], rsi; hSection
0x18004f4c8  call    cs:__imp_CreateDIBSection
0x18004f4ce  mov     rbp, rax
0x18004f4d1  test    rax, rax
0x18004f4d4  jnz     loc_18004F5EF
0x18004f4da  lea     rcx, [rsp+0F8h+var_98]; this
0x18004f4df  call    ??1CBitmapDC@@QEAA@XZ; CBitmapDC::~CBitmapDC(void)
0x18004f4e4  mov     r14d, [rsp+0F8h+var_C8]
0x18004f4e9  mov     ecx, 0FFFFFFFFh
0x18004f4ee  mov     edx, [rsp+0F8h+var_C4]
0x18004f4f2  mov     r9, [rsp+0F8h+var_B0]
0x18004f4f7  jmp     short loc_18004F50A
0x18004f4f9  mov     rax, rbx
0x18004f4fc  jmp     loc_18004F3C2
0x18004f501  mov     r14d, 68h ; 'h'
0x18004f507  mov     r9, rsi
0x18004f50a  test    rdi, rdi
0x18004f50d  jz      loc_18004F5CF
0x18004f513  mov     r10d, [rbx+48h]
0x18004f517  movzx   r11d, word ptr [rbx+50h]
0x18004f51c  mov     eax, r10d
0x18004f51f  imul    rax, r11
0x18004f523  cmp     rax, rcx
0x18004f526  ja      loc_18004F391
0x18004f52c  mov     r8d, [rbx+4Ch]; int
0x18004f530  mov     eax, eax
0x18004f532  imul    rax, r8
0x18004f536  cmp     rax, rcx
0x18004f539  ja      loc_18004F391
0x18004f53f  cmp     [rbx+38h], eax
0x18004f542  jnz     loc_18004F391
0x18004f548  lea     ecx, [rax+r14]
0x18004f54c  cmp     ecx, r14d
0x18004f54f  jb      loc_18004F391
0x18004f555  cmp     edx, ecx
0x18004f557  jb      loc_18004F391
0x18004f55d  movzx   eax, word ptr [rbx+52h]
0x18004f561  lea     rdx, [rbx+60h]
0x18004f565  add     rdx, r9
0x18004f568  mov     r14d, ecx
0x18004f56b  mov     ecx, [rbx+44h]; int
0x18004f56e  cmp     eax, 20h ; ' '
0x18004f571  jz      short loc_18004F5D4
0x18004f573  mov     [rsp+0F8h+hSection], rdx; lpBits
0x18004f578  mov     r9d, eax; nBitCount
0x18004f57b  mov     edx, r10d; nHeight
0x18004f57e  mov     r8d, r11d; nPlanes
0x18004f581  call    cs:__imp_CreateBitmap
0x18004f587  mov     rdi, rax
0x18004f58a  mov     edx, r14d
0x18004f58d  lea     rcx, [rdx+7]
0x18004f591  mov     rax, rcx
0x18004f594  and     rax, 0FFFFFFFFFFFFFFF8h
0x18004f598  cmp     rcx, rdx
0x18004f59b  cmovb   rax, rsi
0x18004f59f  add     rbx, rax
0x18004f5a2  mov     rcx, [r15]; ho
0x18004f5a5  test    rcx, rcx
0x18004f5a8  jnz     loc_18004F661
0x18004f5ae  mov     [r15], rbp
0x18004f5b1  test    r13, r13
0x18004f5b4  jz      short loc_18004F5C7
0x18004f5b6  mov     rcx, [r13+0]; ho
0x18004f5ba  test    rcx, rcx
0x18004f5bd  jnz     loc_18004F66C
0x18004f5c3  mov     [r13+0], rdi
0x18004f5c7  mov     rax, rbx
0x18004f5ca  jmp     loc_18004F393
0x18004f5cf  mov     rdi, rsi
0x18004f5d2  jmp     short loc_18004F58A
0x18004f5d4  mov     r9, rdx; unsigned __int8 *
0x18004f5d7  mov     edx, r10d; int
0x18004f5da  call    ?CreateDIB@@YAPEAUHBITMAP__@@HHHPEAE_K@Z; CreateDIB(int,int,int,uchar *,unsigned __int64)
0x18004f5df  mov     rdi, rax
0x18004f5e2  jmp     short loc_18004F58A
0x18004f5e4  cmp     ecx, 2
0x18004f5e7  jnz     loc_18004F391
0x18004f5ed  jmp     short loc_18004F5A2
0x18004f5ef  mov     edi, esi
0x18004f5f1  test    r14d, r14d
0x18004f5f4  jle     short loc_18004F638
0x18004f5f6  movsxd  r13, r12d
0x18004f5f9  lea     r15, [rbx+60h]
0x18004f5fd  nop     dword ptr [rax]
0x18004f600  mov     eax, edi
0x18004f602  mov     r8, r13; Size
0x18004f605  imul    eax, r12d
0x18004f609  movsxd  rdx, eax
0x18004f60c  mov     eax, r14d
0x18004f60f  sub     eax, edi
0x18004f611  add     rdx, r15; Src
0x18004f614  dec     eax
0x18004f616  imul    eax, r12d
0x18004f61a  movsxd  rcx, eax
0x18004f61d  add     rcx, [rsp+0F8h+ppvBits]; void *
0x18004f622  call    memcpy_0
0x18004f627  inc     edi
0x18004f629  cmp     edi, r14d
0x18004f62c  jl      short loc_18004F600
0x18004f62e  mov     r15, [rsp+0F8h+var_A8]
0x18004f633  mov     r13, [rsp+0F8h+var_A0]
0x18004f638  mov     rdi, [rsp+0F8h+var_B8]
0x18004f63d  jmp     loc_18004F4DA
0x18004f642  lea     rax, [rbx+60h]
0x18004f646  mov     r9d, ecx; nBitCount
0x18004f649  mov     ecx, ebp; nWidth
0x18004f64b  mov     [rsp+0F8h+hSection], rax; lpBits
0x18004f650  mov     edx, r14d; nHeight
0x18004f653  call    cs:__imp_CreateBitmap
0x18004f659  mov     rbp, rax
0x18004f65c  jmp     loc_18004F4E4
0x18004f661  call    cs:__imp_DeleteObject
0x18004f667  jmp     loc_18004F5AE
0x18004f66c  call    cs:__imp_DeleteObject
0x18004f672  jmp     loc_18004F5C3
```
