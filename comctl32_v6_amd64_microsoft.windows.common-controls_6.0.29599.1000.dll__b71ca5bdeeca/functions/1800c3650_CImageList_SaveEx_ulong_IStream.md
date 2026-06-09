# CImageList::SaveEx(ulong,IStream *)

- ea: `0x1800c3650`
- end: `0x1800c39df`
- name: `?SaveEx@CImageList@@UEAAJKPEAUIStream@@@Z`
- size: `911`
- prototype: `int(CImageList *__hidden this, unsigned int, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800c3650`
- `0x1800c39e8`
- `0x1800c3d2c`
- `0x180114520`
- `0x180147c58`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c395b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c39b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c395b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c39b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c36b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3860`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c36b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3860`
- `GDI32!DeleteObject` at `0x1800c392c`
- `GDI32!DeleteObject` at `0x1800c394a`
- `GDI32!DeleteObject` at `0x1800c3993`
- `GDI32!DeleteObject` at `0x1800c39a7`
- `GDI32!DeleteObject` at `0x1800c392c`
- `GDI32!DeleteObject` at `0x1800c394a`
- `GDI32!DeleteObject` at `0x1800c3993`
- `GDI32!DeleteObject` at `0x1800c39a7`

## pseudocode

```c
__int64 __fastcall CImageList::SaveEx(CImageList *this, int a2, struct IStream *a3)
{
  int v4; // esi
  struct _RTL_CRITICAL_SECTION *v7; // r14
  HBITMAP v8; // r13
  HBITMAP v9; // r15
  __int16 v10; // ax
  __int16 v11; // cx
  int i; // edx
  __int64 j; // rcx
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // r8
  HBITMAP v17; // rsi
  HBITMAP v18; // r14
  _QWORD *v19; // rax
  HBITMAP v20; // [rsp+20h] [rbp-49h]
  HBITMAP v21; // [rsp+20h] [rbp-49h]
  HBITMAP v22; // [rsp+30h] [rbp-39h] BYREF
  int v23; // [rsp+38h] [rbp-31h]
  HBITMAP v24; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v25[3]; // [rsp+48h] [rbp-21h] BYREF
  __int16 v26; // [rsp+78h] [rbp+Fh]

  v23 = a2;
  v4 = a2;
  if ( !a3 )
    return 2147942487LL;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = (HBITMAP)*((_QWORD *)this + 16);
  v9 = (HBITMAP)*((_QWORD *)this + 15);
  LOWORD(v25[0]) = 19529;
  v10 = 1568;
  v24 = v8;
  v22 = v9;
  if ( v4 )
    v10 = 257;
  v11 = *((_WORD *)this + 48);
  WORD1(v25[0]) = v10;
  WORD2(v25[0]) = *((_WORD *)this + 38);
  WORD3(v25[0]) = *((_WORD *)this + 40);
  WORD4(v25[0]) = *((_WORD *)this + 42);
  WORD5(v25[0]) = *((_WORD *)this + 44);
  WORD6(v25[0]) = *((_WORD *)this + 46);
  *(_DWORD *)((char *)v25 + 14) = *((_DWORD *)this + 26);
  WORD1(v25[1]) = v11;
  if ( v4 == 1 )
  {
    CreateDownlevelBitmap(
      *((_DWORD *)this + 22),
      *((_DWORD *)this + 23),
      *((_DWORD *)this + 19),
      *((HDC *)this + 19),
      v20,
      &v22);
    if ( *((_QWORD *)this + 16) )
    {
      CreateDownlevelBitmap(
        *((_DWORD *)this + 22),
        *((_DWORD *)this + 23),
        *((_DWORD *)this + 19),
        *((HDC *)this + 20),
        v20,
        &v24);
      v8 = v24;
    }
    v9 = v22;
    v11 = WORD1(v25[1]);
  }
  if ( *((_QWORD *)this + 66) )
  {
    v11 |= 0x2000u;
    WORD1(v25[1]) = v11;
  }
  for ( i = 4; i < 15; ++i )
  {
    if ( *((_DWORD *)this + i + 42) != -1 )
    {
      WORD1(v25[1]) = v11 | 0x1000;
      break;
    }
  }
  for ( j = 0; j != 15; ++j )
    *((_WORD *)&v25[1] + j + 2) = *((_WORD *)this + 2 * j + 84);
  v14 = (*(__int64 (__fastcall **)(struct IStream *, _OWORD *, __int64, _QWORD))(*(_QWORD *)a3 + 32LL))(a3, v25, 28, 0);
  if ( v14 >= 0 )
  {
    v14 = Stream_WriteBitmap(a3, v9, 0);
    if ( v14 >= 0 )
    {
      if ( !*((_QWORD *)this + 20) || (v14 = Stream_WriteBitmap(a3, v8, 1u), v14 >= 0) )
      {
        if ( (WORD1(v25[1]) & 0x1000) != 0 )
          v14 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64))(*(_QWORD *)a3 + 32LL))(
                  a3,
                  (char *)&v25[1] + 12,
                  22);
        v15 = *((_QWORD *)this + 66);
        if ( v15 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 64));
          v16 = *((_QWORD *)this + 66);
          v17 = *(HBITMAP *)(v16 + 160);
          v18 = *(HBITMAP *)(v16 + 168);
          v22 = v17;
          v24 = v18;
          if ( v23 == 1 )
          {
            CreateDownlevelBitmap(
              *((_DWORD *)this + 22),
              *((_DWORD *)this + 23),
              *(_DWORD *)(v16 + 116),
              *(HDC *)(v16 + 192),
              v20,
              &v22);
            if ( *((_QWORD *)this + 16) )
            {
              CreateDownlevelBitmap(
                *((_DWORD *)this + 22),
                *((_DWORD *)this + 23),
                *(_DWORD *)(*((_QWORD *)this + 66) + 116LL),
                *(HDC *)(*((_QWORD *)this + 66) + 200LL),
                v21,
                &v24);
              v18 = v24;
            }
            v17 = v22;
          }
          v14 = Stream_WriteBitmap(a3, v17, 0);
          v19 = (_QWORD *)*((_QWORD *)this + 66);
          if ( v19[25] )
          {
            v14 = Stream_WriteBitmap(a3, v18, 1u);
            v19 = (_QWORD *)*((_QWORD *)this + 66);
          }
          if ( v18 && v18 != (HBITMAP)v19[21] )
          {
            DeleteObject(v18);
            v19 = (_QWORD *)*((_QWORD *)this + 66);
          }
          if ( v17 && v17 != (HBITMAP)v19[20] )
            DeleteObject(v17);
          LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 66) + 64LL));
          v4 = v23;
          v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
        }
        if ( v14 >= 0 && v4 != 1 )
          v14 = DSA_SaveStream(*((_QWORD *)this + 17), a3);
      }
    }
  }
  if ( v8 && v8 != *((HBITMAP *)this + 16) )
    DeleteObject(v8);
  if ( v9 )
  {
    if ( v9 != *((HBITMAP *)this + 15) )
      DeleteObject(v9);
  }
  LeaveCriticalSection(v7);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800c3650  mov     [rsp-8+arg_8], rbx
0x1800c3655  push    rbp
0x1800c3656  push    rsi
0x1800c3657  push    rdi
0x1800c3658  push    r12
0x1800c365a  push    r13
0x1800c365c  push    r14
0x1800c365e  push    r15
0x1800c3660  lea     rbp, [rsp-27h]
0x1800c3665  sub     rsp, 90h
0x1800c366c  mov     rax, cs:__security_cookie
0x1800c3673  xor     rax, rsp
0x1800c3676  mov     [rbp+57h+var_40], rax
0x1800c367a  mov     [rbp+57h+var_88], edx
0x1800c367d  mov     r12, r8
0x1800c3680  mov     esi, edx
0x1800c3682  mov     rbx, rcx
0x1800c3685  test    r8, r8
0x1800c3688  jnz     short loc_1800C3694
0x1800c368a  mov     eax, 80070057h
0x1800c368f  jmp     loc_1800C39B8
0x1800c3694  xorps   xmm0, xmm0
0x1800c3697  lea     r14, [rcx+18h]
0x1800c369b  xor     eax, eax
0x1800c369d  mov     rcx, r14; lpCriticalSection
0x1800c36a0  movups  [rbp+57h+var_78], xmm0
0x1800c36a4  mov     [rbp+57h+var_48], ax
0x1800c36a8  movups  [rbp+57h+var_68], xmm0
0x1800c36ac  movups  [rbp+57h+var_58], xmm0
0x1800c36b0  call    cs:__imp_EnterCriticalSection
0x1800c36b6  mov     r13, [rbx+80h]
0x1800c36bd  mov     eax, 4C49h
0x1800c36c2  mov     r15, [rbx+78h]
0x1800c36c6  mov     word ptr [rbp+57h+var_78], ax
0x1800c36ca  mov     eax, 620h
0x1800c36cf  mov     [rbp+57h+var_80], r13
0x1800c36d3  mov     [rbp+57h+var_90], r15
0x1800c36d7  test    esi, esi
0x1800c36d9  jz      short loc_1800C36E0
0x1800c36db  mov     eax, 101h
0x1800c36e0  movzx   ecx, word ptr [rbx+60h]
0x1800c36e4  mov     word ptr [rbp+57h+var_78+2], ax
0x1800c36e8  movzx   eax, word ptr [rbx+4Ch]
0x1800c36ec  mov     word ptr [rbp+57h+var_78+4], ax
0x1800c36f0  movzx   eax, word ptr [rbx+50h]
0x1800c36f4  mov     word ptr [rbp+57h+var_78+6], ax
0x1800c36f8  movzx   eax, word ptr [rbx+54h]
0x1800c36fc  mov     word ptr [rbp+57h+var_78+8], ax
0x1800c3700  movzx   eax, word ptr [rbx+58h]
0x1800c3704  mov     word ptr [rbp+57h+var_78+0Ah], ax
0x1800c3708  movzx   eax, word ptr [rbx+5Ch]
0x1800c370c  mov     word ptr [rbp+57h+var_78+0Ch], ax
0x1800c3710  mov     eax, [rbx+68h]
0x1800c3713  mov     dword ptr [rbp+57h+var_78+0Eh], eax
0x1800c3716  mov     word ptr [rbp+57h+var_68+2], cx
0x1800c371a  cmp     esi, 1
0x1800c371d  jnz     short loc_1800C3773
0x1800c371f  mov     r9, [rbx+98h]; HDC
0x1800c3726  lea     rax, [rbp+57h+var_90]
0x1800c372a  mov     r8d, [rbx+4Ch]; int
0x1800c372e  mov     edx, [rbx+5Ch]; cy
0x1800c3731  mov     ecx, [rbx+58h]; cx
0x1800c3734  mov     [rsp+0C0h+var_98], rax; HBITMAP *
0x1800c3739  call    ?CreateDownlevelBitmap@@YAHHHHPEAUHDC__@@PEAUHBITMAP__@@PEAPEAU2@@Z; CreateDownlevelBitmap(int,int,int,HDC__ *,HBITMAP__ *,HBITMAP__ * *)
0x1800c373e  cmp     qword ptr [rbx+80h], 0
0x1800c3746  jz      short loc_1800C376B
0x1800c3748  mov     r9, [rbx+0A0h]; HDC
0x1800c374f  lea     rax, [rbp+57h+var_80]
0x1800c3753  mov     r8d, [rbx+4Ch]; int
0x1800c3757  mov     edx, [rbx+5Ch]; cy
0x1800c375a  mov     ecx, [rbx+58h]; cx
0x1800c375d  mov     [rsp+0C0h+var_98], rax; HBITMAP *
0x1800c3762  call    ?CreateDownlevelBitmap@@YAHHHHPEAUHDC__@@PEAUHBITMAP__@@PEAPEAU2@@Z; CreateDownlevelBitmap(int,int,int,HDC__ *,HBITMAP__ *,HBITMAP__ * *)
0x1800c3767  mov     r13, [rbp+57h+var_80]
0x1800c376b  mov     r15, [rbp+57h+var_90]
0x1800c376f  movzx   ecx, word ptr [rbp+57h+var_68+2]
0x1800c3773  cmp     qword ptr [rbx+210h], 0
0x1800c377b  jz      short loc_1800C3786
0x1800c377d  or      cx, 2000h
0x1800c3782  mov     word ptr [rbp+57h+var_68+2], cx
0x1800c3786  mov     edx, 4
0x1800c378b  cmp     edx, 0Fh
0x1800c378e  jge     short loc_1800C37AA
0x1800c3790  movsxd  rax, edx
0x1800c3793  cmp     dword ptr [rbx+rax*4+0A8h], 0FFFFFFFFh
0x1800c379b  jnz     short loc_1800C37A1
0x1800c379d  inc     edx
0x1800c379f  jmp     short loc_1800C378B
0x1800c37a1  or      cx, 1000h
0x1800c37a6  mov     word ptr [rbp+57h+var_68+2], cx
0x1800c37aa  xor     ecx, ecx
0x1800c37ac  movzx   eax, word ptr [rbx+rcx*4+0A8h]
0x1800c37b4  mov     word ptr [rbp+rcx*2+57h+var_68+4], ax
0x1800c37b9  inc     rcx
0x1800c37bc  cmp     rcx, 0Fh
0x1800c37c0  jnz     short loc_1800C37AC
0x1800c37c2  mov     rax, [r12]
0x1800c37c6  lea     r8d, [rcx+0Dh]
0x1800c37ca  xor     r9d, r9d
0x1800c37cd  lea     rdx, [rbp+57h+var_78]
0x1800c37d1  mov     rcx, r12
0x1800c37d4  mov     rax, [rax+20h]
0x1800c37d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c37dd  mov     edi, eax
0x1800c37df  test    eax, eax
0x1800c37e1  js      loc_1800C3982
0x1800c37e7  xor     r8d, r8d; unsigned int
0x1800c37ea  mov     rdx, r15; HBITMAP
0x1800c37ed  mov     rcx, r12; struct IStream *
0x1800c37f0  call    ?Stream_WriteBitmap@@YAJPEAUIStream@@PEAUHBITMAP__@@I@Z; Stream_WriteBitmap(IStream *,HBITMAP__ *,uint)
0x1800c37f5  mov     edi, eax
0x1800c37f7  test    eax, eax
0x1800c37f9  js      loc_1800C3982
0x1800c37ff  cmp     qword ptr [rbx+0A0h], 0
0x1800c3807  jz      short loc_1800C3824
0x1800c3809  mov     r8d, 1; unsigned int
0x1800c380f  mov     rdx, r13; HBITMAP
0x1800c3812  mov     rcx, r12; struct IStream *
0x1800c3815  call    ?Stream_WriteBitmap@@YAJPEAUIStream@@PEAUHBITMAP__@@I@Z; Stream_WriteBitmap(IStream *,HBITMAP__ *,uint)
0x1800c381a  mov     edi, eax
0x1800c381c  test    eax, eax
0x1800c381e  js      loc_1800C3982
0x1800c3824  mov     eax, 1000h
0x1800c3829  test    word ptr [rbp+57h+var_68+2], ax
0x1800c382d  jz      short loc_1800C384C
0x1800c382f  mov     rax, [r12]
0x1800c3833  lea     rdx, [rbp+57h+var_68+0Ch]
0x1800c3837  xor     r9d, r9d
0x1800c383a  mov     rcx, r12
0x1800c383d  mov     rax, [rax+20h]
0x1800c3841  lea     r8d, [r9+16h]
0x1800c3845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c384a  mov     edi, eax
0x1800c384c  mov     rcx, [rbx+210h]
0x1800c3853  test    rcx, rcx
0x1800c3856  jz      loc_1800C3968
0x1800c385c  add     rcx, 40h ; '@'; lpCriticalSection
0x1800c3860  call    cs:__imp_EnterCriticalSection
0x1800c3866  cmp     [rbp+57h+var_88], 1
0x1800c386a  mov     r8, [rbx+210h]
0x1800c3871  mov     rsi, [r8+0A0h]
0x1800c3878  mov     r14, [r8+0A8h]
0x1800c387f  mov     [rbp+57h+var_90], rsi
0x1800c3883  mov     [rbp+57h+var_80], r14
0x1800c3887  jnz     short loc_1800C38E0
0x1800c3889  mov     r9, [r8+0C0h]; HDC
0x1800c3890  lea     rax, [rbp+57h+var_90]
0x1800c3894  mov     r8d, [r8+74h]; int
0x1800c3898  mov     edx, [rbx+5Ch]; cy
0x1800c389b  mov     ecx, [rbx+58h]; cx
0x1800c389e  mov     [rsp+0C0h+var_98], rax; HBITMAP *
0x1800c38a3  call    ?CreateDownlevelBitmap@@YAHHHHPEAUHDC__@@PEAUHBITMAP__@@PEAPEAU2@@Z; CreateDownlevelBitmap(int,int,int,HDC__ *,HBITMAP__ *,HBITMAP__ * *)
0x1800c38a8  cmp     qword ptr [rbx+80h], 0
0x1800c38b0  jz      short loc_1800C38DC
0x1800c38b2  mov     r8, [rbx+210h]
0x1800c38b9  lea     rax, [rbp+57h+var_80]
0x1800c38bd  mov     edx, [rbx+5Ch]; cy
0x1800c38c0  mov     ecx, [rbx+58h]; cx
0x1800c38c3  mov     [rsp+0C0h+var_98], rax; HBITMAP *
0x1800c38c8  mov     r9, [r8+0C8h]; HDC
0x1800c38cf  mov     r8d, [r8+74h]; int
0x1800c38d3  call    ?CreateDownlevelBitmap@@YAHHHHPEAUHDC__@@PEAUHBITMAP__@@PEAPEAU2@@Z; CreateDownlevelBitmap(int,int,int,HDC__ *,HBITMAP__ *,HBITMAP__ * *)
0x1800c38d8  mov     r14, [rbp+57h+var_80]
0x1800c38dc  mov     rsi, [rbp+57h+var_90]
0x1800c38e0  xor     r8d, r8d; unsigned int
0x1800c38e3  mov     rdx, rsi; HBITMAP
0x1800c38e6  mov     rcx, r12; struct IStream *
0x1800c38e9  call    ?Stream_WriteBitmap@@YAJPEAUIStream@@PEAUHBITMAP__@@I@Z; Stream_WriteBitmap(IStream *,HBITMAP__ *,uint)
0x1800c38ee  mov     edi, eax
0x1800c38f0  mov     rax, [rbx+210h]
0x1800c38f7  cmp     qword ptr [rax+0C8h], 0
0x1800c38ff  jz      short loc_1800C391B
0x1800c3901  mov     r8d, 1; unsigned int
0x1800c3907  mov     rdx, r14; HBITMAP
0x1800c390a  mov     rcx, r12; struct IStream *
0x1800c390d  call    ?Stream_WriteBitmap@@YAJPEAUIStream@@PEAUHBITMAP__@@I@Z; Stream_WriteBitmap(IStream *,HBITMAP__ *,uint)
0x1800c3912  mov     edi, eax
0x1800c3914  mov     rax, [rbx+210h]
0x1800c391b  test    r14, r14
0x1800c391e  jz      short loc_1800C3939
0x1800c3920  cmp     r14, [rax+0A8h]
0x1800c3927  jz      short loc_1800C3939
0x1800c3929  mov     rcx, r14; ho
0x1800c392c  call    cs:__imp_DeleteObject
0x1800c3932  mov     rax, [rbx+210h]
0x1800c3939  test    rsi, rsi
0x1800c393c  jz      short loc_1800C3950
0x1800c393e  cmp     rsi, [rax+0A0h]
0x1800c3945  jz      short loc_1800C3950
0x1800c3947  mov     rcx, rsi; ho
0x1800c394a  call    cs:__imp_DeleteObject
0x1800c3950  mov     rcx, [rbx+210h]
0x1800c3957  add     rcx, 40h ; '@'; lpCriticalSection
0x1800c395b  call    cs:__imp_LeaveCriticalSection
0x1800c3961  mov     esi, [rbp+57h+var_88]
0x1800c3964  lea     r14, [rbx+18h]
0x1800c3968  test    edi, edi
0x1800c396a  js      short loc_1800C3982
0x1800c396c  cmp     esi, 1
0x1800c396f  jz      short loc_1800C3982
0x1800c3971  mov     rcx, [rbx+88h]
0x1800c3978  mov     rdx, r12
0x1800c397b  call    DSA_SaveStream
0x1800c3980  mov     edi, eax
0x1800c3982  test    r13, r13
0x1800c3985  jz      short loc_1800C3999
0x1800c3987  cmp     r13, [rbx+80h]
0x1800c398e  jz      short loc_1800C3999
0x1800c3990  mov     rcx, r13; ho
0x1800c3993  call    cs:__imp_DeleteObject
0x1800c3999  test    r15, r15
0x1800c399c  jz      short loc_1800C39AD
0x1800c399e  cmp     r15, [rbx+78h]
0x1800c39a2  jz      short loc_1800C39AD
0x1800c39a4  mov     rcx, r15; ho
0x1800c39a7  call    cs:__imp_DeleteObject
0x1800c39ad  mov     rcx, r14; lpCriticalSection
0x1800c39b0  call    cs:__imp_LeaveCriticalSection
0x1800c39b6  mov     eax, edi
0x1800c39b8  mov     rcx, [rbp+57h+var_40]
0x1800c39bc  xor     rcx, rsp; StackCookie
0x1800c39bf  call    __security_check_cookie
0x1800c39c4  mov     rbx, [rsp+0C0h+arg_8]
0x1800c39cc  add     rsp, 90h
0x1800c39d3  pop     r15
0x1800c39d5  pop     r14
0x1800c39d7  pop     r13
0x1800c39d9  pop     r12
0x1800c39db  pop     rdi
0x1800c39dc  pop     rsi
0x1800c39dd  pop     rbp
0x1800c39de  retn
```
